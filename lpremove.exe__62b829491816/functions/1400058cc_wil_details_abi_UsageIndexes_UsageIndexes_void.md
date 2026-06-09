# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1400058cc`
- end: `0x140005959`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400052b4`
- `0x140009790`
- `0x14000a2a0`
- `0x140010086`

## callees

- `0x1400058cc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400058f0`
- `KERNEL32!GetProcessHeap` at `0x140005915`
- `KERNEL32!GetProcessHeap` at `0x14000593a`
- `KERNEL32!GetProcessHeap` at `0x1400058f0`
- `KERNEL32!GetProcessHeap` at `0x140005915`
- `KERNEL32!GetProcessHeap` at `0x14000593a`
- `KERNEL32!HeapFree` at `0x1400058fe`
- `KERNEL32!HeapFree` at `0x140005923`
- `KERNEL32!HeapFree` at `0x140005948`
- `KERNEL32!HeapFree` at `0x1400058fe`
- `KERNEL32!HeapFree` at `0x140005923`
- `KERNEL32!HeapFree` at `0x140005948`

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
0x1400058cc  mov     [rsp+arg_0], rbx
0x1400058d1  push    rdi
0x1400058d2  sub     rsp, 20h
0x1400058d6  mov     rdi, [rcx+0B0h]
0x1400058dd  mov     rbx, rcx
0x1400058e0  mov     qword ptr [rcx+0B0h], 0
0x1400058eb  test    rdi, rdi
0x1400058ee  jz      short loc_140005904
0x1400058f0  call    cs:__imp_GetProcessHeap
0x1400058f6  mov     r8, rdi; lpMem
0x1400058f9  xor     edx, edx; dwFlags
0x1400058fb  mov     rcx, rax; hHeap
0x1400058fe  call    cs:__imp_HeapFree
0x140005904  mov     rdi, [rbx+70h]
0x140005908  mov     qword ptr [rbx+70h], 0
0x140005910  test    rdi, rdi
0x140005913  jz      short loc_140005929
0x140005915  call    cs:__imp_GetProcessHeap
0x14000591b  mov     r8, rdi; lpMem
0x14000591e  xor     edx, edx; dwFlags
0x140005920  mov     rcx, rax; hHeap
0x140005923  call    cs:__imp_HeapFree
0x140005929  mov     rdi, [rbx+30h]
0x14000592d  mov     qword ptr [rbx+30h], 0
0x140005935  test    rdi, rdi
0x140005938  jz      short loc_14000594E
0x14000593a  call    cs:__imp_GetProcessHeap
0x140005940  mov     r8, rdi; lpMem
0x140005943  xor     edx, edx; dwFlags
0x140005945  mov     rcx, rax; hHeap
0x140005948  call    cs:__imp_HeapFree
0x14000594e  mov     rbx, [rsp+28h+arg_0]
0x140005953  add     rsp, 20h
0x140005957  pop     rdi
0x140005958  retn
```
