# CPDFComponent::ImportToProvider(ISimpleTableWrite *)

- ea: `0x1800465e0`
- end: `0x180046e57`
- name: `?ImportToProvider@CPDFComponent@@QEAAJPEAUISimpleTableWrite@@@Z`
- size: `2167`
- prototype: `__int64 __fastcall(CPDFComponent *__hidden this, struct ISimpleTableWrite *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004557c`

## callees

- `0x180044d94`
- `0x1800465e0`
- `0x180046e60`
- `0x180055526`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180046af9`
- `msvcrt!_wcsicmp` at `0x180046b18`
- `msvcrt!_wcsicmp` at `0x180046af9`
- `msvcrt!_wcsicmp` at `0x180046b18`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004690f`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180046bf2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180046d25`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004690f`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180046bf2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180046d25`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046652`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800466e3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046771`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046652`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800466e3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046771`

## string_xrefs

- `0x180046669`: `Install`

## pseudocode

```c
__int64 __fastcall CPDFComponent::ImportToProvider(CPDFComponent *this, struct ISimpleTableWrite *a2)
{
  const OLECHAR *v4; // rcx
  int SimpleTableDispenser; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // r14d
  int v9; // eax
  const wchar_t *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // r14
  CPDFInterface *v14; // rcx
  __int64 v15; // rcx
  struct ISimpleTableWrite *v17; // [rsp+50h] [rbp-89h] BYREF
  int v18; // [rsp+58h] [rbp-81h] BYREF
  signed __int64 v19; // [rsp+60h] [rbp-79h] BYREF
  int v20; // [rsp+68h] [rbp-71h] BYREF
  __int64 v21; // [rsp+70h] [rbp-69h] BYREF
  int v22; // [rsp+78h] [rbp-61h] BYREF
  int v23; // [rsp+7Ch] [rbp-5Dh] BYREF
  int v24; // [rsp+80h] [rbp-59h] BYREF
  GUID *p_pclsid; // [rsp+88h] [rbp-51h] BYREF
  __int64 v26; // [rsp+90h] [rbp-49h]
  int v27; // [rsp+98h] [rbp-41h]
  int v28; // [rsp+9Ch] [rbp-3Dh]
  int *v29; // [rsp+A0h] [rbp-39h]
  int v30; // [rsp+A8h] [rbp-31h]
  int v31; // [rsp+ACh] [rbp-2Dh]
  int v32; // [rsp+B0h] [rbp-29h]
  int v33; // [rsp+B4h] [rbp-25h]
  GUID pclsid; // [rsp+B8h] [rbp-21h] BYREF
  GUID v35; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v36; // [rsp+D8h] [rbp-1h] BYREF
  __int128 v37; // [rsp+E8h] [rbp+Fh]

  v18 = 0;
  v4 = (const OLECHAR *)*((_QWORD *)this + 1);
  pclsid = GUID_NULL;
  v22 = 0;
  v35 = GUID_NULL;
  v23 = 1;
  v20 = 1;
  v36 = 0;
  v24 = 0;
  v37 = 0;
  v21 = 0;
  SimpleTableDispenser = CLSIDFromString(v4, &pclsid);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  v6 = wcscmp_0(*((const wchar_t **)this + 16), L"Install");
  v7 = *(_QWORD *)a2;
  v8 = v6;
  *((_QWORD *)&v36 + 1) = &GUID_DefaultAppPartition;
  *(_QWORD *)&v36 = &pclsid;
  *(_QWORD *)&v37 = &GUID_NULL;
  *((_QWORD *)&v37 + 1) = &v20;
  v9 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, __int128 *))(v7 + 56))(a2, 0, &v36);
  if ( !v9 )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 128LL))(a2);
    if ( SimpleTableDispenser )
      goto LABEL_89;
    if ( v8 )
    {
      SimpleTableDispenser = CLSIDFromString(*(LPCOLESTR *)this, &v35);
      if ( SimpleTableDispenser )
        goto LABEL_89;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                               a2,
                               9,
                               0,
                               &v35);
      if ( SimpleTableDispenser )
        goto LABEL_89;
    }
    goto LABEL_7;
  }
  if ( v9 != -2146367487 )
    goto LABEL_7;
  if ( !v8 )
  {
    SimpleTableDispenser = -2146368488;
    goto LABEL_89;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 120LL))(a2);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = CLSIDFromString(*(LPCOLESTR *)this, &v35);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           0,
                           0,
                           &pclsid);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           1,
                           0,
                           *((_QWORD *)this + 9));
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           9,
                           0,
                           &v35);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           52,
                           0,
                           &v23);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           54,
                           0,
                           &v24);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           6,
                           0,
                           &GUID_DefaultAppPartition);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           7,
                           0,
                           &GUID_NULL);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           8,
                           0,
                           &v20);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  v11 = qword_180075518;
  p_pclsid = &pclsid;
  v29 = &v20;
  v19 = 0;
  v26 = 0;
  v27 = 72;
  v28 = 16;
  v30 = 0;
  v31 = 8;
  v32 = 19;
  v33 = 4;
  v21 = 0;
  if ( qword_180075518 )
    goto LABEL_28;
  v17 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v17);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( !v17 )
    {
      SimpleTableDispenser = -2147024882;
      goto LABEL_89;
    }
    if ( _InterlockedCompareExchange64(&qword_180075518, (signed __int64)v17, 0) )
      (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 16LL))(v17);
    v11 = qword_180075518;
LABEL_28:
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, GUID **, __int64, int, int, __int64 *))(*(_QWORD *)v11 + 24LL))(
                             v11,
                             didCOMSERVICES,
                             tidCOMSERVICES_CLASSES,
                             &p_pclsid,
                             2,
                             1,
                             2097159,
                             &v21);
  }
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, signed __int64 *))(*(_QWORD *)v21 + 64LL))(
                           v21,
                           2,
                           0,
                           0,
                           &v19);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_89;
  if ( v19 )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64))(*(_QWORD *)a2 + 160LL))(
                             a2,
                             48);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_89;
  }
LABEL_7:
  v10 = (const wchar_t *)*((_QWORD *)this + 4);
  if ( !wcscmp_0(v10, L"Required") )
  {
    v18 = 3;
  }
  else if ( !wcscmp_0(v10, L"Requires new") )
  {
    v18 = 4;
  }
  else if ( !wcscmp_0(v10, L"Supported") )
  {
    v18 = 2;
  }
  else if ( !wcscmp_0(v10, L"Not supported") )
  {
    v18 = 1;
  }
  else if ( !wcscmp_0(v10, L"Ignored") )
  {
    v18 = 0;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           17,
                           0,
                           &v18);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  if ( !_wcsicmp(*((const wchar_t **)this + 7), L"N") )
  {
    SimpleTableDispenser = -2147467259;
    goto LABEL_89;
  }
  if ( !_wcsicmp(*((const wchar_t **)this + 13), L"Y") )
    v22 = 1;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                           a2,
                           23,
                           0,
                           &v22);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 96LL))(a2);
  if ( SimpleTableDispenser )
    goto LABEL_89;
  if ( !*((_DWORD *)this + 56) )
    goto LABEL_74;
  v12 = qword_180075518;
  p_pclsid = &pclsid;
  v29 = &v20;
  v26 = 0;
  v27 = 72;
  v28 = 16;
  v30 = 0;
  v31 = 4;
  v32 = 19;
  v33 = 4;
  v17 = 0;
  if ( !qword_180075518 )
  {
    v19 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v19);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_63;
    if ( !v19 )
    {
      SimpleTableDispenser = -2147024882;
      goto LABEL_71;
    }
    if ( _InterlockedCompareExchange64(&qword_180075518, v19, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v19 + 16LL))(v19);
    v12 = qword_180075518;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *, GUID **, __int64, int, int, struct ISimpleTableWrite **))(*(_QWORD *)v12 + 24LL))(
                           v12,
                           didCOMSERVICES,
                           &tidCOMSERVICES_CLASSINTERFACE,
                           &p_pclsid,
                           2,
                           1,
                           4,
                           &v17);
LABEL_63:
  if ( !SimpleTableDispenser )
  {
    if ( !v17 )
    {
      SimpleTableDispenser = -2147024882;
      goto LABEL_89;
    }
    SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 24LL))(v17);
    if ( !SimpleTableDispenser )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 32LL))(v17);
      if ( !SimpleTableDispenser )
      {
        v13 = (_QWORD *)*((_QWORD *)this + 26);
        do
        {
          if ( !v13 )
            break;
          v14 = (CPDFInterface *)v13[2];
          v13 = (_QWORD *)*v13;
          SimpleTableDispenser = CPDFInterface::ImportToProvider(v14, v17);
        }
        while ( !SimpleTableDispenser );
      }
    }
  }
LABEL_71:
  if ( v17 )
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 16LL))(v17);
  if ( !SimpleTableDispenser )
  {
LABEL_74:
    if ( !*((_DWORD *)this + 42) )
      goto LABEL_89;
    v15 = qword_180075518;
    v17 = 0;
    if ( !qword_180075518 )
    {
      v19 = 0;
      SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v19);
      if ( SimpleTableDispenser < 0 )
      {
LABEL_83:
        if ( SimpleTableDispenser >= 0 )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 24LL))(v17);
          if ( SimpleTableDispenser >= 0 )
          {
            SimpleTableDispenser = AddRolesToProvider(
                                     30,
                                     (__int64)v17,
                                     (__int64)this + 256,
                                     *(const OLECHAR **)this,
                                     *((const OLECHAR **)this + 1),
                                     0,
                                     (__int64)this + 144);
            if ( !SimpleTableDispenser )
              SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 96LL))(v17);
          }
        }
        goto LABEL_87;
      }
      if ( !v19 )
      {
        SimpleTableDispenser = -2147024882;
LABEL_87:
        if ( v17 )
          (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v17 + 16LL))(v17);
        goto LABEL_89;
      }
      if ( _InterlockedCompareExchange64(&qword_180075518, v19, 0) )
        (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v19 + 16LL))(v19);
      v15 = qword_180075518;
    }
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD, _QWORD, int, int, struct ISimpleTableWrite **))(*(_QWORD *)v15 + 24LL))(
                             v15,
                             didCOMSERVICES,
                             tidCOMSERVICES_LT_ROLESBYCLSID,
                             0,
                             0,
                             1,
                             12,
                             &v17);
    goto LABEL_83;
  }
LABEL_89:
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x1800465e0  mov     [rsp-8+arg_10], rbx
0x1800465e5  push    rbp
0x1800465e6  push    rsi
0x1800465e7  push    rdi
0x1800465e8  push    r12
0x1800465ea  push    r13
0x1800465ec  push    r14
0x1800465ee  push    r15
0x1800465f0  lea     rbp, [rsp-27h]
0x1800465f5  sub     rsp, 100h
0x1800465fc  mov     rax, cs:__security_cookie
0x180046603  xor     rax, rsp
0x180046606  mov     [rbp+57h+var_38], rax
0x18004660a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180046611  xor     r15d, r15d
0x180046614  mov     rdi, rdx
0x180046617  mov     rsi, rcx
0x18004661a  mov     [rsp+130h+var_D8], r15d
0x18004661f  mov     rcx, [rcx+8]; lpsz
0x180046623  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180046627  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18004662c  lea     eax, [r15+1]
0x180046630  mov     [rbp+57h+var_B8], r15d
0x180046634  movdqu  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x180046639  mov     [rbp+57h+var_B4], eax
0x18004663c  xorps   xmm0, xmm0
0x18004663f  mov     [rbp+57h+var_C8], eax
0x180046642  movups  [rbp+57h+var_58], xmm0
0x180046646  mov     [rbp+57h+var_B0], r15d
0x18004664a  movups  [rbp+57h+var_48], xmm0
0x18004664e  mov     [rbp+57h+var_C0], r15
0x180046652  call    cs:__imp_CLSIDFromString
0x180046658  mov     ebx, eax
0x18004665a  test    eax, eax
0x18004665c  jnz     loc_180046E19
0x180046662  mov     rcx, [rsi+80h]; String1
0x180046669  lea     rdx, aInstall; "Install"
0x180046670  call    wcscmp_0
0x180046675  mov     rcx, [rdi]
0x180046678  lea     r12, GUID_DefaultAppPartition
0x18004667f  mov     r14d, eax
0x180046682  mov     qword ptr [rbp+57h+var_58+8], r12
0x180046686  lea     rax, [rbp+57h+pclsid]
0x18004668a  xor     edx, edx
0x18004668c  mov     qword ptr [rbp+57h+var_58], rax
0x180046690  lea     r13, GUID_NULL
0x180046697  lea     rax, [rbp+57h+var_C8]
0x18004669b  mov     qword ptr [rbp+57h+var_48], r13
0x18004669f  mov     qword ptr [rbp+57h+var_48+8], rax
0x1800466a3  lea     r8, [rbp+57h+var_58]
0x1800466a7  mov     rax, [rcx+38h]
0x1800466ab  mov     rcx, rdi
0x1800466ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466b3  test    eax, eax
0x1800466b5  jnz     loc_180046741
0x1800466bb  mov     rax, [rdi]
0x1800466be  mov     rcx, rdi
0x1800466c1  mov     rax, [rax+80h]
0x1800466c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466cd  mov     ebx, eax
0x1800466cf  test    eax, eax
0x1800466d1  jnz     loc_180046E19
0x1800466d7  test    r14d, r14d
0x1800466da  jz      short loc_180046719
0x1800466dc  mov     rcx, [rsi]; lpsz
0x1800466df  lea     rdx, [rbp+57h+var_68]; pclsid
0x1800466e3  call    cs:__imp_CLSIDFromString
0x1800466e9  mov     ebx, eax
0x1800466eb  test    eax, eax
0x1800466ed  jnz     loc_180046E19
0x1800466f3  mov     rax, [rdi]
0x1800466f6  lea     r9, [rbp+57h+var_68]
0x1800466fa  xor     r8d, r8d
0x1800466fd  lea     edx, [rbx+9]
0x180046700  mov     rcx, rdi
0x180046703  mov     rax, [rax+0A0h]
0x18004670a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004670f  mov     ebx, eax
0x180046711  test    eax, eax
0x180046713  jnz     loc_180046E19
0x180046719  mov     rbx, [rsi+20h]
0x18004671d  lea     rdx, aRequired; "Required"
0x180046724  mov     rcx, rbx; String1
0x180046727  call    wcscmp_0
0x18004672c  test    eax, eax
0x18004672e  jnz     loc_180046A57
0x180046734  mov     [rsp+130h+var_D8], 3
0x18004673c  jmp     loc_180046AC6
0x180046741  cmp     eax, 80110801h
0x180046746  jnz     short loc_180046719
0x180046748  test    r14d, r14d
0x18004674b  jz      loc_180046A4D
0x180046751  mov     rax, [rdi]
0x180046754  mov     rcx, rdi
0x180046757  mov     rax, [rax+78h]
0x18004675b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046760  mov     ebx, eax
0x180046762  test    eax, eax
0x180046764  jnz     loc_180046E19
0x18004676a  mov     rcx, [rsi]; lpsz
0x18004676d  lea     rdx, [rbp+57h+var_68]; pclsid
0x180046771  call    cs:__imp_CLSIDFromString
0x180046777  mov     ebx, eax
0x180046779  test    eax, eax
0x18004677b  jnz     loc_180046E19
0x180046781  mov     rax, [rdi]
0x180046784  lea     r9, [rbp+57h+pclsid]
0x180046788  xor     r8d, r8d
0x18004678b  xor     edx, edx
0x18004678d  mov     rcx, rdi
0x180046790  mov     rax, [rax+0A0h]
0x180046797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004679c  mov     ebx, eax
0x18004679e  test    eax, eax
0x1800467a0  jnz     loc_180046E19
0x1800467a6  mov     rax, [rdi]
0x1800467a9  lea     edx, [rbx+1]
0x1800467ac  mov     r9, [rsi+48h]
0x1800467b0  xor     r8d, r8d
0x1800467b3  mov     rcx, rdi
0x1800467b6  mov     rax, [rax+0A0h]
0x1800467bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467c2  mov     ebx, eax
0x1800467c4  test    eax, eax
0x1800467c6  jnz     loc_180046E19
0x1800467cc  mov     rax, [rdi]
0x1800467cf  lea     r9, [rbp+57h+var_68]
0x1800467d3  xor     r8d, r8d
0x1800467d6  lea     edx, [rbx+9]
0x1800467d9  mov     rcx, rdi
0x1800467dc  mov     rax, [rax+0A0h]
0x1800467e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467e8  mov     ebx, eax
0x1800467ea  test    eax, eax
0x1800467ec  jnz     loc_180046E19
0x1800467f2  mov     rax, [rdi]
0x1800467f5  lea     r9, [rbp+57h+var_B4]
0x1800467f9  xor     r8d, r8d
0x1800467fc  lea     edx, [rbx+34h]
0x1800467ff  mov     rcx, rdi
0x180046802  mov     rax, [rax+0A0h]
0x180046809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004680e  mov     ebx, eax
0x180046810  test    eax, eax
0x180046812  jnz     loc_180046E19
0x180046818  mov     rax, [rdi]
0x18004681b  lea     r9, [rbp+57h+var_B0]
0x18004681f  xor     r8d, r8d
0x180046822  lea     edx, [rbx+36h]
0x180046825  mov     rcx, rdi
0x180046828  mov     rax, [rax+0A0h]
0x18004682f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046834  mov     ebx, eax
0x180046836  test    eax, eax
0x180046838  jnz     loc_180046E19
0x18004683e  mov     rax, [rdi]
0x180046841  lea     edx, [rbx+6]
0x180046844  mov     r9, r12
0x180046847  xor     r8d, r8d
0x18004684a  mov     rcx, rdi
0x18004684d  mov     rax, [rax+0A0h]
0x180046854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046859  mov     ebx, eax
0x18004685b  test    eax, eax
0x18004685d  jnz     loc_180046E19
0x180046863  mov     rax, [rdi]
0x180046866  lea     edx, [rbx+7]
0x180046869  mov     r9, r13
0x18004686c  xor     r8d, r8d
0x18004686f  mov     rcx, rdi
0x180046872  mov     rax, [rax+0A0h]
0x180046879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004687e  mov     ebx, eax
0x180046880  test    eax, eax
0x180046882  jnz     loc_180046E19
0x180046888  mov     rax, [rdi]
0x18004688b  lea     r14d, [rbx+8]
0x18004688f  lea     r9, [rbp+57h+var_C8]
0x180046893  xor     r8d, r8d
0x180046896  mov     edx, r14d
0x180046899  mov     rcx, rdi
0x18004689c  mov     rax, [rax+0A0h]
0x1800468a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468a8  mov     ebx, eax
0x1800468aa  test    eax, eax
0x1800468ac  jnz     loc_180046E19
0x1800468b2  mov     rcx, cs:qword_180075518
0x1800468b9  lea     rax, [rbp+57h+pclsid]
0x1800468bd  mov     [rbp+57h+var_A8], rax
0x1800468c1  lea     rax, [rbp+57h+var_C8]
0x1800468c5  mov     [rbp+57h+var_90], rax
0x1800468c9  mov     [rbp+57h+var_D0], r15
0x1800468cd  mov     [rbp+57h+var_A0], r15
0x1800468d1  mov     [rbp+57h+var_98], 48h ; 'H'
0x1800468d8  mov     [rbp+57h+var_94], 10h
0x1800468df  mov     [rbp+57h+var_88], r15d
0x1800468e3  mov     [rbp+57h+var_84], r14d
0x1800468e7  mov     [rbp+57h+var_80], 13h
0x1800468ee  mov     [rbp+57h+var_7C], 4
0x1800468f5  mov     [rbp+57h+var_C0], r15
0x1800468f9  test    rcx, rcx
0x1800468fc  jnz     short loc_180046954
0x1800468fe  lea     rdx, [rsp+130h+var_E0]
0x180046903  mov     [rsp+130h+var_E0], r15
0x180046908  lea     rcx, IID_ISimpleTableDispenser
0x18004690f  call    cs:__imp_GetSimpleTableDispenser
0x180046915  mov     ebx, eax
0x180046917  test    eax, eax
0x180046919  js      short loc_180046996
0x18004691b  mov     rcx, [rsp+130h+var_E0]
0x180046920  test    rcx, rcx
0x180046923  jnz     short loc_18004692F
0x180046925  mov     ebx, 8007000Eh
0x18004692a  jmp     loc_180046E19
0x18004692f  xor     eax, eax
0x180046931  lock cmpxchg cs:qword_180075518, rcx
0x18004693a  jz      short loc_18004694D
0x18004693c  mov     rcx, [rsp+130h+var_E0]
0x180046941  mov     rax, [rcx]
0x180046944  mov     rax, [rax+10h]
0x180046948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004694d  mov     rcx, cs:qword_180075518
0x180046954  mov     rax, [rcx]
0x180046957  lea     rdx, [rbp+57h+var_C0]
0x18004695b  mov     [rsp+130h+var_F8], rdx
0x180046960  lea     r9, [rbp+57h+var_A8]
0x180046964  mov     dword ptr [rsp+130h+var_100], 200007h
0x18004696c  lea     r8, tidCOMSERVICES_CLASSES
0x180046973  mov     dword ptr [rsp+130h+var_108], 1
0x18004697b  lea     rdx, didCOMSERVICES
0x180046982  mov     rax, [rax+18h]
0x180046986  mov     [rsp+130h+var_110], 2
0x18004698f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046994  mov     ebx, eax
0x180046996  test    ebx, ebx
0x180046998  jnz     loc_180046E19
0x18004699e  mov     rcx, [rbp+57h+var_C0]
0x1800469a2  mov     rax, [rcx]
0x1800469a5  mov     rax, [rax+18h]
0x1800469a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469ae  mov     ebx, eax
0x1800469b0  test    eax, eax
0x1800469b2  jnz     loc_180046E19
0x1800469b8  mov     rcx, [rbp+57h+var_C0]
0x1800469bc  mov     rax, [rcx]
0x1800469bf  mov     rax, [rax+20h]
0x1800469c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469c8  mov     ebx, eax
0x1800469ca  test    eax, eax
0x1800469cc  jnz     loc_180046E19
0x1800469d2  mov     rcx, [rbp+57h+var_C0]
0x1800469d6  mov     rax, [rcx]
0x1800469d9  mov     rax, [rax+28h]
0x1800469dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469e2  mov     ebx, eax
0x1800469e4  test    eax, eax
0x1800469e6  jnz     loc_180046E19
0x1800469ec  mov     rcx, [rbp+57h+var_C0]
0x1800469f0  lea     rdx, [rbp+57h+var_D0]
0x1800469f4  mov     [rsp+130h+var_110], rdx
0x1800469f9  xor     r9d, r9d
0x1800469fc  xor     r8d, r8d
0x1800469ff  lea     edx, [rbx+2]
0x180046a02  mov     rax, [rcx]
0x180046a05  mov     rax, [rax+40h]
0x180046a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a0e  mov     ebx, eax
0x180046a10  test    eax, eax
0x180046a12  js      loc_180046E19
0x180046a18  mov     r9, [rbp+57h+var_D0]
0x180046a1c  test    r9, r9
0x180046a1f  jz      loc_180046719
0x180046a25  mov     rax, [rdi]
0x180046a28  xor     r8d, r8d
0x180046a2b  mov     rcx, rdi
0x180046a2e  mov     rax, [rax+0A0h]
0x180046a35  lea     edx, [r8+30h]
0x180046a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a3e  mov     ebx, eax
0x180046a40  test    eax, eax
0x180046a42  js      loc_180046E19
0x180046a48  jmp     loc_180046719
0x180046a4d  mov     ebx, 80110418h
0x180046a52  jmp     loc_180046E19
0x180046a57  lea     rdx, aRequiresNew; "Requires new"
0x180046a5e  mov     rcx, rbx; String1
0x180046a61  call    wcscmp_0
0x180046a66  test    eax, eax
0x180046a68  jnz     short loc_180046A74
0x180046a6a  mov     [rsp+130h+var_D8], 4
0x180046a72  jmp     short loc_180046AC6
0x180046a74  lea     rdx, aSupported; "Supported"
0x180046a7b  mov     rcx, rbx; String1
0x180046a7e  call    wcscmp_0
0x180046a83  test    eax, eax
0x180046a85  jnz     short loc_180046A91
0x180046a87  mov     [rsp+130h+var_D8], 2
0x180046a8f  jmp     short loc_180046AC6
0x180046a91  lea     rdx, aNotSupported; "Not supported"
0x180046a98  mov     rcx, rbx; String1
  ... truncated ...
```
