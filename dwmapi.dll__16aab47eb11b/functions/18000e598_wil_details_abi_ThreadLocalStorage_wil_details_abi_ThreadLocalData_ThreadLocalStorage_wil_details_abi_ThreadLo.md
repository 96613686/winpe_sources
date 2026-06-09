# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000e598`
- end: `0x18000e5f0`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e538`

## callees

- `0x18000e598`
- `0x18000e824`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e5c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e5c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e5d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e5d0`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18000e598  push    rbx
0x18000e59a  push    rbp
0x18000e59b  push    rsi
0x18000e59c  push    rdi
0x18000e59d  sub     rsp, 28h
0x18000e5a1  lea     rbp, [rcx+50h]
0x18000e5a5  mov     rdi, rcx
0x18000e5a8  cmp     rcx, rbp
0x18000e5ab  jz      short loc_18000E5E7
0x18000e5ad  mov     rsi, [rdi]
0x18000e5b0  jmp     short loc_18000E5D6
0x18000e5b2  mov     rbx, rsi
0x18000e5b5  mov     rsi, [rsi+8]
0x18000e5b9  lea     rcx, [rbx+10h]; this
0x18000e5bd  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x18000e5c2  call    cs:__imp_GetProcessHeap
0x18000e5c8  mov     r8, rbx; lpMem
0x18000e5cb  xor     edx, edx; dwFlags
0x18000e5cd  mov     rcx, rax; hHeap
0x18000e5d0  call    cs:__imp_HeapFree
0x18000e5d6  test    rsi, rsi
0x18000e5d9  jnz     short loc_18000E5B2
0x18000e5db  mov     [rdi], rsi
0x18000e5de  add     rdi, 8
0x18000e5e2  cmp     rdi, rbp
0x18000e5e5  jnz     short loc_18000E5AD
0x18000e5e7  add     rsp, 28h
0x18000e5eb  pop     rdi
0x18000e5ec  pop     rsi
0x18000e5ed  pop     rbp
0x18000e5ee  pop     rbx
0x18000e5ef  retn
```
