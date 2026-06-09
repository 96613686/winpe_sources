# SavedCredsFeatureEnabledForCerts(void *)

- ea: `0x18006853c`
- end: `0x180068713`
- name: `?SavedCredsFeatureEnabledForCerts@@YAHPEAX@Z`
- size: `471`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180068c68`

## callees

- `0x180005010`
- `0x180022358`
- `0x180033cb0`
- `0x180035b9c`
- `0x18006853c`
- `0x180068e18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068593`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800686e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800686e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068639`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068639`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180068687`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180068687`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800686f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800686f2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180068583`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180068583`

## string_xrefs

- `0x18006862b`: `Software\Microsoft\Wlansvc\Configuration`

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
0x18006853c  mov     [rsp-18h+arg_0], rbx
0x180068541  push    rbp
0x180068542  push    rsi
0x180068543  push    rdi
0x180068544  mov     rbp, rsp
0x180068547  sub     rsp, 40h
0x18006854b  xor     ebx, ebx
0x18006854d  mov     [rbp+cbData], 4
0x180068554  mov     [rbp+hKey], rbx
0x180068558  mov     rdi, rcx
0x18006855b  mov     [rbp+Type], ebx
0x18006855e  xor     esi, esi
0x180068560  mov     dword ptr [rbp+Data], ebx
0x180068563  mov     [rbp+arg_8], ebx
0x180068566  mov     [rbp+arg_10], ebx
0x180068569  call    PolicyInit
0x18006856e  mov     eax, gs:179Ch
0x180068576  test    eax, eax
0x180068578  jnz     short loc_1800685C3
0x18006857a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18006857e  jz      short loc_1800685C3
0x180068580  mov     rcx, rdi; hToken
0x180068583  call    cs:__imp_ImpersonateLoggedOnUser
0x18006858a  nop     dword ptr [rax+rax+00h]
0x18006858f  test    eax, eax
0x180068591  jnz     short loc_1800685BE
0x180068593  call    cs:__imp_GetLastError
0x18006859a  nop     dword ptr [rax+rax+00h]
0x18006859f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800685a6  lea     rdx, WPP_GLOBAL_Control
0x1800685ad  cmp     rcx, rdx
0x1800685b0  jz      loc_1800686D9
0x1800685b6  lea     edx, [rbx+11h]
0x1800685b9  jmp     loc_1800686C6
0x1800685be  mov     esi, 1
0x1800685c3  cmp     cs:?g_hPolicyExtLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hPolicyExtLib
0x1800685ca  jz      short loc_1800685E7
0x1800685cc  lea     r8, [rbp+arg_8]
0x1800685d0  lea     rdx, aAlloweapcertss; "AllowEAPCertSSO"
0x1800685d7  call    PolicyExtLibIsPolicySetByMobileDeviceManager
0x1800685dc  test    eax, eax
0x1800685de  jns     short loc_1800685E7
0x1800685e0  xor     eax, eax
0x1800685e2  mov     [rbp+arg_8], eax
0x1800685e5  jmp     short loc_1800685EA
0x1800685e7  mov     eax, [rbp+arg_8]
0x1800685ea  test    eax, eax
0x1800685ec  jz      short loc_180068619
0x1800685ee  lea     r8, [rbp+arg_10]
0x1800685f2  lea     rdx, aAlloweapcertss; "AllowEAPCertSSO"
0x1800685f9  call    PolicyExtLibGetPolicyInt
0x1800685fe  test    eax, eax
0x180068600  js      loc_1800686D9
0x180068606  cmp     [rbp+arg_10], ebx
0x180068609  jz      loc_1800686D9
0x18006860f  mov     ebx, 1
0x180068614  jmp     loc_1800686D9
0x180068619  lea     rax, [rbp+hKey]
0x18006861d  mov     r9d, 20019h; samDesired
0x180068623  xor     r8d, r8d; ulOptions
0x180068626  mov     [rsp+40h+phkResult], rax; phkResult
0x18006862b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Wlansvc\\Configura"...
0x180068632  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180068639  call    cs:__imp_RegOpenKeyExW
0x180068640  nop     dword ptr [rax+rax+00h]
0x180068645  test    eax, eax
0x180068647  jz      short loc_180068663
0x180068649  mov     rcx, cs:WPP_GLOBAL_Control
0x180068650  lea     rdx, WPP_GLOBAL_Control
0x180068657  cmp     rcx, rdx
0x18006865a  jz      short loc_1800686D9
0x18006865c  mov     edx, 12h
0x180068661  jmp     short loc_1800686C6
0x180068663  mov     rcx, [rbp+hKey]; hKey
0x180068667  lea     rax, [rbp+cbData]
0x18006866b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180068670  lea     r9, [rbp+Type]; lpType
0x180068674  lea     rax, [rbp+Data]
0x180068678  xor     r8d, r8d; lpReserved
0x18006867b  lea     rdx, aEnableusrcerts; "EnableUsrCertStoring"
0x180068682  mov     [rsp+40h+phkResult], rax; lpData
0x180068687  call    cs:__imp_RegQueryValueExW
0x18006868e  nop     dword ptr [rax+rax+00h]
0x180068693  test    eax, eax
0x180068695  jnz     short loc_1800686AE
0x180068697  cmp     [rbp+Type], 4
0x18006869b  jnz     short loc_1800686D9
0x18006869d  cmp     [rbp+cbData], 4
0x1800686a1  jnz     short loc_1800686D9
0x1800686a3  cmp     dword ptr [rbp+Data], 1
0x1800686a7  jnz     short loc_1800686D9
0x1800686a9  jmp     loc_18006860F
0x1800686ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800686b5  lea     rdx, WPP_GLOBAL_Control
0x1800686bc  cmp     rcx, rdx
0x1800686bf  jz      short loc_1800686D9
0x1800686c1  mov     edx, 13h
0x1800686c6  mov     rcx, [rcx+10h]
0x1800686ca  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800686d1  mov     r9d, eax
0x1800686d4  call    WPP_SF_d
0x1800686d9  mov     rcx, [rbp+hKey]; hKey
0x1800686dd  test    rcx, rcx
0x1800686e0  jz      short loc_1800686EE
0x1800686e2  call    cs:__imp_RegCloseKey
0x1800686e9  nop     dword ptr [rax+rax+00h]
0x1800686ee  test    esi, esi
0x1800686f0  jz      short loc_1800686FE
0x1800686f2  call    cs:__imp_RevertToSelf
0x1800686f9  nop     dword ptr [rax+rax+00h]
0x1800686fe  call    PolicyDeInit
0x180068703  mov     eax, ebx
0x180068705  mov     rbx, [rsp+40h+arg_0]
0x18006870a  add     rsp, 40h
0x18006870e  pop     rdi
0x18006870f  pop     rsi
0x180068710  pop     rbp
0x180068711  retn
```
