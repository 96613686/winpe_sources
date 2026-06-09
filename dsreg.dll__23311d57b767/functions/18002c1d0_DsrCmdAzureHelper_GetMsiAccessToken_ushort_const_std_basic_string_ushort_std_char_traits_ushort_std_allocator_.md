# DsrCmdAzureHelper::GetMsiAccessToken(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x18002c1d0`
- end: `0x18002c88d`
- name: `?GetMsiAccessToken@DsrCmdAzureHelper@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `1725`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update`

## callers

- `0x180099424`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x180012c7c`
- `0x18001378c`
- `0x18001dfcc`
- `0x180028440`
- `0x180029250`
- `0x18002927c`
- `0x18002999c`
- `0x18002b9b4`
- `0x18002c1d0`
- `0x18002dd24`
- `0x18002dda0`
- `0x18002dde4`
- `0x1800319ac`
- `0x180039290`
- `0x180039c74`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800a0e10`
- `0x1800a13f0`

## string_xrefs

- `0x18002c222`: `AzureVmMsiTokenEndpoint`
- `0x18002c244`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c281`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c2c9`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c303`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c31d`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c36a`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c3a4`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c3be`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c54c`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c589`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c5aa`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c5de`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c61f`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c63e`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c66f`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c6bd`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c6e8`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c74b`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c788`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c7db`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c818`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c83c`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18002c2d0`: `%s: MSI token endpoint from registry is null or empty.\n`
- `0x18002c30a`: `%s: MSI token endpoint from registry is null or empty.\n`
- `0x18002c324`: `%s: MSI token endpoint from registry is null or empty.\n`
- `0x18002c371`: `%s: Token endpoint from registry is invalid.\n`
- `0x18002c3ab`: `%s: Token endpoint from registry is invalid.\n`
- `0x18002c3c5`: `%s: Token endpoint from registry is invalid.\n`
- `0x18002c24b`: `%s: Getting MSI token endpoint from registry failed . Error code: 0x%08x%.\n`
- `0x18002c288`: `%s: Getting MSI token endpoint from registry failed . Error code: 0x%08x%.\n`
- `0x18002c29b`: `%s: Getting MSI token endpoint from registry failed . Error code: 0x%08x%.\n`
- `0x18002c553`: `%s: Getting Msi Access Token for ADRS failed. Error code: 0x%08x%.\n`
- `0x18002c590`: `%s: Getting Msi Access Token for ADRS failed. Error code: 0x%08x%.\n`
- `0x18002c5a3`: `%s: Getting Msi Access Token for ADRS failed. Error code: 0x%08x%.\n`
- `0x18002c752`: `%s: Failed to deserialize Msi json response. Error code: 0x%08x%.\n`
- `0x18002c78f`: `%s: Failed to deserialize Msi json response. Error code: 0x%08x%.\n`
- `0x18002c7a2`: `%s: Failed to deserialize Msi json response. Error code: 0x%08x%.\n`
- `0x18002c7b1`: `access_token`
- `0x18002c5e5`: `%s: Unable to get access token for ADRS, status code %d\n`
- `0x18002c626`: `%s: Unable to get access token for ADRS, status code %d\n`
- `0x18002c645`: `%s: Unable to get access token for ADRS, status code %d\n`
- `0x18002c7e2`: `%s: Failed to extract access_token property. Error code: 0x%08x%.\n`
- `0x18002c81f`: `%s: Failed to extract access_token property. Error code: 0x%08x%.\n`
- `0x18002c832`: `%s: Failed to extract access_token property. Error code: 0x%08x%.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DsrCmdAzureHelper::GetMsiAccessToken(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int MetadataRestResponse; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int16 *v15; // rbx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  _BYTE *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  _QWORD *v44; // rax
  __int64 v45; // rdx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rdx
  _QWORD *v53; // rax
  __int64 v54; // rdx
  unsigned int v55; // ebx
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 *v59; // r8
  __int64 v60; // rdx
  __int64 v61; // rcx
  _QWORD *v62; // rax
  __int64 v63; // rdx
  _QWORD *v64; // rax
  __int64 v65; // rdx
  __int64 *v66; // rbx
  __int64 v67; // rax
  __int64 *v68; // r8
  unsigned __int16 *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // rcx
  _QWORD *v74; // rax
  __int64 v75; // rdx
  _QWORD *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rdx
  _QWORD *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rax
  unsigned int v89; // [rsp+30h] [rbp-138h] BYREF
  unsigned __int16 *v90; // [rsp+38h] [rbp-130h] BYREF
  __int64 v91[3]; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int64 v92; // [rsp+58h] [rbp-110h]
  char *Src[4]; // [rsp+60h] [rbp-108h] BYREF
  _BYTE v94[32]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v95[32]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v96[32]; // [rsp+C0h] [rbp-A8h] BYREF
  _BYTE v97[80]; // [rsp+E0h] [rbp-88h] BYREF

  std::wstring::wstring((__int64)v91);
  v89 = 0;
  v90 = 0;
  std::wstring::wstring((__int64)Src);
  MetadataRestResponse = ReadStringOption(L"AzureVmMsiTokenEndpoint", &v90);
  if ( (MetadataRestResponse & 0x80000000) == 0 )
  {
    v15 = v90;
    if ( (unsigned int)IsEmptyString(v90) )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v17, v16) )
      {
        wprintf(L"%s: MSI token endpoint from registry is null or empty.\n", L"DsrCmdAzureHelper::GetMsiAccessToken");
        CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v19, v18);
        if ( *(_BYTE *)(*CurrentRef + 12LL) )
        {
          v22 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v21);
          if ( *(_QWORD *)(*v22 + 184LL) )
          {
            v24 = CmdOptions::GetCurrentRef(*v22, v23);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v24 + 184LL),
              L"%s: MSI token endpoint from registry is null or empty.\n",
              L"DsrCmdAzureHelper::GetMsiAccessToken");
          }
        }
      }
      Logger::TraceError(
        L"%s: MSI token endpoint from registry is null or empty.\n",
        L"DsrCmdAzureHelper::GetMsiAccessToken");
      SafeFree(v15);
      MetadataRestResponse = -2145648515;
    }
    else if ( !a3 || DsrCmdAzureHelper::ValidateEndpoint(v17, 2u) )
    {
      try
      {
        v34 = -1;
        do
          ++v34;
        while ( v15[v34] );
        std::wstring::_Assign<unsigned short>(Src, v15, (char *)v34);
      }
      catch ( ... )
      {
        SafeFree(v90);
        throw;
      }
      SafeFree(v15);
      if ( a3 )
      {
        v35 = std::wstring::wstring((__int64)v94, a1);
        v36 = std::operator+<unsigned short>(v96, L"?resource=", v35);
        std::operator+<unsigned short>(v95, v36, L"&api-version=2020-06-01");
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Tidy_deallocate((__int64)v95);
        std::wstring::_Tidy_deallocate((__int64)v96);
        v37 = v94;
      }
      else
      {
        v38 = std::wstring::wstring((__int64)v95, a1);
        v39 = std::operator+<unsigned short>(v96, L"?resource=", v38);
        std::operator+<unsigned short>(v94, v39, L"&api-version=2018-02-01");
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Tidy_deallocate((__int64)v94);
        std::wstring::_Tidy_deallocate((__int64)v96);
        v37 = v95;
      }
      std::wstring::_Tidy_deallocate((__int64)v37);
      MetadataRestResponse = DsrCmdAzureHelper::GetMetadataRestResponse((LPCWSTR)Src, &v89, v91, a3, 1);
      if ( (MetadataRestResponse & 0x80000000) == 0 )
      {
        if ( v89 == 200 )
        {
          dsreg::CJsonValue::CJsonValue((dsreg::CJsonValue *)v97);
          v69 = (unsigned __int16 *)std::wstring::wstring(v94, v91);
          MetadataRestResponse = DsrCmdAzureHelper::GetJsonValue(v69, (struct dsreg::CJsonValue *)v97);
          if ( (MetadataRestResponse & 0x80000000) == 0 )
          {
            MetadataRestResponse = DsrCmdAzureHelper::GetStringValueFromProperty(
                                     (struct dsreg::CJsonValue *)v97,
                                     L"access_token");
            if ( (MetadataRestResponse & 0x80000000) != 0 )
            {
              if ( **(_BYTE **)CmdOptions::GetCurrentRef(v80, v79) )
              {
                wprintf(
                  L"%s: Failed to extract access_token property. Error code: 0x%08x%.\n",
                  L"DsrCmdAzureHelper::GetMsiAccessToken",
                  MetadataRestResponse);
                v83 = (_QWORD *)CmdOptions::GetCurrentRef(v82, v81);
                if ( *(_BYTE *)(*v83 + 12LL) )
                {
                  v85 = (_QWORD *)CmdOptions::GetCurrentRef(*v83, v84);
                  if ( *(_QWORD *)(*v85 + 184LL) )
                  {
                    v87 = CmdOptions::GetCurrentRef(*v85, v86);
                    fwprintf_s(
                      *(FILE *const *)(*(_QWORD *)v87 + 184LL),
                      L"%s: Failed to extract access_token property. Error code: 0x%08x%.\n",
                      L"DsrCmdAzureHelper::GetMsiAccessToken",
                      MetadataRestResponse);
                  }
                }
              }
              Logger::TraceError(
                L"%s: Failed to extract access_token property. Error code: 0x%08x%.\n",
                L"DsrCmdAzureHelper::GetMsiAccessToken",
                MetadataRestResponse);
            }
          }
          else
          {
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v71, v70) )
            {
              wprintf(
                L"%s: Failed to deserialize Msi json response. Error code: 0x%08x%.\n",
                L"DsrCmdAzureHelper::GetMsiAccessToken",
                MetadataRestResponse);
              v74 = (_QWORD *)CmdOptions::GetCurrentRef(v73, v72);
              if ( *(_BYTE *)(*v74 + 12LL) )
              {
                v76 = (_QWORD *)CmdOptions::GetCurrentRef(*v74, v75);
                if ( *(_QWORD *)(*v76 + 184LL) )
                {
                  v78 = CmdOptions::GetCurrentRef(*v76, v77);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v78 + 184LL),
                    L"%s: Failed to deserialize Msi json response. Error code: 0x%08x%.\n",
                    L"DsrCmdAzureHelper::GetMsiAccessToken",
                    MetadataRestResponse);
                }
              }
            }
            Logger::TraceError(
              L"%s: Failed to deserialize Msi json response. Error code: 0x%08x%.\n",
              L"DsrCmdAzureHelper::GetMsiAccessToken",
              MetadataRestResponse);
          }
          dsreg::CJsonValue::~CJsonValue((dsreg::CJsonValue *)v97, v79);
        }
        else
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v41, v40) )
          {
            wprintf(
              L"%s: Unable to get access token for ADRS, status code %d\n",
              L"DsrCmdAzureHelper::GetMsiAccessToken",
              v89);
            v51 = (_QWORD *)CmdOptions::GetCurrentRef(v50, v49);
            if ( *(_BYTE *)(*v51 + 12LL) )
            {
              v53 = (_QWORD *)CmdOptions::GetCurrentRef(*v51, v52);
              if ( *(_QWORD *)(*v53 + 184LL) )
              {
                v55 = v89;
                v56 = CmdOptions::GetCurrentRef(*v53, v54);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v56 + 184LL),
                  L"%s: Unable to get access token for ADRS, status code %d\n",
                  L"DsrCmdAzureHelper::GetMsiAccessToken",
                  v55);
              }
            }
          }
          Logger::TraceError(
            L"%s: Unable to get access token for ADRS, status code %d\n",
            L"DsrCmdAzureHelper::GetMsiAccessToken",
            v89);
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v58, v57) )
          {
            v59 = v91;
            if ( v92 > 7 )
              v59 = (__int64 *)v91[0];
            wprintf(L"%s: %s\n", L"DsrCmdAzureHelper::GetMsiAccessToken", v59);
            v62 = (_QWORD *)CmdOptions::GetCurrentRef(v61, v60);
            if ( *(_BYTE *)(*v62 + 12LL) )
            {
              v64 = (_QWORD *)CmdOptions::GetCurrentRef(*v62, v63);
              if ( *(_QWORD *)(*v64 + 184LL) )
              {
                v66 = v91;
                if ( v92 > 7 )
                  v66 = (__int64 *)v91[0];
                v67 = CmdOptions::GetCurrentRef(*v64, v65);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v67 + 184LL),
                  L"%s: %s\n",
                  L"DsrCmdAzureHelper::GetMsiAccessToken",
                  v66);
              }
            }
          }
          v68 = v91;
          if ( v92 > 7 )
            v68 = (__int64 *)v91[0];
          Logger::TraceError(L"%s: %s\n", L"DsrCmdAzureHelper::GetMsiAccessToken", v68);
          MetadataRestResponse = -2145648575;
        }
      }
      else
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v41, v40) )
        {
          wprintf(
            L"%s: Getting Msi Access Token for ADRS failed. Error code: 0x%08x%.\n",
            L"DsrCmdAzureHelper::GetMsiAccessToken",
            MetadataRestResponse);
          v44 = (_QWORD *)CmdOptions::GetCurrentRef(v43, v42);
          if ( *(_BYTE *)(*v44 + 12LL) )
          {
            v46 = (_QWORD *)CmdOptions::GetCurrentRef(*v44, v45);
            if ( *(_QWORD *)(*v46 + 184LL) )
            {
              v48 = CmdOptions::GetCurrentRef(*v46, v47);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v48 + 184LL),
                L"%s: Getting Msi Access Token for ADRS failed. Error code: 0x%08x%.\n",
                L"DsrCmdAzureHelper::GetMsiAccessToken",
                MetadataRestResponse);
            }
          }
        }
        Logger::TraceError(
          L"%s: Getting Msi Access Token for ADRS failed. Error code: 0x%08x%.\n",
          L"DsrCmdAzureHelper::GetMsiAccessToken",
          MetadataRestResponse);
      }
    }
    else
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v26, v25) )
      {
        wprintf(L"%s: Token endpoint from registry is invalid.\n", L"DsrCmdAzureHelper::GetMsiAccessToken");
        v29 = (_QWORD *)CmdOptions::GetCurrentRef(v28, v27);
        if ( *(_BYTE *)(*v29 + 12LL) )
        {
          v31 = (_QWORD *)CmdOptions::GetCurrentRef(*v29, v30);
          if ( *(_QWORD *)(*v31 + 184LL) )
          {
            v33 = CmdOptions::GetCurrentRef(*v31, v32);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v33 + 184LL),
              L"%s: Token endpoint from registry is invalid.\n",
              L"DsrCmdAzureHelper::GetMsiAccessToken");
          }
        }
      }
      Logger::TraceError(L"%s: Token endpoint from registry is invalid.\n", L"DsrCmdAzureHelper::GetMsiAccessToken");
      SafeFree(v15);
      MetadataRestResponse = -2145648495;
    }
  }
  else
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v6, v5) )
    {
      wprintf(
        L"%s: Getting MSI token endpoint from registry failed . Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetMsiAccessToken",
        MetadataRestResponse);
      v10 = (_QWORD *)CmdOptions::GetCurrentRef(v9, v8);
      if ( *(_BYTE *)(*v10 + 12LL) )
      {
        v12 = (_QWORD *)CmdOptions::GetCurrentRef(*v10, v11);
        if ( *(_QWORD *)(*v12 + 184LL) )
        {
          v14 = CmdOptions::GetCurrentRef(*v12, v13);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v14 + 184LL),
            L"%s: Getting MSI token endpoint from registry failed . Error code: 0x%08x%.\n",
            L"DsrCmdAzureHelper::GetMsiAccessToken",
            MetadataRestResponse);
        }
      }
    }
    Logger::TraceError(
      L"%s: Getting MSI token endpoint from registry failed . Error code: 0x%08x%.\n",
      L"DsrCmdAzureHelper::GetMsiAccessToken",
      MetadataRestResponse);
  }
  std::wstring::_Tidy_deallocate((__int64)Src);
  std::wstring::_Tidy_deallocate((__int64)v91);
  return MetadataRestResponse;
}

```

## disassembly

```asm
0x18002c1d0  push    rbx
0x18002c1d2  push    rsi
0x18002c1d3  push    rdi
0x18002c1d4  push    r14
0x18002c1d6  push    r15
0x18002c1d8  sub     rsp, 140h
0x18002c1df  mov     rax, cs:__security_cookie
0x18002c1e6  xor     rax, rsp
0x18002c1e9  mov     [rsp+168h+var_38], rax
0x18002c1f1  mov     dil, r8b
0x18002c1f4  mov     r14, rdx
0x18002c1f7  mov     rsi, rcx
0x18002c1fa  lea     rcx, [rsp+168h+var_128]
0x18002c1ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002c204  nop
0x18002c205  xor     r15d, r15d
0x18002c208  mov     [rsp+168h+var_138], r15d
0x18002c20d  mov     [rsp+168h+var_130], r15
0x18002c212  lea     rcx, [rsp+168h+Src]
0x18002c217  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002c21c  nop
0x18002c21d  lea     rdx, [rsp+168h+var_130]; unsigned __int16 **
0x18002c222  lea     rcx, aAzurevmmsitoke; "AzureVmMsiTokenEndpoint"
0x18002c229  call    ?ReadStringOption@@YAJPEBGPEAPEAG@Z; ReadStringOption(ushort const *,ushort * *)
0x18002c22e  mov     ebx, eax
0x18002c230  test    eax, eax
0x18002c232  jns     short loc_18002C2A7
0x18002c234  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c239  mov     rcx, [rax]
0x18002c23c  cmp     [rcx], r15b
0x18002c23f  jz      short loc_18002C29B
0x18002c241  mov     r8d, ebx
0x18002c244  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c24b  lea     rcx, aSGettingMsiTok; "%s: Getting MSI token endpoint from reg"...
0x18002c252  call    wprintf
0x18002c257  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c25c  mov     rcx, [rax]
0x18002c25f  cmp     [rcx+0Ch], r15b
0x18002c263  jz      short loc_18002C29B
0x18002c265  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c26a  mov     rcx, [rax]
0x18002c26d  cmp     [rcx+0B8h], r15
0x18002c274  jz      short loc_18002C29B
0x18002c276  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c27b  mov     rcx, [rax]
0x18002c27e  mov     r9d, ebx
0x18002c281  lea     r8, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c288  lea     rdx, aSGettingMsiTok; "%s: Getting MSI token endpoint from reg"...
0x18002c28f  mov     rcx, [rcx+0B8h]; Stream
0x18002c296  call    fwprintf_s
0x18002c29b  lea     rcx, aSGettingMsiTok; "%s: Getting MSI token endpoint from reg"...
0x18002c2a2  jmp     loc_18002C5AA
0x18002c2a7  mov     rbx, [rsp+168h+var_130]
0x18002c2ac  mov     rcx, rbx; unsigned __int16 *
0x18002c2af  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18002c2b4  test    eax, eax
0x18002c2b6  jz      loc_18002C342
0x18002c2bc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c2c1  mov     rcx, [rax]
0x18002c2c4  cmp     [rcx], r15b
0x18002c2c7  jz      short loc_18002C31D
0x18002c2c9  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c2d0  lea     rcx, aSMsiTokenEndpo; "%s: MSI token endpoint from registry is"...
0x18002c2d7  call    wprintf
0x18002c2dc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c2e1  mov     rcx, [rax]
0x18002c2e4  cmp     [rcx+0Ch], r15b
0x18002c2e8  jz      short loc_18002C31D
0x18002c2ea  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c2ef  mov     rcx, [rax]
0x18002c2f2  cmp     [rcx+0B8h], r15
0x18002c2f9  jz      short loc_18002C31D
0x18002c2fb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c300  mov     rcx, [rax]
0x18002c303  lea     r8, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c30a  lea     rdx, aSMsiTokenEndpo; "%s: MSI token endpoint from registry is"...
0x18002c311  mov     rcx, [rcx+0B8h]; Stream
0x18002c318  call    fwprintf_s
0x18002c31d  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c324  lea     rcx, aSMsiTokenEndpo; "%s: MSI token endpoint from registry is"...
0x18002c32b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c330  mov     rcx, rbx; lpMem
0x18002c333  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002c338  mov     ebx, 801C007Dh
0x18002c33d  jmp     loc_18002C857
0x18002c342  test    dil, dil
0x18002c345  jz      loc_18002C3E3
0x18002c34b  mov     edx, 2; unsigned int
0x18002c350  call    ?ValidateEndpoint@DsrCmdAzureHelper@@CA_NPEAGK@Z; DsrCmdAzureHelper::ValidateEndpoint(ushort *,ulong)
0x18002c355  test    al, al
0x18002c357  jnz     loc_18002C3E3
0x18002c35d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c362  mov     rcx, [rax]
0x18002c365  cmp     [rcx], r15b
0x18002c368  jz      short loc_18002C3BE
0x18002c36a  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c371  lea     rcx, aSTokenEndpoint; "%s: Token endpoint from registry is inv"...
0x18002c378  call    wprintf
0x18002c37d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c382  mov     rcx, [rax]
0x18002c385  cmp     [rcx+0Ch], r15b
0x18002c389  jz      short loc_18002C3BE
0x18002c38b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c390  mov     rcx, [rax]
0x18002c393  cmp     [rcx+0B8h], r15
0x18002c39a  jz      short loc_18002C3BE
0x18002c39c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c3a1  mov     rcx, [rax]
0x18002c3a4  lea     r8, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c3ab  lea     rdx, aSTokenEndpoint; "%s: Token endpoint from registry is inv"...
0x18002c3b2  mov     rcx, [rcx+0B8h]; Stream
0x18002c3b9  call    fwprintf_s
0x18002c3be  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c3c5  lea     rcx, aSTokenEndpoint; "%s: Token endpoint from registry is inv"...
0x18002c3cc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c3d1  mov     rcx, rbx; lpMem
0x18002c3d4  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002c3d9  mov     ebx, 801C0091h
0x18002c3de  jmp     loc_18002C857
0x18002c3e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c3e7  inc     r8
0x18002c3ea  cmp     [rbx+r8*2], r15w
0x18002c3ef  jnz     short loc_18002C3E7
0x18002c3f1  mov     rdx, rbx
0x18002c3f4  lea     rcx, [rsp+168h+Src]
0x18002c3f9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002c3fe  nop
0x18002c3ff  mov     rcx, rbx; lpMem
0x18002c402  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002c407  mov     rdx, rsi
0x18002c40a  test    dil, dil
0x18002c40d  jz      loc_18002C493
0x18002c413  lea     rcx, [rsp+168h+var_E8]
0x18002c41b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002c420  nop
0x18002c421  mov     r8, rax
0x18002c424  lea     rdx, aResource_0; "?resource="
0x18002c42b  lea     rcx, [rsp+168h+var_A8]
0x18002c433  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18002c438  nop
0x18002c439  lea     r8, aApiVersion2020_0; "&api-version=2020-06-01"
0x18002c440  mov     rdx, rax
0x18002c443  lea     rcx, [rsp+168h+var_C8]
0x18002c44b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002c450  nop
0x18002c451  mov     r8, [rax+10h]
0x18002c455  cmp     qword ptr [rax+18h], 7
0x18002c45a  jbe     short loc_18002C45F
0x18002c45c  mov     rax, [rax]
0x18002c45f  mov     rdx, rax
0x18002c462  lea     rcx, [rsp+168h+Src]; Src
0x18002c467  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002c46c  nop
0x18002c46d  lea     rcx, [rsp+168h+var_C8]
0x18002c475  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c47a  nop
0x18002c47b  lea     rcx, [rsp+168h+var_A8]
0x18002c483  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c488  nop
0x18002c489  lea     rcx, [rsp+168h+var_E8]
0x18002c491  jmp     short loc_18002C511
0x18002c493  lea     rcx, [rsp+168h+var_C8]
0x18002c49b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002c4a0  nop
0x18002c4a1  mov     r8, rax
0x18002c4a4  lea     rdx, aResource_0; "?resource="
0x18002c4ab  lea     rcx, [rsp+168h+var_A8]
0x18002c4b3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18002c4b8  nop
0x18002c4b9  lea     r8, aApiVersion2018; "&api-version=2018-02-01"
0x18002c4c0  mov     rdx, rax
0x18002c4c3  lea     rcx, [rsp+168h+var_E8]
0x18002c4cb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002c4d0  nop
0x18002c4d1  mov     r8, [rax+10h]
0x18002c4d5  cmp     qword ptr [rax+18h], 7
0x18002c4da  jbe     short loc_18002C4DF
0x18002c4dc  mov     rax, [rax]
0x18002c4df  mov     rdx, rax
0x18002c4e2  lea     rcx, [rsp+168h+Src]; Src
0x18002c4e7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002c4ec  nop
0x18002c4ed  lea     rcx, [rsp+168h+var_E8]
0x18002c4f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c4fa  nop
0x18002c4fb  lea     rcx, [rsp+168h+var_A8]
0x18002c503  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c508  nop
0x18002c509  lea     rcx, [rsp+168h+var_C8]
0x18002c511  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c516  mov     [rsp+168h+var_148], 1; char
0x18002c51b  mov     r9b, dil
0x18002c51e  lea     r8, [rsp+168h+var_128]
0x18002c523  lea     rdx, [rsp+168h+var_138]
0x18002c528  lea     rcx, [rsp+168h+Src]; pwszUrl
0x18002c52d  call    ?GetMetadataRestResponse@DsrCmdAzureHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAKAEAV23@_N3@Z; DsrCmdAzureHelper::GetMetadataRestResponse(std::wstring const &,ulong &,std::wstring &,bool,bool)
0x18002c532  mov     ebx, eax
0x18002c534  test    eax, eax
0x18002c536  jns     loc_18002C5BE
0x18002c53c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c541  mov     rcx, [rax]
0x18002c544  cmp     [rcx], r15b
0x18002c547  jz      short loc_18002C5A3
0x18002c549  mov     r8d, ebx
0x18002c54c  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c553  lea     rcx, aSGettingMsiAcc; "%s: Getting Msi Access Token for ADRS f"...
0x18002c55a  call    wprintf
0x18002c55f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c564  mov     rcx, [rax]
0x18002c567  cmp     [rcx+0Ch], r15b
0x18002c56b  jz      short loc_18002C5A3
0x18002c56d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c572  mov     rcx, [rax]
0x18002c575  cmp     [rcx+0B8h], r15
0x18002c57c  jz      short loc_18002C5A3
0x18002c57e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c583  mov     rcx, [rax]
0x18002c586  mov     r9d, ebx
0x18002c589  lea     r8, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c590  lea     rdx, aSGettingMsiAcc; "%s: Getting Msi Access Token for ADRS f"...
0x18002c597  mov     rcx, [rcx+0B8h]; Stream
0x18002c59e  call    fwprintf_s
0x18002c5a3  lea     rcx, aSGettingMsiAcc; "%s: Getting Msi Access Token for ADRS f"...
0x18002c5aa  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c5b1  mov     r8d, ebx
0x18002c5b4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c5b9  jmp     loc_18002C857
0x18002c5be  cmp     [rsp+168h+var_138], 0C8h
0x18002c5c6  jz      loc_18002C705
0x18002c5cc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c5d1  mov     rcx, [rax]
0x18002c5d4  cmp     [rcx], r15b
0x18002c5d7  jz      short loc_18002C639
0x18002c5d9  mov     r8d, [rsp+168h+var_138]
0x18002c5de  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c5e5  lea     rcx, aSUnableToGetAc; "%s: Unable to get access token for ADRS"...
0x18002c5ec  call    wprintf
0x18002c5f1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c5f6  mov     rcx, [rax]
0x18002c5f9  cmp     [rcx+0Ch], r15b
0x18002c5fd  jz      short loc_18002C639
0x18002c5ff  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c604  mov     rcx, [rax]
0x18002c607  cmp     [rcx+0B8h], r15
0x18002c60e  jz      short loc_18002C639
0x18002c610  mov     ebx, [rsp+168h+var_138]
0x18002c614  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c619  mov     rcx, [rax]
0x18002c61c  mov     r9d, ebx
0x18002c61f  lea     r8, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c626  lea     rdx, aSUnableToGetAc; "%s: Unable to get access token for ADRS"...
0x18002c62d  mov     rcx, [rcx+0B8h]; Stream
0x18002c634  call    fwprintf_s
0x18002c639  mov     r8d, [rsp+168h+var_138]
0x18002c63e  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c645  lea     rcx, aSUnableToGetAc; "%s: Unable to get access token for ADRS"...
0x18002c64c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c651  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c656  mov     rcx, [rax]
0x18002c659  cmp     [rcx], r15b
0x18002c65c  jz      short loc_18002C6D7
0x18002c65e  lea     r8, [rsp+168h+var_128]
0x18002c663  cmp     [rsp+168h+var_110], 7
0x18002c669  cmova   r8, [rsp+168h+var_128]
0x18002c66f  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c676  lea     rcx, aSS_2; "%s: %s\n"
0x18002c67d  call    wprintf
0x18002c682  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c687  mov     rcx, [rax]
0x18002c68a  cmp     [rcx+0Ch], r15b
0x18002c68e  jz      short loc_18002C6D7
0x18002c690  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c695  mov     rcx, [rax]
0x18002c698  cmp     [rcx+0B8h], r15
0x18002c69f  jz      short loc_18002C6D7
0x18002c6a1  lea     rbx, [rsp+168h+var_128]
0x18002c6a6  cmp     [rsp+168h+var_110], 7
0x18002c6ac  cmova   rbx, [rsp+168h+var_128]
0x18002c6b2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c6b7  mov     rcx, [rax]
0x18002c6ba  mov     r9, rbx
0x18002c6bd  lea     r8, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c6c4  lea     rdx, aSS_2; "%s: %s\n"
0x18002c6cb  mov     rcx, [rcx+0B8h]; Stream
0x18002c6d2  call    fwprintf_s
0x18002c6d7  lea     r8, [rsp+168h+var_128]
0x18002c6dc  cmp     [rsp+168h+var_110], 7
0x18002c6e2  cmova   r8, [rsp+168h+var_128]
0x18002c6e8  lea     rdx, aDsrcmdazurehel_7; "DsrCmdAzureHelper::GetMsiAccessToken"
0x18002c6ef  lea     rcx, aSS_2; "%s: %s\n"
0x18002c6f6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c6fb  mov     ebx, 801C0041h
0x18002c700  jmp     loc_18002C857
0x18002c705  lea     rcx, [rsp+168h+var_88]; this
0x18002c70d  call    ??0CJsonValue@dsreg@@QEAA@XZ; dsreg::CJsonValue::CJsonValue(void)
0x18002c712  nop
0x18002c713  lea     rdx, [rsp+168h+var_128]
0x18002c718  lea     rcx, [rsp+168h+var_E8]
0x18002c720  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c725  lea     rdx, [rsp+168h+var_88]; struct dsreg::CJsonValue *
  ... truncated ...
```
