# acmDriverPriority

- ea: `0x1800089c0`
- end: `0x180008bed`
- name: `acmDriverPriority`
- size: `557`
- prototype: `MMRESULT __stdcall(HACMDRIVERID hadid, DWORD dwPriority, DWORD fdwPriority)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180001570`
- `0x180001a40`
- `0x180001ad0`
- `0x180001dc0`
- `0x1800021e0`
- `0x180002220`
- `0x1800023c0`
- `0x180002a80`
- `0x180003ec0`
- `0x180003f40`
- `0x180004ab0`
- `0x180004af0`
- `0x180007720`
- `0x1800089c0`
- `0x180008dd8`
- `0x18000afdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a05`

## pseudocode

```c
MMRESULT __stdcall acmDriverPriority(HACMDRIVERID hadid, DWORD dwPriority, DWORD fdwPriority)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // rbx
  DWORD v11; // esi
  __int64 v12; // rcx
  int v13; // r14d
  int v14; // ebp
  DWORD v15; // ebx
  __int64 v16; // r8
  MMRESULT v17; // esi
  __int64 v18; // [rsp+88h] [rbp+20h] BYREF

  v6 = pagFindAndBoot();
  v7 = v6;
  if ( !v6 )
    return 1;
  if ( (unsigned int)threadQueryInListShared(v6) )
    return 512;
  CurrentThreadId = GetCurrentThreadId();
  if ( (fdwPriority & 0xFFFCFFFC) != 0 )
    return 10;
  v10 = CurrentThreadId;
  if ( !(unsigned int)IDriverLockPriority(v7, CurrentThreadId, 5) )
    return 4;
  if ( !*(_QWORD *)(v7 + 120) )
  {
    AcquireLockExclusive((LPCRITICAL_SECTION)(v7 + 128));
    if ( (unsigned int)IDriverPrioritiesRestore(v7) )
      IDriverBroadcastNotify(v7);
    ReleaseLock(v7 + 128);
  }
  if ( !hadid )
  {
    v11 = fdwPriority & 0x30000;
    if ( v11 != 0x10000 )
    {
      if ( v11 == 0x20000 )
      {
        if ( (unsigned int)IDriverLockPriority(v7, v10, 2) )
        {
LABEL_15:
          IDriverPrioritiesSave(v12);
          IDriverBroadcastNotify(v7);
          return 0;
        }
        return 4;
      }
      return 10;
    }
    if ( (unsigned int)IDriverLockPriority(v7, v10, 1) )
      return 0;
    return 4;
  }
  if ( !(unsigned int)ValidateHandle(hadid, 1) )
    return 5;
  v13 = (_DWORD)hadid[14] & 0x10000000;
  v14 = (_DWORD)hadid[14] & 0x40000000;
  if ( dwPriority )
  {
    if ( v13 || v14 )
      return 8;
    if ( dwPriority != -1 )
    {
      v15 = 0;
      v18 = 0;
      AcquireLockShared((LPCRITICAL_SECTION)(v7 + 128));
      threadEnterListShared(v7);
      v16 = 0;
      while ( !(unsigned int)IDriverGetNext(v7, &v18, v16, 0xC0000000) )
      {
        v16 = v18;
        ++v15;
      }
      threadLeaveListShared(v7);
      ReleaseLock(v7 + 128);
      if ( dwPriority > v15 )
        return 11;
    }
  }
  AcquireLockExclusive((LPCRITICAL_SECTION)(v7 + 128));
  v17 = IDriverPriority(v7, hadid, dwPriority, fdwPriority);
  ReleaseLock(v7 + 128);
  if ( !v17 )
  {
    if ( v14 )
      return 0;
    if ( v13 )
      return 0;
    IDriverRefreshPriority(v7);
    if ( *(_QWORD *)(v7 + 120) )
      return 0;
    v12 = v7;
    goto LABEL_15;
  }
  return v17;
}

```

## disassembly

```asm
0x1800089c0  push    rbx
0x1800089c2  push    rbp
0x1800089c3  push    rsi
0x1800089c4  push    rdi
0x1800089c5  push    r12
0x1800089c7  push    r13
0x1800089c9  push    r14
0x1800089cb  push    r15
0x1800089cd  sub     rsp, 28h
0x1800089d1  mov     esi, r8d
0x1800089d4  mov     r12d, edx
0x1800089d7  mov     r15, rcx
0x1800089da  call    pagFindAndBoot
0x1800089df  mov     rdi, rax
0x1800089e2  test    rax, rax
0x1800089e5  jnz     short loc_1800089EF
0x1800089e7  lea     eax, [rdi+1]
0x1800089ea  jmp     loc_180008BDC
0x1800089ef  mov     rcx, rdi
0x1800089f2  call    threadQueryInListShared
0x1800089f7  test    eax, eax
0x1800089f9  jz      short loc_180008A05
0x1800089fb  mov     eax, 200h
0x180008a00  jmp     loc_180008BDC
0x180008a05  call    cs:__imp_GetCurrentThreadId
0x180008a0b  test    esi, 0FFFCFFFCh
0x180008a11  jnz     loc_180008BD7
0x180008a17  mov     r14d, 5
0x180008a1d  mov     edx, eax
0x180008a1f  mov     r8d, r14d
0x180008a22  mov     ebx, eax
0x180008a24  mov     rcx, rdi
0x180008a27  call    IDriverLockPriority
0x180008a2c  test    eax, eax
0x180008a2e  jz      loc_180008AC1
0x180008a34  cmp     qword ptr [rdi+78h], 0
0x180008a39  jnz     short loc_180008A66
0x180008a3b  lea     rbp, [rdi+80h]
0x180008a42  mov     rcx, rbp; lpCriticalSection
0x180008a45  call    AcquireLockExclusive
0x180008a4a  mov     rcx, rdi
0x180008a4d  call    IDriverPrioritiesRestore
0x180008a52  test    eax, eax
0x180008a54  jz      short loc_180008A5E
0x180008a56  mov     rcx, rdi
0x180008a59  call    IDriverBroadcastNotify
0x180008a5e  mov     rcx, rbp
0x180008a61  call    ReleaseLock
0x180008a66  test    r15, r15
0x180008a69  jnz     short loc_180008ACB
0x180008a6b  and     esi, 30000h
0x180008a71  cmp     esi, 10000h
0x180008a77  jz      short loc_180008AAC
0x180008a79  cmp     esi, 20000h
0x180008a7f  jnz     loc_180008BD7
0x180008a85  lea     r8d, [r15+2]
0x180008a89  mov     rdx, rbx
0x180008a8c  mov     rcx, rdi
0x180008a8f  call    IDriverLockPriority
0x180008a94  test    eax, eax
0x180008a96  jz      short loc_180008AC1
0x180008a98  call    IDriverPrioritiesSave
0x180008a9d  mov     rcx, rdi
0x180008aa0  call    IDriverBroadcastNotify
0x180008aa5  xor     eax, eax
0x180008aa7  jmp     loc_180008BDC
0x180008aac  mov     r8d, 1
0x180008ab2  mov     rdx, rbx
0x180008ab5  mov     rcx, rdi
0x180008ab8  call    IDriverLockPriority
0x180008abd  test    eax, eax
0x180008abf  jnz     short loc_180008AA5
0x180008ac1  mov     eax, 4
0x180008ac6  jmp     loc_180008BDC
0x180008acb  mov     edx, 1
0x180008ad0  mov     rcx, r15
0x180008ad3  call    ValidateHandle
0x180008ad8  test    eax, eax
0x180008ada  jnz     short loc_180008AE4
0x180008adc  mov     eax, r14d
0x180008adf  jmp     loc_180008BDC
0x180008ae4  mov     ebp, [r15+38h]
0x180008ae8  mov     r14d, ebp
0x180008aeb  and     r14d, 10000000h
0x180008af2  and     ebp, 40000000h
0x180008af8  test    r12d, r12d
0x180008afb  jz      short loc_180008B79
0x180008afd  test    r14d, r14d
0x180008b00  jnz     short loc_180008B72
0x180008b02  test    ebp, ebp
0x180008b04  jnz     short loc_180008B72
0x180008b06  cmp     r12d, 0FFFFFFFFh
0x180008b0a  jz      short loc_180008B79
0x180008b0c  lea     r13, [rdi+80h]
0x180008b13  xor     ebx, ebx
0x180008b15  mov     rcx, r13; lpCriticalSection
0x180008b18  mov     [rsp+68h+arg_18], rbx
0x180008b20  call    AcquireLockShared
0x180008b25  mov     rcx, rdi
0x180008b28  call    threadEnterListShared
0x180008b2d  xor     r8d, r8d
0x180008b30  jmp     short loc_180008B3C
0x180008b32  mov     r8, [rsp+68h+arg_18]
0x180008b3a  inc     ebx
0x180008b3c  mov     r9d, 0C0000000h
0x180008b42  lea     rdx, [rsp+68h+arg_18]
0x180008b4a  mov     rcx, rdi
0x180008b4d  call    IDriverGetNext
0x180008b52  test    eax, eax
0x180008b54  jz      short loc_180008B32
0x180008b56  mov     rcx, rdi
0x180008b59  call    threadLeaveListShared
0x180008b5e  mov     rcx, r13
0x180008b61  call    ReleaseLock
0x180008b66  cmp     r12d, ebx
0x180008b69  jbe     short loc_180008B79
0x180008b6b  mov     eax, 0Bh
0x180008b70  jmp     short loc_180008BDC
0x180008b72  mov     eax, 8
0x180008b77  jmp     short loc_180008BDC
0x180008b79  lea     rbx, [rdi+80h]
0x180008b80  mov     rcx, rbx; lpCriticalSection
0x180008b83  call    AcquireLockExclusive
0x180008b88  mov     r9d, esi
0x180008b8b  mov     r8d, r12d
0x180008b8e  mov     rdx, r15
0x180008b91  mov     rcx, rdi
0x180008b94  call    IDriverPriority
0x180008b99  mov     rcx, rbx
0x180008b9c  mov     esi, eax
0x180008b9e  call    ReleaseLock
0x180008ba3  test    esi, esi
0x180008ba5  jz      short loc_180008BAB
0x180008ba7  mov     eax, esi
0x180008ba9  jmp     short loc_180008BDC
0x180008bab  test    ebp, ebp
0x180008bad  jnz     loc_180008AA5
0x180008bb3  test    r14d, r14d
0x180008bb6  jnz     loc_180008AA5
0x180008bbc  mov     rcx, rdi
0x180008bbf  call    IDriverRefreshPriority
0x180008bc4  cmp     qword ptr [rdi+78h], 0
0x180008bc9  jnz     loc_180008AA5
0x180008bcf  mov     rcx, rdi
0x180008bd2  jmp     loc_180008A98
0x180008bd7  mov     eax, 0Ah
0x180008bdc  add     rsp, 28h
0x180008be0  pop     r15
0x180008be2  pop     r14
0x180008be4  pop     r13
0x180008be6  pop     r12
0x180008be8  pop     rdi
0x180008be9  pop     rsi
0x180008bea  pop     rbp
0x180008beb  pop     rbx
0x180008bec  retn
```
