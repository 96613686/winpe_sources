# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x18000420c`
- end: `0x180004299`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d98`
- `0x1800071a0`
- `0x180007fec`
- `0x180011db7`

## callees

- `0x18000420c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004230`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004255`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000427a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004230`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004255`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000427a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000423e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004263`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004288`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000423e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004263`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004288`

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
0x18000420c  mov     [rsp+arg_0], rbx
0x180004211  push    rdi
0x180004212  sub     rsp, 20h
0x180004216  mov     rdi, [rcx+0B0h]
0x18000421d  mov     rbx, rcx
0x180004220  mov     qword ptr [rcx+0B0h], 0
0x18000422b  test    rdi, rdi
0x18000422e  jz      short loc_180004244
0x180004230  call    cs:__imp_GetProcessHeap
0x180004236  mov     r8, rdi; lpMem
0x180004239  xor     edx, edx; dwFlags
0x18000423b  mov     rcx, rax; hHeap
0x18000423e  call    cs:__imp_HeapFree
0x180004244  mov     rdi, [rbx+70h]
0x180004248  mov     qword ptr [rbx+70h], 0
0x180004250  test    rdi, rdi
0x180004253  jz      short loc_180004269
0x180004255  call    cs:__imp_GetProcessHeap
0x18000425b  mov     r8, rdi; lpMem
0x18000425e  xor     edx, edx; dwFlags
0x180004260  mov     rcx, rax; hHeap
0x180004263  call    cs:__imp_HeapFree
0x180004269  mov     rdi, [rbx+30h]
0x18000426d  mov     qword ptr [rbx+30h], 0
0x180004275  test    rdi, rdi
0x180004278  jz      short loc_18000428E
0x18000427a  call    cs:__imp_GetProcessHeap
0x180004280  mov     r8, rdi; lpMem
0x180004283  xor     edx, edx; dwFlags
0x180004285  mov     rcx, rax; hHeap
0x180004288  call    cs:__imp_HeapFree
0x18000428e  mov     rbx, [rsp+28h+arg_0]
0x180004293  add     rsp, 20h
0x180004297  pop     rdi
0x180004298  retn
```
