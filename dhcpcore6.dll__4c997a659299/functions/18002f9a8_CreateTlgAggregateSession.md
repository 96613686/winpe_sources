# CreateTlgAggregateSession

- ea: `0x18002f9a8`
- end: `0x18002fa7e`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030174`

## callees

- `0x18002f9a8`
- `0x18002fa84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f9dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f9dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9c2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002f9fc`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002f9fc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fa24`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fa24`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_180042728 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18002f9a8  mov     [rsp+arg_0], rbx
0x18002f9ad  mov     [rsp+arg_18], rsi
0x18002f9b2  push    rdi
0x18002f9b3  sub     rsp, 20h
0x18002f9b7  mov     sil, cl
0x18002f9ba  xor     dil, dil
0x18002f9bd  mov     [rsp+28h+arg_8], dil
0x18002f9c2  call    cs:__imp_GetProcessHeap
0x18002f9c9  nop     dword ptr [rax+rax+00h]
0x18002f9ce  mov     rcx, rax; hHeap
0x18002f9d1  mov     edx, 8; dwFlags
0x18002f9d6  mov     r8d, 168h; dwBytes
0x18002f9dc  call    cs:__imp_HeapAlloc
0x18002f9e3  nop     dword ptr [rax+rax+00h]
0x18002f9e8  mov     rbx, rax
0x18002f9eb  mov     [rsp+28h+arg_10], rax
0x18002f9f0  test    rax, rax
0x18002f9f3  jz      short loc_18002FA5B
0x18002f9f5  lea     rcx, [rax+108h]; SRWLock
0x18002f9fc  call    cs:__imp_InitializeSRWLock
0x18002fa03  nop     dword ptr [rax+rax+00h]
0x18002fa08  test    sil, sil
0x18002fa0b  jz      short loc_18002FA58
0x18002fa0d  mov     ecx, cs:dword_180042728
0x18002fa13  test    ecx, ecx
0x18002fa15  jnz     short loc_18002FA5B
0x18002fa17  xor     r8d, r8d; pcbe
0x18002fa1a  mov     rdx, rbx; pv
0x18002fa1d  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18002fa24  call    cs:__imp_CreateThreadpoolTimer
0x18002fa2b  nop     dword ptr [rax+rax+00h]
0x18002fa30  mov     [rbx+158h], rax
0x18002fa37  jmp     short loc_18002FA4E
0x18002fa39  mov     eax, 1
0x18002fa3e  xchg    eax, cs:dword_180042728
0x18002fa44  mov     dil, [rsp+28h+arg_8]
0x18002fa49  mov     rbx, [rsp+28h+arg_10]
0x18002fa4e  cmp     qword ptr [rbx+158h], 0
0x18002fa56  jz      short loc_18002FA5B
0x18002fa58  mov     dil, 1
0x18002fa5b  test    dil, dil
0x18002fa5e  jnz     short loc_18002FA6A
0x18002fa60  mov     rcx, rbx; lpMem
0x18002fa63  call    DestroyAggregateSession
0x18002fa68  xor     ebx, ebx
0x18002fa6a  mov     rax, rbx
0x18002fa6d  mov     rbx, [rsp+28h+arg_0]
0x18002fa72  mov     rsi, [rsp+28h+arg_18]
0x18002fa77  add     rsp, 20h
0x18002fa7b  pop     rdi
0x18002fa7c  retn
0x180030a36  push    rbp
0x180030a38  sub     rsp, 20h
0x180030a3c  mov     rbp, rdx
0x180030a3f  mov     rax, [rcx]
0x180030a42  xor     ecx, ecx
0x180030a44  cmp     dword ptr [rax], 0C000000Dh
0x180030a4a  setz    cl
0x180030a4d  mov     eax, ecx
0x180030a4f  add     rsp, 20h
0x180030a53  pop     rbp
0x180030a54  retn
```
