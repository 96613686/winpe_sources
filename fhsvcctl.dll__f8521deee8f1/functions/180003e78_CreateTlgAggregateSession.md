# CreateTlgAggregateSession

- ea: `0x180003e78`
- end: `0x180003f4e`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004998`

## callees

- `0x180003bdc`
- `0x180003e78`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x180003ec0`
- `KERNEL32!InitializeSRWLock` at `0x180003ec0`
- `KERNEL32!HeapFree` at `0x180003f33`
- `KERNEL32!HeapFree` at `0x180003f33`
- `KERNEL32!CreateThreadpoolTimer` at `0x180003ee2`
- `KERNEL32!CreateThreadpoolTimer` at `0x180003ee2`
- `KERNEL32!HeapAlloc` at `0x180003ea6`
- `KERNEL32!HeapAlloc` at `0x180003ea6`
- `KERNEL32!GetProcessHeap` at `0x180003e92`
- `KERNEL32!GetProcessHeap` at `0x180003f25`
- `KERNEL32!GetProcessHeap` at `0x180003e92`
- `KERNEL32!GetProcessHeap` at `0x180003f25`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  HANDLE v6; // rax

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_18000A720 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    if ( v5 )
    {
      CancelTimerCallbacksAndDeleteTimer((__int64)v5);
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180003e78  mov     [rsp+arg_0], rbx
0x180003e7d  mov     [rsp+arg_18], rsi
0x180003e82  push    rdi
0x180003e83  sub     rsp, 20h
0x180003e87  mov     sil, cl
0x180003e8a  xor     dil, dil
0x180003e8d  mov     [rsp+28h+arg_8], dil
0x180003e92  call    cs:__imp_GetProcessHeap
0x180003e98  mov     rcx, rax; hHeap
0x180003e9b  mov     edx, 8; dwFlags
0x180003ea0  mov     r8d, 168h; dwBytes
0x180003ea6  call    cs:__imp_HeapAlloc
0x180003eac  mov     rbx, rax
0x180003eaf  mov     [rsp+28h+arg_10], rax
0x180003eb4  test    rax, rax
0x180003eb7  jz      short loc_180003F13
0x180003eb9  lea     rcx, [rax+108h]; SRWLock
0x180003ec0  call    cs:__imp_InitializeSRWLock
0x180003ec6  test    sil, sil
0x180003ec9  jz      short loc_180003F10
0x180003ecb  mov     ecx, cs:dword_18000A720
0x180003ed1  test    ecx, ecx
0x180003ed3  jnz     short loc_180003F13
0x180003ed5  xor     r8d, r8d; pcbe
0x180003ed8  mov     rdx, rbx; pv
0x180003edb  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180003ee2  call    cs:__imp_CreateThreadpoolTimer
0x180003ee8  mov     [rbx+158h], rax
0x180003eef  jmp     short loc_180003F06
0x180003ef1  mov     eax, 1
0x180003ef6  xchg    eax, cs:dword_18000A720
0x180003efc  mov     dil, [rsp+28h+arg_8]
0x180003f01  mov     rbx, [rsp+28h+arg_10]
0x180003f06  cmp     qword ptr [rbx+158h], 0
0x180003f0e  jz      short loc_180003F13
0x180003f10  mov     dil, 1
0x180003f13  test    dil, dil
0x180003f16  jnz     short loc_180003F3B
0x180003f18  test    rbx, rbx
0x180003f1b  jz      short loc_180003F39
0x180003f1d  mov     rcx, rbx
0x180003f20  call    CancelTimerCallbacksAndDeleteTimer
0x180003f25  call    cs:__imp_GetProcessHeap
0x180003f2b  mov     rcx, rax; hHeap
0x180003f2e  mov     r8, rbx; lpMem
0x180003f31  xor     edx, edx; dwFlags
0x180003f33  call    cs:__imp_HeapFree
0x180003f39  xor     ebx, ebx
0x180003f3b  mov     rax, rbx
0x180003f3e  mov     rbx, [rsp+28h+arg_0]
0x180003f43  mov     rsi, [rsp+28h+arg_18]
0x180003f48  add     rsp, 20h
0x180003f4c  pop     rdi
0x180003f4d  retn
0x1800052b6  push    rbp
0x1800052b8  sub     rsp, 20h
0x1800052bc  mov     rbp, rdx
0x1800052bf  mov     rax, [rcx]
0x1800052c2  xor     ecx, ecx
0x1800052c4  cmp     dword ptr [rax], 0C000000Dh
0x1800052ca  setz    cl
0x1800052cd  mov     eax, ecx
0x1800052cf  add     rsp, 20h
0x1800052d3  pop     rbp
0x1800052d4  retn
```
