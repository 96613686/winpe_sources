# CHost::GetTrustPolicyFromRegistry(void)

- ea: `0x1400051cc`
- end: `0x14000540f`
- name: `?GetTrustPolicyFromRegistry@CHost@@IEAAXXZ`
- size: `579`
- prototype: `void __fastcall(CHost *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003e2c`

## callees

- `0x140004b50`
- `0x1400051cc`
- `0x140005760`
- `0x140008ec4`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140005263`
- `KERNEL32!WideCharToMultiByte` at `0x1400052b6`
- `KERNEL32!WideCharToMultiByte` at `0x140005263`
- `KERNEL32!WideCharToMultiByte` at `0x1400052b6`
- `KERNEL32!GetLastError` at `0x1400052e4`
- `KERNEL32!GetLastError` at `0x1400052e4`
- `ADVAPI32!RegOpenKeyExA` at `0x1400052dc`
- `ADVAPI32!RegOpenKeyExA` at `0x1400052dc`
- `ADVAPI32!RegOpenKeyExW` at `0x140005235`
- `ADVAPI32!RegOpenKeyExW` at `0x140005235`
- `ADVAPI32!RegCloseKey` at `0x1400053e1`
- `ADVAPI32!RegCloseKey` at `0x1400053f0`
- `ADVAPI32!RegCloseKey` at `0x1400053e1`
- `ADVAPI32!RegCloseKey` at `0x1400053f0`

## pseudocode

```c
void __fastcall CHost::GetTrustPolicyFromRegistry(CHost *this)
{
  char v2; // di
  bool v3; // bl
  int v4; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v6; // rax
  void *v7; // rsp
  unsigned int v8; // edi
  HKEY v9; // rcx
  int RegSettingsBool; // eax
  CHAR MultiByteStr; // [rsp+40h] [rbp+0h] BYREF
  bool v12; // [rsp+41h] [rbp+1h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+8h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+18h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = 0;
  phkResult = 0;
  v12 = 0;
  *(_DWORD *)Data = 0;
  MultiByteStr = 0;
  if ( Global::g_fWindowsNT )
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0, 0x20019u, &phkResult);
  }
  else
  {
    v4 = WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, 0, 0, 0, 0);
    cbMultiByte = v4;
    if ( !v4 )
      goto LABEL_8;
    v6 = v4 + 15LL;
    if ( cbMultiByte + 15 < cbMultiByte )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( WideCharToMultiByte(
           0,
           0,
           L"Software\\Microsoft\\Windows Script Host\\Settings",
           -1,
           &MultiByteStr,
           cbMultiByte,
           0,
           0) )
    {
      RegOpenKeyExA(HKEY_LOCAL_MACHINE, &MultiByteStr, 0, 0x20019u, &phkResult);
    }
    else
    {
LABEL_8:
      GetLastError();
    }
  }
  if ( !phkResult || (GetRegSettingsBool(phkResult, L"IgnoreUserSettings", &v12), !v12) )
    OpenRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
  if ( hKey )
  {
    v8 = (unsigned int)GetRegSettingsInt(hKey, L"TrustPolicy", Data) >> 31;
    v3 = (int)GetRegSettingsBool(hKey, L"UseWINSAFER", (bool *)&MultiByteStr) >= 0;
    v2 = v8 ^ 1;
    if ( v2 )
      goto LABEL_17;
  }
  v9 = phkResult;
  if ( phkResult )
  {
    if ( (int)GetRegSettingsInt(phkResult, L"TrustPolicy", Data) >= 0 )
      v2 = 1;
LABEL_17:
    v9 = phkResult;
  }
  if ( !v3 && v9 )
  {
    RegSettingsBool = GetRegSettingsBool(v9, L"UseWINSAFER", (bool *)&MultiByteStr);
    v9 = phkResult;
    v3 = RegSettingsBool >= 0;
  }
  if ( v2 && *(int *)Data > *((_DWORD *)this + 19) )
    *((_DWORD *)this + 19) = *(_DWORD *)Data;
  if ( v3 )
    *((_BYTE *)this + 74) = MultiByteStr;
  if ( hKey )
  {
    RegCloseKey(hKey);
    v9 = phkResult;
  }
  if ( v9 )
    RegCloseKey(v9);
}

```

## disassembly

```asm
0x1400051cc  push    rbp
0x1400051ce  push    rbx
0x1400051cf  push    rsi
0x1400051d0  push    rdi
0x1400051d1  push    r14
0x1400051d3  push    r15
0x1400051d5  sub     rsp, 78h
0x1400051d9  lea     rbp, [rsp+40h]
0x1400051de  mov     rax, cs:__security_cookie
0x1400051e5  xor     rax, rbp
0x1400051e8  mov     [rbp+60h+var_38], rax
0x1400051ec  xor     r15d, r15d
0x1400051ef  mov     rsi, rcx
0x1400051f2  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x1400051f9  mov     dil, r15b
0x1400051fc  mov     [rbp+60h+hKey], r15
0x140005200  mov     bl, r15b
0x140005203  mov     [rbp+60h+var_58], r15
0x140005207  mov     [rbp+60h+var_5F], r15b
0x14000520b  mov     dword ptr [rbp+60h+Data], r15d
0x14000520f  mov     [rbp+60h+MultiByteStr], r15b
0x140005213  jz      short loc_140005240
0x140005215  lea     rax, [rbp+60h+var_58]
0x140005219  mov     r9d, 20019h; samDesired
0x14000521f  xor     r8d, r8d; ulOptions
0x140005222  mov     [rsp+0A0h+phkResult], rax; phkResult
0x140005227  lea     rdx, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x14000522e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005235  call    cs:__imp_RegOpenKeyExW
0x14000523b  jmp     loc_1400052EA
0x140005240  mov     [rsp+0A0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140005245  lea     r8, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x14000524c  mov     [rsp+0A0h+lpDefaultChar], r15; lpDefaultChar
0x140005251  or      r9d, 0FFFFFFFFh; cchWideChar
0x140005255  mov     [rsp+0A0h+cbMultiByte], r15d; cbMultiByte
0x14000525a  xor     edx, edx; dwFlags
0x14000525c  xor     ecx, ecx; CodePage
0x14000525e  mov     [rsp+0A0h+phkResult], r15; lpMultiByteStr
0x140005263  call    cs:__imp_WideCharToMultiByte
0x140005269  movsxd  rdx, eax
0x14000526c  test    eax, eax
0x14000526e  jz      short loc_1400052E4
0x140005270  lea     rax, [rdx+0Fh]
0x140005274  cmp     rax, rdx
0x140005277  ja      short loc_140005283
0x140005279  mov     rax, 0FFFFFFFFFFFFFF0h
0x140005283  and     rax, 0FFFFFFFFFFFFFFF0h
0x140005287  call    _alloca_probe
0x14000528c  sub     rsp, rax
0x14000528f  lea     r8, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x140005296  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000529a  xor     ecx, ecx; CodePage
0x14000529c  mov     [rsp+0A0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1400052a1  lea     r14, [rsp+0A0h+MultiByteStr]
0x1400052a6  mov     [rsp+0A0h+lpDefaultChar], r15; lpDefaultChar
0x1400052ab  mov     [rsp+0A0h+cbMultiByte], edx; cbMultiByte
0x1400052af  xor     edx, edx; dwFlags
0x1400052b1  mov     [rsp+0A0h+phkResult], r14; lpMultiByteStr
0x1400052b6  call    cs:__imp_WideCharToMultiByte
0x1400052bc  test    eax, eax
0x1400052be  jz      short loc_1400052E4
0x1400052c0  lea     rax, [rbp+60h+var_58]
0x1400052c4  mov     r9d, 20019h; samDesired
0x1400052ca  xor     r8d, r8d; ulOptions
0x1400052cd  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1400052d2  mov     rdx, r14; lpSubKey
0x1400052d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400052dc  call    cs:__imp_RegOpenKeyExA
0x1400052e2  jmp     short loc_1400052EA
0x1400052e4  call    cs:__imp_GetLastError
0x1400052ea  mov     rcx, [rbp+60h+var_58]; hKey
0x1400052ee  test    rcx, rcx
0x1400052f1  jz      short loc_140005309
0x1400052f3  lea     r8, [rbp+60h+var_5F]; bool *
0x1400052f7  lea     rdx, aIgnoreusersett; "IgnoreUserSettings"
0x1400052fe  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x140005303  cmp     [rbp+60h+var_5F], r15b
0x140005307  jnz     short loc_140005326
0x140005309  lea     r9, [rbp+60h+hKey]; phkResult
0x14000530d  mov     r8d, 20019h; samDesired
0x140005313  lea     rdx, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x14000531a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140005321  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140005326  mov     rax, [rbp+60h+hKey]
0x14000532a  mov     r14d, 1
0x140005330  test    rax, rax
0x140005333  jz      short loc_14000536E
0x140005335  lea     r8, [rbp+60h+Data]; lpData
0x140005339  mov     rcx, rax; hKey
0x14000533c  lea     rdx, aTrustpolicy; "TrustPolicy"
0x140005343  call    ?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)
0x140005348  mov     rcx, [rbp+60h+hKey]; hKey
0x14000534c  lea     r8, [rbp+60h+MultiByteStr]; bool *
0x140005350  mov     edi, eax
0x140005352  lea     rdx, aUsewinsafer; "UseWINSAFER"
0x140005359  shr     edi, 1Fh
0x14000535c  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x140005361  mov     ebx, eax
0x140005363  shr     ebx, 1Fh
0x140005366  xor     bl, r14b
0x140005369  xor     dil, r14b
0x14000536c  jnz     short loc_140005391
0x14000536e  mov     rcx, [rbp+60h+var_58]; hKey
0x140005372  test    rcx, rcx
0x140005375  jz      short loc_140005395
0x140005377  lea     r8, [rbp+60h+Data]; lpData
0x14000537b  lea     rdx, aTrustpolicy; "TrustPolicy"
0x140005382  call    ?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)
0x140005387  test    eax, eax
0x140005389  movzx   edi, dil
0x14000538d  cmovns  edi, r14d
0x140005391  mov     rcx, [rbp+60h+var_58]; hKey
0x140005395  test    bl, bl
0x140005397  jnz     short loc_1400053BB
0x140005399  test    rcx, rcx
0x14000539c  jz      short loc_1400053BB
0x14000539e  lea     r8, [rbp+60h+MultiByteStr]; bool *
0x1400053a2  lea     rdx, aUsewinsafer; "UseWINSAFER"
0x1400053a9  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400053ae  mov     rcx, [rbp+60h+var_58]
0x1400053b2  test    eax, eax
0x1400053b4  movzx   ebx, bl
0x1400053b7  cmovns  ebx, r14d
0x1400053bb  test    dil, dil
0x1400053be  jz      short loc_1400053CB
0x1400053c0  mov     eax, dword ptr [rbp+60h+Data]
0x1400053c3  cmp     eax, [rsi+4Ch]
0x1400053c6  jle     short loc_1400053CB
0x1400053c8  mov     [rsi+4Ch], eax
0x1400053cb  test    bl, bl
0x1400053cd  jz      short loc_1400053D5
0x1400053cf  mov     al, [rbp+60h+MultiByteStr]
0x1400053d2  mov     [rsi+4Ah], al
0x1400053d5  mov     rax, [rbp+60h+hKey]
0x1400053d9  test    rax, rax
0x1400053dc  jz      short loc_1400053EB
0x1400053de  mov     rcx, rax; hKey
0x1400053e1  call    cs:__imp_RegCloseKey
0x1400053e7  mov     rcx, [rbp+60h+var_58]; hKey
0x1400053eb  test    rcx, rcx
0x1400053ee  jz      short loc_1400053F6
0x1400053f0  call    cs:__imp_RegCloseKey
0x1400053f6  mov     rcx, [rbp+60h+var_38]
0x1400053fa  xor     rcx, rbp; StackCookie
0x1400053fd  call    __security_check_cookie
0x140005402  lea     rsp, [rbp+38h]
0x140005406  pop     r15
0x140005408  pop     r14
0x14000540a  pop     rdi
0x14000540b  pop     rsi
0x14000540c  pop     rbx
0x14000540d  pop     rbp
0x14000540e  retn
```
