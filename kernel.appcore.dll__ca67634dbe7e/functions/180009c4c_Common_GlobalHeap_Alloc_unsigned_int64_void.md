# Common::GlobalHeap::Alloc(unsigned __int64,void * *)

- ea: `0x180009c4c`
- end: `0x180009c7f`
- name: `?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z`
- size: `51`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180009a9c`
- `0x180009b80`

## callees

- `0x180002b40`
- `0x180009c4c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009c62`
- `ntdll!RtlAllocateHeap` at `0x180009c62`

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
0x180009c4c  push    rbx
0x180009c4e  sub     rsp, 20h
0x180009c52  mov     rbx, rdx
0x180009c55  mov     r8, rcx
0x180009c58  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x180009c5d  mov     rcx, rax; HeapHandle
0x180009c60  xor     edx, edx; Flags
0x180009c62  call    cs:__imp_RtlAllocateHeap
0x180009c68  test    rax, rax
0x180009c6b  jnz     short loc_180009C74
0x180009c6d  mov     eax, 8007000Eh
0x180009c72  jmp     short loc_180009C79
0x180009c74  mov     [rbx], rax
0x180009c77  xor     eax, eax
0x180009c79  add     rsp, 20h
0x180009c7d  pop     rbx
0x180009c7e  retn
```
