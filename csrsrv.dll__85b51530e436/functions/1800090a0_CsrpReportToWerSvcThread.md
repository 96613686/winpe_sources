# CsrpReportToWerSvcThread

- ea: `0x1800090a0`
- end: `0x1800090c0`
- name: `CsrpReportToWerSvcThread`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800090a0`

## import_xrefs

- `ntdll!RtlReportException` at `0x1800090b9`

## pseudocode

```c
__int64 __fastcall CsrpReportToWerSvcThread(_QWORD *a1)
{
  if ( a1 )
    return RtlReportException(*a1, a1[1], 3);
  else
    return 3221225485LL;
}

```

## disassembly

```asm
0x1800090a0  test    rcx, rcx
0x1800090a3  jnz     short loc_1800090AC
0x1800090a5  mov     eax, 0C000000Dh
0x1800090aa  retn
0x1800090ac  mov     rdx, [rcx+8]
0x1800090b0  mov     r8d, 3
0x1800090b6  mov     rcx, [rcx]
0x1800090b9  jmp     cs:__imp_RtlReportException
```
