# FwMoneisPlumbCloudResourceNrpt(void)

- ea: `0x18004b920`
- end: `0x18004bd87`
- name: `?FwMoneisPlumbCloudResourceNrpt@@YAKXZ`
- size: `1127`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180055a20`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18002bd6c`
- `0x18003336c`
- `0x18004b920`
- `0x18004bd90`
- `0x18005e7e8`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004bc9c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004bc9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004bbfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004bbfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bc12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bc12`
- `ntdll!RtlNtStatusToDosError` at `0x18004bc5d`
- `ntdll!RtlNtStatusToDosError` at `0x18004bc5d`
- `fwbase!FwBaseFree` at `0x18004bcfa`
- `fwbase!FwBaseFree` at `0x18004bd14`
- `fwbase!FwBaseFree` at `0x18004bd24`
- `fwbase!FwBaseFree` at `0x18004bd36`
- `fwbase!FwBaseFree` at `0x18004bd4c`
- `fwbase!FwBaseFree` at `0x18004bd5d`
- `fwbase!FwBaseFree` at `0x18004bcfa`
- `fwbase!FwBaseFree` at `0x18004bd14`
- `fwbase!FwBaseFree` at `0x18004bd24`
- `fwbase!FwBaseFree` at `0x18004bd36`
- `fwbase!FwBaseFree` at `0x18004bd4c`
- `fwbase!FwBaseFree` at `0x18004bd5d`
- `fwbase!FwRegQueryString` at `0x18004ba3f`
- `fwbase!FwRegQueryString` at `0x18004ba3f`
- `fwbase!FwRegSetDWord` at `0x18004bce9`
- `fwbase!FwRegSetDWord` at `0x18004bce9`
- `fwbase!FwParseEdpCloudResourceStringToNrptRuleList` at `0x18004bbb4`
- `fwbase!FwParseEdpCloudResourceStringToNrptRuleList` at `0x18004bbb4`
- `fwbase!FwHResultToWindowsError` at `0x18004baad`
- `fwbase!FwHResultToWindowsError` at `0x18004bb42`
- `fwbase!FwHResultToWindowsError` at `0x18004baad`
- `fwbase!FwHResultToWindowsError` at `0x18004bb42`
- `fwbase!FwStringCopy` at `0x18004ba7d`
- `fwbase!FwStringCopy` at `0x18004bb34`
- `fwbase!FwStringCopy` at `0x18004ba7d`
- `fwbase!FwStringCopy` at `0x18004bb34`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18004ba90`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18004ba90`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18004ba67`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18004ba67`

## string_xrefs

- `0x18004bbf5`: `ntdll.dll`
- `0x18004b945`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x18004bc39`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x18004bc45`: `TargetPath`
- `0x18004bc4c`: `Dnscache`

## pseudocode

```c
__int64 FwMoneisPlumbCloudResourceNrpt(void)
{
  unsigned int v0; // edi
  FwPolicy2 *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // r9
  unsigned int v4; // ebx
  unsigned int v5; // eax
  ULONG v6; // eax
  unsigned int v7; // eax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  NTSTATUS v10; // eax
  _QWORD *v11; // rsi
  _QWORD *v12; // rbx
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v19[3]; // [rsp+64h] [rbp-9Ch] BYREF
  _OWORD v20[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[22]; // [rsp+B0h] [rbp-50h]
  _BYTE v22[442]; // [rsp+C6h] [rbp-3Ah] BYREF

  v20[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\dnscache";
  v20[1] = *(_OWORD *)L"urrentControlSet\\Services\\dnscache";
  v20[2] = *(_OWORD *)L"ntrolSet\\Services\\dnscache";
  v20[3] = *(_OWORD *)L"\\Services\\dnscache";
  *(_OWORD *)v21 = *(_OWORD *)L"s\\dnscache";
  *(_QWORD *)&v21[14] = *(_QWORD *)L"che";
  v18 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v19[0] = 0;
  v16 = 0;
  memset_0(v22, 0, 0x1B2u);
  if ( !(unsigned __int8)IsPolicyManager_GetPolicyStringPresent() )
  {
    v0 = 50;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 431;
      v3 = 50;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v3);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v4 = FwRegQueryString(
         -2147483646,
         L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
         L"CloudResources",
         &v14,
         &v18);
  if ( !v18 )
  {
    PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseCloudResources", &v15);
    v4 = FwStringCopy(v15, &v14);
    PolicyManager_FreeStringValue(v15);
  }
  if ( !v14 )
  {
    v0 = 0;
    goto LABEL_41;
  }
  v5 = FwHResultToWindowsError(v4);
  v0 = v5;
  if ( !v5 )
  {
    v6 = FwMoneisUnPlumbCloudResourceNrpt();
    v0 = v6;
    if ( v6 == 2 )
    {
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 433, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    }
    else if ( v6 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v2 = 434;
      goto LABEL_26;
    }
    v7 = FwStringCopy(v14, &v17);
    v6 = FwHResultToWindowsError(v7);
    v0 = v6;
    if ( v6 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v2 = 435;
    }
    else
    {
      v6 = FwParseEdpCloudResourceStringToNrptRuleList(v17, 0, &v16, v19);
      v0 = v6;
      if ( v6 )
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_41;
        v2 = 436;
      }
      else
      {
        RasAddNrptRules(v16, v19[0]);
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
        if ( !ProcAddress
          || (v10 = ((__int64 (__fastcall *)(const wchar_t *, const wchar_t *, const wchar_t *, _QWORD, _OWORD *, int, _QWORD))ProcAddress)(
                      L"Dnscache",
                      L"TargetPath",
                      L"SYSTEM\\CurrentControlSet\\Services\\dnscache",
                      0,
                      v20,
                      520,
                      0),
              v6 = RtlNtStatusToDosError(v10),
              (v0 = v6) == 0) )
        {
          if ( (unsigned int)_o_wcscat_s(v20, 260, L"\\Parameters") )
          {
            v0 = 87;
            v1 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v2 = 438;
              v3 = 87;
              goto LABEL_5;
            }
          }
          else
          {
            FwRegSetDWord(-2147483646, v20, L"ShortnameProxyDefault", 1);
          }
          goto LABEL_41;
        }
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_41;
        v2 = 437;
      }
    }
LABEL_26:
    v3 = v6;
    goto LABEL_5;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = 432;
    v3 = v5;
    goto LABEL_5;
  }
LABEL_41:
  FwBaseFree(v14);
  v11 = v16;
  if ( v16 )
  {
    do
    {
      FwBaseFree(v11[5]);
      FwBaseFree(v11[7]);
      v12 = (_QWORD *)*v11;
      FwBaseFree(v11);
      v11 = v12;
    }
    while ( v12 );
  }
  FwBaseFree(0);
  FwBaseFree(v17);
  return v0;
}

```

## disassembly

```asm
0x18004b920  push    rbp
0x18004b922  push    rbx
0x18004b923  push    rsi
0x18004b924  push    rdi
0x18004b925  lea     rbp, [rsp-198h]
0x18004b92d  sub     rsp, 298h
0x18004b934  mov     rax, cs:__security_cookie
0x18004b93b  xor     rax, rsp
0x18004b93e  mov     [rbp+1B0h+var_30], rax
0x18004b945  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x18004b94c  lea     rcx, [rbp+1B0h+var_1EA]; void *
0x18004b950  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\dnscache"
0x18004b957  xor     edx, edx; Val
0x18004b959  movaps  [rsp+2B0h+var_240], xmm0
0x18004b95e  mov     r8d, 1B2h; Size
0x18004b964  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\dnscache"
0x18004b96b  movaps  [rbp+1B0h+var_230], xmm1
0x18004b96f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\dnscache"
0x18004b976  movaps  [rbp+1B0h+var_220], xmm0
0x18004b97a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\dnscache"
0x18004b981  movaps  [rbp+1B0h+var_210], xmm1
0x18004b985  movsd   xmm1, qword ptr cs:aSystemCurrentc+4Eh; "che"
0x18004b98d  movaps  xmmword ptr [rbp+1B0h+var_200], xmm0
0x18004b991  movsd   qword ptr [rbp+1B0h+var_200+0Eh], xmm1
0x18004b996  mov     [rsp+2B0h+var_250], 0
0x18004b99e  mov     [rsp+2B0h+var_270], 0
0x18004b9a7  mov     [rsp+2B0h+var_258], 0
0x18004b9b0  mov     [rsp+2B0h+var_268], 0
0x18004b9b9  mov     [rsp+2B0h+var_24C], 0
0x18004b9c1  mov     [rsp+2B0h+var_260], 0
0x18004b9ca  call    memset_0
0x18004b9cf  call    IsPolicyManager_GetPolicyStringPresent
0x18004b9d4  test    al, al
0x18004b9d6  jnz     short loc_18004BA1B
0x18004b9d8  mov     edi, 32h ; '2'
0x18004b9dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9e4  lea     rbx, WPP_GLOBAL_Control
0x18004b9eb  cmp     rcx, rbx
0x18004b9ee  jz      loc_18004BCF5
0x18004b9f4  test    byte ptr [rcx+1Ch], 1
0x18004b9f8  jz      loc_18004BCF5
0x18004b9fe  mov     edx, 1AFh
0x18004ba03  mov     r9d, edi
0x18004ba06  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004ba0d  mov     rcx, [rcx+10h]
0x18004ba11  call    WPP_SF_d
0x18004ba16  jmp     loc_18004BCF5
0x18004ba1b  lea     rax, [rsp+2B0h+var_250]
0x18004ba20  mov     rcx, 0FFFFFFFF80000002h
0x18004ba27  lea     r9, [rsp+2B0h+var_270]
0x18004ba2c  mov     [rsp+2B0h+var_290], rax
0x18004ba31  lea     r8, aCloudresources; "CloudResources"
0x18004ba38  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18004ba3f  call    cs:__imp_FwRegQueryString
0x18004ba46  nop     dword ptr [rax+rax+00h]
0x18004ba4b  cmp     [rsp+2B0h+var_250], 0
0x18004ba50  mov     ebx, eax
0x18004ba52  jnz     short loc_18004BA9C
0x18004ba54  lea     r8, [rsp+2B0h+var_268]
0x18004ba59  lea     rdx, aEnterpriseclou; "EnterpriseCloudResources"
0x18004ba60  lea     rcx, aNetworkisolati_32; "NetworkIsolation"
0x18004ba67  call    cs:__imp_PolicyManager_GetPolicyString
0x18004ba6e  nop     dword ptr [rax+rax+00h]
0x18004ba73  mov     rcx, [rsp+2B0h+var_268]
0x18004ba78  lea     rdx, [rsp+2B0h+var_270]
0x18004ba7d  call    cs:__imp_FwStringCopy
0x18004ba84  nop     dword ptr [rax+rax+00h]
0x18004ba89  mov     rcx, [rsp+2B0h+var_268]
0x18004ba8e  mov     ebx, eax
0x18004ba90  call    cs:__imp_PolicyManager_FreeStringValue
0x18004ba97  nop     dword ptr [rax+rax+00h]
0x18004ba9c  cmp     [rsp+2B0h+var_270], 0
0x18004baa2  jnz     short loc_18004BAAB
0x18004baa4  xor     edi, edi
0x18004baa6  jmp     loc_18004BCF5
0x18004baab  mov     ecx, ebx
0x18004baad  call    cs:__imp_FwHResultToWindowsError
0x18004bab4  nop     dword ptr [rax+rax+00h]
0x18004bab9  mov     edi, eax
0x18004babb  test    eax, eax
0x18004babd  jz      short loc_18004BAED
0x18004babf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bac6  lea     rbx, WPP_GLOBAL_Control
0x18004bacd  cmp     rcx, rbx
0x18004bad0  jz      loc_18004BCF5
0x18004bad6  test    byte ptr [rcx+1Ch], 1
0x18004bada  jz      loc_18004BCF5
0x18004bae0  mov     edx, 1B0h
0x18004bae5  mov     r9d, eax
0x18004bae8  jmp     loc_18004BA06
0x18004baed  call    ?FwMoneisUnPlumbCloudResourceNrpt@@YAKXZ; FwMoneisUnPlumbCloudResourceNrpt(void)
0x18004baf2  lea     rbx, WPP_GLOBAL_Control
0x18004baf9  mov     edi, eax
0x18004bafb  lea     rsi, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004bb02  cmp     eax, 2
0x18004bb05  jnz     short loc_18004BB75
0x18004bb07  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb0e  cmp     rcx, rbx
0x18004bb11  jz      short loc_18004BB2A
0x18004bb13  test    byte ptr [rcx+1Ch], 4
0x18004bb17  jz      short loc_18004BB2A
0x18004bb19  mov     rcx, [rcx+10h]
0x18004bb1d  mov     edx, 1B1h
0x18004bb22  mov     r8, rsi
0x18004bb25  call    WPP_SF_
0x18004bb2a  mov     rcx, [rsp+2B0h+var_270]
0x18004bb2f  lea     rdx, [rsp+2B0h+var_258]
0x18004bb34  call    cs:__imp_FwStringCopy
0x18004bb3b  nop     dword ptr [rax+rax+00h]
0x18004bb40  mov     ecx, eax
0x18004bb42  call    cs:__imp_FwHResultToWindowsError
0x18004bb49  nop     dword ptr [rax+rax+00h]
0x18004bb4e  mov     edi, eax
0x18004bb50  test    eax, eax
0x18004bb52  jz      short loc_18004BBA3
0x18004bb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb5b  cmp     rcx, rbx
0x18004bb5e  jz      loc_18004BCF5
0x18004bb64  test    byte ptr [rcx+1Ch], 1
0x18004bb68  jz      loc_18004BCF5
0x18004bb6e  mov     edx, 1B3h
0x18004bb73  jmp     short loc_18004BB98
0x18004bb75  test    eax, eax
0x18004bb77  jz      short loc_18004BB2A
0x18004bb79  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb80  cmp     rcx, rbx
0x18004bb83  jz      loc_18004BCF5
0x18004bb89  test    byte ptr [rcx+1Ch], 1
0x18004bb8d  jz      loc_18004BCF5
0x18004bb93  mov     edx, 1B2h
0x18004bb98  mov     r9d, eax
0x18004bb9b  mov     r8, rsi
0x18004bb9e  jmp     loc_18004BA0D
0x18004bba3  mov     rcx, [rsp+2B0h+var_258]
0x18004bba8  lea     r9, [rsp+2B0h+var_24C]
0x18004bbad  lea     r8, [rsp+2B0h+var_260]
0x18004bbb2  xor     edx, edx
0x18004bbb4  call    cs:__imp_FwParseEdpCloudResourceStringToNrptRuleList
0x18004bbbb  nop     dword ptr [rax+rax+00h]
0x18004bbc0  mov     edi, eax
0x18004bbc2  test    eax, eax
0x18004bbc4  jz      short loc_18004BBE7
0x18004bbc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbcd  cmp     rcx, rbx
0x18004bbd0  jz      loc_18004BCF5
0x18004bbd6  test    byte ptr [rcx+1Ch], 1
0x18004bbda  jz      loc_18004BCF5
0x18004bbe0  mov     edx, 1B4h
0x18004bbe5  jmp     short loc_18004BB98
0x18004bbe7  mov     edx, [rsp+2B0h+var_24C]
0x18004bbeb  mov     rcx, [rsp+2B0h+var_260]
0x18004bbf0  call    RasAddNrptRules
0x18004bbf5  lea     rcx, ModuleName; "ntdll.dll"
0x18004bbfc  call    cs:__imp_GetModuleHandleW
0x18004bc03  nop     dword ptr [rax+rax+00h]
0x18004bc08  mov     rcx, rax; hModule
0x18004bc0b  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18004bc12  call    cs:__imp_GetProcAddress
0x18004bc19  nop     dword ptr [rax+rax+00h]
0x18004bc1e  test    rax, rax
0x18004bc21  jz      short loc_18004BC8B
0x18004bc23  mov     [rsp+2B0h+var_280], 0
0x18004bc2c  lea     rcx, [rsp+2B0h+var_240]
0x18004bc31  mov     [rsp+2B0h+var_288], 208h
0x18004bc39  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x18004bc40  mov     [rsp+2B0h+var_290], rcx
0x18004bc45  lea     rdx, aTargetpath; "TargetPath"
0x18004bc4c  lea     rcx, aDnscache; "Dnscache"
0x18004bc53  xor     r9d, r9d
0x18004bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc5b  mov     ecx, eax; Status
0x18004bc5d  call    cs:__imp_RtlNtStatusToDosError
0x18004bc64  nop     dword ptr [rax+rax+00h]
0x18004bc69  mov     edi, eax
0x18004bc6b  test    eax, eax
0x18004bc6d  jz      short loc_18004BC8B
0x18004bc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc76  cmp     rcx, rbx
0x18004bc79  jz      short loc_18004BCF5
0x18004bc7b  test    byte ptr [rcx+1Ch], 1
0x18004bc7f  jz      short loc_18004BCF5
0x18004bc81  mov     edx, 1B5h
0x18004bc86  jmp     loc_18004BB98
0x18004bc8b  lea     r8, aParameters; "\\Parameters"
0x18004bc92  mov     edx, 104h
0x18004bc97  lea     rcx, [rsp+2B0h+var_240]
0x18004bc9c  call    cs:__imp__o_wcscat_s
0x18004bca3  nop     dword ptr [rax+rax+00h]
0x18004bca8  test    eax, eax
0x18004bcaa  jz      short loc_18004BCD0
0x18004bcac  mov     edi, 57h ; 'W'
0x18004bcb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bcb8  cmp     rcx, rbx
0x18004bcbb  jz      short loc_18004BCF5
0x18004bcbd  test    byte ptr [rcx+1Ch], 1
0x18004bcc1  jz      short loc_18004BCF5
0x18004bcc3  mov     edx, 1B6h
0x18004bcc8  mov     r9d, edi
0x18004bccb  jmp     loc_18004BB9B
0x18004bcd0  mov     r9d, 1
0x18004bcd6  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x18004bcdd  lea     rdx, [rsp+2B0h+var_240]
0x18004bce2  mov     rcx, 0FFFFFFFF80000002h
0x18004bce9  call    cs:__imp_FwRegSetDWord
0x18004bcf0  nop     dword ptr [rax+rax+00h]
0x18004bcf5  mov     rcx, [rsp+2B0h+var_270]
0x18004bcfa  call    cs:__imp_FwBaseFree
0x18004bd01  nop     dword ptr [rax+rax+00h]
0x18004bd06  mov     rsi, [rsp+2B0h+var_260]
0x18004bd0b  test    rsi, rsi
0x18004bd0e  jz      short loc_18004BD4A
0x18004bd10  mov     rcx, [rsi+28h]
0x18004bd14  call    cs:__imp_FwBaseFree
0x18004bd1b  nop     dword ptr [rax+rax+00h]
0x18004bd20  mov     rcx, [rsi+38h]
0x18004bd24  call    cs:__imp_FwBaseFree
0x18004bd2b  nop     dword ptr [rax+rax+00h]
0x18004bd30  mov     rbx, [rsi]
0x18004bd33  mov     rcx, rsi
0x18004bd36  call    cs:__imp_FwBaseFree
0x18004bd3d  nop     dword ptr [rax+rax+00h]
0x18004bd42  mov     rsi, rbx
0x18004bd45  test    rbx, rbx
0x18004bd48  jnz     short loc_18004BD10
0x18004bd4a  xor     ecx, ecx
0x18004bd4c  call    cs:__imp_FwBaseFree
0x18004bd53  nop     dword ptr [rax+rax+00h]
0x18004bd58  mov     rcx, [rsp+2B0h+var_258]
0x18004bd5d  call    cs:__imp_FwBaseFree
0x18004bd64  nop     dword ptr [rax+rax+00h]
0x18004bd69  mov     eax, edi
0x18004bd6b  mov     rcx, [rbp+1B0h+var_30]
0x18004bd72  xor     rcx, rsp; StackCookie
0x18004bd75  call    __security_check_cookie
0x18004bd7a  add     rsp, 298h
0x18004bd81  pop     rdi
0x18004bd82  pop     rsi
0x18004bd83  pop     rbx
0x18004bd84  pop     rbp
0x18004bd85  retn
```
