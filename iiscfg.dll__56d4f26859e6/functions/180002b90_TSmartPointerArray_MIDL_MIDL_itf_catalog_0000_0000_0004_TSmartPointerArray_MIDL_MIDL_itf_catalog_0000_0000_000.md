# TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)

- ea: `0x180002b90`
- end: `0x180002bbe`
- name: `??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180003370`
- `0x18000593c`
- `0x18000d110`
- `0x180022a20`
- `0x18002e676`
- `0x18002e8df`
- `0x18002eec9`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002b9c`
- `ole32!CoTaskMemFree` at `0x180002bab`
- `ole32!CoTaskMemFree` at `0x180002b9c`
- `ole32!CoTaskMemFree` at `0x180002bab`

## pseudocode

```c
void __fastcall TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(
        LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
  CoTaskMemFree(0);
  *a1 = 0;
}

```

## disassembly

```asm
0x180002b90  push    rbx
0x180002b92  sub     rsp, 20h
0x180002b96  mov     rbx, rcx
0x180002b99  mov     rcx, [rcx]; pv
0x180002b9c  call    cs:__imp_CoTaskMemFree
0x180002ba2  xor     ecx, ecx; pv
0x180002ba4  mov     qword ptr [rbx], 0
0x180002bab  call    cs:__imp_CoTaskMemFree
0x180002bb1  mov     qword ptr [rbx], 0
0x180002bb8  add     rsp, 20h
0x180002bbc  pop     rbx
0x180002bbd  retn
```
