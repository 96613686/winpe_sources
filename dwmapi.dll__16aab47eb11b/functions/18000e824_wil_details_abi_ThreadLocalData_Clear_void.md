# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x18000e824`
- end: `0x18000e8b4`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `144`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e598`

## callees

- `0x18000c788`
- `0x18000e824`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e854`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e887`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e854`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e887`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e862`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e895`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e862`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e895`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
{
  __int64 i; // rdi
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(v7, *((_QWORD *)this + 3));
  for ( i = v7[0]; i != v7[1]; i += 80 )
  {
    v3 = *(void **)(i + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *(_QWORD *)(i + 64) = 0;
    *(_QWORD *)(i + 72) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  v6 = GetProcessHeap();
  HeapFree(v6, 0, v5);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000e824  mov     [rsp+arg_0], rbx
0x18000e829  mov     [rsp+arg_8], rsi
0x18000e82e  push    rdi
0x18000e82f  sub     rsp, 30h
0x18000e833  movzx   r8d, word ptr [rcx+20h]
0x18000e838  mov     rsi, rcx
0x18000e83b  mov     rdx, [rcx+18h]
0x18000e83f  lea     rcx, [rsp+38h+var_18]
0x18000e844  call    ??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z; wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)
0x18000e849  mov     rdi, [rsp+38h+var_18]
0x18000e84e  jmp     short loc_18000E87C
0x18000e850  mov     rbx, [rdi+40h]
0x18000e854  call    cs:__imp_GetProcessHeap
0x18000e85a  mov     r8, rbx; lpMem
0x18000e85d  xor     edx, edx; dwFlags
0x18000e85f  mov     rcx, rax; hHeap
0x18000e862  call    cs:__imp_HeapFree
0x18000e868  mov     qword ptr [rdi+40h], 0
0x18000e870  mov     qword ptr [rdi+48h], 0
0x18000e878  add     rdi, 50h ; 'P'
0x18000e87c  cmp     rdi, [rsp+38h+var_10]
0x18000e881  jnz     short loc_18000E850
0x18000e883  mov     rbx, [rsi+18h]
0x18000e887  call    cs:__imp_GetProcessHeap
0x18000e88d  mov     r8, rbx; lpMem
0x18000e890  xor     edx, edx; dwFlags
0x18000e892  mov     rcx, rax; hHeap
0x18000e895  call    cs:__imp_HeapFree
0x18000e89b  mov     rbx, [rsp+38h+arg_0]
0x18000e8a0  xor     eax, eax
0x18000e8a2  mov     [rsi+20h], eax
0x18000e8a5  mov     [rsi+18h], rax
0x18000e8a9  mov     rsi, [rsp+38h+arg_8]
0x18000e8ae  add     rsp, 30h
0x18000e8b2  pop     rdi
0x18000e8b3  retn
```
