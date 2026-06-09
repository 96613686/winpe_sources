# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800086b8`
- end: `0x180008745`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000824c`
- `0x18000af30`
- `0x18000b9f4`
- `0x180016250`

## callees

- `0x1800086b8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800086ea`
- `KERNEL32!HeapFree` at `0x18000870f`
- `KERNEL32!HeapFree` at `0x180008734`
- `KERNEL32!HeapFree` at `0x1800086ea`
- `KERNEL32!HeapFree` at `0x18000870f`
- `KERNEL32!HeapFree` at `0x180008734`
- `KERNEL32!GetProcessHeap` at `0x1800086dc`
- `KERNEL32!GetProcessHeap` at `0x180008701`
- `KERNEL32!GetProcessHeap` at `0x180008726`
- `KERNEL32!GetProcessHeap` at `0x1800086dc`
- `KERNEL32!GetProcessHeap` at `0x180008701`
- `KERNEL32!GetProcessHeap` at `0x180008726`

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
0x1800086b8  mov     [rsp+arg_0], rbx
0x1800086bd  push    rdi
0x1800086be  sub     rsp, 20h
0x1800086c2  mov     rdi, [rcx+0B0h]
0x1800086c9  mov     rbx, rcx
0x1800086cc  mov     qword ptr [rcx+0B0h], 0
0x1800086d7  test    rdi, rdi
0x1800086da  jz      short loc_1800086F0
0x1800086dc  call    cs:__imp_GetProcessHeap
0x1800086e2  mov     r8, rdi; lpMem
0x1800086e5  xor     edx, edx; dwFlags
0x1800086e7  mov     rcx, rax; hHeap
0x1800086ea  call    cs:__imp_HeapFree
0x1800086f0  mov     rdi, [rbx+70h]
0x1800086f4  mov     qword ptr [rbx+70h], 0
0x1800086fc  test    rdi, rdi
0x1800086ff  jz      short loc_180008715
0x180008701  call    cs:__imp_GetProcessHeap
0x180008707  mov     r8, rdi; lpMem
0x18000870a  xor     edx, edx; dwFlags
0x18000870c  mov     rcx, rax; hHeap
0x18000870f  call    cs:__imp_HeapFree
0x180008715  mov     rdi, [rbx+30h]
0x180008719  mov     qword ptr [rbx+30h], 0
0x180008721  test    rdi, rdi
0x180008724  jz      short loc_18000873A
0x180008726  call    cs:__imp_GetProcessHeap
0x18000872c  mov     r8, rdi; lpMem
0x18000872f  xor     edx, edx; dwFlags
0x180008731  mov     rcx, rax; hHeap
0x180008734  call    cs:__imp_HeapFree
0x18000873a  mov     rbx, [rsp+28h+arg_0]
0x18000873f  add     rsp, 20h
0x180008743  pop     rdi
0x180008744  retn
```
