# int_ReadActiveDeviceTunnelRegistryContent(ushort * *,ushort * *,void * *)

- ea: `0x1800d849c`
- end: `0x1800d8caa`
- name: `?int_ReadActiveDeviceTunnelRegistryContent@@YAKPEAPEAG0PEAPEAX@Z`
- size: `2062`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, void **)`
- caller_count: `2`
- callee_count: `12`
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
- `0x1800d849c`
- `0x1800de5f8`
- `0x1800e3ca0`
- `0x1800e3fac`
- `0x1800e427c`
- `0x1800e4534`
- `0x1800e8ef0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d851d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d851d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8a1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d8556`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d8556`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d8bc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d8bc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8666`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8794`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d88b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d895b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8666`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d8794`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d88b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d895b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8aaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8bfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8aaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8bfe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d8a0a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d8a0a`

## string_xrefs

- `0x1800d8529`: `SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800d8538`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800d88a2`: `UserSID`
- `0x1800d8954`: `UserSID`
- `0x1800d8a56`: `ConvertStringSidToSid`
- `0x1800d8838`: `VpnStringCopy for profile name`
- `0x1800d8a9f`: `VpnSidCopy`
- `0x1800d85a2`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d883f`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d8bab`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d8658`: `AutoTriggerProfilePhoneBookPath`
- `0x1800d8598`: `RegOpenKeyEx`
- `0x1800d870d`: `VpnStringCopy for profile path`
- `0x1800d8761`: `FixAutoTriggerProfilePath`

## pseudocode

```c
__int64 __fastcall int_ReadActiveDeviceTunnelRegistryContent(LPVOID *a1, unsigned __int16 **a2, void **a3)
{
  struct _LIST_ENTRY *v5; // rcx
  unsigned __int16 *v6; // r15
  char IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  BYTE *v11; // r14
  const char *v12; // rdx
  __int64 v13; // r8
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  struct _LIST_ENTRY *v17; // rcx
  int v18; // edi
  int v19; // eax
  int v20; // edx
  unsigned int fixed; // eax
  int v22; // eax
  struct _LIST_ENTRY *v23; // rcx
  int v24; // edi
  int v25; // eax
  int v26; // edx
  LSTATUS v27; // eax
  unsigned int v28; // eax
  DWORD LastError; // eax
  unsigned int v30; // eax
  void *v31; // rdi
  void **v32; // rax
  const char *v33; // rdx
  PSID v34; // rcx
  __int64 v35; // r8
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  LPVOID v38; // [rsp+38h] [rbp-41h] BYREF
  DWORD Type; // [rsp+40h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-31h] BYREF
  PSID Sid; // [rsp+50h] [rbp-29h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-21h]
  LPVOID v43; // [rsp+60h] [rbp-19h]
  void **v44; // [rsp+68h] [rbp-11h]
  _BYTE v45[16]; // [rsp+70h] [rbp-9h] BYREF
  LPVOID *v46; // [rsp+80h] [rbp+7h]
  __int64 v47; // [rsp+88h] [rbp+Fh]

  v44 = a3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 144, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  hKey = 0;
  v6 = 0;
  cbData = 0;
  Type = 0;
  Sid = 0;
  lpMem = 0;
  v43 = 0;
  v38 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v5);
  v8 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
  if ( !IsStateSeparationEnabled )
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x2001Fu, &hKey);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 145, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v9);
    }
    v11 = 0;
    v12 = "RegOpenKeyEx";
LABEL_11:
    v13 = v10;
LABEL_12:
    VpnReportError("int_ReadActiveDeviceTunnelRegistryContent", v12, v13);
    goto LABEL_104;
  }
  cbData = 522;
  v11 = (BYTE *)VpnAlloc(522);
  if ( !v11 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 146, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
      v14 = WPP_GLOBAL_Control;
    }
    v10 = 14;
    if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v14[1].Blink) & 1) == 0 )
      goto LABEL_104;
    v15 = 147;
    goto LABEL_21;
  }
  cbData = 520;
  v10 = RegQueryValueExW(hKey, L"AutoTriggerProfilePhoneBookPath", 0, &Type, v11, &cbData);
  if ( v10 || Type - 1 > 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 148, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1168);
    }
    v10 = 1168;
LABEL_102:
    v33 = "RegQueryValueEx";
LABEL_103:
    VpnReportError("int_ReadActiveDeviceTunnelRegistryContent", v33, 1168);
    goto LABEL_104;
  }
  *(_WORD *)&v11[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v16 = VpnStringCopy(v11);
  v17 = WPP_GLOBAL_Control;
  v18 = v16;
  if ( v16 >= 0
    || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
  {
    if ( v16 >= 0 )
      goto LABEL_36;
  }
  else
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 149, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v16);
    v17 = WPP_GLOBAL_Control;
  }
  v19 = (v18 >> 16) & 0x1FFF;
  if ( v19 == 7 )
    v20 = (unsigned __int16)v18;
  else
    v20 = v18;
  if ( v20 )
  {
    v12 = "VpnStringCopy for profile path";
    if ( v19 == 7 )
      v18 = (unsigned __int16)v18;
    v13 = (unsigned int)v18;
    goto LABEL_12;
  }
LABEL_36:
  if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v17[1].Blink) & 4) != 0 )
    WPP_SF_S(v17[1].Flink, 150, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, lpMem);
  fixed = FixAutoTriggerProfilePath(hKey);
  v10 = fixed;
  if ( fixed )
  {
    v13 = fixed;
    v12 = "FixAutoTriggerProfilePath";
    goto LABEL_12;
  }
  cbData = 520;
  v10 = RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, v11, &cbData);
  if ( v10 || Type - 1 > 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 151, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1168);
    }
    v10 = 1168;
    v33 = "RegQueryValueEx for REG_VAL_PROFILE_NAME";
    goto LABEL_103;
  }
  *(_WORD *)&v11[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v22 = VpnStringCopy(v11);
  v23 = WPP_GLOBAL_Control;
  v24 = v22;
  if ( v22 >= 0
    || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
  {
    if ( v22 >= 0 )
      goto LABEL_55;
  }
  else
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 152, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v22);
    v23 = WPP_GLOBAL_Control;
  }
  v25 = (v24 >> 16) & 0x1FFF;
  if ( v25 == 7 )
    v26 = (unsigned __int16)v24;
  else
    v26 = v24;
  if ( v26 )
  {
    if ( v25 == 7 )
      v24 = (unsigned __int16)v24;
    VpnReportError("int_ReadActiveDeviceTunnelRegistryContent", "VpnStringCopy for profile name", (unsigned int)v24);
    v6 = (unsigned __int16 *)v43;
    goto LABEL_104;
  }
LABEL_55:
  v6 = (unsigned __int16 *)v43;
  if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
    WPP_SF_S(v23[1].Flink, 153, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v43);
  cbData = 520;
  v27 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v11, &cbData);
  if ( v27 != 234 )
  {
    if ( !v27 && Type - 1 <= 1 )
      goto LABEL_74;
    v10 = 1168;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 157, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1168);
    }
    goto LABEL_102;
  }
  MprCommonFree(v11);
  v11 = (BYTE *)VpnAlloc(cbData + 1);
  if ( v11 )
  {
    v28 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v11, &cbData);
    v10 = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 156, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v28);
      }
      v13 = v10;
      goto LABEL_71;
    }
LABEL_74:
    if ( cbData > 1 )
    {
      *(_WORD *)&v11[2 * ((unsigned __int64)cbData >> 1)] = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 158, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v11);
      }
      if ( ConvertStringSidToSidW((LPCWSTR)v11, &Sid) )
      {
        v30 = VpnSidCopy(Sid);
        v10 = v30;
        if ( v30 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 160, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v30);
          }
          v12 = "VpnSidCopy";
          goto LABEL_11;
        }
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 159, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
          }
          v12 = "ConvertStringSidToSid";
          goto LABEL_11;
        }
      }
      LocalFree(Sid);
      v31 = v38;
      *a1 = lpMem;
      v32 = v44;
      *a2 = v6;
      Sid = 0;
      *v32 = v31;
      goto LABEL_105;
    }
    v10 = 1168;
    v13 = 1168;
LABEL_71:
    v12 = "RegQueryValueEx";
    goto LABEL_12;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 154, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
    v14 = WPP_GLOBAL_Control;
  }
  v10 = 14;
  if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v14[1].Blink) & 1) == 0 )
    goto LABEL_104;
  v15 = 155;
LABEL_21:
  WPP_SF_d(v14[1].Flink, v15, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
LABEL_104:
  v31 = v38;
LABEL_105:
  if ( hKey )
    RegCloseKey(hKey);
  MprCommonFree(v11);
  if ( v10 )
  {
    MprCommonFree(lpMem);
    MprCommonFree(v6);
    MprCommonFree(v31);
    v34 = Sid;
    if ( Sid )
    {
      LocalFree(Sid);
      Sid = 0;
    }
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    LODWORD(v38) = v10;
    v46 = &v38;
    v47 = 4;
    McGenEventWrite_EventWriteTransfer(v34, VpnAutoTriggerReadConfigRegistryContent, v35, 2, v45);
  }
  g_fConfigDeviceRegContentFailed = v10 != 0;
  if ( (v10 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 161, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1800d849c  mov     [rsp-8+arg_18], rbx
0x1800d84a1  push    rbp
0x1800d84a2  push    rsi
0x1800d84a3  push    rdi
0x1800d84a4  push    r12
0x1800d84a6  push    r13
0x1800d84a8  push    r14
0x1800d84aa  push    r15
0x1800d84ac  lea     rbp, [rsp-27h]
0x1800d84b1  sub     rsp, 0A0h
0x1800d84b8  mov     rax, cs:__security_cookie
0x1800d84bf  xor     rax, rsp
0x1800d84c2  mov     [rbp+57h+var_40], rax
0x1800d84c6  mov     [rbp+57h+var_68], r8
0x1800d84ca  mov     r13, rdx
0x1800d84cd  mov     r12, rcx
0x1800d84d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d84d7  lea     rsi, WPP_GLOBAL_Control
0x1800d84de  cmp     rcx, rsi
0x1800d84e1  jz      short loc_1800D84FE
0x1800d84e3  test    byte ptr [rcx+1Ch], 8
0x1800d84e7  jz      short loc_1800D84FE
0x1800d84e9  mov     rcx, [rcx+10h]
0x1800d84ed  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d84f4  mov     edx, 90h
0x1800d84f9  call    WPP_SF_
0x1800d84fe  xor     edi, edi
0x1800d8500  mov     [rbp+57h+hKey], rdi
0x1800d8504  mov     r15d, edi
0x1800d8507  mov     [rbp+57h+cbData], edi
0x1800d850a  mov     [rbp+57h+Type], edi
0x1800d850d  mov     [rbp+57h+Sid], rdi
0x1800d8511  mov     [rbp+57h+lpMem], rdi
0x1800d8515  mov     [rbp+57h+var_70], rdi
0x1800d8519  mov     [rbp+57h+var_98], rdi
0x1800d851d  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800d8524  nop     dword ptr [rax+rax+00h]
0x1800d8529  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800d8530  mov     r9d, 2001Fh; samDesired
0x1800d8536  test    al, al
0x1800d8538  lea     rdx, aOsdataSystemCu_1; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800d853f  lea     rax, [rbp+57h+hKey]
0x1800d8543  cmovz   rdx, rcx; lpSubKey
0x1800d8547  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800d854c  xor     r8d, r8d; ulOptions
0x1800d854f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d8556  call    cs:__imp_RegOpenKeyExW
0x1800d855d  nop     dword ptr [rax+rax+00h]
0x1800d8562  mov     ebx, eax
0x1800d8564  test    eax, eax
0x1800d8566  jz      short loc_1800D85BA
0x1800d8568  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d856f  cmp     rcx, rsi
0x1800d8572  jz      short loc_1800D8595
0x1800d8574  lea     esi, [rdi+1]
0x1800d8577  test    [rcx+1Ch], sil
0x1800d857b  jz      short loc_1800D8595
0x1800d857d  mov     rcx, [rcx+10h]
0x1800d8581  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8588  mov     edx, 91h
0x1800d858d  mov     r9d, eax
0x1800d8590  call    WPP_SF_d
0x1800d8595  mov     r14, rdi
0x1800d8598  lea     rdx, aRegopenkeyex; "RegOpenKeyEx"
0x1800d859f  mov     r8d, ebx
0x1800d85a2  lea     rcx, aIntReadactived; "int_ReadActiveDeviceTunnelRegistryConte"...
0x1800d85a9  call    VpnReportError
0x1800d85ae  lea     r12, WPP_GLOBAL_Control
0x1800d85b5  jmp     loc_1800D8BB7
0x1800d85ba  mov     ecx, 20Ah
0x1800d85bf  mov     [rbp+57h+cbData], ecx
0x1800d85c2  call    VpnAlloc
0x1800d85c7  mov     r14, rax
0x1800d85ca  test    rax, rax
0x1800d85cd  jnz     short loc_1800D863F
0x1800d85cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d85d6  lea     r12, WPP_GLOBAL_Control
0x1800d85dd  lea     esi, [rax+1]
0x1800d85e0  lea     edi, [rax+0Eh]
0x1800d85e3  cmp     rcx, r12
0x1800d85e6  jz      short loc_1800D860D
0x1800d85e8  test    [rcx+1Ch], sil
0x1800d85ec  jz      short loc_1800D860D
0x1800d85ee  mov     rcx, [rcx+10h]
0x1800d85f2  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d85f9  mov     edx, 92h
0x1800d85fe  mov     r9d, edi
0x1800d8601  call    WPP_SF_d
0x1800d8606  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d860d  mov     ebx, edi
0x1800d860f  cmp     rcx, r12
0x1800d8612  jz      loc_1800D8BB7
0x1800d8618  test    [rcx+1Ch], sil
0x1800d861c  jz      loc_1800D8BB7
0x1800d8622  mov     edx, 93h
0x1800d8627  mov     rcx, [rcx+10h]
0x1800d862b  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8632  mov     r9d, edi
0x1800d8635  call    WPP_SF_d
0x1800d863a  jmp     loc_1800D8BB7
0x1800d863f  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d8643  lea     rax, [rbp+57h+cbData]
0x1800d8647  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800d864c  lea     r9, [rbp+57h+Type]; lpType
0x1800d8650  xor     r8d, r8d; lpReserved
0x1800d8653  mov     [rsp+0D0h+phkResult], r14; lpData
0x1800d8658  lea     rdx, aAutotriggerpro_0; "AutoTriggerProfilePhoneBookPath"
0x1800d865f  mov     [rbp+57h+cbData], 208h
0x1800d8666  call    cs:__imp_RegQueryValueExW
0x1800d866d  nop     dword ptr [rax+rax+00h]
0x1800d8672  mov     ebx, eax
0x1800d8674  mov     esi, 1
0x1800d8679  test    eax, eax
0x1800d867b  jnz     loc_1800D8B69
0x1800d8681  mov     eax, [rbp+57h+Type]
0x1800d8684  dec     eax
0x1800d8686  cmp     eax, esi
0x1800d8688  ja      loc_1800D8B69
0x1800d868e  mov     ecx, [rbp+57h+cbData]
0x1800d8691  lea     rdx, [rbp+57h+lpMem]
0x1800d8695  shr     rcx, 1
0x1800d8698  mov     [r14+rcx*2], di
0x1800d869d  mov     rcx, r14; Src
0x1800d86a0  call    VpnStringCopy
0x1800d86a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d86ac  mov     edi, eax
0x1800d86ae  test    eax, eax
0x1800d86b0  jns     short loc_1800D86E5
0x1800d86b2  lea     rax, WPP_GLOBAL_Control
0x1800d86b9  cmp     rcx, rax
0x1800d86bc  jz      short loc_1800D86E5
0x1800d86be  test    [rcx+1Ch], sil
0x1800d86c2  jz      short loc_1800D86E5
0x1800d86c4  mov     rcx, [rcx+10h]
0x1800d86c8  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d86cf  mov     edx, 95h
0x1800d86d4  mov     r9d, edi
0x1800d86d7  call    WPP_SF_d
0x1800d86dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d86e3  jmp     short loc_1800D86E9
0x1800d86e5  test    edi, edi
0x1800d86e7  jns     short loc_1800D8720
0x1800d86e9  mov     eax, edi
0x1800d86eb  sar     eax, 10h
0x1800d86ee  and     eax, 1FFFh
0x1800d86f3  cmp     eax, 7
0x1800d86f6  jnz     short loc_1800D8700
0x1800d86f8  movzx   edx, di
0x1800d86fb  mov     r8d, edx
0x1800d86fe  jmp     short loc_1800D8706
0x1800d8700  mov     edx, edi
0x1800d8702  movzx   r8d, di
0x1800d8706  test    edx, edx
0x1800d8708  jz      short loc_1800D8720
0x1800d870a  cmp     eax, 7
0x1800d870d  lea     rdx, aVpnstringcopyF_2; "VpnStringCopy for profile path"
0x1800d8714  cmovz   edi, r8d
0x1800d8718  mov     r8d, edi
0x1800d871b  jmp     loc_1800D85A2
0x1800d8720  lea     rax, WPP_GLOBAL_Control
0x1800d8727  cmp     rcx, rax
0x1800d872a  jz      short loc_1800D874B
0x1800d872c  test    byte ptr [rcx+1Ch], 4
0x1800d8730  jz      short loc_1800D874B
0x1800d8732  mov     r9, [rbp+57h+lpMem]
0x1800d8736  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d873d  mov     rcx, [rcx+10h]
0x1800d8741  mov     edx, 96h
0x1800d8746  call    WPP_SF_S
0x1800d874b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d874f  lea     rdx, [rbp+57h+lpMem]
0x1800d8753  call    FixAutoTriggerProfilePath
0x1800d8758  mov     ebx, eax
0x1800d875a  test    eax, eax
0x1800d875c  jz      short loc_1800D876D
0x1800d875e  mov     r8d, eax
0x1800d8761  lea     rdx, aFixautotrigger; "FixAutoTriggerProfilePath"
0x1800d8768  jmp     loc_1800D85A2
0x1800d876d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d8771  lea     rax, [rbp+57h+cbData]
0x1800d8775  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800d877a  lea     r9, [rbp+57h+Type]; lpType
0x1800d877e  xor     r8d, r8d; lpReserved
0x1800d8781  mov     [rsp+0D0h+phkResult], r14; lpData
0x1800d8786  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x1800d878d  mov     [rbp+57h+cbData], 208h
0x1800d8794  call    cs:__imp_RegQueryValueExW
0x1800d879b  nop     dword ptr [rax+rax+00h]
0x1800d87a0  mov     ebx, eax
0x1800d87a2  test    eax, eax
0x1800d87a4  jnz     loc_1800D8B28
0x1800d87aa  mov     eax, [rbp+57h+Type]
0x1800d87ad  dec     eax
0x1800d87af  cmp     eax, esi
0x1800d87b1  ja      loc_1800D8B28
0x1800d87b7  mov     ecx, [rbp+57h+cbData]
0x1800d87ba  lea     rdx, [rbp+57h+var_70]
0x1800d87be  shr     rcx, 1
0x1800d87c1  xor     eax, eax
0x1800d87c3  mov     [r14+rcx*2], ax
0x1800d87c8  mov     rcx, r14; Src
0x1800d87cb  call    VpnStringCopy
0x1800d87d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d87d7  mov     edi, eax
0x1800d87d9  test    eax, eax
0x1800d87db  jns     short loc_1800D8810
0x1800d87dd  lea     rax, WPP_GLOBAL_Control
0x1800d87e4  cmp     rcx, rax
0x1800d87e7  jz      short loc_1800D8810
0x1800d87e9  test    [rcx+1Ch], sil
0x1800d87ed  jz      short loc_1800D8810
0x1800d87ef  mov     rcx, [rcx+10h]
0x1800d87f3  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d87fa  mov     edx, 98h
0x1800d87ff  mov     r9d, edi
0x1800d8802  call    WPP_SF_d
0x1800d8807  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d880e  jmp     short loc_1800D8814
0x1800d8810  test    edi, edi
0x1800d8812  jns     short loc_1800D885B
0x1800d8814  mov     eax, edi
0x1800d8816  sar     eax, 10h
0x1800d8819  and     eax, 1FFFh
0x1800d881e  cmp     eax, 7
0x1800d8821  jnz     short loc_1800D882B
0x1800d8823  movzx   edx, di
0x1800d8826  mov     r8d, edx
0x1800d8829  jmp     short loc_1800D8831
0x1800d882b  mov     edx, edi
0x1800d882d  movzx   r8d, di
0x1800d8831  test    edx, edx
0x1800d8833  jz      short loc_1800D885B
0x1800d8835  cmp     eax, 7
0x1800d8838  lea     rdx, aVpnstringcopyF_0; "VpnStringCopy for profile name"
0x1800d883f  lea     rcx, aIntReadactived; "int_ReadActiveDeviceTunnelRegistryConte"...
0x1800d8846  cmovz   edi, r8d
0x1800d884a  mov     r8d, edi
0x1800d884d  call    VpnReportError
0x1800d8852  mov     r15, [rbp+57h+var_70]
0x1800d8856  jmp     loc_1800D85AE
0x1800d885b  mov     r15, [rbp+57h+var_70]
0x1800d885f  lea     rdi, WPP_GLOBAL_Control
0x1800d8866  cmp     rcx, rdi
0x1800d8869  jz      short loc_1800D8889
0x1800d886b  test    byte ptr [rcx+1Ch], 4
0x1800d886f  jz      short loc_1800D8889
0x1800d8871  mov     rcx, [rcx+10h]
0x1800d8875  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d887c  mov     edx, 99h
0x1800d8881  mov     r9, r15
0x1800d8884  call    WPP_SF_S
0x1800d8889  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d888d  lea     rax, [rbp+57h+cbData]
0x1800d8891  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800d8896  lea     r9, [rbp+57h+Type]; lpType
0x1800d889a  xor     r8d, r8d; lpReserved
0x1800d889d  mov     [rsp+0D0h+phkResult], r14; lpData
0x1800d88a2  lea     rdx, aUsersid; "UserSID"
0x1800d88a9  mov     [rbp+57h+cbData], 208h
0x1800d88b0  call    cs:__imp_RegQueryValueExW
0x1800d88b7  nop     dword ptr [rax+rax+00h]
0x1800d88bc  cmp     eax, 0EAh
0x1800d88c1  jnz     loc_1800D89A6
0x1800d88c7  mov     rcx, r14; lpMem
0x1800d88ca  call    MprCommonFree
0x1800d88cf  mov     ecx, [rbp+57h+cbData]
0x1800d88d2  inc     ecx
0x1800d88d4  call    VpnAlloc
0x1800d88d9  mov     r14, rax
0x1800d88dc  test    rax, rax
0x1800d88df  jnz     short loc_1800D893B
0x1800d88e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d88e8  lea     r12, WPP_GLOBAL_Control
0x1800d88ef  lea     edi, [rax+0Eh]
0x1800d88f2  cmp     rcx, r12
0x1800d88f5  jz      short loc_1800D891C
0x1800d88f7  test    [rcx+1Ch], sil
0x1800d88fb  jz      short loc_1800D891C
0x1800d88fd  mov     rcx, [rcx+10h]
0x1800d8901  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8908  mov     edx, 9Ah
0x1800d890d  mov     r9d, edi
0x1800d8910  call    WPP_SF_d
0x1800d8915  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d891c  mov     ebx, edi
0x1800d891e  cmp     rcx, r12
0x1800d8921  jz      loc_1800D8BB7
0x1800d8927  test    [rcx+1Ch], sil
0x1800d892b  jz      loc_1800D8BB7
0x1800d8931  mov     edx, 9Bh
0x1800d8936  jmp     loc_1800D8627
0x1800d893b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d893f  lea     rax, [rbp+57h+cbData]
0x1800d8943  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800d8948  lea     r9, [rbp+57h+Type]; lpType
0x1800d894c  xor     r8d, r8d; lpReserved
0x1800d894f  mov     [rsp+0D0h+phkResult], r14; lpData
0x1800d8954  lea     rdx, aUsersid; "UserSID"
0x1800d895b  call    cs:__imp_RegQueryValueExW
0x1800d8962  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
