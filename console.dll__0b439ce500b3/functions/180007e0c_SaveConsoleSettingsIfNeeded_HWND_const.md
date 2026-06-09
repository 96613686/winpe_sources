# SaveConsoleSettingsIfNeeded(HWND__ * const)

- ea: `0x180007e0c`
- end: `0x180008067`
- name: `?SaveConsoleSettingsIfNeeded@@YAXQEAUHWND__@@@Z`
- size: `603`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000752c`
- `0x180007998`
- `0x180007c60`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x1800058a4`
- `0x180005ea4`
- `0x180007e0c`
- `0x180008714`
- `0x180011eac`
- `0x180011f44`
- `0x1800175e4`
- `0x1800180bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007fbe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007ffe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007fbe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007ffe`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x180007f9a`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x180007f9a`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18000801e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18000801e`

## string_xrefs

- `0x180007f27`: `onecore\windows\core\console\open\src\propsheet\console.cpp`
- `0x180007f11`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`

## pseudocode

```c
void __fastcall SaveConsoleSettingsIfNeeded(HWND hWnd)
{
  struct _CONSOLE_STATE_INFO *v2; // rcx
  _WORD *v3; // r10
  unsigned __int16 *v4; // rax
  int v5; // r8d
  int v6; // edx
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // edx
  struct _CONSOLE_STATE_INFO *v10; // rcx
  int v11; // r8d
  IID rclsid; // [rsp+20h] [rbp-E0h] BYREF
  _STARTUPINFOW StartupInfo; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Text[360]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+498h]

  v2 = gpStateInfo;
  if ( (*((_BYTE *)gpStateInfo + 96) & 0x40) == 0 )
    return;
  if ( *((_DWORD *)gpStateInfo + 5) == DefaultFontFamily
    && *((_WORD *)gpStateInfo + 8) == DefaultFontSize.X
    && *((_WORD *)gpStateInfo + 9) == DefaultFontSize.Y
    && *((_DWORD *)gpStateInfo + 6) == 400 )
  {
    v3 = (_WORD *)((char *)gpStateInfo + 28);
    v4 = (unsigned __int16 *)((char *)gpStateInfo + 28);
    do
    {
      v5 = *(unsigned __int16 *)((char *)v4 + (char *)&DefaultFaceName - ((char *)gpStateInfo + 28));
      v6 = *v4 - v5;
      if ( v6 )
        break;
      ++v4;
    }
    while ( v5 );
    if ( !v6 )
    {
      *(_QWORD *)((char *)gpStateInfo + 20) = 0;
      *((_DWORD *)v2 + 4) = 0;
      *v3 = 0;
    }
  }
  rclsid = *(IID *)((char *)&g_selectedPackage + 4);
  v7 = DelegationConfig::s_Set(L"DelegationConsole", &rclsid);
  if ( v7 < 0 )
  {
    v8 = 228;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
      (const char *)(unsigned int)v7,
      rclsid.Data1);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\console.cpp",
      (const char *)(unsigned int)v7,
      rclsid.Data1);
    goto LABEL_16;
  }
  rclsid = *(IID *)((char *)&xmmword_180023290 + 4);
  v7 = DelegationConfig::s_Set(L"DelegationTerminal", &rclsid);
  if ( v7 < 0 )
  {
    v8 = 229;
    goto LABEL_15;
  }
LABEL_16:
  if ( *((_QWORD *)gpStateInfo + 25) )
  {
    SetGlobalRegistryValues();
    if ( (int)ShortcutSerialization::s_SetLinkValues(v10, v9, v11, *((_DWORD *)gpStateInfo + 53) != 0) < 0 )
    {
      memset_0(Buffer, 0, 0x208u);
      memset_0(&StartupInfo, 0, sizeof(StartupInfo));
      GetStartupInfoW(&StartupInfo);
      LoadStringW(ghInstance, 9u, Buffer, 260);
      StringCchPrintfW(Text, 0x168u, Buffer, *((_QWORD *)gpStateInfo + 25));
      LoadStringW(ghInstance, 8u, Buffer, 260);
      MessageBoxW(hWnd, Text, Buffer, 0x10010u);
      return;
    }
  }
  else
  {
    SetRegistryValues(gpStateInfo);
  }
  *((_DWORD *)gpStateInfo + 24) &= ~0x40u;
}

```

## disassembly

```asm
0x180007e0c  mov     [rsp-8+arg_8], rbx
0x180007e11  mov     [rsp-8+arg_10], rdi
0x180007e16  push    rbp
0x180007e17  lea     rbp, [rsp-490h]
0x180007e1f  sub     rsp, 590h
0x180007e26  mov     rax, cs:__security_cookie
0x180007e2d  xor     rax, rsp
0x180007e30  mov     [rbp+490h+var_10], rax
0x180007e37  mov     rdi, rcx
0x180007e3a  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007e41  test    byte ptr [rcx+60h], 40h
0x180007e45  jz      loc_180008042
0x180007e4b  movzx   eax, cs:?DefaultFontFamily@@3EA; uchar DefaultFontFamily
0x180007e52  cmp     [rcx+14h], eax
0x180007e55  jnz     short loc_180007EB6
0x180007e57  movzx   eax, word ptr cs:?DefaultFontSize@@3U_COORD@@A; _COORD DefaultFontSize
0x180007e5e  cmp     [rcx+10h], ax
0x180007e62  jnz     short loc_180007EB6
0x180007e64  movzx   eax, word ptr cs:?DefaultFontSize@@3U_COORD@@A+2; _COORD DefaultFontSize
0x180007e6b  cmp     [rcx+12h], ax
0x180007e6f  jnz     short loc_180007EB6
0x180007e71  cmp     dword ptr [rcx+18h], 190h
0x180007e78  jnz     short loc_180007EB6
0x180007e7a  lea     r10, [rcx+1Ch]
0x180007e7e  lea     r9, ?DefaultFaceName@@3PA_WA; wchar_t near * DefaultFaceName
0x180007e85  mov     rax, r10
0x180007e88  sub     r9, r10
0x180007e8b  movzx   edx, word ptr [rax]
0x180007e8e  movzx   r8d, word ptr [rax+r9]
0x180007e93  sub     edx, r8d
0x180007e96  jnz     short loc_180007EA1
0x180007e98  add     rax, 2
0x180007e9c  test    r8d, r8d
0x180007e9f  jnz     short loc_180007E8B
0x180007ea1  test    edx, edx
0x180007ea3  jnz     short loc_180007EB6
0x180007ea5  xor     eax, eax
0x180007ea7  mov     qword ptr [rcx+14h], 0
0x180007eaf  mov     [rcx+10h], eax
0x180007eb2  mov     [r10], ax
0x180007eb6  movups  xmm0, cs:?g_selectedPackage@@3UDelegationPackage@DelegationConfig@@A+4; DelegationConfig::DelegationPackage g_selectedPackage
0x180007ebd  lea     rdx, [rsp+590h+rclsid]; rclsid
0x180007ec2  lea     rcx, aDelegationcons; "DelegationConsole"
0x180007ec9  movdqu  xmmword ptr [rsp+590h+rclsid.Data1], xmm0
0x180007ecf  call    ?s_Set@DelegationConfig@@CAJPEB_WU_GUID@@@Z; DelegationConfig::s_Set(wchar_t const *,_GUID)
0x180007ed4  mov     ebx, eax
0x180007ed6  test    eax, eax
0x180007ed8  jns     short loc_180007EE1
0x180007eda  mov     edx, 0E4h
0x180007edf  jmp     short loc_180007F0A
0x180007ee1  movups  xmm0, cs:xmmword_180023290+4
0x180007ee8  lea     rdx, [rsp+590h+rclsid]; rclsid
0x180007eed  lea     rcx, aDelegationterm; "DelegationTerminal"
0x180007ef4  movdqu  xmmword ptr [rsp+590h+rclsid.Data1], xmm0; int
0x180007efa  call    ?s_Set@DelegationConfig@@CAJPEB_WU_GUID@@@Z; DelegationConfig::s_Set(wchar_t const *,_GUID)
0x180007eff  mov     ebx, eax
0x180007f01  test    eax, eax
0x180007f03  jns     short loc_180007F3B
0x180007f05  mov     edx, 0E5h; void *
0x180007f0a  mov     rcx, [rbp+498h]; this
0x180007f11  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180007f18  mov     r9d, ebx; char *
0x180007f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f20  mov     rcx, [rbp+498h]; this
0x180007f27  lea     r8, aOnecoreWindows_0; "onecore\\windows\\core\\console\\open\\"...
0x180007f2e  mov     r9d, ebx; char *
0x180007f31  mov     edx, 63h ; 'c'; void *
0x180007f36  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007f3b  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; struct _CONSOLE_STATE_INFO *
0x180007f42  cmp     qword ptr [rcx+0C8h], 0
0x180007f4a  jz      loc_18000802C
0x180007f50  call    ?SetGlobalRegistryValues@@YAXXZ; SetGlobalRegistryValues(void)
0x180007f55  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007f5c  cmp     dword ptr [rax+0D4h], 0
0x180007f63  setnz   r9b; bool
0x180007f67  call    ?s_SetLinkValues@ShortcutSerialization@@SAJPEAU_CONSOLE_STATE_INFO@@HH_N@Z; ShortcutSerialization::s_SetLinkValues(_CONSOLE_STATE_INFO *,int,int,bool)
0x180007f6c  test    eax, eax
0x180007f6e  jns     loc_180008037
0x180007f74  xor     edx, edx; Val
0x180007f76  lea     rcx, [rbp+490h+Buffer]; void *
0x180007f7a  mov     r8d, 208h; Size
0x180007f80  call    memset_0
0x180007f85  xor     edx, edx; Val
0x180007f87  lea     rcx, [rsp+590h+StartupInfo]; void *
0x180007f8c  lea     r8d, [rdx+68h]; Size
0x180007f90  call    memset_0
0x180007f95  lea     rcx, [rsp+590h+StartupInfo]; lpStartupInfo
0x180007f9a  call    cs:__imp_GetStartupInfoW
0x180007fa1  nop     dword ptr [rax+rax+00h]
0x180007fa6  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180007fad  lea     r8, [rbp+490h+Buffer]; lpBuffer
0x180007fb1  mov     ebx, 104h
0x180007fb6  mov     edx, 9; uID
0x180007fbb  mov     r9d, ebx; cchBufferMax
0x180007fbe  call    cs:__imp_LoadStringW
0x180007fc5  nop     dword ptr [rax+rax+00h]
0x180007fca  mov     r9, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007fd1  lea     r8, [rbp+490h+Buffer]; wchar_t *
0x180007fd5  lea     edx, [rbx+64h]; unsigned __int64
0x180007fd8  lea     rcx, [rbp+490h+Text]; wchar_t *
0x180007fdf  mov     r9, [r9+0C8h]
0x180007fe6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180007feb  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180007ff2  lea     r8, [rbp+490h+Buffer]; lpBuffer
0x180007ff6  mov     r9d, ebx; cchBufferMax
0x180007ff9  mov     edx, 8; uID
0x180007ffe  call    cs:__imp_LoadStringW
0x180008005  nop     dword ptr [rax+rax+00h]
0x18000800a  mov     r9d, 10010h; uType
0x180008010  lea     r8, [rbp+490h+Buffer]; lpCaption
0x180008014  lea     rdx, [rbp+490h+Text]; lpText
0x18000801b  mov     rcx, rdi; hWnd
0x18000801e  call    cs:__imp_MessageBoxW
0x180008025  nop     dword ptr [rax+rax+00h]
0x18000802a  jmp     short loc_180008042
0x18000802c  mov     edx, cs:?gnCurrentPage@@3IA; unsigned int
0x180008032  call    ?SetRegistryValues@@YAXPEAU_CONSOLE_STATE_INFO@@K@Z; SetRegistryValues(_CONSOLE_STATE_INFO *,ulong)
0x180008037  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000803e  and     dword ptr [rax+60h], 0FFFFFFBFh
0x180008042  mov     rcx, [rbp+490h+var_10]
0x180008049  xor     rcx, rsp; StackCookie
0x18000804c  call    __security_check_cookie
0x180008051  lea     r11, [rsp+590h+var_s0]
0x180008059  mov     rbx, [r11+18h]
0x18000805d  mov     rdi, [r11+20h]
0x180008061  mov     rsp, r11
0x180008064  pop     rbp
0x180008065  retn
```
