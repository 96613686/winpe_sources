# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003c48`
- end: `0x180003ca3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000366c`
- `0x180005038`

## callees

- `0x180003c48`
- `0x180003eb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, SIZE_T a2)
{
  LPVOID result; // rax

  result = g_hLocalHeap;
  if ( g_hLocalHeap || (result = GetProcessHeap(), (g_hLocalHeap = result) != 0) )
    result = HeapAlloc(result, 0, a2);
  if ( !result )
    ATL::AtlThrowImpl(-2147024882);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180003c48  mov     [rsp+arg_0], rbx
0x180003c4d  push    rdi
0x180003c4e  sub     rsp, 20h
0x180003c52  mov     rdi, rdx
0x180003c55  mov     rbx, rcx
0x180003c58  mov     rax, cs:?g_hLocalHeap@@3PEAXEA; void * g_hLocalHeap
0x180003c5f  test    rax, rax
0x180003c62  jnz     short loc_180003C76
0x180003c64  call    cs:__imp_GetProcessHeap
0x180003c6a  mov     cs:?g_hLocalHeap@@3PEAXEA, rax; void * g_hLocalHeap
0x180003c71  test    rax, rax
0x180003c74  jz      short loc_180003C85
0x180003c76  mov     r8, rdi; dwBytes
0x180003c79  xor     edx, edx; dwFlags
0x180003c7b  mov     rcx, rax; hHeap
0x180003c7e  call    cs:__imp_HeapAlloc
0x180003c84  nop
0x180003c85  test    rax, rax
0x180003c88  jz      short loc_180003C98
0x180003c8a  mov     [rbx], rax
0x180003c8d  mov     rbx, [rsp+28h+arg_0]
0x180003c92  add     rsp, 20h
0x180003c96  pop     rdi
0x180003c97  retn
0x180003c98  mov     ecx, 8007000Eh; int
0x180003c9d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
