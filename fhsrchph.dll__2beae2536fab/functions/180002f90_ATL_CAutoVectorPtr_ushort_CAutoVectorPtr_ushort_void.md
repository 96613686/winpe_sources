# ATL::CAutoVectorPtr<ushort>::~CAutoVectorPtr<ushort>(void)

- ea: `0x180002f90`
- end: `0x180002faf`
- name: `??1?$CAutoVectorPtr@G@ATL@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000af7c`
- `0x18000af8e`
- `0x18000b3b8`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180002f9c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002f9c`

## pseudocode

```c
void __fastcall ATL::CAutoVectorPtr<unsigned short>::~CAutoVectorPtr<unsigned short>(void **a1)
{
  operator delete[](*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180002f90  push    rbx
0x180002f92  sub     rsp, 20h
0x180002f96  mov     rbx, rcx
0x180002f99  mov     rcx, [rcx]
0x180002f9c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002fa2  mov     qword ptr [rbx], 0
0x180002fa9  add     rsp, 20h
0x180002fad  pop     rbx
0x180002fae  retn
```
