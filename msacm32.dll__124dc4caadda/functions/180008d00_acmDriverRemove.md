# acmDriverRemove

- ea: `0x180008d00`
- end: `0x180008dd1`
- name: `acmDriverRemove`
- size: `209`
- prototype: `MMRESULT __stdcall(HACMDRIVERID hadid, DWORD fdwRemove)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001570`
- `0x180001a40`
- `0x180001dc0`
- `0x1800023c0`
- `0x180002a80`
- `0x180003ec0`
- `0x180003f40`
- `0x180005760`
- `0x180008d00`
- `0x180008dd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008da7`

## pseudocode

```c
MMRESULT __stdcall acmDriverRemove(HACMDRIVERID hadid, DWORD fdwRemove)
{
  __int64 v4; // rdi
  int v6; // esi
  MMRESULT v7; // ebp

  v4 = pagFindAndBoot();
  if ( !v4 )
    return 1;
  if ( !(unsigned int)ValidateHandle(hadid, 1) )
    return 5;
  if ( (fdwRemove & 0xFFFFFFFE) != 0 )
    return 10;
  v6 = *((_DWORD *)hadid + 14);
  if ( (unsigned int)threadQueryInListShared(v4) )
    return 512;
  AcquireLockExclusive((LPCRITICAL_SECTION)(v4 + 128));
  v7 = IDriverRemove((__int64)hadid, fdwRemove);
  ReleaseLock(v4 + 128);
  if ( v7 )
    return v7;
  if ( (v6 & 0x40000000) == 0 && (v6 & 0x10000000) == 0 )
  {
    IDriverRefreshPriority(v4);
    GetCurrentThreadId();
    if ( !*(_QWORD *)(v4 + 120) )
    {
      IDriverPrioritiesSave(v4);
      IDriverBroadcastNotify(v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008d00  push    rbx
0x180008d02  push    rbp
0x180008d03  push    rsi
0x180008d04  push    rdi
0x180008d05  push    r14
0x180008d07  sub     rsp, 20h
0x180008d0b  mov     r14d, edx
0x180008d0e  mov     rbp, rcx
0x180008d11  call    pagFindAndBoot
0x180008d16  mov     rdi, rax
0x180008d19  test    rax, rax
0x180008d1c  jnz     short loc_180008D26
0x180008d1e  lea     eax, [rdi+1]
0x180008d21  jmp     loc_180008DC6
0x180008d26  mov     edx, 1
0x180008d2b  mov     rcx, rbp
0x180008d2e  call    ValidateHandle
0x180008d33  test    eax, eax
0x180008d35  jnz     short loc_180008D41
0x180008d37  mov     eax, 5
0x180008d3c  jmp     loc_180008DC6
0x180008d41  test    r14d, 0FFFFFFFEh
0x180008d48  jz      short loc_180008D51
0x180008d4a  mov     eax, 0Ah
0x180008d4f  jmp     short loc_180008DC6
0x180008d51  mov     esi, [rbp+38h]
0x180008d54  mov     rcx, rdi
0x180008d57  call    threadQueryInListShared
0x180008d5c  test    eax, eax
0x180008d5e  jz      short loc_180008D67
0x180008d60  mov     eax, 200h
0x180008d65  jmp     short loc_180008DC6
0x180008d67  lea     rbx, [rdi+80h]
0x180008d6e  mov     rcx, rbx; lpCriticalSection
0x180008d71  call    AcquireLockExclusive
0x180008d76  mov     edx, r14d
0x180008d79  mov     rcx, rbp
0x180008d7c  call    IDriverRemove
0x180008d81  mov     rcx, rbx
0x180008d84  mov     ebp, eax
0x180008d86  call    ReleaseLock
0x180008d8b  test    ebp, ebp
0x180008d8d  jz      short loc_180008D93
0x180008d8f  mov     eax, ebp
0x180008d91  jmp     short loc_180008DC6
0x180008d93  bt      esi, 1Eh
0x180008d97  jb      short loc_180008DC4
0x180008d99  bt      esi, 1Ch
0x180008d9d  jb      short loc_180008DC4
0x180008d9f  mov     rcx, rdi
0x180008da2  call    IDriverRefreshPriority
0x180008da7  call    cs:__imp_GetCurrentThreadId
0x180008dad  cmp     qword ptr [rdi+78h], 0
0x180008db2  jnz     short loc_180008DC4
0x180008db4  mov     rcx, rdi
0x180008db7  call    IDriverPrioritiesSave
0x180008dbc  mov     rcx, rdi
0x180008dbf  call    IDriverBroadcastNotify
0x180008dc4  xor     eax, eax
0x180008dc6  add     rsp, 20h
0x180008dca  pop     r14
0x180008dcc  pop     rdi
0x180008dcd  pop     rsi
0x180008dce  pop     rbp
0x180008dcf  pop     rbx
0x180008dd0  retn
```
