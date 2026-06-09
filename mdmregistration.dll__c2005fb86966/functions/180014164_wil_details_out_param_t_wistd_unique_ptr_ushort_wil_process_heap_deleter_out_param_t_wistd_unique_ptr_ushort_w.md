# wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)

- ea: `0x180014164`
- end: `0x1800141a9`
- name: `??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180022e74`
- `0x18004c12b`
- `0x18004c14f`
- `0x18004c2e0`
- `0x18004c68a`
- `0x18004c6e4`
- `0x18004c9d8`
- `0x18004cb64`
- `0x18004cb76`
- `0x18004cb88`
- `0x18004cb9a`
- `0x18004cbac`
- `0x18004cbbe`

## callees

- `0x180014164`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014196`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014182`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(
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
0x180014164  push    rbx
0x180014166  sub     rsp, 20h
0x18001416a  cmp     byte ptr [rcx+10h], 0
0x18001416e  jz      short loc_1800141A2
0x180014170  mov     rdx, [rcx]
0x180014173  mov     rax, [rcx+8]
0x180014177  mov     rbx, [rdx]
0x18001417a  mov     [rdx], rax
0x18001417d  test    rbx, rbx
0x180014180  jz      short loc_1800141A2
0x180014182  call    cs:__imp_GetProcessHeap
0x180014189  nop     dword ptr [rax+rax+00h]
0x18001418e  mov     r8, rbx; lpMem
0x180014191  xor     edx, edx; dwFlags
0x180014193  mov     rcx, rax; hHeap
0x180014196  call    cs:__imp_HeapFree
0x18001419d  nop     dword ptr [rax+rax+00h]
0x1800141a2  add     rsp, 20h
0x1800141a6  pop     rbx
0x1800141a7  retn
```
