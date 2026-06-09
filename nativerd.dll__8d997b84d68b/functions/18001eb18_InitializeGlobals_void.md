# InitializeGlobals(void)

- ea: `0x18001eb18`
- end: `0x18001efb3`
- name: `?InitializeGlobals@@YAJXZ`
- size: `1179`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fa70`

## callees

- `0x18001b498`
- `0x18001c250`
- `0x18001e300`
- `0x18001e508`
- `0x18001eb18`
- `0x18001fd38`
- `0x18002ab9c`
- `0x180059794`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001ec0c`
- `msvcrt!wcsrchr` at `0x18001ec0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebe5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001eba8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001eba8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ebdb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ebdb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ec77`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ec77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ef22`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ef22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eeea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eeea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef7a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ef8a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ef8a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ec68`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ec68`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001eb69`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001eb69`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001ee8a`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001ee8a`
- `iisutil!PuCreateDebugPrintsObject` at `0x18001eb8f`
- `iisutil!PuCreateDebugPrintsObject` at `0x18001eb8f`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18001ebb7`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18001ebb7`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001ec37`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001ec37`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001ec53`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001ec53`

## string_xrefs

- `0x18001eba1`: `Unable to Create Debug Print Object \n`
- `0x18001ec47`: `\IISRES.DLL`
- `0x18001eedc`: `Software\Microsoft\InetStp\Configuration`
- `0x18001ef1b`: `MaxWebConfigFileSizeInKB`
- `0x18001ee69`: `TOKEN_CACHE`
- `0x18001ebb0`: `System\CurrentControlSet\Services\W3SVC\Parameters\nativerd`

## pseudocode

```c
__int64 InitializeGlobals(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  bool v2; // cc
  wchar_t *v3; // rax
  const WCHAR *Str; // rax
  _DWORD *v5; // rax
  struct FAST_STRING_TABLE *v6; // rbx
  unsigned int v7; // edx
  unsigned int i; // edi
  unsigned int v9; // esi
  _QWORD *v10; // rax
  __int64 v11; // rsi
  SUPPORT_ERROR_INFO *v12; // rax
  void *v13; // rax
  CLKRHashTable *v14; // rax
  TOKEN_CACHE *v15; // rbx
  TOKEN_CACHE *v16; // rcx
  unsigned int v17; // edx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v24[256]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v22, v24, 0x100u);
  hKey = 0;
  Type = 0;
  cbData = 0;
  g_pDebug = PuCreateDebugPrintsObject("nativerd", 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\nativerd", 0);
  g_initStatus = 1;
  if ( !GetModuleFileNameW(g_hModule, Filename, 0x104u) )
    goto LABEL_4;
  v3 = wcsrchr(Filename, 0x5Cu);
  if ( !v3 )
  {
    v1 = -2147024883;
    goto LABEL_40;
  }
  v1 = STRU::Copy((STRU *)v22, Filename, v3 - Filename);
  if ( v1 >= 0 )
  {
    v1 = STRU::Append((STRU *)v22, L"\\IISRES.DLL");
    if ( v1 >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v22);
      g_hResourceDll = LoadLibraryExW(Str, 0, 8u);
      if ( !g_hResourceDll )
      {
LABEL_4:
        LastError = GetLastError();
        v1 = LastError;
        v2 = LastError <= 0;
        goto LABEL_5;
      }
      g_initStatus = 2;
      LastError = McGenEventRegister_EtwEventRegister();
      v1 = LastError;
      v2 = LastError <= 0;
      if ( LastError )
      {
LABEL_5:
        if ( !v2 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_40;
      }
      g_initStatus = 3;
      v5 = operator new(0xC80u);
      v6 = (struct FAST_STRING_TABLE *)v5;
      if ( !v5 )
      {
        v1 = -2147024888;
        goto LABEL_39;
      }
      v5[4] = 65;
      *(_QWORD *)v5 = &FAST_STRING_TABLE::`vftable';
      *((_QWORD *)v5 + 1) = &g_rgFastStrings;
      memset_0(v5 + 6, 0, 0xC68u);
      g_pFastStringTable = v6;
      for ( i = 0; ; ++i )
      {
        if ( i >= *((_DWORD *)v6 + 4) )
        {
          g_initStatus = 4;
          v1 = CONFIG_SECTION::Initialize();
          if ( v1 < 0 )
            goto LABEL_40;
          CONFIG_DOM_NODE::sm_pTraceLog = 0;
          CONFIG_ELEMENT::sm_pTraceLog = 0;
          SCHEMA_ELEMENT::sm_pTraceLog = 0;
          LOCATION_CONTEXT::s_pTraceLog = 0;
          SEARCH_RESULT::sm_pTraceLog = 0;
          g_initStatus = 12;
          v12 = (SUPPORT_ERROR_INFO *)operator new(0x10u);
          if ( v12 )
          {
            g_pSupportErrorInfo = SUPPORT_ERROR_INFO::SUPPORT_ERROR_INFO(v12);
            if ( g_pSupportErrorInfo )
            {
              g_initStatus = 13;
              v13 = operator new(1u);
              if ( v13 )
              {
                g_pExtensionTable = v13;
                CONFIG_EXCEPTION::sm_pTraceLog = 0;
                g_initStatus = 16;
                v14 = (CLKRHashTable *)operator new(0x48u);
                v15 = v14;
                if ( v14 )
                {
                  CLKRHashTable::CLKRHashTable(
                    v14,
                    "TOKEN_CACHE",
                    (unsigned __int64 (*)(const void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
                    (unsigned int (*)(unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
                    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
                    (void (*)(const void *, int))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
                    4.0,
                    1u,
                    0,
                    0);
                  g_pTokenCache = v15;
                  v1 = TOKEN_CACHE::Initialize(v16);
                  if ( v1 >= 0 )
                  {
                    g_initStatus = 17;
                    if ( !RegOpenKeyExW(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\InetStp\\Configuration",
                            0,
                            0x20019u,
                            &hKey) )
                    {
                      cbData = 4;
                      if ( RegQueryValueExW(
                             hKey,
                             L"MaxWebConfigFileSizeInKB",
                             0,
                             &Type,
                             &g_dwMaxWebConfigFileSizeInKb,
                             &cbData)
                        || Type != 4
                        || cbData != 4 )
                      {
                        *(_DWORD *)&g_dwMaxWebConfigFileSizeInKb = 250;
                      }
                    }
                  }
                  else
                  {
                    if ( g_pTokenCache )
                      TOKEN_CACHE::`scalar deleting destructor'(g_pTokenCache, v17);
                    g_pTokenCache = 0;
                  }
                  goto LABEL_40;
                }
                g_pTokenCache = 0;
              }
              else
              {
                g_pExtensionTable = 0;
              }
            }
          }
          else
          {
            g_pSupportErrorInfo = 0;
          }
          v1 = -2147024888;
          goto LABEL_40;
        }
        v9 = HashString(*(const unsigned __int16 **)(*((_QWORD *)v6 + 1) + 8LL * i), v7);
        v10 = operator new(0x10u);
        if ( !v10 )
          break;
        *v10 = *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL * i);
        v10[1] = 0;
        v7 = v9 / 0x18D;
        v11 = v9 % 0x18D;
        v10[1] = *((_QWORD *)v6 + v11 + 3);
        *((_QWORD *)v6 + v11 + 3) = v10;
      }
      v1 = -2147024888;
      if ( g_pFastStringTable )
        (**(void (__fastcall ***)(struct FAST_STRING_TABLE *, __int64, _QWORD))g_pFastStringTable)(
          g_pFastStringTable,
          1,
          0);
LABEL_39:
      g_pFastStringTable = 0;
    }
  }
LABEL_40:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  STRU::~STRU((STRU *)v22);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001eb18  push    rbp
0x18001eb1a  push    rbx
0x18001eb1b  push    rsi
0x18001eb1c  push    rdi
0x18001eb1d  push    r12
0x18001eb1f  push    r14
0x18001eb21  push    r15
0x18001eb23  lea     rbp, [rsp-3C0h]
0x18001eb2b  sub     rsp, 4C0h
0x18001eb32  mov     rax, cs:__security_cookie
0x18001eb39  xor     rax, rsp
0x18001eb3c  mov     [rbp+3F0h+var_40], rax
0x18001eb43  xor     edx, edx; Val
0x18001eb45  lea     rcx, [rbp+3F0h+var_240]; void *
0x18001eb4c  mov     r8d, 200h; Size
0x18001eb52  call    memset_0
0x18001eb57  mov     r8d, 100h
0x18001eb5d  lea     rdx, [rbp+3F0h+var_240]
0x18001eb64  lea     rcx, [rsp+4F0h+var_490]
0x18001eb69  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001eb6f  xor     r15d, r15d
0x18001eb72  lea     rcx, aNativerd; "nativerd"
0x18001eb79  mov     [rsp+4F0h+hKey], r15
0x18001eb7e  mov     [rsp+4F0h+Type], r15d
0x18001eb83  mov     [rsp+4F0h+cbData], r15d
0x18001eb88  lea     r12d, [r15+1]
0x18001eb8c  mov     edx, r12d
0x18001eb8f  call    cs:__imp_PuCreateDebugPrintsObject
0x18001eb95  mov     cs:g_pDebug, rax
0x18001eb9c  test    rax, rax
0x18001eb9f  jnz     short loc_18001EBAE
0x18001eba1  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x18001eba8  call    cs:__imp_OutputDebugStringA
0x18001ebae  xor     edx, edx
0x18001ebb0  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18001ebb7  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x18001ebbd  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x18001ebc4  lea     rdx, [rbp+3F0h+Filename]; lpFilename
0x18001ebc8  mov     r8d, 104h; nSize
0x18001ebce  mov     cs:g_dwDebugFlags, eax
0x18001ebd4  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, r12d; GLOBAL_INIT_STATUS g_initStatus
0x18001ebdb  call    cs:__imp_GetModuleFileNameW
0x18001ebe1  test    eax, eax
0x18001ebe3  jnz     short loc_18001EC03
0x18001ebe5  call    cs:__imp_GetLastError
0x18001ebeb  mov     ebx, eax
0x18001ebed  test    eax, eax
0x18001ebef  jle     loc_18001EF70
0x18001ebf5  movzx   ebx, ax
0x18001ebf8  or      ebx, 80070000h
0x18001ebfe  jmp     loc_18001EF70
0x18001ec03  mov     edx, 5Ch ; '\'; Ch
0x18001ec08  lea     rcx, [rbp+3F0h+Filename]; Str
0x18001ec0c  call    cs:__imp_wcsrchr
0x18001ec12  test    rax, rax
0x18001ec15  jnz     short loc_18001EC21
0x18001ec17  mov     ebx, 8007000Dh
0x18001ec1c  jmp     loc_18001EF70
0x18001ec21  lea     rcx, [rbp+3F0h+Filename]
0x18001ec25  sub     rax, rcx
0x18001ec28  lea     rdx, [rbp+3F0h+Filename]
0x18001ec2c  sar     rax, 1
0x18001ec2f  lea     rcx, [rsp+4F0h+var_490]
0x18001ec34  mov     r8d, eax
0x18001ec37  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001ec3d  mov     ebx, eax
0x18001ec3f  test    eax, eax
0x18001ec41  js      loc_18001EF70
0x18001ec47  lea     rdx, aIisresDll; "\\IISRES.DLL"
0x18001ec4e  lea     rcx, [rsp+4F0h+var_490]
0x18001ec53  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001ec59  mov     ebx, eax
0x18001ec5b  test    eax, eax
0x18001ec5d  js      loc_18001EF70
0x18001ec63  lea     rcx, [rsp+4F0h+var_490]
0x18001ec68  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ec6e  xor     edx, edx; hFile
0x18001ec70  mov     rcx, rax; lpLibFileName
0x18001ec73  lea     r8d, [rdx+8]; dwFlags
0x18001ec77  call    cs:__imp_LoadLibraryExW
0x18001ec7d  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResourceDll
0x18001ec84  test    rax, rax
0x18001ec87  jz      loc_18001EBE5
0x18001ec8d  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, 2; GLOBAL_INIT_STATUS g_initStatus
0x18001ec97  call    McGenEventRegister_EtwEventRegister
0x18001ec9c  mov     ebx, eax
0x18001ec9e  test    eax, eax
0x18001eca0  jnz     loc_18001EBEF
0x18001eca6  mov     ecx, 0C80h; Size
0x18001ecab  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, 3; GLOBAL_INIT_STATUS g_initStatus
0x18001ecb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ecba  mov     rbx, rax
0x18001ecbd  test    rax, rax
0x18001ecc0  jz      loc_18001EF64
0x18001ecc6  lea     rax, ??_7FAST_STRING_TABLE@@6B@; const FAST_STRING_TABLE::`vftable'
0x18001eccd  mov     dword ptr [rbx+10h], 41h ; 'A'
0x18001ecd4  mov     [rbx], rax
0x18001ecd7  lea     rcx, [rbx+18h]; void *
0x18001ecdb  lea     rax, ?g_rgFastStrings@@3PAPEBGA; ushort const * near * g_rgFastStrings
0x18001ece2  xor     edx, edx; Val
0x18001ece4  mov     r8d, 0C68h; Size
0x18001ecea  mov     [rbx+8], rax
0x18001ecee  call    memset_0
0x18001ecf3  mov     cs:?g_pFastStringTable@@3PEAVFAST_STRING_TABLE@@EA, rbx; FAST_STRING_TABLE * g_pFastStringTable
0x18001ecfa  mov     edi, r15d
0x18001ecfd  cmp     edi, [rbx+10h]
0x18001ed00  jnb     loc_18001ED86
0x18001ed06  mov     rcx, [rbx+8]
0x18001ed0a  mov     r14d, edi
0x18001ed0d  mov     rcx, [rcx+r14*8]; unsigned __int16 *
0x18001ed11  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x18001ed16  mov     ecx, 10h; Size
0x18001ed1b  mov     esi, eax
0x18001ed1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ed22  mov     r8, rax
0x18001ed25  test    rax, rax
0x18001ed28  jz      short loc_18001ED5E
0x18001ed2a  mov     rcx, [rbx+8]
0x18001ed2e  mov     rdx, [rcx+r14*8]
0x18001ed32  mov     [rax], rdx
0x18001ed35  mov     [rax+8], r15
0x18001ed39  mov     eax, 2944FF5Bh
0x18001ed3e  mul     esi
0x18001ed40  shr     edx, 6
0x18001ed43  imul    ecx, edx, 18Dh
0x18001ed49  sub     esi, ecx
0x18001ed4b  add     edi, r12d
0x18001ed4e  mov     rax, [rbx+rsi*8+18h]
0x18001ed53  mov     [r8+8], rax
0x18001ed57  mov     [rbx+rsi*8+18h], r8
0x18001ed5c  jmp     short loc_18001ECFD
0x18001ed5e  mov     rcx, cs:?g_pFastStringTable@@3PEAVFAST_STRING_TABLE@@EA; FAST_STRING_TABLE * g_pFastStringTable
0x18001ed65  mov     ebx, 80070008h
0x18001ed6a  test    rcx, rcx
0x18001ed6d  jz      loc_18001EF69
0x18001ed73  mov     rax, [rcx]
0x18001ed76  mov     edx, r12d
0x18001ed79  mov     rax, [rax]
0x18001ed7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed81  jmp     loc_18001EF69
0x18001ed86  mov     edi, 4
0x18001ed8b  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, edi; GLOBAL_INIT_STATUS g_initStatus
0x18001ed91  call    ?Initialize@CONFIG_SECTION@@SAJXZ; CONFIG_SECTION::Initialize(void)
0x18001ed96  mov     ebx, eax
0x18001ed98  test    eax, eax
0x18001ed9a  js      loc_18001EF70
0x18001eda0  lea     ecx, [rdi+0Ch]; Size
0x18001eda3  mov     cs:?sm_pTraceLog@CONFIG_DOM_NODE@@0PEAU_TRACE_LOG@@EA, r15; _TRACE_LOG * CONFIG_DOM_NODE::sm_pTraceLog
0x18001edaa  mov     cs:?sm_pTraceLog@CONFIG_ELEMENT@@0PEAU_TRACE_LOG@@EA, r15; _TRACE_LOG * CONFIG_ELEMENT::sm_pTraceLog
0x18001edb1  mov     cs:?sm_pTraceLog@SCHEMA_ELEMENT@@0PEAU_TRACE_LOG@@EA, r15; _TRACE_LOG * SCHEMA_ELEMENT::sm_pTraceLog
0x18001edb8  mov     cs:?s_pTraceLog@LOCATION_CONTEXT@@0PEAU_TRACE_LOG@@EA, r15; _TRACE_LOG * LOCATION_CONTEXT::s_pTraceLog
0x18001edbf  mov     cs:?sm_pTraceLog@SEARCH_RESULT@@0PEAU_TRACE_LOG@@EA, r15; _TRACE_LOG * SEARCH_RESULT::sm_pTraceLog
0x18001edc6  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, 0Ch; GLOBAL_INIT_STATUS g_initStatus
0x18001edd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001edd5  test    rax, rax
0x18001edd8  jz      loc_18001EF56
0x18001edde  mov     rcx, rax; this
0x18001ede1  call    ??0SUPPORT_ERROR_INFO@@QEAA@XZ; SUPPORT_ERROR_INFO::SUPPORT_ERROR_INFO(void)
0x18001ede6  mov     cs:?g_pSupportErrorInfo@@3PEAVSUPPORT_ERROR_INFO@@EA, rax; SUPPORT_ERROR_INFO * g_pSupportErrorInfo
0x18001eded  test    rax, rax
0x18001edf0  jz      loc_18001EF5D
0x18001edf6  mov     rcx, r12; Size
0x18001edf9  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, 0Dh; GLOBAL_INIT_STATUS g_initStatus
0x18001ee03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ee08  test    rax, rax
0x18001ee0b  jz      loc_18001EF4D
0x18001ee11  lea     ecx, [rdi+44h]; Size
0x18001ee14  mov     cs:?g_pExtensionTable@@3PEAVEXTENSION_TABLE@@EA, rax; EXTENSION_TABLE * g_pExtensionTable
0x18001ee1b  mov     cs:?sm_pTraceLog@CONFIG_EXCEPTION@@0PEAU_TRACE_LOG@@EA, r15; _TRACE_LOG * CONFIG_EXCEPTION::sm_pTraceLog
0x18001ee22  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, 10h; GLOBAL_INIT_STATUS g_initStatus
0x18001ee2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ee31  mov     rbx, rax
0x18001ee34  test    rax, rax
0x18001ee37  jz      loc_18001EF44
0x18001ee3d  movsd   xmm0, cs:__real@4010000000000000
0x18001ee45  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18001ee4c  mov     [rsp+4F0h+var_4A8], r15b
0x18001ee51  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18001ee58  mov     [rsp+4F0h+var_4B0], r15d
0x18001ee5d  lea     r8, ?_ExtractKey@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x18001ee64  mov     [rsp+4F0h+var_4B8], r12d
0x18001ee69  lea     rdx, aTokenCache; "TOKEN_CACHE"
0x18001ee70  movsd   [rsp+4F0h+var_4C0], xmm0
0x18001ee76  mov     rcx, rbx
0x18001ee79  mov     [rsp+4F0h+lpcbData], rax
0x18001ee7e  lea     rax, ?_EqualKeys@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18001ee85  mov     [rsp+4F0h+phkResult], rax
0x18001ee8a  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001ee90  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, rbx; TOKEN_CACHE * g_pTokenCache
0x18001ee97  call    ?Initialize@TOKEN_CACHE@@QEAAJXZ; TOKEN_CACHE::Initialize(void)
0x18001ee9c  mov     ebx, eax
0x18001ee9e  test    eax, eax
0x18001eea0  jns     short loc_18001EEBF
0x18001eea2  mov     rcx, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; this
0x18001eea9  test    rcx, rcx
0x18001eeac  jz      short loc_18001EEB3
0x18001eeae  call    ??_GTOKEN_CACHE@@QEAAPEAXI@Z; TOKEN_CACHE::`scalar deleting destructor'(uint)
0x18001eeb3  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, r15; TOKEN_CACHE * g_pTokenCache
0x18001eeba  jmp     loc_18001EF70
0x18001eebf  lea     rax, [rsp+4F0h+hKey]
0x18001eec4  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, 11h; GLOBAL_INIT_STATUS g_initStatus
0x18001eece  mov     r9d, 20019h; samDesired
0x18001eed4  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18001eed9  xor     r8d, r8d; ulOptions
0x18001eedc  lea     rdx, SubKey; "Software\\Microsoft\\InetStp\\Configura"...
0x18001eee3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eeea  call    cs:__imp_RegOpenKeyExW
0x18001eef0  test    eax, eax
0x18001eef2  jnz     short loc_18001EF70
0x18001eef4  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18001eef9  lea     rax, [rsp+4F0h+cbData]
0x18001eefe  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x18001ef03  lea     r9, [rsp+4F0h+Type]; lpType
0x18001ef08  lea     rax, ?g_dwMaxWebConfigFileSizeInKb@@3KA; ulong g_dwMaxWebConfigFileSizeInKb
0x18001ef0f  mov     [rsp+4F0h+cbData], edi
0x18001ef13  xor     r8d, r8d; lpReserved
0x18001ef16  mov     [rsp+4F0h+phkResult], rax; lpData
0x18001ef1b  lea     rdx, ValueName; "MaxWebConfigFileSizeInKB"
0x18001ef22  call    cs:__imp_RegQueryValueExW
0x18001ef28  test    eax, eax
0x18001ef2a  jnz     short loc_18001EF38
0x18001ef2c  cmp     [rsp+4F0h+Type], edi
0x18001ef30  jnz     short loc_18001EF38
0x18001ef32  cmp     [rsp+4F0h+cbData], edi
0x18001ef36  jz      short loc_18001EF70
0x18001ef38  mov     cs:?g_dwMaxWebConfigFileSizeInKb@@3KA, 0FAh; ulong g_dwMaxWebConfigFileSizeInKb
0x18001ef42  jmp     short loc_18001EF70
0x18001ef44  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, r15; TOKEN_CACHE * g_pTokenCache
0x18001ef4b  jmp     short loc_18001EF5D
0x18001ef4d  mov     cs:?g_pExtensionTable@@3PEAVEXTENSION_TABLE@@EA, r15; EXTENSION_TABLE * g_pExtensionTable
0x18001ef54  jmp     short loc_18001EF5D
0x18001ef56  mov     cs:?g_pSupportErrorInfo@@3PEAVSUPPORT_ERROR_INFO@@EA, r15; SUPPORT_ERROR_INFO * g_pSupportErrorInfo
0x18001ef5d  mov     ebx, 80070008h
0x18001ef62  jmp     short loc_18001EF70
0x18001ef64  mov     ebx, 80070008h
0x18001ef69  mov     cs:?g_pFastStringTable@@3PEAVFAST_STRING_TABLE@@EA, r15; FAST_STRING_TABLE * g_pFastStringTable
0x18001ef70  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18001ef75  test    rcx, rcx
0x18001ef78  jz      short loc_18001EF85
0x18001ef7a  call    cs:__imp_RegCloseKey
0x18001ef80  mov     [rsp+4F0h+hKey], r15
0x18001ef85  lea     rcx, [rsp+4F0h+var_490]
0x18001ef8a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ef90  mov     eax, ebx
0x18001ef92  mov     rcx, [rbp+3F0h+var_40]
0x18001ef99  xor     rcx, rsp; StackCookie
0x18001ef9c  call    __security_check_cookie
0x18001efa1  add     rsp, 4C0h
0x18001efa8  pop     r15
0x18001efaa  pop     r14
0x18001efac  pop     r12
0x18001efae  pop     rdi
0x18001efaf  pop     rsi
0x18001efb0  pop     rbx
0x18001efb1  pop     rbp
0x18001efb2  retn
```
