# CsrAllocateThread

- ea: `0x180002f60`
- end: `0x180002fca`
- name: `CsrAllocateThread`
- size: `106`
- prototype: `_DWORD *__fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001bb0`
- `0x1800020c0`
- `0x180002a00`
- `0x180002c90`
- `0x180009370`
- `0x18000a070`

## callees

- `0x180002f60`
- `0x18000ab61`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180002f86`
- `ntdll!RtlAllocateHeap` at `0x180002f86`

## pseudocode

```c
_DWORD *__fastcall CsrAllocateThread(__int64 a1)
{
  _DWORD *result; // rax
  _DWORD *v3; // rbx

  result = RtlAllocateHeap(CsrHeap, CsrBaseTag + 0x100000, 0x58u);
  v3 = result;
  if ( result )
  {
    memset_0(result, 0, 0x58u);
    v3[19] = 1;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 100));
    *((_QWORD *)v3 + 7) = a1;
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp+arg_0], rbx
0x180002f65  push    rdi
0x180002f66  sub     rsp, 20h
0x180002f6a  mov     edx, cs:CsrBaseTag
0x180002f70  mov     rdi, rcx
0x180002f73  mov     rcx, cs:CsrHeap; HeapHandle
0x180002f7a  add     edx, 100000h; Flags
0x180002f80  mov     r8d, 58h ; 'X'; Size
0x180002f86  call    cs:__imp_RtlAllocateHeap
0x180002f8d  nop     dword ptr [rax+rax+00h]
0x180002f92  mov     rbx, rax
0x180002f95  test    rax, rax
0x180002f98  jz      short loc_180002FC8
0x180002f9a  xor     edx, edx; Val
0x180002f9c  mov     r8d, 58h ; 'X'; Size
0x180002fa2  mov     rcx, rax; void *
0x180002fa5  call    memset_0
0x180002faa  mov     dword ptr [rbx+4Ch], 1
0x180002fb1  lock inc dword ptr [rdi+64h]
0x180002fb5  mov     [rbx+38h], rdi
0x180002fb9  mov     rax, rbx
0x180002fbc  mov     rbx, [rsp+28h+arg_0]
0x180002fc1  add     rsp, 20h
0x180002fc5  pop     rdi
0x180002fc6  retn
0x180002fc8  jmp     short loc_180002FBC
```
