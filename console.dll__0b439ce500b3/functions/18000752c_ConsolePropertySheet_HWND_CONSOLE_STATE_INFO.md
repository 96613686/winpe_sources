# ConsolePropertySheet(HWND__ *,_CONSOLE_STATE_INFO *)

- ea: `0x18000752c`
- end: `0x180007886`
- name: `?ConsolePropertySheet@@YA_JPEAUHWND__@@PEAU_CONSOLE_STATE_INFO@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(HWND, struct _CONSOLE_STATE_INFO *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18000f100`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180005de0`
- `0x18000752c`
- `0x180007ae8`
- `0x180007e0c`
- `0x18000811c`
- `0x180008714`
- `0x1800088f4`
- `0x180009578`
- `0x18000f970`
- `0x1800103b4`
- `0x180010470`
- `0x1800114d4`
- `0x180011c68`
- `0x180012894`
- `0x180016c14`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007720`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000784f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000784f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000783b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000783b`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x1800075f0`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180007603`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180007616`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180007629`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x1800075f0`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180007603`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180007616`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180007629`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007755`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007755`

## string_xrefs

- `0x1800076b0`: `onecore\windows\core\console\open\src\propsheet\console.cpp`

## pseudocode

```c
__int64 __fastcall ConsolePropertySheet(HWND a1, struct _CONSOLE_STATE_INFO *a2)
{
  bool v4; // zf
  BOOL v5; // ecx
  int AvailablePackages; // eax
  unsigned __int64 v7; // rdx
  struct _CONSOLE_STATE_INFO *v8; // rcx
  unsigned __int64 v9; // rdx
  wchar_t *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rdi
  int v13; // ebx
  struct _CONSOLE_STATE_INFO *v14; // rdx
  int v15; // ecx
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v19; // [rsp+20h] [rbp-E0h]
  _DWORD v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  HWND v21; // [rsp+38h] [rbp-C8h]
  HINSTANCE v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  WCHAR *p_Buffer; // [rsp+50h] [rbp-B0h]
  int v25; // [rsp+58h] [rbp-A8h]
  unsigned int v26; // [rsp+60h] [rbp-A0h]
  _PROPSHEETPAGEW *v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  _PROPSHEETPAGEW v29; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR Dst[263]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  memset_0(v20, 0, 0x60u);
  memset_0(&Buffer, 0, 0x208u);
  v4 = *((_DWORD *)a2 + 53) == 0;
  gpStateInfo = a2;
  if ( v4 )
  {
    if ( GetOEMCP() != 932 && GetOEMCP() != 949 && GetOEMCP() != 950 && GetOEMCP() != 936 )
    {
      v5 = 0;
      goto LABEL_12;
    }
  }
  else if ( CodePageToCharSet(*((_DWORD *)a2 + 52)) != 0x80
         && CodePageToCharSet(*((_DWORD *)gpStateInfo + 52)) != 0x81
         && CodePageToCharSet(*((_DWORD *)gpStateInfo + 52)) != 0x88 )
  {
    v5 = CodePageToCharSet(*((_DWORD *)gpStateInfo + 52)) == 0x86;
    goto LABEL_12;
  }
  v5 = 1;
LABEL_12:
  g_fEastAsianSystem = v5;
  if ( *((char *)gpStateInfo + 96) < 0 )
  {
    InitRegistryValues(a2);
    GetRegistryValues(a2);
  }
  InitializeFonts();
  g_currentFontIndex = FindCreateFont(
                         *((_DWORD *)gpStateInfo + 5),
                         (wchar_t *)gpStateInfo + 14,
                         *(struct _COORD *)((char *)gpStateInfo + 16),
                         *((_DWORD *)gpStateInfo + 6),
                         *((_DWORD *)gpStateInfo + 52));
  RecreateFontHandles(a1);
  AvailablePackages = DelegationConfig::s_GetAvailablePackages();
  if ( AvailablePackages < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\console.cpp",
      (const char *)(unsigned int)AvailablePackages,
      v19);
  gnCurrentPage = GetRegistryValues(0);
  memset_0(&v29, 0, 0x208u);
  PopulatePropSheetPageArray(&v29, v7, 0);
  v20[0] = 96;
  v20[1] = 33554827;
  if ( *((char *)gpStateInfo + 96) >= 0 )
  {
    Buffer = 34;
    ExpandEnvironmentStringsW(*((LPCWSTR *)gpStateInfo + 24), Dst, 0x102u);
    StringCchCatW(&Buffer, v9, L"\"");
    v10 = TranslateConsoleTitle(*((const wchar_t **)gpStateInfo + 24));
    v8 = gpStateInfo;
    *((_QWORD *)gpStateInfo + 24) = v10;
  }
  else
  {
    LoadStringW(ghInstance, 3u, &Buffer, 260);
    v8 = gpStateInfo;
  }
  v21 = a1;
  v23 = *((_QWORD *)v8 + 23);
  v22 = ghInstance;
  p_Buffer = &Buffer;
  v28 = 0;
  v11 = gnCurrentPage;
  v25 = g_fForceV2 + 4;
  if ( gnCurrentPage > 5 )
    v11 = 5;
  v26 = v11;
  v27 = &v29;
  v12 = IsolationAwarePropertySheetW(v20);
  v13 = *((_DWORD *)gpStateInfo + 24);
  SaveConsoleSettingsIfNeeded(a1);
  v14 = gpStateInfo;
  v15 = *((_DWORD *)gpStateInfo + 24) ^ ((unsigned __int8)v13 ^ (unsigned __int8)*((_DWORD *)gpStateInfo + 24)) & 0x40;
  *((_DWORD *)gpStateInfo + 24) = v15;
  if ( (v15 & 0x80u) == 0 )
  {
    v16 = (void *)*((_QWORD *)v14 + 24);
    if ( v16 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v16);
    }
  }
  DestroyFonts();
  return v12;
}

```

## disassembly

```asm
0x18000752c  mov     [rsp-8+arg_10], rbx
0x180007531  push    rbp
0x180007532  push    rsi
0x180007533  push    rdi
0x180007534  lea     rbp, [rsp-3C0h]
0x18000753c  sub     rsp, 4C0h
0x180007543  mov     rax, cs:__security_cookie
0x18000754a  xor     rax, rsp
0x18000754d  mov     [rbp+3D0h+var_20], rax
0x180007554  mov     rbx, rdx
0x180007557  mov     rsi, rcx
0x18000755a  mov     edi, 60h ; '`'
0x18000755f  lea     rcx, [rsp+4D0h+var_4A0]; void *
0x180007564  mov     r8d, edi; Size
0x180007567  xor     edx, edx; Val
0x180007569  call    memset_0
0x18000756e  xor     edx, edx; Val
0x180007570  lea     rcx, [rbp+3D0h+Buffer]; void *
0x180007577  mov     r8d, 208h; Size
0x18000757d  call    memset_0
0x180007582  cmp     dword ptr [rbx+0D4h], 0
0x180007589  mov     cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA, rbx; _CONSOLE_STATE_INFO * gpStateInfo
0x180007590  jz      short loc_1800075F0
0x180007592  mov     ecx, [rbx+0D0h]; unsigned int
0x180007598  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x18000759d  cmp     al, 80h
0x18000759f  jz      loc_180007640
0x1800075a5  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800075ac  mov     ecx, [rcx+0D0h]; unsigned int
0x1800075b2  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x1800075b7  cmp     al, 81h
0x1800075b9  jz      loc_180007640
0x1800075bf  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800075c6  mov     ecx, [rcx+0D0h]; unsigned int
0x1800075cc  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x1800075d1  cmp     al, 88h
0x1800075d3  jz      short loc_180007640
0x1800075d5  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800075dc  mov     ecx, [rcx+0D0h]; unsigned int
0x1800075e2  call    ?CodePageToCharSet@@YAEI@Z; CodePageToCharSet(uint)
0x1800075e7  xor     ecx, ecx
0x1800075e9  cmp     al, 86h
0x1800075eb  setz    cl
0x1800075ee  jmp     short loc_180007645
0x1800075f0  call    cs:__imp_GetOEMCP
0x1800075f7  nop     dword ptr [rax+rax+00h]
0x1800075fc  cmp     eax, 3A4h
0x180007601  jz      short loc_180007640
0x180007603  call    cs:__imp_GetOEMCP
0x18000760a  nop     dword ptr [rax+rax+00h]
0x18000760f  cmp     eax, 3B5h
0x180007614  jz      short loc_180007640
0x180007616  call    cs:__imp_GetOEMCP
0x18000761d  nop     dword ptr [rax+rax+00h]
0x180007622  cmp     eax, 3B6h
0x180007627  jz      short loc_180007640
0x180007629  call    cs:__imp_GetOEMCP
0x180007630  nop     dword ptr [rax+rax+00h]
0x180007635  cmp     eax, 3A8h
0x18000763a  jz      short loc_180007640
0x18000763c  xor     ecx, ecx
0x18000763e  jmp     short loc_180007645
0x180007640  mov     ecx, 1
0x180007645  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000764c  mov     cs:?g_fEastAsianSystem@@3HA, ecx; int g_fEastAsianSystem
0x180007652  test    byte ptr [rax+60h], 80h
0x180007656  jz      short loc_180007668
0x180007658  mov     rcx, rbx; struct _CONSOLE_STATE_INFO *
0x18000765b  call    ?InitRegistryValues@@YAXPEAU_CONSOLE_STATE_INFO@@@Z; InitRegistryValues(_CONSOLE_STATE_INFO *)
0x180007660  mov     rcx, rbx; struct _CONSOLE_STATE_INFO *
0x180007663  call    ?GetRegistryValues@@YAKPEAU_CONSOLE_STATE_INFO@@@Z; GetRegistryValues(_CONSOLE_STATE_INFO *)
0x180007668  call    ?InitializeFonts@@YAXXZ; InitializeFonts(void)
0x18000766d  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007674  mov     eax, [rcx+0D0h]
0x18000767a  lea     rdx, [rcx+1Ch]; wchar_t *
0x18000767e  mov     r9d, [rcx+18h]; int
0x180007682  mov     r8d, [rcx+10h]; struct _COORD
0x180007686  mov     ecx, [rcx+14h]; unsigned int
0x180007689  mov     [rsp+4D0h+var_4B0], eax; int
0x18000768d  call    ?FindCreateFont@@YAHKPEA_WU_COORD@@JI@Z; FindCreateFont(ulong,wchar_t *,_COORD,long,uint)
0x180007692  mov     rcx, rsi; HWND
0x180007695  mov     cs:?g_currentFontIndex@@3KA, eax; ulong g_currentFontIndex
0x18000769b  call    ?RecreateFontHandles@@YAXQEAUHWND__@@@Z; RecreateFontHandles(HWND__ * const)
0x1800076a0  call    ?s_GetAvailablePackages@DelegationConfig@@SAJAEAV?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAUDelegationPackage@1@@Z; DelegationConfig::s_GetAvailablePackages(std::vector<DelegationConfig::DelegationPackage> &,DelegationConfig::DelegationPackage &)
0x1800076a5  test    eax, eax
0x1800076a7  jns     short loc_1800076C4
0x1800076a9  mov     rcx, [rbp+3D8h]; this
0x1800076b0  lea     r8, aOnecoreWindows_0; "onecore\\windows\\core\\console\\open\\"...
0x1800076b7  mov     r9d, eax; char *
0x1800076ba  mov     edx, 26Eh; void *
0x1800076bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800076c4  xor     ecx, ecx; struct _CONSOLE_STATE_INFO *
0x1800076c6  call    ?GetRegistryValues@@YAKPEAU_CONSOLE_STATE_INFO@@@Z; GetRegistryValues(_CONSOLE_STATE_INFO *)
0x1800076cb  xor     edx, edx; Val
0x1800076cd  mov     cs:?gnCurrentPage@@3IA, eax; uint gnCurrentPage
0x1800076d3  mov     r8d, 208h; Size
0x1800076d9  lea     rcx, [rbp+3D0h+var_440]; void *
0x1800076dd  call    memset_0
0x1800076e2  xor     r8d, r8d; int
0x1800076e5  lea     rcx, [rbp+3D0h+var_440]; struct _PROPSHEETPAGEW *
0x1800076e9  call    ?PopulatePropSheetPageArray@@YAHPEAU_PROPSHEETPAGEW@@_KH@Z; PopulatePropSheetPageArray(_PROPSHEETPAGEW *,unsigned __int64,int)
0x1800076ee  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800076f5  mov     [rsp+4D0h+var_4A0], edi
0x1800076f9  mov     [rsp+4D0h+var_49C], 200018Bh
0x180007701  test    byte ptr [rcx+60h], 80h
0x180007705  jz      short loc_180007735
0x180007707  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000770e  lea     r8, [rbp+3D0h+Buffer]; lpBuffer
0x180007715  mov     r9d, 104h; cchBufferMax
0x18000771b  mov     edx, 3; uID
0x180007720  call    cs:__imp_LoadStringW
0x180007727  nop     dword ptr [rax+rax+00h]
0x18000772c  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007733  jmp     short loc_180007795
0x180007735  mov     eax, 22h ; '"'
0x18000773a  lea     rdx, [rbp+3D0h+Dst]; lpDst
0x180007741  mov     [rbp+3D0h+Buffer], ax
0x180007748  mov     r8d, 102h; nSize
0x18000774e  mov     rcx, [rcx+0C0h]; lpSrc
0x180007755  call    cs:__imp_ExpandEnvironmentStringsW
0x18000775c  nop     dword ptr [rax+rax+00h]
0x180007761  lea     r8, asc_18001CA3C; "\""
0x180007768  lea     rcx, [rbp+3D0h+Buffer]; wchar_t *
0x18000776f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007774  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000777b  mov     rcx, [rcx+0C0h]; wchar_t *
0x180007782  call    ?TranslateConsoleTitle@@YAPEA_WPEB_W@Z; TranslateConsoleTitle(wchar_t const *)
0x180007787  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000778e  mov     [rcx+0C0h], rax
0x180007795  mov     [rsp+4D0h+var_498], rsi
0x18000779a  mov     rax, [rcx+0B8h]
0x1800077a1  mov     [rsp+4D0h+var_488], rax
0x1800077a6  mov     rax, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghInstance
0x1800077ad  mov     [rsp+4D0h+var_490], rax
0x1800077b2  lea     rax, [rbp+3D0h+Buffer]
0x1800077b9  mov     [rsp+4D0h+var_480], rax
0x1800077be  mov     eax, cs:?g_fForceV2@@3HA; int g_fForceV2
0x1800077c4  neg     eax
0x1800077c6  mov     [rsp+4D0h+var_460], 0
0x1800077cf  mov     eax, cs:?gnCurrentPage@@3IA; uint gnCurrentPage
0x1800077d5  sbb     ecx, ecx
0x1800077d7  neg     ecx
0x1800077d9  add     ecx, 4
0x1800077dc  mov     [rsp+4D0h+var_478], ecx
0x1800077e0  mov     ecx, 5
0x1800077e5  cmp     eax, ecx
0x1800077e7  cmova   eax, ecx
0x1800077ea  lea     rcx, [rsp+4D0h+var_4A0]
0x1800077ef  mov     [rsp+4D0h+var_470], eax
0x1800077f3  lea     rax, [rbp+3D0h+var_440]
0x1800077f7  mov     [rsp+4D0h+var_468], rax
0x1800077fc  call    IsolationAwarePropertySheetW
0x180007801  mov     rdx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007808  mov     rcx, rsi; hWnd
0x18000780b  mov     rdi, rax
0x18000780e  mov     ebx, [rdx+60h]
0x180007811  call    ?SaveConsoleSettingsIfNeeded@@YAXQEAUHWND__@@@Z; SaveConsoleSettingsIfNeeded(HWND__ * const)
0x180007816  mov     rdx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000781d  mov     ecx, [rdx+60h]
0x180007820  xor     ecx, ebx
0x180007822  and     ecx, 40h
0x180007825  xor     ecx, [rdx+60h]
0x180007828  mov     [rdx+60h], ecx
0x18000782b  test    cl, cl
0x18000782d  js      short loc_18000785B
0x18000782f  mov     rbx, [rdx+0C0h]
0x180007836  test    rbx, rbx
0x180007839  jz      short loc_18000785B
0x18000783b  call    cs:__imp_GetProcessHeap
0x180007842  nop     dword ptr [rax+rax+00h]
0x180007847  mov     r8, rbx; lpMem
0x18000784a  xor     edx, edx; dwFlags
0x18000784c  mov     rcx, rax; hHeap
0x18000784f  call    cs:__imp_HeapFree
0x180007856  nop     dword ptr [rax+rax+00h]
0x18000785b  call    ?DestroyFonts@@YAXXZ; DestroyFonts(void)
0x180007860  mov     rax, rdi
0x180007863  mov     rcx, [rbp+3D0h+var_20]
0x18000786a  xor     rcx, rsp; StackCookie
0x18000786d  call    __security_check_cookie
0x180007872  mov     rbx, [rsp+4D0h+arg_10]
0x18000787a  add     rsp, 4C0h
0x180007881  pop     rdi
0x180007882  pop     rsi
0x180007883  pop     rbp
0x180007884  retn
```
