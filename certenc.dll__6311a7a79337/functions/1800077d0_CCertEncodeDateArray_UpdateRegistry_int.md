# CCertEncodeDateArray::UpdateRegistry(int)

- ea: `0x1800077d0`
- end: `0x180007808`
- name: `?UpdateRegistry@CCertEncodeDateArray@@SAJH@Z`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004788`
- `0x180004ae4`
- `0x1800077d0`

## pseudocode

```c
int __fastcall CCertEncodeDateArray::UpdateRegistry(ATL::CComModule *a1)
{
  if ( (_DWORD)a1 )
    return ATL::CComModule::RegisterClassHelper(
             a1,
             &CLSID_CCertEncodeDateArray,
             L"CertificateAuthority.EncodeDateArray.1",
             L"CertificateAuthority.EncodeDateArray",
             1u);
  else
    return ATL::CComModule::UnregisterClassHelper(
             (OLECHAR *)a1,
             &CLSID_CCertEncodeDateArray,
             L"CertificateAuthority.EncodeDateArray.1",
             L"CertificateAuthority.EncodeDateArray");
}

```

## disassembly

```asm
0x1800077d0  sub     rsp, 38h
0x1800077d4  lea     r9, aCertificateaut_7; "CertificateAuthority.EncodeDateArray"
0x1800077db  lea     r8, aCertificateaut_10; "CertificateAuthority.EncodeDateArray.1"
0x1800077e2  lea     rdx, CLSID_CCertEncodeDateArray; struct _GUID *
0x1800077e9  test    ecx, ecx
0x1800077eb  jz      short loc_1800077FF
0x1800077ed  mov     [rsp+38h+var_18], 1; unsigned int
0x1800077f5  call    ?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z; ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)
0x1800077fa  add     rsp, 38h
0x1800077fe  retn
0x1800077ff  add     rsp, 38h
0x180007803  jmp     ?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z; ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)
```
