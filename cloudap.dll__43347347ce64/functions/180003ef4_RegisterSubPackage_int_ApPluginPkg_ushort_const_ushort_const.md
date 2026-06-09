# RegisterSubPackage(int,_ApPluginPkg *,ushort const *,ushort const *)

- ea: `0x180003ef4`
- end: `0x180004458`
- name: `?RegisterSubPackage@@YAJHPEAU_ApPluginPkg@@PEBG1@Z`
- size: `1380`
- prototype: `int(int, struct _ApPluginPkg *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000498c`
- `0x180018a20`
- `0x18004c808`

## callees

- `0x180003584`
- `0x180003e70`
- `0x180003ef4`
- `0x1800046f4`
- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18001b580`
- `0x18002fdec`
- `0x180032968`
- `0x18003ca18`
- `0x18003f660`
- `0x180042410`
- `0x18004cf50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000418a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000418a`
- `ntdll!RtlReleaseResource` at `0x1800043be`
- `ntdll!RtlReleaseResource` at `0x1800043be`
- `ntdll!RtlAcquireResourceShared` at `0x180003fbd`
- `ntdll!RtlAcquireResourceShared` at `0x180003fbd`
- `ntdll!RtlAvlRemoveNode` at `0x180004025`
- `ntdll!RtlAvlRemoveNode` at `0x180004036`
- `ntdll!RtlAvlRemoveNode` at `0x180004025`
- `ntdll!RtlAvlRemoveNode` at `0x180004036`
- `ntdll!RtlAvlInsertNodeEx` at `0x180004359`
- `ntdll!RtlAvlInsertNodeEx` at `0x1800043ad`
- `ntdll!RtlAvlInsertNodeEx` at `0x180004359`
- `ntdll!RtlAvlInsertNodeEx` at `0x1800043ad`

## string_xrefs

- `0x180003f80`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800040a6`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x180004118`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800041a1`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800041f9`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x180004244`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18000428f`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800042e3`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800043d2`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800041bc`: `RegCreateKeyEx`
- `0x18000425f`: `RtlStringCchCopyW`
- `0x1800042aa`: `RtlStringCchCopyW`

## pseudocode

```c
__int64 __fastcall RegisterSubPackage(
        int a1,
        struct _ApPluginPkg *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rbp
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rax
  unsigned int v11; // ebx
  const char *v12; // r9
  struct _RTL_BALANCED_NODE **v13; // r12
  __int64 *v14; // rbx
  int v15; // eax
  struct _RTL_BALANCED_NODE *v16; // rbx
  int v17; // eax
  const char *v18; // r9
  const char *v19; // r9
  LSTATUS v20; // eax
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  struct _RTL_BALANCED_NODE *v27; // rbx
  struct _RTL_BALANCED_NODE *v28; // rax
  __int64 v29; // r8
  struct _RTL_BALANCED_NODE *v30; // rbx
  struct _RTL_BALANCED_NODE *v31; // rax
  const char *v32; // r9
  const char *v33; // rax
  bool v34; // zf
  DWORD dwOptions[2]; // [rsp+20h] [rbp-B8h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-B8h]
  DWORD dwDisposition; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-80h] BYREF
  WCHAR SubKey[24]; // [rsp+60h] [rbp-78h] BYREF

  dwDisposition = 0;
  v8 = 0;
  if ( !a3 )
  {
    v11 = -1073741811;
LABEL_63:
    v32 = "";
    do
    {
      v33 = v32--;
      v34 = *v32 == 92;
      if ( *v32 == 92 )
        goto LABEL_67;
    }
    while ( v32 > "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" );
    v34 = *v32 == 92;
LABEL_67:
    if ( v34 )
      v32 = v33;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v32, 1616, "RtlStringCchLengthW", &Class);
    goto LABEL_70;
  }
  v9 = 16;
  v10 = a3;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = v9 == 0 ? 0xC000000D : 0;
  if ( !v9 )
    goto LABEL_63;
  v11 = RtlStringCchLengthW(a4, 0x100u, &v39);
  if ( v11 )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v12, 1619, "RtlStringCchLengthW", &Class);
    goto LABEL_70;
  }
  RtlAcquireResourceShared(*((PRTL_RESOURCE *)a2 + 45), 1u);
  v13 = (struct _RTL_BALANCED_NODE **)((char *)a2 + 376);
  v14 = (__int64 *)*((_QWORD *)a2 + 47);
  if ( v14 )
  {
    do
    {
      v15 = SubPkgTable_CompareNames(a3, (struct _RTL_BALANCED_NODE *)v14);
      if ( v15 >= 0 )
      {
        if ( v15 <= 0 )
          break;
        v14 = (__int64 *)v14[1];
      }
      else
      {
        v14 = (__int64 *)*v14;
      }
    }
    while ( v14 );
    if ( v14 )
    {
      if ( a1 || !CloudAPCompareStrings((PCWSTR)v14 + 40, a4) )
        goto LABEL_17;
      SCLockConvertSharedToExclusive(*((PRTL_RESOURCE *)a2 + 45));
      RtlAvlRemoveNode((char *)a2 + 376, v14);
      RtlAvlRemoveNode((char *)a2 + 384, v14 + 3);
      FreeSubPkg((struct _ApPluginSubPkg *)v14);
      SCLockConvertExclusiveToShared(*((PRTL_RESOURCE *)a2 + 45));
    }
  }
  SCLockConvertSharedToExclusive(*((PRTL_RESOURCE *)a2 + 45));
  v16 = *v13;
  if ( *v13 )
  {
    do
    {
      v17 = SubPkgTable_CompareNames(a3, v16);
      if ( v17 >= 0 )
      {
        if ( v17 <= 0 )
          break;
        v16 = v16->Children[1];
      }
      else
      {
        v16 = v16->Children[0];
      }
    }
    while ( v16 );
    if ( v16 )
    {
LABEL_17:
      v11 = 0;
      goto LABEL_61;
    }
  }
  v8 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(600);
  if ( !v8 )
  {
    v11 = -1073741801;
    v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v18, 1669, "AllocateLsaHeap", &Class);
    goto LABEL_61;
  }
  v11 = RtlStringCchPrintfW(SubKey, 0x18u, L"%ws\\%ws", L"SubPkgs", a3);
  if ( v11 )
  {
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptions[0] = 1678;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v19, *(_QWORD *)dwOptions, "RtlStringCchPrintfW", &Class);
    goto LABEL_61;
  }
  v20 = RegCreateKeyExW(*((HKEY *)a2 + 44), SubKey, 0, 0, 0, 0xF003Fu, 0, (PHKEY)(v8 + 592), &dwDisposition);
  v11 = v20;
  if ( v20 )
  {
    if ( v20 > 0 )
      v11 = (unsigned __int16)v20 | 0xC0070000;
    v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptionsa[0] = 1695;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v21, *(_QWORD *)dwOptionsa, "RegCreateKeyEx", &Class);
    goto LABEL_61;
  }
  if ( !a1 )
  {
    v11 = SetStringRegVal(*(HKEY *)(v8 + 592), 0, 0, L"AuthenticatingAuthorityDns", a4);
    if ( v11 )
    {
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      dwOptionsa[0] = 1710;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v22, *(_QWORD *)dwOptionsa, "SetStringRegVal", &Class);
      goto LABEL_61;
    }
  }
  v11 = RtlStringCchCopyW((unsigned __int16 *)(v8 + 48), 0x10u, a3);
  if ( v11 )
  {
    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptionsa[0] = 1714;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v23, *(_QWORD *)dwOptionsa, "RtlStringCchCopyW", &Class);
    goto LABEL_61;
  }
  v11 = RtlStringCchCopyW((unsigned __int16 *)(v8 + 80), 0x100u, a4);
  if ( v11 )
  {
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptionsa[0] = 1717;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v24, *(_QWORD *)dwOptionsa, "RtlStringCchCopyW", &Class);
    goto LABEL_61;
  }
  v11 = (*((__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 *))g_pLsaIdProvHostFunctionTable
         + 12))(
          *((_QWORD *)a2 + 2),
          a3,
          a4);
  if ( v11 )
  {
    v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptionsa[0] = 1723;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v26, *(_QWORD *)dwOptionsa, "RegisterSubProvider", &Class);
    goto LABEL_61;
  }
  v27 = *v13;
  LOBYTE(v25) = 0;
  if ( *v13 )
  {
    while ( 1 )
    {
      if ( (int)SubPkgTable_CompareNames(a3, v27) < 0 )
      {
        v28 = v27->Children[0];
        if ( !v27->Children[0] )
        {
          LOBYTE(v25) = 0;
          break;
        }
      }
      else
      {
        v28 = v27->Children[1];
        if ( !v28 )
        {
          LOBYTE(v25) = 1;
          break;
        }
      }
      v27 = v28;
    }
  }
  RtlAvlInsertNodeEx((char *)a2 + 376, v27, v25, v8);
  if ( !a4 )
    goto LABEL_60;
  LOBYTE(v29) = 0;
  v30 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)a2 + 48);
  if ( !v30 )
    goto LABEL_59;
  while ( (int)SubPkgTable_CompareDnsNames(a4, v30) >= 0 )
  {
    v31 = v30->Children[1];
    if ( !v31 )
    {
      LOBYTE(v29) = 1;
      goto LABEL_59;
    }
LABEL_57:
    v30 = v31;
  }
  v31 = v30->Children[0];
  if ( v30->Children[0] )
    goto LABEL_57;
  LOBYTE(v29) = 0;
LABEL_59:
  RtlAvlInsertNodeEx((char *)a2 + 384, v30, v29, v8 + 24);
LABEL_60:
  v8 = 0;
  v11 = 0;
LABEL_61:
  RtlReleaseResource(*((PRTL_RESOURCE *)a2 + 45));
LABEL_70:
  FreeSubPkg((struct _ApPluginSubPkg *)v8);
  return v11;
}

```

## disassembly

```asm
0x180003ef4  mov     [rsp+arg_0], rbx
0x180003ef9  push    rbp
0x180003efa  push    rsi
0x180003efb  push    rdi
0x180003efc  push    r12
0x180003efe  push    r13
0x180003f00  push    r14
0x180003f02  push    r15
0x180003f04  sub     rsp, 0A0h
0x180003f0b  mov     rax, cs:__security_cookie
0x180003f12  xor     rax, rsp
0x180003f15  mov     [rsp+0D8h+var_48], rax
0x180003f1d  xor     esi, esi
0x180003f1f  mov     r14, r9
0x180003f22  mov     [rsp+0D8h+dwDisposition], esi
0x180003f26  mov     rdi, r8
0x180003f29  mov     r15, rdx
0x180003f2c  mov     r13d, ecx
0x180003f2f  mov     ebp, esi
0x180003f31  test    r8, r8
0x180003f34  jz      loc_1800043C6
0x180003f3a  lea     edx, [rsi+10h]
0x180003f3d  mov     rax, r8
0x180003f40  cmp     [rax], si
0x180003f43  jz      short loc_180003F4F
0x180003f45  add     rax, 2
0x180003f49  sub     rdx, 1
0x180003f4d  jnz     short loc_180003F40
0x180003f4f  mov     rax, rdx
0x180003f52  neg     rax
0x180003f55  sbb     ebx, ebx
0x180003f57  not     ebx
0x180003f59  and     ebx, 0C000000Dh
0x180003f5f  test    rdx, rdx
0x180003f62  jz      loc_1800043CB
0x180003f68  lea     r8, [rsp+0D8h+var_80]; unsigned __int64 *
0x180003f6d  mov     edx, 100h; unsigned __int64
0x180003f72  mov     rcx, r14; unsigned __int16 *
0x180003f75  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180003f7a  mov     ebx, eax
0x180003f7c  test    eax, eax
0x180003f7e  jz      short loc_180003FB4
0x180003f80  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180003f87  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180003f8c  mov     r9, rax
0x180003f8f  lea     rax, Class
0x180003f96  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x180003f9b  lea     rax, aRtlstringcchle_0; "RtlStringCchLengthW"
0x180003fa2  mov     qword ptr [rsp+0D8h+samDesired], rax
0x180003fa7  mov     [rsp+0D8h+dwOptions], 653h
0x180003faf  jmp     loc_180004412
0x180003fb4  mov     rcx, [r15+168h]; Resource
0x180003fbb  mov     dl, 1; Wait
0x180003fbd  call    cs:__imp_RtlAcquireResourceShared
0x180003fc3  lea     r12, [r15+178h]
0x180003fca  mov     rbx, [r12]
0x180003fce  test    rbx, rbx
0x180003fd1  jz      short loc_180004050
0x180003fd3  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180003fd6  mov     rcx, rdi; SourceString
0x180003fd9  call    ?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)
0x180003fde  test    eax, eax
0x180003fe0  jns     short loc_180003FE7
0x180003fe2  mov     rbx, [rbx]
0x180003fe5  jmp     short loc_180003FED
0x180003fe7  jle     short loc_180003FF2
0x180003fe9  mov     rbx, [rbx+8]
0x180003fed  test    rbx, rbx
0x180003ff0  jnz     short loc_180003FD3
0x180003ff2  test    rbx, rbx
0x180003ff5  jz      short loc_180004050
0x180003ff7  test    r13d, r13d
0x180003ffa  jnz     short loc_18000400C
0x180003ffc  lea     rcx, [rbx+50h]; SourceString
0x180004000  mov     rdx, r14; PCWSTR
0x180004003  call    ?CloudAPCompareStrings@@YAHPEBG0@Z; CloudAPCompareStrings(ushort const *,ushort const *)
0x180004008  test    eax, eax
0x18000400a  jnz     short loc_180004013
0x18000400c  mov     ebx, esi
0x18000400e  jmp     loc_1800043B7
0x180004013  mov     rcx, [r15+168h]; Resource
0x18000401a  call    SCLockConvertSharedToExclusive
0x18000401f  mov     rdx, rbx
0x180004022  mov     rcx, r12
0x180004025  call    cs:__imp_RtlAvlRemoveNode
0x18000402b  lea     rdx, [rbx+18h]
0x18000402f  lea     rcx, [r15+180h]
0x180004036  call    cs:__imp_RtlAvlRemoveNode
0x18000403c  mov     rcx, rbx; struct _ApPluginSubPkg *
0x18000403f  call    ?FreeSubPkg@@YAXPEAU_ApPluginSubPkg@@@Z; FreeSubPkg(_ApPluginSubPkg *)
0x180004044  mov     rcx, [r15+168h]; Resource
0x18000404b  call    SCLockConvertExclusiveToShared
0x180004050  mov     rcx, [r15+168h]; Resource
0x180004057  call    SCLockConvertSharedToExclusive
0x18000405c  mov     rbx, [r12]
0x180004060  test    rbx, rbx
0x180004063  jz      short loc_180004089
0x180004065  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180004068  mov     rcx, rdi; SourceString
0x18000406b  call    ?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)
0x180004070  test    eax, eax
0x180004072  jns     short loc_180004079
0x180004074  mov     rbx, [rbx]
0x180004077  jmp     short loc_18000407F
0x180004079  jle     short loc_180004084
0x18000407b  mov     rbx, [rbx+8]
0x18000407f  test    rbx, rbx
0x180004082  jnz     short loc_180004065
0x180004084  test    rbx, rbx
0x180004087  jnz     short loc_18000400C
0x180004089  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180004090  mov     ecx, 258h
0x180004095  mov     rax, [rax+28h]
0x180004099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409e  mov     rbp, rax
0x1800040a1  test    rax, rax
0x1800040a4  jnz     short loc_1800040F0
0x1800040a6  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x1800040ad  mov     ebx, 0C0000017h
0x1800040b2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800040b7  mov     r9, rax
0x1800040ba  lea     rax, Class
0x1800040c1  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x1800040c6  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x1800040cd  mov     qword ptr [rsp+0D8h+samDesired], rax
0x1800040d2  mov     [rsp+0D8h+dwOptions], 685h
0x1800040da  mov     r8d, ebx
0x1800040dd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800040e4  xor     ecx, ecx
0x1800040e6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800040eb  jmp     loc_1800043B7
0x1800040f0  lea     r9, aSubpkgs; "SubPkgs"
0x1800040f7  mov     qword ptr [rsp+0D8h+dwOptions], rdi
0x1800040fc  lea     r8, aWsWs_1; "%ws\\%ws"
0x180004103  mov     edx, 18h; unsigned __int64
0x180004108  lea     rcx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x18000410d  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004112  mov     ebx, eax
0x180004114  test    eax, eax
0x180004116  jz      short loc_180004149
0x180004118  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18000411f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004124  mov     r9, rax
0x180004127  lea     rax, Class
0x18000412e  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x180004133  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18000413a  mov     qword ptr [rsp+0D8h+samDesired], rax
0x18000413f  mov     [rsp+0D8h+dwOptions], 68Eh
0x180004147  jmp     short loc_1800040DA
0x180004149  mov     rcx, [r15+160h]; hKey
0x180004150  lea     rax, [rsp+0D8h+dwDisposition]
0x180004155  mov     [rsp+0D8h+lpdwDisposition], rax; lpdwDisposition
0x18000415a  lea     rsi, [rbp+250h]
0x180004161  mov     [rsp+0D8h+phkResult], rsi; phkResult
0x180004166  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18000416b  mov     [rsp+0D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180004174  xor     r9d, r9d; lpClass
0x180004177  mov     [rsp+0D8h+samDesired], 0F003Fh; samDesired
0x18000417f  xor     r8d, r8d; Reserved
0x180004182  mov     [rsp+0D8h+dwOptions], 0; dwOptions
0x18000418a  call    cs:__imp_RegCreateKeyExW
0x180004190  mov     ebx, eax
0x180004192  test    eax, eax
0x180004194  jz      short loc_1800041D5
0x180004196  jle     short loc_1800041A1
0x180004198  movzx   ebx, ax
0x18000419b  or      ebx, 0C0070000h
0x1800041a1  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x1800041a8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800041ad  mov     r9, rax
0x1800041b0  lea     rax, Class
0x1800041b7  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x1800041bc  lea     rax, aRegcreatekeyex; "RegCreateKeyEx"
0x1800041c3  mov     qword ptr [rsp+0D8h+samDesired], rax
0x1800041c8  mov     [rsp+0D8h+dwOptions], 69Fh
0x1800041d0  jmp     loc_1800040DA
0x1800041d5  test    r13d, r13d
0x1800041d8  jnz     short loc_18000422D
0x1800041da  mov     rcx, [rsi]; HKEY
0x1800041dd  lea     r9, aAuthenticating_0; "AuthenticatingAuthorityDns"
0x1800041e4  xor     r8d, r8d; unsigned __int16 *
0x1800041e7  mov     qword ptr [rsp+0D8h+dwOptions], r14; unsigned __int16 *
0x1800041ec  xor     edx, edx; unsigned __int16 *
0x1800041ee  call    ?SetStringRegVal@@YAJPEAUHKEY__@@PEBG111@Z; SetStringRegVal(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800041f3  mov     ebx, eax
0x1800041f5  test    eax, eax
0x1800041f7  jz      short loc_18000422D
0x1800041f9  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180004200  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004205  mov     r9, rax
0x180004208  lea     rax, Class
0x18000420f  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x180004214  lea     rax, aSetstringregva_10; "SetStringRegVal"
0x18000421b  mov     qword ptr [rsp+0D8h+samDesired], rax
0x180004220  mov     [rsp+0D8h+dwOptions], 6AEh
0x180004228  jmp     loc_1800040DA
0x18000422d  lea     rcx, [rbp+30h]; unsigned __int16 *
0x180004231  mov     r8, rdi; unsigned __int16 *
0x180004234  mov     edx, 10h; unsigned __int64
0x180004239  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000423e  mov     ebx, eax
0x180004240  test    eax, eax
0x180004242  jz      short loc_180004278
0x180004244  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18000424b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004250  mov     r9, rax
0x180004253  lea     rax, Class
0x18000425a  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x18000425f  lea     rax, aRtlstringcchco_0; "RtlStringCchCopyW"
0x180004266  mov     qword ptr [rsp+0D8h+samDesired], rax
0x18000426b  mov     [rsp+0D8h+dwOptions], 6B2h
0x180004273  jmp     loc_1800040DA
0x180004278  lea     rcx, [rbp+50h]; unsigned __int16 *
0x18000427c  mov     r8, r14; unsigned __int16 *
0x18000427f  mov     edx, 100h; unsigned __int64
0x180004284  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004289  mov     ebx, eax
0x18000428b  test    eax, eax
0x18000428d  jz      short loc_1800042C3
0x18000428f  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180004296  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000429b  mov     r9, rax
0x18000429e  lea     rax, Class
0x1800042a5  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x1800042aa  lea     rax, aRtlstringcchco_0; "RtlStringCchCopyW"
0x1800042b1  mov     qword ptr [rsp+0D8h+samDesired], rax
0x1800042b6  mov     [rsp+0D8h+dwOptions], 6B5h
0x1800042be  jmp     loc_1800040DA
0x1800042c3  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x1800042ca  mov     r8, r14
0x1800042cd  mov     rcx, [r15+10h]
0x1800042d1  mov     rdx, rdi
0x1800042d4  mov     rax, [rax+60h]
0x1800042d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042dd  mov     ebx, eax
0x1800042df  test    eax, eax
0x1800042e1  jz      short loc_180004317
0x1800042e3  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x1800042ea  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800042ef  mov     r9, rax
0x1800042f2  lea     rax, Class
0x1800042f9  mov     [rsp+0D8h+lpSecurityAttributes], rax
0x1800042fe  lea     rax, aRegistersubpro; "RegisterSubProvider"
0x180004305  mov     qword ptr [rsp+0D8h+samDesired], rax
0x18000430a  mov     [rsp+0D8h+dwOptions], 6BBh
0x180004312  jmp     loc_1800040DA
0x180004317  mov     rbx, [r12]
0x18000431b  xor     r8b, r8b
0x18000431e  test    rbx, rbx
0x180004321  jz      short loc_180004350
0x180004323  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180004326  mov     rcx, rdi; SourceString
0x180004329  call    ?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)
0x18000432e  test    eax, eax
0x180004330  js      short loc_180004340
0x180004332  mov     rax, [rbx+8]
0x180004336  test    rax, rax
0x180004339  jnz     short loc_180004348
0x18000433b  mov     r8b, 1
0x18000433e  jmp     short loc_180004350
0x180004340  mov     rax, [rbx]
0x180004343  test    rax, rax
0x180004346  jz      short loc_18000434D
0x180004348  mov     rbx, rax
0x18000434b  jmp     short loc_180004323
0x18000434d  xor     r8b, r8b
0x180004350  mov     r9, rbp
0x180004353  mov     rdx, rbx
0x180004356  mov     rcx, r12
0x180004359  call    cs:__imp_RtlAvlInsertNodeEx
0x18000435f  test    r14, r14
0x180004362  jz      short loc_1800043B3
0x180004364  lea     rdi, [r15+180h]
0x18000436b  xor     r8b, r8b
0x18000436e  mov     rbx, [rdi]
0x180004371  test    rbx, rbx
0x180004374  jz      short loc_1800043A3
0x180004376  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180004379  mov     rcx, r14; void *
0x18000437c  call    ?SubPkgTable_CompareDnsNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareDnsNames(void *,_RTL_BALANCED_NODE *)
0x180004381  test    eax, eax
0x180004383  js      short loc_180004393
0x180004385  mov     rax, [rbx+8]
0x180004389  test    rax, rax
0x18000438c  jnz     short loc_18000439B
0x18000438e  mov     r8b, 1
0x180004391  jmp     short loc_1800043A3
0x180004393  mov     rax, [rbx]
0x180004396  test    rax, rax
0x180004399  jz      short loc_1800043A0
0x18000439b  mov     rbx, rax
0x18000439e  jmp     short loc_180004376
0x1800043a0  xor     r8b, r8b
0x1800043a3  lea     r9, [rbp+18h]
0x1800043a7  mov     rdx, rbx
0x1800043aa  mov     rcx, rdi
0x1800043ad  call    cs:__imp_RtlAvlInsertNodeEx
0x1800043b3  xor     ebp, ebp
0x1800043b5  xor     ebx, ebx
0x1800043b7  mov     rcx, [r15+168h]; Resource
  ... truncated ...
```
