# myConvertStringSecurityDescriptorToSecurityDescriptor(ushort const *,ulong,void * *,ulong *)

- ea: `0x1800270d8`
- end: `0x1800270e8`
- name: `?myConvertStringSecurityDescriptorToSecurityDescriptor@@YAHPEBGKPEAPEAXPEAK@Z`
- size: `16`
- prototype: `BOOL __fastcall(const unsigned __int16 *, __int64, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028040`
- `0x1800280a0`
- `0x180030c18`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800270e1`

## pseudocode

```c
BOOL __fastcall myConvertStringSecurityDescriptorToSecurityDescriptor(
        const unsigned __int16 *a1,
        __int64 a2,
        void **a3,
        unsigned int *a4)
{
  return ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, a3, 0);
}

```

## disassembly

```asm
0x1800270d8  xchg    ax, ax
0x1800270da  xor     r9d, r9d
0x1800270dd  lea     edx, [r9+1]
0x1800270e1  jmp     cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
```
