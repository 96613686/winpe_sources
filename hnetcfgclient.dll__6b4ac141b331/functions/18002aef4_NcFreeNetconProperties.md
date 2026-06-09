# NcFreeNetconProperties

- ea: `0x18002aef4`
- end: `0x18002af24`
- name: `NcFreeNetconProperties`
- size: `48`
- prototype: `void __stdcall(NETCON_PROPERTIES *pProps)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014bc0`
- `0x180015200`
- `0x180028d74`

## callees

- `0x18002aef4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af18`

## pseudocode

```c
void __stdcall NcFreeNetconProperties(NETCON_PROPERTIES *pProps)
{
  if ( pProps )
  {
    CoTaskMemFree(pProps->pszwName);
    CoTaskMemFree(pProps->pszwDeviceName);
    CoTaskMemFree(pProps);
  }
}

```

## disassembly

```asm
0x18002aef4  test    rcx, rcx
0x18002aef7  jz      short locret_18002AF23
0x18002aef9  push    rbx
0x18002aefa  sub     rsp, 20h
0x18002aefe  mov     rbx, rcx
0x18002af01  mov     rcx, [rcx+10h]; pv
0x18002af05  call    cs:__imp_CoTaskMemFree
0x18002af0b  mov     rcx, [rbx+18h]; pv
0x18002af0f  call    cs:__imp_CoTaskMemFree
0x18002af15  mov     rcx, rbx; pv
0x18002af18  call    cs:__imp_CoTaskMemFree
0x18002af1e  add     rsp, 20h
0x18002af22  pop     rbx
0x18002af23  retn
```
