# CCertEncodeAltName::UpdateRegistry(int)

- ea: `0x180007710`
- end: `0x180007748`
- name: `?UpdateRegistry@CCertEncodeAltName@@SAJH@Z`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004788`
- `0x180004ae4`
- `0x180007710`

## pseudocode

```c
int __fastcall CCertEncodeAltName::UpdateRegistry(ATL::CComModule *a1)
{
  if ( (_DWORD)a1 )
    return ATL::CComModule::RegisterClassHelper(
             a1,
             &CLSID_CCertEncodeAltName,
             L"CertificateAuthority.EncodeAltName.1",
             L"CertificateAuthority.EncodeAltName",
             3u);
  else
    return ATL::CComModule::UnregisterClassHelper(
             (OLECHAR *)a1,
             &CLSID_CCertEncodeAltName,
             L"CertificateAuthority.EncodeAltName.1",
             L"CertificateAuthority.EncodeAltName");
}

```

## disassembly

```asm
0x180007710  sub     rsp, 38h
0x180007714  lea     r9, aCertificateaut_15; "CertificateAuthority.EncodeAltName"
0x18000771b  lea     r8, aCertificateaut; "CertificateAuthority.EncodeAltName.1"
0x180007722  lea     rdx, CLSID_CCertEncodeAltName; struct _GUID *
0x180007729  test    ecx, ecx
0x18000772b  jz      short loc_18000773F
0x18000772d  mov     [rsp+38h+var_18], 3; unsigned int
0x180007735  call    ?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z; ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)
0x18000773a  add     rsp, 38h
0x18000773e  retn
0x18000773f  add     rsp, 38h
0x180007743  jmp     ?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z; ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)
```
