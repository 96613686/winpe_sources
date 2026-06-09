# Common::GlobalHeap::Alloc(unsigned __int64,void * *)

- ea: `0x18000be00`
- end: `0x18000be33`
- name: `?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z`
- size: `51`
- prototype: `__int64 __fastcall(ReservedForLocalUse *, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bca0`
- `0x18000ca4c`
- `0x180018aac`
- `0x180018b90`
- `0x180018ffc`

## callees

- `0x18000be00`
- `0x18000be64`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000be16`
- `ntdll!RtlAllocateHeap` at `0x18000be16`

## pseudocode

```c
__int64 __fastcall Common::GlobalHeap::Alloc(ReservedForLocalUse *a1, void **a2)
{
  void *Heap; // rax
  SIZE_T v4; // r8
  PVOID v5; // rax

  Heap = ReservedForLocalUse::GetHeap(a1);
  v5 = RtlAllocateHeap(Heap, 0, v4);
  if ( !v5 )
    return 2147942414LL;
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000be00  push    rbx
0x18000be02  sub     rsp, 20h
0x18000be06  mov     rbx, rdx
0x18000be09  mov     r8, rcx
0x18000be0c  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x18000be11  mov     rcx, rax; HeapHandle
0x18000be14  xor     edx, edx; Flags
0x18000be16  call    cs:__imp_RtlAllocateHeap
0x18000be1c  test    rax, rax
0x18000be1f  jnz     short loc_18000BE28
0x18000be21  mov     eax, 8007000Eh
0x18000be26  jmp     short loc_18000BE2D
0x18000be28  mov     [rbx], rax
0x18000be2b  xor     eax, eax
0x18000be2d  add     rsp, 20h
0x18000be31  pop     rbx
0x18000be32  retn
```
