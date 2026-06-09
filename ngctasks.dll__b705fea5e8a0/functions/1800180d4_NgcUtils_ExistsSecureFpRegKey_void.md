# NgcUtils::ExistsSecureFpRegKey(void)

- ea: `0x1800180d4`
- end: `0x18001845a`
- name: `?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ`
- size: `902`
- prototype: `char __fastcall(NgcUtils *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800189d4`

## callees

- `0x1800024a8`
- `0x180006330`
- `0x180013be0`
- `0x1800171d4`
- `0x180017488`
- `0x1800180d4`
- `0x180018d20`
- `0x18001aa44`
- `0x18001aaa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018321`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001836e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001837e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018321`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001836e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001837e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018306`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018306`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001829d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001829d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180018401`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001843a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180018401`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001843a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180018208`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180018208`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180018171`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180018171`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180018352`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180018352`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18001824d`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18001824d`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800181ac`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800181ac`

## string_xrefs

- `0x180018216`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180018264`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x1800182b1`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180018410`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x18001814e`: `Configurations`

## pseudocode

```c
char __fastcall NgcUtils::ExistsSecureFpRegKey(NgcUtils *this)
{
  __int64 DeviceInfoList; // rcx
  const char *v2; // r9
  __int64 v3; // rdx
  char v4; // bl
  unsigned int v5; // edi
  __int64 i; // r9
  __int64 v7; // rdx
  const char *v8; // r9
  const char *v9; // r9
  const WCHAR *v10; // rax
  HKEY v11; // r10
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  char v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 *v20; // [rsp+68h] [rbp-98h]
  char v21; // [rsp+70h] [rbp-90h]
  HKEY *p_hkey; // [rsp+78h] [rbp-88h]
  HKEY *v23; // [rsp+80h] [rbp-80h]
  char v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[32]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v26[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v27[3]; // [rsp+D0h] [rbp-30h] BYREF
  char *v28; // [rsp+120h] [rbp+20h]
  __int64 v29; // [rsp+128h] [rbp+28h]
  HKEY *v30; // [rsp+130h] [rbp+30h]
  __int64 v31; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v15 = -1;
  v20 = &v15;
  v21 = 1;
  memset(v26, 0, sizeof(v26));
  memset(v27, 0, sizeof(v27));
  std::wstring::wstring(v25, L"WinBio");
  std::wstring::_Append<unsigned short>(v25, L"\\", 1);
  std::wstring::_Append<unsigned short>(v25, L"Configurations", 14);
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v15 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v3 = 748;
    goto LABEL_30;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16, 0, 0) )
  {
    v3 = 764;
LABEL_30:
    wil::details::in1diag3::Log_GetLastError(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      v2);
    std::wstring::_Tidy_deallocate((__int64)v25);
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      ((void (*)(void))DevObjDestroyDeviceInfoList)();
    return 0;
  }
  v4 = 0;
  v5 = 0;
  LODWORD(v26[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v15, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i, v26); i = v5 )
  {
    v7 = v5++;
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    p_hkey = &hkey;
    v23 = &hKey;
    v24 = 1;
    LODWORD(v27[0]) = 48;
    if ( (unsigned int)DevObjEnumDeviceInfo(v15, v7, v27) )
    {
      hKey = (HKEY)DevObjOpenDevRegKey(v15, v27, 1);
      if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)0x32D,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
          v9);
      }
      else
      {
        v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
        if ( RegOpenKeyExW(v11, v10, 0, 0x20019u, &hkey) )
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
            v4 = 1;
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
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x320,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
        v8);
    }
    if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  if ( (unsigned int)dword_180031038 > 4 )
  {
    hKey = (HKEY)v5;
    v14 = v4;
    v30 = &hKey;
    v31 = 8;
    v28 = &v14;
    v29 = 1;
    tlgWriteTransfer_EventWriteTransfer(&dword_180031038, &word_180029A3E);
  }
  std::wstring::_Tidy_deallocate((__int64)v25);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList(v15);
  return v4;
}

```

## disassembly

```asm
0x1800180d4  push    rbp
0x1800180d6  push    rbx
0x1800180d7  push    rsi
0x1800180d8  push    rdi
0x1800180d9  lea     rbp, [rsp-58h]
0x1800180de  sub     rsp, 158h
0x1800180e5  mov     rax, cs:__security_cookie
0x1800180ec  xor     rax, rsp
0x1800180ef  mov     [rbp+70h+var_30], rax
0x1800180f3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800180f7  mov     [rsp+170h+var_128], rsi
0x1800180fc  lea     rax, [rsp+170h+var_128]
0x180018101  mov     [rsp+170h+var_108], rax
0x180018106  mov     [rsp+170h+var_100], 1
0x18001810b  xorps   xmm0, xmm0
0x18001810e  movups  [rbp+70h+var_C0], xmm0
0x180018112  movups  [rbp+70h+var_B0], xmm0
0x180018116  xorps   xmm1, xmm1
0x180018119  movups  [rbp+70h+var_A0], xmm1
0x18001811d  movups  [rbp+70h+var_90], xmm1
0x180018121  movups  [rbp+70h+var_80], xmm1
0x180018125  lea     rdx, aWinbio; "WinBio"
0x18001812c  lea     rcx, [rbp+70h+var_E0]
0x180018130  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180018135  nop
0x180018136  lea     r8d, [rsi+2]
0x18001813a  lea     rdx, asc_180024838; "\\"
0x180018141  lea     rcx, [rbp+70h+var_E0]
0x180018145  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001814a  lea     r8d, [rsi+0Fh]
0x18001814e  lea     rdx, aConfigurations; "Configurations"
0x180018155  lea     rcx, [rbp+70h+var_E0]
0x180018159  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001815e  mov     [rsp+170h+phkResult], 0
0x180018167  xor     r9d, r9d
0x18001816a  xor     r8d, r8d
0x18001816d  xor     edx, edx
0x18001816f  xor     ecx, ecx
0x180018171  call    cs:__imp_DevObjCreateDeviceInfoList
0x180018177  mov     rcx, rax
0x18001817a  mov     [rsp+170h+var_128], rax
0x18001817f  dec     rax
0x180018182  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018186  ja      loc_18001840B
0x18001818c  mov     [rsp+170h+pvData], 0
0x180018195  mov     [rsp+170h+phkResult], 0
0x18001819e  lea     r9d, [rsi+11h]
0x1800181a2  xor     r8d, r8d
0x1800181a5  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x1800181ac  call    cs:__imp_DevObjGetClassDevs
0x1800181b2  test    eax, eax
0x1800181b4  jnz     short loc_1800181C0
0x1800181b6  mov     edx, 2FCh
0x1800181bb  jmp     loc_180018410
0x1800181c0  xor     bl, bl
0x1800181c2  xor     edi, edi
0x1800181c4  mov     dword ptr [rbp+70h+var_C0], 20h ; ' '
0x1800181cb  xor     r9d, r9d
0x1800181ce  jmp     loc_18001833B
0x1800181d3  mov     edx, edi
0x1800181d5  inc     edi
0x1800181d7  mov     [rsp+170h+hKey], rsi
0x1800181dc  mov     [rsp+170h+hkey], rsi
0x1800181e1  lea     rax, [rsp+170h+hkey]
0x1800181e6  mov     [rsp+170h+var_F8], rax
0x1800181eb  lea     rax, [rsp+170h+hKey]
0x1800181f0  mov     [rbp+70h+var_F0], rax
0x1800181f4  mov     [rbp+70h+var_E8], 1
0x1800181f8  mov     dword ptr [rbp+70h+var_A0], 30h ; '0'
0x1800181ff  lea     r8, [rbp+70h+var_A0]
0x180018203  mov     rcx, [rsp+170h+var_128]
0x180018208  call    cs:__imp_DevObjEnumDeviceInfo
0x18001820e  test    eax, eax
0x180018210  jnz     short loc_18001822D
0x180018212  mov     rcx, [rbp+78h]; this
0x180018216  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18001821d  mov     edx, 320h; void *
0x180018222  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180018227  nop
0x180018228  jmp     loc_180018317
0x18001822d  mov     dword ptr [rsp+170h+pvData], 20019h
0x180018235  mov     dword ptr [rsp+170h+phkResult], 1
0x18001823d  xor     r9d, r9d
0x180018240  lea     r8d, [r9+1]
0x180018244  lea     rdx, [rbp+70h+var_A0]
0x180018248  mov     rcx, [rsp+170h+var_128]
0x18001824d  call    cs:__imp_DevObjOpenDevRegKey
0x180018253  mov     r10, rax
0x180018256  mov     [rsp+170h+hKey], rax
0x18001825b  cmp     rax, rsi
0x18001825e  jnz     short loc_18001827B
0x180018260  mov     rcx, [rbp+78h]; this
0x180018264  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18001826b  mov     edx, 32Dh; void *
0x180018270  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180018275  nop
0x180018276  jmp     loc_180018317
0x18001827b  lea     rcx, [rbp+70h+var_E0]
0x18001827f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018284  mov     rdx, rax; lpSubKey
0x180018287  lea     rax, [rsp+170h+hkey]
0x18001828c  mov     [rsp+170h+phkResult], rax; unsigned int
0x180018291  mov     r9d, 20019h; samDesired
0x180018297  xor     r8d, r8d; ulOptions
0x18001829a  mov     rcx, r10; hKey
0x18001829d  call    cs:__imp_RegOpenKeyExW
0x1800182a3  test    eax, eax
0x1800182a5  jz      short loc_1800182C5
0x1800182a7  mov     rcx, [rbp+78h]; this
0x1800182ab  mov     r9d, 3F3h; char *
0x1800182b1  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800182b8  mov     edx, 338h; void *
0x1800182bd  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800182c2  nop
0x1800182c3  jmp     short loc_180018317
0x1800182c5  mov     [rsp+170h+var_110], 0
0x1800182cd  mov     [rsp+170h+var_10C], 4
0x1800182d5  lea     rax, [rsp+170h+var_10C]
0x1800182da  mov     [rsp+170h+pcbData], rax; pcbData
0x1800182df  lea     rax, [rsp+170h+var_110]
0x1800182e4  mov     [rsp+170h+pvData], rax; pvData
0x1800182e9  mov     [rsp+170h+phkResult], 0; pdwType
0x1800182f2  mov     r9d, 18h; dwFlags
0x1800182f8  lea     r8, aSecurefingerpr; "SecureFingerprint"
0x1800182ff  xor     edx, edx; lpSubKey
0x180018301  mov     rcx, [rsp+170h+hkey]; hkey
0x180018306  call    cs:__imp_RegGetValueW
0x18001830c  test    eax, eax
0x18001830e  jnz     short loc_180018317
0x180018310  cmp     [rsp+170h+var_110], 1
0x180018315  jz      short loc_180018362
0x180018317  mov     rcx, [rsp+170h+hkey]; hKey
0x18001831c  cmp     rcx, rsi
0x18001831f  jz      short loc_180018327
0x180018321  call    cs:__imp_RegCloseKey
0x180018327  mov     rcx, [rsp+170h+hKey]; hKey
0x18001832c  cmp     rcx, rsi
0x18001832f  jz      short loc_180018338
0x180018331  call    cs:__imp_RegCloseKey
0x180018337  nop
0x180018338  mov     r9d, edi
0x18001833b  lea     rax, [rbp+70h+var_C0]
0x18001833f  mov     [rsp+170h+phkResult], rax
0x180018344  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x18001834b  xor     edx, edx
0x18001834d  mov     rcx, [rsp+170h+var_128]
0x180018352  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180018358  test    eax, eax
0x18001835a  jnz     loc_1800181D3
0x180018360  jmp     short loc_180018385
0x180018362  mov     bl, 1
0x180018364  mov     rcx, [rsp+170h+hkey]; hKey
0x180018369  cmp     rcx, rsi
0x18001836c  jz      short loc_180018374
0x18001836e  call    cs:__imp_RegCloseKey
0x180018374  mov     rcx, [rsp+170h+hKey]; hKey
0x180018379  cmp     rcx, rsi
0x18001837c  jz      short loc_180018385
0x18001837e  call    cs:__imp_RegCloseKey
0x180018384  nop
0x180018385  mov     eax, cs:dword_180031038
0x18001838b  cmp     eax, 4
0x18001838e  jbe     short loc_1800183E8
0x180018390  mov     eax, edi
0x180018392  mov     [rsp+170h+hKey], rax
0x180018397  mov     [rsp+170h+var_130], bl
0x18001839b  lea     rax, [rsp+170h+hKey]
0x1800183a0  mov     [rbp+70h+var_40], rax
0x1800183a4  mov     [rbp+70h+var_38], 8
0x1800183ac  lea     rax, [rsp+170h+var_130]
0x1800183b1  mov     [rbp+70h+var_50], rax
0x1800183b5  mov     [rbp+70h+var_48], 1
0x1800183bd  lea     rax, [rbp+70h+var_70]
0x1800183c1  mov     [rsp+170h+pvData], rax
0x1800183c6  mov     dword ptr [rsp+170h+phkResult], 4
0x1800183ce  xor     r9d, r9d
0x1800183d1  xor     r8d, r8d
0x1800183d4  lea     rdx, word_180029A3E
0x1800183db  lea     rcx, dword_180031038
0x1800183e2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800183e7  nop
0x1800183e8  lea     rcx, [rbp+70h+var_E0]
0x1800183ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800183f1  nop
0x1800183f2  mov     rcx, [rsp+170h+var_128]
0x1800183f7  lea     rdx, [rcx-1]
0x1800183fb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800183ff  ja      short loc_180018407
0x180018401  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180018407  mov     al, bl
0x180018409  jmp     short loc_180018442
0x18001840b  mov     edx, 2ECh; void *
0x180018410  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180018417  mov     rcx, [rbp+78h]; this
0x18001841b  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180018420  nop
0x180018421  lea     rcx, [rbp+70h+var_E0]
0x180018425  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001842a  nop
0x18001842b  mov     rcx, [rsp+170h+var_128]
0x180018430  lea     rax, [rcx-1]
0x180018434  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018438  ja      short loc_180018440
0x18001843a  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180018440  xor     al, al
0x180018442  mov     rcx, [rbp+70h+var_30]
0x180018446  xor     rcx, rsp; StackCookie
0x180018449  call    __security_check_cookie
0x18001844e  add     rsp, 158h
0x180018455  pop     rdi
0x180018456  pop     rsi
0x180018457  pop     rbx
0x180018458  pop     rbp
0x180018459  retn
```
