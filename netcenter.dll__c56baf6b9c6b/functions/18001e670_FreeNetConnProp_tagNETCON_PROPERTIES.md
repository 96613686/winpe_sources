# FreeNetConnProp(tagNETCON_PROPERTIES *)

- ea: `0x18001e670`
- end: `0x18001e6a0`
- name: `?FreeNetConnProp@@YAXPEAUtagNETCON_PROPERTIES@@@Z`
- size: `48`
- prototype: `void __fastcall(struct tagNETCON_PROPERTIES *pv)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009c1c`
- `0x18000c36c`
- `0x18001e460`
- `0x18001fde8`

## callees

- `0x18001e670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e694`

## pseudocode

```c
void __fastcall FreeNetConnProp(struct tagNETCON_PROPERTIES *pv)
{
  if ( pv )
  {
    CoTaskMemFree(pv->pszwName);
    CoTaskMemFree(pv->pszwDeviceName);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18001e670  test    rcx, rcx
0x18001e673  jz      short locret_18001E69F
0x18001e675  push    rbx
0x18001e676  sub     rsp, 20h
0x18001e67a  mov     rbx, rcx
0x18001e67d  mov     rcx, [rcx+10h]; pv
0x18001e681  call    cs:__imp_CoTaskMemFree
0x18001e687  mov     rcx, [rbx+18h]; pv
0x18001e68b  call    cs:__imp_CoTaskMemFree
0x18001e691  mov     rcx, rbx; pv
0x18001e694  call    cs:__imp_CoTaskMemFree
0x18001e69a  add     rsp, 20h
0x18001e69e  pop     rbx
0x18001e69f  retn
```
