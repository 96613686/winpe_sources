# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140005848`
- end: `0x1400058c4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004e84`

## callees

- `0x140005848`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000586d`
- `KERNEL32!GetProcessHeap` at `0x14000589e`
- `KERNEL32!GetProcessHeap` at `0x14000586d`
- `KERNEL32!GetProcessHeap` at `0x14000589e`
- `KERNEL32!HeapFree` at `0x14000587b`
- `KERNEL32!HeapFree` at `0x1400058ac`
- `KERNEL32!HeapFree` at `0x14000587b`
- `KERNEL32!HeapFree` at `0x1400058ac`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x140005848  push    rbx
0x14000584a  push    rbp
0x14000584b  push    rsi
0x14000584c  push    rdi
0x14000584d  sub     rsp, 28h
0x140005851  movzx   eax, word ptr [rcx+20h]
0x140005855  mov     rsi, rcx
0x140005858  mov     rdi, [rcx+18h]
0x14000585c  lea     rbp, [rax+rax*4]
0x140005860  shl     rbp, 4
0x140005864  add     rbp, rdi
0x140005867  jmp     short loc_140005895
0x140005869  mov     rbx, [rdi+40h]
0x14000586d  call    cs:__imp_GetProcessHeap
0x140005873  mov     r8, rbx; lpMem
0x140005876  xor     edx, edx; dwFlags
0x140005878  mov     rcx, rax; hHeap
0x14000587b  call    cs:__imp_HeapFree
0x140005881  mov     qword ptr [rdi+40h], 0
0x140005889  mov     qword ptr [rdi+48h], 0
0x140005891  add     rdi, 50h ; 'P'
0x140005895  cmp     rdi, rbp
0x140005898  jnz     short loc_140005869
0x14000589a  mov     rbx, [rsi+18h]
0x14000589e  call    cs:__imp_GetProcessHeap
0x1400058a4  mov     r8, rbx; lpMem
0x1400058a7  xor     edx, edx; dwFlags
0x1400058a9  mov     rcx, rax; hHeap
0x1400058ac  call    cs:__imp_HeapFree
0x1400058b2  xor     eax, eax
0x1400058b4  mov     [rsi+20h], eax
0x1400058b7  mov     [rsi+18h], rax
0x1400058bb  add     rsp, 28h
0x1400058bf  pop     rdi
0x1400058c0  pop     rsi
0x1400058c1  pop     rbp
0x1400058c2  pop     rbx
0x1400058c3  retn
```
