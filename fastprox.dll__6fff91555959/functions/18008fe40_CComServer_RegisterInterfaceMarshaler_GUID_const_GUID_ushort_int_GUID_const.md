# CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)

- ea: `0x18008fe40`
- end: `0x18009030f`
- name: `?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z`
- size: `1231`
- prototype: `int(CComServer *__hidden this, const struct _GUID *, struct _GUID *__struct_ptr, unsigned __int16 *, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180084640`

## callees

- `0x180034cf8`
- `0x180037120`
- `0x180080514`
- `0x18008fc48`
- `0x18008fcb4`
- `0x18008fe40`
- `0x1800910f8`
- `0x180091180`
- `0x18009124c`
- `0x1800915f0`
- `0x1800917e0`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008fe91`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008fea1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008fe91`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008fea1`
- `wbemcomn!GetMemLogObject` at `0x18008fec7`
- `wbemcomn!GetMemLogObject` at `0x18008ff3d`
- `wbemcomn!GetMemLogObject` at `0x18008ffba`
- `wbemcomn!GetMemLogObject` at `0x180090054`
- `wbemcomn!GetMemLogObject` at `0x1800900b9`
- `wbemcomn!GetMemLogObject` at `0x18009015c`
- `wbemcomn!GetMemLogObject` at `0x1800901dc`
- `wbemcomn!GetMemLogObject` at `0x18009027b`
- `wbemcomn!GetMemLogObject` at `0x18008fec7`
- `wbemcomn!GetMemLogObject` at `0x18008ff3d`
- `wbemcomn!GetMemLogObject` at `0x18008ffba`
- `wbemcomn!GetMemLogObject` at `0x180090054`
- `wbemcomn!GetMemLogObject` at `0x1800900b9`
- `wbemcomn!GetMemLogObject` at `0x18009015c`
- `wbemcomn!GetMemLogObject` at `0x1800901dc`
- `wbemcomn!GetMemLogObject` at `0x18009027b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008fed2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ff48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ffc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009005f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800900c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090167`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800901e7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090286`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008fed2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ff48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ffc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009005f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800900c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090167`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800901e7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090286`

## string_xrefs

- `0x1800900a2`: `ProxyStubClsid32`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CComServer::RegisterInterfaceMarshaler(
        CComServer *this,
        const struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  int v7; // edx
  int PathString; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v10; // r8
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  CMemoryLog *v14; // rax
  __int64 v15; // rdx
  int Key; // ebx
  CMemoryLog *v17; // rax
  int v18; // r8d
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rbx
  __int64 v23; // rax
  int v24; // edi
  int v25; // r8d
  int v26; // r9d
  CMemoryLog *v27; // rax
  int v28; // r8d
  __int64 v29; // rdx
  int v30; // edi
  CMemoryLog *v31; // rax
  int v32; // r8d
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rax
  int v36; // edi
  int v37; // r8d
  int v38; // r9d
  CMemoryLog *v39; // rax
  int v40; // edx
  int v41; // r8d
  __int64 v42; // rdx
  int v43; // edi
  CMemoryLog *v44; // rax
  int v45; // r8d
  int v46; // r8d
  int v47; // r9d
  int v48; // ebx
  CMemoryLog *v49; // rax
  int v50; // r8d
  unsigned int v51; // ebx
  _BYTE v52[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v53[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v54[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v55[32]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR v56[128]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v57[256]; // [rsp+200h] [rbp+100h] BYREF
  OLECHAR sz[128]; // [rsp+400h] [rbp+300h] BYREF

  StringFromGUID2(a2, sz, 128);
  StringFromGUID2(a3, v56, 128);
  PathString = CreatePathString(v57, v7, sz, L"SOFTWARE\\Classes\\Interface\\");
  if ( PathString < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, PathString);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v10, sz);
    }
    return 2147500037LL;
  }
  v11 = StringCchPrintfW(v55, 0x20u, L"%d", a5);
  if ( v11 < 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v11);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, a5);
    }
    return 2147500037LL;
  }
  Key = DLRegCreateKeyExW(-2147483646, (unsigned int)v57, v12, v13);
  if ( Key )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, Key);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v18, Key, (__int64)v57);
    }
    return 2147500037LL;
  }
  MakeGuard<long (*)(HKEY__ *),HKEY__ *>(v52, v15, 0);
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( a4[v23] );
  v24 = DLRegSetValueExW(0, 0, v20, v21, (__int64)a4, 2 * (int)v23 + 2);
  if ( v24 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, v24);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v28, v24, (__int64)a4);
    }
    goto LABEL_29;
  }
  v30 = DLRegCreateKeyExW(0, (unsigned int)L"ProxyStubClsid32", v25, v26);
  if ( v30 )
  {
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, v30);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v32, v30, (__int64)v57);
    }
    goto LABEL_29;
  }
  MakeGuard<long (*)(HKEY__ *),HKEY__ *>(v53, v29, 0);
  v35 = -1;
  do
    ++v35;
  while ( v56[v35] );
  v36 = DLRegSetValueExW(0, 0, v33, v34, (__int64)v56, 2 * (int)v35 + 2);
  if ( v36 )
  {
    v39 = GetMemLogObject();
    CMemoryLog::Write(v39, v36);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, v41, v36, (__int64)v57, (__int64)v56);
    }
LABEL_42:
    ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v53);
LABEL_29:
    ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v52);
    return 2147500037LL;
  }
  v43 = DLRegCreateKeyExW(0, (unsigned int)L"NumMethods", v37, v38);
  if ( v43 )
  {
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, v43);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v45, v43, (__int64)v57);
    }
    goto LABEL_42;
  }
  MakeGuard<long (*)(HKEY__ *),HKEY__ *>(v54, v42, 0);
  do
    ++v22;
  while ( v55[v22] );
  v48 = DLRegSetValueExW(0, 0, v46, v47, (__int64)v55, 2 * (int)v22 + 2);
  if ( v48 )
  {
    v49 = GetMemLogObject();
    CMemoryLog::Write(v49, v48);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v50, v48, (__int64)v57);
    }
    v51 = -2147467259;
  }
  else
  {
    v51 = 0;
  }
  ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v54);
  ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v53);
  ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>::~ScopeGuardImpl1<unsigned short * (*)(unsigned short const *),unsigned short *>((__int64)v52);
  return v51;
}

```

## disassembly

```asm
0x18008fe40  push    rbp
0x18008fe42  push    rbx
0x18008fe43  push    rsi
0x18008fe44  push    rdi
0x18008fe45  push    r14
0x18008fe47  lea     rbp, [rsp-410h]
0x18008fe4f  sub     rsp, 510h
0x18008fe56  mov     rax, cs:__security_cookie
0x18008fe5d  xor     rax, rsp
0x18008fe60  mov     [rbp+430h+var_30], rax
0x18008fe67  mov     rsi, r9
0x18008fe6a  mov     rbx, r8
0x18008fe6d  mov     rcx, rdx; rguid
0x18008fe70  xor     r14d, r14d
0x18008fe73  mov     [rsp+530h+var_4E0], r14
0x18008fe78  mov     [rsp+530h+var_4D8], r14
0x18008fe7d  mov     [rsp+530h+var_4D0], r14
0x18008fe82  mov     edi, 80h
0x18008fe87  mov     r8d, edi; cchMax
0x18008fe8a  lea     rdx, [rbp+430h+sz]; lpsz
0x18008fe91  call    cs:__imp_StringFromGUID2
0x18008fe97  mov     r8d, edi; cchMax
0x18008fe9a  lea     rdx, [rbp+430h+var_430]; lpsz
0x18008fe9e  mov     rcx, rbx; rguid
0x18008fea1  call    cs:__imp_StringFromGUID2
0x18008fea7  lea     r9, aSoftwareClasse_0; "SOFTWARE\\Classes\\Interface\\"
0x18008feae  lea     r8, [rbp+430h+sz]; unsigned __int16 *
0x18008feb5  lea     rcx, [rbp+430h+var_330]; unsigned __int16 *
0x18008febc  call    ?CreatePathString@@YAJPEAGH00@Z; CreatePathString(ushort *,int,ushort *,ushort *)
0x18008fec1  mov     ebx, eax
0x18008fec3  test    eax, eax
0x18008fec5  jns     short loc_18008FF1B
0x18008fec7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008fecd  mov     edx, ebx
0x18008fecf  mov     rcx, rax
0x18008fed2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008fed8  lea     rax, WPP_GLOBAL_Control
0x18008fedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fee6  cmp     rcx, rax
0x18008fee9  jz      loc_180090007
0x18008feef  test    byte ptr [rcx+1Ch], 1
0x18008fef3  jz      loc_180090007
0x18008fef9  cmp     byte ptr [rcx+19h], 2
0x18008fefd  jb      loc_180090007
0x18008ff03  lea     edx, [rdi-5Dh]
0x18008ff06  lea     r9, [rbp+430h+sz]
0x18008ff0d  mov     rcx, [rcx+10h]
0x18008ff11  call    WPP_SF_S
0x18008ff16  jmp     loc_180090007
0x18008ff1b  mov     r9d, [rbp+430h+arg_20]
0x18008ff22  lea     r8, aD; "%d"
0x18008ff29  mov     edx, 20h ; ' '; unsigned __int64
0x18008ff2e  lea     rcx, [rbp+430h+var_470]; unsigned __int16 *
0x18008ff32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008ff37  mov     ebx, eax
0x18008ff39  test    eax, eax
0x18008ff3b  jns     short loc_18008FF97
0x18008ff3d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008ff43  mov     edx, ebx
0x18008ff45  mov     rcx, rax
0x18008ff48  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008ff4e  lea     rax, WPP_GLOBAL_Control
0x18008ff55  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ff5c  cmp     rcx, rax
0x18008ff5f  jz      loc_180090007
0x18008ff65  test    byte ptr [rcx+1Ch], 1
0x18008ff69  jz      loc_180090007
0x18008ff6f  cmp     byte ptr [rcx+19h], 2
0x18008ff73  jb      loc_180090007
0x18008ff79  mov     edx, 24h ; '$'
0x18008ff7e  mov     r9d, [rbp+430h+arg_20]
0x18008ff85  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x18008ff8c  mov     rcx, [rcx+10h]
0x18008ff90  call    WPP_SF_d
0x18008ff95  jmp     short loc_180090007
0x18008ff97  lea     rax, [rsp+530h+var_4E0]
0x18008ff9c  mov     [rsp+530h+var_4F8], rax
0x18008ffa1  lea     rdx, [rbp+430h+var_330]
0x18008ffa8  mov     rcx, 0FFFFFFFF80000002h
0x18008ffaf  call    DLRegCreateKeyExW
0x18008ffb4  mov     ebx, eax
0x18008ffb6  test    eax, eax
0x18008ffb8  jz      short loc_180090011
0x18008ffba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008ffc0  mov     edx, ebx
0x18008ffc2  mov     rcx, rax
0x18008ffc5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008ffcb  lea     rax, WPP_GLOBAL_Control
0x18008ffd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ffd9  cmp     rcx, rax
0x18008ffdc  jz      short loc_180090007
0x18008ffde  test    byte ptr [rcx+1Ch], 1
0x18008ffe2  jz      short loc_180090007
0x18008ffe4  cmp     byte ptr [rcx+19h], 2
0x18008ffe8  jb      short loc_180090007
0x18008ffea  mov     edx, 25h ; '%'
0x18008ffef  lea     rax, [rbp+430h+var_330]
0x18008fff6  mov     [rsp+530h+var_510], rax
0x18008fffb  mov     r9d, ebx
0x18008fffe  mov     rcx, [rcx+10h]
0x180090002  call    WPP_SF_LS
0x180090007  mov     eax, 80004005h
0x18009000c  jmp     loc_1800902F2
0x180090011  mov     r8, [rsp+530h+var_4E0]
0x180090016  lea     rcx, [rsp+530h+var_4C0]
0x18009001b  call    ??$MakeGuard@P6AJPEAUHKEY__@@@ZPEAU1@@@YA?AV?$ScopeGuardImpl1@P6AJPEAUHKEY__@@@ZPEAU1@@@P6AJPEAUHKEY__@@@Z0@Z; MakeGuard<long (*)(HKEY__ *),HKEY__ *>(long (*)(HKEY__ *),HKEY__ *)
0x180090020  nop
0x180090021  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180090025  mov     rax, rbx
0x180090028  inc     rax
0x18009002b  cmp     [rsi+rax*2], r14w
0x180090030  jnz     short loc_180090028
0x180090032  lea     eax, ds:2[rax*2]
0x180090039  mov     dword ptr [rsp+530h+var_508], eax
0x18009003d  mov     [rsp+530h+var_510], rsi
0x180090042  xor     edx, edx
0x180090044  mov     rcx, [rsp+530h+var_4E0]
0x180090049  call    DLRegSetValueExW
0x18009004e  mov     edi, eax
0x180090050  test    eax, eax
0x180090052  jz      short loc_180090098
0x180090054  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009005a  mov     edx, edi
0x18009005c  mov     rcx, rax
0x18009005f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090065  lea     rax, WPP_GLOBAL_Control
0x18009006c  mov     rcx, cs:WPP_GLOBAL_Control
0x180090073  cmp     rcx, rax
0x180090076  jz      loc_180090107
0x18009007c  test    byte ptr [rcx+1Ch], 1
0x180090080  jz      loc_180090107
0x180090086  cmp     byte ptr [rcx+19h], 2
0x18009008a  jb      short loc_180090107
0x18009008c  mov     edx, 26h ; '&'
0x180090091  mov     [rsp+530h+var_510], rsi
0x180090096  jmp     short loc_1800900FA
0x180090098  lea     rax, [rsp+530h+var_4D8]
0x18009009d  mov     [rsp+530h+var_4F8], rax
0x1800900a2  lea     rdx, aProxystubclsid; "ProxyStubClsid32"
0x1800900a9  mov     rcx, [rsp+530h+var_4E0]
0x1800900ae  call    DLRegCreateKeyExW
0x1800900b3  mov     edi, eax
0x1800900b5  test    eax, eax
0x1800900b7  jz      short loc_180090116
0x1800900b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800900bf  mov     edx, edi
0x1800900c1  mov     rcx, rax
0x1800900c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800900ca  lea     rax, WPP_GLOBAL_Control
0x1800900d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800900d8  cmp     rcx, rax
0x1800900db  jz      short loc_180090107
0x1800900dd  test    byte ptr [rcx+1Ch], 1
0x1800900e1  jz      short loc_180090107
0x1800900e3  cmp     byte ptr [rcx+19h], 2
0x1800900e7  jb      short loc_180090107
0x1800900e9  mov     edx, 27h ; '''
0x1800900ee  lea     rax, [rbp+430h+var_330]
0x1800900f5  mov     [rsp+530h+var_510], rax
0x1800900fa  mov     r9d, edi
0x1800900fd  mov     rcx, [rcx+10h]
0x180090101  call    WPP_SF_LS
0x180090106  nop
0x180090107  lea     rcx, [rsp+530h+var_4C0]
0x18009010c  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090111  jmp     loc_180090007
0x180090116  mov     r8, [rsp+530h+var_4D8]
0x18009011b  lea     rcx, [rbp+430h+var_4A8]
0x18009011f  call    ??$MakeGuard@P6AJPEAUHKEY__@@@ZPEAU1@@@YA?AV?$ScopeGuardImpl1@P6AJPEAUHKEY__@@@ZPEAU1@@@P6AJPEAUHKEY__@@@Z0@Z; MakeGuard<long (*)(HKEY__ *),HKEY__ *>(long (*)(HKEY__ *),HKEY__ *)
0x180090124  nop
0x180090125  lea     rcx, [rbp+430h+var_430]
0x180090129  mov     rax, rbx
0x18009012c  inc     rax
0x18009012f  cmp     [rcx+rax*2], r14w
0x180090134  jnz     short loc_18009012C
0x180090136  lea     eax, ds:2[rax*2]
0x18009013d  mov     dword ptr [rsp+530h+var_508], eax
0x180090141  lea     rax, [rbp+430h+var_430]
0x180090145  mov     [rsp+530h+var_510], rax
0x18009014a  xor     edx, edx
0x18009014c  mov     rcx, [rsp+530h+var_4D8]
0x180090151  call    DLRegSetValueExW
0x180090156  mov     edi, eax
0x180090158  test    eax, eax
0x18009015a  jz      short loc_1800901BB
0x18009015c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090162  mov     edx, edi
0x180090164  mov     rcx, rax
0x180090167  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009016d  lea     rax, WPP_GLOBAL_Control
0x180090174  mov     rcx, cs:WPP_GLOBAL_Control
0x18009017b  cmp     rcx, rax
0x18009017e  jz      loc_18009022A
0x180090184  test    byte ptr [rcx+1Ch], 1
0x180090188  jz      loc_18009022A
0x18009018e  cmp     byte ptr [rcx+19h], 2
0x180090192  jb      loc_18009022A
0x180090198  lea     rax, [rbp+430h+var_430]
0x18009019c  mov     [rsp+530h+var_508], rax
0x1800901a1  lea     rax, [rbp+430h+var_330]
0x1800901a8  mov     [rsp+530h+var_510], rax
0x1800901ad  mov     r9d, edi
0x1800901b0  mov     rcx, [rcx+10h]
0x1800901b4  call    WPP_SF_LSS
0x1800901b9  jmp     short loc_18009022A
0x1800901bb  lea     rax, [rsp+530h+var_4D0]
0x1800901c0  mov     [rsp+530h+var_4F8], rax
0x1800901c5  lea     rdx, aNummethods; "NumMethods"
0x1800901cc  mov     rcx, [rsp+530h+var_4E0]
0x1800901d1  call    DLRegCreateKeyExW
0x1800901d6  mov     edi, eax
0x1800901d8  test    eax, eax
0x1800901da  jz      short loc_180090238
0x1800901dc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800901e2  mov     edx, edi
0x1800901e4  mov     rcx, rax
0x1800901e7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800901ed  lea     rax, WPP_GLOBAL_Control
0x1800901f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800901fb  cmp     rcx, rax
0x1800901fe  jz      short loc_18009022A
0x180090200  test    byte ptr [rcx+1Ch], 1
0x180090204  jz      short loc_18009022A
0x180090206  cmp     byte ptr [rcx+19h], 2
0x18009020a  jb      short loc_18009022A
0x18009020c  mov     edx, 29h ; ')'
0x180090211  lea     rax, [rbp+430h+var_330]
0x180090218  mov     [rsp+530h+var_510], rax
0x18009021d  mov     r9d, edi
0x180090220  mov     rcx, [rcx+10h]
0x180090224  call    WPP_SF_LS
0x180090229  nop
0x18009022a  lea     rcx, [rbp+430h+var_4A8]
0x18009022e  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x180090233  jmp     loc_180090107
0x180090238  mov     r8, [rsp+530h+var_4D0]
0x18009023d  lea     rcx, [rbp+430h+var_490]
0x180090241  call    ??$MakeGuard@P6AJPEAUHKEY__@@@ZPEAU1@@@YA?AV?$ScopeGuardImpl1@P6AJPEAUHKEY__@@@ZPEAU1@@@P6AJPEAUHKEY__@@@Z0@Z; MakeGuard<long (*)(HKEY__ *),HKEY__ *>(long (*)(HKEY__ *),HKEY__ *)
0x180090246  nop
0x180090247  lea     rax, [rbp+430h+var_470]
0x18009024b  inc     rbx
0x18009024e  cmp     [rax+rbx*2], r14w
0x180090253  jnz     short loc_18009024B
0x180090255  lea     eax, ds:2[rbx*2]
0x18009025c  mov     dword ptr [rsp+530h+var_508], eax
0x180090260  lea     rax, [rbp+430h+var_470]
0x180090264  mov     [rsp+530h+var_510], rax
0x180090269  xor     edx, edx
0x18009026b  mov     rcx, [rsp+530h+var_4D0]
0x180090270  call    DLRegSetValueExW
0x180090275  mov     ebx, eax
0x180090277  test    eax, eax
0x180090279  jz      short loc_1800902CF
0x18009027b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090281  mov     edx, ebx
0x180090283  mov     rcx, rax
0x180090286  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009028c  lea     rax, WPP_GLOBAL_Control
0x180090293  mov     rcx, cs:WPP_GLOBAL_Control
0x18009029a  cmp     rcx, rax
0x18009029d  jz      short loc_1800902C8
0x18009029f  test    byte ptr [rcx+1Ch], 1
0x1800902a3  jz      short loc_1800902C8
0x1800902a5  cmp     byte ptr [rcx+19h], 2
0x1800902a9  jb      short loc_1800902C8
0x1800902ab  mov     edx, 2Ah ; '*'
0x1800902b0  lea     rax, [rbp+430h+var_330]
0x1800902b7  mov     [rsp+530h+var_510], rax
0x1800902bc  mov     r9d, ebx
0x1800902bf  mov     rcx, [rcx+10h]
0x1800902c3  call    WPP_SF_LS
0x1800902c8  mov     ebx, 80004005h
0x1800902cd  jmp     short loc_1800902D2
0x1800902cf  mov     ebx, r14d
0x1800902d2  lea     rcx, [rbp+430h+var_490]
0x1800902d6  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x1800902db  nop
0x1800902dc  lea     rcx, [rbp+430h+var_4A8]
0x1800902e0  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x1800902e5  nop
0x1800902e6  lea     rcx, [rsp+530h+var_4C0]
0x1800902eb  call    ??1?$ScopeGuardImpl1@P6APEAGPEBG@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>::~ScopeGuardImpl1<ushort * (*)(ushort const *),ushort *>(void)
0x1800902f0  mov     eax, ebx
0x1800902f2  mov     rcx, [rbp+430h+var_30]
0x1800902f9  xor     rcx, rsp; StackCookie
0x1800902fc  call    __security_check_cookie
0x180090301  add     rsp, 510h
0x180090308  pop     r14
0x18009030a  pop     rdi
0x18009030b  pop     rsi
0x18009030c  pop     rbx
0x18009030d  pop     rbp
0x18009030e  retn
```
