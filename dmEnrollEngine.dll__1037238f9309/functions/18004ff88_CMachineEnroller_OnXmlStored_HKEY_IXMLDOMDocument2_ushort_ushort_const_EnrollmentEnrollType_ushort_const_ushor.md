# CMachineEnroller::OnXmlStored(HKEY__ *,IXMLDOMDocument2 *,ushort *,ushort const *,EnrollmentEnrollType,ushort const *,ushort,int,int,ulong)

- ea: `0x18004ff88`
- end: `0x180050552`
- name: `?OnXmlStored@CMachineEnroller@@SAJPEAUHKEY__@@PEAUIXMLDOMDocument2@@PEAGPEBGW4EnrollmentEnrollType@@3GHHK@Z`
- size: `1482`
- prototype: `__int64 __fastcall(HKEY, struct IXMLDOMDocument2 *, OLECHAR *, unsigned __int16 *, unsigned int, __int64, __int16, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180050558`

## callees

- `0x18000de50`
- `0x18001208c`
- `0x180012370`
- `0x18001367c`
- `0x180016508`
- `0x18001aec8`
- `0x180020cb4`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18003aabc`
- `0x18003dba8`
- `0x1800460a4`
- `0x18004c594`
- `0x18004e5a4`
- `0x18004ee14`
- `0x18004ef34`
- `0x18004f260`
- `0x18004f648`
- `0x18004f938`
- `0x18004ff88`
- `0x180050b00`
- `0x18005c50c`
- `0x18007150c`
- `0x180071c00`
- `0x180071c90`
- `0x180072284`
- `0x180072338`
- `0x1800723ec`
- `0x18007b010`

## import_xrefs

- `omadmapi!__imp_OmaDmSetAcctInfo` at `0x1800502fe`
- `omadmapi!__imp_OmaDmSetAcctInfo` at `0x1800502fe`
- `omadmapi!__imp_OmaDmDeleteAcctInfo` at `0x18005003c`
- `omadmapi!__imp_OmaDmDeleteAcctInfo` at `0x18005003c`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x1800502df`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x1800502df`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800501c9`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800501c9`
- `enterpriseresourcemanager!EnterpriseResourceManagerStore_RemoveAllIgnoredUri` at `0x1800504c2`
- `enterpriseresourcemanager!EnterpriseResourceManagerStore_RemoveAllIgnoredUri` at `0x1800504c2`

## string_xrefs

- `0x1800500f9`: `//characteristic[@type='Registry']`
- `0x180050231`: `//characteristic[@type='Registry']`
- `0x180050360`: `FailedProvXML.txt`
- `0x1800503ba`: `FailedProvXML.txt`
- `0x1800501bc`: `RootCertAlreadyExisted`
- `0x180050397`: `CMachineEnroller::OnXmlStored`

## pseudocode

```c
__int64 __fastcall CMachineEnroller::OnXmlStored(
        HKEY a1,
        struct IXMLDOMDocument2 *a2,
        OLECHAR *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        __int64 a6,
        __int16 a7,
        int a8,
        int a9,
        unsigned int a10)
{
  __int64 v11; // r8
  unsigned __int16 *v12; // r10
  unsigned __int16 *v13; // rdi
  unsigned __int16 *v14; // rsi
  unsigned __int16 *v15; // r14
  int v16; // eax
  int v17; // r15d
  HRESULT (__stdcall *get_xml)(IXMLDOMDocument2 *, BSTR *); // rbx
  __int64 v19; // rax
  int v20; // ebx
  int v21; // eax
  HRESULT (__stdcall *v22)(IXMLDOMDocument2 *, BSTR *); // rbx
  __int64 v23; // rax
  int v24; // ebx
  int v25; // eax
  CEnrollmentLogger *v26; // rax
  const unsigned __int16 *v27; // r8
  int v28; // r12d
  CEnrollmentLogger *Logger; // rax
  __int64 v30; // rcx
  int v31; // ebx
  CEnrollmentLogger *v32; // rax
  const unsigned __int16 *v33; // r9
  HKEY v34; // rdi
  CEnrollmentLogger *v35; // rax
  CEnrollmentLogger *v36; // rax
  CEnrollmentLogger *v37; // rax
  int v39[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+84h] [rbp-7Ch] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  int v44; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int16 *v45; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+98h] [rbp-68h]
  OLECHAR *v47; // [rsp+A0h] [rbp-60h]
  HKEY v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v50; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v51; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v52; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v53; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v54; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v57[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v58; // [rsp+100h] [rbp+0h]
  _BYTE v59[40]; // [rsp+108h] [rbp+8h] BYREF
  int v60; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v61[508]; // [rsp+134h] [rbp+34h] BYREF

  v47 = a3;
  v48 = a1;
  v40 = a4;
  v49 = a6;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v59);
  v57[0] = 0;
  v55 = 0;
  v54 = 0;
  v13 = 0;
  v53 = 0;
  v14 = 0;
  v52 = 0;
  v15 = 0;
  v51 = 0;
  v56 = 0;
  v50 = 0;
  v41 = 0;
  v44 = 0;
  v45 = 0;
  v43 = 0;
  v42 = 0;
  v57[1] = &v40;
  v58 = 1;
  if ( !a8 && !a9 )
  {
    v16 = OmaDmDeleteAcctInfo(v11);
    v17 = 0;
    if ( v16 != -2147024894 )
      v17 = v16;
    if ( v17 < 0 )
      goto LABEL_52;
    v12 = v40;
  }
  v46 = a10 & 0x80;
  if ( (a10 & 0x80) == 0 )
  {
    v17 = CMachineEnroller::ExtractCertThumbs(a2, v12, &v53, &v52, &v51, a10, &v43, &v42);
    if ( v17 < 0 )
      goto LABEL_52;
    v13 = v53;
    v14 = v52;
    v15 = v51;
    v12 = v40;
  }
  if ( !a8 && !a9 )
  {
    v17 = CMachineEnroller::HandleBackCompatForBlueDesktop(a2, v47, v12, v48, &v44);
    if ( v17 < 0 )
      goto LABEL_52;
    CMachineEnroller::RemoveProvXMLNode(a2, L"//characteristic[@type='Registry']", 0);
    v39[0] = 0;
    v17 = Mmpc_IsOnPremiseSupportingDevice(v39);
    if ( v17 < 0 )
      goto LABEL_52;
    if ( v39[0] )
    {
      CMachineEnroller::RemoveProvXMLNode(
        a2,
        L"wap-provisioningdoc/characteristic[@type='DMClient']/characteristic[@type='Provider']/*/parm[@name='AADResourceID']",
        0);
      CMachineEnroller::RemoveProvXMLNode(
        a2,
        L"wap-provisioningdoc/characteristic[@type='DMClient']/characteristic[@type='Provider']/*/characteristic[@type='Pu"
         "sh']/parm[@name='PFN']",
        0);
    }
    get_xml = a2->lpVtbl->get_xml;
    v19 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v54);
    v17 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64))get_xml)(a2, v19);
    if ( v17 < 0 )
      goto LABEL_52;
    v20 = (int)v40;
    v21 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v45);
    v17 = InternalDMProcessConfigXML(v54, v21, (_DWORD)v47, v20, v49, a7);
LABEL_26:
    if ( v17 >= 0 )
      goto LABEL_27;
LABEL_28:
    v39[0] = 0;
    HlpLogAllProvXMLFailures(v45, v39);
    v28 = v39[0];
    if ( v39[0] >= 0 )
      v28 = -2145910749;
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollOMADMClientConfigFail(Logger, v28, v17);
    v31 = WriteToTempFile(v45, L"FailedProvXML.txt");
    if ( v17 == -2102788095 )
    {
      v32 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollProvisioningBadXMLError(v32, "CMachineEnroller::OnXmlStored");
    }
    else if ( v17 != -2102657014 && v17 != -2046820317 )
    {
      v17 = v28;
    }
    if ( v31 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
        McTemplateU0zq_EventWriteTransfer(v30, SavingTempFileFailedEvent, L"FailedProvXML.txt", (unsigned int)v31);
      goto LABEL_52;
    }
    if ( v17 < 0 )
      goto LABEL_52;
    goto LABEL_39;
  }
  OmaDmRegistryGetDWORD(v48, 0, L"RootCertAlreadyExisted", &v41);
  v17 = CMachineEnroller::ExtractNodeStringValue(
          a2,
          L"wap-provisioningdoc/characteristic[@type='APPLICATION']/parm[@name='SSLCLIENTCERTSEARCHCRITERIA']/@value",
          &v50,
          1);
  if ( v17 < 0 )
    goto LABEL_52;
  CMachineEnroller::RemoveProvXMLNode(a2, L"//characteristic[@type='APPLICATION']", 0);
  CMachineEnroller::RemoveProvXMLNode(a2, L"//characteristic[@type='DMClient']", 0);
  if ( a9 )
  {
    CMachineEnroller::RemoveProvXMLNode(
      a2,
      L"//characteristic[@type='CertificateStore']/characteristic[@type='My']/characteristic[@type='WSTEP']",
      0);
    CMachineEnroller::RemoveProvXMLNode(a2, L"//characteristic[@type='Registry']", 0);
  }
  v22 = a2->lpVtbl->get_xml;
  v23 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v55);
  v17 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64))v22)(a2, v23);
  if ( v17 < 0 )
    goto LABEL_52;
  v24 = (int)v40;
  v25 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v45);
  v17 = InternalDMProcessConfigXML(v55, v25, (_DWORD)v47, v24, v49, a7);
  if ( v17 < 0 )
    goto LABEL_28;
  if ( v50 )
  {
    memset_0(v61, 0, sizeof(v61));
    v60 = 512;
    v17 = OmaDmSetValueInStruct(23, &v60, 0xFFFFFFFFLL);
    if ( v17 < 0 )
      goto LABEL_52;
    v17 = OmaDmSetAcctInfo(v40, 1, &v60);
    if ( v17 < 0 )
      goto LABEL_52;
    goto LABEL_26;
  }
LABEL_27:
  v26 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogEnrollOMADMClientConfigSuccess(v26);
LABEL_39:
  if ( !v46 )
  {
    v33 = v13;
    v34 = v48;
    v17 = CMachineEnroller::FixupCerts(v48, v40, v27, v33, v14, v15, a8, a9, a10, v43, v42, v41);
    if ( v17 < 0 )
    {
      v35 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollBindCertsFailed(v35, v17);
      goto LABEL_52;
    }
    v17 = CMachineEnroller::CleanupCertContainers(v34);
    if ( v17 < 0 )
      goto LABEL_52;
  }
  if ( v44 )
  {
    if ( a8 || a9 )
      goto LABEL_52;
  }
  else
  {
    if ( a8 || a9 )
      goto LABEL_52;
    v17 = SyncPollingOptions(v40, v49, v27, a5);
    if ( v17 < 0 )
    {
      v36 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollDMPollScheduleSetupFail(v36, v17);
      goto LABEL_52;
    }
  }
  v17 = SyncPollingOptionsForMultipleSession(v40);
  if ( v17 < 0 )
  {
    v37 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollScheduleForMultipleSessionSetupFail(v37, v17);
  }
LABEL_52:
  EnterpriseResourceManagerStore_RemoveAllIgnoredUri(v40);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v50);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v56);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v51);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v52);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v53);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v57);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v59);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18004ff88  push    rbp
0x18004ff8a  push    rbx
0x18004ff8b  push    rsi
0x18004ff8c  push    rdi
0x18004ff8d  push    r12
0x18004ff8f  push    r13
0x18004ff91  push    r14
0x18004ff93  push    r15
0x18004ff95  lea     rbp, [rsp-248h]
0x18004ff9d  sub     rsp, 348h
0x18004ffa4  mov     rax, cs:__security_cookie
0x18004ffab  xor     rax, rsp
0x18004ffae  mov     [rbp+280h+var_50], rax
0x18004ffb5  mov     r10, r9
0x18004ffb8  mov     [rbp+280h+var_2E0], r8
0x18004ffbc  mov     r12, rdx
0x18004ffbf  mov     [rbp+280h+var_2D8], rcx
0x18004ffc3  mov     [rsp+380h+var_310], r9
0x18004ffc8  mov     rax, [rbp+280h+arg_28]
0x18004ffcf  mov     [rbp+280h+var_2D0], rax
0x18004ffd3  lea     rcx, [rbp+280h+var_278]
0x18004ffd7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004ffdc  nop
0x18004ffdd  xor     edx, edx
0x18004ffdf  mov     [rbp+280h+var_290], rdx
0x18004ffe3  mov     [rbp+280h+var_2A0], rdx
0x18004ffe7  mov     [rbp+280h+var_2A8], rdx
0x18004ffeb  mov     edi, edx
0x18004ffed  mov     [rbp+280h+var_2B0], rdx
0x18004fff1  mov     esi, edx
0x18004fff3  mov     [rbp+280h+var_2B8], rdx
0x18004fff7  mov     r14d, edx
0x18004fffa  mov     [rbp+280h+var_2C0], rdx
0x18004fffe  mov     [rbp+280h+var_298], rdx
0x180050002  mov     [rbp+280h+var_2C8], rdx
0x180050006  mov     [rbp+280h+var_300], edx
0x180050009  mov     [rbp+280h+var_2F4], edx
0x18005000c  mov     [rbp+280h+var_2F0], rdx
0x180050010  mov     [rbp+280h+var_2F8], edx
0x180050013  mov     [rbp+280h+var_2FC], edx
0x180050016  lea     rax, [rsp+380h+var_310]
0x18005001b  mov     [rbp+280h+var_288], rax
0x18005001f  mov     [rbp+280h+var_280], 1
0x180050023  mov     r13d, [rbp+280h+arg_40]
0x18005002a  mov     ebx, [rbp+280h+arg_38]
0x180050030  test    ebx, ebx
0x180050032  jnz     short loc_18005005E
0x180050034  test    r13d, r13d
0x180050037  jnz     short loc_18005005E
0x180050039  mov     rcx, r8
0x18005003c  call    cs:__imp_OmaDmDeleteAcctInfo
0x180050042  xor     edx, edx
0x180050044  mov     r15d, edx
0x180050047  cmp     eax, 80070002h
0x18005004c  cmovnz  r15d, eax
0x180050050  test    r15d, r15d
0x180050053  js      loc_1800504BD
0x180050059  mov     r10, [rsp+380h+var_310]
0x18005005e  mov     ecx, dword ptr [rbp+280h+arg_48]
0x180050064  mov     eax, ecx
0x180050066  and     eax, 80h
0x18005006b  mov     [rbp+280h+var_2E8], eax
0x18005006e  jnz     short loc_1800500BE
0x180050070  lea     rax, [rbp+280h+var_2FC]
0x180050074  mov     [rsp+380h+var_348], rax; int *
0x180050079  lea     rax, [rbp+280h+var_2F8]
0x18005007d  mov     [rsp+380h+var_350], rax; int *
0x180050082  mov     dword ptr [rsp+380h+var_358], ecx; char
0x180050086  lea     rax, [rbp+280h+var_2C0]
0x18005008a  mov     [rsp+380h+var_360], rax; unsigned __int16 **
0x18005008f  lea     r9, [rbp+280h+var_2B8]; unsigned __int16 **
0x180050093  lea     r8, [rbp+280h+var_2B0]; unsigned __int16 **
0x180050097  mov     rdx, r10; unsigned __int16 *
0x18005009a  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18005009d  call    ?ExtractCertThumbs@CMachineEnroller@@CAJPEAUIXMLDOMDocument2@@PEBGPEAPEAG22KPEAH3@Z; CMachineEnroller::ExtractCertThumbs(IXMLDOMDocument2 *,ushort const *,ushort * *,ushort * *,ushort * *,ulong,int *,int *)
0x1800500a2  mov     r15d, eax
0x1800500a5  test    eax, eax
0x1800500a7  js      loc_1800504BD
0x1800500ad  mov     rdi, [rbp+280h+var_2B0]
0x1800500b1  mov     rsi, [rbp+280h+var_2B8]
0x1800500b5  mov     r14, [rbp+280h+var_2C0]
0x1800500b9  mov     r10, [rsp+380h+var_310]
0x1800500be  test    ebx, ebx
0x1800500c0  jnz     loc_1800501B8
0x1800500c6  test    r13d, r13d
0x1800500c9  jnz     loc_1800501B8
0x1800500cf  lea     rax, [rbp+280h+var_2F4]
0x1800500d3  mov     [rsp+380h+var_360], rax; int *
0x1800500d8  mov     r9, [rbp+280h+var_2D8]; HKEY
0x1800500dc  mov     r8, r10; psz
0x1800500df  mov     rdx, [rbp+280h+var_2E0]; OLECHAR *
0x1800500e3  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800500e6  call    ?HandleBackCompatForBlueDesktop@CMachineEnroller@@CAJPEAUIXMLDOMDocument2@@PEAGPEBGPEAUHKEY__@@PEAH@Z; CMachineEnroller::HandleBackCompatForBlueDesktop(IXMLDOMDocument2 *,ushort *,ushort const *,HKEY__ *,int *)
0x1800500eb  mov     r15d, eax
0x1800500ee  test    eax, eax
0x1800500f0  js      loc_1800504BD
0x1800500f6  xor     r8d, r8d; unsigned __int16 *
0x1800500f9  lea     rdx, aCharacteristic_0; "//characteristic[@type='Registry']"
0x180050100  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180050103  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180050108  mov     [rsp+380h+var_320], r13d
0x18005010d  lea     rcx, [rsp+380h+var_320]; int *
0x180050112  call    ?Mmpc_IsOnPremiseSupportingDevice@@YAJPEAH@Z; Mmpc_IsOnPremiseSupportingDevice(int *)
0x180050117  mov     r15d, eax
0x18005011a  test    eax, eax
0x18005011c  js      loc_1800504BD
0x180050122  cmp     [rsp+380h+var_320], r13d
0x180050127  jz      short loc_18005014D
0x180050129  xor     r8d, r8d; unsigned __int16 *
0x18005012c  lea     rdx, aWapProvisionin_8; "wap-provisioningdoc/characteristic[@typ"...
0x180050133  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180050136  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x18005013b  xor     r8d, r8d; unsigned __int16 *
0x18005013e  lea     rdx, aWapProvisionin_12; "wap-provisioningdoc/characteristic[@typ"...
0x180050145  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180050148  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x18005014d  mov     rax, [r12]
0x180050151  mov     rbx, [rax+110h]
0x180050158  lea     rcx, [rbp+280h+var_2A8]
0x18005015c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180050161  mov     rdx, rax
0x180050164  mov     rcx, r12
0x180050167  mov     rax, rbx
0x18005016a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005016f  mov     r15d, eax
0x180050172  test    eax, eax
0x180050174  js      loc_1800504BD
0x18005017a  mov     rbx, [rsp+380h+var_310]
0x18005017f  lea     rcx, [rbp+280h+var_2F0]
0x180050183  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180050188  movzx   ecx, [rbp+280h+arg_30]
0x18005018f  mov     word ptr [rsp+380h+var_358], cx
0x180050194  mov     rcx, [rbp+280h+var_2D0]
0x180050198  mov     [rsp+380h+var_360], rcx
0x18005019d  mov     r9, rbx
0x1800501a0  mov     r8, [rbp+280h+var_2E0]
0x1800501a4  mov     rdx, rax
0x1800501a7  mov     rcx, [rbp+280h+var_2A8]
0x1800501ab  call    InternalDMProcessConfigXML
0x1800501b0  mov     r15d, eax
0x1800501b3  jmp     loc_18005030F
0x1800501b8  lea     r9, [rbp+280h+var_300]
0x1800501bc  lea     r8, aRootcertalread; "RootCertAlreadyExisted"
0x1800501c3  xor     edx, edx
0x1800501c5  mov     rcx, [rbp+280h+var_2D8]
0x1800501c9  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800501cf  mov     r9d, 1; int
0x1800501d5  lea     r8, [rbp+280h+var_2C8]; unsigned __int16 **
0x1800501d9  lea     rdx, aWapProvisionin_10; "wap-provisioningdoc/characteristic[@typ"...
0x1800501e0  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800501e3  call    ?ExtractNodeStringValue@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBGPEAPEAGH@Z; CMachineEnroller::ExtractNodeStringValue(IXMLDOMDocument2 *,ushort const *,ushort * *,int)
0x1800501e8  mov     r15d, eax
0x1800501eb  test    eax, eax
0x1800501ed  js      loc_1800504BD
0x1800501f3  xor     r8d, r8d; unsigned __int16 *
0x1800501f6  lea     rdx, aCharacteristic_1; "//characteristic[@type='APPLICATION']"
0x1800501fd  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180050200  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180050205  xor     r8d, r8d; unsigned __int16 *
0x180050208  lea     rdx, aCharacteristic_5; "//characteristic[@type='DMClient']"
0x18005020f  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180050212  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180050217  test    r13d, r13d
0x18005021a  jz      short loc_180050240
0x18005021c  xor     r8d, r8d; unsigned __int16 *
0x18005021f  lea     rdx, aCharacteristic_4; "//characteristic[@type='CertificateStor"...
0x180050226  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180050229  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x18005022e  xor     r8d, r8d; unsigned __int16 *
0x180050231  lea     rdx, aCharacteristic_0; "//characteristic[@type='Registry']"
0x180050238  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18005023b  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180050240  mov     rax, [r12]
0x180050244  mov     rbx, [rax+110h]
0x18005024b  lea     rcx, [rbp+280h+var_2A0]
0x18005024f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180050254  mov     rdx, rax
0x180050257  mov     rcx, r12
0x18005025a  mov     rax, rbx
0x18005025d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050262  mov     r15d, eax
0x180050265  test    eax, eax
0x180050267  js      loc_1800504BD
0x18005026d  mov     rbx, [rsp+380h+var_310]
0x180050272  lea     rcx, [rbp+280h+var_2F0]
0x180050276  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18005027b  movzx   ecx, [rbp+280h+arg_30]
0x180050282  mov     word ptr [rsp+380h+var_358], cx
0x180050287  mov     rcx, [rbp+280h+var_2D0]
0x18005028b  mov     [rsp+380h+var_360], rcx
0x180050290  mov     r9, rbx
0x180050293  mov     r8, [rbp+280h+var_2E0]
0x180050297  mov     rdx, rax
0x18005029a  mov     rcx, [rbp+280h+var_2A0]
0x18005029e  call    InternalDMProcessConfigXML
0x1800502a3  mov     r15d, eax
0x1800502a6  test    eax, eax
0x1800502a8  js      short loc_180050326
0x1800502aa  mov     rbx, [rbp+280h+var_2C8]
0x1800502ae  test    rbx, rbx
0x1800502b1  jz      short loc_180050314
0x1800502b3  xor     edx, edx; Val
0x1800502b5  mov     r8d, 1FCh; Size
0x1800502bb  lea     rcx, [rbp+280h+var_24C]; void *
0x1800502bf  call    memset_0
0x1800502c4  mov     [rbp+280h+var_250], 200h
0x1800502cb  mov     [rsp+380h+var_360], rbx
0x1800502d0  xor     r9d, r9d
0x1800502d3  or      r8d, 0FFFFFFFFh
0x1800502d7  lea     rdx, [rbp+280h+var_250]
0x1800502db  lea     ecx, [r9+17h]
0x1800502df  call    cs:__imp_OmaDmSetValueInStruct
0x1800502e5  mov     r15d, eax
0x1800502e8  test    eax, eax
0x1800502ea  js      loc_1800504BD
0x1800502f0  lea     r8, [rbp+280h+var_250]
0x1800502f4  mov     edx, 1
0x1800502f9  mov     rcx, [rsp+380h+var_310]
0x1800502fe  call    cs:__imp_OmaDmSetAcctInfo
0x180050304  mov     r15d, eax
0x180050307  test    eax, eax
0x180050309  js      loc_1800504BD
0x18005030f  test    r15d, r15d
0x180050312  js      short loc_180050326
0x180050314  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180050319  mov     rcx, rax; this
0x18005031c  call    ?LogEnrollOMADMClientConfigSuccess@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogEnrollOMADMClientConfigSuccess(void)
0x180050321  jmp     loc_1800503DB
0x180050326  mov     [rsp+380h+var_320], 0
0x18005032e  lea     rdx, [rsp+380h+var_320]; int *
0x180050333  mov     rcx, [rbp+280h+var_2F0]; unsigned __int16 *
0x180050337  call    ?HlpLogAllProvXMLFailures@@YAJPEAGPEAJ@Z; HlpLogAllProvXMLFailures(ushort *,long *)
0x18005033c  mov     r12d, [rsp+380h+var_320]
0x180050341  mov     eax, 80180023h
0x180050346  test    r12d, r12d
0x180050349  cmovns  r12d, eax
0x18005034d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180050352  mov     r8d, r15d; int
0x180050355  mov     edx, r12d; int
0x180050358  mov     rcx, rax; this
0x18005035b  call    ?LogEnrollOMADMClientConfigFail@CEnrollmentLogger@@QEAAXJJ@Z; CEnrollmentLogger::LogEnrollOMADMClientConfigFail(long,long)
0x180050360  lea     rdx, aFailedprovxmlT; "FailedProvXML.txt"
0x180050367  mov     rcx, [rbp+280h+var_2F0]; unsigned __int16 *
0x18005036b  call    ?WriteToTempFile@@YAJPEBG0@Z; WriteToTempFile(ushort const *,ushort const *)
0x180050370  mov     ebx, eax
0x180050372  cmp     r15d, 82AA0001h
0x180050379  jz      short loc_180050392
0x18005037b  cmp     r15d, 82AC000Ah
0x180050382  jz      short loc_1800503A6
0x180050384  cmp     r15d, 86000023h
0x18005038b  jz      short loc_1800503A6
0x18005038d  mov     r15d, r12d
0x180050390  jmp     short loc_1800503A6
0x180050392  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180050397  lea     rdx, aCmachineenroll_0; "CMachineEnroller::OnXmlStored"
0x18005039e  mov     rcx, rax; this
0x1800503a1  call    ?LogEnrollProvisioningBadXMLError@CEnrollmentLogger@@QEAAXPEBD@Z; CEnrollmentLogger::LogEnrollProvisioningBadXMLError(char const *)
0x1800503a6  test    ebx, ebx
0x1800503a8  jns     short loc_1800503D2
0x1800503aa  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x1800503b1  jz      loc_1800504BD
0x1800503b7  mov     r9d, ebx
0x1800503ba  lea     r8, aFailedprovxmlT; "FailedProvXML.txt"
0x1800503c1  lea     rdx, SavingTempFileFailedEvent
0x1800503c8  call    McTemplateU0zq_EventWriteTransfer
0x1800503cd  jmp     loc_1800504BD
0x1800503d2  test    r15d, r15d
0x1800503d5  js      loc_1800504BD
0x1800503db  mov     ebx, [rbp+280h+arg_38]
0x1800503e1  cmp     [rbp+280h+var_2E8], 0
0x1800503e5  jnz     short loc_180050455
0x1800503e7  mov     eax, [rbp+280h+var_300]
0x1800503ea  mov     [rsp+380h+var_328], eax; unsigned int
0x1800503ee  mov     eax, [rbp+280h+var_2FC]
0x1800503f1  mov     [rsp+380h+var_330], eax; int
0x1800503f5  mov     eax, [rbp+280h+var_2F8]
0x1800503f8  mov     [rsp+380h+var_338], eax; int
0x1800503fc  mov     eax, dword ptr [rbp+280h+arg_48]
0x180050402  mov     [rsp+380h+var_340], eax; unsigned int
0x180050406  mov     dword ptr [rsp+380h+var_348], r13d; int
0x18005040b  mov     dword ptr [rsp+380h+var_350], ebx; int
0x18005040f  mov     [rsp+380h+var_358], r14; unsigned __int16 *
0x180050414  mov     [rsp+380h+var_360], rsi; unsigned __int16 *
0x180050419  mov     r9, rdi; unsigned __int16 *
0x18005041c  mov     rdx, [rsp+380h+var_310]; unsigned __int16 *
0x180050421  mov     rdi, [rbp+280h+var_2D8]
0x180050425  mov     rcx, rdi; HKEY
0x180050428  call    ?FixupCerts@CMachineEnroller@@CAJPEAUHKEY__@@PEBG1111HHKHHK@Z; CMachineEnroller::FixupCerts(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,int,ulong,int,int,ulong)
0x18005042d  mov     r15d, eax
0x180050430  test    eax, eax
0x180050432  jns     short loc_180050446
0x180050434  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180050439  mov     edx, r15d; int
0x18005043c  mov     rcx, rax; this
0x18005043f  call    ?LogEnrollBindCertsFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollBindCertsFailed(long)
0x180050444  jmp     short loc_1800504BD
0x180050446  mov     rcx, rdi; HKEY
0x180050449  call    ?CleanupCertContainers@CMachineEnroller@@SAJPEAUHKEY__@@@Z; CMachineEnroller::CleanupCertContainers(HKEY__ *)
0x18005044e  mov     r15d, eax
0x180050451  test    eax, eax
  ... truncated ...
```
