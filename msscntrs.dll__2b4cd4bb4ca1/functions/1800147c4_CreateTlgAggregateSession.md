# CreateTlgAggregateSession

- ea: `0x1800147c4`
- end: `0x18001489a`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800152e8`

## callees

- `0x180014528`
- `0x1800147c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001480c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001480c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800147f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800147f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014871`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001487f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001487f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001482e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001482e`

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
    if ( !a1 || !dword_1800222F0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800147c4  mov     [rsp+arg_0], rbx
0x1800147c9  mov     [rsp+arg_18], rsi
0x1800147ce  push    rdi
0x1800147cf  sub     rsp, 20h
0x1800147d3  mov     sil, cl
0x1800147d6  xor     dil, dil
0x1800147d9  mov     [rsp+28h+arg_8], dil
0x1800147de  call    cs:__imp_GetProcessHeap
0x1800147e4  mov     rcx, rax; hHeap
0x1800147e7  mov     edx, 8; dwFlags
0x1800147ec  mov     r8d, 168h; dwBytes
0x1800147f2  call    cs:__imp_HeapAlloc
0x1800147f8  mov     rbx, rax
0x1800147fb  mov     [rsp+28h+arg_10], rax
0x180014800  test    rax, rax
0x180014803  jz      short loc_18001485F
0x180014805  lea     rcx, [rax+108h]; SRWLock
0x18001480c  call    cs:__imp_InitializeSRWLock
0x180014812  test    sil, sil
0x180014815  jz      short loc_18001485C
0x180014817  mov     ecx, cs:dword_1800222F0
0x18001481d  test    ecx, ecx
0x18001481f  jnz     short loc_18001485F
0x180014821  xor     r8d, r8d; pcbe
0x180014824  mov     rdx, rbx; pv
0x180014827  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18001482e  call    cs:__imp_CreateThreadpoolTimer
0x180014834  mov     [rbx+158h], rax
0x18001483b  jmp     short loc_180014852
0x18001483d  mov     eax, 1
0x180014842  xchg    eax, cs:dword_1800222F0
0x180014848  mov     dil, [rsp+28h+arg_8]
0x18001484d  mov     rbx, [rsp+28h+arg_10]
0x180014852  cmp     qword ptr [rbx+158h], 0
0x18001485a  jz      short loc_18001485F
0x18001485c  mov     dil, 1
0x18001485f  test    dil, dil
0x180014862  jnz     short loc_180014887
0x180014864  test    rbx, rbx
0x180014867  jz      short loc_180014885
0x180014869  mov     rcx, rbx
0x18001486c  call    CancelTimerCallbacksAndDeleteTimer
0x180014871  call    cs:__imp_GetProcessHeap
0x180014877  mov     rcx, rax; hHeap
0x18001487a  mov     r8, rbx; lpMem
0x18001487d  xor     edx, edx; dwFlags
0x18001487f  call    cs:__imp_HeapFree
0x180014885  xor     ebx, ebx
0x180014887  mov     rax, rbx
0x18001488a  mov     rbx, [rsp+28h+arg_0]
0x18001488f  mov     rsi, [rsp+28h+arg_18]
0x180014894  add     rsp, 20h
0x180014898  pop     rdi
0x180014899  retn
0x180016e95  push    rbp
0x180016e97  sub     rsp, 20h
0x180016e9b  mov     rbp, rdx
0x180016e9e  mov     rax, [rcx]
0x180016ea1  xor     ecx, ecx
0x180016ea3  cmp     dword ptr [rax], 0C000000Dh
0x180016ea9  setz    cl
0x180016eac  mov     eax, ecx
0x180016eae  add     rsp, 20h
0x180016eb2  pop     rbp
0x180016eb3  retn
```
