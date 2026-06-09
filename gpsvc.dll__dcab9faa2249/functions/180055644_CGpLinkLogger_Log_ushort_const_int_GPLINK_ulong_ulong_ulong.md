# CGpLinkLogger::Log(ushort const *,int,_GPLINK *,ulong,ulong,ulong)

- ea: `0x180055644`
- end: `0x180055d83`
- name: `?Log@CGpLinkLogger@@QEAAHPEBGHPEAU_GPLINK@@KKK@Z`
- size: `1855`
- prototype: `int(CGpLinkLogger *__hidden this, const unsigned __int16 *, int, struct _GPLINK *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800ad024`

## callees

- `0x180003770`
- `0x18000a504`
- `0x180055644`
- `0x180055d8c`
- `0x180072a08`
- `0x180073280`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d6f0`
- `0x18007d794`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055d00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055d00`
- `OLEAUT32!__imp_SysAllocString` at `0x180055926`
- `OLEAUT32!__imp_SysAllocString` at `0x180055b51`
- `OLEAUT32!__imp_SysAllocString` at `0x180055926`
- `OLEAUT32!__imp_SysAllocString` at `0x180055b51`
- `OLEAUT32!__imp_SysFreeString` at `0x180055baf`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180055cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180055cd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180055d32`
- `OLEAUT32!__imp_SysFreeString` at `0x180055baf`
- `OLEAUT32!__imp_SysFreeString` at `0x180055bc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180055cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180055cd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180055d32`

## string_xrefs

- `0x18005569b`: `CGpLinkLogger::Log: Failed to initialize.`
- `0x1800556cb`: `CGpLinkLogger::Log: Failed to initialize.`
- `0x180055839`: `CGpLinkLogger::Log: Put failed with 0x%x`
- `0x180055869`: `CGpLinkLogger::Log: Put failed with 0x%x`
- `0x1800559e7`: `CGpLinkLogger::Log: Put failed with 0x%x`
- `0x180055a15`: `CGpLinkLogger::Log: Put failed with 0x%x`
- `0x180055c1e`: `CGpLinkLogger::Log: Put failed with 0x%x`
- `0x180055c41`: `CGpLinkLogger::Log: Put failed with 0x%x`
- `0x180055952`: `CGpLinkLogger::Log: Failed to allocate memory`
- `0x180055975`: `CGpLinkLogger::Log: Failed to allocate memory`
- `0x180055b7a`: `CGpLinkLogger::Log: Failed to allocate memory`
- `0x180055b9d`: `CGpLinkLogger::Log: Failed to allocate memory`
- `0x180055c97`: `CGpLinkLogger::Log: PutInstance failed with 0x%x`
- `0x180055cb2`: `CGpLinkLogger::Log: PutInstance failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CGpLinkLogger::Log(
        CGpLinkLogger *this,
        const unsigned __int16 *a2,
        int a3,
        struct _GPLINK *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  bool v15; // zf
  int v16; // eax
  int v17; // eax
  unsigned __int16 *v18; // r15
  unsigned __int16 *v19; // r14
  const wchar_t *v20; // r9
  const unsigned __int16 *v21; // r8
  OLECHAR *v22; // rcx
  OLECHAR *v23; // rdi
  OLECHAR *v24; // rbx
  OLECHAR *v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rax
  unsigned __int64 v29; // rcx
  __int64 v30; // rax
  unsigned __int64 v31; // rax
  unsigned __int16 *v32; // rsi
  unsigned __int64 v33; // rdx
  unsigned __int16 *i; // rcx
  unsigned __int64 v35; // rax
  BSTR v36; // rax
  OLECHAR *v37; // rdi
  OLECHAR *v38; // rcx
  int v39; // eax
  __int64 v40; // r8
  void (*v41)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v42; // rdx
  int v43; // eax
  __int64 v45; // [rsp+28h] [rbp-C9h]
  OLECHAR *psz; // [rsp+30h] [rbp-C1h] BYREF
  unsigned __int16 *v47; // [rsp+38h] [rbp-B9h] BYREF
  unsigned __int16 *v48; // [rsp+40h] [rbp-B1h] BYREF
  __int128 v49; // [rsp+48h] [rbp-A9h] BYREF
  __int64 v50; // [rsp+58h] [rbp-99h]
  unsigned int v51; // [rsp+60h] [rbp-91h]
  unsigned __int64 v52; // [rsp+68h] [rbp-89h]
  unsigned __int64 v53; // [rsp+70h] [rbp-81h]
  OLECHAR *v54; // [rsp+78h] [rbp-79h]
  __int64 v55; // [rsp+80h] [rbp-71h]
  unsigned __int64 v56; // [rsp+88h] [rbp-69h]
  unsigned __int16 v57[8]; // [rsp+90h] [rbp-61h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-51h]
  int v59; // [rsp+B0h] [rbp-41h]
  _OWORD v60[3]; // [rsp+B8h] [rbp-39h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-9h]

  if ( !*(_DWORD *)this )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CGpLinkLogger::Log: Failed to initialize.");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CGpLinkLogger::Log: Failed to initialize.");
      }
    }
    return 0;
  }
  v49 = 0;
  v50 = 0;
  LOWORD(v49) = 3;
  DWORD2(v49) = a5;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 3),
          0,
          &v49,
          0);
  v12 = (unsigned int)v11;
  if ( v11 < 0 )
    goto LABEL_17;
  LOWORD(v49) = 3;
  DWORD2(v49) = a6;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 4),
          0,
          &v49,
          0);
  v12 = (unsigned int)v13;
  if ( v13 < 0 )
    goto LABEL_17;
  LOWORD(v49) = 3;
  DWORD2(v49) = a7;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 5),
          0,
          &v49,
          0);
  v12 = (unsigned int)v14;
  if ( v14 < 0 )
    goto LABEL_17;
  LOWORD(v49) = 11;
  v15 = *((_DWORD *)a4 + 2) == 0;
  WORD4(v49) = -1;
  if ( v15 )
    WORD4(v49) = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 6),
          0,
          &v49,
          0);
  v12 = (unsigned int)v16;
  if ( v16 < 0 )
    goto LABEL_17;
  v15 = *((_DWORD *)a4 + 3) == 0;
  WORD4(v49) = -1;
  if ( v15 )
    WORD4(v49) = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 7),
          0,
          &v49,
          0);
  v12 = (unsigned int)v17;
  if ( v17 < 0 )
  {
LABEL_17:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CGpLinkLogger::Log: Put failed with 0x%x", v12);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CGpLinkLogger::Log: Put failed with 0x%x", v12);
      }
    }
    return 0;
  }
  v18 = EscapeDNForWMI(a2);
  v48 = v18;
  v19 = EscapeDNForWMI(v18);
  v47 = v19;
  v60[0] = *(_OWORD *)L"RSOP_SOM.id=\"%ws\",reason=%s";
  v60[1] = *(_OWORD *)L".id=\"%ws\",reason=%s";
  v60[2] = *(_OWORD *)L"\",reason=%s";
  v61 = *(_QWORD *)L"=%s";
  psz = 0;
  v20 = L"2";
  if ( v19 )
    v21 = v19;
  else
    v21 = a2;
  if ( !a3 )
    v20 = L"1";
  if ( !(unsigned int)PrintToString(&psz, v60, v21, v20) )
  {
    v22 = psz;
LABEL_95:
    operator delete(v22);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v47);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v48);
    return 0;
  }
  v23 = psz;
  v24 = 0;
  v54 = 0;
  if ( psz )
  {
    v24 = SysAllocString(psz);
    v54 = v24;
  }
  if ( !v24 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CGpLinkLogger::Log: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CGpLinkLogger::Log: Failed to allocate memory");
      }
    }
    v25 = 0;
    goto LABEL_94;
  }
  LOWORD(v49) = 8;
  *((_QWORD *)&v49 + 1) = __PAIR64__(HIDWORD(v54), (unsigned int)v24);
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 1),
          0,
          &v49,
          0);
  if ( v26 < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CGpLinkLogger::Log: Put failed with 0x%x", (unsigned int)v26);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CGpLinkLogger::Log: Put failed with 0x%x", (unsigned int)v26);
      }
    }
    goto LABEL_93;
  }
  *(_OWORD *)v57 = *(_OWORD *)L"RSOP_GPO.id=\"%ws\"";
  v58 = *(_OWORD *)L".id=\"%ws\"";
  v59 = *(_DWORD *)L"\"";
  v27 = *(_QWORD *)a4;
  v55 = *(_QWORD *)a4;
  v28 = -1;
  do
    ++v28;
  while ( v57[v28] );
  v29 = (unsigned int)(v28 + 32);
  v51 = v28 + 32;
  if ( v27 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(v27 + 2 * v30) );
    v29 = (unsigned int)(v30 + v29);
    v51 = v29;
  }
  v52 = v29;
  v31 = 2 * v29;
  if ( !is_mul_ok(v29, 2u) )
    v31 = -1;
  v32 = (unsigned __int16 *)operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
  operator delete(0);
  v56 = (unsigned __int64)v32;
  if ( !v32 )
  {
LABEL_92:
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"PrintToString: Failed to allocate memory");
    operator delete(0);
LABEL_93:
    v25 = v24;
LABEL_94:
    SysFreeString(v25);
    v22 = v23;
    goto LABEL_95;
  }
  v33 = v52;
  for ( i = v32; ; i = (unsigned __int16 *)v52 )
  {
    LODWORD(v45) = 0;
    if ( (int)StringCchPrintfW(i, v33, v57, v55, 0, v45) >= 0 )
      break;
    v51 *= 2;
    v53 = v51;
    v35 = 2LL * v51;
    if ( !is_mul_ok(v51, 2u) )
      v35 = -1;
    v52 = (unsigned __int64)operator new[](v35, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v32);
    v32 = (unsigned __int16 *)v52;
    v56 = v52;
    if ( !v52 )
      goto LABEL_92;
    v33 = v53;
  }
  v36 = SysAllocString(v32);
  v37 = v36;
  v53 = (unsigned __int64)v36;
  if ( !v36 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CGpLinkLogger::Log: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CGpLinkLogger::Log: Failed to allocate memory");
      }
    }
    v38 = 0;
    goto LABEL_70;
  }
  *((_QWORD *)&v49 + 1) = __PAIR64__(HIDWORD(v53), (unsigned int)v36);
  v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, _DWORD))(**((_QWORD **)this + 10) + 40LL))(
          *((_QWORD *)this + 10),
          *((_QWORD *)this + 2),
          0,
          &v49,
          0);
  v40 = (unsigned int)v39;
  if ( v39 < 0 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_79:
      v38 = v37;
LABEL_70:
      SysFreeString(v38);
      operator delete(v32);
      SysFreeString(v24);
      v22 = psz;
      goto LABEL_95;
    }
    v41 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"CGpLinkLogger::Log: Put failed with 0x%x", v40);
      goto LABEL_79;
    }
    v42 = L"CGpLinkLogger::Log: Put failed with 0x%x";
LABEL_75:
    v41(2u, v42, v40);
    goto LABEL_79;
  }
  v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 11) + 112LL))(
          *((_QWORD *)this + 11),
          *((_QWORD *)this + 10),
          0,
          0,
          0);
  v40 = (unsigned int)v43;
  if ( v43 < 0 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_79;
    v41 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"CGpLinkLogger::Log: PutInstance failed with 0x%x", v40);
      goto LABEL_79;
    }
    v42 = L"CGpLinkLogger::Log: PutInstance failed with 0x%x";
    goto LABEL_75;
  }
  SysFreeString(v37);
  operator delete(v32);
  SysFreeString(v24);
  operator delete(psz);
  if ( v19 )
    LocalFree(v19);
  if ( v18 )
    LocalFree(v18);
  return 1;
}

```

## disassembly

```asm
0x180055644  mov     [rsp-8+arg_10], rbx
0x180055649  push    rbp
0x18005564a  push    rsi
0x18005564b  push    rdi
0x18005564c  push    r12
0x18005564e  push    r13
0x180055650  push    r14
0x180055652  push    r15
0x180055654  lea     rbp, [rsp-0Fh]
0x180055659  sub     rsp, 100h
0x180055660  mov     rax, cs:__security_cookie
0x180055667  xor     rax, rsp
0x18005566a  mov     [rbp+3Fh+var_40], rax
0x18005566e  mov     rsi, r9
0x180055671  mov     ebx, r8d
0x180055674  mov     rdi, rdx
0x180055677  mov     r13, rcx
0x18005567a  xor     r12d, r12d
0x18005567d  cmp     [rcx], r12d
0x180055680  jnz     short loc_1800556E1
0x180055682  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180055689  jz      loc_180055D5A
0x18005568f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180055696  test    rax, rax
0x180055699  jz      short loc_1800556B1
0x18005569b  lea     rdx, aCgplinkloggerL_2; "CGpLinkLogger::Log: Failed to initializ"...
0x1800556a2  lea     ecx, [r12+2]
0x1800556a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556ac  jmp     loc_180055D5A
0x1800556b1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800556b8  jz      loc_180055D5A
0x1800556be  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800556c5  jz      loc_180055D5A
0x1800556cb  lea     rdx, aCgplinkloggerL_2; "CGpLinkLogger::Log: Failed to initializ"...
0x1800556d2  mov     ecx, 2; unsigned int
0x1800556d7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800556dc  jmp     loc_180055D5A
0x1800556e1  xorps   xmm0, xmm0
0x1800556e4  xor     eax, eax
0x1800556e6  movups  [rsp+130h+var_E8], xmm0
0x1800556eb  mov     [rsp+130h+var_D8], rax
0x1800556f0  lea     r14d, [rax+3]
0x1800556f4  mov     word ptr [rsp+130h+var_E8], r14w
0x1800556fa  mov     eax, [rbp+3Fh+arg_20]
0x1800556fd  mov     dword ptr [rsp+130h+var_E8+8], eax
0x180055701  mov     rcx, [rcx+50h]
0x180055705  mov     rax, [rcx]
0x180055708  mov     dword ptr [rsp+130h+var_110], r12d
0x18005570d  lea     r9, [rsp+130h+var_E8]
0x180055712  xor     r8d, r8d
0x180055715  mov     rdx, [r13+18h]
0x180055719  mov     rax, [rax+28h]
0x18005571d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055722  mov     r8d, eax
0x180055725  test    eax, eax
0x180055727  js      loc_180055820
0x18005572d  mov     word ptr [rsp+130h+var_E8], r14w
0x180055733  mov     eax, [rbp+3Fh+arg_28]
0x180055736  mov     dword ptr [rsp+130h+var_E8+8], eax
0x18005573a  mov     rcx, [r13+50h]
0x18005573e  mov     rax, [rcx]
0x180055741  mov     dword ptr [rsp+130h+var_110], r12d
0x180055746  lea     r9, [rsp+130h+var_E8]
0x18005574b  xor     r8d, r8d
0x18005574e  mov     rdx, [r13+20h]
0x180055752  mov     rax, [rax+28h]
0x180055756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005575b  mov     r8d, eax
0x18005575e  test    eax, eax
0x180055760  js      loc_180055820
0x180055766  mov     word ptr [rsp+130h+var_E8], r14w
0x18005576c  mov     eax, [rbp+3Fh+arg_30]
0x18005576f  mov     dword ptr [rsp+130h+var_E8+8], eax
0x180055773  mov     rcx, [r13+50h]
0x180055777  mov     rax, [rcx]
0x18005577a  mov     dword ptr [rsp+130h+var_110], r12d
0x18005577f  lea     r9, [rsp+130h+var_E8]
0x180055784  xor     r8d, r8d
0x180055787  mov     rdx, [r13+28h]
0x18005578b  mov     rax, [rax+28h]
0x18005578f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055794  mov     r8d, eax
0x180055797  test    eax, eax
0x180055799  js      loc_180055820
0x18005579f  lea     eax, [r14+8]
0x1800557a3  mov     word ptr [rsp+130h+var_E8], ax
0x1800557a8  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800557ac  cmp     [rsi+8], r12d
0x1800557b0  mov     word ptr [rsp+130h+var_E8+8], r14w
0x1800557b6  jnz     short loc_1800557BE
0x1800557b8  mov     word ptr [rsp+130h+var_E8+8], r12w
0x1800557be  mov     rcx, [r13+50h]
0x1800557c2  mov     rax, [rcx]
0x1800557c5  mov     dword ptr [rsp+130h+var_110], r12d
0x1800557ca  lea     r9, [rsp+130h+var_E8]
0x1800557cf  xor     r8d, r8d
0x1800557d2  mov     rdx, [r13+30h]
0x1800557d6  mov     rax, [rax+28h]
0x1800557da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557df  mov     r8d, eax
0x1800557e2  test    eax, eax
0x1800557e4  js      short loc_180055820
0x1800557e6  cmp     [rsi+0Ch], r12d
0x1800557ea  mov     word ptr [rsp+130h+var_E8+8], r14w
0x1800557f0  jnz     short loc_1800557F8
0x1800557f2  mov     word ptr [rsp+130h+var_E8+8], r12w
0x1800557f8  mov     rcx, [r13+50h]
0x1800557fc  mov     rax, [rcx]
0x1800557ff  mov     dword ptr [rsp+130h+var_110], r12d
0x180055804  lea     r9, [rsp+130h+var_E8]
0x180055809  xor     r8d, r8d
0x18005580c  mov     rdx, [r13+38h]
0x180055810  mov     rax, [rax+28h]
0x180055814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055819  mov     r8d, eax
0x18005581c  test    eax, eax
0x18005581e  jns     short loc_18005587F
0x180055820  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180055827  jz      loc_180055D5A
0x18005582d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180055834  test    rax, rax
0x180055837  jz      short loc_18005584F
0x180055839  lea     rdx, aCgplinkloggerL_1; "CGpLinkLogger::Log: Put failed with 0x%"...
0x180055840  mov     ecx, 2
0x180055845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005584a  jmp     loc_180055D5A
0x18005584f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180055856  jz      loc_180055D5A
0x18005585c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180055863  jz      loc_180055D5A
0x180055869  lea     rdx, aCgplinkloggerL_1; "CGpLinkLogger::Log: Put failed with 0x%"...
0x180055870  mov     ecx, 2; unsigned int
0x180055875  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005587a  jmp     loc_180055D5A
0x18005587f  mov     rcx, rdi; unsigned __int16 *
0x180055882  call    ?EscapeDNForWMI@@YAPEAGPEBG@Z; EscapeDNForWMI(ushort const *)
0x180055887  mov     r15, rax
0x18005588a  mov     [rsp+130h+var_F0], rax
0x18005588f  mov     rcx, rax; unsigned __int16 *
0x180055892  call    ?EscapeDNForWMI@@YAPEAGPEBG@Z; EscapeDNForWMI(ushort const *)
0x180055897  mov     r14, rax
0x18005589a  mov     [rsp+130h+var_F8], rax
0x18005589f  movups  xmm0, xmmword ptr cs:aRsopSomIdWsRea; "RSOP_SOM.id=\"%ws\",reason=%s"
0x1800558a6  movups  [rbp+3Fh+var_78], xmm0
0x1800558aa  movups  xmm1, xmmword ptr cs:aRsopSomIdWsRea+10h; ".id=\"%ws\",reason=%s"
0x1800558b1  movups  [rbp+3Fh+var_68], xmm1
0x1800558b5  movups  xmm0, xmmword ptr cs:aRsopSomIdWsRea+20h; "\",reason=%s"
0x1800558bc  movups  [rbp+3Fh+var_58], xmm0
0x1800558c0  movsd   xmm1, qword ptr cs:aRsopSomIdWsRea+30h; "=%s"
0x1800558c8  movsd   [rbp+3Fh+var_48], xmm1
0x1800558cd  mov     [rsp+130h+psz], r12
0x1800558d2  lea     r9, a2; "2"
0x1800558d9  lea     rdx, [rbp+3Fh+var_78]
0x1800558dd  lea     rcx, [rsp+130h+psz]
0x1800558e2  test    rax, rax
0x1800558e5  lea     rax, a1; "1"
0x1800558ec  jz      short loc_18005590D
0x1800558ee  mov     r8, r14
0x1800558f1  test    ebx, ebx
0x1800558f3  cmovz   r9, rax
0x1800558f7  call    ?PrintToString@@YAHAEAV?$XPtrST@G@@PEBG11K@Z; PrintToString(XPtrST<ushort> &,ushort const *,ushort const *,ushort const *,ulong)
0x1800558fc  test    eax, eax
0x1800558fe  jnz     short loc_180055912
0x180055900  lea     edx, [rax+2]
0x180055903  mov     rcx, [rsp+130h+psz]
0x180055908  jmp     loc_180055D3F
0x18005590d  mov     r8, rdi
0x180055910  jmp     short loc_1800558F1
0x180055912  mov     rdi, [rsp+130h+psz]
0x180055917  mov     rbx, r12
0x18005591a  mov     [rbp+3Fh+var_B8], rbx
0x18005591e  test    rdi, rdi
0x180055921  jz      short loc_180055933
0x180055923  mov     rcx, rdi; psz
0x180055926  call    cs:__imp_SysAllocString
0x18005592c  mov     rbx, rax
0x18005592f  mov     [rbp+3Fh+var_B8], rax
0x180055933  test    rbx, rbx
0x180055936  jnz     short loc_18005598C
0x180055938  xor     ecx, ecx
0x18005593a  lea     r12d, [rbx+2]
0x18005593e  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x180055944  jz      short loc_180055985
0x180055946  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005594d  test    rax, rax
0x180055950  jz      short loc_180055963
0x180055952  lea     rdx, aCgplinkloggerL; "CGpLinkLogger::Log: Failed to allocate "...
0x180055959  mov     ecx, r12d
0x18005595c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055961  jmp     short loc_180055985
0x180055963  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x18005596a  jz      short loc_180055985
0x18005596c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180055973  jz      short loc_180055985
0x180055975  lea     rdx, aCgplinkloggerL; "CGpLinkLogger::Log: Failed to allocate "...
0x18005597c  mov     ecx, r12d; unsigned int
0x18005597f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180055984  nop
0x180055985  xor     ecx, ecx
0x180055987  jmp     loc_180055D32
0x18005598c  mov     eax, 8
0x180055991  mov     word ptr [rsp+130h+var_E8], ax
0x180055996  mov     dword ptr [rsp+130h+var_E8+8], ebx
0x18005599a  mov     eax, dword ptr [rbp+3Fh+var_B8+4]
0x18005599d  mov     dword ptr [rsp+130h+var_E8+0Ch], eax
0x1800559a1  mov     rcx, [r13+50h]
0x1800559a5  mov     rax, [rcx]
0x1800559a8  mov     dword ptr [rsp+130h+var_110], r12d
0x1800559ad  lea     r9, [rsp+130h+var_E8]
0x1800559b2  xor     r8d, r8d
0x1800559b5  mov     rdx, [r13+8]
0x1800559b9  mov     rax, [rax+28h]
0x1800559bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559c2  mov     r8d, eax
0x1800559c5  test    eax, eax
0x1800559c7  jns     short loc_180055A29
0x1800559c9  xor     ecx, ecx
0x1800559cb  lea     r12d, [rcx+2]
0x1800559cf  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x1800559d5  jz      loc_180055D2F
0x1800559db  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800559e2  test    rax, rax
0x1800559e5  jz      short loc_1800559FB
0x1800559e7  lea     rdx, aCgplinkloggerL_1; "CGpLinkLogger::Log: Put failed with 0x%"...
0x1800559ee  mov     ecx, r12d
0x1800559f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559f6  jmp     loc_180055D2F
0x1800559fb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x180055a02  jz      loc_180055D2F
0x180055a08  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180055a0f  jz      loc_180055D2F
0x180055a15  lea     rdx, aCgplinkloggerL_1; "CGpLinkLogger::Log: Put failed with 0x%"...
0x180055a1c  mov     ecx, r12d; unsigned int
0x180055a1f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180055a24  jmp     loc_180055D2F
0x180055a29  movups  xmm0, xmmword ptr cs:aRsopGpoIdWs; "RSOP_GPO.id=\"%ws\""
0x180055a30  movups  xmmword ptr [rbp+3Fh+var_A0], xmm0
0x180055a34  movups  xmm1, xmmword ptr cs:aRsopGpoIdWs+10h; ".id=\"%ws\""
0x180055a3b  movups  [rbp+3Fh+var_90], xmm1
0x180055a3f  mov     eax, dword ptr cs:aRsopGpoIdWs+20h; "\""
0x180055a45  mov     [rbp+3Fh+var_80], eax
0x180055a48  mov     rdx, [rsi]
0x180055a4b  mov     [rbp+3Fh+var_B0], rdx
0x180055a4f  lea     rcx, [rbp+3Fh+var_A0]
0x180055a53  or      r8, 0FFFFFFFFFFFFFFFFh
0x180055a57  mov     rax, r8
0x180055a5a  inc     rax
0x180055a5d  cmp     [rcx+rax*2], r12w
0x180055a62  jnz     short loc_180055A5A
0x180055a64  lea     ecx, [rax+20h]
0x180055a67  mov     [rsp+130h+var_D0], ecx
0x180055a6b  test    rdx, rdx
0x180055a6e  jz      short loc_180055A83
0x180055a70  mov     rax, r8
0x180055a73  inc     rax
0x180055a76  cmp     [rdx+rax*2], r12w
0x180055a7b  jnz     short loc_180055A73
0x180055a7d  add     ecx, eax
0x180055a7f  mov     [rsp+130h+var_D0], ecx
0x180055a83  mov     [rsp+130h+var_C8], rcx
0x180055a88  mov     r12d, 2
0x180055a8e  mov     eax, r12d
0x180055a91  mul     rcx
0x180055a94  cmovb   rax, r8
0x180055a98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180055a9f  mov     rcx, rax; unsigned __int64
0x180055aa2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180055aa7  mov     rsi, rax
0x180055aaa  mov     edx, r12d
0x180055aad  xor     ecx, ecx; Block
0x180055aaf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180055ab4  mov     [rbp+3Fh+var_A8], rsi
0x180055ab8  test    rsi, rsi
0x180055abb  jz      loc_180055D0D
0x180055ac1  mov     rdx, [rsp+130h+var_C8]; unsigned __int64
0x180055ac6  mov     rcx, rsi; unsigned __int16 *
0x180055ac9  mov     dword ptr [rsp+130h+var_108], 0
0x180055ad1  mov     [rsp+130h+var_110], 0
0x180055ada  mov     r9, [rbp+3Fh+var_B0]
0x180055ade  lea     r8, [rbp+3Fh+var_A0]; unsigned __int16 *
0x180055ae2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055ae7  test    eax, eax
0x180055ae9  jns     short loc_180055B4E
0x180055aeb  mov     eax, [rsp+130h+var_D0]
0x180055aef  add     eax, eax
0x180055af1  mov     [rsp+130h+var_D0], eax
0x180055af5  mov     ecx, eax
0x180055af7  mov     [rsp+130h+var_C0], rcx
0x180055afc  mov     rax, r12
0x180055aff  mul     rcx
0x180055b02  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180055b09  cmovb   rax, rcx
0x180055b0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180055b14  mov     rcx, rax; unsigned __int64
0x180055b17  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180055b1c  mov     [rsp+130h+var_C8], rax
0x180055b21  mov     rdx, r12
0x180055b24  mov     rcx, rsi; Block
0x180055b27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180055b2c  mov     rax, [rsp+130h+var_C8]
  ... truncated ...
```
