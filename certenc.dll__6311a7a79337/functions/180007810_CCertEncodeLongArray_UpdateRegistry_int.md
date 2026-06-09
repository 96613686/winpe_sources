# CCertEncodeLongArray::UpdateRegistry(int)

- ea: `0x180007810`
- end: `0x180007848`
- name: `?UpdateRegistry@CCertEncodeLongArray@@SAJH@Z`
- size: `56`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004788`
- `0x180004ae4`
- `0x180007810`

## pseudocode

```c
int __fastcall CCertEncodeLongArray::UpdateRegistry(ATL::CComModule *a1)
{
  if ( (_DWORD)a1 )
    return ATL::CComModule::RegisterClassHelper(
             a1,
             &CLSID_CCertEncodeLongArray,
             L"CertificateAuthority.EncodeLongArray.1",
             L"CertificateAuthority.EncodeLongArray",
             2u);
  else
    return ATL::CComModule::UnregisterClassHelper(
             (OLECHAR *)a1,
             &CLSID_CCertEncodeLongArray,
             L"CertificateAuthority.EncodeLongArray.1",
             L"CertificateAuthority.EncodeLongArray");
}

```

## disassembly

```asm
0x180007810  sub     rsp, 38h
0x180007814  lea     r9, aCertificateaut_6; "CertificateAuthority.EncodeLongArray"
0x18000781b  lea     r8, aCertificateaut_8; "CertificateAuthority.EncodeLongArray.1"
0x180007822  lea     rdx, CLSID_CCertEncodeLongArray; struct _GUID *
0x180007829  test    ecx, ecx
0x18000782b  jz      short loc_18000783F
0x18000782d  mov     [rsp+38h+var_18], 2; unsigned int
0x180007835  call    ?RegisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1IK@Z; ATL::CComModule::RegisterClassHelper(_GUID const &,ushort const *,ushort const *,uint,ulong)
0x18000783a  add     rsp, 38h
0x18000783e  retn
0x18000783f  add     rsp, 38h
0x180007843  jmp     ?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z; ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)
```
