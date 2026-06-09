# RasUser::processUser(IASTL::IASRequest &,ushort const *,ushort const *)

- ea: `0x180024890`
- end: `0x180024cf7`
- name: `?processUser@RasUser@@UEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@PEBG1@Z`
- size: `1127`
- prototype: `enum _IASREQUESTSTATUS __high(struct IASTL::IASRequest *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001c88`
- `0x18000a4a8`
- `0x18000a760`
- `0x18000acf4`
- `0x18000bf20`
- `0x18000c4a4`
- `0x18000d49c`
- `0x18000d55c`
- `0x180016884`
- `0x1800169e0`
- `0x18001d8d0`
- `0x18001d9a4`
- `0x180024890`
- `0x180024d00`
- `0x1800254a0`
- `0x1800285c8`
- `0x18002944c`
- `0x18002b472`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180024a28`
- `KERNEL32!LocalFree` at `0x180024a28`
- `WLDAP32!__imp_ldap_first_entry` at `0x180024975`
- `WLDAP32!__imp_ldap_first_entry` at `0x180024975`
- `WLDAP32!__imp_ldap_get_dnW` at `0x180024989`
- `WLDAP32!__imp_ldap_get_dnW` at `0x180024989`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800249b9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800249b9`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800249a6`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800249a6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800249dd`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800249dd`
- `WLDAP32!__imp_ldap_conn_from_msg` at `0x180024964`
- `WLDAP32!__imp_ldap_conn_from_msg` at `0x180024964`

## string_xrefs

- `0x180024a87`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x180024b99`: `Inserting attribute msRADIUSServiceType.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RasUser::processUser(_QWORD *a1, __int64 a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  DWORD UserAttributes; // eax
  DWORD RasUser0; // ebx
  LDAP *v10; // rdi
  LDAPMessage *entry; // rax
  LDAPMessage *v12; // r15
  unsigned __int16 *dnW; // rbx
  PWCHAR *valuesW; // rax
  PWCHAR *v15; // rdi
  PWCHAR v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  _DWORD *v22; // rax
  bool v23; // dl
  char v24; // cl
  _DWORD *v25; // rbx
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v28; // [rsp+40h] [rbp-C0h]
  LDAPMessage *res[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR WideCharStr[135]; // [rsp+62h] [rbp-9Eh] BYREF
  char Buffer[256]; // [rsp+170h] [rbp+70h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Using downlevel dial-in parameters.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids, "NPSSVC");
  }
  memset_0(v30, 0, 0x104u);
  *(_OWORD *)res = 0;
  UserAttributes = IASNtdsQueryUserAttributes(
                     a3,
                     a4,
                     2u,
                     (unsigned __int16 **)&off_180031370,
                     (struct _IAS_NTDS_RESULT *)res);
  RasUser0 = UserAttributes;
  if ( UserAttributes )
  {
    if ( UserAttributes == 8200 )
    {
      hMem = 0;
      RasUser0 = IASGetUserParameters(a4, a3, &hMem);
      if ( !RasUser0 )
      {
        RasUser0 = IASParmsQueryRasUser0(hMem, v30);
        LocalFree(hMem);
      }
    }
  }
  else
  {
    v10 = ldap_conn_from_msg(0, res[1]);
    entry = ldap_first_entry(v10, res[1]);
    v12 = entry;
    if ( entry )
    {
      dnW = ldap_get_dnW(v10, entry);
      IASStoreFQUserName(*(struct IAttributesRaw **)(a2 + 8), DS_FQDN_1779_NAME, dnW);
      ldap_memfreeW(dnW);
      valuesW = ldap_get_valuesW(v10, v12, L"userParameters");
      v15 = valuesW;
      if ( valuesW )
        v16 = *valuesW;
      else
        v16 = 0;
      RasUser0 = IASParmsQueryRasUser0(v16, v30);
      ldap_value_freeW(v15);
    }
    else
    {
      RasUser0 = 1317;
    }
  }
  if ( RasUser0 )
  {
    v17 = IASFormatSysErr(RasUser0, Buffer);
    if ( v17 >= 0x100 )
      _report_rangecheckfailure(v18);
    Buffer[v17] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"Per-user attribute retrieval failed", (__int64)Buffer);
    }
    v19 = IASMapWin32Error(RasUser0, 6);
    v20 = IASProcessFailure(*(_QWORD *)a2, v19);
    IASNtdsFreeResult(res);
    return v20;
  }
  else
  {
    v27 = 0;
    if ( (v30[0] & 8) != 0 )
      v22 = (_DWORD *)a1[1];
    else
      v22 = (_DWORD *)a1[2];
    v28 = v22;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Inserting attribute msNPAllowDialin.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids, "NPSSVC");
    }
    OverwriteAttribute(
      *(struct IAttributesRaw **)(a2 + 8),
      (struct _ATTRIBUTEPOSITION *)&v27,
      (struct _ATTRIBUTEPOSITION *)res);
    v24 = v30[0];
    if ( (v30[0] & 7) != 1 )
    {
      v28 = (_DWORD *)a1[3];
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Inserting attribute msRADIUSServiceType.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids, "NPSSVC");
      }
      OverwriteAttribute(
        *(struct IAttributesRaw **)(a2 + 8),
        (struct _ATTRIBUTEPOSITION *)&v27,
        (struct _ATTRIBUTEPOSITION *)res);
      v24 = v30[0];
    }
    if ( (v24 & 2) != 0 )
    {
      IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&hMem, v23);
      v25 = hMem;
      *((_DWORD *)hMem + 2) = 19;
      IASTL::IASAttribute::setOctetString((IASTL::IASAttribute *)&hMem, WideCharStr);
      v25[1] |= 1u;
      v28 = v25;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Inserting attribute msRADIUSCallbackNumber.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids, "NPSSVC");
      }
      OverwriteAttribute(
        *(struct IAttributesRaw **)(a2 + 8),
        (struct _ATTRIBUTEPOSITION *)&v27,
        (struct _ATTRIBUTEPOSITION *)res);
      IASAttributeRelease(v25);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Successfully retrieved per-user attributes.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids, "NPSSVC");
    }
    IASNtdsFreeResult(res);
    return 2;
  }
}

```

## disassembly

```asm
0x180024890  mov     [rsp-8+arg_0], rbx
0x180024895  push    rbp
0x180024896  push    rsi
0x180024897  push    rdi
0x180024898  push    r14
0x18002489a  push    r15
0x18002489c  lea     rbp, [rsp-180h]
0x1800248a4  sub     rsp, 280h
0x1800248ab  mov     rax, cs:__security_cookie
0x1800248b2  xor     rax, rsp
0x1800248b5  mov     [rbp+1A0h+var_30], rax
0x1800248bc  mov     r15, r9
0x1800248bf  mov     rdi, r8
0x1800248c2  mov     rsi, rdx
0x1800248c5  mov     r14, rcx
0x1800248c8  lea     rcx, WPP_GLOBAL_Control
0x1800248cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800248d6  cmp     rax, rcx
0x1800248d9  jz      short loc_180024916
0x1800248db  cmp     byte ptr [rax+19h], 4
0x1800248df  jb      short loc_180024916
0x1800248e1  test    byte ptr [rax+1Ch], 4
0x1800248e5  jz      short loc_180024916
0x1800248e7  lea     rcx, aUsingDownlevel_0; "Using downlevel dial-in parameters."
0x1800248ee  call    WppDbgPrint
0x1800248f3  mov     edx, 0Ah
0x1800248f8  lea     r9, aNpssvc; "NPSSVC"
0x1800248ff  lea     r8, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids
0x180024906  mov     rcx, cs:WPP_GLOBAL_Control
0x18002490d  mov     rcx, [rcx+10h]
0x180024911  call    WPP_SF_s
0x180024916  xor     edx, edx; Val
0x180024918  mov     r8d, 104h; Size
0x18002491e  lea     rcx, [rsp+2A0h+var_240]; void *
0x180024923  call    memset_0
0x180024928  xorps   xmm0, xmm0
0x18002492b  movdqu  xmmword ptr [rsp+2A0h+res], xmm0
0x180024931  lea     rax, [rsp+2A0h+res]
0x180024936  mov     [rsp+2A0h+var_280], rax; struct _IAS_NTDS_RESULT *
0x18002493b  lea     r9, off_180031370; unsigned __int16 **
0x180024942  mov     r8d, 2; unsigned int
0x180024948  mov     rdx, r15; unsigned __int16 *
0x18002494b  mov     rcx, rdi; unsigned __int16 *
0x18002494e  call    IASNtdsQueryUserAttributes
0x180024953  mov     ebx, eax
0x180024955  test    eax, eax
0x180024957  jnz     loc_1800249EC
0x18002495d  mov     rdx, [rsp+2A0h+res+8]; res
0x180024962  xor     ecx, ecx; PrimaryConn
0x180024964  call    cs:__imp_ldap_conn_from_msg
0x18002496a  mov     rdi, rax
0x18002496d  mov     rdx, [rsp+2A0h+res+8]; res
0x180024972  mov     rcx, rax; ld
0x180024975  call    cs:__imp_ldap_first_entry
0x18002497b  mov     r15, rax
0x18002497e  test    rax, rax
0x180024981  jz      short loc_1800249E5
0x180024983  mov     rdx, rax; entry
0x180024986  mov     rcx, rdi; ld
0x180024989  call    cs:__imp_ldap_get_dnW
0x18002498f  mov     rbx, rax
0x180024992  mov     r8, rax; unsigned __int16 *
0x180024995  mov     edx, 1; enum DS_NAME_FORMAT
0x18002499a  mov     rcx, [rsi+8]; struct IAttributesRaw *
0x18002499e  call    ?IASStoreFQUserName@@YAJPEAUIAttributesRaw@@W4DS_NAME_FORMAT@@PEBG@Z; IASStoreFQUserName(IAttributesRaw *,DS_NAME_FORMAT,ushort const *)
0x1800249a3  mov     rcx, rbx; Block
0x1800249a6  call    cs:__imp_ldap_memfreeW
0x1800249ac  mov     r8, cs:off_180031370; attr
0x1800249b3  mov     rdx, r15; entry
0x1800249b6  mov     rcx, rdi; ld
0x1800249b9  call    cs:__imp_ldap_get_valuesW
0x1800249bf  mov     rdi, rax
0x1800249c2  test    rax, rax
0x1800249c5  jz      short loc_1800249CC
0x1800249c7  mov     rcx, [rax]
0x1800249ca  jmp     short loc_1800249CE
0x1800249cc  xor     ecx, ecx
0x1800249ce  lea     rdx, [rsp+2A0h+var_240]
0x1800249d3  call    IASParmsQueryRasUser0
0x1800249d8  mov     ebx, eax
0x1800249da  mov     rcx, rdi; vals
0x1800249dd  call    cs:__imp_ldap_value_freeW
0x1800249e3  jmp     short loc_180024A2E
0x1800249e5  mov     ebx, 525h
0x1800249ea  jmp     short loc_180024A2E
0x1800249ec  cmp     eax, 2008h
0x1800249f1  jnz     short loc_180024A2E
0x1800249f3  mov     [rsp+2A0h+hMem], 0
0x1800249fc  lea     r8, [rsp+2A0h+hMem]
0x180024a01  mov     rdx, rdi
0x180024a04  mov     rcx, r15
0x180024a07  call    IASGetUserParameters
0x180024a0c  mov     ebx, eax
0x180024a0e  test    eax, eax
0x180024a10  jnz     short loc_180024A2E
0x180024a12  lea     rdx, [rsp+2A0h+var_240]
0x180024a17  mov     rcx, [rsp+2A0h+hMem]
0x180024a1c  call    IASParmsQueryRasUser0
0x180024a21  mov     ebx, eax
0x180024a23  mov     rcx, [rsp+2A0h+hMem]; hMem
0x180024a28  call    cs:__imp_LocalFree
0x180024a2e  test    ebx, ebx
0x180024a30  jz      loc_180024AEC
0x180024a36  lea     rdx, [rbp+1A0h+Buffer]; Buffer
0x180024a3a  mov     ecx, ebx; dwMessageId
0x180024a3c  call    IASFormatSysErr
0x180024a41  cmp     eax, 100h
0x180024a46  jnb     loc_180024AE6
0x180024a4c  mov     eax, eax
0x180024a4e  mov     [rbp+rax+1A0h+Buffer], 0
0x180024a53  mov     rax, cs:WPP_GLOBAL_Control
0x180024a5a  lea     rcx, WPP_GLOBAL_Control
0x180024a61  cmp     rax, rcx
0x180024a64  jz      short loc_180024ABD
0x180024a66  cmp     byte ptr [rax+19h], 2
0x180024a6a  jb      short loc_180024ABD
0x180024a6c  test    byte ptr [rax+1Ch], 4
0x180024a70  jz      short loc_180024ABD
0x180024a72  lea     r9, [rbp+1A0h+Buffer]
0x180024a76  lea     rdi, aPerUserAttribu; "Per-user attribute retrieval failed"
0x180024a7d  mov     r8, rdi
0x180024a80  lea     rdx, aNpssvc; "NPSSVC"
0x180024a87  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180024a8e  call    WppDbgPrint
0x180024a93  mov     edx, 0Bh
0x180024a98  lea     rax, [rbp+1A0h+Buffer]
0x180024a9c  mov     [rsp+2A0h+var_278], rax; __int64
0x180024aa1  mov     [rsp+2A0h+var_280], rdi; __int64
0x180024aa6  lea     r8, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids
0x180024aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ab4  mov     rcx, [rcx+10h]; LoggerHandle
0x180024ab8  call    WPP_SF_sss
0x180024abd  mov     edx, 6
0x180024ac2  mov     ecx, ebx
0x180024ac4  call    IASMapWin32Error
0x180024ac9  mov     edx, eax
0x180024acb  mov     rcx, [rsi]
0x180024ace  call    ?IASProcessFailure@@YA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@J@Z; IASProcessFailure(IRequest *,long)
0x180024ad3  mov     ebx, eax
0x180024ad5  lea     rcx, [rsp+2A0h+res]
0x180024ada  call    IASNtdsFreeResult
0x180024adf  mov     eax, ebx
0x180024ae1  jmp     loc_180024CD1
0x180024ae6  call    __report_rangecheckfailure
0x180024aec  mov     [rsp+2A0h+var_268], 0
0x180024af5  test    [rsp+2A0h+var_240], 8
0x180024afa  jnz     short loc_180024B02
0x180024afc  mov     rax, [r14+10h]
0x180024b00  jmp     short loc_180024B06
0x180024b02  mov     rax, [r14+8]
0x180024b06  mov     [rsp+2A0h+var_260], rax
0x180024b0b  mov     rax, cs:WPP_GLOBAL_Control
0x180024b12  lea     rdi, WPP_GLOBAL_Control
0x180024b19  cmp     rax, rdi
0x180024b1c  jz      short loc_180024B59
0x180024b1e  cmp     byte ptr [rax+19h], 4
0x180024b22  jb      short loc_180024B59
0x180024b24  test    byte ptr [rax+1Ch], 4
0x180024b28  jz      short loc_180024B59
0x180024b2a  lea     rcx, aInsertingAttri_2; "Inserting attribute msNPAllowDialin."
0x180024b31  call    WppDbgPrint
0x180024b36  mov     edx, 0Ch
0x180024b3b  lea     r9, aNpssvc; "NPSSVC"
0x180024b42  lea     r8, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids
0x180024b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b50  mov     rcx, [rcx+10h]
0x180024b54  call    WPP_SF_s
0x180024b59  lea     r8, [rsp+2A0h+res]; struct _ATTRIBUTEPOSITION *
0x180024b5e  lea     rdx, [rsp+2A0h+var_268]; struct _ATTRIBUTEPOSITION *
0x180024b63  mov     rcx, [rsi+8]; struct IAttributesRaw *
0x180024b67  call    ?OverwriteAttribute@@YAXPEAUIAttributesRaw@@PEAU_ATTRIBUTEPOSITION@@1@Z; OverwriteAttribute(IAttributesRaw *,_ATTRIBUTEPOSITION *,_ATTRIBUTEPOSITION *)
0x180024b6c  mov     cl, [rsp+2A0h+var_240]
0x180024b70  mov     al, cl
0x180024b72  and     al, 7
0x180024b74  cmp     al, 1
0x180024b76  jz      short loc_180024BDF
0x180024b78  mov     rax, [r14+18h]
0x180024b7c  mov     [rsp+2A0h+var_260], rax
0x180024b81  mov     rax, cs:WPP_GLOBAL_Control
0x180024b88  cmp     rax, rdi
0x180024b8b  jz      short loc_180024BC8
0x180024b8d  cmp     byte ptr [rax+19h], 4
0x180024b91  jb      short loc_180024BC8
0x180024b93  test    byte ptr [rax+1Ch], 4
0x180024b97  jz      short loc_180024BC8
0x180024b99  lea     rcx, aInsertingAttri_3; "Inserting attribute msRADIUSServiceType"...
0x180024ba0  call    WppDbgPrint
0x180024ba5  mov     edx, 0Dh
0x180024baa  lea     r9, aNpssvc; "NPSSVC"
0x180024bb1  lea     r8, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids
0x180024bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bbf  mov     rcx, [rcx+10h]
0x180024bc3  call    WPP_SF_s
0x180024bc8  lea     r8, [rsp+2A0h+res]; struct _ATTRIBUTEPOSITION *
0x180024bcd  lea     rdx, [rsp+2A0h+var_268]; struct _ATTRIBUTEPOSITION *
0x180024bd2  mov     rcx, [rsi+8]; struct IAttributesRaw *
0x180024bd6  call    ?OverwriteAttribute@@YAXPEAUIAttributesRaw@@PEAU_ATTRIBUTEPOSITION@@1@Z; OverwriteAttribute(IAttributesRaw *,_ATTRIBUTEPOSITION *,_ATTRIBUTEPOSITION *)
0x180024bdb  mov     cl, [rsp+2A0h+var_240]
0x180024bdf  test    cl, 2
0x180024be2  jz      loc_180024C7A
0x180024be8  lea     rcx, [rsp+2A0h+hMem]; this
0x180024bed  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180024bf2  nop
0x180024bf3  mov     rbx, [rsp+2A0h+hMem]
0x180024bf8  mov     dword ptr [rbx+8], 13h
0x180024bff  lea     rdx, [rsp+2A0h+WideCharStr]; lpWideCharStr
0x180024c04  lea     rcx, [rsp+2A0h+hMem]; this
0x180024c09  call    ?setOctetString@IASAttribute@IASTL@@QEAAXPEBG@Z; IASTL::IASAttribute::setOctetString(ushort const *)
0x180024c0e  or      dword ptr [rbx+4], 1
0x180024c12  mov     [rsp+2A0h+var_260], rbx
0x180024c17  mov     rax, cs:WPP_GLOBAL_Control
0x180024c1e  cmp     rax, rdi
0x180024c21  jz      short loc_180024C5E
0x180024c23  cmp     byte ptr [rax+19h], 4
0x180024c27  jb      short loc_180024C5E
0x180024c29  test    byte ptr [rax+1Ch], 4
0x180024c2d  jz      short loc_180024C5E
0x180024c2f  lea     rcx, aInsertingAttri_0; "Inserting attribute msRADIUSCallbackNum"...
0x180024c36  call    WppDbgPrint
0x180024c3b  mov     edx, 0Eh
0x180024c40  lea     r9, aNpssvc; "NPSSVC"
0x180024c47  lea     r8, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids
0x180024c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c55  mov     rcx, [rcx+10h]
0x180024c59  call    WPP_SF_s
0x180024c5e  lea     r8, [rsp+2A0h+res]; struct _ATTRIBUTEPOSITION *
0x180024c63  lea     rdx, [rsp+2A0h+var_268]; struct _ATTRIBUTEPOSITION *
0x180024c68  mov     rcx, [rsi+8]; struct IAttributesRaw *
0x180024c6c  call    ?OverwriteAttribute@@YAXPEAUIAttributesRaw@@PEAU_ATTRIBUTEPOSITION@@1@Z; OverwriteAttribute(IAttributesRaw *,_ATTRIBUTEPOSITION *,_ATTRIBUTEPOSITION *)
0x180024c71  nop
0x180024c72  mov     rcx, rbx; pv
0x180024c75  call    IASAttributeRelease
0x180024c7a  mov     rax, cs:WPP_GLOBAL_Control
0x180024c81  cmp     rax, rdi
0x180024c84  jz      short loc_180024CC2
0x180024c86  cmp     byte ptr [rax+19h], 4
0x180024c8a  jb      short loc_180024CC2
0x180024c8c  test    byte ptr [rax+1Ch], 4
0x180024c90  jz      short loc_180024CC2
0x180024c92  lea     rcx, aSuccessfullyRe; "Successfully retrieved per-user attribu"...
0x180024c99  call    WppDbgPrint
0x180024c9e  mov     edx, 0Fh
0x180024ca3  lea     r9, aNpssvc; "NPSSVC"
0x180024caa  lea     r8, WPP_7305a1fdd0c5332a5382b9563da23d62_Traceguids
0x180024cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cb8  mov     rcx, [rcx+10h]
0x180024cbc  call    WPP_SF_s
0x180024cc1  nop
0x180024cc2  lea     rcx, [rsp+2A0h+res]
0x180024cc7  call    IASNtdsFreeResult
0x180024ccc  mov     eax, 2
0x180024cd1  mov     rcx, [rbp+1A0h+var_30]
0x180024cd8  xor     rcx, rsp; StackCookie
0x180024cdb  call    __security_check_cookie
0x180024ce0  mov     rbx, [rsp+2A0h+arg_0]
0x180024ce8  add     rsp, 280h
0x180024cef  pop     r15
0x180024cf1  pop     r14
0x180024cf3  pop     rdi
0x180024cf4  pop     rsi
0x180024cf5  pop     rbp
0x180024cf6  retn
```
