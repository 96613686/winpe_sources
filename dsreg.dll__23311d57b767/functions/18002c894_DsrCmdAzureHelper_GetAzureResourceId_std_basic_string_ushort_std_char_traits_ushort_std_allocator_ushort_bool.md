# DsrCmdAzureHelper::GetAzureResourceId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x18002c894`
- end: `0x18002d2d1`
- name: `?GetAzureResourceId@DsrCmdAzureHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `2621`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099424`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x180012948`
- `0x180012c7c`
- `0x180016b90`
- `0x18001dfcc`
- `0x180028440`
- `0x180029250`
- `0x18002927c`
- `0x18002999c`
- `0x18002b9b4`
- `0x18002c894`
- `0x18002dd24`
- `0x18002dde4`
- `0x18002de44`
- `0x1800319ac`
- `0x180036b74`
- `0x180039290`
- `0x180039c74`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800a0e10`
- `0x1800a13f0`

## string_xrefs

- `0x18002c8e7`: `AzureVmComputeMetadataEndpoint`
- `0x18002ca33`: `%s: Compute metadata endpoint from registry is invalid.\n`
- `0x18002ca6d`: `%s: Compute metadata endpoint from registry is invalid.\n`
- `0x18002ca87`: `%s: Compute metadata endpoint from registry is invalid.\n`
- `0x18002c910`: `%s: Getting compute metadata endpoint from registry failed. Error code: 0x%08x%.\n`
- `0x18002c94d`: `%s: Getting compute metadata endpoint from registry failed. Error code: 0x%08x%.\n`
- `0x18002c960`: `%s: Getting compute metadata endpoint from registry failed. Error code: 0x%08x%.\n`
- `0x18002c995`: `%s: Compute metadata endpoint from registry is null or empty.\n`
- `0x18002c9cf`: `%s: Compute metadata endpoint from registry is null or empty.\n`
- `0x18002c9e9`: `%s: Compute metadata endpoint from registry is null or empty.\n`
- `0x18002ccc9`: `%s: Failed to deserialize VM metadata json response. Error code: 0x%08x%.\n`
- `0x18002cd06`: `%s: Failed to deserialize VM metadata json response. Error code: 0x%08x%.\n`
- `0x18002cd23`: `%s: Failed to deserialize VM metadata json response. Error code: 0x%08x%.\n`
- `0x18002d17e`: `/providers/Microsoft.Compute/virtualMachines/`
- `0x18002d0bf`: `/providers/Microsoft.HybridCompute/machines/`
- `0x18002d235`: `/providers/Microsoft.Compute/virtualMachineScaleSets/`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DsrCmdAzureHelper::GetAzureResourceId(_QWORD *a1, char a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int MetadataRestResponse; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int16 *v14; // rbx
  __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rdx
  _QWORD *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 *v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rcx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  _QWORD *v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rdi
  unsigned int v51; // ebx
  __int64 v52; // rax
  __int64 *v53; // r9
  unsigned __int16 *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  _QWORD *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rax
  unsigned int v64; // edx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  _QWORD *v69; // rax
  __int64 v70; // rdx
  _QWORD *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  _QWORD *v78; // rax
  __int64 v79; // rdx
  _QWORD *v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  _QWORD *v87; // rax
  __int64 v88; // rdx
  _QWORD *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rcx
  _QWORD *v96; // rax
  __int64 v97; // rdx
  _QWORD *v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rax
  const unsigned __int16 *v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  _BYTE *v108; // rcx
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  unsigned int v119; // [rsp+30h] [rbp-1E8h] BYREF
  unsigned __int16 *v120; // [rsp+38h] [rbp-1E0h] BYREF
  __int64 v121[3]; // [rsp+40h] [rbp-1D8h] BYREF
  unsigned __int64 v122; // [rsp+58h] [rbp-1C0h]
  unsigned __int16 *v123[4]; // [rsp+60h] [rbp-1B8h] BYREF
  _BYTE v124[32]; // [rsp+80h] [rbp-198h] BYREF
  _BYTE v125[32]; // [rsp+A0h] [rbp-178h] BYREF
  _BYTE v126[32]; // [rsp+C0h] [rbp-158h] BYREF
  _BYTE v127[32]; // [rsp+E0h] [rbp-138h] BYREF
  char *Src[4]; // [rsp+100h] [rbp-118h] BYREF
  _BYTE v129[32]; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v130[32]; // [rsp+140h] [rbp-D8h] BYREF
  _BYTE v131[32]; // [rsp+160h] [rbp-B8h] BYREF
  _BYTE v132[32]; // [rsp+180h] [rbp-98h] BYREF
  _BYTE v133[80]; // [rsp+1A0h] [rbp-78h] BYREF

  std::wstring::wstring((__int64)v121);
  v119 = 0;
  v120 = 0;
  std::wstring::wstring((__int64)Src);
  MetadataRestResponse = ReadStringOption(L"AzureVmComputeMetadataEndpoint", &v120);
  if ( (MetadataRestResponse & 0x80000000) != 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v5, v4) )
    {
      wprintf(
        L"%s: Getting compute metadata endpoint from registry failed. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
      CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v8, v7);
      if ( *(_BYTE *)(*CurrentRef + 12LL) )
      {
        v11 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v10);
        if ( *(_QWORD *)(*v11 + 184LL) )
        {
          v13 = CmdOptions::GetCurrentRef(*v11, v12);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v13 + 184LL),
            L"%s: Getting compute metadata endpoint from registry failed. Error code: 0x%08x%.\n",
            L"DsrCmdAzureHelper::GetAzureResourceId",
            MetadataRestResponse);
        }
      }
    }
    Logger::TraceError(
      L"%s: Getting compute metadata endpoint from registry failed. Error code: 0x%08x%.\n",
      L"DsrCmdAzureHelper::GetAzureResourceId",
      MetadataRestResponse);
    goto LABEL_72;
  }
  v14 = v120;
  if ( (unsigned int)IsEmptyString(v120) )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v16, v15) )
    {
      wprintf(
        L"%s: Compute metadata endpoint from registry is null or empty.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId");
      v19 = (_QWORD *)CmdOptions::GetCurrentRef(v18, v17);
      if ( *(_BYTE *)(*v19 + 12LL) )
      {
        v21 = (_QWORD *)CmdOptions::GetCurrentRef(*v19, v20);
        if ( *(_QWORD *)(*v21 + 184LL) )
        {
          v23 = CmdOptions::GetCurrentRef(*v21, v22);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v23 + 184LL),
            L"%s: Compute metadata endpoint from registry is null or empty.\n",
            L"DsrCmdAzureHelper::GetAzureResourceId");
        }
      }
    }
    Logger::TraceError(
      L"%s: Compute metadata endpoint from registry is null or empty.\n",
      L"DsrCmdAzureHelper::GetAzureResourceId");
    SafeFree(v14);
    MetadataRestResponse = -2145648513;
    goto LABEL_72;
  }
  if ( a2 && !DsrCmdAzureHelper::ValidateEndpoint(v16, 0) )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v25, v24) )
    {
      wprintf(L"%s: Compute metadata endpoint from registry is invalid.\n", L"DsrCmdAzureHelper::GetAzureResourceId");
      v28 = (_QWORD *)CmdOptions::GetCurrentRef(v27, v26);
      if ( *(_BYTE *)(*v28 + 12LL) )
      {
        v30 = (_QWORD *)CmdOptions::GetCurrentRef(*v28, v29);
        if ( *(_QWORD *)(*v30 + 184LL) )
        {
          v32 = CmdOptions::GetCurrentRef(*v30, v31);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v32 + 184LL),
            L"%s: Compute metadata endpoint from registry is invalid.\n",
            L"DsrCmdAzureHelper::GetAzureResourceId");
        }
      }
    }
    Logger::TraceError(
      L"%s: Compute metadata endpoint from registry is invalid.\n",
      L"DsrCmdAzureHelper::GetAzureResourceId");
    SafeFree(v14);
    MetadataRestResponse = -2145648497;
    goto LABEL_72;
  }
  try
  {
    v33 = -1;
    do
      ++v33;
    while ( v14[v33] );
    std::wstring::_Assign<unsigned short>(Src, v14, (char *)v33);
  }
  catch ( ... )
  {
    SafeFree(v120);
    throw;
  }
  SafeFree(v14);
  std::wstring::_Append<unsigned short>(Src);
  MetadataRestResponse = DsrCmdAzureHelper::GetMetadataRestResponse((LPCWSTR)Src, &v119, v121, a2, 0);
  if ( (MetadataRestResponse & 0x80000000) != 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v35, v34) )
    {
      wprintf(
        L"%s: Unable to get VM metadata. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
      v38 = (_QWORD *)CmdOptions::GetCurrentRef(v37, v36);
      if ( *(_BYTE *)(*v38 + 12LL) )
      {
        v40 = (_QWORD *)CmdOptions::GetCurrentRef(*v38, v39);
        if ( *(_QWORD *)(*v40 + 184LL) )
        {
          v42 = CmdOptions::GetCurrentRef(*v40, v41);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v42 + 184LL),
            L"%s: Unable to get VM metadata. Error code: 0x%08x%.\n",
            L"DsrCmdAzureHelper::GetAzureResourceId",
            MetadataRestResponse);
        }
      }
    }
    Logger::TraceError(
      L"%s: Unable to get VM metadata. Error code: 0x%08x%.\n",
      L"DsrCmdAzureHelper::GetAzureResourceId",
      MetadataRestResponse);
    goto LABEL_72;
  }
  if ( v119 == 200 )
  {
    dsreg::CJsonValue::CJsonValue((dsreg::CJsonValue *)v133);
    v54 = (unsigned __int16 *)std::wstring::wstring(v127, v121);
    MetadataRestResponse = DsrCmdAzureHelper::GetJsonValue(v54, (struct dsreg::CJsonValue *)v133);
    if ( (MetadataRestResponse & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v56, v55) )
      {
        wprintf(
          L"%s: Failed to deserialize VM metadata json response. Error code: 0x%08x%.\n",
          L"DsrCmdAzureHelper::GetAzureResourceId",
          MetadataRestResponse);
        v59 = (_QWORD *)CmdOptions::GetCurrentRef(v58, v57);
        if ( *(_BYTE *)(*v59 + 12LL) )
        {
          v61 = (_QWORD *)CmdOptions::GetCurrentRef(*v59, v60);
          if ( *(_QWORD *)(*v61 + 184LL) )
          {
            v63 = CmdOptions::GetCurrentRef(*v61, v62);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v63 + 184LL),
              L"%s: Failed to deserialize VM metadata json response. Error code: 0x%08x%.\n",
              L"DsrCmdAzureHelper::GetAzureResourceId",
              MetadataRestResponse);
          }
        }
      }
      Logger::TraceError(
        L"%s: Failed to deserialize VM metadata json response. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
      goto LABEL_71;
    }
    std::wstring::wstring((__int64)v125);
    std::wstring::wstring((__int64)v124);
    std::wstring::wstring((__int64)v126);
    std::wstring::wstring((__int64)v123);
    MetadataRestResponse = DsrCmdAzureHelper::GetStringValueFromProperty(
                             (struct dsreg::CJsonValue *)v133,
                             L"subscriptionId");
    if ( (MetadataRestResponse & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v66, v65) )
      {
        wprintf(
          L"%s: Failed to extract subscriptionId property. Error code: 0x%08x%.\n",
          L"DsrCmdAzureHelper::GetAzureResourceId",
          MetadataRestResponse);
        v69 = (_QWORD *)CmdOptions::GetCurrentRef(v68, v67);
        if ( *(_BYTE *)(*v69 + 12LL) )
        {
          v71 = (_QWORD *)CmdOptions::GetCurrentRef(*v69, v70);
          if ( *(_QWORD *)(*v71 + 184LL) )
          {
            v73 = CmdOptions::GetCurrentRef(*v71, v72);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v73 + 184LL),
              L"%s: Failed to extract subscriptionId property. Error code: 0x%08x%.\n",
              L"DsrCmdAzureHelper::GetAzureResourceId",
              MetadataRestResponse);
          }
        }
      }
      Logger::TraceError(
        L"%s: Failed to extract subscriptionId property. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
LABEL_70:
      std::wstring::_Tidy_deallocate((__int64)v123);
      std::wstring::_Tidy_deallocate((__int64)v126);
      std::wstring::_Tidy_deallocate((__int64)v124);
      std::wstring::_Tidy_deallocate((__int64)v125);
LABEL_71:
      dsreg::CJsonValue::~CJsonValue((dsreg::CJsonValue *)v133, v64);
      goto LABEL_72;
    }
    MetadataRestResponse = DsrCmdAzureHelper::GetStringValueFromProperty(
                             (struct dsreg::CJsonValue *)v133,
                             L"resourceGroupName");
    if ( (MetadataRestResponse & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v75, v74) )
      {
        wprintf(
          L"%s: Failed to extract resourceGroupName property. Error code: 0x%08x%.\n",
          L"DsrCmdAzureHelper::GetAzureResourceId",
          MetadataRestResponse);
        v78 = (_QWORD *)CmdOptions::GetCurrentRef(v77, v76);
        if ( *(_BYTE *)(*v78 + 12LL) )
        {
          v80 = (_QWORD *)CmdOptions::GetCurrentRef(*v78, v79);
          if ( *(_QWORD *)(*v80 + 184LL) )
          {
            v82 = CmdOptions::GetCurrentRef(*v80, v81);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v82 + 184LL),
              L"%s: Failed to extract resourceGroupName property. Error code: 0x%08x%.\n",
              L"DsrCmdAzureHelper::GetAzureResourceId",
              MetadataRestResponse);
          }
        }
      }
      Logger::TraceError(
        L"%s: Failed to extract resourceGroupName property. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
      goto LABEL_70;
    }
    MetadataRestResponse = DsrCmdAzureHelper::GetStringValueFromProperty((struct dsreg::CJsonValue *)v133, L"name");
    if ( (MetadataRestResponse & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v84, v83) )
      {
        wprintf(
          L"%s: Failed to extract name property. Error code: 0x%08x%.\n",
          L"DsrCmdAzureHelper::GetAzureResourceId",
          MetadataRestResponse);
        v87 = (_QWORD *)CmdOptions::GetCurrentRef(v86, v85);
        if ( *(_BYTE *)(*v87 + 12LL) )
        {
          v89 = (_QWORD *)CmdOptions::GetCurrentRef(*v87, v88);
          if ( *(_QWORD *)(*v89 + 184LL) )
          {
            v91 = CmdOptions::GetCurrentRef(*v89, v90);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v91 + 184LL),
              L"%s: Failed to extract name property. Error code: 0x%08x%.\n",
              L"DsrCmdAzureHelper::GetAzureResourceId",
              MetadataRestResponse);
          }
        }
      }
      Logger::TraceError(
        L"%s: Failed to extract name property. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
      goto LABEL_70;
    }
    MetadataRestResponse = DsrCmdAzureHelper::GetStringValueFromProperty(
                             (struct dsreg::CJsonValue *)v133,
                             L"vmScaleSetName");
    if ( (MetadataRestResponse & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v93, v92) )
      {
        wprintf(
          L"%s: Failed to extract vmScaleSetName property. Error code: 0x%08x%.\n",
          L"DsrCmdAzureHelper::GetAzureResourceId",
          MetadataRestResponse);
        v96 = (_QWORD *)CmdOptions::GetCurrentRef(v95, v94);
        if ( *(_BYTE *)(*v96 + 12LL) )
        {
          v98 = (_QWORD *)CmdOptions::GetCurrentRef(*v96, v97);
          if ( *(_QWORD *)(*v98 + 184LL) )
          {
            v100 = CmdOptions::GetCurrentRef(*v98, v99);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v100 + 184LL),
              L"%s: Failed to extract vmScaleSetName property. Error code: 0x%08x%.\n",
              L"DsrCmdAzureHelper::GetAzureResourceId",
              MetadataRestResponse);
          }
        }
      }
      Logger::TraceError(
        L"%s: Failed to extract vmScaleSetName property. Error code: 0x%08x%.\n",
        L"DsrCmdAzureHelper::GetAzureResourceId",
        MetadataRestResponse);
      goto LABEL_70;
    }
    v102 = (const unsigned __int16 *)v123;
    if ( v123[3] > (unsigned __int16 *)7 )
      v102 = v123[0];
    if ( (unsigned int)IsEmptyString(v102) )
    {
      if ( a2 )
      {
        v103 = std::operator+<unsigned short>(v132, L"/subscriptions/", v125);
        v104 = std::operator+<unsigned short>(v131, v103, L"/resourceGroups/");
        v105 = std::operator+<unsigned short>(v130, v104, v124);
        v106 = std::operator+<unsigned short>(v129, v105, L"/providers/Microsoft.HybridCompute/machines/");
        v107 = std::operator+<unsigned short>(v127, v106, v126);
        std::wstring::operator=((__int64)a1, v107);
        std::wstring::_Tidy_deallocate((__int64)v127);
        std::wstring::_Tidy_deallocate((__int64)v129);
        std::wstring::_Tidy_deallocate((__int64)v130);
        std::wstring::_Tidy_deallocate((__int64)v131);
        v108 = v132;
LABEL_81:
        std::wstring::_Tidy_deallocate((__int64)v108);
        if ( a1[3] > 7u )
          a1 = (_QWORD *)*a1;
        Logger::TraceInformation(L"AzureResourceId: %s", a1);
        goto LABEL_70;
      }
      v109 = std::operator+<unsigned short>(v127, L"/subscriptions/", v125);
      v110 = std::operator+<unsigned short>(v129, v109, L"/resourceGroups/");
      v111 = std::operator+<unsigned short>(v130, v110, v124);
      v112 = std::operator+<unsigned short>(v131, v111, L"/providers/Microsoft.Compute/virtualMachines/");
      v113 = std::operator+<unsigned short>(v132, v112, v126);
      std::wstring::operator=((__int64)a1, v113);
      std::wstring::_Tidy_deallocate((__int64)v132);
      std::wstring::_Tidy_deallocate((__int64)v131);
      std::wstring::_Tidy_deallocate((__int64)v130);
      std::wstring::_Tidy_deallocate((__int64)v129);
    }
    else
    {
      v114 = std::operator+<unsigned short>(v127, L"/subscriptions/", v125);
      v115 = std::operator+<unsigned short>(v129, v114, L"/resourceGroups/");
      v116 = std::operator+<unsigned short>(v130, v115, v124);
      v117 = std::operator+<unsigned short>(v131, v116, L"/providers/Microsoft.Compute/virtualMachineScaleSets/");
      v118 = std::operator+<unsigned short>(v132, v117, v123);
      std::wstring::operator=((__int64)a1, v118);
      std::wstring::_Tidy_deallocate((__int64)v132);
      std::wstring::_Tidy_deallocate((__int64)v131);
      std::wstring::_Tidy_deallocate((__int64)v130);
      std::wstring::_Tidy_deallocate((__int64)v129);
    }
    v108 = v127;
    goto LABEL_81;
  }
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v35, v34) )
  {
    v43 = v121;
    if ( v122 > 7 )
      v43 = (__int64 *)v121[0];
    wprintf(L"%s: Unable to get VM metadata, status code %d\n%s\n", L"DsrCmdAzureHelper::GetAzureResourceId", v119, v43);
    v46 = (_QWORD *)CmdOptions::GetCurrentRef(v45, v44);
    if ( *(_BYTE *)(*v46 + 12LL) )
    {
      v48 = (_QWORD *)CmdOptions::GetCurrentRef(*v46, v47);
      if ( *(_QWORD *)(*v48 + 184LL) )
      {
        v50 = v121;
        if ( v122 > 7 )
          v50 = (__int64 *)v121[0];
        v51 = v119;
        v52 = CmdOptions::GetCurrentRef(*v48, v49);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v52 + 184LL),
          L"%s: Unable to get VM metadata, status code %d\n%s\n",
          L"DsrCmdAzureHelper::GetAzureResourceId",
          v51,
          v50);
      }
    }
  }
  v53 = v121;
  if ( v122 > 7 )
    v53 = (__int64 *)v121[0];
  Logger::TraceError(
    L"%s: Unable to get VM metadata, status code %d\n%s\n",
    L"DsrCmdAzureHelper::GetAzureResourceId",
    v119,
    v53);
  MetadataRestResponse = -2145648573;
LABEL_72:
  std::wstring::_Tidy_deallocate((__int64)Src);
  std::wstring::_Tidy_deallocate((__int64)v121);
  return MetadataRestResponse;
}

```

## disassembly

```asm
0x18002c894  mov     [rsp+arg_10], rbx
0x18002c899  push    rsi
0x18002c89a  push    rdi
0x18002c89b  push    r14
0x18002c89d  sub     rsp, 200h
0x18002c8a4  mov     rax, cs:__security_cookie
0x18002c8ab  xor     rax, rsp
0x18002c8ae  mov     [rsp+218h+var_28], rax
0x18002c8b6  mov     sil, dl
0x18002c8b9  mov     rdi, rcx
0x18002c8bc  lea     rcx, [rsp+218h+var_1D8]
0x18002c8c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002c8c6  nop
0x18002c8c7  xor     r14d, r14d
0x18002c8ca  mov     [rsp+218h+var_1E8], r14d
0x18002c8cf  mov     [rsp+218h+var_1E0], r14
0x18002c8d4  lea     rcx, [rsp+218h+Src]
0x18002c8dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002c8e1  nop
0x18002c8e2  lea     rdx, [rsp+218h+var_1E0]; unsigned __int16 **
0x18002c8e7  lea     rcx, aAzurevmcompute; "AzureVmComputeMetadataEndpoint"
0x18002c8ee  call    ?ReadStringOption@@YAJPEBGPEAPEAG@Z; ReadStringOption(ushort const *,ushort * *)
0x18002c8f3  mov     ebx, eax
0x18002c8f5  test    eax, eax
0x18002c8f7  jns     short loc_18002C96C
0x18002c8f9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c8fe  mov     rcx, [rax]
0x18002c901  cmp     [rcx], r14b
0x18002c904  jz      short loc_18002C960
0x18002c906  mov     r8d, ebx
0x18002c909  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002c910  lea     rcx, aSGettingComput; "%s: Getting compute metadata endpoint f"...
0x18002c917  call    wprintf
0x18002c91c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c921  mov     rcx, [rax]
0x18002c924  cmp     [rcx+0Ch], r14b
0x18002c928  jz      short loc_18002C960
0x18002c92a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c92f  mov     rcx, [rax]
0x18002c932  cmp     [rcx+0B8h], r14
0x18002c939  jz      short loc_18002C960
0x18002c93b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c940  mov     rcx, [rax]
0x18002c943  mov     r9d, ebx
0x18002c946  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002c94d  lea     rdx, aSGettingComput; "%s: Getting compute metadata endpoint f"...
0x18002c954  mov     rcx, [rcx+0B8h]; Stream
0x18002c95b  call    fwprintf_s
0x18002c960  lea     rcx, aSGettingComput; "%s: Getting compute metadata endpoint f"...
0x18002c967  jmp     loc_18002CB8B
0x18002c96c  mov     rbx, [rsp+218h+var_1E0]
0x18002c971  mov     rcx, rbx; unsigned __int16 *
0x18002c974  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18002c979  test    eax, eax
0x18002c97b  jz      loc_18002CA07
0x18002c981  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c986  mov     rcx, [rax]
0x18002c989  cmp     [rcx], r14b
0x18002c98c  jz      short loc_18002C9E2
0x18002c98e  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002c995  lea     rcx, aSComputeMetada; "%s: Compute metadata endpoint from regi"...
0x18002c99c  call    wprintf
0x18002c9a1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c9a6  mov     rcx, [rax]
0x18002c9a9  cmp     [rcx+0Ch], r14b
0x18002c9ad  jz      short loc_18002C9E2
0x18002c9af  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c9b4  mov     rcx, [rax]
0x18002c9b7  cmp     [rcx+0B8h], r14
0x18002c9be  jz      short loc_18002C9E2
0x18002c9c0  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002c9c5  mov     rcx, [rax]
0x18002c9c8  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002c9cf  lea     rdx, aSComputeMetada; "%s: Compute metadata endpoint from regi"...
0x18002c9d6  mov     rcx, [rcx+0B8h]; Stream
0x18002c9dd  call    fwprintf_s
0x18002c9e2  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002c9e9  lea     rcx, aSComputeMetada; "%s: Compute metadata endpoint from regi"...
0x18002c9f0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c9f5  mov     rcx, rbx; lpMem
0x18002c9f8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002c9fd  mov     ebx, 801C007Fh
0x18002ca02  jmp     loc_18002D00C
0x18002ca07  test    sil, sil
0x18002ca0a  jz      loc_18002CAA5
0x18002ca10  xor     edx, edx; unsigned int
0x18002ca12  call    ?ValidateEndpoint@DsrCmdAzureHelper@@CA_NPEAGK@Z; DsrCmdAzureHelper::ValidateEndpoint(ushort *,ulong)
0x18002ca17  test    al, al
0x18002ca19  jnz     loc_18002CAA5
0x18002ca1f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ca24  mov     rcx, [rax]
0x18002ca27  cmp     [rcx], r14b
0x18002ca2a  jz      short loc_18002CA80
0x18002ca2c  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002ca33  lea     rcx, aSComputeMetada_0; "%s: Compute metadata endpoint from regi"...
0x18002ca3a  call    wprintf
0x18002ca3f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ca44  mov     rcx, [rax]
0x18002ca47  cmp     [rcx+0Ch], r14b
0x18002ca4b  jz      short loc_18002CA80
0x18002ca4d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ca52  mov     rcx, [rax]
0x18002ca55  cmp     [rcx+0B8h], r14
0x18002ca5c  jz      short loc_18002CA80
0x18002ca5e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ca63  mov     rcx, [rax]
0x18002ca66  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002ca6d  lea     rdx, aSComputeMetada_0; "%s: Compute metadata endpoint from regi"...
0x18002ca74  mov     rcx, [rcx+0B8h]; Stream
0x18002ca7b  call    fwprintf_s
0x18002ca80  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002ca87  lea     rcx, aSComputeMetada_0; "%s: Compute metadata endpoint from regi"...
0x18002ca8e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002ca93  mov     rcx, rbx; lpMem
0x18002ca96  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002ca9b  mov     ebx, 801C008Fh
0x18002caa0  jmp     loc_18002D00C
0x18002caa5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002caa9  inc     r8
0x18002caac  cmp     [rbx+r8*2], r14w
0x18002cab1  jnz     short loc_18002CAA9
0x18002cab3  mov     rdx, rbx
0x18002cab6  lea     rcx, [rsp+218h+Src]
0x18002cabe  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002cac3  nop
0x18002cac4  mov     rcx, rbx; lpMem
0x18002cac7  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002cacc  lea     rax, aApiVersion2017; "?api-version=2017-12-01"
0x18002cad3  lea     rdx, aApiVersion2020; "?api-version=2020-06-01"
0x18002cada  test    sil, sil
0x18002cadd  cmovz   rdx, rax
0x18002cae1  mov     r8d, 17h
0x18002cae7  lea     rcx, [rsp+218h+Src]; Src
0x18002caef  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002caf4  mov     [rsp+218h+var_1F8], r14b; char
0x18002caf9  mov     r9b, sil
0x18002cafc  lea     r8, [rsp+218h+var_1D8]
0x18002cb01  lea     rdx, [rsp+218h+var_1E8]
0x18002cb06  lea     rcx, [rsp+218h+Src]; pwszUrl
0x18002cb0e  call    ?GetMetadataRestResponse@DsrCmdAzureHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAKAEAV23@_N3@Z; DsrCmdAzureHelper::GetMetadataRestResponse(std::wstring const &,ulong &,std::wstring &,bool,bool)
0x18002cb13  mov     ebx, eax
0x18002cb15  test    eax, eax
0x18002cb17  jns     loc_18002CB9F
0x18002cb1d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cb22  mov     rcx, [rax]
0x18002cb25  cmp     [rcx], r14b
0x18002cb28  jz      short loc_18002CB84
0x18002cb2a  mov     r8d, ebx
0x18002cb2d  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cb34  lea     rcx, aSUnableToGetVm; "%s: Unable to get VM metadata. Error co"...
0x18002cb3b  call    wprintf
0x18002cb40  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cb45  mov     rcx, [rax]
0x18002cb48  cmp     [rcx+0Ch], r14b
0x18002cb4c  jz      short loc_18002CB84
0x18002cb4e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cb53  mov     rcx, [rax]
0x18002cb56  cmp     [rcx+0B8h], r14
0x18002cb5d  jz      short loc_18002CB84
0x18002cb5f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cb64  mov     rcx, [rax]
0x18002cb67  mov     r9d, ebx
0x18002cb6a  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cb71  lea     rdx, aSUnableToGetVm; "%s: Unable to get VM metadata. Error co"...
0x18002cb78  mov     rcx, [rcx+0B8h]; Stream
0x18002cb7f  call    fwprintf_s
0x18002cb84  lea     rcx, aSUnableToGetVm; "%s: Unable to get VM metadata. Error co"...
0x18002cb8b  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cb92  mov     r8d, ebx
0x18002cb95  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cb9a  jmp     loc_18002D00C
0x18002cb9f  cmp     [rsp+218h+var_1E8], 0C8h
0x18002cba7  jz      loc_18002CC78
0x18002cbad  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cbb2  mov     rcx, [rax]
0x18002cbb5  cmp     [rcx], r14b
0x18002cbb8  jz      loc_18002CC45
0x18002cbbe  lea     r9, [rsp+218h+var_1D8]
0x18002cbc3  cmp     [rsp+218h+var_1C0], 7
0x18002cbc9  cmova   r9, [rsp+218h+var_1D8]
0x18002cbcf  mov     r8d, [rsp+218h+var_1E8]
0x18002cbd4  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cbdb  lea     rcx, aSUnableToGetVm_0; "%s: Unable to get VM metadata, status c"...
0x18002cbe2  call    wprintf
0x18002cbe7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cbec  mov     rcx, [rax]
0x18002cbef  cmp     [rcx+0Ch], r14b
0x18002cbf3  jz      short loc_18002CC45
0x18002cbf5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cbfa  mov     rcx, [rax]
0x18002cbfd  cmp     [rcx+0B8h], r14
0x18002cc04  jz      short loc_18002CC45
0x18002cc06  lea     rdi, [rsp+218h+var_1D8]
0x18002cc0b  cmp     [rsp+218h+var_1C0], 7
0x18002cc11  cmova   rdi, [rsp+218h+var_1D8]
0x18002cc17  mov     ebx, [rsp+218h+var_1E8]
0x18002cc1b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cc20  mov     rcx, [rax]
0x18002cc23  mov     qword ptr [rsp+218h+var_1F8], rdi
0x18002cc28  mov     r9d, ebx
0x18002cc2b  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cc32  lea     rdx, aSUnableToGetVm_0; "%s: Unable to get VM metadata, status c"...
0x18002cc39  mov     rcx, [rcx+0B8h]; Stream
0x18002cc40  call    fwprintf_s
0x18002cc45  lea     r9, [rsp+218h+var_1D8]
0x18002cc4a  cmp     [rsp+218h+var_1C0], 7
0x18002cc50  cmova   r9, [rsp+218h+var_1D8]
0x18002cc56  mov     r8d, [rsp+218h+var_1E8]
0x18002cc5b  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cc62  lea     rcx, aSUnableToGetVm_0; "%s: Unable to get VM metadata, status c"...
0x18002cc69  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cc6e  mov     ebx, 801C0043h
0x18002cc73  jmp     loc_18002D00C
0x18002cc78  lea     rcx, [rsp+218h+var_78]; this
0x18002cc80  call    ??0CJsonValue@dsreg@@QEAA@XZ; dsreg::CJsonValue::CJsonValue(void)
0x18002cc85  nop
0x18002cc86  lea     rdx, [rsp+218h+var_1D8]
0x18002cc8b  lea     rcx, [rsp+218h+var_138]
0x18002cc93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cc98  lea     rdx, [rsp+218h+var_78]; struct dsreg::CJsonValue *
0x18002cca0  mov     rcx, rax; unsigned __int16 *
0x18002cca3  call    ?GetJsonValue@DsrCmdAzureHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCJsonValue@dsreg@@@Z; DsrCmdAzureHelper::GetJsonValue(std::wstring,dsreg::CJsonValue &)
0x18002cca8  mov     ebx, eax
0x18002ccaa  test    eax, eax
0x18002ccac  jns     loc_18002CD34
0x18002ccb2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ccb7  mov     rcx, [rax]
0x18002ccba  cmp     [rcx], r14b
0x18002ccbd  jz      short loc_18002CD19
0x18002ccbf  mov     r8d, ebx
0x18002ccc2  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002ccc9  lea     rcx, aSFailedToDeser_1; "%s: Failed to deserialize VM metadata j"...
0x18002ccd0  call    wprintf
0x18002ccd5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ccda  mov     rcx, [rax]
0x18002ccdd  cmp     [rcx+0Ch], r14b
0x18002cce1  jz      short loc_18002CD19
0x18002cce3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cce8  mov     rcx, [rax]
0x18002cceb  cmp     [rcx+0B8h], r14
0x18002ccf2  jz      short loc_18002CD19
0x18002ccf4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002ccf9  mov     rcx, [rax]
0x18002ccfc  mov     r9d, ebx
0x18002ccff  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cd06  lea     rdx, aSFailedToDeser_1; "%s: Failed to deserialize VM metadata j"...
0x18002cd0d  mov     rcx, [rcx+0B8h]; Stream
0x18002cd14  call    fwprintf_s
0x18002cd19  mov     r8d, ebx
0x18002cd1c  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cd23  lea     rcx, aSFailedToDeser_1; "%s: Failed to deserialize VM metadata j"...
0x18002cd2a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cd2f  jmp     loc_18002CFFE
0x18002cd34  lea     rcx, [rsp+218h+var_178]
0x18002cd3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cd41  nop
0x18002cd42  lea     rcx, [rsp+218h+var_198]
0x18002cd4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cd4f  nop
0x18002cd50  lea     rcx, [rsp+218h+var_158]
0x18002cd58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cd5d  nop
0x18002cd5e  lea     rcx, [rsp+218h+var_1B8]
0x18002cd63  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cd68  nop
0x18002cd69  lea     r8, [rsp+218h+var_178]
0x18002cd71  lea     rdx, aSubscriptionid; "subscriptionId"
0x18002cd78  lea     rcx, [rsp+218h+var_78]; struct dsreg::CJsonValue *
0x18002cd80  call    ?GetStringValueFromProperty@DsrCmdAzureHelper@@CAJPEAVCJsonValue@dsreg@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DsrCmdAzureHelper::GetStringValueFromProperty(dsreg::CJsonValue *,ushort const *,std::wstring &)
0x18002cd85  mov     ebx, eax
0x18002cd87  test    eax, eax
0x18002cd89  jns     short loc_18002CDFE
0x18002cd8b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cd90  mov     rcx, [rax]
0x18002cd93  cmp     [rcx], r14b
0x18002cd96  jz      short loc_18002CDF2
0x18002cd98  mov     r8d, ebx
0x18002cd9b  lea     rdx, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cda2  lea     rcx, aSFailedToExtra_0; "%s: Failed to extract subscriptionId pr"...
0x18002cda9  call    wprintf
0x18002cdae  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cdb3  mov     rcx, [rax]
0x18002cdb6  cmp     [rcx+0Ch], r14b
0x18002cdba  jz      short loc_18002CDF2
0x18002cdbc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cdc1  mov     rcx, [rax]
0x18002cdc4  cmp     [rcx+0B8h], r14
0x18002cdcb  jz      short loc_18002CDF2
0x18002cdcd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002cdd2  mov     rcx, [rax]
0x18002cdd5  mov     r9d, ebx
0x18002cdd8  lea     r8, aDsrcmdazurehel_3; "DsrCmdAzureHelper::GetAzureResourceId"
0x18002cddf  lea     rdx, aSFailedToExtra_0; "%s: Failed to extract subscriptionId pr"...
0x18002cde6  mov     rcx, [rcx+0B8h]; Stream
0x18002cded  call    fwprintf_s
0x18002cdf2  lea     rcx, aSFailedToExtra_0; "%s: Failed to extract subscriptionId pr"...
0x18002cdf9  jmp     loc_18002CFB9
0x18002cdfe  lea     r8, [rsp+218h+var_198]
0x18002ce06  lea     rdx, aResourcegroupn; "resourceGroupName"
0x18002ce0d  lea     rcx, [rsp+218h+var_78]; struct dsreg::CJsonValue *
  ... truncated ...
```
