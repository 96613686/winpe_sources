# CreateGlobals(void)

- ea: `0x180014488`
- end: `0x180014857`
- name: `?CreateGlobals@@YAHXZ`
- size: `975`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800141a0`

## callees

- `0x180014488`
- `0x1800157dc`
- `0x180025a1c`
- `0x180025abc`
- `0x180025bec`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800144d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800144f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014516`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014530`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001454a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014564`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001457e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014598`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800145b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800145cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800144d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800144f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014516`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014530`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001454a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014564`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001457e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014598`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800145b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800145cc`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1800147c3`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1800147c3`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180014685`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x180014685`
- `api-ms-win-core-localization-l1-2-0!GetCPInfoExW` at `0x1800147ee`
- `api-ms-win-core-localization-l1-2-0!GetCPInfoExW` at `0x1800147ee`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x1800146a6`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x1800146a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014701`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014714`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014714`
- `KERNEL32!CheckElevationEnabled` at `0x180014810`
- `KERNEL32!CheckElevationEnabled` at `0x180014810`
- `USER32!RegisterWindowMessageW` at `0x18001463a`
- `USER32!RegisterWindowMessageW` at `0x18001463a`

## pseudocode

```c
__int64 CreateGlobals(void)
{
  BOOL v0; // eax
  UINT v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rcx
  struct _uilang * near **v4; // rax
  __int64 v5; // rdx
  struct _uilang * near **v6; // rax
  BOOL v7; // eax
  bool v8; // zf
  int v9; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _cpinfoexW CPInfoEx; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  dwDisposition = 0;
  LoadStringW(hInstance, 5u, &g_szLocaleGetError, 180);
  LoadStringW(hInstance, 4u, &g_szLocaleCustomName, 300);
  LoadStringW(hInstance, 0x37u, &g_szStyleH, 3);
  LoadStringW(hInstance, 0x38u, &g_szStyleh, 3);
  LoadStringW(hInstance, 0x39u, &g_szStyleM, 3);
  LoadStringW(hInstance, 0x3Au, &g_szStylem, 3);
  LoadStringW(hInstance, 0x3Bu, &g_szStyles, 3);
  LoadStringW(hInstance, 0x3Cu, &g_szStylet, 3);
  LoadStringW(hInstance, 0x3Du, &g_szStyled, 3);
  LoadStringW(hInstance, 0x3Eu, &g_szStyley, 3);
  v0 = g_szStyleH != 72
    || g_szStyleh != 104
    || g_szStyleM != 77
    || g_szStylem != 109
    || g_szStyles != 115
    || g_szStylet != 116
    || g_szStyled != 100
    || g_szStyley != 121;
  g_fStylesLocalized = v0;
  v1 = RegisterWindowMessageW(L"LpksetupOperationFinished");
  v2 = g_localeInfo;
  g_uBroadcastId = v1;
  if ( !g_localeInfo )
  {
    if ( !(unsigned int)Intl_InitializeLocaleArray() )
      return 0;
    v2 = g_localeInfo;
    if ( !g_localeInfo )
      return 0;
  }
  if ( !v2[UserLocaleIndex] )
    return 0;
  GeoID = GetUserGeoID(0x10u);
  if ( IsValidLocaleName(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL)) )
  {
    RegUserLocaleIndex = UserLocaleIndex;
  }
  else
  {
    UserLocaleIndex = SysLocaleIndex;
    RegUserLocaleIndex = SysLocaleIndex;
    if ( !(unsigned int)Intl_InstallUserLocale(SysLocaleIndex) )
      ExitProcess(0xFFFFFFFF);
  }
  if ( RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\International", 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    return 0;
  RegCloseKey(hKey);
  if ( dwDisposition == 1 )
    Intl_InstallUserLocale(UserLocaleIndex);
  v3 = 32;
  v4 = &g_UIFirstFallback;
  v5 = 32;
  do
  {
    *(_BYTE *)v4 = 0;
    v4 = (struct _uilang * near **)((char *)v4 + 1);
    --v5;
  }
  while ( v5 );
  v6 = &g_UISecondFallback;
  do
  {
    *(_BYTE *)v6 = 0;
    v6 = (struct _uilang * near **)((char *)v6 + 1);
    --v3;
  }
  while ( v3 );
  bShowRtL = IsRtLLocale(*(const unsigned __int16 **)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL));
  v7 = bShowRtL && (*(_WORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 16LL) & 0x3FF) != 0xD;
  bShowArabic = v7;
  memset_0(&CPInfoEx, 0, sizeof(CPInfoEx));
  GetCPInfoExW(2u, 0, &CPInfoEx);
  v12 = 0;
  g_bUTF8InRegistry = CPInfoEx.CodePage == 65001;
  v8 = (unsigned int)CheckElevationEnabled(&v12) == 0;
  v9 = 1;
  if ( v8 )
    v9 = v12;
  g_bIsLUAEnabled = v9;
  g_bAdmin_Privileges = Intl_HasAdminPrivileges();
  return 1;
}

```

## disassembly

```asm
0x180014488  mov     [rsp-8+arg_0], rbx
0x18001448d  push    rbp
0x18001448e  lea     rbp, [rsp-190h]
0x180014496  sub     rsp, 290h
0x18001449d  mov     rax, cs:__security_cookie
0x1800144a4  xor     rax, rsp
0x1800144a7  mov     [rbp+190h+var_10], rax
0x1800144ae  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800144b5  lea     r8, ?g_szLocaleGetError@@3PAGA; lpBuffer
0x1800144bc  mov     r9d, 0B4h; cchBufferMax
0x1800144c2  mov     [rsp+290h+hKey], 0
0x1800144cb  mov     edx, 5; uID
0x1800144d0  mov     [rsp+290h+dwDisposition], 0
0x1800144d8  call    cs:__imp_LoadStringW
0x1800144de  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800144e5  lea     r8, ?g_szLocaleCustomName@@3PAGA; lpBuffer
0x1800144ec  mov     r9d, 12Ch; cchBufferMax
0x1800144f2  mov     edx, 4; uID
0x1800144f7  call    cs:__imp_LoadStringW
0x1800144fd  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180014504  lea     r8, ?g_szStyleH@@3PAGA; lpBuffer
0x18001450b  mov     ebx, 3
0x180014510  mov     r9d, ebx; cchBufferMax
0x180014513  lea     edx, [rbx+34h]; uID
0x180014516  call    cs:__imp_LoadStringW
0x18001451c  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180014523  lea     r8, ?g_szStyleh@@3PAGA; lpBuffer
0x18001452a  mov     r9d, ebx; cchBufferMax
0x18001452d  lea     edx, [rbx+35h]; uID
0x180014530  call    cs:__imp_LoadStringW
0x180014536  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18001453d  lea     r8, ?g_szStyleM@@3PAGA; lpBuffer
0x180014544  mov     r9d, ebx; cchBufferMax
0x180014547  lea     edx, [rbx+36h]; uID
0x18001454a  call    cs:__imp_LoadStringW
0x180014550  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180014557  lea     r8, ?g_szStylem@@3PAGA; lpBuffer
0x18001455e  mov     r9d, ebx; cchBufferMax
0x180014561  lea     edx, [rbx+37h]; uID
0x180014564  call    cs:__imp_LoadStringW
0x18001456a  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180014571  lea     r8, ?g_szStyles@@3PAGA; lpBuffer
0x180014578  mov     r9d, ebx; cchBufferMax
0x18001457b  lea     edx, [rbx+38h]; uID
0x18001457e  call    cs:__imp_LoadStringW
0x180014584  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18001458b  lea     r8, ?g_szStylet@@3PAGA; lpBuffer
0x180014592  mov     r9d, ebx; cchBufferMax
0x180014595  lea     edx, [rbx+39h]; uID
0x180014598  call    cs:__imp_LoadStringW
0x18001459e  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800145a5  lea     r8, ?g_szStyled@@3PAGA; lpBuffer
0x1800145ac  mov     r9d, ebx; cchBufferMax
0x1800145af  lea     edx, [rbx+3Ah]; uID
0x1800145b2  call    cs:__imp_LoadStringW
0x1800145b8  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800145bf  lea     r8, ?g_szStyley@@3PAGA; lpBuffer
0x1800145c6  mov     r9d, ebx; cchBufferMax
0x1800145c9  lea     edx, [rbx+3Bh]; uID
0x1800145cc  call    cs:__imp_LoadStringW
0x1800145d2  cmp     cs:?g_szStyleH@@3PAGA, 48h ; 'H'; ushort near * g_szStyleH
0x1800145da  mov     ebx, 1
0x1800145df  jnz     short loc_18001462B
0x1800145e1  cmp     cs:?g_szStyleh@@3PAGA, 68h ; 'h'; ushort near * g_szStyleh
0x1800145e9  jnz     short loc_18001462B
0x1800145eb  cmp     cs:?g_szStyleM@@3PAGA, 4Dh ; 'M'; ushort near * g_szStyleM
0x1800145f3  jnz     short loc_18001462B
0x1800145f5  cmp     cs:?g_szStylem@@3PAGA, 6Dh ; 'm'; ushort near * g_szStylem
0x1800145fd  jnz     short loc_18001462B
0x1800145ff  cmp     cs:?g_szStyles@@3PAGA, 73h ; 's'; ushort near * g_szStyles
0x180014607  jnz     short loc_18001462B
0x180014609  cmp     cs:?g_szStylet@@3PAGA, 74h ; 't'; ushort near * g_szStylet
0x180014611  jnz     short loc_18001462B
0x180014613  cmp     cs:?g_szStyled@@3PAGA, 64h ; 'd'; ushort near * g_szStyled
0x18001461b  jnz     short loc_18001462B
0x18001461d  cmp     cs:?g_szStyley@@3PAGA, 79h ; 'y'; ushort near * g_szStyley
0x180014625  jnz     short loc_18001462B
0x180014627  xor     eax, eax
0x180014629  jmp     short loc_18001462D
0x18001462b  mov     eax, ebx
0x18001462d  lea     rcx, String; "LpksetupOperationFinished"
0x180014634  mov     cs:?g_fStylesLocalized@@3HA, eax; int g_fStylesLocalized
0x18001463a  call    cs:__imp_RegisterWindowMessageW
0x180014640  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180014647  mov     cs:?g_uBroadcastId@@3KA, eax; ulong g_uBroadcastId
0x18001464d  test    rcx, rcx
0x180014650  jnz     short loc_18001466F
0x180014652  call    ?Intl_InitializeLocaleArray@@YAHXZ; Intl_InitializeLocaleArray(void)
0x180014657  test    eax, eax
0x180014659  jz      loc_180014835
0x18001465f  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180014666  test    rcx, rcx
0x180014669  jz      loc_180014835
0x18001466f  mov     eax, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180014675  cmp     qword ptr [rcx+rax*8], 0
0x18001467a  jz      loc_180014835
0x180014680  mov     ecx, 10h; GeoClass
0x180014685  call    cs:__imp_GetUserGeoID
0x18001468b  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180014691  mov     cs:?GeoID@@3JA, eax; long GeoID
0x180014697  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001469e  mov     rcx, [rax+rcx*8]
0x1800146a2  mov     rcx, [rcx+8]; lpLocaleName
0x1800146a6  call    cs:__imp_IsValidLocaleName
0x1800146ac  test    eax, eax
0x1800146ae  jz      loc_1800147A1
0x1800146b4  mov     eax, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800146ba  mov     cs:?RegUserLocaleIndex@@3KA, eax; ulong RegUserLocaleIndex
0x1800146c0  lea     rax, [rsp+290h+dwDisposition]
0x1800146c5  xor     r9d, r9d; lpClass
0x1800146c8  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x1800146cd  lea     rdx, aControlPanelIn_3; "Control Panel\\International"
0x1800146d4  lea     rax, [rsp+290h+hKey]
0x1800146d9  xor     r8d, r8d; Reserved
0x1800146dc  mov     [rsp+290h+phkResult], rax; phkResult
0x1800146e1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800146e8  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800146f1  mov     [rsp+290h+samDesired], 20006h; samDesired
0x1800146f9  mov     [rsp+290h+dwOptions], 0; dwOptions
0x180014701  call    cs:__imp_RegCreateKeyExW
0x180014707  test    eax, eax
0x180014709  jnz     loc_180014835
0x18001470f  mov     rcx, [rsp+290h+hKey]; hKey
0x180014714  call    cs:__imp_RegCloseKey
0x18001471a  cmp     [rsp+290h+dwDisposition], ebx
0x18001471e  jnz     short loc_18001472B
0x180014720  mov     ecx, cs:?UserLocaleIndex@@3KA; unsigned int
0x180014726  call    ?Intl_InstallUserLocale@@YAHK@Z; Intl_InstallUserLocale(ulong)
0x18001472b  mov     ecx, 20h ; ' '
0x180014730  lea     rax, ?g_UIFirstFallback@@3PAPEAU_uilang@@A; _uilang * near * g_UIFirstFallback
0x180014737  mov     edx, ecx
0x180014739  mov     byte ptr [rax], 0
0x18001473c  add     rax, rbx
0x18001473f  sub     rdx, rbx
0x180014742  jnz     short loc_180014739
0x180014744  lea     rax, ?g_UISecondFallback@@3PAPEAU_uilang@@A; _uilang * near * g_UISecondFallback
0x18001474b  mov     byte ptr [rax], 0
0x18001474e  add     rax, rbx
0x180014751  sub     rcx, rbx
0x180014754  jnz     short loc_18001474B
0x180014756  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001475c  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180014763  mov     rcx, [rax+rcx*8]
0x180014767  mov     rcx, [rcx+8]; unsigned __int16 *
0x18001476b  call    ?IsRtLLocale@@YAHPEBG@Z; IsRtLLocale(ushort const *)
0x180014770  mov     cs:?bShowRtL@@3HA, eax; int bShowRtL
0x180014776  test    eax, eax
0x180014778  jz      short loc_1800147CA
0x18001477a  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180014781  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180014787  mov     rcx, [rax+rcx*8]
0x18001478b  movzx   eax, word ptr [rcx+10h]
0x18001478f  mov     ecx, 3FFh
0x180014794  and     ax, cx
0x180014797  cmp     ax, 0Dh
0x18001479b  jz      short loc_1800147CA
0x18001479d  mov     eax, ebx
0x18001479f  jmp     short loc_1800147CC
0x1800147a1  mov     ecx, cs:?SysLocaleIndex@@3KA; unsigned int
0x1800147a7  mov     cs:?UserLocaleIndex@@3KA, ecx; ulong UserLocaleIndex
0x1800147ad  mov     cs:?RegUserLocaleIndex@@3KA, ecx; ulong RegUserLocaleIndex
0x1800147b3  call    ?Intl_InstallUserLocale@@YAHK@Z; Intl_InstallUserLocale(ulong)
0x1800147b8  test    eax, eax
0x1800147ba  jnz     loc_1800146C0
0x1800147c0  or      ecx, 0FFFFFFFFh; uExitCode
0x1800147c3  call    cs:__imp_ExitProcess
0x1800147ca  xor     eax, eax
0x1800147cc  xor     edx, edx; Val
0x1800147ce  mov     cs:?bShowArabic@@3HA, eax; int bShowArabic
0x1800147d4  mov     r8d, 220h; Size
0x1800147da  lea     rcx, [rsp+290h+CPInfoEx]; void *
0x1800147df  call    memset_0
0x1800147e4  xor     edx, edx; dwFlags
0x1800147e6  lea     r8, [rsp+290h+CPInfoEx]; lpCPInfoEx
0x1800147eb  lea     ecx, [rdx+2]; CodePage
0x1800147ee  call    cs:__imp_GetCPInfoExW
0x1800147f4  cmp     [rsp+290h+CPInfoEx.CodePage], 0FDE9h
0x1800147fc  lea     rcx, [rsp+290h+var_23C]
0x180014801  mov     [rsp+290h+var_23C], 0
0x180014809  setz    cs:?g_bUTF8InRegistry@@3_NA; bool g_bUTF8InRegistry
0x180014810  call    cs:__imp_CheckElevationEnabled
0x180014816  test    eax, eax
0x180014818  mov     eax, ebx
0x18001481a  jnz     short loc_180014820
0x18001481c  mov     eax, [rsp+290h+var_23C]
0x180014820  mov     cs:?g_bIsLUAEnabled@@3HA, eax; int g_bIsLUAEnabled
0x180014826  call    ?Intl_HasAdminPrivileges@@YAHXZ; Intl_HasAdminPrivileges(void)
0x18001482b  mov     cs:?g_bAdmin_Privileges@@3HA, eax; int g_bAdmin_Privileges
0x180014831  mov     eax, ebx
0x180014833  jmp     short loc_180014837
0x180014835  xor     eax, eax
0x180014837  mov     rcx, [rbp+190h+var_10]
0x18001483e  xor     rcx, rsp; StackCookie
0x180014841  call    __security_check_cookie
0x180014846  mov     rbx, [rsp+290h+arg_0]
0x18001484e  add     rsp, 290h
0x180014855  pop     rbp
0x180014856  retn
```
