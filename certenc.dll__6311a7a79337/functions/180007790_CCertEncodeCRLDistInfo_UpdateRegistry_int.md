# CCertEncodeCRLDistInfo::UpdateRegistry(int)

- ea: `0x180007790`
- end: `0x1800077c8`
- name: `?UpdateRegistry@CCertEncodeCRLDistInfo@@SAJH@Z`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004788`
- `0x180004ae4`
- `0x180007790`

## pseudocode

```c
int __fastcall CCertEncodeCRLDistInfo::UpdateRegistry(ATL::CComModule *a1)
{
  if ( (_DWORD)a1 )
    return ATL::CComModule::RegisterClassHelper(
             a1,
             &CLSID_CCertEncodeCRLDistInfo,
             L"CertificateAuthority.EncodeCRLDistInfo.1",
             L"CertificateAuthority.EncodeCRLDistInfo",
             6u);
  else
    return ATL::CComModule::UnregisterClassHelper(
             (OLECHAR *)a1,
             &CLSID_CCertEncodeCRLDistInfo,
             L"CertificateAuthority.EncodeCRLDistInfo.1",
             L"CertificateAuthority.EncodeCRLDistInfo");
}

```

## disassembly

```asm
0x180007790  sub     rsp, 38h
0x180007794  lea     r9, aCertificateaut_2; "CertificateAuthority.EncodeCRLDistInfo"
0x18000779b  lea     r8, aCertificateaut_16; "CertificateAuthority.EncodeCRLDistInfo."...
0x1800077a2  lea     rdx, CLSID_CCertEncodeCRLDistInfo; struct _GUID *
0x1800077a9  test    ecx, ecx
0x1800077ab  jz      short loc_1800077BF
0x1800077ad  mov     [rsp+38h+var_18], 6; unsigned int
0x1800077b5  call    ?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z; ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)
0x1800077ba  add     rsp, 38h
0x1800077be  retn
0x1800077bf  add     rsp, 38h
0x1800077c3  jmp     ?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z; ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)
```
