# WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)

- ea: `0x1800375ec`
- end: `0x18003787f`
- name: `?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z`
- size: `659`
- prototype: `int(struct _AUTOVERIFIER_IPT_SETTINGS *, unsigned int, HKEY, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b4c4`
- `0x18002ecac`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x1800375ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037678`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037727`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800377b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037727`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800377b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037661`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037661`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003786b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003786b`

## pseudocode

```c
__int64 __fastcall WerPluginWriteSettings(const BYTE *a1, unsigned int a2, HKEY a3, const wchar_t *a4)
{
  HKEY v5; // rdi
  HKEY *phkResult; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  const BYTE *v15; // rax
  const BYTE *v16; // r8
  unsigned __int64 v17; // rax
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  v5 = a3;
  if ( !a1 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942487LL;
  }
  if ( a4 )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegCreateKeyExW(v5, a4, 0, 0, 0, 2u, 0, phkResult, 0) || (v5 = hKey) == 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids, v10);
      goto LABEL_25;
    }
  }
  v11 = 0;
  if ( !a2 )
  {
LABEL_24:
    v10 = 0;
    goto LABEL_25;
  }
  while ( 1 )
  {
    v12 = 568LL * v11;
    if ( !*(_DWORD *)&a1[v12 + 564] )
      goto LABEL_23;
    if ( *(_DWORD *)&a1[v12] == 1 )
      break;
    if ( *(_DWORD *)&a1[v12] == 4 && RegSetValueExW(v5, (LPCWSTR)&a1[v12 + 4], 0, 4u, &a1[v12 + 560], 4u) )
    {
      v10 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 21;
LABEL_19:
        WPP_SF_(v13[2], v14, &WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
LABEL_23:
    if ( ++v11 >= a2 )
      goto LABEL_24;
  }
  v15 = *(const BYTE **)&a1[v12 + 536];
  v16 = *(const BYTE **)&a1[v12 + 528];
  if ( v16 == v15 )
    goto LABEL_23;
  v17 = (v15 - v16) >> 1;
  if ( v17 >= 0x7FFFFFFF )
  {
    v10 = -2147024362;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 22;
      goto LABEL_19;
    }
    goto LABEL_25;
  }
  if ( !RegSetValueExW(v5, (LPCWSTR)&a1[v12 + 4], 0, 1u, v16, 2 * v17 + 2) )
    goto LABEL_23;
  v10 = -2147467259;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 23;
    goto LABEL_19;
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1800375ec  mov     rax, rsp
0x1800375ef  push    rbx
0x1800375f0  push    rbp
0x1800375f1  push    rsi
0x1800375f2  push    rdi
0x1800375f3  sub     rsp, 58h
0x1800375f7  mov     qword ptr [rax+8], 0
0x1800375ff  mov     rsi, r9
0x180037602  mov     rdi, r8
0x180037605  mov     ebp, edx
0x180037607  mov     rbx, rcx
0x18003760a  test    rcx, rcx
0x18003760d  jz      loc_180037830
0x180037613  test    r8, r8
0x180037616  jz      loc_180037830
0x18003761c  test    r9, r9
0x18003761f  jz      loc_1800376CB
0x180037625  lea     rcx, [rax+8]
0x180037629  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18003762e  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180037637  xor     r9d, r9d; lpClass
0x18003763a  mov     [rsp+78h+phkResult], rax; phkResult
0x18003763f  xor     r8d, r8d; Reserved
0x180037642  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003764b  mov     rdx, rsi; lpSubKey
0x18003764e  mov     [rsp+78h+samDesired], 2; samDesired
0x180037656  mov     rcx, rdi; hKey
0x180037659  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180037661  call    cs:__imp_RegCreateKeyExW
0x180037667  test    eax, eax
0x180037669  jnz     short loc_180037678
0x18003766b  mov     rdi, [rsp+78h+hKey]
0x180037673  test    rdi, rdi
0x180037676  jnz     short loc_1800376CB
0x180037678  call    cs:__imp_GetLastError
0x18003767e  mov     ebx, eax
0x180037680  test    eax, eax
0x180037682  jle     short loc_18003768D
0x180037684  movzx   ebx, ax
0x180037687  or      ebx, 80070000h
0x18003768d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037694  lea     rax, WPP_GLOBAL_Control
0x18003769b  cmp     rcx, rax
0x18003769e  jz      loc_1800377C6
0x1800376a4  test    byte ptr [rcx+1Ch], 1
0x1800376a8  jz      loc_1800377C6
0x1800376ae  mov     rcx, [rcx+10h]
0x1800376b2  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x1800376b9  mov     edx, 14h
0x1800376be  mov     r9d, ebx
0x1800376c1  call    WPP_SF_d
0x1800376c6  jmp     loc_1800377C6
0x1800376cb  xor     esi, esi
0x1800376cd  test    ebp, ebp
0x1800376cf  jz      loc_1800377C4
0x1800376d5  mov     eax, esi
0x1800376d7  imul    rcx, rax, 238h
0x1800376de  cmp     dword ptr [rcx+rbx+234h], 0
0x1800376e6  jz      loc_1800377BA
0x1800376ec  mov     edx, [rcx+rbx]
0x1800376ef  sub     edx, 1
0x1800376f2  jz      short loc_18003776A
0x1800376f4  cmp     edx, 3
0x1800376f7  jnz     loc_1800377BA
0x1800376fd  lea     rax, [rbx+230h]
0x180037704  mov     [rsp+78h+samDesired], 4; cbData
0x18003770c  add     rax, rcx
0x18003770f  lea     rdx, [rbx+4]
0x180037713  add     rdx, rcx; lpValueName
0x180037716  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x18003771b  mov     rcx, rdi; hKey
0x18003771e  mov     r9d, 4; dwType
0x180037724  xor     r8d, r8d; Reserved
0x180037727  call    cs:__imp_RegSetValueExW
0x18003772d  test    eax, eax
0x18003772f  jz      loc_1800377BA
0x180037735  mov     ebx, 80004005h
0x18003773a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037741  lea     rax, WPP_GLOBAL_Control
0x180037748  cmp     rcx, rax
0x18003774b  jz      short loc_1800377C6
0x18003774d  test    byte ptr [rcx+1Ch], 1
0x180037751  jz      short loc_1800377C6
0x180037753  mov     edx, 15h
0x180037758  mov     rcx, [rcx+10h]
0x18003775c  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x180037763  call    WPP_SF_
0x180037768  jmp     short loc_1800377C6
0x18003776a  mov     rax, [rcx+rbx+218h]
0x180037772  mov     r8, [rcx+rbx+210h]
0x18003777a  cmp     r8, rax
0x18003777d  jz      short loc_1800377BA
0x18003777f  sub     rax, r8
0x180037782  sar     rax, 1
0x180037785  cmp     rax, 7FFFFFFFh
0x18003778b  jnb     short loc_180037808
0x18003778d  lea     eax, ds:2[rax*2]
0x180037794  mov     r9d, 1; dwType
0x18003779a  mov     [rsp+78h+samDesired], eax; cbData
0x18003779e  lea     rdx, [rbx+4]
0x1800377a2  mov     qword ptr [rsp+78h+dwOptions], r8; lpData
0x1800377a7  add     rdx, rcx; lpValueName
0x1800377aa  xor     r8d, r8d; Reserved
0x1800377ad  mov     rcx, rdi; hKey
0x1800377b0  call    cs:__imp_RegSetValueExW
0x1800377b6  test    eax, eax
0x1800377b8  jnz     short loc_1800377E0
0x1800377ba  inc     esi
0x1800377bc  cmp     esi, ebp
0x1800377be  jb      loc_1800376D5
0x1800377c4  xor     ebx, ebx
0x1800377c6  mov     rcx, [rsp+78h+hKey]; hKey
0x1800377ce  test    rcx, rcx
0x1800377d1  jz      short loc_1800377D9
0x1800377d3  call    cs:__imp_RegCloseKey
0x1800377d9  mov     eax, ebx
0x1800377db  jmp     loc_180037876
0x1800377e0  mov     ebx, 80004005h
0x1800377e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377ec  lea     rax, WPP_GLOBAL_Control
0x1800377f3  cmp     rcx, rax
0x1800377f6  jz      short loc_1800377C6
0x1800377f8  test    byte ptr [rcx+1Ch], 1
0x1800377fc  jz      short loc_1800377C6
0x1800377fe  mov     edx, 17h
0x180037803  jmp     loc_180037758
0x180037808  mov     ebx, 80070216h
0x18003780d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037814  lea     rax, WPP_GLOBAL_Control
0x18003781b  cmp     rcx, rax
0x18003781e  jz      short loc_1800377C6
0x180037820  test    byte ptr [rcx+1Ch], 1
0x180037824  jz      short loc_1800377C6
0x180037826  mov     edx, 16h
0x18003782b  jmp     loc_180037758
0x180037830  mov     rcx, cs:WPP_GLOBAL_Control
0x180037837  lea     rax, WPP_GLOBAL_Control
0x18003783e  cmp     rcx, rax
0x180037841  jz      short loc_18003785E
0x180037843  test    byte ptr [rcx+1Ch], 1
0x180037847  jz      short loc_18003785E
0x180037849  mov     rcx, [rcx+10h]
0x18003784d  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x180037854  mov     edx, 13h
0x180037859  call    WPP_SF_
0x18003785e  mov     rcx, [rsp+78h+hKey]; hKey
0x180037866  test    rcx, rcx
0x180037869  jz      short loc_180037871
0x18003786b  call    cs:__imp_RegCloseKey
0x180037871  mov     eax, 80070057h
0x180037876  add     rsp, 58h
0x18003787a  pop     rdi
0x18003787b  pop     rsi
0x18003787c  pop     rbp
0x18003787d  pop     rbx
0x18003787e  retn
```
