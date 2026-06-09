# InitGlobalMetrics

- ea: `0x18001923c`
- end: `0x180019536`
- name: `InitGlobalMetrics`
- size: `762`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017bac`
- `0x180022bb0`
- `0x18002aab0`
- `0x18002d670`
- `0x180035b40`
- `0x1800371b0`
- `0x18003eff0`
- `0x180046d90`
- `0x18004f220`
- `0x18005a094`
- `0x180066d40`
- `0x18006e230`
- `0x1800890a0`

## callees

- `0x1800115f0`
- `0x18001923c`
- `0x18001953c`
- `0x18008ea60`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001937b`
- `ADVAPI32!RegOpenKeyExW` at `0x18001937b`
- `ADVAPI32!RegOpenCurrentUser` at `0x180019306`
- `ADVAPI32!RegOpenCurrentUser` at `0x180019306`
- `ADVAPI32!RegQueryValueExW` at `0x1800193b5`
- `ADVAPI32!RegQueryValueExW` at `0x1800193b5`
- `ADVAPI32!RegCloseKey` at `0x1800193c0`
- `ADVAPI32!RegCloseKey` at `0x180019510`
- `ADVAPI32!RegCloseKey` at `0x1800193c0`
- `ADVAPI32!RegCloseKey` at `0x180019510`
- `USER32!GetSystemMetrics` at `0x18001929b`
- `USER32!GetSystemMetrics` at `0x1800192ac`
- `USER32!GetSystemMetrics` at `0x1800192bd`
- `USER32!GetSystemMetrics` at `0x1800192ce`
- `USER32!GetSystemMetrics` at `0x1800192df`
- `USER32!GetSystemMetrics` at `0x1800192f0`
- `USER32!GetSystemMetrics` at `0x1800193ee`
- `USER32!GetSystemMetrics` at `0x1800193ff`
- `USER32!GetSystemMetrics` at `0x180019410`
- `USER32!GetSystemMetrics` at `0x180019421`
- `USER32!GetSystemMetrics` at `0x18001942f`
- `USER32!GetSystemMetrics` at `0x180019440`
- `USER32!GetSystemMetrics` at `0x18001944b`
- `USER32!GetSystemMetrics` at `0x18001945c`
- `USER32!GetSystemMetrics` at `0x1800194d4`
- `USER32!GetSystemMetrics` at `0x1800194e5`
- `USER32!GetSystemMetrics` at `0x18001929b`
- `USER32!GetSystemMetrics` at `0x1800192ac`
- `USER32!GetSystemMetrics` at `0x1800192bd`
- `USER32!GetSystemMetrics` at `0x1800192ce`
- `USER32!GetSystemMetrics` at `0x1800192df`
- `USER32!GetSystemMetrics` at `0x1800192f0`
- `USER32!GetSystemMetrics` at `0x1800193ee`
- `USER32!GetSystemMetrics` at `0x1800193ff`
- `USER32!GetSystemMetrics` at `0x180019410`
- `USER32!GetSystemMetrics` at `0x180019421`
- `USER32!GetSystemMetrics` at `0x18001942f`
- `USER32!GetSystemMetrics` at `0x180019440`
- `USER32!GetSystemMetrics` at `0x18001944b`
- `USER32!GetSystemMetrics` at `0x18001945c`
- `USER32!GetSystemMetrics` at `0x1800194d4`
- `USER32!GetSystemMetrics` at `0x1800194e5`
- `USER32!RegisterWindowMessageW` at `0x180019275`
- `USER32!RegisterWindowMessageW` at `0x180019275`
- `USER32!SystemParametersInfoW` at `0x180019290`
- `USER32!SystemParametersInfoW` at `0x180019335`
- `USER32!SystemParametersInfoW` at `0x18001947a`
- `USER32!SystemParametersInfoW` at `0x180019500`
- `USER32!SystemParametersInfoW` at `0x180019290`
- `USER32!SystemParametersInfoW` at `0x180019335`
- `USER32!SystemParametersInfoW` at `0x18001947a`
- `USER32!SystemParametersInfoW` at `0x180019500`

## pseudocode

```c
LSTATUS __fastcall InitGlobalMetrics(__int64 a1)
{
  int SystemMetrics; // eax
  LSTATUS result; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD pvParam[128]; // [rsp+50h] [rbp-B0h] BYREF

  phkResult = 0;
  g_uDragImages = RegisterWindowMessageW(L"ShellGetDragImage");
  SystemParametersInfoW(0x68u, 0, &g_ucScrollLines, 0);
  g_cxIcon = GetSystemMetrics(11);
  g_cyIcon = GetSystemMetrics(12);
  g_cxSmIcon = GetSystemMetrics(49);
  g_cySmIcon = GetSystemMetrics(50);
  g_cxIconSpacing = GetSystemMetrics(38);
  g_cyIconSpacing = GetSystemMetrics(39);
  RegOpenCurrentUser(0x20019u, &phkResult);
  if ( !g_bRemoteSession )
  {
    if ( !a1 || a1 == 37 )
      SystemParametersInfoW(0x26u, 4u, &g_fDragFullWindows, 0);
    *(_DWORD *)&g_fSmoothScroll = 1;
    if ( !(unsigned int)IsSystemProcess() )
    {
      if ( phkResult )
      {
        hKey = 0;
        if ( !RegOpenKeyExW(phkResult, L"Control Panel\\Desktop", 0, 0x20019u, &hKey) )
        {
          cbData = 4;
          RegQueryValueExW(hKey, L"SmoothScroll", 0, 0, &g_fSmoothScroll, &cbData);
          RegCloseKey(hKey);
        }
      }
    }
  }
  if ( !a1 || a1 == 42 )
  {
    memset(pvParam, 0, 0x1F4u);
    g_cxEdge = GetSystemMetrics(45);
    g_cyEdge = GetSystemMetrics(46);
    g_cxBorder = GetSystemMetrics(5);
    g_cyBorder = GetSystemMetrics(6);
    g_cxScreen = GetSystemMetrics(0);
    GetSystemMetrics(1);
    g_cxFrame = GetSystemMetrics(32);
    SystemMetrics = GetSystemMetrics(33);
    pvParam[0] = 500;
    g_cyFrame = SystemMetrics;
    SystemParametersInfoW(0x29u, 0x1F4u, pvParam, 0);
    g_cxScrollbar = pvParam[2];
    g_cxVScroll = pvParam[2];
    g_cyScrollbar = pvParam[3];
    g_cyHScroll = pvParam[3];
    g_cxIconMargin = 8 * g_cxBorder;
    g_cyIconMargin = g_cyEdge;
    g_cyLabelSpace = 2 * g_cyEdge;
    g_cxLabelMargin = g_cxEdge;
    g_cxDoubleClk = GetSystemMetrics(36);
    g_cyDoubleClk = GetSystemMetrics(37);
  }
  result = SystemParametersInfoW(0x66u, 0, &g_dwHoverSelectTimeout, 0);
  if ( phkResult )
    return RegCloseKey(phkResult);
  return result;
}

```

## disassembly

```asm
0x18001923c  mov     [rsp-8+arg_0], rbx
0x180019241  push    rbp
0x180019242  lea     rbp, [rsp-160h]
0x18001924a  sub     rsp, 260h
0x180019251  mov     rax, cs:__security_cookie
0x180019258  xor     rax, rsp
0x18001925b  mov     [rbp+160h+var_10], rax
0x180019262  mov     rbx, rcx
0x180019265  mov     [rsp+260h+phkResult], 0
0x18001926e  lea     rcx, aShellgetdragim; "ShellGetDragImage"
0x180019275  call    cs:__imp_RegisterWindowMessageW
0x18001927b  xor     edx, edx; uiParam
0x18001927d  lea     r8, g_ucScrollLines; pvParam
0x180019284  xor     r9d, r9d; fWinIni
0x180019287  mov     cs:g_uDragImages, eax
0x18001928d  lea     ecx, [rdx+68h]; uiAction
0x180019290  call    cs:__imp_SystemParametersInfoW
0x180019296  mov     ecx, 0Bh; nIndex
0x18001929b  call    cs:__imp_GetSystemMetrics
0x1800192a1  mov     ecx, 0Ch; nIndex
0x1800192a6  mov     cs:g_cxIcon, eax
0x1800192ac  call    cs:__imp_GetSystemMetrics
0x1800192b2  mov     ecx, 31h ; '1'; nIndex
0x1800192b7  mov     cs:g_cyIcon, eax
0x1800192bd  call    cs:__imp_GetSystemMetrics
0x1800192c3  mov     ecx, 32h ; '2'; nIndex
0x1800192c8  mov     cs:g_cxSmIcon, eax
0x1800192ce  call    cs:__imp_GetSystemMetrics
0x1800192d4  mov     ecx, 26h ; '&'; nIndex
0x1800192d9  mov     cs:g_cySmIcon, eax
0x1800192df  call    cs:__imp_GetSystemMetrics
0x1800192e5  mov     ecx, 27h ; '''; nIndex
0x1800192ea  mov     cs:g_cxIconSpacing, eax
0x1800192f0  call    cs:__imp_GetSystemMetrics
0x1800192f6  lea     rdx, [rsp+260h+phkResult]; phkResult
0x1800192fb  mov     ecx, 20019h; samDesired
0x180019300  mov     cs:g_cyIconSpacing, eax
0x180019306  call    cs:__imp_RegOpenCurrentUser
0x18001930c  cmp     cs:g_bRemoteSession, 0
0x180019313  jnz     loc_1800193C6
0x180019319  test    rbx, rbx
0x18001931c  jz      short loc_180019324
0x18001931e  cmp     rbx, 25h ; '%'
0x180019322  jnz     short loc_18001933B
0x180019324  xor     r9d, r9d; fWinIni
0x180019327  lea     r8, g_fDragFullWindows; pvParam
0x18001932e  lea     edx, [r9+4]; uiParam
0x180019332  lea     ecx, [rdx+22h]; uiAction
0x180019335  call    cs:__imp_SystemParametersInfoW
0x18001933b  mov     cs:g_fSmoothScroll, 1
0x180019345  call    IsSystemProcess
0x18001934a  test    eax, eax
0x18001934c  jnz     short loc_1800193C6
0x18001934e  mov     rcx, [rsp+260h+phkResult]; hKey
0x180019353  test    rcx, rcx
0x180019356  jz      short loc_1800193C6
0x180019358  lea     rax, [rsp+260h+hKey]
0x18001935d  mov     [rsp+260h+hKey], 0
0x180019366  mov     r9d, 20019h; samDesired
0x18001936c  mov     [rsp+260h+var_240], rax; phkResult
0x180019371  xor     r8d, r8d; ulOptions
0x180019374  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x18001937b  call    cs:__imp_RegOpenKeyExW
0x180019381  test    eax, eax
0x180019383  jnz     short loc_1800193C6
0x180019385  mov     rcx, [rsp+260h+hKey]; hKey
0x18001938a  lea     rax, [rsp+260h+cbData]
0x18001938f  mov     [rsp+260h+lpcbData], rax; lpcbData
0x180019394  lea     rdx, aSmoothscroll; "SmoothScroll"
0x18001939b  lea     rax, g_fSmoothScroll
0x1800193a2  mov     [rsp+260h+cbData], 4
0x1800193aa  xor     r9d, r9d; lpType
0x1800193ad  mov     [rsp+260h+var_240], rax; lpData
0x1800193b2  xor     r8d, r8d; lpReserved
0x1800193b5  call    cs:__imp_RegQueryValueExW
0x1800193bb  mov     rcx, [rsp+260h+hKey]; hKey
0x1800193c0  call    cs:__imp_RegCloseKey
0x1800193c6  test    rbx, rbx
0x1800193c9  jz      short loc_1800193D5
0x1800193cb  cmp     rbx, 2Ah ; '*'
0x1800193cf  jnz     loc_1800194F1
0x1800193d5  mov     ebx, 1F4h
0x1800193da  lea     rcx, [rsp+260h+pvParam]; void *
0x1800193df  mov     r8d, ebx; Size
0x1800193e2  xor     edx, edx; Val
0x1800193e4  call    memset
0x1800193e9  mov     ecx, 2Dh ; '-'; nIndex
0x1800193ee  call    cs:__imp_GetSystemMetrics
0x1800193f4  mov     ecx, 2Eh ; '.'; nIndex
0x1800193f9  mov     cs:g_cxEdge, eax
0x1800193ff  call    cs:__imp_GetSystemMetrics
0x180019405  mov     ecx, 5; nIndex
0x18001940a  mov     cs:g_cyEdge, eax
0x180019410  call    cs:__imp_GetSystemMetrics
0x180019416  mov     ecx, 6; nIndex
0x18001941b  mov     cs:g_cxBorder, eax
0x180019421  call    cs:__imp_GetSystemMetrics
0x180019427  xor     ecx, ecx; nIndex
0x180019429  mov     cs:g_cyBorder, eax
0x18001942f  call    cs:__imp_GetSystemMetrics
0x180019435  mov     ecx, 1; nIndex
0x18001943a  mov     cs:g_cxScreen, eax
0x180019440  call    cs:__imp_GetSystemMetrics
0x180019446  mov     ecx, 20h ; ' '; nIndex
0x18001944b  call    cs:__imp_GetSystemMetrics
0x180019451  mov     ecx, 21h ; '!'; nIndex
0x180019456  mov     cs:g_cxFrame, eax
0x18001945c  call    cs:__imp_GetSystemMetrics
0x180019462  xor     r9d, r9d; fWinIni
0x180019465  mov     [rsp+260h+pvParam], ebx
0x180019469  lea     r8, [rsp+260h+pvParam]; pvParam
0x18001946e  mov     cs:g_cyFrame, eax
0x180019474  mov     edx, ebx; uiParam
0x180019476  lea     ecx, [r9+29h]; uiAction
0x18001947a  call    cs:__imp_SystemParametersInfoW
0x180019480  mov     eax, [rsp+260h+var_208]
0x180019484  mov     ecx, 24h ; '$'; nIndex
0x180019489  mov     cs:g_cxScrollbar, eax
0x18001948f  mov     cs:g_cxVScroll, eax
0x180019495  mov     eax, [rsp+260h+var_204]
0x180019499  mov     cs:g_cyScrollbar, eax
0x18001949f  mov     cs:g_cyHScroll, eax
0x1800194a5  mov     eax, cs:g_cxBorder
0x1800194ab  shl     eax, 3
0x1800194ae  mov     cs:g_cxIconMargin, eax
0x1800194b4  mov     eax, cs:g_cyEdge
0x1800194ba  mov     cs:g_cyIconMargin, eax
0x1800194c0  add     eax, eax
0x1800194c2  mov     cs:g_cyLabelSpace, eax
0x1800194c8  mov     eax, cs:g_cxEdge
0x1800194ce  mov     cs:g_cxLabelMargin, eax
0x1800194d4  call    cs:__imp_GetSystemMetrics
0x1800194da  mov     ecx, 25h ; '%'; nIndex
0x1800194df  mov     cs:g_cxDoubleClk, eax
0x1800194e5  call    cs:__imp_GetSystemMetrics
0x1800194eb  mov     cs:g_cyDoubleClk, eax
0x1800194f1  xor     edx, edx; uiParam
0x1800194f3  lea     r8, g_dwHoverSelectTimeout; pvParam
0x1800194fa  xor     r9d, r9d; fWinIni
0x1800194fd  lea     ecx, [rdx+66h]; uiAction
0x180019500  call    cs:__imp_SystemParametersInfoW
0x180019506  mov     rcx, [rsp+260h+phkResult]; hKey
0x18001950b  test    rcx, rcx
0x18001950e  jz      short loc_180019516
0x180019510  call    cs:__imp_RegCloseKey
0x180019516  mov     rcx, [rbp+160h+var_10]
0x18001951d  xor     rcx, rsp; StackCookie
0x180019520  call    __security_check_cookie
0x180019525  mov     rbx, [rsp+260h+arg_0]
0x18001952d  add     rsp, 260h
0x180019534  pop     rbp
0x180019535  retn
```
