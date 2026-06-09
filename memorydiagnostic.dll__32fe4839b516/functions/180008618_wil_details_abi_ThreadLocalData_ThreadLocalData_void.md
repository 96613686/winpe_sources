# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180008618`
- end: `0x1800086d2`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800076f4`

## callees

- `0x180008618`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008656`
- `KERNEL32!GetProcessHeap` at `0x18000868e`
- `KERNEL32!GetProcessHeap` at `0x180008656`
- `KERNEL32!GetProcessHeap` at `0x18000868e`
- `KERNEL32!HeapFree` at `0x18000866a`
- `KERNEL32!HeapFree` at `0x1800086a2`
- `KERNEL32!HeapFree` at `0x18000866a`
- `KERNEL32!HeapFree` at `0x1800086a2`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax

  v1 = *((_QWORD *)this + 3);
  v3 = v1 + 80LL * *((unsigned __int16 *)this + 16);
  if ( v1 != v3 )
  {
    v4 = v1 + 64;
    do
    {
      v5 = *(void **)v4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *(_QWORD *)v4 = 0;
      *(_QWORD *)(v4 + 8) = 0;
      v4 += 80;
    }
    while ( v4 - 64 != v3 );
  }
  v7 = (void *)*((_QWORD *)this + 3);
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v7);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180008618  mov     rax, rsp
0x18000861b  mov     [rax+8], rbx
0x18000861f  mov     [rax+10h], rbp
0x180008623  mov     [rax+18h], rsi
0x180008627  mov     [rax+20h], rdi
0x18000862b  push    r14
0x18000862d  sub     rsp, 20h
0x180008631  mov     rdi, [rcx+18h]
0x180008635  xor     r14d, r14d
0x180008638  movzx   eax, word ptr [rcx+20h]
0x18000863c  mov     rbp, rcx
0x18000863f  lea     rsi, [rax+rax*4]
0x180008643  shl     rsi, 4
0x180008647  add     rsi, rdi
0x18000864a  cmp     rdi, rsi
0x18000864d  jz      short loc_18000868A
0x18000864f  add     rdi, 40h ; '@'
0x180008653  mov     rbx, [rdi]
0x180008656  call    cs:__imp_GetProcessHeap
0x18000865d  nop     dword ptr [rax+rax+00h]
0x180008662  mov     r8, rbx; lpMem
0x180008665  xor     edx, edx; dwFlags
0x180008667  mov     rcx, rax; hHeap
0x18000866a  call    cs:__imp_HeapFree
0x180008671  nop     dword ptr [rax+rax+00h]
0x180008676  mov     [rdi], r14
0x180008679  mov     [rdi+8], r14
0x18000867d  lea     rdi, [rdi+50h]
0x180008681  lea     rax, [rdi-40h]
0x180008685  cmp     rax, rsi
0x180008688  jnz     short loc_180008653
0x18000868a  mov     rbx, [rbp+18h]
0x18000868e  call    cs:__imp_GetProcessHeap
0x180008695  nop     dword ptr [rax+rax+00h]
0x18000869a  mov     r8, rbx; lpMem
0x18000869d  xor     edx, edx; dwFlags
0x18000869f  mov     rcx, rax; hHeap
0x1800086a2  call    cs:__imp_HeapFree
0x1800086a9  nop     dword ptr [rax+rax+00h]
0x1800086ae  mov     rbx, [rsp+28h+arg_0]
0x1800086b3  mov     rsi, [rsp+28h+arg_10]
0x1800086b8  mov     rdi, [rsp+28h+arg_18]
0x1800086bd  mov     [rbp+20h], r14d
0x1800086c1  mov     [rbp+18h], r14
0x1800086c5  mov     rbp, [rsp+28h+arg_8]
0x1800086ca  add     rsp, 20h
0x1800086ce  pop     r14
0x1800086d0  retn
```
