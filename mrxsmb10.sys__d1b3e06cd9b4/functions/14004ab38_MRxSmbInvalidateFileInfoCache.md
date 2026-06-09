# MRxSmbInvalidateFileInfoCache

- ea: `0x14004ab38`
- end: `0x14004ab5d`
- name: `MRxSmbInvalidateFileInfoCache`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140029440`
- `0x14002b980`
- `0x14002cec0`
- `0x14002d030`
- `0x14002f120`
- `0x140036d40`
- `0x14003a204`
- `0x14003a494`
- `0x14003b4c8`
- `0x14003c3f8`
- `0x140048b30`
- `0x140052c00`

## callees

- `0x14004ab70`
- `0x14004ac50`
- `0x14004b470`

## pseudocode

```c
void __fastcall MRxSmbInvalidateFileInfoCache(__int64 a1)
{
  MRxSmbInvalidateBasicFileInfoCache(a1);
  MRxSmbInvalidateStandardFileInfoCache(a1);
  MRxSmbInvalidateFullDirectoryCache(a1);
}

```

## disassembly

```asm
0x14004ab38  push    rbx
0x14004ab3a  sub     rsp, 20h
0x14004ab3e  mov     rbx, rcx
0x14004ab41  call    MRxSmbInvalidateBasicFileInfoCache
0x14004ab46  mov     rcx, rbx
0x14004ab49  call    MRxSmbInvalidateStandardFileInfoCache
0x14004ab4e  mov     rcx, rbx
0x14004ab51  call    MRxSmbInvalidateFullDirectoryCache
0x14004ab56  add     rsp, 20h
0x14004ab5a  pop     rbx
0x14004ab5b  retn
```
