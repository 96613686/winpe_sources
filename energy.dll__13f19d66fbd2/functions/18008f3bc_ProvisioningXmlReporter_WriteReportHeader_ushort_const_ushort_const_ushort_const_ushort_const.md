# ProvisioningXmlReporter::WriteReportHeader(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18008f3bc`
- end: `0x18008f5b5`
- name: `?WriteReportHeader@ProvisioningXmlReporter@@IEAAKPEBG000@Z`
- size: `505`
- prototype: `unsigned int __fastcall(ProvisioningXmlReporter *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f294`

## callees

- `0x18000ff60`
- `0x18001107c`
- `0x18004ca90`
- `0x18008f3bc`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18008f409`
- `RPCRT4!UuidCreate` at `0x18008f409`

## string_xrefs

- `0x18008f413`: `<?xml version="1.0" encoding="utf-8"?>\n`
- `0x18008f433`: `  <PackageConfig xmlns="urn:schemas-Microsoft-com:Windows-ICD-Package-Config.v1.0">\n`
- `0x18008f53f`: `  <Settings xmlns="urn:schemas-microsoft-com:windows-provisioning">\n`
- `0x18008f521`: `  </PackageConfig>\n`
- `0x18008f55d`: `      <Common>\n`

## pseudocode

```c
__int64 __fastcall ProvisioningXmlReporter::WriteReportHeader(
        ProvisioningXmlReporter *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  bool v5; // zf
  unsigned int v10; // edi
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  UUID Uuid; // [rsp+20h] [rbp-58h] BYREF

  v5 = *((_DWORD *)this + 2) == 1;
  Uuid = 0;
  if ( !v5 || UuidCreate(&Uuid) )
  {
    return 1627;
  }
  else
  {
    v10 = 0;
    XmlReporter::WriteRawString(this, L"<?xml version=\"1.0\" encoding=\"utf-8\"?>\n");
    XmlReporter::WriteRawString(this, L"<WindowsCustomizatons>\n");
    XmlReporter::WriteRawString(
      this,
      L"  <PackageConfig xmlns=\"urn:schemas-Microsoft-com:Windows-ICD-Package-Config.v1.0\">\n");
    XmlReporter::WriteRawString(this, L"    <ID>");
    if ( a5 )
      XmlReporter::WriteRawString(this, a5);
    else
      XmlReporter::WriteGuid(this, &Uuid);
    XmlReporter::WriteRawString(this, L"</ID>\n");
    XmlReporter::WriteRawString(this, L"    <Name>");
    if ( a2 )
    {
      XmlReporter::WriteRawString(this, a2);
      v11 = L"</Name>\n";
    }
    else
    {
      v11 = L"CustomOEM.Power.Settings.Control</Name>\n";
    }
    XmlReporter::WriteRawString(this, v11);
    XmlReporter::WriteRawString(this, L"    <Version>");
    if ( a3 )
    {
      XmlReporter::WriteRawString(this, a3);
      v12 = L"</Version>\n";
    }
    else
    {
      v12 = L"1.0</Version>\n";
    }
    XmlReporter::WriteRawString(this, v12);
    XmlReporter::WriteRawString(this, L"    <OwnerType>");
    if ( a4 )
    {
      XmlReporter::WriteRawString(this, a4);
      v13 = L"</OwnerType>\n";
    }
    else
    {
      v13 = L"OEM</OwnerType>\n";
    }
    XmlReporter::WriteRawString(this, v13);
    XmlReporter::WriteRawString(this, L"  </PackageConfig>\n");
    XmlReporter::WriteRawString(this, L"\n");
    XmlReporter::WriteRawString(this, L"  <Settings xmlns=\"urn:schemas-microsoft-com:windows-provisioning\">\n");
    XmlReporter::WriteRawString(this, L"    <Customizations>\n");
    XmlReporter::WriteRawString(this, L"      <Common>\n");
    XmlReporter::WriteRawString(this, L"          <Power>\n");
    XmlReporter::WriteRawString(this, L"            <Policy>\n");
    XmlReporter::WriteRawString(this, L"              <Settings>\n");
  }
  return v10;
}

```

## disassembly

```asm
0x18008f3bc  push    rbx
0x18008f3be  push    rbp
0x18008f3bf  push    rsi
0x18008f3c0  push    rdi
0x18008f3c1  push    r14
0x18008f3c3  push    r15
0x18008f3c5  sub     rsp, 48h
0x18008f3c9  mov     rax, cs:__security_cookie
0x18008f3d0  xor     rax, rsp
0x18008f3d3  mov     [rsp+78h+var_48], rax
0x18008f3d8  cmp     dword ptr [rcx+8], 1
0x18008f3dc  xorps   xmm0, xmm0
0x18008f3df  mov     rbp, [rsp+78h+arg_20]
0x18008f3e7  mov     r14, r9
0x18008f3ea  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18008f3ef  mov     r15, r8
0x18008f3f2  mov     rsi, rdx
0x18008f3f5  mov     rbx, rcx
0x18008f3f8  jz      short loc_18008F404
0x18008f3fa  mov     edi, 65Bh
0x18008f3ff  jmp     loc_18008F599
0x18008f404  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18008f409  call    cs:__imp_UuidCreate
0x18008f40f  test    eax, eax
0x18008f411  jnz     short loc_18008F3FA
0x18008f413  lea     rdx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18008f41a  mov     rcx, rbx; this
0x18008f41d  xor     edi, edi
0x18008f41f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f424  lea     rdx, aWindowscustomi; "<WindowsCustomizatons>\n"
0x18008f42b  mov     rcx, rbx; this
0x18008f42e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f433  lea     rdx, aPackageconfigX; "  <PackageConfig xmlns=\"urn:schemas-Mi"...
0x18008f43a  mov     rcx, rbx; this
0x18008f43d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f442  lea     rdx, aId; "    <ID>"
0x18008f449  mov     rcx, rbx; this
0x18008f44c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f451  mov     rcx, rbx; this
0x18008f454  test    rbp, rbp
0x18008f457  jnz     short loc_18008F465
0x18008f459  lea     rdx, [rsp+78h+Uuid]; struct _GUID *
0x18008f45e  call    ?WriteGuid@XmlReporter@@IEAAKPEBU_GUID@@@Z; XmlReporter::WriteGuid(_GUID const *)
0x18008f463  jmp     short loc_18008F46D
0x18008f465  mov     rdx, rbp; unsigned __int16 *
0x18008f468  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f46d  lea     rdx, aId_5; "</ID>\n"
0x18008f474  mov     rcx, rbx; this
0x18008f477  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f47c  lea     rdx, aName_4; "    <Name>"
0x18008f483  mov     rcx, rbx; this
0x18008f486  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f48b  test    rsi, rsi
0x18008f48e  jnz     short loc_18008F499
0x18008f490  lea     rdx, aCustomoemPower; "CustomOEM.Power.Settings.Control</Name>"...
0x18008f497  jmp     short loc_18008F4AB
0x18008f499  mov     rdx, rsi; unsigned __int16 *
0x18008f49c  mov     rcx, rbx; this
0x18008f49f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f4a4  lea     rdx, aName_2; "</Name>\n"
0x18008f4ab  mov     rcx, rbx; this
0x18008f4ae  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f4b3  lea     rdx, aVersion_0; "    <Version>"
0x18008f4ba  mov     rcx, rbx; this
0x18008f4bd  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f4c2  test    r15, r15
0x18008f4c5  jnz     short loc_18008F4D0
0x18008f4c7  lea     rdx, a10Version; "1.0</Version>\n"
0x18008f4ce  jmp     short loc_18008F4E2
0x18008f4d0  mov     rdx, r15; unsigned __int16 *
0x18008f4d3  mov     rcx, rbx; this
0x18008f4d6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f4db  lea     rdx, aVersion; "</Version>\n"
0x18008f4e2  mov     rcx, rbx; this
0x18008f4e5  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f4ea  lea     rdx, aOwnertype_0; "    <OwnerType>"
0x18008f4f1  mov     rcx, rbx; this
0x18008f4f4  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f4f9  test    r14, r14
0x18008f4fc  jnz     short loc_18008F507
0x18008f4fe  lea     rdx, aOemOwnertype; "OEM</OwnerType>\n"
0x18008f505  jmp     short loc_18008F519
0x18008f507  mov     rdx, r14; unsigned __int16 *
0x18008f50a  mov     rcx, rbx; this
0x18008f50d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f512  lea     rdx, aOwnertype; "</OwnerType>\n"
0x18008f519  mov     rcx, rbx; this
0x18008f51c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f521  lea     rdx, aPackageconfig; "  </PackageConfig>\n"
0x18008f528  mov     rcx, rbx; this
0x18008f52b  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f530  lea     rdx, asc_18009E340; "\n"
0x18008f537  mov     rcx, rbx; this
0x18008f53a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f53f  lea     rdx, aSettingsXmlnsU; "  <Settings xmlns=\"urn:schemas-microso"...
0x18008f546  mov     rcx, rbx; this
0x18008f549  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f54e  lea     rdx, aCustomizations; "    <Customizations>\n"
0x18008f555  mov     rcx, rbx; this
0x18008f558  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f55d  lea     rdx, aCommon; "      <Common>\n"
0x18008f564  mov     rcx, rbx; this
0x18008f567  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f56c  lea     rdx, aPower_1; "          <Power>\n"
0x18008f573  mov     rcx, rbx; this
0x18008f576  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f57b  lea     rdx, aPolicy; "            <Policy>\n"
0x18008f582  mov     rcx, rbx; this
0x18008f585  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f58a  lea     rdx, aSettings_2; "              <Settings>\n"
0x18008f591  mov     rcx, rbx; this
0x18008f594  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008f599  mov     eax, edi
0x18008f59b  mov     rcx, [rsp+78h+var_48]
0x18008f5a0  xor     rcx, rsp; StackCookie
0x18008f5a3  call    __security_check_cookie
0x18008f5a8  add     rsp, 48h
0x18008f5ac  pop     r15
0x18008f5ae  pop     r14
0x18008f5b0  pop     rdi
0x18008f5b1  pop     rsi
0x18008f5b2  pop     rbp
0x18008f5b3  pop     rbx
0x18008f5b4  retn
```
