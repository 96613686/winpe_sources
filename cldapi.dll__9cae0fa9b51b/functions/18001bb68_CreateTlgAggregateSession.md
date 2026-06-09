# CreateTlgAggregateSession

- ea: `0x18001bb68`
- end: `0x18001bc3e`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c76c`

## callees

- `0x18001bb68`
- `0x18001bc44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bb9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bb9c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001bbbc`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001bbbc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bbe4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bbe4`

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
    if ( !a1 || !dword_18002AB98 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18001bb68  mov     [rsp+arg_0], rbx
0x18001bb6d  mov     [rsp+arg_18], rsi
0x18001bb72  push    rdi
0x18001bb73  sub     rsp, 20h
0x18001bb77  mov     sil, cl
0x18001bb7a  xor     dil, dil
0x18001bb7d  mov     [rsp+28h+arg_8], dil
0x18001bb82  call    cs:__imp_GetProcessHeap
0x18001bb89  nop     dword ptr [rax+rax+00h]
0x18001bb8e  mov     rcx, rax; hHeap
0x18001bb91  mov     edx, 8; dwFlags
0x18001bb96  mov     r8d, 168h; dwBytes
0x18001bb9c  call    cs:__imp_HeapAlloc
0x18001bba3  nop     dword ptr [rax+rax+00h]
0x18001bba8  mov     rbx, rax
0x18001bbab  mov     [rsp+28h+arg_10], rax
0x18001bbb0  test    rax, rax
0x18001bbb3  jz      short loc_18001BC1B
0x18001bbb5  lea     rcx, [rax+108h]; SRWLock
0x18001bbbc  call    cs:__imp_InitializeSRWLock
0x18001bbc3  nop     dword ptr [rax+rax+00h]
0x18001bbc8  test    sil, sil
0x18001bbcb  jz      short loc_18001BC18
0x18001bbcd  mov     ecx, cs:dword_18002AB98
0x18001bbd3  test    ecx, ecx
0x18001bbd5  jnz     short loc_18001BC1B
0x18001bbd7  xor     r8d, r8d; pcbe
0x18001bbda  mov     rdx, rbx; pv
0x18001bbdd  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18001bbe4  call    cs:__imp_CreateThreadpoolTimer
0x18001bbeb  nop     dword ptr [rax+rax+00h]
0x18001bbf0  mov     [rbx+158h], rax
0x18001bbf7  jmp     short loc_18001BC0E
0x18001bbf9  mov     eax, 1
0x18001bbfe  xchg    eax, cs:dword_18002AB98
0x18001bc04  mov     dil, [rsp+28h+arg_8]
0x18001bc09  mov     rbx, [rsp+28h+arg_10]
0x18001bc0e  cmp     qword ptr [rbx+158h], 0
0x18001bc16  jz      short loc_18001BC1B
0x18001bc18  mov     dil, 1
0x18001bc1b  test    dil, dil
0x18001bc1e  jnz     short loc_18001BC2A
0x18001bc20  mov     rcx, rbx; lpMem
0x18001bc23  call    DestroyAggregateSession
0x18001bc28  xor     ebx, ebx
0x18001bc2a  mov     rax, rbx
0x18001bc2d  mov     rbx, [rsp+28h+arg_0]
0x18001bc32  mov     rsi, [rsp+28h+arg_18]
0x18001bc37  add     rsp, 20h
0x18001bc3b  pop     rdi
0x18001bc3c  retn
0x18001d1d6  push    rbp
0x18001d1d8  sub     rsp, 20h
0x18001d1dc  mov     rbp, rdx
0x18001d1df  mov     rax, [rcx]
0x18001d1e2  xor     ecx, ecx
0x18001d1e4  cmp     dword ptr [rax], 0C000000Dh
0x18001d1ea  setz    cl
0x18001d1ed  mov     eax, ecx
0x18001d1ef  add     rsp, 20h
0x18001d1f3  pop     rbp
0x18001d1f4  retn
```
