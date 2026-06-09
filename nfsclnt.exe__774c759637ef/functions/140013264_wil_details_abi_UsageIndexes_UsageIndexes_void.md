# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140013264`
- end: `0x1400132f1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140012f14`
- `0x140015aac`
- `0x140016560`

## callees

- `0x140013264`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140013296`
- `KERNEL32!HeapFree` at `0x1400132bb`
- `KERNEL32!HeapFree` at `0x1400132e0`
- `KERNEL32!HeapFree` at `0x140013296`
- `KERNEL32!HeapFree` at `0x1400132bb`
- `KERNEL32!HeapFree` at `0x1400132e0`
- `KERNEL32!GetProcessHeap` at `0x140013288`
- `KERNEL32!GetProcessHeap` at `0x1400132ad`
- `KERNEL32!GetProcessHeap` at `0x1400132d2`
- `KERNEL32!GetProcessHeap` at `0x140013288`
- `KERNEL32!GetProcessHeap` at `0x1400132ad`
- `KERNEL32!GetProcessHeap` at `0x1400132d2`

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
0x140013264  mov     [rsp+arg_0], rbx
0x140013269  push    rdi
0x14001326a  sub     rsp, 20h
0x14001326e  mov     rdi, [rcx+0B0h]
0x140013275  mov     rbx, rcx
0x140013278  mov     qword ptr [rcx+0B0h], 0
0x140013283  test    rdi, rdi
0x140013286  jz      short loc_14001329C
0x140013288  call    cs:__imp_GetProcessHeap
0x14001328e  mov     r8, rdi; lpMem
0x140013291  xor     edx, edx; dwFlags
0x140013293  mov     rcx, rax; hHeap
0x140013296  call    cs:__imp_HeapFree
0x14001329c  mov     rdi, [rbx+70h]
0x1400132a0  mov     qword ptr [rbx+70h], 0
0x1400132a8  test    rdi, rdi
0x1400132ab  jz      short loc_1400132C1
0x1400132ad  call    cs:__imp_GetProcessHeap
0x1400132b3  mov     r8, rdi; lpMem
0x1400132b6  xor     edx, edx; dwFlags
0x1400132b8  mov     rcx, rax; hHeap
0x1400132bb  call    cs:__imp_HeapFree
0x1400132c1  mov     rdi, [rbx+30h]
0x1400132c5  mov     qword ptr [rbx+30h], 0
0x1400132cd  test    rdi, rdi
0x1400132d0  jz      short loc_1400132E6
0x1400132d2  call    cs:__imp_GetProcessHeap
0x1400132d8  mov     r8, rdi; lpMem
0x1400132db  xor     edx, edx; dwFlags
0x1400132dd  mov     rcx, rax; hHeap
0x1400132e0  call    cs:__imp_HeapFree
0x1400132e6  mov     rbx, [rsp+28h+arg_0]
0x1400132eb  add     rsp, 20h
0x1400132ef  pop     rdi
0x1400132f0  retn
```
