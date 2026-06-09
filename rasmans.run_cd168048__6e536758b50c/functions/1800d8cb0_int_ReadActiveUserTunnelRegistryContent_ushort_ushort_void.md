# int_ReadActiveUserTunnelRegistryContent(ushort * *,ushort * *,void * *)

- ea: `0x1800d8cb0`
- end: `0x1800d9564`
- name: `?int_ReadActiveUserTunnelRegistryContent@@YAKPEAPEAG0PEAPEAX@Z`
- size: `2228`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, void **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cea20`
- `0x1800e0e34`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x1800ab634`
- `0x1800c6930`
- `0x1800d8cb0`
- `0x1800de5f8`
- `0x1800e2be4`
- `0x1800e3ca0`
- `0x1800e3fac`
- `0x1800e427c`
- `0x1800e4534`
- `0x1800e8ef0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d8d30`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d8dde`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d8d30`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d8dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d92b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d92b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d8d6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d8d6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d947d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d947d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8ec0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d90fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d91a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8ec0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8ff0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d90fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d91a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9363`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d94b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9363`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d94b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d92a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d92a6`

## string_xrefs

- `0x1800d8d3c`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800d8dff`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800d8d4b`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800d90ee`: `UserSID`
- `0x1800d919e`: `UserSID`
- `0x1800d9300`: `ConvertStringSidToSid`
- `0x1800d9094`: `VpnStringCopy for profile name`
- `0x1800d9353`: `VpnSidCopy`
- `0x1800d8eb2`: `AutoTriggerProfilePhoneBookPath`
- `0x1800d8dad`: `RegOpenKeyEx`
- `0x1800d8f69`: `VpnStringCopy for profile path`
- `0x1800d8fbd`: `FixAutoTriggerProfilePath`
- `0x1800d8db4`: `int_ReadActiveUserTunnelRegistryContent`
- `0x1800d9464`: `int_ReadActiveUserTunnelRegistryContent`

## pseudocode

```c
__int64 __fastcall int_ReadActiveUserTunnelRegistryContent(LPVOID *a1, unsigned __int16 **a2, void **a3)
{
  struct _LIST_ENTRY *v6; // rcx
  BYTE *v7; // r14
  char IsStateSeparationEnabled; // al
  const wchar_t *v9; // rbx
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // edi
  __int64 v14; // r8
  const char *v15; // rdx
  BYTE *v16; // rax
  struct _LIST_ENTRY *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  struct _LIST_ENTRY *v20; // rcx
  int v21; // ebx
  int v22; // eax
  int v23; // edx
  unsigned int fixed; // eax
  int v25; // eax
  struct _LIST_ENTRY *v26; // rcx
  int v27; // ebx
  int v28; // eax
  int v29; // edx
  unsigned __int16 *v30; // rbx
  LSTATUS v31; // eax
  unsigned int v32; // eax
  DWORD v33; // eax
  unsigned int v34; // eax
  void *v35; // rbx
  struct _LIST_ENTRY *v36; // rcx
  DWORD v37; // ebx
  DWORD LastError; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  PSID v41; // rcx
  __int64 v42; // r8
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  LPVOID v45; // [rsp+38h] [rbp-31h] BYREF
  DWORD Type; // [rsp+40h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  PSID Sid; // [rsp+50h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-11h]
  LPVOID v50; // [rsp+60h] [rbp-9h]
  _BYTE v51[16]; // [rsp+68h] [rbp-1h] BYREF
  LPVOID *v52; // [rsp+78h] [rbp+Fh]
  __int64 v53; // [rsp+80h] [rbp+17h]

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 124, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  v7 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  Sid = 0;
  lpMem = 0;
  v50 = 0;
  v45 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v6);
  v9 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  v10 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !IsStateSeparationEnabled )
    v10 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20017u, &hKey);
  v13 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 125, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v11);
    }
    v14 = v13;
    v15 = "RegOpenKeyEx";
    goto LABEL_110;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled(v12) )
      v9 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 126, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v9);
  }
  cbData = 522;
  v16 = (BYTE *)VpnAlloc(522);
  v7 = v16;
  if ( !v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
      v17 = WPP_GLOBAL_Control;
    }
    v13 = 14;
    if ( v17 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v17[1].Blink) & 1) == 0 )
      goto LABEL_111;
    v18 = 128;
    goto LABEL_23;
  }
  cbData = 520;
  v13 = RegQueryValueExW(hKey, L"AutoTriggerProfilePhoneBookPath", 0, &Type, v16, &cbData);
  if ( v13 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_104;
    }
    v37 = Type;
    LastError = GetLastError();
    WPP_SF_DDD(WPP_GLOBAL_Control[1].Flink, v39, v40, LastError, v37, v13);
LABEL_103:
    v36 = WPP_GLOBAL_Control;
LABEL_104:
    if ( v36 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v36[1].Blink) & 1) != 0 )
      WPP_SF_d(v36[1].Flink, 130, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1168);
    v13 = 1168;
    goto LABEL_108;
  }
  if ( Type - 1 > 1 )
    goto LABEL_103;
  *(_WORD *)&v7[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v19 = VpnStringCopy(v7);
  v20 = WPP_GLOBAL_Control;
  v21 = v19;
  if ( v19 >= 0
    || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
  {
    if ( v19 >= 0 )
      goto LABEL_38;
  }
  else
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 131, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v19);
    v20 = WPP_GLOBAL_Control;
  }
  v22 = (v21 >> 16) & 0x1FFF;
  if ( v22 == 7 )
    v23 = (unsigned __int16)v21;
  else
    v23 = v21;
  if ( v23 )
  {
    v15 = "VpnStringCopy for profile path";
    if ( v22 == 7 )
      v21 = (unsigned __int16)v21;
    v14 = (unsigned int)v21;
    goto LABEL_110;
  }
LABEL_38:
  if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v20[1].Blink) & 4) != 0 )
    WPP_SF_S(v20[1].Flink, 132, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, lpMem);
  fixed = FixAutoTriggerProfilePath(hKey);
  v13 = fixed;
  if ( fixed )
  {
    v14 = fixed;
    v15 = "FixAutoTriggerProfilePath";
    goto LABEL_110;
  }
  cbData = 520;
  v13 = RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, v7, &cbData);
  if ( v13 || Type - 1 > 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 133, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1168);
    }
    v13 = 1168;
    v15 = "RegQueryValueEx for REG_VAL_PROFILE_NAME";
    v14 = 1168;
    goto LABEL_110;
  }
  *(_WORD *)&v7[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v25 = VpnStringCopy(v7);
  v26 = WPP_GLOBAL_Control;
  v27 = v25;
  if ( v25 >= 0
    || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
  {
    if ( v25 >= 0 )
      goto LABEL_57;
  }
  else
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 134, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v25);
    v26 = WPP_GLOBAL_Control;
  }
  v28 = (v27 >> 16) & 0x1FFF;
  if ( v28 == 7 )
    v29 = (unsigned __int16)v27;
  else
    v29 = v27;
  if ( v29 )
  {
    v15 = "VpnStringCopy for profile name";
    if ( v28 == 7 )
      v27 = (unsigned __int16)v27;
    v14 = (unsigned int)v27;
    goto LABEL_110;
  }
LABEL_57:
  v30 = (unsigned __int16 *)v50;
  if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v26[1].Blink) & 4) != 0 )
    WPP_SF_S(v26[1].Flink, 135, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v50);
  cbData = 520;
  v31 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v7, &cbData);
  if ( v31 != 234 )
  {
    if ( !v31 && Type - 1 <= 1 )
      goto LABEL_78;
    v13 = 1168;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 139, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1168);
    }
LABEL_108:
    v14 = 1168;
LABEL_109:
    v15 = "RegQueryValueEx";
    goto LABEL_110;
  }
  MprCommonFree(v7);
  v7 = (BYTE *)VpnAlloc(cbData + 1);
  if ( v7 )
  {
    v32 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v7, &cbData);
    v13 = v32;
    if ( v32 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 138, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v32);
      }
      v14 = v13;
      goto LABEL_109;
    }
LABEL_78:
    if ( cbData > 1 )
    {
      *(_WORD *)&v7[2 * ((unsigned __int64)cbData >> 1)] = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 140, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v7);
      }
      if ( ConvertStringSidToSidW((LPCWSTR)v7, &Sid) )
      {
        v34 = VpnSidCopy(Sid);
        v13 = v34;
        if ( v34 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 142, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v34);
          }
          v14 = v13;
          v15 = "VpnSidCopy";
          goto LABEL_110;
        }
      }
      else
      {
        v33 = GetLastError();
        v13 = v33;
        if ( v33 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 141, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v33);
          }
          v14 = v13;
          v15 = "ConvertStringSidToSid";
          goto LABEL_110;
        }
      }
      LocalFree(Sid);
      *a1 = lpMem;
      *a2 = v30;
      v35 = v45;
      *a3 = v45;
      Sid = 0;
      goto LABEL_112;
    }
    v15 = "RegQueryValueEx";
    v13 = 1168;
    v14 = 1168;
LABEL_110:
    VpnReportError("int_ReadActiveUserTunnelRegistryContent", v15, v14);
    goto LABEL_111;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 136, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
    v17 = WPP_GLOBAL_Control;
  }
  v13 = 14;
  if ( v17 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v17[1].Blink) & 1) == 0 )
    goto LABEL_111;
  v18 = 137;
LABEL_23:
  WPP_SF_d(v17[1].Flink, v18, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
LABEL_111:
  v35 = v45;
LABEL_112:
  if ( hKey )
    RegCloseKey(hKey);
  MprCommonFree(v7);
  if ( v13 )
  {
    MprCommonFree(lpMem);
    MprCommonFree(v50);
    MprCommonFree(v35);
    v41 = Sid;
    if ( Sid )
    {
      LocalFree(Sid);
      Sid = 0;
    }
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    LODWORD(v45) = v13;
    v52 = &v45;
    v53 = 4;
    McGenEventWrite_EventWriteTransfer(v41, VpnAutoTriggerReadConfigRegistryContent, v42, 2, v51);
  }
  g_fConfigUserRegContentFailed = v13 != 0;
  if ( (v13 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 143, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x1800d8cb0  mov     [rsp-8+arg_18], rbx
0x1800d8cb5  push    rbp
0x1800d8cb6  push    rsi
0x1800d8cb7  push    rdi
0x1800d8cb8  push    r12
0x1800d8cba  push    r13
0x1800d8cbc  push    r14
0x1800d8cbe  push    r15
0x1800d8cc0  lea     rbp, [rsp-27h]
0x1800d8cc5  sub     rsp, 90h
0x1800d8ccc  mov     rax, cs:__security_cookie
0x1800d8cd3  xor     rax, rsp
0x1800d8cd6  mov     [rbp+57h+var_38], rax
0x1800d8cda  mov     r13, r8
0x1800d8cdd  mov     r12, rdx
0x1800d8ce0  mov     r15, rcx
0x1800d8ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8cea  lea     rsi, WPP_GLOBAL_Control
0x1800d8cf1  cmp     rcx, rsi
0x1800d8cf4  jz      short loc_1800D8D11
0x1800d8cf6  test    byte ptr [rcx+1Ch], 8
0x1800d8cfa  jz      short loc_1800D8D11
0x1800d8cfc  mov     rcx, [rcx+10h]
0x1800d8d00  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8d07  mov     edx, 7Ch ; '|'
0x1800d8d0c  call    WPP_SF_
0x1800d8d11  xor     r14d, r14d
0x1800d8d14  mov     [rbp+57h+hKey], r14
0x1800d8d18  mov     [rbp+57h+cbData], r14d
0x1800d8d1c  mov     [rbp+57h+Type], r14d
0x1800d8d20  mov     [rbp+57h+Sid], r14
0x1800d8d24  mov     [rbp+57h+lpMem], r14
0x1800d8d28  mov     [rbp+57h+var_60], r14
0x1800d8d2c  mov     [rbp+57h+var_88], r14
0x1800d8d30  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800d8d37  nop     dword ptr [rax+rax+00h]
0x1800d8d3c  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800d8d43  mov     r9d, 20017h; samDesired
0x1800d8d49  test    al, al
0x1800d8d4b  lea     rbx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800d8d52  lea     rax, [rbp+57h+hKey]
0x1800d8d56  mov     rdx, rbx
0x1800d8d59  cmovz   rdx, rcx; lpSubKey
0x1800d8d5d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800d8d62  xor     r8d, r8d; ulOptions
0x1800d8d65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d8d6c  call    cs:__imp_RegOpenKeyExW
0x1800d8d73  nop     dword ptr [rax+rax+00h]
0x1800d8d78  mov     edi, eax
0x1800d8d7a  test    eax, eax
0x1800d8d7c  jz      short loc_1800D8DCC
0x1800d8d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8d85  cmp     rcx, rsi
0x1800d8d88  jz      short loc_1800D8DAA
0x1800d8d8a  lea     esi, [r14+1]
0x1800d8d8e  test    [rcx+1Ch], sil
0x1800d8d92  jz      short loc_1800D8DAA
0x1800d8d94  mov     rcx, [rcx+10h]
0x1800d8d98  lea     edx, [rsi+7Ch]
0x1800d8d9b  mov     r9d, eax
0x1800d8d9e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8da5  call    WPP_SF_d
0x1800d8daa  mov     r8d, edi
0x1800d8dad  lea     rdx, aRegopenkeyex; "RegOpenKeyEx"
0x1800d8db4  lea     rcx, aIntReadactiveu; "int_ReadActiveUserTunnelRegistryContent"
0x1800d8dbb  call    VpnReportError
0x1800d8dc0  lea     r15, WPP_GLOBAL_Control
0x1800d8dc7  jmp     loc_1800D9470
0x1800d8dcc  mov     rax, cs:WPP_GLOBAL_Control
0x1800d8dd3  cmp     rax, rsi
0x1800d8dd6  jz      short loc_1800D8E16
0x1800d8dd8  test    byte ptr [rax+1Ch], 4
0x1800d8ddc  jz      short loc_1800D8E16
0x1800d8dde  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800d8de5  nop     dword ptr [rax+rax+00h]
0x1800d8dea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8df1  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8df8  test    al, al
0x1800d8dfa  mov     edx, 7Eh ; '~'
0x1800d8dff  lea     rax, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800d8e06  cmovz   rbx, rax
0x1800d8e0a  mov     rcx, [rcx+10h]
0x1800d8e0e  mov     r9, rbx
0x1800d8e11  call    WPP_SF_S
0x1800d8e16  mov     ecx, 20Ah
0x1800d8e1b  mov     [rbp+57h+cbData], ecx
0x1800d8e1e  call    VpnAlloc
0x1800d8e23  mov     r14, rax
0x1800d8e26  test    rax, rax
0x1800d8e29  jnz     short loc_1800D8E99
0x1800d8e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8e32  lea     r15, WPP_GLOBAL_Control
0x1800d8e39  lea     esi, [rax+1]
0x1800d8e3c  lea     ebx, [rax+0Eh]
0x1800d8e3f  cmp     rcx, r15
0x1800d8e42  jz      short loc_1800D8E67
0x1800d8e44  test    [rcx+1Ch], sil
0x1800d8e48  jz      short loc_1800D8E67
0x1800d8e4a  mov     rcx, [rcx+10h]
0x1800d8e4e  lea     edx, [rax+7Fh]
0x1800d8e51  mov     r9d, ebx
0x1800d8e54  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8e5b  call    WPP_SF_d
0x1800d8e60  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8e67  mov     edi, ebx
0x1800d8e69  cmp     rcx, r15
0x1800d8e6c  jz      loc_1800D9470
0x1800d8e72  test    [rcx+1Ch], sil
0x1800d8e76  jz      loc_1800D9470
0x1800d8e7c  mov     edx, 80h
0x1800d8e81  mov     rcx, [rcx+10h]
0x1800d8e85  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8e8c  mov     r9d, ebx
0x1800d8e8f  call    WPP_SF_d
0x1800d8e94  jmp     loc_1800D9470
0x1800d8e99  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d8e9d  lea     rax, [rbp+57h+cbData]
0x1800d8ea1  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1800d8ea6  lea     r9, [rbp+57h+Type]; lpType
0x1800d8eaa  xor     r8d, r8d; lpReserved
0x1800d8ead  mov     [rsp+0C0h+phkResult], r14; lpData
0x1800d8eb2  lea     rdx, aAutotriggerpro_0; "AutoTriggerProfilePhoneBookPath"
0x1800d8eb9  mov     [rbp+57h+cbData], 208h
0x1800d8ec0  call    cs:__imp_RegQueryValueExW
0x1800d8ec7  nop     dword ptr [rax+rax+00h]
0x1800d8ecc  mov     edi, eax
0x1800d8ece  mov     esi, 1
0x1800d8ed3  test    eax, eax
0x1800d8ed5  jnz     loc_1800D93E6
0x1800d8edb  mov     eax, [rbp+57h+Type]
0x1800d8ede  dec     eax
0x1800d8ee0  cmp     eax, esi
0x1800d8ee2  ja      loc_1800D93DD
0x1800d8ee8  mov     ecx, [rbp+57h+cbData]
0x1800d8eeb  lea     rdx, [rbp+57h+lpMem]
0x1800d8eef  shr     rcx, 1
0x1800d8ef2  xor     eax, eax
0x1800d8ef4  mov     [r14+rcx*2], ax
0x1800d8ef9  mov     rcx, r14; Src
0x1800d8efc  call    VpnStringCopy
0x1800d8f01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8f08  mov     ebx, eax
0x1800d8f0a  test    eax, eax
0x1800d8f0c  jns     short loc_1800D8F41
0x1800d8f0e  lea     rax, WPP_GLOBAL_Control
0x1800d8f15  cmp     rcx, rax
0x1800d8f18  jz      short loc_1800D8F41
0x1800d8f1a  test    [rcx+1Ch], sil
0x1800d8f1e  jz      short loc_1800D8F41
0x1800d8f20  mov     rcx, [rcx+10h]
0x1800d8f24  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8f2b  mov     edx, 83h
0x1800d8f30  mov     r9d, ebx
0x1800d8f33  call    WPP_SF_d
0x1800d8f38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8f3f  jmp     short loc_1800D8F45
0x1800d8f41  test    ebx, ebx
0x1800d8f43  jns     short loc_1800D8F7C
0x1800d8f45  mov     eax, ebx
0x1800d8f47  sar     eax, 10h
0x1800d8f4a  and     eax, 1FFFh
0x1800d8f4f  cmp     eax, 7
0x1800d8f52  jnz     short loc_1800D8F5C
0x1800d8f54  movzx   edx, bx
0x1800d8f57  mov     r8d, edx
0x1800d8f5a  jmp     short loc_1800D8F62
0x1800d8f5c  mov     edx, ebx
0x1800d8f5e  movzx   r8d, bx
0x1800d8f62  test    edx, edx
0x1800d8f64  jz      short loc_1800D8F7C
0x1800d8f66  cmp     eax, 7
0x1800d8f69  lea     rdx, aVpnstringcopyF_2; "VpnStringCopy for profile path"
0x1800d8f70  cmovz   ebx, r8d
0x1800d8f74  mov     r8d, ebx
0x1800d8f77  jmp     loc_1800D8DB4
0x1800d8f7c  lea     rax, WPP_GLOBAL_Control
0x1800d8f83  cmp     rcx, rax
0x1800d8f86  jz      short loc_1800D8FA7
0x1800d8f88  test    byte ptr [rcx+1Ch], 4
0x1800d8f8c  jz      short loc_1800D8FA7
0x1800d8f8e  mov     r9, [rbp+57h+lpMem]
0x1800d8f92  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8f99  mov     rcx, [rcx+10h]
0x1800d8f9d  mov     edx, 84h
0x1800d8fa2  call    WPP_SF_S
0x1800d8fa7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d8fab  lea     rdx, [rbp+57h+lpMem]
0x1800d8faf  call    FixAutoTriggerProfilePath
0x1800d8fb4  mov     edi, eax
0x1800d8fb6  test    eax, eax
0x1800d8fb8  jz      short loc_1800D8FC9
0x1800d8fba  mov     r8d, eax
0x1800d8fbd  lea     rdx, aFixautotrigger; "FixAutoTriggerProfilePath"
0x1800d8fc4  jmp     loc_1800D8DB4
0x1800d8fc9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d8fcd  lea     rax, [rbp+57h+cbData]
0x1800d8fd1  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1800d8fd6  lea     r9, [rbp+57h+Type]; lpType
0x1800d8fda  xor     r8d, r8d; lpReserved
0x1800d8fdd  mov     [rsp+0C0h+phkResult], r14; lpData
0x1800d8fe2  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x1800d8fe9  mov     [rbp+57h+cbData], 208h
0x1800d8ff0  call    cs:__imp_RegQueryValueExW
0x1800d8ff7  nop     dword ptr [rax+rax+00h]
0x1800d8ffc  mov     edi, eax
0x1800d8ffe  test    eax, eax
0x1800d9000  jnz     loc_1800D9396
0x1800d9006  mov     eax, [rbp+57h+Type]
0x1800d9009  dec     eax
0x1800d900b  cmp     eax, esi
0x1800d900d  ja      loc_1800D9396
0x1800d9013  mov     ecx, [rbp+57h+cbData]
0x1800d9016  lea     rdx, [rbp+57h+var_60]
0x1800d901a  shr     rcx, 1
0x1800d901d  xor     eax, eax
0x1800d901f  mov     [r14+rcx*2], ax
0x1800d9024  mov     rcx, r14; Src
0x1800d9027  call    VpnStringCopy
0x1800d902c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9033  mov     ebx, eax
0x1800d9035  test    eax, eax
0x1800d9037  jns     short loc_1800D906C
0x1800d9039  lea     rax, WPP_GLOBAL_Control
0x1800d9040  cmp     rcx, rax
0x1800d9043  jz      short loc_1800D906C
0x1800d9045  test    [rcx+1Ch], sil
0x1800d9049  jz      short loc_1800D906C
0x1800d904b  mov     rcx, [rcx+10h]
0x1800d904f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9056  mov     edx, 86h
0x1800d905b  mov     r9d, ebx
0x1800d905e  call    WPP_SF_d
0x1800d9063  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d906a  jmp     short loc_1800D9070
0x1800d906c  test    ebx, ebx
0x1800d906e  jns     short loc_1800D90A7
0x1800d9070  mov     eax, ebx
0x1800d9072  sar     eax, 10h
0x1800d9075  and     eax, 1FFFh
0x1800d907a  cmp     eax, 7
0x1800d907d  jnz     short loc_1800D9087
0x1800d907f  movzx   edx, bx
0x1800d9082  mov     r8d, edx
0x1800d9085  jmp     short loc_1800D908D
0x1800d9087  mov     edx, ebx
0x1800d9089  movzx   r8d, bx
0x1800d908d  test    edx, edx
0x1800d908f  jz      short loc_1800D90A7
0x1800d9091  cmp     eax, 7
0x1800d9094  lea     rdx, aVpnstringcopyF_0; "VpnStringCopy for profile name"
0x1800d909b  cmovz   ebx, r8d
0x1800d909f  mov     r8d, ebx
0x1800d90a2  jmp     loc_1800D8DB4
0x1800d90a7  mov     rbx, [rbp+57h+var_60]
0x1800d90ab  lea     rdi, WPP_GLOBAL_Control
0x1800d90b2  cmp     rcx, rdi
0x1800d90b5  jz      short loc_1800D90D5
0x1800d90b7  test    byte ptr [rcx+1Ch], 4
0x1800d90bb  jz      short loc_1800D90D5
0x1800d90bd  mov     rcx, [rcx+10h]
0x1800d90c1  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d90c8  mov     edx, 87h
0x1800d90cd  mov     r9, rbx
0x1800d90d0  call    WPP_SF_S
0x1800d90d5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d90d9  lea     rax, [rbp+57h+cbData]
0x1800d90dd  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1800d90e2  lea     r9, [rbp+57h+Type]; lpType
0x1800d90e6  xor     r8d, r8d; lpReserved
0x1800d90e9  mov     [rsp+0C0h+phkResult], r14; lpData
0x1800d90ee  lea     rdx, aUsersid; "UserSID"
0x1800d90f5  mov     [rbp+57h+cbData], 208h
0x1800d90fc  call    cs:__imp_RegQueryValueExW
0x1800d9103  nop     dword ptr [rax+rax+00h]
0x1800d9108  cmp     eax, 0EAh
0x1800d910d  jnz     loc_1800D91F4
0x1800d9113  mov     rcx, r14; lpMem
0x1800d9116  call    MprCommonFree
0x1800d911b  mov     ecx, [rbp+57h+cbData]
0x1800d911e  inc     ecx
0x1800d9120  call    VpnAlloc
0x1800d9125  mov     r14, rax
0x1800d9128  test    rax, rax
0x1800d912b  jnz     short loc_1800D9185
0x1800d912d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9134  lea     r15, WPP_GLOBAL_Control
0x1800d913b  lea     ebx, [rax+0Eh]
0x1800d913e  cmp     rcx, r15
0x1800d9141  jz      short loc_1800D9166
0x1800d9143  test    [rcx+1Ch], sil
0x1800d9147  jz      short loc_1800D9166
0x1800d9149  mov     rcx, [rcx+10h]
0x1800d914d  lea     edx, [rbx+7Ah]
0x1800d9150  mov     r9d, ebx
0x1800d9153  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d915a  call    WPP_SF_d
0x1800d915f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9166  mov     edi, ebx
0x1800d9168  cmp     rcx, r15
0x1800d916b  jz      loc_1800D9470
  ... truncated ...
```
