# operator delete(void *)

- ea: `0x180001de8`
- end: `0x180001e0e`
- name: `??3@YAXPEAX@Z`
- size: `38`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180001de8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001e03`
- `ntdll!RtlFreeHeap` at `0x180001e03`

## pseudocode

```c
void __fastcall operator delete(PVOID P)
{
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
}

```

## disassembly

```asm
0x180001de8  sub     rsp, 28h
0x180001dec  mov     r8, rcx; P
0x180001def  test    rcx, rcx
0x180001df2  jz      short loc_180001E09
0x180001df4  mov     rcx, gs:60h
0x180001dfd  xor     edx, edx; Flags
0x180001dff  mov     rcx, [rcx+30h]; HeapHandle
0x180001e03  call    cs:__imp_RtlFreeHeap
0x180001e09  add     rsp, 28h
0x180001e0d  retn
```
