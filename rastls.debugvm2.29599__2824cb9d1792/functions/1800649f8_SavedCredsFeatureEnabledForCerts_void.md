# SavedCredsFeatureEnabledForCerts(void *)

- ea: `0x1800649f8`
- end: `0x180064baa`
- name: `?SavedCredsFeatureEnabledForCerts@@YAHPEAX@Z`
- size: `434`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800650c0`

## callees

- `0x180004bd0`
- `0x180020528`
- `0x180031b44`
- `0x180033284`
- `0x1800649f8`
- `0x180065270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064b86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064b86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064ae9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064b31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064b31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180064b90`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180064b90`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180064a3f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180064a3f`

## string_xrefs

- `0x180064adb`: `Software\Microsoft\Wlansvc\Configuration`

## pseudocode

```c
__int64 __fastcall SavedCredsFeatureEnabledForCerts(HANDLE hToken)
{
  unsigned int v1; // ebx
  int v3; // esi
  __int64 v4; // rcx
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int v13; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v1 = 0;
  cbData = 4;
  hKey = 0;
  Type = 0;
  v3 = 0;
  *(_DWORD *)Data = 0;
  v13 = 0;
  v14 = 0;
  PolicyInit();
  if ( !NtCurrentTeb()->IsImpersonating && hToken != (HANDLE)-1LL )
  {
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_26;
      v7 = 17;
LABEL_25:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
      goto LABEL_26;
    }
    v3 = 1;
  }
  if ( g_hPolicyExtLib && (int)PolicyExtLibIsPolicySetByMobileDeviceManager(v4, L"AllowEAPCertSSO", &v13) < 0 )
  {
    v8 = 0;
    v13 = 0;
  }
  else
  {
    v8 = v13;
  }
  if ( v8 )
  {
    if ( (int)PolicyExtLibGetPolicyInt(v4, L"AllowEAPCertSSO", &v14) >= 0 && v14 )
      goto LABEL_14;
  }
  else
  {
    LastError = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Wlansvc\\Configuration", 0, 0x20019u, &hKey);
    if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_26;
      v7 = 18;
      goto LABEL_25;
    }
    LastError = RegQueryValueExW(hKey, L"EnableUsrCertStoring", 0, &Type, Data, &cbData);
    if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_26;
      v7 = 19;
      goto LABEL_25;
    }
    if ( Type == 4 && cbData == 4 && *(_DWORD *)Data == 1 )
LABEL_14:
      v1 = 1;
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    RevertToSelf();
  PolicyDeInit();
  return v1;
}

```

## disassembly

```asm
0x1800649f8  mov     [rsp-18h+arg_0], rbx
0x1800649fd  push    rbp
0x1800649fe  push    rsi
0x1800649ff  push    rdi
0x180064a00  mov     rbp, rsp
0x180064a03  sub     rsp, 40h
0x180064a07  xor     ebx, ebx
0x180064a09  mov     [rbp+cbData], 4
0x180064a10  mov     [rbp+hKey], rbx
0x180064a14  mov     rdi, rcx
0x180064a17  mov     [rbp+Type], ebx
0x180064a1a  xor     esi, esi
0x180064a1c  mov     dword ptr [rbp+Data], ebx
0x180064a1f  mov     [rbp+arg_8], ebx
0x180064a22  mov     [rbp+arg_10], ebx
0x180064a25  call    PolicyInit
0x180064a2a  mov     eax, gs:179Ch
0x180064a32  test    eax, eax
0x180064a34  jnz     short loc_180064A73
0x180064a36  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180064a3a  jz      short loc_180064A73
0x180064a3c  mov     rcx, rdi; hToken
0x180064a3f  call    cs:__imp_ImpersonateLoggedOnUser
0x180064a45  test    eax, eax
0x180064a47  jnz     short loc_180064A6E
0x180064a49  call    cs:__imp_GetLastError
0x180064a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a56  lea     rdx, WPP_GLOBAL_Control
0x180064a5d  cmp     rcx, rdx
0x180064a60  jz      loc_180064B7D
0x180064a66  lea     edx, [rbx+11h]
0x180064a69  jmp     loc_180064B6A
0x180064a6e  mov     esi, 1
0x180064a73  cmp     cs:?g_hPolicyExtLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hPolicyExtLib
0x180064a7a  jz      short loc_180064A97
0x180064a7c  lea     r8, [rbp+arg_8]
0x180064a80  lea     rdx, aAlloweapcertss; "AllowEAPCertSSO"
0x180064a87  call    PolicyExtLibIsPolicySetByMobileDeviceManager
0x180064a8c  test    eax, eax
0x180064a8e  jns     short loc_180064A97
0x180064a90  xor     eax, eax
0x180064a92  mov     [rbp+arg_8], eax
0x180064a95  jmp     short loc_180064A9A
0x180064a97  mov     eax, [rbp+arg_8]
0x180064a9a  test    eax, eax
0x180064a9c  jz      short loc_180064AC9
0x180064a9e  lea     r8, [rbp+arg_10]
0x180064aa2  lea     rdx, aAlloweapcertss; "AllowEAPCertSSO"
0x180064aa9  call    PolicyExtLibGetPolicyInt
0x180064aae  test    eax, eax
0x180064ab0  js      loc_180064B7D
0x180064ab6  cmp     [rbp+arg_10], ebx
0x180064ab9  jz      loc_180064B7D
0x180064abf  mov     ebx, 1
0x180064ac4  jmp     loc_180064B7D
0x180064ac9  lea     rax, [rbp+hKey]
0x180064acd  mov     r9d, 20019h; samDesired
0x180064ad3  xor     r8d, r8d; ulOptions
0x180064ad6  mov     [rsp+40h+phkResult], rax; phkResult
0x180064adb  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Wlansvc\\Configura"...
0x180064ae2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180064ae9  call    cs:__imp_RegOpenKeyExW
0x180064aef  test    eax, eax
0x180064af1  jz      short loc_180064B0D
0x180064af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180064afa  lea     rdx, WPP_GLOBAL_Control
0x180064b01  cmp     rcx, rdx
0x180064b04  jz      short loc_180064B7D
0x180064b06  mov     edx, 12h
0x180064b0b  jmp     short loc_180064B6A
0x180064b0d  mov     rcx, [rbp+hKey]; hKey
0x180064b11  lea     rax, [rbp+cbData]
0x180064b15  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180064b1a  lea     r9, [rbp+Type]; lpType
0x180064b1e  lea     rax, [rbp+Data]
0x180064b22  xor     r8d, r8d; lpReserved
0x180064b25  lea     rdx, aEnableusrcerts; "EnableUsrCertStoring"
0x180064b2c  mov     [rsp+40h+phkResult], rax; lpData
0x180064b31  call    cs:__imp_RegQueryValueExW
0x180064b37  test    eax, eax
0x180064b39  jnz     short loc_180064B52
0x180064b3b  cmp     [rbp+Type], 4
0x180064b3f  jnz     short loc_180064B7D
0x180064b41  cmp     [rbp+cbData], 4
0x180064b45  jnz     short loc_180064B7D
0x180064b47  cmp     dword ptr [rbp+Data], 1
0x180064b4b  jnz     short loc_180064B7D
0x180064b4d  jmp     loc_180064ABF
0x180064b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180064b59  lea     rdx, WPP_GLOBAL_Control
0x180064b60  cmp     rcx, rdx
0x180064b63  jz      short loc_180064B7D
0x180064b65  mov     edx, 13h
0x180064b6a  mov     rcx, [rcx+10h]
0x180064b6e  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180064b75  mov     r9d, eax
0x180064b78  call    WPP_SF_d
0x180064b7d  mov     rcx, [rbp+hKey]; hKey
0x180064b81  test    rcx, rcx
0x180064b84  jz      short loc_180064B8C
0x180064b86  call    cs:__imp_RegCloseKey
0x180064b8c  test    esi, esi
0x180064b8e  jz      short loc_180064B96
0x180064b90  call    cs:__imp_RevertToSelf
0x180064b96  call    PolicyDeInit
0x180064b9b  mov     eax, ebx
0x180064b9d  mov     rbx, [rsp+40h+arg_0]
0x180064ba2  add     rsp, 40h
0x180064ba6  pop     rdi
0x180064ba7  pop     rsi
0x180064ba8  pop     rbp
0x180064ba9  retn
```
