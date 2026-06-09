# wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)

- ea: `0x18000eb6c`
- end: `0x18000eba4`
- name: `??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e47`

## callees

- `0x18000eb6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb98`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(
        __int64 a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
  }
}

```

## disassembly

```asm
0x18000eb6c  push    rbx
0x18000eb6e  sub     rsp, 20h
0x18000eb72  cmp     byte ptr [rcx+10h], 0
0x18000eb76  jz      short loc_18000EB9E
0x18000eb78  mov     rdx, [rcx]
0x18000eb7b  mov     rax, [rcx+8]
0x18000eb7f  mov     rbx, [rdx]
0x18000eb82  mov     [rdx], rax
0x18000eb85  test    rbx, rbx
0x18000eb88  jz      short loc_18000EB9E
0x18000eb8a  call    cs:__imp_GetProcessHeap
0x18000eb90  mov     r8, rbx; lpMem
0x18000eb93  xor     edx, edx; dwFlags
0x18000eb95  mov     rcx, rax; hHeap
0x18000eb98  call    cs:__imp_HeapFree
0x18000eb9e  add     rsp, 20h
0x18000eba2  pop     rbx
0x18000eba3  retn
```
