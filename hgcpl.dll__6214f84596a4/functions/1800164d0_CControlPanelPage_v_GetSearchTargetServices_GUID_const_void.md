# CControlPanelPage::v_GetSearchTargetServices(_GUID const &,void * *)

- ea: `0x1800164d0`
- end: `0x1800164f4`
- name: `?v_GetSearchTargetServices@CControlPanelPage@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `36`
- prototype: `int(CControlPanelPage *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800164e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800164e9`

## pseudocode

```c
HRESULT __fastcall CControlPanelPage::v_GetSearchTargetServices(
        CControlPanelPage *this,
        const struct _GUID *a2,
        void **ppv)
{
  return CoCreateInstance(&CLSID_CPLSearchTargetServices, 0, 3u, a2, ppv);
}

```

## disassembly

```asm
0x1800164d0  sub     rsp, 38h
0x1800164d4  mov     r9, rdx; riid
0x1800164d7  mov     [rsp+38h+ppv], r8; ppv
0x1800164dc  xor     edx, edx; pUnkOuter
0x1800164de  lea     rcx, CLSID_CPLSearchTargetServices; rclsid
0x1800164e5  lea     r8d, [rdx+3]; dwClsContext
0x1800164e9  call    cs:__imp_CoCreateInstance
0x1800164ef  add     rsp, 38h
0x1800164f3  retn
```
