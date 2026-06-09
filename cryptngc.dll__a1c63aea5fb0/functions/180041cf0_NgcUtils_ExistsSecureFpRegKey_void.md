# NgcUtils::ExistsSecureFpRegKey(void)

- ea: `0x180041cf0`
- end: `0x180042040`
- name: `?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ`
- size: `848`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800420d4`

## callees

- `0x1800046e0`
- `0x18000edb0`
- `0x18000fc20`
- `0x180038e9c`
- `0x180041cf0`
- `0x1800422dc`
- `0x180042304`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041e94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041e94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041efc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f66`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180041d92`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180041d92`
- `DEVOBJ!DevObjGetClassDevs` at `0x180041dcd`
- `DEVOBJ!DevObjGetClassDevs` at `0x180041dcd`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180041f40`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180041f40`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180041fea`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004201e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180041fea`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004201e`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180041e59`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180041e59`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180041e0e`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180041e0e`

## string_xrefs

- `0x180041ea8`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180041d6e`: `Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall NgcUtils::ExistsSecureFpRegKey(NgcUtils *this)
{
  __int64 DeviceInfoList; // rcx
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 v4; // rdx
  char v5; // si
  unsigned int v6; // edi
  __int64 i; // r9
  __int64 v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rdx
  HKEY v12; // rcx
  HKEY v13; // rbx
  const WCHAR *v14; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  char v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+60h] [rbp-A0h]
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v24[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v25[3]; // [rsp+B0h] [rbp-50h] BYREF
  char v26[32]; // [rsp+E0h] [rbp-20h] BYREF
  char *v27; // [rsp+100h] [rbp+0h]
  __int64 v28; // [rsp+108h] [rbp+8h]
  HKEY *p_hkey; // [rsp+110h] [rbp+10h]
  __int64 v30; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v18 = -1;
  hkey = (HKEY)&v18;
  v21 = 1;
  memset(v24, 0, sizeof(v24));
  memset(v25, 0, sizeof(v25));
  std::wstring::wstring(lpSubKey, L"WinBio");
  std::wstring::_Append<unsigned short>(lpSubKey);
  std::wstring::_Append<unsigned short>(lpSubKey);
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v18 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = 748;
    goto LABEL_33;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 16, 0, 0) )
  {
    v4 = 764;
LABEL_33:
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v4, v2, v3);
    std::wstring::~wstring(lpSubKey);
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      DevObjDestroyDeviceInfoList();
    return 0;
  }
  v5 = 0;
  v6 = 0;
  LODWORD(v24[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v18, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i, v24); i = v6 )
  {
    v8 = v6++;
    hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    LODWORD(v25[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v18, v8, v25) )
    {
      v11 = 800;
      goto LABEL_7;
    }
    v13 = (HKEY)DevObjOpenDevRegKey(v18, v25, 1);
    if ( v13 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v11 = 813;
LABEL_7:
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v11, v9, v10);
      v12 = hkey;
      if ( hkey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        continue;
      goto LABEL_20;
    }
    v14 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v14 = lpSubKey[0];
    if ( RegOpenKeyExW(v13, v14, 0, 0x20019u, &hkey) )
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
        v5 = 1;
        if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          RegCloseKey(hkey);
        RegCloseKey(v13);
        break;
      }
    }
    if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
    v12 = v13;
LABEL_20:
    RegCloseKey(v12);
  }
  if ( (unsigned int)dword_18006E000 > 4 )
  {
    hkey = (HKEY)v6;
    v17 = v5;
    p_hkey = &hkey;
    v30 = 8;
    v27 = &v17;
    v28 = 1;
    tlgWriteTransfer_EventWriteTransfer(&dword_18006E000, &byte_180063307, 0, 0, 4, v26);
  }
  std::wstring::~wstring(lpSubKey);
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList();
  return v5;
}

```

## disassembly

```asm
0x180041cf0  push    rbp
0x180041cf2  push    rbx
0x180041cf3  push    rsi
0x180041cf4  push    rdi
0x180041cf5  push    r15
0x180041cf7  lea     rbp, [rsp-30h]
0x180041cfc  sub     rsp, 130h
0x180041d03  mov     rax, cs:__security_cookie
0x180041d0a  xor     rax, rsp
0x180041d0d  mov     [rbp+50h+var_30], rax
0x180041d11  or      r15, 0FFFFFFFFFFFFFFFFh
0x180041d15  mov     [rsp+150h+var_108], r15
0x180041d1a  lea     rax, [rsp+150h+var_108]
0x180041d1f  mov     [rsp+150h+hkey], rax
0x180041d24  mov     [rsp+150h+var_F0], 1
0x180041d29  xorps   xmm0, xmm0
0x180041d2c  movups  [rbp+50h+var_C0], xmm0
0x180041d30  movups  [rbp+50h+var_B0], xmm0
0x180041d34  xorps   xmm1, xmm1
0x180041d37  movups  [rbp+50h+var_A0], xmm1
0x180041d3b  movups  [rbp+50h+var_90], xmm1
0x180041d3f  movups  [rbp+50h+var_80], xmm1
0x180041d43  lea     rdx, aWinbio; "WinBio"
0x180041d4a  lea     rcx, [rsp+150h+lpSubKey]
0x180041d4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041d54  nop
0x180041d55  lea     r8d, [r15+2]
0x180041d59  lea     rdx, asc_180050E74; "\\"
0x180041d60  lea     rcx, [rsp+150h+lpSubKey]; Src
0x180041d65  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180041d6a  lea     r8d, [r15+0Fh]
0x180041d6e  lea     rdx, aConfigurations; "Configurations"
0x180041d75  lea     rcx, [rsp+150h+lpSubKey]; Src
0x180041d7a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180041d7f  mov     [rsp+150h+phkResult], 0
0x180041d88  xor     r9d, r9d
0x180041d8b  xor     r8d, r8d
0x180041d8e  xor     edx, edx
0x180041d90  xor     ecx, ecx
0x180041d92  call    cs:__imp_DevObjCreateDeviceInfoList
0x180041d98  mov     rcx, rax
0x180041d9b  mov     [rsp+150h+var_108], rax
0x180041da0  dec     rax
0x180041da3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041da7  ja      loc_180041FF5
0x180041dad  mov     [rsp+150h+pvData], 0
0x180041db6  mov     [rsp+150h+phkResult], 0
0x180041dbf  lea     r9d, [r15+11h]
0x180041dc3  xor     r8d, r8d
0x180041dc6  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180041dcd  call    cs:__imp_DevObjGetClassDevs
0x180041dd3  test    eax, eax
0x180041dd5  jnz     short loc_180041DE1
0x180041dd7  mov     edx, 2FCh
0x180041ddc  jmp     loc_180041FFA
0x180041de1  xor     sil, sil
0x180041de4  xor     edi, edi
0x180041de6  mov     dword ptr [rbp+50h+var_C0], 20h ; ' '
0x180041ded  xor     r9d, r9d
0x180041df0  jmp     loc_180041F29
0x180041df5  mov     edx, edi
0x180041df7  inc     edi
0x180041df9  mov     [rsp+150h+hkey], r15
0x180041dfe  mov     dword ptr [rbp+50h+var_A0], 30h ; '0'
0x180041e05  lea     r8, [rbp+50h+var_A0]
0x180041e09  mov     rcx, [rsp+150h+var_108]
0x180041e0e  call    cs:__imp_DevObjEnumDeviceInfo
0x180041e14  test    eax, eax
0x180041e16  jnz     short loc_180041E39
0x180041e18  mov     edx, 320h; void *
0x180041e1d  mov     rcx, [rbp+58h]; this
0x180041e21  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180041e26  mov     rcx, [rsp+150h+hkey]
0x180041e2b  cmp     rcx, r15
0x180041e2e  jz      loc_180041F26
0x180041e34  jmp     loc_180041F20
0x180041e39  mov     dword ptr [rsp+150h+pvData], 20019h
0x180041e41  mov     dword ptr [rsp+150h+phkResult], 1
0x180041e49  xor     r9d, r9d
0x180041e4c  lea     r8d, [r9+1]
0x180041e50  lea     rdx, [rbp+50h+var_A0]
0x180041e54  mov     rcx, [rsp+150h+var_108]
0x180041e59  call    cs:__imp_DevObjOpenDevRegKey
0x180041e5f  mov     rbx, rax
0x180041e62  cmp     rax, r15
0x180041e65  jnz     short loc_180041E6E
0x180041e67  mov     edx, 32Dh
0x180041e6c  jmp     short loc_180041E1D
0x180041e6e  lea     rdx, [rsp+150h+lpSubKey]
0x180041e73  cmp     [rbp+50h+var_C8], 7
0x180041e78  cmova   rdx, [rsp+150h+lpSubKey]; lpSubKey
0x180041e7e  lea     rax, [rsp+150h+hkey]
0x180041e83  mov     [rsp+150h+phkResult], rax; unsigned int
0x180041e88  mov     r9d, 20019h; samDesired
0x180041e8e  xor     r8d, r8d; ulOptions
0x180041e91  mov     rcx, rbx; hKey
0x180041e94  call    cs:__imp_RegOpenKeyExW
0x180041e9a  test    eax, eax
0x180041e9c  jz      short loc_180041EBB
0x180041e9e  mov     rcx, [rbp+58h]; this
0x180041ea2  mov     r9d, 3F3h; char *
0x180041ea8  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180041eaf  mov     edx, 338h; void *
0x180041eb4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180041eb9  jmp     short loc_180041F0D
0x180041ebb  mov     [rsp+150h+var_100], 0
0x180041ec3  mov     [rsp+150h+var_E8], 4
0x180041ecb  lea     rax, [rsp+150h+var_E8]
0x180041ed0  mov     [rsp+150h+pcbData], rax; pcbData
0x180041ed5  lea     rax, [rsp+150h+var_100]
0x180041eda  mov     [rsp+150h+pvData], rax; pvData
0x180041edf  mov     [rsp+150h+phkResult], 0; pdwType
0x180041ee8  mov     r9d, 18h; dwFlags
0x180041eee  lea     r8, aSecurefingerpr; "SecureFingerprint"
0x180041ef5  xor     edx, edx; lpSubKey
0x180041ef7  mov     rcx, [rsp+150h+hkey]; hkey
0x180041efc  call    cs:__imp_RegGetValueW
0x180041f02  test    eax, eax
0x180041f04  jnz     short loc_180041F0D
0x180041f06  cmp     [rsp+150h+var_100], 1
0x180041f0b  jz      short loc_180041F50
0x180041f0d  mov     rcx, [rsp+150h+hkey]; hKey
0x180041f12  cmp     rcx, r15
0x180041f15  jz      short loc_180041F1D
0x180041f17  call    cs:__imp_RegCloseKey
0x180041f1d  mov     rcx, rbx; hKey
0x180041f20  call    cs:__imp_RegCloseKey
0x180041f26  mov     r9d, edi
0x180041f29  lea     rax, [rbp+50h+var_C0]
0x180041f2d  mov     [rsp+150h+phkResult], rax
0x180041f32  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180041f39  xor     edx, edx
0x180041f3b  mov     rcx, [rsp+150h+var_108]
0x180041f40  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180041f46  test    eax, eax
0x180041f48  jnz     loc_180041DF5
0x180041f4e  jmp     short loc_180041F6C
0x180041f50  mov     sil, 1
0x180041f53  mov     rcx, [rsp+150h+hkey]; hKey
0x180041f58  cmp     rcx, r15
0x180041f5b  jz      short loc_180041F63
0x180041f5d  call    cs:__imp_RegCloseKey
0x180041f63  mov     rcx, rbx; hKey
0x180041f66  call    cs:__imp_RegCloseKey
0x180041f6c  mov     eax, cs:dword_18006E000
0x180041f72  cmp     eax, 4
0x180041f75  jbe     short loc_180041FD0
0x180041f77  mov     eax, edi
0x180041f79  mov     [rsp+150h+hkey], rax
0x180041f7e  mov     [rsp+150h+var_110], sil
0x180041f83  lea     rax, [rsp+150h+hkey]
0x180041f88  mov     [rbp+50h+var_40], rax
0x180041f8c  mov     [rbp+50h+var_38], 8
0x180041f94  lea     rax, [rsp+150h+var_110]
0x180041f99  mov     [rbp+50h+var_50], rax
0x180041f9d  mov     [rbp+50h+var_48], 1
0x180041fa5  lea     rax, [rbp+50h+var_70]
0x180041fa9  mov     [rsp+150h+pvData], rax
0x180041fae  mov     dword ptr [rsp+150h+phkResult], 4
0x180041fb6  xor     r9d, r9d
0x180041fb9  xor     r8d, r8d
0x180041fbc  lea     rdx, byte_180063307
0x180041fc3  lea     rcx, dword_18006E000
0x180041fca  call    _tlgWriteTransfer_EventWriteTransfer
0x180041fcf  nop
0x180041fd0  lea     rcx, [rsp+150h+lpSubKey]
0x180041fd5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041fda  nop
0x180041fdb  mov     rcx, [rsp+150h+var_108]
0x180041fe0  lea     rdx, [rcx-1]
0x180041fe4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180041fe8  ja      short loc_180041FF0
0x180041fea  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180041ff0  mov     al, sil
0x180041ff3  jmp     short loc_180042026
0x180041ff5  mov     edx, 2ECh; void *
0x180041ffa  mov     rcx, [rbp+58h]; this
0x180041ffe  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180042003  nop
0x180042004  lea     rcx, [rsp+150h+lpSubKey]
0x180042009  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004200e  nop
0x18004200f  mov     rcx, [rsp+150h+var_108]
0x180042014  lea     rax, [rcx-1]
0x180042018  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004201c  ja      short loc_180042024
0x18004201e  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180042024  xor     al, al
0x180042026  mov     rcx, [rbp+50h+var_30]
0x18004202a  xor     rcx, rsp; StackCookie
0x18004202d  call    __security_check_cookie
0x180042032  add     rsp, 130h
0x180042039  pop     r15
0x18004203b  pop     rdi
0x18004203c  pop     rsi
0x18004203d  pop     rbx
0x18004203e  pop     rbp
0x18004203f  retn
```
