# RegisterServer(CClassInfo *,int)

- ea: `0x180090318`
- end: `0x180090856`
- name: `?RegisterServer@@YAJPEAUCClassInfo@@H@Z`
- size: `1342`
- prototype: `__int64 __fastcall(struct CClassInfo *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180090df0`

## callees

- `0x180034cf8`
- `0x180037120`
- `0x180072230`
- `0x180080514`
- `0x18008fc48`
- `0x18008fcb4`
- `0x180090318`
- `0x1800910f8`
- `0x18009124c`
- `0x1800915f0`
- `0x1800917e0`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009035f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009035f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18009068b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18009068b`
- `wbemcomn!GetMemLogObject` at `0x180090382`
- `wbemcomn!GetMemLogObject` at `0x1800903f4`
- `wbemcomn!GetMemLogObject` at `0x180090493`
- `wbemcomn!GetMemLogObject` at `0x180090507`
- `wbemcomn!GetMemLogObject` at `0x18009058e`
- `wbemcomn!GetMemLogObject` at `0x180090604`
- `wbemcomn!GetMemLogObject` at `0x180090695`
- `wbemcomn!GetMemLogObject` at `0x18009071b`
- `wbemcomn!GetMemLogObject` at `0x1800907cf`
- `wbemcomn!GetMemLogObject` at `0x180090382`
- `wbemcomn!GetMemLogObject` at `0x1800903f4`
- `wbemcomn!GetMemLogObject` at `0x180090493`
- `wbemcomn!GetMemLogObject` at `0x180090507`
- `wbemcomn!GetMemLogObject` at `0x18009058e`
- `wbemcomn!GetMemLogObject` at `0x180090604`
- `wbemcomn!GetMemLogObject` at `0x180090695`
- `wbemcomn!GetMemLogObject` at `0x18009071b`
- `wbemcomn!GetMemLogObject` at `0x1800907cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009038d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800903ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800904a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090513`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009059a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009060f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800906a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090726`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800907da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009038d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800903ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800904a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090513`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009059a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009060f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800906a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090726`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800907da`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180090485`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180090485`

## string_xrefs

- `0x180090365`: `SOFTWARE\Classes\CLSID\`
- `0x1800907b8`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegisterServer(const GUID *const *a1)
{
  int v2; // edx
  int PathString; // ebx
  int v4; // r8d
  int v5; // r9d
  CMemoryLog *MemLogObject; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  int Key; // ebx
  CMemoryLog *v10; // rax
  int v11; // r8d
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  unsigned __int16 *v16; // rax
  __int64 v17; // rsi
  CMemoryLog *v18; // rax
  __int64 v19; // r8
  int v20; // r8d
  int v21; // r9d
  int v22; // r14d
  CMemoryLog *v23; // rax
  __int64 v24; // rax
  int v25; // r8d
  int v26; // r9d
  int v27; // r14d
  CMemoryLog *v28; // rax
  int v29; // r8d
  __int64 v30; // rdx
  unsigned int v31; // esi
  CMemoryLog *v32; // rax
  int v33; // r8d
  int v34; // r9d
  CMemoryLog *v35; // rax
  CWbemRefreshingSvc *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  __int64 v39; // rax
  int v40; // esi
  int v41; // r8d
  int v42; // r9d
  CMemoryLog *v43; // rax
  int v44; // r8d
  const wchar_t *v45; // rcx
  unsigned int v46; // ebx
  CMemoryLog *v47; // rax
  unsigned int v48; // ebx
  _BYTE v49[24]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v50[32]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[128]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Filename[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v53[256]; // [rsp+3B0h] [rbp+2B0h] BYREF

  StringFromGUID2(a1[3], sz, 128);
  PathString = CreatePathString(v53, v2, sz, L"SOFTWARE\\Classes\\CLSID\\");
  if ( PathString < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, PathString);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v7, sz);
    }
    return 2147500037LL;
  }
  Key = DLRegCreateKeyExW(-2147483646, (unsigned int)v53, v4, v5);
  if ( Key )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, Key);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v11, Key, (__int64)v53);
    }
    return 2147500037LL;
  }
  MakeGuard<long (*)(HKEY__ *),HKEY__ *>(v49, v8, 0);
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*((_QWORD *)a1 + 5) + 2 * v14) );
  v15 = (int)v14 + 100;
  v16 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v15, 2u));
  v17 = (__int64)v16;
  if ( !v16 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147024882);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v19, v53);
    }
LABEL_36:
    ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v49);
    return 2147500037LL;
  }
  v22 = StringCchPrintfW(v16, v15, L"Microsoft WBEM %s", *((_QWORD *)a1 + 5));
  if ( v22 < 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, v22);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
    }
    goto LABEL_36;
  }
  v24 = -1;
  do
    ++v24;
  while ( *(_WORD *)(v17 + 2 * v24) );
  v27 = DLRegSetValueExW(0, 0, v20, v21, v17, 2 * (int)v24 + 2);
  if ( v27 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v27);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v29, v27, v17);
    }
    goto LABEL_36;
  }
  v31 = DLRegCreateKeyExW(0, (unsigned int)L"InprocServer32", v25, v26);
  if ( v31 )
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, v31);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, v31);
    }
    goto LABEL_36;
  }
  MakeGuard<long (*)(HKEY__ *),HKEY__ *>(v50, v30, 0);
  Filename[260] = 48;
  if ( !GetModuleFileNameW(qword_1800D80A8, Filename, 0x104u) )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, 0);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_61;
    }
    v37 = 19;
    v38 = 0;
    goto LABEL_60;
  }
  v39 = -1;
  do
    ++v39;
  while ( Filename[v39] );
  v40 = DLRegSetValueExW(0, 0, v33, v34, (__int64)Filename, 2 * (int)v39 + 2);
  if ( v40 )
  {
    v43 = GetMemLogObject();
    CMemoryLog::Write(v43, v40);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v44, v40, (__int64)Filename);
    }
    goto LABEL_61;
  }
  if ( *((_DWORD *)a1 + 12) )
  {
    v45 = L"Both";
    if ( *((_DWORD *)a1 + 13) )
      v45 = L"Free";
  }
  else
  {
    v45 = L"Apartment";
  }
  do
    ++v13;
  while ( v45[v13] );
  v46 = DLRegSetValueExW(0, (unsigned int)L"ThreadingModel", v41, v42, (__int64)v45, 2 * (int)v13 + 2);
  if ( !v46 )
  {
    v48 = 0;
    goto LABEL_63;
  }
  v47 = GetMemLogObject();
  CMemoryLog::Write(v47, v46);
  v36 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v37 = 21;
    v38 = v46;
LABEL_60:
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, v38);
  }
LABEL_61:
  v48 = -2147467259;
LABEL_63:
  ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v50);
  ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v49);
  return v48;
}

```

## disassembly

```asm
0x180090318  push    rbp
0x18009031a  push    rbx
0x18009031b  push    rsi
0x18009031c  push    rdi
0x18009031d  push    r14
0x18009031f  push    r15
0x180090321  lea     rbp, [rsp-4C8h]
0x180090329  sub     rsp, 5C8h
0x180090330  mov     rax, cs:__security_cookie
0x180090337  xor     rax, rsp
0x18009033a  mov     [rbp+4F0h+var_40], rax
0x180090341  mov     rdi, rcx
0x180090344  xor     r15d, r15d
0x180090347  mov     [rsp+5F0h+var_5A0], r15
0x18009034c  mov     [rsp+5F0h+var_598], r15
0x180090351  mov     r8d, 80h; cchMax
0x180090357  lea     rdx, [rbp+4F0h+sz]; lpsz
0x18009035b  mov     rcx, [rcx+18h]; rguid
0x18009035f  call    cs:__imp_StringFromGUID2
0x180090365  lea     r9, aSoftwareClasse_4; "SOFTWARE\\Classes\\CLSID\\"
0x18009036c  lea     r8, [rbp+4F0h+sz]; unsigned __int16 *
0x180090370  lea     rcx, [rbp+4F0h+var_240]; unsigned __int16 *
0x180090377  call    ?CreatePathString@@YAJPEAGH00@Z; CreatePathString(ushort *,int,ushort *,ushort *)
0x18009037c  mov     ebx, eax
0x18009037e  test    eax, eax
0x180090380  jns     short loc_1800903D1
0x180090382  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090388  mov     edx, ebx
0x18009038a  mov     rcx, rax
0x18009038d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090393  lea     rax, WPP_GLOBAL_Control
0x18009039a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800903a1  cmp     rcx, rax
0x1800903a4  jz      loc_180090441
0x1800903aa  test    byte ptr [rcx+1Ch], 1
0x1800903ae  jz      loc_180090441
0x1800903b4  cmp     byte ptr [rcx+19h], 2
0x1800903b8  jb      loc_180090441
0x1800903be  lea     edx, [r15+0Dh]
0x1800903c2  lea     r9, [rbp+4F0h+sz]
0x1800903c6  mov     rcx, [rcx+10h]
0x1800903ca  call    WPP_SF_S
0x1800903cf  jmp     short loc_180090441
0x1800903d1  lea     rax, [rsp+5F0h+var_5A0]
0x1800903d6  mov     [rsp+5F0h+var_5B8], rax
0x1800903db  lea     rdx, [rbp+4F0h+var_240]
0x1800903e2  mov     rcx, 0FFFFFFFF80000002h
0x1800903e9  call    DLRegCreateKeyExW
0x1800903ee  mov     ebx, eax
0x1800903f0  test    eax, eax
0x1800903f2  jz      short loc_18009044B
0x1800903f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800903fa  mov     edx, ebx
0x1800903fc  mov     rcx, rax
0x1800903ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090405  lea     rax, WPP_GLOBAL_Control
0x18009040c  mov     rcx, cs:WPP_GLOBAL_Control
0x180090413  cmp     rcx, rax
0x180090416  jz      short loc_180090441
0x180090418  test    byte ptr [rcx+1Ch], 1
0x18009041c  jz      short loc_180090441
0x18009041e  cmp     byte ptr [rcx+19h], 2
0x180090422  jb      short loc_180090441
0x180090424  mov     edx, 0Eh
0x180090429  lea     rax, [rbp+4F0h+var_240]
0x180090430  mov     [rsp+5F0h+var_5D0], rax
0x180090435  mov     r9d, ebx
0x180090438  mov     rcx, [rcx+10h]
0x18009043c  call    WPP_SF_LS
0x180090441  mov     eax, 80004005h
0x180090446  jmp     loc_180090837
0x18009044b  mov     r8, [rsp+5F0h+var_5A0]
0x180090450  lea     rcx, [rsp+5F0h+var_588]
0x180090455  call    ??$MakeGuard@P6AJPEAUHKEY__@@@ZPEAU1@@@YA?AV?$ScopeGuardImpl1@P6AJPEAUHKEY__@@@ZPEAU1@@@P6AJPEAUHKEY__@@@Z0@Z; MakeGuard<long (*)(HKEY__ *),HKEY__ *>(long (*)(HKEY__ *),HKEY__ *)
0x18009045a  nop
0x18009045b  mov     rcx, [rdi+28h]
0x18009045f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180090463  mov     rax, rbx
0x180090466  inc     rax
0x180090469  cmp     [rcx+rax*2], r15w
0x18009046e  jnz     short loc_180090466
0x180090470  add     eax, 64h ; 'd'
0x180090473  movsxd  r14, eax
0x180090476  mov     eax, 2
0x18009047b  mul     r14
0x18009047e  cmovb   rax, rbx
0x180090482  mov     rcx, rax
0x180090485  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18009048b  mov     rsi, rax
0x18009048e  test    rax, rax
0x180090491  jnz     short loc_1800904EA
0x180090493  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090499  mov     edx, 8007000Eh
0x18009049e  mov     rcx, rax
0x1800904a1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800904a7  lea     rax, WPP_GLOBAL_Control
0x1800904ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800904b5  cmp     rcx, rax
0x1800904b8  jz      loc_18009064D
0x1800904be  test    byte ptr [rcx+1Ch], 1
0x1800904c2  jz      loc_18009064D
0x1800904c8  cmp     byte ptr [rcx+19h], 2
0x1800904cc  jb      loc_18009064D
0x1800904d2  lea     edx, [rsi+0Fh]
0x1800904d5  lea     r9, [rbp+4F0h+var_240]
0x1800904dc  mov     rcx, [rcx+10h]
0x1800904e0  call    WPP_SF_S
0x1800904e5  jmp     loc_18009064D
0x1800904ea  mov     r9, [rdi+28h]
0x1800904ee  lea     r8, aMicrosoftWbemS; "Microsoft WBEM %s"
0x1800904f5  mov     rdx, r14; unsigned __int64
0x1800904f8  mov     rcx, rsi; unsigned __int16 *
0x1800904fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180090500  mov     r14d, eax
0x180090503  test    eax, eax
0x180090505  jns     short loc_18009055E
0x180090507  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009050d  mov     edx, r14d
0x180090510  mov     rcx, rax
0x180090513  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090519  lea     rax, WPP_GLOBAL_Control
0x180090520  mov     rcx, cs:WPP_GLOBAL_Control
0x180090527  cmp     rcx, rax
0x18009052a  jz      loc_18009064D
0x180090530  test    byte ptr [rcx+1Ch], 1
0x180090534  jz      loc_18009064D
0x18009053a  cmp     byte ptr [rcx+19h], 2
0x18009053e  jb      loc_18009064D
0x180090544  mov     edx, 10h
0x180090549  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180090550  mov     rcx, [rcx+10h]
0x180090554  call    WPP_SF_
0x180090559  jmp     loc_18009064D
0x18009055e  mov     rax, rbx
0x180090561  inc     rax
0x180090564  cmp     [rsi+rax*2], r15w
0x180090569  jnz     short loc_180090561
0x18009056b  lea     eax, ds:2[rax*2]
0x180090572  mov     [rsp+5F0h+var_5C8], eax
0x180090576  mov     [rsp+5F0h+var_5D0], rsi
0x18009057b  xor     edx, edx
0x18009057d  mov     rcx, [rsp+5F0h+var_5A0]
0x180090582  call    DLRegSetValueExW
0x180090587  mov     r14d, eax
0x18009058a  test    eax, eax
0x18009058c  jz      short loc_1800905E3
0x18009058e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090594  mov     edx, r14d
0x180090597  mov     rcx, rax
0x18009059a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800905a0  lea     rax, WPP_GLOBAL_Control
0x1800905a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800905ae  cmp     rcx, rax
0x1800905b1  jz      loc_18009064D
0x1800905b7  test    byte ptr [rcx+1Ch], 1
0x1800905bb  jz      loc_18009064D
0x1800905c1  cmp     byte ptr [rcx+19h], 2
0x1800905c5  jb      loc_18009064D
0x1800905cb  mov     edx, 11h
0x1800905d0  mov     [rsp+5F0h+var_5D0], rsi
0x1800905d5  mov     r9d, r14d
0x1800905d8  mov     rcx, [rcx+10h]
0x1800905dc  call    WPP_SF_LS
0x1800905e1  jmp     short loc_18009064D
0x1800905e3  lea     rax, [rsp+5F0h+var_598]
0x1800905e8  mov     [rsp+5F0h+var_5B8], rax
0x1800905ed  lea     rdx, aInprocserver32; "InprocServer32"
0x1800905f4  mov     rcx, [rsp+5F0h+var_5A0]
0x1800905f9  call    DLRegCreateKeyExW
0x1800905fe  mov     esi, eax
0x180090600  test    eax, eax
0x180090602  jz      short loc_18009065C
0x180090604  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009060a  mov     edx, esi
0x18009060c  mov     rcx, rax
0x18009060f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090615  lea     rax, WPP_GLOBAL_Control
0x18009061c  mov     rcx, cs:WPP_GLOBAL_Control
0x180090623  cmp     rcx, rax
0x180090626  jz      short loc_18009064D
0x180090628  test    byte ptr [rcx+1Ch], 1
0x18009062c  jz      short loc_18009064D
0x18009062e  cmp     byte ptr [rcx+19h], 2
0x180090632  jb      short loc_18009064D
0x180090634  mov     edx, 12h
0x180090639  mov     r9d, esi
0x18009063c  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180090643  mov     rcx, [rcx+10h]
0x180090647  call    WPP_SF_d
0x18009064c  nop
0x18009064d  lea     rcx, [rsp+5F0h+var_588]
0x180090652  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090657  jmp     loc_180090441
0x18009065c  mov     r8, [rsp+5F0h+var_598]
0x180090661  lea     rcx, [rbp+4F0h+var_570]
0x180090665  call    ??$MakeGuard@P6AJPEAUHKEY__@@@ZPEAU1@@@YA?AV?$ScopeGuardImpl1@P6AJPEAUHKEY__@@@ZPEAU1@@@P6AJPEAUHKEY__@@@Z0@Z; MakeGuard<long (*)(HKEY__ *),HKEY__ *>(long (*)(HKEY__ *),HKEY__ *)
0x18009066a  nop
0x18009066b  mov     eax, 30h ; '0'
0x180090670  mov     [rbp+4F0h+var_248], ax
0x180090677  mov     r8d, 104h; nSize
0x18009067d  lea     rdx, [rbp+4F0h+Filename]; lpFilename
0x180090684  mov     rcx, cs:qword_1800D80A8; hModule
0x18009068b  call    cs:__imp_GetModuleFileNameW
0x180090691  test    eax, eax
0x180090693  jnz     short loc_1800906DE
0x180090695  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009069b  xor     edx, edx
0x18009069d  mov     rcx, rax
0x1800906a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800906a6  lea     rax, WPP_GLOBAL_Control
0x1800906ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800906b4  cmp     rcx, rax
0x1800906b7  jz      loc_180090817
0x1800906bd  test    byte ptr [rcx+1Ch], 1
0x1800906c1  jz      loc_180090817
0x1800906c7  cmp     byte ptr [rcx+19h], 2
0x1800906cb  jb      loc_180090817
0x1800906d1  mov     edx, 13h
0x1800906d6  xor     r9d, r9d
0x1800906d9  jmp     loc_180090807
0x1800906de  lea     rcx, [rbp+4F0h+Filename]
0x1800906e5  mov     rax, rbx
0x1800906e8  inc     rax
0x1800906eb  cmp     [rcx+rax*2], r15w
0x1800906f0  jnz     short loc_1800906E8
0x1800906f2  lea     eax, ds:2[rax*2]
0x1800906f9  mov     [rsp+5F0h+var_5C8], eax
0x1800906fd  lea     rax, [rbp+4F0h+Filename]
0x180090704  mov     [rsp+5F0h+var_5D0], rax
0x180090709  xor     edx, edx
0x18009070b  mov     rcx, [rsp+5F0h+var_598]
0x180090710  call    DLRegSetValueExW
0x180090715  mov     esi, eax
0x180090717  test    eax, eax
0x180090719  jz      short loc_180090779
0x18009071b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090721  mov     edx, esi
0x180090723  mov     rcx, rax
0x180090726  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009072c  lea     rax, WPP_GLOBAL_Control
0x180090733  mov     rcx, cs:WPP_GLOBAL_Control
0x18009073a  cmp     rcx, rax
0x18009073d  jz      loc_180090817
0x180090743  test    byte ptr [rcx+1Ch], 1
0x180090747  jz      loc_180090817
0x18009074d  cmp     byte ptr [rcx+19h], 2
0x180090751  jb      loc_180090817
0x180090757  mov     edx, 14h
0x18009075c  lea     rax, [rbp+4F0h+Filename]
0x180090763  mov     [rsp+5F0h+var_5D0], rax
0x180090768  mov     r9d, esi
0x18009076b  mov     rcx, [rcx+10h]
0x18009076f  call    WPP_SF_LS
0x180090774  jmp     loc_180090817
0x180090779  cmp     [rdi+30h], r15d
0x18009077d  jz      short loc_180090797
0x18009077f  lea     rax, aFree; "Free"
0x180090786  lea     rcx, aBoth; "Both"
0x18009078d  cmp     [rdi+34h], r15d
0x180090791  cmovnz  rcx, rax
0x180090795  jmp     short loc_18009079E
0x180090797  lea     rcx, aApartment; "Apartment"
0x18009079e  inc     rbx
0x1800907a1  cmp     [rcx+rbx*2], r15w
0x1800907a6  jnz     short loc_18009079E
0x1800907a8  lea     eax, ds:2[rbx*2]
0x1800907af  mov     [rsp+5F0h+var_5C8], eax
0x1800907b3  mov     [rsp+5F0h+var_5D0], rcx
0x1800907b8  lea     rdx, aThreadingmodel; "ThreadingModel"
0x1800907bf  mov     rcx, [rsp+5F0h+var_598]
0x1800907c4  call    DLRegSetValueExW
0x1800907c9  mov     ebx, eax
0x1800907cb  test    eax, eax
0x1800907cd  jz      short loc_18009081E
0x1800907cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800907d5  mov     edx, ebx
0x1800907d7  mov     rcx, rax
0x1800907da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800907e0  lea     rax, WPP_GLOBAL_Control
0x1800907e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800907ee  cmp     rcx, rax
0x1800907f1  jz      short loc_180090817
0x1800907f3  test    byte ptr [rcx+1Ch], 1
0x1800907f7  jz      short loc_180090817
0x1800907f9  cmp     byte ptr [rcx+19h], 2
0x1800907fd  jb      short loc_180090817
0x1800907ff  mov     edx, 15h
0x180090804  mov     r9d, ebx
0x180090807  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x18009080e  mov     rcx, [rcx+10h]
0x180090812  call    WPP_SF_d
0x180090817  mov     ebx, 80004005h
0x18009081c  jmp     short loc_180090821
0x18009081e  mov     ebx, r15d
0x180090821  lea     rcx, [rbp+4F0h+var_570]
0x180090825  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x18009082a  nop
0x18009082b  lea     rcx, [rsp+5F0h+var_588]
0x180090830  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090835  mov     eax, ebx
  ... truncated ...
```
