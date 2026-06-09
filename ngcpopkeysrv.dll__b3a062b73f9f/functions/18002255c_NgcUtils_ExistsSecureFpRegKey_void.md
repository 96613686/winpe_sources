# NgcUtils::ExistsSecureFpRegKey(void)

- ea: `0x18002255c`
- end: `0x1800228e3`
- name: `?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ`
- size: `903`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022af0`

## callees

- `0x180001248`
- `0x180004de0`
- `0x1800106cc`
- `0x180013754`
- `0x180014ba4`
- `0x180014f80`
- `0x18002255c`
- `0x180022d08`
- `0x180022d28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022794`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022794`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002272b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002272b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002280c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800227fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002280c`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800226e2`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800226e2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800225f9`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800225f9`
- `DEVOBJ!DevObjGetClassDevs` at `0x180022634`
- `DEVOBJ!DevObjGetClassDevs` at `0x180022634`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800227e0`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800227e0`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002288f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800228c2`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002288f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800228c2`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800226a4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800226a4`

## string_xrefs

- `0x1800225d6`: `Configurations`
- `0x18002273f`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall NgcUtils::ExistsSecureFpRegKey(NgcUtils *this)
{
  __int64 DeviceInfoList; // rcx
  unsigned int v2; // r8d
  const char *v3; // r9
  unsigned int v4; // r8d
  const char *v5; // r9
  char v6; // bl
  unsigned int v7; // edi
  __int64 i; // r9
  __int64 v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  unsigned int v12; // r8d
  const char *v13; // r9
  const WCHAR *v14; // rax
  HKEY v15; // r10
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  char v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 *v25; // [rsp+68h] [rbp-98h]
  char v26; // [rsp+70h] [rbp-90h]
  HKEY *p_hkey; // [rsp+78h] [rbp-88h]
  HKEY *v28; // [rsp+80h] [rbp-80h]
  char v29; // [rsp+88h] [rbp-78h]
  _BYTE v30[32]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v31[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v32[3]; // [rsp+D0h] [rbp-30h] BYREF
  char v33[32]; // [rsp+100h] [rbp+0h] BYREF
  char *v34; // [rsp+120h] [rbp+20h]
  __int64 v35; // [rsp+128h] [rbp+28h]
  HKEY *v36; // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v20 = -1;
  v25 = &v20;
  v26 = 1;
  memset(v31, 0, sizeof(v31));
  memset(v32, 0, sizeof(v32));
  std::wstring::wstring(v30, L"WinBio");
  std::wstring::_Append<unsigned short>(v30, L"\\", 1);
  std::wstring::_Append<unsigned short>(v30, L"Configurations", 14);
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v20 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x2EC, v2, v3);
    std::wstring::_Tidy_deallocate(v30);
    goto LABEL_30;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16, 0, 0) )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x2FC, v4, v5);
    std::wstring::_Tidy_deallocate(v30);
LABEL_30:
    if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      DevObjDestroyDeviceInfoList();
    return 0;
  }
  v6 = 0;
  v7 = 0;
  LODWORD(v31[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v20, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i, v31); i = v7 )
  {
    v9 = v7++;
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    p_hkey = &hkey;
    v28 = &hKey;
    v29 = 1;
    LODWORD(v32[0]) = 48;
    if ( (unsigned int)DevObjEnumDeviceInfo(v20, v9, v32) )
    {
      hKey = (HKEY)DevObjOpenDevRegKey(v20, v32, 1);
      if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x32D, v12, v13);
      }
      else
      {
        v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
        if ( RegOpenKeyExW(v15, v14, 0, 0x20019u, &hkey) )
        {
          wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)0x338,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
            (const char *)0x3F3,
            phkResult);
        }
        else
        {
          pvData = 0;
          pcbData = 4;
          if ( !RegGetValueW(hkey, 0, L"SecureFingerprint", 0x18u, 0, &pvData, &pcbData) && pvData == 1 )
          {
            v6 = 1;
            if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
              RegCloseKey(hkey);
            if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
              RegCloseKey(hKey);
            break;
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x320, v10, v11);
    }
    if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  if ( (unsigned int)dword_180037000 > 4 )
  {
    hKey = (HKEY)v7;
    v19 = v6;
    v36 = &hKey;
    v37 = 8;
    v34 = &v19;
    v35 = 1;
    LODWORD(phkResulta) = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180037000, &unk_18002F0E0, 0, 0, phkResulta, v33);
  }
  std::wstring::_Tidy_deallocate(v30);
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList();
  return v6;
}

```

## disassembly

```asm
0x18002255c  push    rbp
0x18002255e  push    rbx
0x18002255f  push    rsi
0x180022560  push    rdi
0x180022561  lea     rbp, [rsp-58h]
0x180022566  sub     rsp, 158h
0x18002256d  mov     rax, cs:__security_cookie
0x180022574  xor     rax, rsp
0x180022577  mov     [rbp+70h+var_30], rax
0x18002257b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002257f  mov     [rsp+170h+var_128], rsi
0x180022584  lea     rax, [rsp+170h+var_128]
0x180022589  mov     [rsp+170h+var_108], rax
0x18002258e  mov     [rsp+170h+var_100], 1
0x180022593  xorps   xmm0, xmm0
0x180022596  movups  [rbp+70h+var_C0], xmm0
0x18002259a  movups  [rbp+70h+var_B0], xmm0
0x18002259e  xorps   xmm1, xmm1
0x1800225a1  movups  [rbp+70h+var_A0], xmm1
0x1800225a5  movups  [rbp+70h+var_90], xmm1
0x1800225a9  movups  [rbp+70h+var_80], xmm1
0x1800225ad  lea     rdx, aWinbio; "WinBio"
0x1800225b4  lea     rcx, [rbp+70h+var_E0]
0x1800225b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800225bd  nop
0x1800225be  lea     r8d, [rsi+2]
0x1800225c2  lea     rdx, asc_18002A2B8; "\\"
0x1800225c9  lea     rcx, [rbp+70h+var_E0]
0x1800225cd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800225d2  lea     r8d, [rsi+0Fh]
0x1800225d6  lea     rdx, aConfigurations; "Configurations"
0x1800225dd  lea     rcx, [rbp+70h+var_E0]
0x1800225e1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800225e6  mov     [rsp+170h+phkResult], 0
0x1800225ef  xor     r9d, r9d
0x1800225f2  xor     r8d, r8d
0x1800225f5  xor     edx, edx
0x1800225f7  xor     ecx, ecx
0x1800225f9  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800225ff  mov     rcx, rax
0x180022602  mov     [rsp+170h+var_128], rax
0x180022607  dec     rax
0x18002260a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002260e  ja      loc_18002289A
0x180022614  mov     [rsp+170h+pvData], 0
0x18002261d  mov     [rsp+170h+phkResult], 0
0x180022626  lea     r9d, [rsi+11h]
0x18002262a  xor     r8d, r8d
0x18002262d  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180022634  call    cs:__imp_DevObjGetClassDevs
0x18002263a  test    eax, eax
0x18002263c  jnz     short loc_18002265C
0x18002263e  mov     rcx, [rbp+78h]; this
0x180022642  mov     edx, 2FCh; void *
0x180022647  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18002264c  nop
0x18002264d  lea     rcx, [rbp+70h+var_E0]
0x180022651  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022656  nop
0x180022657  jmp     loc_1800228B3
0x18002265c  xor     bl, bl
0x18002265e  xor     edi, edi
0x180022660  mov     dword ptr [rbp+70h+var_C0], 20h ; ' '
0x180022667  xor     r9d, r9d
0x18002266a  jmp     loc_1800227C9
0x18002266f  mov     edx, edi
0x180022671  inc     edi
0x180022673  mov     [rsp+170h+hKey], rsi
0x180022678  mov     [rsp+170h+hkey], rsi
0x18002267d  lea     rax, [rsp+170h+hkey]
0x180022682  mov     [rsp+170h+var_F8], rax
0x180022687  lea     rax, [rsp+170h+hKey]
0x18002268c  mov     [rbp+70h+var_F0], rax
0x180022690  mov     [rbp+70h+var_E8], 1
0x180022694  mov     dword ptr [rbp+70h+var_A0], 30h ; '0'
0x18002269b  lea     r8, [rbp+70h+var_A0]
0x18002269f  mov     rcx, [rsp+170h+var_128]
0x1800226a4  call    cs:__imp_DevObjEnumDeviceInfo
0x1800226aa  test    eax, eax
0x1800226ac  jnz     short loc_1800226C2
0x1800226ae  mov     rcx, [rbp+78h]; this
0x1800226b2  mov     edx, 320h; void *
0x1800226b7  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800226bc  nop
0x1800226bd  jmp     loc_1800227A5
0x1800226c2  mov     dword ptr [rsp+170h+pvData], 20019h
0x1800226ca  mov     dword ptr [rsp+170h+phkResult], 1
0x1800226d2  xor     r9d, r9d
0x1800226d5  lea     r8d, [r9+1]
0x1800226d9  lea     rdx, [rbp+70h+var_A0]
0x1800226dd  mov     rcx, [rsp+170h+var_128]
0x1800226e2  call    cs:__imp_DevObjOpenDevRegKey
0x1800226e8  mov     r10, rax
0x1800226eb  mov     [rsp+170h+hKey], rax
0x1800226f0  cmp     rax, rsi
0x1800226f3  jnz     short loc_180022709
0x1800226f5  mov     rcx, [rbp+78h]; this
0x1800226f9  mov     edx, 32Dh; void *
0x1800226fe  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180022703  nop
0x180022704  jmp     loc_1800227A5
0x180022709  lea     rcx, [rbp+70h+var_E0]
0x18002270d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022712  mov     rdx, rax; lpSubKey
0x180022715  lea     rax, [rsp+170h+hkey]
0x18002271a  mov     [rsp+170h+phkResult], rax; unsigned int
0x18002271f  mov     r9d, 20019h; samDesired
0x180022725  xor     r8d, r8d; ulOptions
0x180022728  mov     rcx, r10; hKey
0x18002272b  call    cs:__imp_RegOpenKeyExW
0x180022731  test    eax, eax
0x180022733  jz      short loc_180022753
0x180022735  mov     rcx, [rbp+78h]; this
0x180022739  mov     r9d, 3F3h; char *
0x18002273f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180022746  mov     edx, 338h; void *
0x18002274b  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180022750  nop
0x180022751  jmp     short loc_1800227A5
0x180022753  mov     [rsp+170h+var_110], 0
0x18002275b  mov     [rsp+170h+var_10C], 4
0x180022763  lea     rax, [rsp+170h+var_10C]
0x180022768  mov     [rsp+170h+pcbData], rax; pcbData
0x18002276d  lea     rax, [rsp+170h+var_110]
0x180022772  mov     [rsp+170h+pvData], rax; pvData
0x180022777  mov     [rsp+170h+phkResult], 0; pdwType
0x180022780  mov     r9d, 18h; dwFlags
0x180022786  lea     r8, Value; "SecureFingerprint"
0x18002278d  xor     edx, edx; lpSubKey
0x18002278f  mov     rcx, [rsp+170h+hkey]; hkey
0x180022794  call    cs:__imp_RegGetValueW
0x18002279a  test    eax, eax
0x18002279c  jnz     short loc_1800227A5
0x18002279e  cmp     [rsp+170h+var_110], 1
0x1800227a3  jz      short loc_1800227F0
0x1800227a5  mov     rcx, [rsp+170h+hkey]; hKey
0x1800227aa  cmp     rcx, rsi
0x1800227ad  jz      short loc_1800227B5
0x1800227af  call    cs:__imp_RegCloseKey
0x1800227b5  mov     rcx, [rsp+170h+hKey]; hKey
0x1800227ba  cmp     rcx, rsi
0x1800227bd  jz      short loc_1800227C6
0x1800227bf  call    cs:__imp_RegCloseKey
0x1800227c5  nop
0x1800227c6  mov     r9d, edi
0x1800227c9  lea     rax, [rbp+70h+var_C0]
0x1800227cd  mov     [rsp+170h+phkResult], rax
0x1800227d2  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x1800227d9  xor     edx, edx
0x1800227db  mov     rcx, [rsp+170h+var_128]
0x1800227e0  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800227e6  test    eax, eax
0x1800227e8  jnz     loc_18002266F
0x1800227ee  jmp     short loc_180022813
0x1800227f0  mov     bl, 1
0x1800227f2  mov     rcx, [rsp+170h+hkey]; hKey
0x1800227f7  cmp     rcx, rsi
0x1800227fa  jz      short loc_180022802
0x1800227fc  call    cs:__imp_RegCloseKey
0x180022802  mov     rcx, [rsp+170h+hKey]; hKey
0x180022807  cmp     rcx, rsi
0x18002280a  jz      short loc_180022813
0x18002280c  call    cs:__imp_RegCloseKey
0x180022812  nop
0x180022813  mov     eax, cs:dword_180037000
0x180022819  cmp     eax, 4
0x18002281c  jbe     short loc_180022876
0x18002281e  mov     eax, edi
0x180022820  mov     [rsp+170h+hKey], rax
0x180022825  mov     [rsp+170h+var_130], bl
0x180022829  lea     rax, [rsp+170h+hKey]
0x18002282e  mov     [rbp+70h+var_40], rax
0x180022832  mov     [rbp+70h+var_38], 8
0x18002283a  lea     rax, [rsp+170h+var_130]
0x18002283f  mov     [rbp+70h+var_50], rax
0x180022843  mov     [rbp+70h+var_48], 1
0x18002284b  lea     rax, [rbp+70h+var_70]
0x18002284f  mov     [rsp+170h+pvData], rax
0x180022854  mov     dword ptr [rsp+170h+phkResult], 4
0x18002285c  xor     r9d, r9d
0x18002285f  xor     r8d, r8d
0x180022862  lea     rdx, unk_18002F0E0
0x180022869  lea     rcx, dword_180037000
0x180022870  call    _tlgWriteTransfer_EventWriteTransfer
0x180022875  nop
0x180022876  lea     rcx, [rbp+70h+var_E0]
0x18002287a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002287f  nop
0x180022880  mov     rcx, [rsp+170h+var_128]
0x180022885  lea     rdx, [rcx-1]
0x180022889  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002288d  ja      short loc_180022896
0x18002288f  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180022895  nop
0x180022896  mov     al, bl
0x180022898  jmp     short loc_1800228CB
0x18002289a  mov     rcx, [rbp+78h]; this
0x18002289e  mov     edx, 2ECh; void *
0x1800228a3  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800228a8  nop
0x1800228a9  lea     rcx, [rbp+70h+var_E0]
0x1800228ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800228b2  nop
0x1800228b3  mov     rcx, [rsp+170h+var_128]
0x1800228b8  lea     rax, [rcx-1]
0x1800228bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800228c0  ja      short loc_1800228C9
0x1800228c2  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800228c8  nop
0x1800228c9  xor     al, al
0x1800228cb  mov     rcx, [rbp+70h+var_30]
0x1800228cf  xor     rcx, rsp; StackCookie
0x1800228d2  call    __security_check_cookie
0x1800228d7  add     rsp, 158h
0x1800228de  pop     rdi
0x1800228df  pop     rsi
0x1800228e0  pop     rbx
0x1800228e1  pop     rbp
0x1800228e2  retn
```
