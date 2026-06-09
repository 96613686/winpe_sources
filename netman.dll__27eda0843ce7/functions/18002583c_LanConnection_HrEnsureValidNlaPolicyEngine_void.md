# LanConnection::HrEnsureValidNlaPolicyEngine(void)

- ea: `0x18002583c`
- end: `0x180025876`
- name: `?HrEnsureValidNlaPolicyEngine@LanConnection@@AEAAJXZ`
- size: `58`
- prototype: `__int64 __fastcall(LanConnection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024978`

## callees

- `0x18002583c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002586b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002586b`

## pseudocode

```c
HRESULT __fastcall LanConnection::HrEnsureValidNlaPolicyEngine(LanConnection *this)
{
  LPVOID *ppv; // rcx
  HRESULT result; // eax

  ppv = (LPVOID *)((char *)this + 144);
  result = 1;
  if ( !*ppv )
    return CoCreateInstance(&CLSID_NetGroupPolicies, 0, 3u, &GUID_faedcf68_31fe_11d1_aad2_00805fc1270e, ppv);
  return result;
}

```

## disassembly

```asm
0x18002583c  sub     rsp, 38h
0x180025840  add     rcx, 90h
0x180025847  mov     eax, 1
0x18002584c  cmp     qword ptr [rcx], 0
0x180025850  jnz     short loc_180025871
0x180025852  mov     [rsp+38h+ppv], rcx; ppv
0x180025857  lea     r9, _GUID_faedcf68_31fe_11d1_aad2_00805fc1270e; riid
0x18002585e  lea     rcx, CLSID_NetGroupPolicies; rclsid
0x180025865  xor     edx, edx; pUnkOuter
0x180025867  lea     r8d, [rax+2]; dwClsContext
0x18002586b  call    cs:__imp_CoCreateInstance
0x180025871  add     rsp, 38h
0x180025875  retn
```
