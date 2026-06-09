# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800038bc`
- end: `0x180003949`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003448`
- `0x1800069a0`
- `0x1800074b0`
- `0x1800219ab`

## callees

- `0x1800038bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003938`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003905`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000392a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003905`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000392a`

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
0x1800038bc  mov     [rsp+arg_0], rbx
0x1800038c1  push    rdi
0x1800038c2  sub     rsp, 20h
0x1800038c6  mov     rdi, [rcx+0B0h]
0x1800038cd  mov     rbx, rcx
0x1800038d0  mov     qword ptr [rcx+0B0h], 0
0x1800038db  test    rdi, rdi
0x1800038de  jz      short loc_1800038F4
0x1800038e0  call    cs:__imp_GetProcessHeap
0x1800038e6  mov     r8, rdi; lpMem
0x1800038e9  xor     edx, edx; dwFlags
0x1800038eb  mov     rcx, rax; hHeap
0x1800038ee  call    cs:__imp_HeapFree
0x1800038f4  mov     rdi, [rbx+70h]
0x1800038f8  mov     qword ptr [rbx+70h], 0
0x180003900  test    rdi, rdi
0x180003903  jz      short loc_180003919
0x180003905  call    cs:__imp_GetProcessHeap
0x18000390b  mov     r8, rdi; lpMem
0x18000390e  xor     edx, edx; dwFlags
0x180003910  mov     rcx, rax; hHeap
0x180003913  call    cs:__imp_HeapFree
0x180003919  mov     rdi, [rbx+30h]
0x18000391d  mov     qword ptr [rbx+30h], 0
0x180003925  test    rdi, rdi
0x180003928  jz      short loc_18000393E
0x18000392a  call    cs:__imp_GetProcessHeap
0x180003930  mov     r8, rdi; lpMem
0x180003933  xor     edx, edx; dwFlags
0x180003935  mov     rcx, rax; hHeap
0x180003938  call    cs:__imp_HeapFree
0x18000393e  mov     rbx, [rsp+28h+arg_0]
0x180003943  add     rsp, 20h
0x180003947  pop     rdi
0x180003948  retn
```
