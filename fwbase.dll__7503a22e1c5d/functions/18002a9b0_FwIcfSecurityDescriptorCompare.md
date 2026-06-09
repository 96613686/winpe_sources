# FwIcfSecurityDescriptorCompare

- ea: `0x18002a9b0`
- end: `0x18002a9bd`
- name: `FwIcfSecurityDescriptorCompare`
- size: `13`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a9b6`

## pseudocode

```c
__int64 __fastcall FwIcfSecurityDescriptorCompare(_QWORD *a1, _QWORD *a2)
{
  return _o__wcsicmp(*a1, *a2);
}

```

## disassembly

```asm
0x18002a9b0  mov     rdx, [rdx]
0x18002a9b3  mov     rcx, [rcx]
0x18002a9b6  jmp     cs:__imp__o__wcsicmp
```
