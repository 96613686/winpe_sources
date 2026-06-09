# CCertEncodeStringArray::UpdateRegistry(int)

- ea: `0x180007850`
- end: `0x180007888`
- name: `?UpdateRegistry@CCertEncodeStringArray@@SAJH@Z`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004788`
- `0x180004ae4`
- `0x180007850`

## pseudocode

```c
int __fastcall CCertEncodeStringArray::UpdateRegistry(ATL::CComModule *a1)
{
  if ( (_DWORD)a1 )
    return ATL::CComModule::RegisterClassHelper(
             a1,
             &CLSID_CCertEncodeStringArray,
             L"CertificateAuthority.EncodeStringArray.1",
             L"CertificateAuthority.EncodeStringArray",
             4u);
  else
    return ATL::CComModule::UnregisterClassHelper(
             (OLECHAR *)a1,
             &CLSID_CCertEncodeStringArray,
             L"CertificateAuthority.EncodeStringArray.1",
             L"CertificateAuthority.EncodeStringArray");
}

```

## disassembly

```asm
0x180007850  sub     rsp, 38h
0x180007854  lea     r9, aCertificateaut_11; "CertificateAuthority.EncodeStringArray"
0x18000785b  lea     r8, aCertificateaut_0; "CertificateAuthority.EncodeStringArray."...
0x180007862  lea     rdx, CLSID_CCertEncodeStringArray; struct _GUID *
0x180007869  test    ecx, ecx
0x18000786b  jz      short loc_18000787F
0x18000786d  mov     [rsp+38h+var_18], 4; unsigned int
0x180007875  call    ?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z; ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)
0x18000787a  add     rsp, 38h
0x18000787e  retn
0x18000787f  add     rsp, 38h
0x180007883  jmp     ?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z; ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)
```
