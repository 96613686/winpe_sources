# acmDriverEnum

- ea: `0x180002900`
- end: `0x180002a6c`
- name: `acmDriverEnum`
- size: `364`
- prototype: `MMRESULT __stdcall(ACMDRIVERENUMCB fnCallback, DWORD_PTR dwInstance, DWORD fdwEnum)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180001a40`
- `0x180001ad0`
- `0x1800021e0`
- `0x180002220`
- `0x1800023c0`
- `0x180002900`
- `0x180002a80`
- `0x180003f40`
- `0x180004ab0`
- `0x180004af0`
- `0x180008dd8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002952`

## pseudocode

```c
MMRESULT __stdcall acmDriverEnum(ACMDRIVERENUMCB fnCallback, DWORD_PTR dwInstance, DWORD fdwEnum)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rbp
  int v9; // edx
  unsigned int v10; // ecx
  __int64 v11; // r8
  __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  v6 = pagFindAndBoot();
  v7 = v6;
  if ( !v6 )
    return 1;
  if ( !fnCallback )
    return 11;
  if ( (fdwEnum & 0xFFFFFFF) != 0 )
    return 10;
  if ( !(unsigned int)threadQueryInListShared(v6) )
  {
    GetCurrentThreadId();
    if ( !*(_QWORD *)(v7 + 120) )
    {
      AcquireLockExclusive((LPCRITICAL_SECTION)(v7 + 128));
      if ( (unsigned int)IDriverPrioritiesRestore(v7) )
        IDriverBroadcastNotify(v7);
      ReleaseLock(v7 + 128);
    }
  }
  v8 = 0;
  v13 = 0;
  AcquireLockShared((LPCRITICAL_SECTION)(v7 + 128));
  threadEnterListShared(v7);
  while ( !(unsigned int)IDriverGetNext(v7, &v13, v8, fdwEnum) )
  {
    v8 = v13;
    if ( v13 )
    {
      v9 = *(_DWORD *)(v13 + 56);
      v10 = *(_DWORD *)(v13 + 60) | 0x80000000;
      if ( v9 >= 0 )
        v10 = *(_DWORD *)(v13 + 60);
      v11 = v10;
      LODWORD(v11) = v10 | 0x40000000;
      if ( (v9 & 0x40000000) == 0 )
        v11 = v10;
      if ( (v9 & 0x10000000) != 0 )
        v11 = (unsigned int)v11 | 0x10000000;
      if ( !((unsigned int (__fastcall *)(__int64, DWORD_PTR, __int64))fnCallback)(v13, dwInstance, v11) )
        break;
    }
  }
  threadLeaveListShared(v7);
  ReleaseLock(v7 + 128);
  return 0;
}

```

## disassembly

```asm
0x180002900  mov     [rsp+arg_10], rbx
0x180002905  push    rsi
0x180002906  push    rdi
0x180002907  push    r14
0x180002909  sub     rsp, 20h
0x18000290d  mov     edi, r8d
0x180002910  mov     r14, rdx
0x180002913  mov     rsi, rcx
0x180002916  call    pagFindAndBoot
0x18000291b  mov     rbx, rax
0x18000291e  test    rax, rax
0x180002921  jz      loc_180002A32
0x180002927  test    rsi, rsi
0x18000292a  jz      loc_180002A58
0x180002930  test    edi, 0FFFFFFFh
0x180002936  jnz     loc_180002A45
0x18000293c  mov     [rsp+38h+arg_0], rbp
0x180002941  mov     rcx, rax
0x180002944  mov     [rsp+38h+arg_8], r15
0x180002949  call    threadQueryInListShared
0x18000294e  test    eax, eax
0x180002950  jnz     short loc_180002987
0x180002952  call    cs:__imp_GetCurrentThreadId
0x180002958  cmp     qword ptr [rbx+78h], 0
0x18000295d  jnz     short loc_180002987
0x18000295f  lea     rcx, [rbx+80h]; lpCriticalSection
0x180002966  call    AcquireLockExclusive
0x18000296b  mov     rcx, rbx
0x18000296e  call    IDriverPrioritiesRestore
0x180002973  test    eax, eax
0x180002975  jnz     loc_180002A5F
0x18000297b  lea     rcx, [rbx+80h]
0x180002982  call    ReleaseLock
0x180002987  xor     ebp, ebp
0x180002989  lea     rcx, [rbx+80h]; lpCriticalSection
0x180002990  mov     [rsp+38h+arg_18], rbp
0x180002995  call    AcquireLockShared
0x18000299a  mov     rcx, rbx
0x18000299d  call    threadEnterListShared
0x1800029a2  mov     r9d, edi
0x1800029a5  lea     rdx, [rsp+38h+arg_18]
0x1800029aa  mov     r8, rbp
0x1800029ad  mov     rcx, rbx
0x1800029b0  call    IDriverGetNext
0x1800029b5  test    eax, eax
0x1800029b7  jnz     short loc_180002A04
0x1800029b9  mov     rbp, [rsp+38h+arg_18]
0x1800029be  test    rbp, rbp
0x1800029c1  jz      short loc_1800029A2
0x1800029c3  mov     edx, [rbp+38h]
0x1800029c6  mov     ecx, [rbp+3Ch]
0x1800029c9  bts     ecx, 1Fh
0x1800029cd  test    edx, edx
0x1800029cf  cmovns  ecx, [rbp+3Ch]
0x1800029d3  mov     r8d, ecx
0x1800029d6  bts     r8d, 1Eh
0x1800029db  bt      edx, 1Eh
0x1800029df  cmovnb  r8d, ecx
0x1800029e3  mov     rcx, rbp
0x1800029e6  mov     eax, r8d
0x1800029e9  bts     eax, 1Ch
0x1800029ed  bt      edx, 1Ch
0x1800029f1  mov     rdx, r14
0x1800029f4  cmovb   r8d, eax
0x1800029f8  mov     rax, rsi
0x1800029fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a00  test    eax, eax
0x180002a02  jnz     short loc_1800029A2
0x180002a04  mov     rcx, rbx
0x180002a07  call    threadLeaveListShared
0x180002a0c  lea     rcx, [rbx+80h]
0x180002a13  call    ReleaseLock
0x180002a18  mov     r15, [rsp+38h+arg_8]
0x180002a1d  xor     eax, eax
0x180002a1f  mov     rbp, [rsp+38h+arg_0]
0x180002a24  mov     rbx, [rsp+38h+arg_10]
0x180002a29  add     rsp, 20h
0x180002a2d  pop     r14
0x180002a2f  pop     rdi
0x180002a30  pop     rsi
0x180002a31  retn
0x180002a32  mov     eax, 1
0x180002a37  mov     rbx, [rsp+38h+arg_10]
0x180002a3c  add     rsp, 20h
0x180002a40  pop     r14
0x180002a42  pop     rdi
0x180002a43  pop     rsi
0x180002a44  retn
0x180002a45  mov     rbx, [rsp+38h+arg_10]
0x180002a4a  mov     eax, 0Ah
0x180002a4f  add     rsp, 20h
0x180002a53  pop     r14
0x180002a55  pop     rdi
0x180002a56  pop     rsi
0x180002a57  retn
0x180002a58  mov     eax, 0Bh
0x180002a5d  jmp     short loc_180002A24
0x180002a5f  mov     rcx, rbx
0x180002a62  call    IDriverBroadcastNotify
0x180002a67  jmp     loc_18000297B
```
