# CreateTlgAggregateSession

- ea: `0x18001e5f8`
- end: `0x18001e6ce`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f118`

## callees

- `0x18001e35c`
- `0x18001e5f8`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18001e662`
- `KERNEL32!CreateThreadpoolTimer` at `0x18001e662`
- `KERNEL32!InitializeSRWLock` at `0x18001e640`
- `KERNEL32!InitializeSRWLock` at `0x18001e640`
- `KERNEL32!HeapFree` at `0x18001e6b3`
- `KERNEL32!HeapFree` at `0x18001e6b3`
- `KERNEL32!HeapAlloc` at `0x18001e626`
- `KERNEL32!HeapAlloc` at `0x18001e626`
- `KERNEL32!GetProcessHeap` at `0x18001e612`
- `KERNEL32!GetProcessHeap` at `0x18001e6a5`
- `KERNEL32!GetProcessHeap` at `0x18001e612`
- `KERNEL32!GetProcessHeap` at `0x18001e6a5`

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
    if ( !a1 || !dword_18002FEA4 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18001e5f8  mov     [rsp+arg_0], rbx
0x18001e5fd  mov     [rsp+arg_18], rsi
0x18001e602  push    rdi
0x18001e603  sub     rsp, 20h
0x18001e607  mov     sil, cl
0x18001e60a  xor     dil, dil
0x18001e60d  mov     [rsp+28h+arg_8], dil
0x18001e612  call    cs:__imp_GetProcessHeap
0x18001e618  mov     rcx, rax; hHeap
0x18001e61b  mov     edx, 8; dwFlags
0x18001e620  mov     r8d, 168h; dwBytes
0x18001e626  call    cs:__imp_HeapAlloc
0x18001e62c  mov     rbx, rax
0x18001e62f  mov     [rsp+28h+arg_10], rax
0x18001e634  test    rax, rax
0x18001e637  jz      short loc_18001E693
0x18001e639  lea     rcx, [rax+108h]; SRWLock
0x18001e640  call    cs:__imp_InitializeSRWLock
0x18001e646  test    sil, sil
0x18001e649  jz      short loc_18001E690
0x18001e64b  mov     ecx, cs:dword_18002FEA4
0x18001e651  test    ecx, ecx
0x18001e653  jnz     short loc_18001E693
0x18001e655  xor     r8d, r8d; pcbe
0x18001e658  mov     rdx, rbx; pv
0x18001e65b  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18001e662  call    cs:__imp_CreateThreadpoolTimer
0x18001e668  mov     [rbx+158h], rax
0x18001e66f  jmp     short loc_18001E686
0x18001e671  mov     eax, 1
0x18001e676  xchg    eax, cs:dword_18002FEA4
0x18001e67c  mov     dil, [rsp+28h+arg_8]
0x18001e681  mov     rbx, [rsp+28h+arg_10]
0x18001e686  cmp     qword ptr [rbx+158h], 0
0x18001e68e  jz      short loc_18001E693
0x18001e690  mov     dil, 1
0x18001e693  test    dil, dil
0x18001e696  jnz     short loc_18001E6BB
0x18001e698  test    rbx, rbx
0x18001e69b  jz      short loc_18001E6B9
0x18001e69d  mov     rcx, rbx
0x18001e6a0  call    CancelTimerCallbacksAndDeleteTimer
0x18001e6a5  call    cs:__imp_GetProcessHeap
0x18001e6ab  mov     rcx, rax; hHeap
0x18001e6ae  mov     r8, rbx; lpMem
0x18001e6b1  xor     edx, edx; dwFlags
0x18001e6b3  call    cs:__imp_HeapFree
0x18001e6b9  xor     ebx, ebx
0x18001e6bb  mov     rax, rbx
0x18001e6be  mov     rbx, [rsp+28h+arg_0]
0x18001e6c3  mov     rsi, [rsp+28h+arg_18]
0x18001e6c8  add     rsp, 20h
0x18001e6cc  pop     rdi
0x18001e6cd  retn
0x180020934  push    rbp
0x180020936  sub     rsp, 20h
0x18002093a  mov     rbp, rdx
0x18002093d  mov     rax, [rcx]
0x180020940  xor     ecx, ecx
0x180020942  cmp     dword ptr [rax], 0C000000Dh
0x180020948  setz    cl
0x18002094b  mov     eax, ecx
0x18002094d  add     rsp, 20h
0x180020951  pop     rbp
0x180020952  retn
```
