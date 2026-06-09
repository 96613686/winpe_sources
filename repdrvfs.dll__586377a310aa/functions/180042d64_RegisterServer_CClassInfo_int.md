# RegisterServer(CClassInfo *,int)

- ea: `0x180042d64`
- end: `0x1800432db`
- name: `?RegisterServer@@YAJPEAUCClassInfo@@H@Z`
- size: `1399`
- prototype: `__int64 __fastcall(struct CClassInfo *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043870`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800013c8`
- `0x1800216c8`
- `0x180029fbc`
- `0x1800429e4`
- `0x180042d64`
- `0x180043b78`
- `0x180044000`
- `0x180044208`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042ee5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042ee5`
- `wbemcomn!GetMemLogObject` at `0x180042dd0`
- `wbemcomn!GetMemLogObject` at `0x180042e49`
- `wbemcomn!GetMemLogObject` at `0x180042ef3`
- `wbemcomn!GetMemLogObject` at `0x180042f6e`
- `wbemcomn!GetMemLogObject` at `0x180042ff9`
- `wbemcomn!GetMemLogObject` at `0x18004306f`
- `wbemcomn!GetMemLogObject` at `0x180043103`
- `wbemcomn!GetMemLogObject` at `0x18004318d`
- `wbemcomn!GetMemLogObject` at `0x180043247`
- `wbemcomn!GetMemLogObject` at `0x180042dd0`
- `wbemcomn!GetMemLogObject` at `0x180042e49`
- `wbemcomn!GetMemLogObject` at `0x180042ef3`
- `wbemcomn!GetMemLogObject` at `0x180042f6e`
- `wbemcomn!GetMemLogObject` at `0x180042ff9`
- `wbemcomn!GetMemLogObject` at `0x18004306f`
- `wbemcomn!GetMemLogObject` at `0x180043103`
- `wbemcomn!GetMemLogObject` at `0x18004318d`
- `wbemcomn!GetMemLogObject` at `0x180043247`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042ddb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042e54`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042f01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042f7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043005`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004307a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004310e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043198`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043252`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042ddb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042e54`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042f01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042f7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043005`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004307a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004310e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043198`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043252`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800430f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800430f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180042db4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180042db4`

## string_xrefs

- `0x180043230`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegisterServer(const GUID *const *a1)
{
  __int64 v2; // rdx
  unsigned __int16 *v3; // r9
  int PathString; // ebx
  int v5; // r8d
  int v6; // r9d
  CMemoryLog *MemLogObject; // rax
  int Key; // ebx
  CMemoryLog *v9; // rax
  int v10; // r8d
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned __int64 v14; // r14
  unsigned __int16 *v15; // rax
  __int64 v16; // rsi
  CMemoryLog *v17; // rax
  int v18; // r8d
  int v19; // r14d
  CMemoryLog *v20; // rax
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  int v24; // r14d
  CMemoryLog *v25; // rax
  int v26; // r8d
  unsigned int v27; // esi
  CMemoryLog *v28; // rax
  int v29; // r8d
  CMemoryLog *v30; // rax
  CVarObjHeap *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rax
  int v35; // esi
  int v36; // r8d
  CMemoryLog *v37; // rax
  int v38; // r8d
  const wchar_t *v39; // rcx
  unsigned int v40; // ebx
  CMemoryLog *v41; // rax
  unsigned int v42; // ebx
  _BYTE v43[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall *v44)(_QWORD); // [rsp+68h] [rbp-98h]
  __int64 v45; // [rsp+70h] [rbp-90h]
  _BYTE v46[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v47)(_QWORD); // [rsp+80h] [rbp-80h]
  __int64 v48; // [rsp+88h] [rbp-78h]
  OLECHAR sz[128]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Filename[264]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v51[256]; // [rsp+3A0h] [rbp+2A0h] BYREF

  StringFromGUID2(a1[3], sz, 128);
  PathString = CreatePathString(v51, v2, sz, v3);
  if ( PathString < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, PathString);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, sz);
    }
    return 2147500037LL;
  }
  Key = DLRegCreateKeyExW(-2147483646, (unsigned int)v51, v5, v6);
  if ( Key )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, Key);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v10, Key, (__int64)v51);
    }
    return 2147500037LL;
  }
  v43[0] = 0;
  v44 = DLRegCloseKey;
  v45 = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*((_QWORD *)a1 + 5) + 2 * v13) );
  v14 = (int)v13 + 100;
  v15 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v14, 2u));
  v16 = (__int64)v15;
  if ( !v15 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147024882);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, v51);
    }
LABEL_36:
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v43);
    return 2147500037LL;
  }
  v19 = StringCchPrintfW(v15, v14, L"Microsoft WBEM %s", *((_QWORD *)a1 + 5));
  if ( v19 < 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, v19);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
    }
    goto LABEL_36;
  }
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)(v16 + 2 * v21) );
  v24 = DLRegSetValueExW(0, 0, v18, 1, v16, 2 * (int)v21 + 2);
  if ( v24 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, v24);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v26, v24, v16);
    }
    goto LABEL_36;
  }
  v27 = DLRegCreateKeyExW(0, (unsigned int)L"InprocServer32", v22, v23);
  if ( v27 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v27);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, v27);
    }
    goto LABEL_36;
  }
  v46[0] = 0;
  v47 = DLRegCloseKey;
  v48 = 0;
  Filename[260] = 48;
  if ( !GetModuleFileNameW(hModule, Filename, 0x104u) )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, 0);
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_61;
    }
    v32 = 19;
    v33 = 0;
    goto LABEL_60;
  }
  v34 = -1;
  do
    ++v34;
  while ( Filename[v34] );
  v35 = DLRegSetValueExW(0, 0, v29, 1, (__int64)Filename, 2 * (int)v34 + 2);
  if ( v35 )
  {
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, v35);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v38, v35, (__int64)Filename);
    }
    goto LABEL_61;
  }
  if ( *((_DWORD *)a1 + 12) )
  {
    v39 = L"Both";
    if ( *((_DWORD *)a1 + 13) )
      v39 = L"Free";
  }
  else
  {
    v39 = L"Apartment";
  }
  do
    ++v12;
  while ( v39[v12] );
  v40 = DLRegSetValueExW(0, (unsigned int)L"ThreadingModel", v36, 1, (__int64)v39, 2 * (int)v12 + 2);
  if ( !v40 )
  {
    v42 = 0;
    goto LABEL_63;
  }
  v41 = GetMemLogObject();
  CMemoryLog::Write(v41, v40);
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v32 = 21;
    v33 = v40;
LABEL_60:
    WPP_SF_d(*((_QWORD *)v31 + 2), v32, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, v33);
  }
LABEL_61:
  v42 = -2147467259;
LABEL_63:
  ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v46);
  ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v43);
  return v42;
}

```

## disassembly

```asm
0x180042d64  mov     [rsp-8+arg_8], rbx
0x180042d69  mov     [rsp-8+arg_10], rsi
0x180042d6e  push    rbp
0x180042d6f  push    rdi
0x180042d70  push    r12
0x180042d72  push    r14
0x180042d74  push    r15
0x180042d76  lea     rbp, [rsp-4B0h]
0x180042d7e  sub     rsp, 5B0h
0x180042d85  mov     rax, cs:__security_cookie
0x180042d8c  xor     rax, rsp
0x180042d8f  mov     [rbp+4D0h+var_30], rax
0x180042d96  mov     rdi, rcx
0x180042d99  xor     r15d, r15d
0x180042d9c  mov     [rsp+5D0h+var_580], r15
0x180042da1  mov     [rsp+5D0h+var_578], r15
0x180042da6  mov     r8d, 80h; cchMax
0x180042dac  lea     rdx, [rbp+4D0h+sz]; lpsz
0x180042db0  mov     rcx, [rcx+18h]; rguid
0x180042db4  call    cs:__imp_StringFromGUID2
0x180042dba  lea     r8, [rbp+4D0h+sz]; unsigned __int16 *
0x180042dbe  lea     rcx, [rbp+4D0h+var_230]; unsigned __int16 *
0x180042dc5  call    ?CreatePathString@@YAJPEAGH00@Z; CreatePathString(ushort *,int,ushort *,ushort *)
0x180042dca  mov     ebx, eax
0x180042dcc  test    eax, eax
0x180042dce  jns     short loc_180042E26
0x180042dd0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042dd6  mov     edx, ebx
0x180042dd8  mov     rcx, rax
0x180042ddb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042de1  lea     rax, WPP_GLOBAL_Control
0x180042de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180042def  cmp     rcx, rax
0x180042df2  jz      loc_180042E96
0x180042df8  test    byte ptr [rcx+1Ch], 1
0x180042dfc  jz      loc_180042E96
0x180042e02  cmp     byte ptr [rcx+19h], 2
0x180042e06  jb      loc_180042E96
0x180042e0c  lea     edx, [r15+0Dh]
0x180042e10  lea     r9, [rbp+4D0h+sz]
0x180042e14  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042e1b  mov     rcx, [rcx+10h]
0x180042e1f  call    WPP_SF_S
0x180042e24  jmp     short loc_180042E96
0x180042e26  lea     rax, [rsp+5D0h+var_580]
0x180042e2b  mov     [rsp+5D0h+var_598], rax
0x180042e30  lea     rdx, [rbp+4D0h+var_230]
0x180042e37  mov     rcx, 0FFFFFFFF80000002h
0x180042e3e  call    DLRegCreateKeyExW
0x180042e43  mov     ebx, eax
0x180042e45  test    eax, eax
0x180042e47  jz      short loc_180042EA0
0x180042e49  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042e4f  mov     edx, ebx
0x180042e51  mov     rcx, rax
0x180042e54  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042e5a  lea     rax, WPP_GLOBAL_Control
0x180042e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e68  cmp     rcx, rax
0x180042e6b  jz      short loc_180042E96
0x180042e6d  test    byte ptr [rcx+1Ch], 1
0x180042e71  jz      short loc_180042E96
0x180042e73  cmp     byte ptr [rcx+19h], 2
0x180042e77  jb      short loc_180042E96
0x180042e79  mov     edx, 0Eh
0x180042e7e  lea     rax, [rbp+4D0h+var_230]
0x180042e85  mov     [rsp+5D0h+var_5B0], rax
0x180042e8a  mov     r9d, ebx
0x180042e8d  mov     rcx, [rcx+10h]
0x180042e91  call    WPP_SF_LS
0x180042e96  mov     eax, 80004005h
0x180042e9b  jmp     loc_1800432B0
0x180042ea0  mov     [rsp+5D0h+var_570], r15b
0x180042ea5  lea     r12, DLRegCloseKey
0x180042eac  mov     [rsp+5D0h+var_568], r12
0x180042eb1  mov     rax, [rsp+5D0h+var_580]
0x180042eb6  mov     [rsp+5D0h+var_560], rax
0x180042ebb  mov     rcx, [rdi+28h]
0x180042ebf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180042ec3  mov     rax, rbx
0x180042ec6  inc     rax
0x180042ec9  cmp     [rcx+rax*2], r15w
0x180042ece  jnz     short loc_180042EC6
0x180042ed0  add     eax, 64h ; 'd'
0x180042ed3  movsxd  r14, eax
0x180042ed6  mov     eax, 2
0x180042edb  mul     r14
0x180042ede  cmovb   rax, rbx
0x180042ee2  mov     rcx, rax
0x180042ee5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180042eeb  mov     rsi, rax
0x180042eee  test    rax, rax
0x180042ef1  jnz     short loc_180042F51
0x180042ef3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042ef9  mov     edx, 8007000Eh
0x180042efe  mov     rcx, rax
0x180042f01  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042f07  lea     rax, WPP_GLOBAL_Control
0x180042f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f15  cmp     rcx, rax
0x180042f18  jz      loc_1800430B8
0x180042f1e  test    byte ptr [rcx+1Ch], 1
0x180042f22  jz      loc_1800430B8
0x180042f28  cmp     byte ptr [rcx+19h], 2
0x180042f2c  jb      loc_1800430B8
0x180042f32  lea     edx, [rsi+0Fh]
0x180042f35  lea     r9, [rbp+4D0h+var_230]
0x180042f3c  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042f43  mov     rcx, [rcx+10h]
0x180042f47  call    WPP_SF_S
0x180042f4c  jmp     loc_1800430B8
0x180042f51  mov     r9, [rdi+28h]
0x180042f55  lea     r8, aMicrosoftWbemS; "Microsoft WBEM %s"
0x180042f5c  mov     rdx, r14; unsigned __int64
0x180042f5f  mov     rcx, rsi; unsigned __int16 *
0x180042f62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042f67  mov     r14d, eax
0x180042f6a  test    eax, eax
0x180042f6c  jns     short loc_180042FC5
0x180042f6e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042f74  mov     edx, r14d
0x180042f77  mov     rcx, rax
0x180042f7a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042f80  lea     rax, WPP_GLOBAL_Control
0x180042f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f8e  cmp     rcx, rax
0x180042f91  jz      loc_1800430B8
0x180042f97  test    byte ptr [rcx+1Ch], 1
0x180042f9b  jz      loc_1800430B8
0x180042fa1  cmp     byte ptr [rcx+19h], 2
0x180042fa5  jb      loc_1800430B8
0x180042fab  mov     edx, 10h
0x180042fb0  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042fb7  mov     rcx, [rcx+10h]
0x180042fbb  call    WPP_SF_
0x180042fc0  jmp     loc_1800430B8
0x180042fc5  mov     rax, rbx
0x180042fc8  inc     rax
0x180042fcb  cmp     [rsi+rax*2], r15w
0x180042fd0  jnz     short loc_180042FC8
0x180042fd2  lea     eax, ds:2[rax*2]
0x180042fd9  mov     [rsp+5D0h+var_5A8], eax
0x180042fdd  mov     [rsp+5D0h+var_5B0], rsi
0x180042fe2  xor     edx, edx
0x180042fe4  lea     r9d, [rdx+1]
0x180042fe8  mov     rcx, [rsp+5D0h+var_580]
0x180042fed  call    DLRegSetValueExW
0x180042ff2  mov     r14d, eax
0x180042ff5  test    eax, eax
0x180042ff7  jz      short loc_18004304E
0x180042ff9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042fff  mov     edx, r14d
0x180043002  mov     rcx, rax
0x180043005  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004300b  lea     rax, WPP_GLOBAL_Control
0x180043012  mov     rcx, cs:WPP_GLOBAL_Control
0x180043019  cmp     rcx, rax
0x18004301c  jz      loc_1800430B8
0x180043022  test    byte ptr [rcx+1Ch], 1
0x180043026  jz      loc_1800430B8
0x18004302c  cmp     byte ptr [rcx+19h], 2
0x180043030  jb      loc_1800430B8
0x180043036  mov     edx, 11h
0x18004303b  mov     [rsp+5D0h+var_5B0], rsi
0x180043040  mov     r9d, r14d
0x180043043  mov     rcx, [rcx+10h]
0x180043047  call    WPP_SF_LS
0x18004304c  jmp     short loc_1800430B8
0x18004304e  lea     rax, [rsp+5D0h+var_578]
0x180043053  mov     [rsp+5D0h+var_598], rax
0x180043058  lea     rdx, aInprocserver32; "InprocServer32"
0x18004305f  mov     rcx, [rsp+5D0h+var_580]
0x180043064  call    DLRegCreateKeyExW
0x180043069  mov     esi, eax
0x18004306b  test    eax, eax
0x18004306d  jz      short loc_1800430C7
0x18004306f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043075  mov     edx, esi
0x180043077  mov     rcx, rax
0x18004307a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043080  lea     rax, WPP_GLOBAL_Control
0x180043087  mov     rcx, cs:WPP_GLOBAL_Control
0x18004308e  cmp     rcx, rax
0x180043091  jz      short loc_1800430B8
0x180043093  test    byte ptr [rcx+1Ch], 1
0x180043097  jz      short loc_1800430B8
0x180043099  cmp     byte ptr [rcx+19h], 2
0x18004309d  jb      short loc_1800430B8
0x18004309f  mov     edx, 12h
0x1800430a4  mov     r9d, esi
0x1800430a7  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x1800430ae  mov     rcx, [rcx+10h]
0x1800430b2  call    WPP_SF_d
0x1800430b7  nop
0x1800430b8  lea     rcx, [rsp+5D0h+var_570]
0x1800430bd  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x1800430c2  jmp     loc_180042E96
0x1800430c7  mov     [rsp+5D0h+var_558], r15b
0x1800430cc  mov     [rbp+4D0h+var_550], r12
0x1800430d0  mov     rax, [rsp+5D0h+var_578]
0x1800430d5  mov     [rbp+4D0h+var_548], rax
0x1800430d9  mov     eax, 30h ; '0'
0x1800430de  mov     [rbp+4D0h+var_238], ax
0x1800430e5  mov     r8d, 104h; nSize
0x1800430eb  lea     rdx, [rbp+4D0h+Filename]; lpFilename
0x1800430f2  mov     rcx, cs:hModule; hModule
0x1800430f9  call    cs:__imp_GetModuleFileNameW
0x1800430ff  test    eax, eax
0x180043101  jnz     short loc_18004314C
0x180043103  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043109  xor     edx, edx
0x18004310b  mov     rcx, rax
0x18004310e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043114  lea     rax, WPP_GLOBAL_Control
0x18004311b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043122  cmp     rcx, rax
0x180043125  jz      loc_18004328F
0x18004312b  test    byte ptr [rcx+1Ch], 1
0x18004312f  jz      loc_18004328F
0x180043135  cmp     byte ptr [rcx+19h], 2
0x180043139  jb      loc_18004328F
0x18004313f  mov     edx, 13h
0x180043144  xor     r9d, r9d
0x180043147  jmp     loc_18004327F
0x18004314c  lea     rcx, [rbp+4D0h+Filename]
0x180043153  mov     rax, rbx
0x180043156  inc     rax
0x180043159  cmp     [rcx+rax*2], r15w
0x18004315e  jnz     short loc_180043156
0x180043160  lea     eax, ds:2[rax*2]
0x180043167  mov     [rsp+5D0h+var_5A8], eax
0x18004316b  lea     rax, [rbp+4D0h+Filename]
0x180043172  mov     [rsp+5D0h+var_5B0], rax
0x180043177  xor     edx, edx
0x180043179  lea     r9d, [rdx+1]
0x18004317d  mov     rcx, [rsp+5D0h+var_578]
0x180043182  call    DLRegSetValueExW
0x180043187  mov     esi, eax
0x180043189  test    eax, eax
0x18004318b  jz      short loc_1800431EB
0x18004318d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043193  mov     edx, esi
0x180043195  mov     rcx, rax
0x180043198  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004319e  lea     rax, WPP_GLOBAL_Control
0x1800431a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431ac  cmp     rcx, rax
0x1800431af  jz      loc_18004328F
0x1800431b5  test    byte ptr [rcx+1Ch], 1
0x1800431b9  jz      loc_18004328F
0x1800431bf  cmp     byte ptr [rcx+19h], 2
0x1800431c3  jb      loc_18004328F
0x1800431c9  mov     edx, 14h
0x1800431ce  lea     rax, [rbp+4D0h+Filename]
0x1800431d5  mov     [rsp+5D0h+var_5B0], rax
0x1800431da  mov     r9d, esi
0x1800431dd  mov     rcx, [rcx+10h]
0x1800431e1  call    WPP_SF_LS
0x1800431e6  jmp     loc_18004328F
0x1800431eb  cmp     [rdi+30h], r15d
0x1800431ef  jz      short loc_180043209
0x1800431f1  lea     rax, aFree; "Free"
0x1800431f8  lea     rcx, aBoth; "Both"
0x1800431ff  cmp     [rdi+34h], r15d
0x180043203  cmovnz  rcx, rax
0x180043207  jmp     short loc_180043210
0x180043209  lea     rcx, aApartment; "Apartment"
0x180043210  inc     rbx
0x180043213  cmp     [rcx+rbx*2], r15w
0x180043218  jnz     short loc_180043210
0x18004321a  lea     eax, ds:2[rbx*2]
0x180043221  mov     [rsp+5D0h+var_5A8], eax
0x180043225  mov     [rsp+5D0h+var_5B0], rcx
0x18004322a  mov     r9d, 1
0x180043230  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180043237  mov     rcx, [rsp+5D0h+var_578]
0x18004323c  call    DLRegSetValueExW
0x180043241  mov     ebx, eax
0x180043243  test    eax, eax
0x180043245  jz      short loc_180043296
0x180043247  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004324d  mov     edx, ebx
0x18004324f  mov     rcx, rax
0x180043252  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043258  lea     rax, WPP_GLOBAL_Control
0x18004325f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043266  cmp     rcx, rax
0x180043269  jz      short loc_18004328F
0x18004326b  test    byte ptr [rcx+1Ch], 1
0x18004326f  jz      short loc_18004328F
0x180043271  cmp     byte ptr [rcx+19h], 2
0x180043275  jb      short loc_18004328F
0x180043277  mov     edx, 15h
0x18004327c  mov     r9d, ebx
0x18004327f  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180043286  mov     rcx, [rcx+10h]
0x18004328a  call    WPP_SF_d
0x18004328f  mov     ebx, 80004005h
0x180043294  jmp     short loc_180043299
0x180043296  mov     ebx, r15d
  ... truncated ...
```
