# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1400131fc`
- end: `0x140013289`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140012ef8`
- `0x140014f9c`
- `0x14001594c`
- `0x140018d67`

## callees

- `0x1400131fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013220`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001326a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013220`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001326a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001322e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013278`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001322e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013278`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x1400131fc  mov     [rsp+arg_0], rbx
0x140013201  push    rdi
0x140013202  sub     rsp, 20h
0x140013206  mov     rdi, [rcx+0B0h]
0x14001320d  mov     rbx, rcx
0x140013210  mov     qword ptr [rcx+0B0h], 0
0x14001321b  test    rdi, rdi
0x14001321e  jz      short loc_140013234
0x140013220  call    cs:__imp_GetProcessHeap
0x140013226  mov     r8, rdi; lpMem
0x140013229  xor     edx, edx; dwFlags
0x14001322b  mov     rcx, rax; hHeap
0x14001322e  call    cs:__imp_HeapFree
0x140013234  mov     rdi, [rbx+70h]
0x140013238  mov     qword ptr [rbx+70h], 0
0x140013240  test    rdi, rdi
0x140013243  jz      short loc_140013259
0x140013245  call    cs:__imp_GetProcessHeap
0x14001324b  mov     r8, rdi; lpMem
0x14001324e  xor     edx, edx; dwFlags
0x140013250  mov     rcx, rax; hHeap
0x140013253  call    cs:__imp_HeapFree
0x140013259  mov     rdi, [rbx+30h]
0x14001325d  mov     qword ptr [rbx+30h], 0
0x140013265  test    rdi, rdi
0x140013268  jz      short loc_14001327E
0x14001326a  call    cs:__imp_GetProcessHeap
0x140013270  mov     r8, rdi; lpMem
0x140013273  xor     edx, edx; dwFlags
0x140013275  mov     rcx, rax; hHeap
0x140013278  call    cs:__imp_HeapFree
0x14001327e  mov     rbx, [rsp+28h+arg_0]
0x140013283  add     rsp, 20h
0x140013287  pop     rdi
0x140013288  retn
```
