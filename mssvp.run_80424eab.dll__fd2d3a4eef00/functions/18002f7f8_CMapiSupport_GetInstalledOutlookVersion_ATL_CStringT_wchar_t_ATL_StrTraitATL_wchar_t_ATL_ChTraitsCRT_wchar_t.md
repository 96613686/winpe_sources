# CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x18002f7f8`
- end: `0x18002fa71`
- name: `?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z`
- size: `633`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ff80`
- `0x18002b2e0`
- `0x18002ea50`
- `0x18003026c`
- `0x180031828`
- `0x1800320e8`
- `0x1800330b4`

## callees

- `0x1800031c0`
- `0x1800048c0`
- `0x180004d40`
- `0x180006270`
- `0x180019084`
- `0x18001da94`
- `0x180021c38`
- `0x18002f7f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f88f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f88f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f851`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f979`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f9c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f851`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f979`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f9c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f89c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f89c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CMapiSupport::GetInstalledOutlookVersion(_QWORD *a1)
{
  LSTATUS v2; // eax
  LSTATUS v3; // ebx
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  int *v8; // rsi
  __int64 v9; // rbx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  DWORD cbData; // [rsp+30h] [rbp-278h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-270h] BYREF
  DWORD Type; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-260h] BYREF
  ATL::CAtlException *v18; // [rsp+50h] [rbp-258h] BYREF
  ATL::CAtlException *v19; // [rsp+60h] [rbp-248h] BYREF
  _WORD Data[264]; // [rsp+70h] [rbp-238h] BYREF
  void *retaddr; // [rsp+2A8h] [rbp+0h]

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application\\CurVer", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      v11 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.12", 0, 0x20019u, &hKey);
      if ( !v11 )
      {
        try
        {
          v13 = 0;
          ATL::CSimpleStringT<wchar_t,0>::SetString(a1, L"12", 2);
        }
        catch ( ATL::CAtlException *v18 )
        {
          v13 = *(_DWORD *)v18;
          goto LABEL_20;
        }
        catch ( ... )
        {
          indexer::result::details::result_from_caught_exception<0>(
            retaddr,
            364,
            "onecoreuap\\base\\appmodel\\search\\common\\mapilib\\mapisupport.cxx");
        }
        goto LABEL_20;
      }
      if ( v11 == 2 )
      {
        v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.11", 0, 0x20019u, &hKey);
        if ( v12 )
        {
          if ( v12 != 2 || RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.10", 0, 0x20019u, &hKey) )
            return 1;
          try
          {
            v13 = 0;
            ATL::CSimpleStringT<wchar_t,0>::SetString(a1, L"10", 2);
          }
          catch ( ATL::CAtlException *v19 )
          {
            v13 = *(_DWORD *)v19;
          }
          catch ( ... )
          {
            indexer::result::details::result_from_caught_exception<0>(
              retaddr,
              408,
              "onecoreuap\\base\\appmodel\\search\\common\\mapilib\\mapisupport.cxx");
          }
        }
        else
        {
          v13 = 0;
          ATL::CSimpleStringT<wchar_t,0>::SetString(a1, L"11", 2);
        }
LABEL_20:
        RegCloseKey(hKey);
        return v13;
      }
    }
    return 1;
  }
  Type = 0;
  cbData = 520;
  v3 = RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData);
  RegCloseKey(hKey);
  if ( v3 )
    return 1;
  v4 = -1;
  do
    ++v4;
  while ( Data[v4] );
  ATL::CSimpleStringT<wchar_t,0>::SetString(a1, Data, v4);
  v5 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(a1, 46);
  if ( v5 <= 0 )
    return 1;
  v6 = *(_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(
                    a1,
                    v17,
                    (unsigned int)(*(_DWORD *)(*a1 - 16LL) - v5 - 1));
  v7 = (_QWORD *)(v6 - 24);
  v8 = (int *)(*a1 - 24LL);
  if ( (int *)(v6 - 24) != v8 )
  {
    if ( v8[4] >= 0 && *v7 == *(_QWORD *)v8 )
    {
      v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v7);
      ATL::CStringData::Release((ATL::CStringData *)v8);
      *a1 = v9 + 24;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(a1, v6, *(unsigned int *)(v6 - 16));
    }
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v17);
  return 0;
}

```

## disassembly

```asm
0x18002f7f8  mov     [rsp+arg_8], rbx
0x18002f7fd  mov     [rsp+arg_10], rsi
0x18002f802  push    rdi
0x18002f803  push    r14
0x18002f805  push    r15
0x18002f807  sub     rsp, 290h
0x18002f80e  mov     rax, cs:__security_cookie
0x18002f815  xor     rax, rsp
0x18002f818  mov     [rsp+2A8h+var_28], rax
0x18002f820  mov     rdi, rcx
0x18002f823  xor     r14d, r14d
0x18002f826  mov     [rsp+2A8h+hKey], r14
0x18002f82b  lea     rax, [rsp+2A8h+hKey]
0x18002f830  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002f835  mov     ebx, 20019h
0x18002f83a  mov     r9d, ebx; samDesired
0x18002f83d  xor     r8d, r8d; ulOptions
0x18002f840  lea     rdx, aOutlookApplica; "Outlook.Application\\CurVer"
0x18002f847  mov     r15, 0FFFFFFFF80000000h
0x18002f84e  mov     rcx, r15; hKey
0x18002f851  call    cs:__imp_RegOpenKeyExW
0x18002f857  test    eax, eax
0x18002f859  jnz     loc_18002F952
0x18002f85f  mov     [rsp+2A8h+Type], r14d
0x18002f864  mov     [rsp+2A8h+cbData], 208h
0x18002f86c  lea     rax, [rsp+2A8h+cbData]
0x18002f871  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002f876  lea     rax, [rsp+2A8h+Data]
0x18002f87b  mov     [rsp+2A8h+phkResult], rax; lpData
0x18002f880  lea     r9, [rsp+2A8h+Type]; lpType
0x18002f885  xor     r8d, r8d; lpReserved
0x18002f888  xor     edx, edx; lpValueName
0x18002f88a  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002f88f  call    cs:__imp_RegQueryValueExW
0x18002f895  mov     ebx, eax
0x18002f897  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002f89c  call    cs:__imp_RegCloseKey
0x18002f8a2  test    ebx, ebx
0x18002f8a4  jnz     loc_18002FA43
0x18002f8aa  lea     rax, [rsp+2A8h+Data]
0x18002f8af  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f8b3  inc     r8
0x18002f8b6  cmp     [rax+r8*2], r14w
0x18002f8bb  jnz     short loc_18002F8B3
0x18002f8bd  lea     rdx, [rsp+2A8h+Data]
0x18002f8c2  mov     rcx, rdi
0x18002f8c5  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f8ca  mov     edx, 2Eh ; '.'
0x18002f8cf  mov     rcx, rdi
0x18002f8d2  call    ?ReverseFind@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAH_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(wchar_t)
0x18002f8d7  test    eax, eax
0x18002f8d9  jle     loc_18002FA43
0x18002f8df  mov     rcx, [rdi]
0x18002f8e2  mov     r8d, [rcx-10h]
0x18002f8e6  sub     r8d, eax
0x18002f8e9  dec     r8d
0x18002f8ec  lea     rdx, [rsp+2A8h+var_260]
0x18002f8f1  mov     rcx, rdi
0x18002f8f4  call    ?Right@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(int)
0x18002f8f9  nop
0x18002f8fa  mov     rdx, [rax]
0x18002f8fd  lea     rcx, [rdx-18h]
0x18002f901  mov     rsi, [rdi]
0x18002f904  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18002f908  cmp     rcx, rsi
0x18002f90b  jz      short loc_18002F941
0x18002f90d  cmp     [rsi+10h], r14d
0x18002f911  jl      short loc_18002F934
0x18002f913  mov     rax, [rsi]
0x18002f916  cmp     [rcx], rax
0x18002f919  jnz     short loc_18002F934
0x18002f91b  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18002f920  mov     rbx, rax
0x18002f923  mov     rcx, rsi; this
0x18002f926  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002f92b  lea     rax, [rbx+18h]
0x18002f92f  mov     [rdi], rax
0x18002f932  jmp     short loc_18002F941
0x18002f934  mov     r8d, [rdx-10h]
0x18002f938  mov     rcx, rdi
0x18002f93b  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f940  nop
0x18002f941  lea     rcx, [rsp+2A8h+var_260]
0x18002f946  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002f94b  xor     eax, eax
0x18002f94d  jmp     loc_18002FA48
0x18002f952  mov     esi, 2
0x18002f957  cmp     eax, esi
0x18002f959  jnz     loc_18002FA43
0x18002f95f  lea     rax, [rsp+2A8h+hKey]
0x18002f964  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002f969  mov     r9d, ebx; samDesired
0x18002f96c  xor     r8d, r8d; ulOptions
0x18002f96f  lea     rdx, aOutlookApplica_1; "Outlook.Application.12"
0x18002f976  mov     rcx, r15; hKey
0x18002f979  call    cs:__imp_RegOpenKeyExW
0x18002f97f  test    eax, eax
0x18002f981  jnz     short loc_18002F9A7
0x18002f983  mov     ebx, r14d
0x18002f986  mov     r8d, esi
0x18002f989  lea     rdx, a12; "12"
0x18002f990  mov     rcx, rdi
0x18002f993  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f998  jmp     loc_18002FA2C
0x18002f99d  jmp     loc_18002FA30
0x18002f9a2  jmp     loc_18002FA30
0x18002f9a7  cmp     eax, esi
0x18002f9a9  jnz     loc_18002FA43
0x18002f9af  lea     rax, [rsp+2A8h+hKey]
0x18002f9b4  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002f9b9  mov     r9d, ebx; samDesired
0x18002f9bc  xor     r8d, r8d; ulOptions
0x18002f9bf  lea     rdx, aOutlookApplica_0; "Outlook.Application.11"
0x18002f9c6  mov     rcx, r15; hKey
0x18002f9c9  call    cs:__imp_RegOpenKeyExW
0x18002f9cf  test    eax, eax
0x18002f9d1  jnz     short loc_18002F9EE
0x18002f9d3  mov     ebx, r14d
0x18002f9d6  mov     r8d, esi
0x18002f9d9  lea     rdx, a11; "11"
0x18002f9e0  mov     rcx, rdi
0x18002f9e3  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f9e8  jmp     short loc_18002FA2C
0x18002f9ea  jmp     short loc_18002FA30
0x18002f9ec  jmp     short loc_18002FA30
0x18002f9ee  cmp     eax, esi
0x18002f9f0  jnz     short loc_18002FA43
0x18002f9f2  lea     rax, [rsp+2A8h+hKey]
0x18002f9f7  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002f9fc  mov     r9d, ebx; samDesired
0x18002f9ff  xor     r8d, r8d; ulOptions
0x18002fa02  lea     rdx, aOutlookApplica_2; "Outlook.Application.10"
0x18002fa09  mov     rcx, r15; hKey
0x18002fa0c  call    cs:__imp_RegOpenKeyExW
0x18002fa12  test    eax, eax
0x18002fa14  jnz     short loc_18002FA43
0x18002fa16  mov     ebx, r14d
0x18002fa19  mov     r8d, esi
0x18002fa1c  lea     rdx, a10; "10"
0x18002fa23  mov     rcx, rdi
0x18002fa26  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002fa2b  nop
0x18002fa2c  jmp     short loc_18002FA34
0x18002fa2e  jmp     short $+2
0x18002fa30  mov     ebx, [rsp+2A8h+cbData]
0x18002fa34  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002fa39  call    cs:__imp_RegCloseKey
0x18002fa3f  mov     eax, ebx
0x18002fa41  jmp     short loc_18002FA48
0x18002fa43  mov     eax, 1
0x18002fa48  mov     rcx, [rsp+2A8h+var_28]
0x18002fa50  xor     rcx, rsp; StackCookie
0x18002fa53  call    __security_check_cookie
0x18002fa58  lea     r11, [rsp+2A8h+var_18]
0x18002fa60  mov     rbx, [r11+28h]
0x18002fa64  mov     rsi, [r11+30h]
0x18002fa68  mov     rsp, r11
0x18002fa6b  pop     r15
0x18002fa6d  pop     r14
0x18002fa6f  pop     rdi
0x18002fa70  retn
```
