# CPDFPackage::ImportPackageToProvider(CString &,ushort *,ushort *)

- ea: `0x180045c70`
- end: `0x1800465d9`
- name: `?ImportPackageToProvider@CPDFPackage@@QEAAJAEAVCString@@PEAG1@Z`
- size: `2409`
- prototype: `int(CPDFPackage *__hidden this, struct CString *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800474b0`

## callees

- `0x180045c70`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180045fc6`
- `msvcrt!_wcsicmp` at `0x18004609e`
- `msvcrt!_wcsicmp` at `0x180045fc6`
- `msvcrt!_wcsicmp` at `0x18004609e`
- `msvcrt!_wtoi` at `0x180045f13`
- `msvcrt!_wtoi` at `0x180046000`
- `msvcrt!_wtoi` at `0x180045f13`
- `msvcrt!_wtoi` at `0x180046000`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180045d4a`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180045d4a`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x180045cf4`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x180045cf4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045d01`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045d01`

## string_xrefs

- `0x180045f95`: `%systemroot%\system32\com\dmp`
- `0x180046379`: `%systemroot%\system32\com\dmp`

## pseudocode

```c
__int64 __fastcall CPDFPackage::ImportPackageToProvider(
        LPCOLESTR *this,
        struct CString *a2,
        unsigned __int16 *a3,
        BOOL *a4)
{
  HRESULT SimpleTableDispenser; // ebx
  __int64 v8; // rcx
  HRESULT v9; // eax
  int v10; // eax
  BOOL *v11; // r9
  __int64 v12; // rdx
  __int64 v14; // [rsp+50h] [rbp-49h] BYREF
  int v15; // [rsp+58h] [rbp-41h] BYREF
  BOOL v16; // [rsp+5Ch] [rbp-3Dh] BYREF
  int v17; // [rsp+60h] [rbp-39h] BYREF
  int v18; // [rsp+64h] [rbp-35h] BYREF
  int v19; // [rsp+68h] [rbp-31h] BYREF
  int v20; // [rsp+6Ch] [rbp-2Dh] BYREF
  int v21; // [rsp+70h] [rbp-29h] BYREF
  int v22; // [rsp+74h] [rbp-25h] BYREF
  int v23; // [rsp+78h] [rbp-21h] BYREF
  int v24; // [rsp+7Ch] [rbp-1Dh] BYREF
  int v25; // [rsp+80h] [rbp-19h] BYREF
  int v26; // [rsp+84h] [rbp-15h] BYREF
  signed __int64 v27; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v28[2]; // [rsp+90h] [rbp-9h] BYREF
  int v29; // [rsp+A0h] [rbp+7h]
  int v30; // [rsp+A4h] [rbp+Bh]
  GUID pclsid; // [rsp+A8h] [rbp+Fh] BYREF

  v22 = 2;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v17 = 1;
  v25 = 1;
  pclsid = GUID_NULL;
  v15 = 0;
  v23 = 3;
  v24 = 64;
  v21 = 5;
  v26 = 0x40000;
  v14 = 0;
  CString::operator=(this, a2);
  SimpleTableDispenser = CLSIDFromString(*this, &pclsid);
  if ( SimpleTableDispenser )
    goto LABEL_73;
  v8 = qword_180075518;
  v28[0] = &pclsid;
  v28[1] = 0;
  v29 = 72;
  v30 = 16;
  v14 = 0;
  if ( !qword_180075518 )
  {
    v27 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v27);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_10;
    if ( !v27 )
    {
      SimpleTableDispenser = -2147024882;
      goto LABEL_73;
    }
    if ( _InterlockedCompareExchange64(&qword_180075518, v27, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v27 + 16LL))(v27);
    v8 = qword_180075518;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)v8 + 24LL))(
                           v8,
                           didCOMSERVICES,
                           &TID_APPLICATION,
                           v28,
                           1,
                           1,
                           4,
                           &v14);
LABEL_10:
  if ( !SimpleTableDispenser )
  {
    if ( !v14 )
      return (unsigned int)-2147024882;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    if ( !SimpleTableDispenser )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
      if ( !SimpleTableDispenser )
      {
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
        SimpleTableDispenser = v9;
        if ( v9 != -2146367487 )
        {
          if ( !v9 )
            SimpleTableDispenser = -2146368501;
          goto LABEL_73;
        }
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 120LL))(v14);
        if ( !SimpleTableDispenser )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *))(*(_QWORD *)v14 + 160LL))(
                                   v14,
                                   0,
                                   0,
                                   &pclsid);
          if ( !SimpleTableDispenser )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v14 + 160LL))(
                                     v14,
                                     16,
                                     0,
                                     L"Local");
            if ( !SimpleTableDispenser )
            {
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPCOLESTR))(*(_QWORD *)v14 + 160LL))(
                                       v14,
                                       10,
                                       0,
                                       this[2]);
              if ( !SimpleTableDispenser )
              {
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPCOLESTR))(*(_QWORD *)v14 + 160LL))(
                                         v14,
                                         1,
                                         0,
                                         this[1]);
                if ( !SimpleTableDispenser )
                {
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPCOLESTR))(*(_QWORD *)v14 + 160LL))(
                                           v14,
                                           11,
                                           0,
                                           this[3]);
                  if ( !SimpleTableDispenser )
                  {
                    v18 = _wtoi(this[4]);
                    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                             v14,
                                             13,
                                             0,
                                             &v18);
                    if ( !SimpleTableDispenser )
                    {
                      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPCOLESTR))(*(_QWORD *)v14 + 160LL))(
                                               v14,
                                               14,
                                               0,
                                               this[5]);
                      if ( !SimpleTableDispenser )
                      {
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                 v14,
                                                 38,
                                                 0,
                                                 &v21);
                        if ( !SimpleTableDispenser )
                        {
                          SimpleTableDispenser = (*(__int64 (**)(__int64, __int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v14 + 160LL))(
                                                   v14,
                                                   39,
                                                   0,
                                                   L"%systemroot%\\system32\\com\\dmp");
                          if ( !SimpleTableDispenser )
                          {
                            if ( !_wcsicmp(this[6], L"Y") )
                              v19 = 1;
                            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                     v14,
                                                     22,
                                                     0,
                                                     &v19);
                            if ( !SimpleTableDispenser )
                            {
                              v20 = _wtoi(this[7]);
                              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                       v14,
                                                       12,
                                                       0,
                                                       &v20);
                              if ( !SimpleTableDispenser )
                              {
                                if ( a3 && *a3 )
                                {
                                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v14 + 160LL))(
                                                           v14,
                                                           8,
                                                           0,
                                                           a3);
                                  if ( SimpleTableDispenser )
                                    goto LABEL_73;
                                  if ( a4 )
                                  {
                                    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, BOOL *))(*(_QWORD *)v14 + 160LL))(
                                                             v14,
                                                             15,
                                                             0,
                                                             a4);
                                    if ( SimpleTableDispenser )
                                      goto LABEL_73;
                                  }
                                  v10 = _wcsicmp(a3, L"Interactive User");
                                  v11 = &v16;
                                  v12 = 7;
                                  v16 = v10 == 0;
                                }
                                else
                                {
                                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v14 + 160LL))(
                                                           v14,
                                                           8,
                                                           0,
                                                           L"Interactive User");
                                  if ( SimpleTableDispenser )
                                    goto LABEL_73;
                                  v16 = 1;
                                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, BOOL *))(*(_QWORD *)v14 + 160LL))(
                                                           v14,
                                                           7,
                                                           0,
                                                           &v16);
                                  if ( SimpleTableDispenser )
                                    goto LABEL_73;
                                  if ( !a4 || !*(_WORD *)a4 )
                                  {
LABEL_37:
                                    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v14 + 160LL))(
                                                             v14,
                                                             17,
                                                             0,
                                                             L"Y");
                                    if ( !SimpleTableDispenser )
                                    {
                                      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v14 + 160LL))(
                                                               v14,
                                                               18,
                                                               0,
                                                               L"Y");
                                      if ( !SimpleTableDispenser )
                                      {
                                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                 v14,
                                                                 26,
                                                                 0,
                                                                 &v15);
                                        if ( !SimpleTableDispenser )
                                        {
                                          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                   v14,
                                                                   29,
                                                                   0,
                                                                   &v15);
                                          if ( !SimpleTableDispenser )
                                          {
                                            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                     v14,
                                                                     27,
                                                                     0,
                                                                     &v15);
                                            if ( !SimpleTableDispenser )
                                            {
                                              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                       v14,
                                                                       28,
                                                                       0,
                                                                       &v15);
                                              if ( !SimpleTableDispenser )
                                              {
                                                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                         v14,
                                                                         30,
                                                                         0,
                                                                         &v15);
                                                if ( !SimpleTableDispenser )
                                                {
                                                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                           v14,
                                                                           33,
                                                                           0,
                                                                           &v15);
                                                  if ( !SimpleTableDispenser )
                                                  {
                                                    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                             v14,
                                                                             32,
                                                                             0,
                                                                             &v15);
                                                    if ( !SimpleTableDispenser )
                                                    {
                                                      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                               v14,
                                                                               31,
                                                                               0,
                                                                               &v15);
                                                      if ( !SimpleTableDispenser )
                                                      {
                                                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                 v14,
                                                                                 2,
                                                                                 0,
                                                                                 &v15);
                                                        if ( !SimpleTableDispenser )
                                                        {
                                                          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                   v14,
                                                                                   21,
                                                                                   0,
                                                                                   &v17);
                                                          if ( !SimpleTableDispenser )
                                                          {
                                                            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                     v14,
                                                                                     4,
                                                                                     0,
                                                                                     &v22);
                                                            if ( !SimpleTableDispenser )
                                                            {
                                                              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                       v14,
                                                                                       24,
                                                                                       0,
                                                                                       &v23);
                                                              if ( !SimpleTableDispenser )
                                                              {
                                                                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                         v14,
                                                                                         25,
                                                                                         0,
                                                                                         &v24);
                                                                if ( !SimpleTableDispenser )
                                                                {
                                                                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                           v14,
                                                                                           40,
                                                                                           0,
                                                                                           &v17);
                                                                  if ( !SimpleTableDispenser )
                                                                  {
                                                                    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 160LL))(
                                                                                             v14,
                                                                                             6,
                                                                                             0,
                                                                                             0);
                                                                    if ( !SimpleTableDispenser )
                                                                    {
                                                                      SimpleTableDispenser = (*(__int64 (**)(__int64, __int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v14 + 160LL))(
                                                                                               v14,
                                                                                               39,
                                                                                               0,
                                                                                               L"%systemroot%\\system32\\com\\dmp");
                                                                      if ( !SimpleTableDispenser )
                                                                      {
                                                                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)v14 + 160LL))(
                                                                                                 v14,
                                                                                                 41,
                                                                                                 0,
                                                                                                 &GUID_DefaultAppPartition);
                                                                        if ( !SimpleTableDispenser )
                                                                        {
                                                                          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                                   v14,
                                                                                                   49,
                                                                                                   0,
                                                                                                   &v17);
                                                                          if ( !SimpleTableDispenser )
                                                                          {
                                                                            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                                     v14,
                                                                                                     42,
                                                                                                     0,
                                                                                                     &v25);
                                                                            if ( !SimpleTableDispenser )
                                                                            {
                                                                              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(v14, 51, 0, &v26);
                                                                              if ( !SimpleTableDispenser )
                                                                              {
                                                                                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(v14, 52, 0, &v15);
                                                                                if ( !SimpleTableDispenser )
                                                                                {
                                                                                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(v14, 53, 0, &v15);
                                                                                  if ( !SimpleTableDispenser )
                                                                                  {
                                                                                    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 160LL))(v14, 54, 0, 0);
                                                                                    if ( !SimpleTableDispenser )
                                                                                    {
                                                                                      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 160LL))(v14, 55, 0, 0);
                                                                                      if ( !SimpleTableDispenser )
                                                                                      {
                                                                                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 160LL))(v14, 56, 0, 0);
                                                                                        if ( !SimpleTableDispenser )
                                                                                        {
                                                                                          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 144LL))(v14);
                                                                                          if ( !SimpleTableDispenser )
                                                                                            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 96LL))(v14);
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                }
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                    goto LABEL_73;
                                  }
                                  v11 = a4;
                                  v12 = 15;
                                }
                                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, BOOL *))(*(_QWORD *)v14 + 160LL))(
                                                         v14,
                                                         v12,
                                                         0,
                                                         v11);
                                if ( !SimpleTableDispenser )
                                  goto LABEL_37;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_73:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x180045c70  push    rbp
0x180045c72  push    rbx
0x180045c73  push    rsi
0x180045c74  push    rdi
0x180045c75  push    r13
0x180045c77  push    r14
0x180045c79  push    r15
0x180045c7b  lea     rbp, [rsp-27h]
0x180045c80  sub     rsp, 0C0h
0x180045c87  mov     rax, cs:__security_cookie
0x180045c8e  xor     rax, rsp
0x180045c91  mov     [rbp+57h+var_38], rax
0x180045c95  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180045c9c  xor     r15d, r15d
0x180045c9f  mov     [rbp+57h+var_7C], 2
0x180045ca6  mov     rsi, r9
0x180045ca9  mov     [rbp+57h+var_94], r15d
0x180045cad  mov     r14, r8
0x180045cb0  mov     [rbp+57h+var_8C], r15d
0x180045cb4  mov     rdi, rcx
0x180045cb7  mov     [rbp+57h+var_88], r15d
0x180045cbb  lea     r13d, [r15+1]
0x180045cbf  mov     [rbp+57h+var_84], r15d
0x180045cc3  mov     [rbp+57h+var_90], r13d
0x180045cc7  mov     [rbp+57h+var_70], r13d
0x180045ccb  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180045cd0  mov     [rbp+57h+var_98], r15d
0x180045cd4  mov     [rbp+57h+var_78], 3
0x180045cdb  mov     [rbp+57h+var_74], 40h ; '@'
0x180045ce2  mov     [rbp+57h+var_80], 5
0x180045ce9  mov     [rbp+57h+var_6C], 40000h
0x180045cf0  mov     [rbp+57h+var_A0], r15
0x180045cf4  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x180045cfa  mov     rcx, [rdi]; lpsz
0x180045cfd  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180045d01  call    cs:__imp_CLSIDFromString
0x180045d07  mov     ebx, eax
0x180045d09  test    eax, eax
0x180045d0b  jnz     loc_1800465A4
0x180045d11  mov     rcx, cs:qword_180075518
0x180045d18  lea     rax, [rbp+57h+pclsid]
0x180045d1c  mov     [rbp+57h+var_60], rax
0x180045d20  mov     [rbp+57h+var_58], r15
0x180045d24  mov     [rbp+57h+var_50], 48h ; 'H'
0x180045d2b  mov     [rbp+57h+var_4C], 10h
0x180045d32  mov     [rbp+57h+var_A0], r15
0x180045d36  test    rcx, rcx
0x180045d39  jnz     short loc_180045D8D
0x180045d3b  lea     rdx, [rbp+57h+var_68]
0x180045d3f  mov     [rbp+57h+var_68], r15
0x180045d43  lea     rcx, IID_ISimpleTableDispenser
0x180045d4a  call    cs:__imp_GetSimpleTableDispenser
0x180045d50  mov     ebx, eax
0x180045d52  test    eax, eax
0x180045d54  js      short loc_180045DC8
0x180045d56  mov     rcx, [rbp+57h+var_68]
0x180045d5a  test    rcx, rcx
0x180045d5d  jnz     short loc_180045D69
0x180045d5f  mov     ebx, 8007000Eh
0x180045d64  jmp     loc_1800465A4
0x180045d69  xor     eax, eax
0x180045d6b  lock cmpxchg cs:qword_180075518, rcx
0x180045d74  jz      short loc_180045D86
0x180045d76  mov     rcx, [rbp+57h+var_68]
0x180045d7a  mov     rax, [rcx]
0x180045d7d  mov     rax, [rax+10h]
0x180045d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d86  mov     rcx, cs:qword_180075518
0x180045d8d  mov     rax, [rcx]
0x180045d90  lea     rdx, [rbp+57h+var_A0]
0x180045d94  mov     [rsp+0F0h+var_B8], rdx
0x180045d99  lea     r9, [rbp+57h+var_60]
0x180045d9d  mov     [rsp+0F0h+var_C0], 4
0x180045da5  lea     r8, TID_APPLICATION
0x180045dac  mov     [rsp+0F0h+var_C8], r13d
0x180045db1  lea     rdx, didCOMSERVICES
0x180045db8  mov     rax, [rax+18h]
0x180045dbc  mov     [rsp+0F0h+var_D0], r13
0x180045dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045dc6  mov     ebx, eax
0x180045dc8  test    ebx, ebx
0x180045dca  jnz     loc_1800465A4
0x180045dd0  mov     rcx, [rbp+57h+var_A0]
0x180045dd4  test    rcx, rcx
0x180045dd7  jnz     short loc_180045DE3
0x180045dd9  mov     ebx, 8007000Eh
0x180045dde  jmp     loc_1800465B9
0x180045de3  mov     rax, [rcx]
0x180045de6  mov     rax, [rax+18h]
0x180045dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045def  mov     ebx, eax
0x180045df1  test    eax, eax
0x180045df3  jnz     loc_1800465A4
0x180045df9  mov     rcx, [rbp+57h+var_A0]
0x180045dfd  mov     rax, [rcx]
0x180045e00  mov     rax, [rax+20h]
0x180045e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e09  mov     ebx, eax
0x180045e0b  test    eax, eax
0x180045e0d  jnz     loc_1800465A4
0x180045e13  mov     rcx, [rbp+57h+var_A0]
0x180045e17  mov     rax, [rcx]
0x180045e1a  mov     rax, [rax+28h]
0x180045e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e23  mov     ebx, eax
0x180045e25  cmp     eax, 80110801h
0x180045e2a  jnz     loc_18004659B
0x180045e30  mov     rcx, [rbp+57h+var_A0]
0x180045e34  mov     rax, [rcx]
0x180045e37  mov     rax, [rax+78h]
0x180045e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e40  mov     ebx, eax
0x180045e42  test    eax, eax
0x180045e44  jnz     loc_1800465A4
0x180045e4a  mov     rcx, [rbp+57h+var_A0]
0x180045e4e  lea     r9, [rbp+57h+pclsid]
0x180045e52  xor     r8d, r8d
0x180045e55  xor     edx, edx
0x180045e57  mov     rax, [rcx]
0x180045e5a  mov     rax, [rax+0A0h]
0x180045e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e66  mov     ebx, eax
0x180045e68  test    eax, eax
0x180045e6a  jnz     loc_1800465A4
0x180045e70  mov     rcx, [rbp+57h+var_A0]
0x180045e74  lea     r9, aLocal; "Local"
0x180045e7b  xor     r8d, r8d
0x180045e7e  lea     edx, [rbx+10h]
0x180045e81  mov     rax, [rcx]
0x180045e84  mov     rax, [rax+0A0h]
0x180045e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e90  mov     ebx, eax
0x180045e92  test    eax, eax
0x180045e94  jnz     loc_1800465A4
0x180045e9a  mov     rcx, [rbp+57h+var_A0]
0x180045e9e  lea     edx, [rbx+0Ah]
0x180045ea1  mov     r9, [rdi+10h]
0x180045ea5  xor     r8d, r8d
0x180045ea8  mov     rax, [rcx]
0x180045eab  mov     rax, [rax+0A0h]
0x180045eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045eb7  mov     ebx, eax
0x180045eb9  test    eax, eax
0x180045ebb  jnz     loc_1800465A4
0x180045ec1  mov     rcx, [rbp+57h+var_A0]
0x180045ec5  xor     r8d, r8d
0x180045ec8  mov     r9, [rdi+8]
0x180045ecc  mov     edx, r13d
0x180045ecf  mov     rax, [rcx]
0x180045ed2  mov     rax, [rax+0A0h]
0x180045ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ede  mov     ebx, eax
0x180045ee0  test    eax, eax
0x180045ee2  jnz     loc_1800465A4
0x180045ee8  mov     rcx, [rbp+57h+var_A0]
0x180045eec  lea     edx, [rbx+0Bh]
0x180045eef  mov     r9, [rdi+18h]
0x180045ef3  xor     r8d, r8d
0x180045ef6  mov     rax, [rcx]
0x180045ef9  mov     rax, [rax+0A0h]
0x180045f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f05  mov     ebx, eax
0x180045f07  test    eax, eax
0x180045f09  jnz     loc_1800465A4
0x180045f0f  mov     rcx, [rdi+20h]; String
0x180045f13  call    cs:__imp__wtoi
0x180045f19  mov     rcx, [rbp+57h+var_A0]
0x180045f1d  lea     r9, [rbp+57h+var_8C]
0x180045f21  mov     [rbp+57h+var_8C], eax
0x180045f24  lea     edx, [rbx+0Dh]
0x180045f27  xor     r8d, r8d
0x180045f2a  mov     rax, [rcx]
0x180045f2d  mov     rax, [rax+0A0h]
0x180045f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f39  mov     ebx, eax
0x180045f3b  test    eax, eax
0x180045f3d  jnz     loc_1800465A4
0x180045f43  mov     rcx, [rbp+57h+var_A0]
0x180045f47  lea     edx, [rbx+0Eh]
0x180045f4a  mov     r9, [rdi+28h]
0x180045f4e  xor     r8d, r8d
0x180045f51  mov     rax, [rcx]
0x180045f54  mov     rax, [rax+0A0h]
0x180045f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f60  mov     ebx, eax
0x180045f62  test    eax, eax
0x180045f64  jnz     loc_1800465A4
0x180045f6a  mov     rcx, [rbp+57h+var_A0]
0x180045f6e  lea     r9, [rbp+57h+var_80]
0x180045f72  xor     r8d, r8d
0x180045f75  lea     edx, [rbx+26h]
0x180045f78  mov     rax, [rcx]
0x180045f7b  mov     rax, [rax+0A0h]
0x180045f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f87  mov     ebx, eax
0x180045f89  test    eax, eax
0x180045f8b  jnz     loc_1800465A4
0x180045f91  mov     rcx, [rbp+57h+var_A0]
0x180045f95  lea     r9, aSystemrootSyst; "%systemroot%\\system32\\com\\dmp"
0x180045f9c  xor     r8d, r8d
0x180045f9f  lea     edx, [rbx+27h]
0x180045fa2  mov     rax, [rcx]
0x180045fa5  mov     rax, [rax+0A0h]
0x180045fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fb1  mov     ebx, eax
0x180045fb3  test    eax, eax
0x180045fb5  jnz     loc_1800465A4
0x180045fbb  mov     rcx, [rdi+30h]; String1
0x180045fbf  lea     rdx, aY; "Y"
0x180045fc6  call    cs:__imp__wcsicmp
0x180045fcc  test    eax, eax
0x180045fce  jnz     short loc_180045FD4
0x180045fd0  mov     [rbp+57h+var_88], r13d
0x180045fd4  mov     rcx, [rbp+57h+var_A0]
0x180045fd8  lea     r9, [rbp+57h+var_88]
0x180045fdc  xor     r8d, r8d
0x180045fdf  mov     rax, [rcx]
0x180045fe2  lea     edx, [r8+16h]
0x180045fe6  mov     rax, [rax+0A0h]
0x180045fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ff2  mov     ebx, eax
0x180045ff4  test    eax, eax
0x180045ff6  jnz     loc_1800465A4
0x180045ffc  mov     rcx, [rdi+38h]; String
0x180046000  call    cs:__imp__wtoi
0x180046006  mov     rcx, [rbp+57h+var_A0]
0x18004600a  lea     r9, [rbp+57h+var_84]
0x18004600e  mov     [rbp+57h+var_84], eax
0x180046011  lea     edx, [rbx+0Ch]
0x180046014  xor     r8d, r8d
0x180046017  mov     rax, [rcx]
0x18004601a  mov     rax, [rax+0A0h]
0x180046021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046026  mov     ebx, eax
0x180046028  test    eax, eax
0x18004602a  jnz     loc_1800465A4
0x180046030  test    r14, r14
0x180046033  jz      loc_18004652F
0x180046039  cmp     [r14], r15w
0x18004603d  jz      loc_18004652F
0x180046043  mov     rcx, [rbp+57h+var_A0]
0x180046047  lea     edx, [rbx+8]
0x18004604a  mov     r9, r14
0x18004604d  xor     r8d, r8d
0x180046050  mov     rax, [rcx]
0x180046053  mov     rax, [rax+0A0h]
0x18004605a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004605f  mov     ebx, eax
0x180046061  test    eax, eax
0x180046063  jnz     loc_1800465A4
0x180046069  test    rsi, rsi
0x18004606c  jz      short loc_180046094
0x18004606e  mov     rcx, [rbp+57h+var_A0]
0x180046072  lea     edx, [rbx+0Fh]
0x180046075  mov     r9, rsi
0x180046078  xor     r8d, r8d
0x18004607b  mov     rax, [rcx]
0x18004607e  mov     rax, [rax+0A0h]
0x180046085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004608a  mov     ebx, eax
0x18004608c  test    eax, eax
0x18004608e  jnz     loc_1800465A4
0x180046094  lea     rdx, aInteractiveUse; "Interactive User"
0x18004609b  mov     rcx, r14; String1
0x18004609e  call    cs:__imp__wcsicmp
0x1800460a4  mov     ecx, r15d
0x1800460a7  lea     r9, [rbp+57h+var_94]
0x1800460ab  test    eax, eax
0x1800460ad  mov     edx, 7
0x1800460b2  setz    cl
0x1800460b5  mov     [rbp+57h+var_94], ecx
0x1800460b8  mov     rcx, [rbp+57h+var_A0]
0x1800460bc  xor     r8d, r8d
0x1800460bf  mov     rax, [rcx]
0x1800460c2  mov     rax, [rax+0A0h]
0x1800460c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460ce  mov     ebx, eax
0x1800460d0  test    eax, eax
0x1800460d2  jnz     loc_1800465A4
0x1800460d8  mov     rcx, [rbp+57h+var_A0]
0x1800460dc  lea     r9, aY; "Y"
0x1800460e3  xor     r8d, r8d
0x1800460e6  mov     rax, [rcx]
0x1800460e9  lea     edx, [r8+11h]
0x1800460ed  mov     rax, [rax+0A0h]
0x1800460f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460f9  mov     ebx, eax
0x1800460fb  test    eax, eax
0x1800460fd  jnz     loc_1800465A4
0x180046103  mov     rcx, [rbp+57h+var_A0]
0x180046107  lea     r9, aY; "Y"
0x18004610e  xor     r8d, r8d
0x180046111  lea     edx, [rbx+12h]
0x180046114  mov     rax, [rcx]
0x180046117  mov     rax, [rax+0A0h]
0x18004611e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046123  mov     ebx, eax
0x180046125  test    eax, eax
0x180046127  jnz     loc_1800465A4
0x18004612d  mov     rcx, [rbp+57h+var_A0]
  ... truncated ...
```
