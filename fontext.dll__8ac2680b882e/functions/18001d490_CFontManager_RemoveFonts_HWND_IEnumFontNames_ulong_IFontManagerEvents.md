# CFontManager::RemoveFonts(HWND__ *,IEnumFontNames *,ulong,IFontManagerEvents *)

- ea: `0x18001d490`
- end: `0x18001d860`
- name: `?RemoveFonts@CFontManager@@UEAAJPEAUHWND__@@PEAUIEnumFontNames@@KPEAUIFontManagerEvents@@@Z`
- size: `976`
- prototype: `int(CFontManager *__hidden this, HWND, struct IEnumFontNames *, unsigned int, struct IFontManagerEvents *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006f10`
- `0x180006f50`
- `0x180007060`
- `0x180007f30`
- `0x18001317c`
- `0x18001cba4`
- `0x18001d490`
- `0x18001dad0`
- `0x18001e168`
- `0x18001e544`
- `0x18001eda8`
- `0x18001ee80`
- `0x18001f2b8`
- `0x18002265c`
- `0x1800230fc`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18001d7c0`
- `SHELL32!__imp_ILFree` at `0x18001d7c0`
- `SHLWAPI!PathFileExistsW` at `0x18001d52c`
- `SHLWAPI!PathFileExistsW` at `0x18001d52c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d692`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d6b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d692`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d6b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7ff`

## pseudocode

```c
__int64 __fastcall CFontManager::RemoveFonts(
        CFontManager *this,
        HWND a2,
        struct IEnumFontNames *a3,
        unsigned int a4,
        struct IFontManagerEvents *a5)
{
  unsigned int v5; // ebx
  int v7; // r14d
  int v8; // r15d
  CFontManager *v9; // rcx
  __int64 v10; // rax
  WCHAR *v11; // r15
  unsigned __int64 v12; // r13
  struct CFontAgent *v13; // r14
  int v14; // eax
  int v15; // r12d
  CFontManager *v16; // rcx
  unsigned __int64 i; // rbx
  int v18; // eax
  int v19; // edi
  bool v20; // zf
  HWND v21; // rdi
  int v22; // ebx
  ITEMIDLIST *v23; // rcx
  unsigned int v24; // edi
  struct IFontManagerEvents *v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszPath; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h]
  HWND v30; // [rsp+48h] [rbp-B8h]
  unsigned int v31; // [rsp+50h] [rbp-B0h]
  struct CFontAgent *v32; // [rsp+58h] [rbp-A8h] BYREF
  CFontManager *v33; // [rsp+60h] [rbp-A0h]
  WCHAR *v34; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  _BYTE v38[24]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR String2[264]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = 0;
  v31 = a4;
  v30 = a2;
  v33 = this;
  if ( a5 )
    (*(void (__fastcall **)(struct IFontManagerEvents *))(*(_QWORD *)a5 + 56LL))(a5);
  CFontEnumAgents::CFontEnumAgents((CFontEnumAgents *)v38, a3, 0);
  v7 = CFontEnumAgents::AgentCount((CFontEnumAgents *)v38);
  pszPath = 0;
  v8 = 0;
  while ( !(*(unsigned int (__fastcall **)(struct IEnumFontNames *, LPCWSTR *))(*(_QWORD *)a3 + 24LL))(a3, &pszPath) )
  {
    if ( !PathFileExistsW(pszPath) )
    {
      CFontManager::_RemovePathFromRegistry(v9, (unsigned __int16 *)pszPath);
      v8 = 1;
    }
  }
  v10 = *(_QWORD *)a3;
  v29 = v8;
  (*(void (__fastcall **)(struct IEnumFontNames *))(v10 + 32))(a3);
  CleanUpDeletedUserFonts();
  if ( v7 <= 0 )
    goto LABEL_49;
  v11 = 0;
  v36 = 0;
  v12 = 0;
  v34 = 0;
  v35 = 0;
  v37 = 0;
  v32 = 0;
  v5 = CFontEnumAgents::Next((CFontEnumAgents *)v38, &v32);
  if ( v5 == 1 )
    goto LABEL_48;
  do
  {
    if ( v5 )
      goto LABEL_45;
    v13 = v32;
    v27 = 0;
    v14 = (*(__int64 (__fastcall **)(struct CFontAgent *, _QWORD, __int64, int *))(*(_QWORD *)v32 + 88LL))(
            v32,
            0,
            1,
            &v27);
    if ( v27 )
    {
      v15 = 0;
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(struct CFontAgent *, __int64, __int64, int *))(*(_QWORD *)v13 + 88LL))(
              v13,
              1,
              1,
              &v27);
      if ( !v27 )
        goto LABEL_45;
      v15 = 1;
    }
    if ( !v14 )
    {
      pszPath = 0;
      (*(void (__fastcall **)(struct CFontAgent *, LPCWSTR *))(*(_QWORD *)v13 + 120LL))(v13, &pszPath);
      v27 = 1;
      if ( FID_Type((const struct _ITEMIDLIST *)pszPath) != 4 )
        goto LABEL_25;
      memset_0(String2, 0, 0x208u);
      if ( (int)FID_FileName((const struct _ITEMIDLIST *)pszPath, 0, String2) >= 0 )
      {
        for ( i = 0; i < v12; ++i )
        {
          if ( CompareStringOrdinal(&v11[260 * i], 260, String2, 260, 1) == 2 )
          {
            v18 = 0;
            goto LABEL_24;
          }
          CompareStringOrdinal(&v11[260 * i], 260, String2, 260, 1);
        }
        if ( (int)CFontManager::_DisplayTrueTypeCollectionWarning(v33, v30, (struct _ITEMIDLIST *)pszPath, &v27) < 0 )
          goto LABEL_40;
        CTSimpleArray<MaxPathString,4294967294,CTPolicyCoTaskMem<MaxPathString>,CSimpleArrayStandardCompareHelper<MaxPathString>,CSimpleArrayStandardMergeHelper<MaxPathString>>::_Add<MaxPathString const &>(
          &v34,
          String2);
        v18 = v27;
        v12 = v35;
        v11 = v34;
LABEL_24:
        if ( v18 )
        {
LABEL_25:
          v19 = 1;
          v27 = 1;
          while ( 1 )
          {
            v22 = CFontManager::_RemoveFont(v16, v30, v13, v31, v15, v26);
            if ( (_WORD)v22 != 32 )
              break;
            v20 = v19 == 0;
            v21 = v30;
            if ( v20 )
              goto LABEL_31;
            v22 = CFontManager::_DisplayFileInUse(v33, v30, (struct _ITEMIDLIST *)pszPath, &v27);
            if ( v22 < 0 )
              goto LABEL_31;
            v19 = v27;
            if ( !v27 )
            {
              v22 = -2147023673;
              goto LABEL_36;
            }
          }
          v21 = v30;
LABEL_31:
          if ( v22 == -2147024891 )
          {
            CFontManager::_DisplayProtectedFontWarning(v16, v21, (struct _ITEMIDLIST *)pszPath);
          }
          else if ( v22 >= 0 )
          {
            v29 = 1;
          }
LABEL_36:
          v23 = (ITEMIDLIST *)pszPath;
          if ( !pszPath )
            goto LABEL_43;
          if ( v22 < 0 || !a5 )
          {
LABEL_41:
            if ( v23 )
              ILFree(v23);
LABEL_43:
            if ( v13 )
              (**(void (__fastcall ***)(struct CFontAgent *, __int64))v13)(v13, 1);
            goto LABEL_45;
          }
          (*(void (__fastcall **)(struct IFontManagerEvents *, LPCWSTR))(*(_QWORD *)a5 + 64LL))(a5, pszPath);
        }
      }
LABEL_40:
      v23 = (ITEMIDLIST *)pszPath;
      goto LABEL_41;
    }
LABEL_45:
    v5 = CFontEnumAgents::Next((CFontEnumAgents *)v38, &v32);
  }
  while ( v5 != 1 );
  if ( v11 )
    CoTaskMemFree(v11);
LABEL_48:
  v8 = v29;
LABEL_49:
  v24 = 0;
  if ( v5 != 1 )
    v24 = v5;
  if ( a5 )
    (*(void (__fastcall **)(struct IFontManagerEvents *, _QWORD))(*(_QWORD *)a5 + 72LL))(a5, v24);
  if ( v8 )
    CFontManager::_SendFontChangeNotification();
  CFontEnumAgents::~CFontEnumAgents((CFontEnumAgents *)v38);
  return v24;
}

```

## disassembly

```asm
0x18001d490  push    rbp
0x18001d492  push    rbx
0x18001d493  push    rsi
0x18001d494  push    rdi
0x18001d495  push    r12
0x18001d497  push    r13
0x18001d499  push    r14
0x18001d49b  push    r15
0x18001d49d  lea     rbp, [rsp-1C8h]
0x18001d4a5  sub     rsp, 2C8h
0x18001d4ac  mov     rax, cs:__security_cookie
0x18001d4b3  xor     rax, rsp
0x18001d4b6  mov     [rbp+200h+var_50], rax
0x18001d4bd  mov     rsi, [rbp+200h+arg_20]
0x18001d4c4  xor     ebx, ebx
0x18001d4c6  mov     [rsp+300h+var_2B0], r9d
0x18001d4cb  mov     rdi, r8
0x18001d4ce  mov     [rsp+300h+var_2B8], rdx
0x18001d4d3  mov     [rsp+300h+var_2A0], rcx
0x18001d4d8  test    rsi, rsi
0x18001d4db  jz      short loc_18001D4EC
0x18001d4dd  mov     rax, [rsi]
0x18001d4e0  mov     rcx, rsi
0x18001d4e3  mov     rax, [rax+38h]
0x18001d4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4ec  xor     r8d, r8d; int
0x18001d4ef  lea     rcx, [rbp+200h+var_278]; this
0x18001d4f3  mov     rdx, rdi; struct IEnumFontNames *
0x18001d4f6  call    ??0CFontEnumAgents@@QEAA@PEAUIEnumFontNames@@H@Z; CFontEnumAgents::CFontEnumAgents(IEnumFontNames *,int)
0x18001d4fb  lea     rcx, [rbp+200h+var_278]; this
0x18001d4ff  call    ?AgentCount@CFontEnumAgents@@UEBAKXZ; CFontEnumAgents::AgentCount(void)
0x18001d504  mov     r14d, eax
0x18001d507  mov     [rsp+300h+pszPath], rbx
0x18001d50c  xor     r15d, r15d
0x18001d50f  mov     rax, [rdi]
0x18001d512  lea     rdx, [rsp+300h+pszPath]
0x18001d517  mov     rcx, rdi
0x18001d51a  mov     rax, [rax+18h]
0x18001d51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d523  test    eax, eax
0x18001d525  jnz     short loc_18001D548
0x18001d527  mov     rcx, [rsp+300h+pszPath]; pszPath
0x18001d52c  call    cs:__imp_PathFileExistsW
0x18001d532  test    eax, eax
0x18001d534  jnz     short loc_18001D50F
0x18001d536  mov     rdx, [rsp+300h+pszPath]; unsigned __int16 *
0x18001d53b  call    ?_RemovePathFromRegistry@CFontManager@@AEAAXPEAG@Z; CFontManager::_RemovePathFromRegistry(ushort *)
0x18001d540  mov     r15d, 1
0x18001d546  jmp     short loc_18001D50F
0x18001d548  mov     rax, [rdi]
0x18001d54b  mov     rcx, rdi
0x18001d54e  mov     [rsp+300h+var_2C0], r15d
0x18001d553  mov     rax, [rax+20h]
0x18001d557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d55c  call    ?CleanUpDeletedUserFonts@@YAXXZ; CleanUpDeletedUserFonts(void)
0x18001d561  test    r14d, r14d
0x18001d564  jle     loc_18001D80A
0x18001d56a  xor     r15d, r15d
0x18001d56d  mov     [rsp+300h+var_288], rbx
0x18001d572  xor     r13d, r13d
0x18001d575  mov     [rsp+300h+var_298], r15
0x18001d57a  lea     rdx, [rsp+300h+var_2A8]; struct CFontAgent **
0x18001d57f  mov     [rsp+300h+var_290], r13
0x18001d584  lea     rcx, [rbp+200h+var_278]; this
0x18001d588  mov     [rbp+200h+var_280], rbx
0x18001d58c  mov     [rsp+300h+var_2A8], rbx
0x18001d591  call    ?Next@CFontEnumAgents@@UEAAJPEAPEAVCFontAgent@@@Z; CFontEnumAgents::Next(CFontAgent * *)
0x18001d596  mov     ebx, eax
0x18001d598  cmp     eax, 1
0x18001d59b  jz      loc_18001D805
0x18001d5a1  test    ebx, ebx
0x18001d5a3  jnz     loc_18001D7DE
0x18001d5a9  mov     r14, [rsp+300h+var_2A8]
0x18001d5ae  lea     r9, [rsp+300h+var_2D0]
0x18001d5b3  mov     [rsp+300h+var_2D0], ebx
0x18001d5b7  lea     r8d, [rbx+1]
0x18001d5bb  xor     edx, edx
0x18001d5bd  mov     rcx, r14
0x18001d5c0  mov     rax, [r14]
0x18001d5c3  mov     rax, [rax+58h]
0x18001d5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5cc  cmp     [rsp+300h+var_2D0], ebx
0x18001d5d0  jnz     short loc_18001D5FC
0x18001d5d2  mov     rax, [r14]
0x18001d5d5  lea     edx, [rbx+1]
0x18001d5d8  lea     r9, [rsp+300h+var_2D0]
0x18001d5dd  mov     r8d, edx
0x18001d5e0  mov     rcx, r14
0x18001d5e3  mov     rax, [rax+58h]
0x18001d5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ec  cmp     [rsp+300h+var_2D0], ebx
0x18001d5f0  jz      loc_18001D7DE
0x18001d5f6  lea     r12d, [rbx+1]
0x18001d5fa  jmp     short loc_18001D5FF
0x18001d5fc  xor     r12d, r12d
0x18001d5ff  test    eax, eax
0x18001d601  jnz     loc_18001D7DE
0x18001d607  mov     [rsp+300h+pszPath], 0
0x18001d610  lea     rdx, [rsp+300h+pszPath]
0x18001d615  mov     rax, [r14]
0x18001d618  mov     rcx, r14
0x18001d61b  mov     rax, [rax+78h]
0x18001d61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d624  mov     rcx, [rsp+300h+pszPath]; struct _ITEMIDLIST *
0x18001d629  mov     [rsp+300h+var_2D0], 1
0x18001d631  call    ?FID_Type@@YAKPEFBU_ITEMIDLIST@@@Z; FID_Type(_ITEMIDLIST const *)
0x18001d636  cmp     eax, 4
0x18001d639  jnz     loc_18001D70A
0x18001d63f  xor     edx, edx; Val
0x18001d641  lea     rcx, [rbp+200h+String2]; void *
0x18001d645  mov     r8d, 208h; Size
0x18001d64b  call    memset_0
0x18001d650  mov     rcx, [rsp+300h+pszPath]; struct _ITEMIDLIST *
0x18001d655  lea     r8, [rbp+200h+String2]; unsigned __int16 *
0x18001d659  xor     edx, edx; unsigned int
0x18001d65b  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x18001d660  test    eax, eax
0x18001d662  js      loc_18001D7B6
0x18001d668  xor     ebx, ebx
0x18001d66a  cmp     rbx, r13
0x18001d66d  jnb     short loc_18001D6C5
0x18001d66f  mov     eax, 104h
0x18001d674  mov     [rsp+300h+bIgnoreCase], 1; bIgnoreCase
0x18001d67c  imul    rdi, rbx, 208h
0x18001d683  mov     r9d, eax; cchCount2
0x18001d686  lea     r8, [rbp+200h+String2]; lpString2
0x18001d68a  add     rdi, r15
0x18001d68d  mov     edx, eax; cchCount1
0x18001d68f  mov     rcx, rdi; lpString1
0x18001d692  call    cs:__imp_CompareStringOrdinal
0x18001d698  cmp     eax, 2
0x18001d69b  jz      short loc_18001D6C1
0x18001d69d  mov     eax, 104h
0x18001d6a2  mov     [rsp+300h+bIgnoreCase], 1; bIgnoreCase
0x18001d6aa  mov     r9d, eax; cchCount2
0x18001d6ad  lea     r8, [rbp+200h+String2]; lpString2
0x18001d6b1  mov     edx, eax; cchCount1
0x18001d6b3  mov     rcx, rdi; lpString1
0x18001d6b6  call    cs:__imp_CompareStringOrdinal
0x18001d6bc  inc     rbx
0x18001d6bf  jmp     short loc_18001D66A
0x18001d6c1  xor     eax, eax
0x18001d6c3  jmp     short loc_18001D702
0x18001d6c5  mov     r8, [rsp+300h+pszPath]; struct _ITEMIDLIST *
0x18001d6ca  lea     r9, [rsp+300h+var_2D0]; int *
0x18001d6cf  mov     rdx, [rsp+300h+var_2B8]; HWND
0x18001d6d4  mov     rcx, [rsp+300h+var_2A0]; this
0x18001d6d9  call    ?_DisplayTrueTypeCollectionWarning@CFontManager@@AEAAJPEAUHWND__@@PEFAU_ITEMIDLIST@@PEAH@Z; CFontManager::_DisplayTrueTypeCollectionWarning(HWND__ *,_ITEMIDLIST *,int *)
0x18001d6de  test    eax, eax
0x18001d6e0  js      loc_18001D7B6
0x18001d6e6  lea     rdx, [rbp+200h+String2]
0x18001d6ea  lea     rcx, [rsp+300h+var_298]
0x18001d6ef  call    ??$_Add@AEBVMaxPathString@@@?$CTSimpleArray@VMaxPathString@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@VMaxPathString@@@@V?$CSimpleArrayStandardCompareHelper@VMaxPathString@@@@V?$CSimpleArrayStandardMergeHelper@VMaxPathString@@@@@@QEAAJAEBVMaxPathString@@PEA_K@Z; CTSimpleArray<MaxPathString,4294967294,CTPolicyCoTaskMem<MaxPathString>,CSimpleArrayStandardCompareHelper<MaxPathString>,CSimpleArrayStandardMergeHelper<MaxPathString>>::_Add<MaxPathString const &>(MaxPathString const &,unsigned __int64 *)
0x18001d6f4  mov     eax, [rsp+300h+var_2D0]
0x18001d6f8  mov     r13, [rsp+300h+var_290]
0x18001d6fd  mov     r15, [rsp+300h+var_298]
0x18001d702  test    eax, eax
0x18001d704  jz      loc_18001D7B6
0x18001d70a  mov     edi, 1
0x18001d70f  mov     [rsp+300h+var_2D0], edi
0x18001d713  jmp     short loc_18001D743
0x18001d715  test    edi, edi
0x18001d717  mov     rdi, [rsp+300h+var_2B8]
0x18001d71c  jz      short loc_18001D767
0x18001d71e  mov     r8, [rsp+300h+pszPath]; struct _ITEMIDLIST *
0x18001d723  lea     r9, [rsp+300h+var_2D0]; int *
0x18001d728  mov     rcx, [rsp+300h+var_2A0]; this
0x18001d72d  mov     rdx, rdi; HWND
0x18001d730  call    ?_DisplayFileInUse@CFontManager@@AEAAJPEAUHWND__@@PEFAU_ITEMIDLIST@@PEAH@Z; CFontManager::_DisplayFileInUse(HWND__ *,_ITEMIDLIST *,int *)
0x18001d735  mov     ebx, eax
0x18001d737  test    eax, eax
0x18001d739  js      short loc_18001D767
0x18001d73b  mov     edi, [rsp+300h+var_2D0]
0x18001d73f  test    edi, edi
0x18001d741  jz      short loc_18001D77E
0x18001d743  mov     r9d, [rsp+300h+var_2B0]; unsigned int
0x18001d748  mov     r8, r14; struct CFontAgent *
0x18001d74b  mov     rdx, [rsp+300h+var_2B8]; HWND
0x18001d750  mov     [rsp+300h+bIgnoreCase], r12d; int
0x18001d755  call    ?_RemoveFont@CFontManager@@AEAAJPEAUHWND__@@AEAVCFontAgent@@KHPEAUIFontManagerEvents@@@Z; CFontManager::_RemoveFont(HWND__ *,CFontAgent &,ulong,int,IFontManagerEvents *)
0x18001d75a  mov     ebx, eax
0x18001d75c  cmp     ax, 20h ; ' '
0x18001d760  jz      short loc_18001D715
0x18001d762  mov     rdi, [rsp+300h+var_2B8]
0x18001d767  cmp     ebx, 80070005h
0x18001d76d  jnz     short loc_18001D785
0x18001d76f  mov     r8, [rsp+300h+pszPath]; struct _ITEMIDLIST *
0x18001d774  mov     rdx, rdi; HWND
0x18001d777  call    ?_DisplayProtectedFontWarning@CFontManager@@AEAAJPEAUHWND__@@PEFAU_ITEMIDLIST@@@Z; CFontManager::_DisplayProtectedFontWarning(HWND__ *,_ITEMIDLIST *)
0x18001d77c  jmp     short loc_18001D791
0x18001d77e  mov     ebx, 800704C7h
0x18001d783  jmp     short loc_18001D791
0x18001d785  test    ebx, ebx
0x18001d787  js      short loc_18001D791
0x18001d789  mov     [rsp+300h+var_2C0], 1
0x18001d791  mov     rcx, [rsp+300h+pszPath]
0x18001d796  test    rcx, rcx
0x18001d799  jz      short loc_18001D7C6
0x18001d79b  test    ebx, ebx
0x18001d79d  js      short loc_18001D7BB
0x18001d79f  test    rsi, rsi
0x18001d7a2  jz      short loc_18001D7BB
0x18001d7a4  mov     rax, [rsi]
0x18001d7a7  mov     rdx, rcx
0x18001d7aa  mov     rcx, rsi
0x18001d7ad  mov     rax, [rax+40h]
0x18001d7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b6  mov     rcx, [rsp+300h+pszPath]; pidl
0x18001d7bb  test    rcx, rcx
0x18001d7be  jz      short loc_18001D7C6
0x18001d7c0  call    cs:__imp_ILFree
0x18001d7c6  test    r14, r14
0x18001d7c9  jz      short loc_18001D7DE
0x18001d7cb  mov     rax, [r14]
0x18001d7ce  mov     edx, 1
0x18001d7d3  mov     rcx, r14
0x18001d7d6  mov     rax, [rax]
0x18001d7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7de  lea     rdx, [rsp+300h+var_2A8]; struct CFontAgent **
0x18001d7e3  lea     rcx, [rbp+200h+var_278]; this
0x18001d7e7  call    ?Next@CFontEnumAgents@@UEAAJPEAPEAVCFontAgent@@@Z; CFontEnumAgents::Next(CFontAgent * *)
0x18001d7ec  mov     ebx, eax
0x18001d7ee  cmp     eax, 1
0x18001d7f1  jnz     loc_18001D5A1
0x18001d7f7  test    r15, r15
0x18001d7fa  jz      short loc_18001D805
0x18001d7fc  mov     rcx, r15; pv
0x18001d7ff  call    cs:__imp_CoTaskMemFree
0x18001d805  mov     r15d, [rsp+300h+var_2C0]
0x18001d80a  xor     edi, edi
0x18001d80c  cmp     ebx, 1
0x18001d80f  cmovnz  edi, ebx
0x18001d812  test    rsi, rsi
0x18001d815  jz      short loc_18001D828
0x18001d817  mov     rax, [rsi]
0x18001d81a  mov     edx, edi
0x18001d81c  mov     rcx, rsi
0x18001d81f  mov     rax, [rax+48h]
0x18001d823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d828  test    r15d, r15d
0x18001d82b  jz      short loc_18001D832
0x18001d82d  call    ?_SendFontChangeNotification@CFontManager@@CAXXZ; CFontManager::_SendFontChangeNotification(void)
0x18001d832  lea     rcx, [rbp+200h+var_278]; this
0x18001d836  call    ??1CFontEnumAgents@@UEAA@XZ; CFontEnumAgents::~CFontEnumAgents(void)
0x18001d83b  mov     eax, edi
0x18001d83d  mov     rcx, [rbp+200h+var_50]
0x18001d844  xor     rcx, rsp; StackCookie
0x18001d847  call    __security_check_cookie
0x18001d84c  add     rsp, 2C8h
0x18001d853  pop     r15
0x18001d855  pop     r14
0x18001d857  pop     r13
0x18001d859  pop     r12
0x18001d85b  pop     rdi
0x18001d85c  pop     rsi
0x18001d85d  pop     rbx
0x18001d85e  pop     rbp
0x18001d85f  retn
```
