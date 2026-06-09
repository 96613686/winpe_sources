# Microsoft::WRL::Details::MakeAllocator<AutoDeleteFileStream>::~MakeAllocator<AutoDeleteFileStream>(void)

- ea: `0x18000ffdc`
- end: `0x18000fff3`
- name: `??1?$MakeAllocator@VAutoDeleteFileStream@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800440f5`
- `0x1800442f3`
- `0x180044639`
- `0x180044dbc`
- `0x180044eaf`

## callees

- `0x18000ffdc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ffe8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ffe8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ffdc  sub     rsp, 28h
0x18000ffe0  mov     rcx, [rcx]
0x18000ffe3  test    rcx, rcx
0x18000ffe6  jz      short loc_18000FFEE
0x18000ffe8  call    cs:__imp_??3@YAXPEAX@Z
0x18000ffee  add     rsp, 28h
0x18000fff2  retn
```
