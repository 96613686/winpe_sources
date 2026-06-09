# HrCreateInstanceBase(_GUID const &,ulong,_GUID const &,void * *)

- ea: `0x1800305dc`
- end: `0x180030604`
- name: `?HrCreateInstanceBase@@YAJAEBU_GUID@@K0PEAPEAX@Z`
- size: `40`
- prototype: `int(const struct _GUID *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020db0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800305f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800305f9`

## pseudocode

```c
HRESULT __fastcall HrCreateInstanceBase(const struct _GUID *a1, __int64 a2, const struct _GUID *a3, void **ppv)
{
  return CoCreateInstance(&CLSID_HNetCfgMgr, 0, 1u, &GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71, ppv);
}

```

## disassembly

```asm
0x1800305dc  sub     rsp, 38h
0x1800305e0  xor     edx, edx; pUnkOuter
0x1800305e2  mov     [rsp+38h+ppv], r9; ppv
0x1800305e7  lea     r9, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71; riid
0x1800305ee  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x1800305f5  lea     r8d, [rdx+1]; dwClsContext
0x1800305f9  call    cs:__imp_CoCreateInstance
0x1800305ff  add     rsp, 38h
0x180030603  retn
```
