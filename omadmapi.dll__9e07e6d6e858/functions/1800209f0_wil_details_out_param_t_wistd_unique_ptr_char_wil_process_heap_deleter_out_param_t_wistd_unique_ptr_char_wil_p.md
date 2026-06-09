# wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)

- ea: `0x1800209f0`
- end: `0x180020a35`
- name: `??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002341a`

## callees

- `0x1800209f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a0e`

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
0x1800209f0  push    rbx
0x1800209f2  sub     rsp, 20h
0x1800209f6  cmp     byte ptr [rcx+10h], 0
0x1800209fa  jz      short loc_180020A2E
0x1800209fc  mov     rdx, [rcx]
0x1800209ff  mov     rax, [rcx+8]
0x180020a03  mov     rbx, [rdx]
0x180020a06  mov     [rdx], rax
0x180020a09  test    rbx, rbx
0x180020a0c  jz      short loc_180020A2E
0x180020a0e  call    cs:__imp_GetProcessHeap
0x180020a15  nop     dword ptr [rax+rax+00h]
0x180020a1a  mov     r8, rbx; lpMem
0x180020a1d  xor     edx, edx; dwFlags
0x180020a1f  mov     rcx, rax; hHeap
0x180020a22  call    cs:__imp_HeapFree
0x180020a29  nop     dword ptr [rax+rax+00h]
0x180020a2e  add     rsp, 20h
0x180020a32  pop     rbx
0x180020a33  retn
```
