# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180004694`
- end: `0x180004721`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004220`
- `0x180008920`
- `0x180009440`
- `0x18001424f`

## callees

- `0x180004694`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004710`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004710`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004702`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004702`

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
0x180004694  mov     [rsp+arg_0], rbx
0x180004699  push    rdi
0x18000469a  sub     rsp, 20h
0x18000469e  mov     rdi, [rcx+0B0h]
0x1800046a5  mov     rbx, rcx
0x1800046a8  mov     qword ptr [rcx+0B0h], 0
0x1800046b3  test    rdi, rdi
0x1800046b6  jz      short loc_1800046CC
0x1800046b8  call    cs:__imp_GetProcessHeap
0x1800046be  mov     r8, rdi; lpMem
0x1800046c1  xor     edx, edx; dwFlags
0x1800046c3  mov     rcx, rax; hHeap
0x1800046c6  call    cs:__imp_HeapFree
0x1800046cc  mov     rdi, [rbx+70h]
0x1800046d0  mov     qword ptr [rbx+70h], 0
0x1800046d8  test    rdi, rdi
0x1800046db  jz      short loc_1800046F1
0x1800046dd  call    cs:__imp_GetProcessHeap
0x1800046e3  mov     r8, rdi; lpMem
0x1800046e6  xor     edx, edx; dwFlags
0x1800046e8  mov     rcx, rax; hHeap
0x1800046eb  call    cs:__imp_HeapFree
0x1800046f1  mov     rdi, [rbx+30h]
0x1800046f5  mov     qword ptr [rbx+30h], 0
0x1800046fd  test    rdi, rdi
0x180004700  jz      short loc_180004716
0x180004702  call    cs:__imp_GetProcessHeap
0x180004708  mov     r8, rdi; lpMem
0x18000470b  xor     edx, edx; dwFlags
0x18000470d  mov     rcx, rax; hHeap
0x180004710  call    cs:__imp_HeapFree
0x180004716  mov     rbx, [rsp+28h+arg_0]
0x18000471b  add     rsp, 20h
0x18000471f  pop     rdi
0x180004720  retn
```
