# Microsoft::WRL::Details::MakeAllocator<AutoDeleteFileStream>::~MakeAllocator<AutoDeleteFileStream>(void)

- ea: `0x14000d2dc`
- end: `0x14000d2f3`
- name: `??1?$MakeAllocator@VAutoDeleteFileStream@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ee26`

## callees

- `0x14000d2dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000d2e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000d2e8`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<AutoDeleteFileStream>::~MakeAllocator<AutoDeleteFileStream>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x14000d2dc  sub     rsp, 28h
0x14000d2e0  mov     rcx, [rcx]
0x14000d2e3  test    rcx, rcx
0x14000d2e6  jz      short loc_14000D2EE
0x14000d2e8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000d2ee  add     rsp, 28h
0x14000d2f2  retn
```
