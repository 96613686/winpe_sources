# CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)

- ea: `0x180002af0`
- end: `0x180002b37`
- name: `?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z`
- size: `71`
- prototype: `__int64 __fastcall(void *, unsigned __int64, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029c0`

## callees

- `0x180002af0`
- `0x180002b40`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180002b2f`
- `ntdll!RtlReAllocateHeap` at `0x180002b2f`
- `ntdll!RtlAllocateHeap` at `0x180002b08`
- `ntdll!RtlAllocateHeap` at `0x180002b08`

## pseudocode

```c
__int64 __fastcall CommonHeapReAllocDefault(ReservedForLocalUse *a1, __int64 a2, __int64 a3, void **a4)
{
  void *Heap; // rax
  void *v6; // rcx
  SIZE_T v7; // r8
  PVOID v8; // rax
  unsigned int v9; // ecx

  Heap = ReservedForLocalUse::GetHeap(a1);
  if ( v6 )
    v8 = RtlReAllocateHeap(Heap, 0, v6, v7);
  else
    v8 = RtlAllocateHeap(Heap, 0, v7);
  v9 = 0;
  *a4 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  return v9;
}

```

## disassembly

```asm
0x180002af0  push    rbx
0x180002af2  sub     rsp, 20h
0x180002af6  mov     rbx, r9
0x180002af9  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x180002afe  xor     edx, edx; Flags
0x180002b00  test    rcx, rcx
0x180002b03  jnz     short loc_180002B26
0x180002b05  mov     rcx, rax; HeapHandle
0x180002b08  call    cs:__imp_RtlAllocateHeap
0x180002b0e  xor     ecx, ecx
0x180002b10  mov     [rbx], rax
0x180002b13  test    rax, rax
0x180002b16  mov     edx, 8007000Eh
0x180002b1b  cmovz   ecx, edx
0x180002b1e  mov     eax, ecx
0x180002b20  add     rsp, 20h
0x180002b24  pop     rbx
0x180002b25  retn
0x180002b26  mov     r9, r8; Size
0x180002b29  mov     r8, rcx; Ptr
0x180002b2c  mov     rcx, rax; Heap
0x180002b2f  call    cs:__imp_RtlReAllocateHeap
0x180002b35  jmp     short loc_180002B0E
```
