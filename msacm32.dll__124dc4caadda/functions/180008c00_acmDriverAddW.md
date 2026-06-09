# acmDriverAddW

- ea: `0x180008c00`
- end: `0x180008cfa`
- name: `acmDriverAddW`
- size: `250`
- prototype: `MMRESULT __stdcall(LPHACMDRIVERID phadid, HINSTANCE hinstModule, LPARAM lParam, DWORD dwPriority, DWORD fdwAdd)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b0a0`

## callees

- `0x180001570`
- `0x180001a40`
- `0x180001dc0`
- `0x1800023c0`
- `0x180002a80`
- `0x180003e80`
- `0x180003f40`
- `0x180004b70`
- `0x180008c00`
- `0x180008dd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ccc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ccc`

## pseudocode

```c
MMRESULT __stdcall acmDriverAddW(
        LPHACMDRIVERID phadid,
        HINSTANCE hinstModule,
        LPARAM lParam,
        DWORD dwPriority,
        DWORD fdwAdd)
{
  __int64 v10; // rax
  __int64 v11; // rdi
  MMRESULT v12; // ebp

  if ( !(unsigned int)ValidateWritePointer(phadid, 8) )
    return 11;
  if ( (fdwAdd & 0xFFFFFFF0) != 0 )
    return 10;
  v10 = pagFindAndBoot();
  v11 = v10;
  if ( !v10 )
    return 1;
  if ( (unsigned int)threadQueryInListShared(v10) )
    return 512;
  AcquireLockExclusive((LPCRITICAL_SECTION)(v11 + 128));
  v12 = IDriverAdd(v11, (__int64 *)phadid, hinstModule, (HWND)lParam, dwPriority, fdwAdd);
  ReleaseLock(v11 + 128);
  if ( v12 )
    return v12;
  if ( ((_DWORD)(*phadid)[14] & 0x40000000) == 0 && ((_DWORD)(*phadid)[14] & 0x10000000) == 0 )
  {
    IDriverRefreshPriority(v11);
    GetCurrentThreadId();
    if ( !*(_QWORD *)(v11 + 120) )
    {
      IDriverPrioritiesSave(v11);
      IDriverBroadcastNotify(v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008c00  push    rbx
0x180008c02  push    rbp
0x180008c03  push    rsi
0x180008c04  push    rdi
0x180008c05  push    r12
0x180008c07  push    r14
0x180008c09  push    r15
0x180008c0b  sub     rsp, 30h
0x180008c0f  mov     r12, rdx
0x180008c12  mov     r14d, r9d
0x180008c15  mov     edx, 8
0x180008c1a  mov     r15, r8
0x180008c1d  mov     rsi, rcx
0x180008c20  call    ValidateWritePointer
0x180008c25  test    eax, eax
0x180008c27  jnz     short loc_180008C33
0x180008c29  mov     eax, 0Bh
0x180008c2e  jmp     loc_180008CEB
0x180008c33  mov     ebp, [rsp+68h+fdwAdd]
0x180008c3a  test    ebp, 0FFFFFFF0h
0x180008c40  jz      short loc_180008C4C
0x180008c42  mov     eax, 0Ah
0x180008c47  jmp     loc_180008CEB
0x180008c4c  call    pagFindAndBoot
0x180008c51  mov     rdi, rax
0x180008c54  test    rax, rax
0x180008c57  jnz     short loc_180008C61
0x180008c59  lea     eax, [rdi+1]
0x180008c5c  jmp     loc_180008CEB
0x180008c61  mov     rcx, rdi
0x180008c64  call    threadQueryInListShared
0x180008c69  test    eax, eax
0x180008c6b  jz      short loc_180008C74
0x180008c6d  mov     eax, 200h
0x180008c72  jmp     short loc_180008CEB
0x180008c74  lea     rbx, [rdi+80h]
0x180008c7b  mov     rcx, rbx; lpCriticalSection
0x180008c7e  call    AcquireLockExclusive
0x180008c83  mov     r9, r15
0x180008c86  mov     [rsp+68h+var_40], ebp
0x180008c8a  mov     r8, r12
0x180008c8d  mov     [rsp+68h+var_48], r14d
0x180008c92  mov     rdx, rsi
0x180008c95  mov     rcx, rdi
0x180008c98  call    IDriverAdd
0x180008c9d  mov     rcx, rbx
0x180008ca0  mov     ebp, eax
0x180008ca2  call    ReleaseLock
0x180008ca7  test    ebp, ebp
0x180008ca9  jz      short loc_180008CAF
0x180008cab  mov     eax, ebp
0x180008cad  jmp     short loc_180008CEB
0x180008caf  mov     rax, [rsi]
0x180008cb2  test    dword ptr [rax+38h], 40000000h
0x180008cb9  jnz     short loc_180008CE9
0x180008cbb  test    dword ptr [rax+38h], 10000000h
0x180008cc2  jnz     short loc_180008CE9
0x180008cc4  mov     rcx, rdi
0x180008cc7  call    IDriverRefreshPriority
0x180008ccc  call    cs:__imp_GetCurrentThreadId
0x180008cd2  cmp     qword ptr [rdi+78h], 0
0x180008cd7  jnz     short loc_180008CE9
0x180008cd9  mov     rcx, rdi
0x180008cdc  call    IDriverPrioritiesSave
0x180008ce1  mov     rcx, rdi
0x180008ce4  call    IDriverBroadcastNotify
0x180008ce9  xor     eax, eax
0x180008ceb  add     rsp, 30h
0x180008cef  pop     r15
0x180008cf1  pop     r14
0x180008cf3  pop     r12
0x180008cf5  pop     rdi
0x180008cf6  pop     rsi
0x180008cf7  pop     rbp
0x180008cf8  pop     rbx
0x180008cf9  retn
```
