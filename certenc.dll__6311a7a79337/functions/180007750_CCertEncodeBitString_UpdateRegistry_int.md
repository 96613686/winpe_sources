# CCertEncodeBitString::UpdateRegistry(int)

- ea: `0x180007750`
- end: `0x180007788`
- name: `?UpdateRegistry@CCertEncodeBitString@@SAJH@Z`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004788`
- `0x180004ae4`
- `0x180007750`

## pseudocode

```c
int __fastcall CCertEncodeBitString::UpdateRegistry(ATL::CComModule *a1)
{
  if ( (_DWORD)a1 )
    return ATL::CComModule::RegisterClassHelper(
             a1,
             &CLSID_CCertEncodeBitString,
             L"CertificateAuthority.EncodeBitString.1",
             L"CertificateAuthority.EncodeBitString",
             5u);
  else
    return ATL::CComModule::UnregisterClassHelper(
             (OLECHAR *)a1,
             &CLSID_CCertEncodeBitString,
             L"CertificateAuthority.EncodeBitString.1",
             L"CertificateAuthority.EncodeBitString");
}

```

## disassembly

```asm
0x180007750  sub     rsp, 38h
0x180007754  lea     r9, aCertificateaut_12; "CertificateAuthority.EncodeBitString"
0x18000775b  lea     r8, aCertificateaut_14; "CertificateAuthority.EncodeBitString.1"
0x180007762  lea     rdx, CLSID_CCertEncodeBitString; struct _GUID *
0x180007769  test    ecx, ecx
0x18000776b  jz      short loc_18000777F
0x18000776d  mov     [rsp+38h+var_18], 5; unsigned int
0x180007775  call    ?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z; ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)
0x18000777a  add     rsp, 38h
0x18000777e  retn
0x18000777f  add     rsp, 38h
0x180007783  jmp     ?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z; ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)
```
