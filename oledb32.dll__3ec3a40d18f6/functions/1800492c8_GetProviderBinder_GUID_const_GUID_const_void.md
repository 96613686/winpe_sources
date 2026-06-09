# GetProviderBinder(_GUID const &,_GUID const &,void * *)

- ea: `0x1800492c8`
- end: `0x180049315`
- name: `?GetProviderBinder@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `77`
- prototype: `int(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800460a0`
- `0x180046830`

## callees

- `0x180029560`
- `0x1800492c8`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800492e5`
- `ole32!CoCreateInstance` at `0x18004930a`
- `ole32!CoCreateInstance` at `0x1800492e5`
- `ole32!CoCreateInstance` at `0x18004930a`

## pseudocode

```c
HRESULT __fastcall GetProviderBinder(const struct _GUID *a1, const struct _GUID *a2, void **ppv)
{
  unsigned int Instance; // eax

  if ( (bidGblFlags & 2) == 0 )
    return CoCreateInstance(a1, 0, 0x17u, a2, ppv);
  Instance = CoCreateInstance(a1, 0, 0x17u, a2, ppv);
  return bidTraceHR(rclsid, 43017, L"<GetProviderBinder|Trace|HR> ", Instance);
}

```

## disassembly

```asm
0x1800492c8  sub     rsp, 38h
0x1800492cc  mov     r9, rdx; riid
0x1800492cf  mov     [rsp+38h+ppv], r8; ppv
0x1800492d4  xor     edx, edx; pUnkOuter
0x1800492d6  mov     r8d, 17h; dwClsContext
0x1800492dc  test    byte ptr cs:_bidGblFlags, 2
0x1800492e3  jz      short loc_18004930A
0x1800492e5  call    cs:__imp_CoCreateInstance
0x1800492eb  mov     rcx, cs:rclsid; rclsid
0x1800492f2  lea     r8, aGetproviderbin; "<GetProviderBinder|Trace|HR> "
0x1800492f9  mov     r9d, eax
0x1800492fc  mov     edx, 0A809h
0x180049301  add     rsp, 38h
0x180049305  jmp     _bidTraceHR
0x18004930a  call    cs:__imp_CoCreateInstance
0x180049310  add     rsp, 38h
0x180049314  retn
```
