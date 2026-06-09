# FreeNetconProperties(tagNETCON_PROPERTIES *)

- ea: `0x180031d0c`
- end: `0x180031d3c`
- name: `?FreeNetconProperties@@YAXPEAUtagNETCON_PROPERTIES@@@Z`
- size: `48`
- prototype: `void __fastcall(struct tagNETCON_PROPERTIES *pv)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b8c0`
- `0x180023080`
- `0x180024760`
- `0x180024db0`
- `0x180025020`
- `0x18002a1b0`
- `0x18002bd30`
- `0x18002c0c0`
- `0x180030884`

## callees

- `0x180031d0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d30`

## pseudocode

```c
void __fastcall FreeNetconProperties(struct tagNETCON_PROPERTIES *pv)
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
0x180031d0c  test    rcx, rcx
0x180031d0f  jz      short locret_180031D3B
0x180031d11  push    rbx
0x180031d12  sub     rsp, 20h
0x180031d16  mov     rbx, rcx
0x180031d19  mov     rcx, [rcx+10h]; pv
0x180031d1d  call    cs:__imp_CoTaskMemFree
0x180031d23  mov     rcx, [rbx+18h]; pv
0x180031d27  call    cs:__imp_CoTaskMemFree
0x180031d2d  mov     rcx, rbx; pv
0x180031d30  call    cs:__imp_CoTaskMemFree
0x180031d36  add     rsp, 20h
0x180031d3a  pop     rbx
0x180031d3b  retn
```
