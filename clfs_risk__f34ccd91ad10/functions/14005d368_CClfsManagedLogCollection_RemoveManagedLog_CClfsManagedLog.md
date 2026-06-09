# CClfsManagedLogCollection::RemoveManagedLog(CClfsManagedLog *)

- ea: `0x14005d368`
- end: `0x14005d3e5`
- name: `?RemoveManagedLog@CClfsManagedLogCollection@@QEAAJPEAVCClfsManagedLog@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(PUNICODE_PREFIX_TABLE PrefixTable, struct CClfsManagedLog *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14005d1e8`

## callees

- `0x14005d368`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d383`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d383`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d3c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d3c6`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14005d3b6`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14005d3b6`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14005d39f`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14005d39f`

## pseudocode

```c
__int64 __fastcall CClfsManagedLogCollection::RemoveManagedLog(
        PUNICODE_PREFIX_TABLE PrefixTable,
        struct CClfsManagedLog *a2)
{
  struct _UNICODE_PREFIX_TABLE_ENTRY *UnicodePrefix; // rax

  ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[1], 1u);
  UnicodePrefix = RtlFindUnicodePrefix(PrefixTable, (PCUNICODE_STRING)((char *)a2 + 136), 1u);
  if ( UnicodePrefix )
    RtlRemoveUnicodePrefix(PrefixTable, UnicodePrefix);
  ExReleaseResourceLite((PERESOURCE)&PrefixTable[1]);
  return 0;
}

```

## disassembly

```asm
0x14005d368  mov     [rsp+arg_0], rbx
0x14005d36d  mov     [rsp+arg_8], rsi
0x14005d372  push    rdi
0x14005d373  sub     rsp, 20h
0x14005d377  mov     rbx, rdx
0x14005d37a  mov     rdi, rcx
0x14005d37d  mov     dl, 1; Wait
0x14005d37f  add     rcx, 18h; Resource
0x14005d383  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005d38a  nop     dword ptr [rax+rax+00h]
0x14005d38f  lea     rdx, [rbx+88h]; FullName
0x14005d396  mov     r8d, 1; CaseInsensitiveIndex
0x14005d39c  mov     rcx, rdi; PrefixTable
0x14005d39f  call    cs:__imp_RtlFindUnicodePrefix
0x14005d3a6  nop     dword ptr [rax+rax+00h]
0x14005d3ab  test    rax, rax
0x14005d3ae  jz      short loc_14005D3C2
0x14005d3b0  mov     rdx, rax; PrefixTableEntry
0x14005d3b3  mov     rcx, rdi; PrefixTable
0x14005d3b6  call    cs:__imp_RtlRemoveUnicodePrefix
0x14005d3bd  nop     dword ptr [rax+rax+00h]
0x14005d3c2  lea     rcx, [rdi+18h]; Resource
0x14005d3c6  call    cs:__imp_ExReleaseResourceLite
0x14005d3cd  nop     dword ptr [rax+rax+00h]
0x14005d3d2  mov     rbx, [rsp+28h+arg_0]
0x14005d3d7  xor     eax, eax
0x14005d3d9  mov     rsi, [rsp+28h+arg_8]
0x14005d3de  add     rsp, 20h
0x14005d3e2  pop     rdi
0x14005d3e3  retn
```
