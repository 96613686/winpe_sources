# NcFreeNetconProperties

- ea: `0x180009930`
- end: `0x180009960`
- name: `NcFreeNetconProperties`
- size: `48`
- prototype: `void __stdcall(NETCON_PROPERTIES *pProps)`
- caller_count: `24`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008ed0`
- `0x180016bfc`
- `0x18002c0d4`
- `0x18002d4d8`
- `0x18002dc50`
- `0x18002de34`
- `0x18002df10`
- `0x18002ebf8`
- `0x18002f990`
- `0x180030600`
- `0x180030710`
- `0x180030940`
- `0x180033e1c`
- `0x180033fd4`
- `0x180044f34`
- `0x18004c00c`
- `0x18004c20c`
- `0x18004c2ac`
- `0x18004cee0`
- `0x180059710`
- `0x18005985c`
- `0x18005ccfc`
- `0x180061524`
- `0x180061824`

## callees

- `0x180009930`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009941`
- `ole32!CoTaskMemFree` at `0x18000994b`
- `ole32!CoTaskMemFree` at `0x180009954`
- `ole32!CoTaskMemFree` at `0x180009941`
- `ole32!CoTaskMemFree` at `0x18000994b`
- `ole32!CoTaskMemFree` at `0x180009954`

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
0x180009930  test    rcx, rcx
0x180009933  jz      short locret_18000995F
0x180009935  push    rbx
0x180009936  sub     rsp, 20h
0x18000993a  mov     rbx, rcx
0x18000993d  mov     rcx, [rcx+10h]; pv
0x180009941  call    cs:__imp_CoTaskMemFree
0x180009947  mov     rcx, [rbx+18h]; pv
0x18000994b  call    cs:__imp_CoTaskMemFree
0x180009951  mov     rcx, rbx; pv
0x180009954  call    cs:__imp_CoTaskMemFree
0x18000995a  add     rsp, 20h
0x18000995e  pop     rbx
0x18000995f  retn
```
