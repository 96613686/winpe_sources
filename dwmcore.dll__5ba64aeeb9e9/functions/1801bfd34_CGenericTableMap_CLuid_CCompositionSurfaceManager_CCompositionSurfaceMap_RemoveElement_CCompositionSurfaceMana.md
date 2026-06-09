# CGenericTableMap<CLuid,CCompositionSurfaceManager::CCompositionSurfaceMap>::RemoveElement(CCompositionSurfaceManager::CCompositionSurfaceMap *)

- ea: `0x1801bfd34`
- end: `0x1801bfd6d`
- name: `?RemoveElement@?$CGenericTableMap@VCLuid@@VCCompositionSurfaceMap@CCompositionSurfaceManager@@@@QEAAXPEAVCCompositionSurfaceMap@CCompositionSurfaceManager@@@Z`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801bfce0`
- `0x1802338d0`
- `0x180235a70`

## callees

- `0x1801bfd34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1801bfd65`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1801bfd65`
- `ntdll!RtlDeleteElementGenericTable` at `0x1801bfd4e`
- `ntdll!RtlDeleteElementGenericTable` at `0x1801bfd4e`

## pseudocode

```c
void __fastcall CGenericTableMap<CLuid,CCompositionSurfaceManager::CCompositionSurfaceMap>::RemoveElement(
        struct _RTL_GENERIC_TABLE *a1,
        _QWORD *a2)
{
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  Buffer[0] = *a2;
  Buffer[1] = 0;
  if ( !RtlDeleteElementGenericTable(a1, Buffer) )
    RaiseFailFastException(0, 0, 1u);
}

```

## disassembly

```asm
0x1801bfd34  sub     rsp, 38h
0x1801bfd38  mov     rax, [rdx]
0x1801bfd3b  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1801bfd40  mov     [rsp+38h+Buffer], rax
0x1801bfd45  mov     [rsp+38h+var_10], 0
0x1801bfd4e  call    cs:__imp_RtlDeleteElementGenericTable
0x1801bfd54  test    al, al
0x1801bfd56  jz      short loc_1801BFD5D
0x1801bfd58  add     rsp, 38h
0x1801bfd5c  retn
0x1801bfd5d  xor     edx, edx; pContextRecord
0x1801bfd5f  xor     ecx, ecx; pExceptionRecord
0x1801bfd61  lea     r8d, [rdx+1]; dwFlags
0x1801bfd65  call    cs:__imp_RaiseFailFastException
0x1801bfd6b  jmp     short loc_1801BFD58
```
