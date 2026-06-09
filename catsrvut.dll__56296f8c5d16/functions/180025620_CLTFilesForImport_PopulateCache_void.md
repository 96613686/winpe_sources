# CLTFilesForImport::PopulateCache(void)

- ea: `0x180025620`
- end: `0x180025bf3`
- name: `?PopulateCache@CLTFilesForImport@@UEAAJXZ`
- size: `1491`
- prototype: `__int64 __fastcall(CLTFilesForImport *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180025620`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025bcb`
- `catsrv!GetAppImport` at `0x180025695`
- `catsrv!GetAppImport` at `0x180025695`

## pseudocode

```c
__int64 __fastcall CLTFilesForImport::PopulateCache(CLTFilesForImport *this)
{
  char *v1; // r15
  __int64 v3; // rax
  __int64 (__fastcall *v4)(char *, _QWORD); // rax
  int AppImport; // ebx
  unsigned int i; // r12d
  unsigned int j; // r14d
  LPVOID *v8; // rcx
  unsigned int k; // esi
  unsigned int m; // r14d
  __int64 v12; // [rsp+38h] [rbp-31h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v14; // [rsp+50h] [rbp-19h] BYREF
  LPVOID v15[2]; // [rsp+60h] [rbp-9h]

  v1 = (char *)this + 8;
  v3 = *((_QWORD *)this + 1);
  v12 = 0;
  *(_OWORD *)pv = 0;
  v4 = *(__int64 (__fastcall **)(char *, _QWORD))(v3 + 32);
  v14 = 0;
  *(_OWORD *)v15 = 0;
  AppImport = v4((char *)this + 8, 0);
  if ( AppImport >= 0 )
  {
    AppImport = GetAppImport(&IID_IAppImport2, &v12);
    if ( AppImport >= 0 )
    {
      AppImport = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v12 + 32LL))(
                    v12,
                    *((_QWORD *)this + 5),
                    pv);
      if ( AppImport >= 0 )
      {
        for ( i = 0; i < LODWORD(v15[0]); ++i )
        {
          if ( !*((_DWORD *)v15[1] + 10 * i + 7) )
          {
            AppImport = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          0,
                          0,
                          *((_QWORD *)this + 5));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, const OLECHAR *))(**((_QWORD **)this + 4)
                                                                                            + 160LL))(
                          *((_QWORD *)this + 4),
                          1,
                          0,
                          &Password);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          2,
                          0,
                          *((_QWORD *)v15[1] + 5 * i));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          3,
                          0,
                          *((_QWORD *)v15[1] + 5 * i + 1));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          4);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          5);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          6);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          7,
                          0,
                          pv[0]);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          8,
                          0,
                          pv[1]);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int128 *))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          9,
                          0,
                          &v14);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
            if ( AppImport < 0 )
              goto LABEL_36;
          }
          for ( j = 0; j < *((_DWORD *)v15[1] + 10 * i + 7); ++j )
          {
            AppImport = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          0,
                          0,
                          *((_QWORD *)this + 5));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          1,
                          0,
                          *(_QWORD *)(*((_QWORD *)v15[1] + 5 * i + 4) + 8LL * j));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          2,
                          0,
                          *((_QWORD *)v15[1] + 5 * i));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          3,
                          0,
                          *((_QWORD *)v15[1] + 5 * i + 1));
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          4);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          5);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          6);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          7,
                          0,
                          pv[0]);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          8,
                          0,
                          pv[1]);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int128 *))(**((_QWORD **)this + 4) + 160LL))(
                          *((_QWORD *)this + 4),
                          9,
                          0,
                          &v14);
            if ( AppImport < 0 )
              goto LABEL_36;
            AppImport = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
            if ( AppImport < 0 )
              goto LABEL_36;
          }
        }
        AppImport = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 40LL))(v1);
      }
    }
  }
LABEL_36:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  CoTaskMemFree(pv[0]);
  CoTaskMemFree(pv[1]);
  v8 = (LPVOID *)v15[1];
  if ( v15[1] )
  {
    for ( k = 0; k < LODWORD(v15[0]); ++k )
    {
      CoTaskMemFree(v8[5 * k]);
      CoTaskMemFree(*((LPVOID *)v15[1] + 5 * k + 1));
      v8 = (LPVOID *)v15[1];
      if ( *((_QWORD *)v15[1] + 5 * k + 4) )
      {
        for ( m = 0; m < *((_DWORD *)v15[1] + 10 * k + 7); ++m )
        {
          CoTaskMemFree(*((LPVOID *)v8[5 * k + 4] + m));
          v8 = (LPVOID *)v15[1];
        }
        CoTaskMemFree(v8[5 * k + 4]);
        v8 = (LPVOID *)v15[1];
      }
    }
    CoTaskMemFree(v8);
  }
  return (unsigned int)AppImport;
}

```

## disassembly

```asm
0x180025620  push    rbp
0x180025622  push    rbx
0x180025623  push    rsi
0x180025624  push    rdi
0x180025625  push    r12
0x180025627  push    r13
0x180025629  push    r14
0x18002562b  push    r15
0x18002562d  lea     rbp, [rsp-1Fh]
0x180025632  sub     rsp, 88h
0x180025639  mov     rax, cs:__security_cookie
0x180025640  xor     rax, rsp
0x180025643  mov     [rbp+57h+var_50], rax
0x180025647  xorps   xmm0, xmm0
0x18002564a  mov     [rbp+57h+var_8C], 1
0x180025651  lea     r15, [rcx+8]
0x180025655  mov     rdi, rcx
0x180025658  mov     rax, [r15]
0x18002565b  xor     r13d, r13d
0x18002565e  xor     edx, edx
0x180025660  mov     [rbp+57h+var_88], r13
0x180025664  mov     rcx, r15
0x180025667  mov     [rbp+57h+var_90], r13d
0x18002566b  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18002566f  mov     rax, [rax+20h]
0x180025673  movups  [rbp+57h+var_70], xmm0
0x180025677  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002567b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025680  mov     ebx, eax
0x180025682  test    eax, eax
0x180025684  js      loc_180025B22
0x18002568a  lea     rdx, [rbp+57h+var_88]
0x18002568e  lea     rcx, IID_IAppImport2
0x180025695  call    cs:__imp_GetAppImport
0x18002569b  mov     ebx, eax
0x18002569d  test    eax, eax
0x18002569f  js      loc_180025B22
0x1800256a5  mov     rcx, [rbp+57h+var_88]
0x1800256a9  lea     r8, [rbp+57h+pv]
0x1800256ad  mov     rdx, [rdi+28h]
0x1800256b1  mov     rax, [rcx]
0x1800256b4  mov     rax, [rax+20h]
0x1800256b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256bd  mov     ebx, eax
0x1800256bf  test    eax, eax
0x1800256c1  js      loc_180025B22
0x1800256c7  mov     r12d, r13d
0x1800256ca  cmp     r12d, dword ptr [rbp+57h+var_60]
0x1800256ce  jnb     loc_180025B11
0x1800256d4  mov     eax, r12d
0x1800256d7  lea     rsi, [rax+rax*4]
0x1800256db  mov     rax, [rbp+57h+var_60+8]
0x1800256df  cmp     [rax+rsi*8+1Ch], r13d
0x1800256e4  jnz     loc_1800258EE
0x1800256ea  mov     rcx, [rdi+20h]
0x1800256ee  mov     rax, [rcx]
0x1800256f1  mov     rax, [rax+78h]
0x1800256f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256fa  mov     ebx, eax
0x1800256fc  test    eax, eax
0x1800256fe  js      loc_180025B22
0x180025704  mov     rcx, [rdi+20h]
0x180025708  xor     r8d, r8d
0x18002570b  mov     r9, [rdi+28h]
0x18002570f  xor     edx, edx
0x180025711  mov     rax, [rcx]
0x180025714  mov     rax, [rax+0A0h]
0x18002571b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025720  mov     ebx, eax
0x180025722  test    eax, eax
0x180025724  js      loc_180025B22
0x18002572a  mov     rcx, [rdi+20h]
0x18002572e  lea     r9, Password
0x180025735  xor     r8d, r8d
0x180025738  mov     rax, [rcx]
0x18002573b  lea     edx, [r8+1]
0x18002573f  mov     rax, [rax+0A0h]
0x180025746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002574b  mov     ebx, eax
0x18002574d  test    eax, eax
0x18002574f  js      loc_180025B22
0x180025755  mov     rcx, [rdi+20h]
0x180025759  xor     r8d, r8d
0x18002575c  mov     r9, [rbp+57h+var_60+8]
0x180025760  mov     rax, [rcx]
0x180025763  lea     edx, [r8+2]
0x180025767  mov     r9, [r9+rsi*8]
0x18002576b  mov     rax, [rax+0A0h]
0x180025772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025777  mov     ebx, eax
0x180025779  test    eax, eax
0x18002577b  js      loc_180025B22
0x180025781  mov     rcx, [rdi+20h]
0x180025785  xor     r8d, r8d
0x180025788  mov     r9, [rbp+57h+var_60+8]
0x18002578c  mov     rax, [rcx]
0x18002578f  lea     edx, [r8+3]
0x180025793  mov     r9, [r9+rsi*8+8]
0x180025798  mov     rax, [rax+0A0h]
0x18002579f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257a4  mov     ebx, eax
0x1800257a6  test    eax, eax
0x1800257a8  js      loc_180025B22
0x1800257ae  mov     rax, [rbp+57h+var_60+8]
0x1800257b2  lea     r8, [rbp+57h+var_8C]
0x1800257b6  mov     rcx, [rdi+20h]
0x1800257ba  lea     r9, [rbp+57h+var_90]
0x1800257be  cmp     [rax+rsi*8+10h], r13d
0x1800257c3  mov     rdx, [rcx]
0x1800257c6  cmovnz  r9, r8
0x1800257ca  xor     r8d, r8d
0x1800257cd  mov     rax, [rdx+0A0h]
0x1800257d4  lea     edx, [r8+4]
0x1800257d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257dd  mov     ebx, eax
0x1800257df  test    eax, eax
0x1800257e1  js      loc_180025B22
0x1800257e7  mov     rax, [rbp+57h+var_60+8]
0x1800257eb  lea     r8, [rbp+57h+var_8C]
0x1800257ef  mov     rcx, [rdi+20h]
0x1800257f3  lea     r9, [rbp+57h+var_90]
0x1800257f7  cmp     [rax+rsi*8+14h], r13d
0x1800257fc  mov     rdx, [rcx]
0x1800257ff  cmovnz  r9, r8
0x180025803  xor     r8d, r8d
0x180025806  mov     rax, [rdx+0A0h]
0x18002580d  lea     edx, [r8+5]
0x180025811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025816  mov     ebx, eax
0x180025818  test    eax, eax
0x18002581a  js      loc_180025B22
0x180025820  mov     rax, [rbp+57h+var_60+8]
0x180025824  lea     r8, [rbp+57h+var_8C]
0x180025828  mov     rcx, [rdi+20h]
0x18002582c  lea     r9, [rbp+57h+var_90]
0x180025830  cmp     [rax+rsi*8+18h], r13d
0x180025835  mov     rdx, [rcx]
0x180025838  cmovnz  r9, r8
0x18002583c  xor     r8d, r8d
0x18002583f  mov     rax, [rdx+0A0h]
0x180025846  lea     edx, [r8+6]
0x18002584a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002584f  mov     ebx, eax
0x180025851  test    eax, eax
0x180025853  js      loc_180025B22
0x180025859  mov     rcx, [rdi+20h]
0x18002585d  xor     r8d, r8d
0x180025860  mov     r9, [rbp+57h+pv]
0x180025864  mov     rax, [rcx]
0x180025867  lea     edx, [r8+7]
0x18002586b  mov     rax, [rax+0A0h]
0x180025872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025877  mov     ebx, eax
0x180025879  test    eax, eax
0x18002587b  js      loc_180025B22
0x180025881  mov     rcx, [rdi+20h]
0x180025885  xor     r8d, r8d
0x180025888  mov     r9, [rbp+57h+pv+8]
0x18002588c  mov     rax, [rcx]
0x18002588f  lea     edx, [r8+8]
0x180025893  mov     rax, [rax+0A0h]
0x18002589a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002589f  mov     ebx, eax
0x1800258a1  test    eax, eax
0x1800258a3  js      loc_180025B22
0x1800258a9  mov     rcx, [rdi+20h]
0x1800258ad  lea     r9, [rbp+57h+var_70]
0x1800258b1  xor     r8d, r8d
0x1800258b4  mov     rax, [rcx]
0x1800258b7  lea     edx, [r8+9]
0x1800258bb  mov     rax, [rax+0A0h]
0x1800258c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c7  mov     ebx, eax
0x1800258c9  test    eax, eax
0x1800258cb  js      loc_180025B22
0x1800258d1  mov     rcx, [rdi+20h]
0x1800258d5  mov     rax, [rcx]
0x1800258d8  mov     rax, [rax+90h]
0x1800258df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258e4  mov     ebx, eax
0x1800258e6  test    eax, eax
0x1800258e8  js      loc_180025B22
0x1800258ee  mov     r14d, r13d
0x1800258f1  mov     rax, [rbp+57h+var_60+8]
0x1800258f5  cmp     r14d, [rax+rsi*8+1Ch]
0x1800258fa  jnb     loc_180025B09
0x180025900  mov     rcx, [rdi+20h]
0x180025904  mov     rax, [rcx]
0x180025907  mov     rax, [rax+78h]
0x18002590b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025910  mov     ebx, eax
0x180025912  test    eax, eax
0x180025914  js      loc_180025B22
0x18002591a  mov     rcx, [rdi+20h]
0x18002591e  xor     r8d, r8d
0x180025921  mov     r9, [rdi+28h]
0x180025925  xor     edx, edx
0x180025927  mov     rax, [rcx]
0x18002592a  mov     rax, [rax+0A0h]
0x180025931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025936  mov     ebx, eax
0x180025938  test    eax, eax
0x18002593a  js      loc_180025B22
0x180025940  mov     rax, [rbp+57h+var_60+8]
0x180025944  mov     rcx, [rdi+20h]
0x180025948  mov     r8d, r14d
0x18002594b  mov     r9, [rax+rsi*8+20h]
0x180025950  mov     rdx, [rcx]
0x180025953  mov     r9, [r9+r8*8]
0x180025957  xor     r8d, r8d
0x18002595a  mov     rax, [rdx+0A0h]
0x180025961  lea     edx, [r8+1]
0x180025965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002596a  mov     ebx, eax
0x18002596c  test    eax, eax
0x18002596e  js      loc_180025B22
0x180025974  mov     rcx, [rdi+20h]
0x180025978  xor     r8d, r8d
0x18002597b  mov     r9, [rbp+57h+var_60+8]
0x18002597f  mov     rax, [rcx]
0x180025982  lea     edx, [r8+2]
0x180025986  mov     r9, [r9+rsi*8]
0x18002598a  mov     rax, [rax+0A0h]
0x180025991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025996  mov     ebx, eax
0x180025998  test    eax, eax
0x18002599a  js      loc_180025B22
0x1800259a0  mov     rcx, [rdi+20h]
0x1800259a4  xor     r8d, r8d
0x1800259a7  mov     r9, [rbp+57h+var_60+8]
0x1800259ab  mov     rax, [rcx]
0x1800259ae  lea     edx, [r8+3]
0x1800259b2  mov     r9, [r9+rsi*8+8]
0x1800259b7  mov     rax, [rax+0A0h]
0x1800259be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c3  mov     ebx, eax
0x1800259c5  test    eax, eax
0x1800259c7  js      loc_180025B22
0x1800259cd  mov     rax, [rbp+57h+var_60+8]
0x1800259d1  lea     r8, [rbp+57h+var_8C]
0x1800259d5  mov     rcx, [rdi+20h]
0x1800259d9  lea     r9, [rbp+57h+var_90]
0x1800259dd  cmp     [rax+rsi*8+10h], r13d
0x1800259e2  mov     rdx, [rcx]
0x1800259e5  cmovnz  r9, r8
0x1800259e9  xor     r8d, r8d
0x1800259ec  mov     rax, [rdx+0A0h]
0x1800259f3  lea     edx, [r8+4]
0x1800259f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259fc  mov     ebx, eax
0x1800259fe  test    eax, eax
0x180025a00  js      loc_180025B22
0x180025a06  mov     rax, [rbp+57h+var_60+8]
0x180025a0a  lea     r8, [rbp+57h+var_8C]
0x180025a0e  mov     rcx, [rdi+20h]
0x180025a12  lea     r9, [rbp+57h+var_90]
0x180025a16  cmp     [rax+rsi*8+14h], r13d
0x180025a1b  mov     rdx, [rcx]
0x180025a1e  cmovnz  r9, r8
0x180025a22  xor     r8d, r8d
0x180025a25  mov     rax, [rdx+0A0h]
0x180025a2c  lea     edx, [r8+5]
0x180025a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a35  mov     ebx, eax
0x180025a37  test    eax, eax
0x180025a39  js      loc_180025B22
0x180025a3f  mov     rax, [rbp+57h+var_60+8]
0x180025a43  lea     r8, [rbp+57h+var_8C]
0x180025a47  mov     rcx, [rdi+20h]
0x180025a4b  lea     r9, [rbp+57h+var_90]
0x180025a4f  cmp     [rax+rsi*8+18h], r13d
0x180025a54  mov     rdx, [rcx]
0x180025a57  cmovnz  r9, r8
0x180025a5b  xor     r8d, r8d
0x180025a5e  mov     rax, [rdx+0A0h]
0x180025a65  lea     edx, [r8+6]
0x180025a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a6e  mov     ebx, eax
0x180025a70  test    eax, eax
0x180025a72  js      loc_180025B22
0x180025a78  mov     rcx, [rdi+20h]
0x180025a7c  xor     r8d, r8d
0x180025a7f  mov     r9, [rbp+57h+pv]
0x180025a83  mov     rax, [rcx]
0x180025a86  lea     edx, [r8+7]
0x180025a8a  mov     rax, [rax+0A0h]
0x180025a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a96  mov     ebx, eax
0x180025a98  test    eax, eax
0x180025a9a  js      loc_180025B22
0x180025aa0  mov     rcx, [rdi+20h]
0x180025aa4  xor     r8d, r8d
0x180025aa7  mov     r9, [rbp+57h+pv+8]
0x180025aab  mov     rax, [rcx]
0x180025aae  lea     edx, [r8+8]
0x180025ab2  mov     rax, [rax+0A0h]
0x180025ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025abe  mov     ebx, eax
0x180025ac0  test    eax, eax
0x180025ac2  js      short loc_180025B22
  ... truncated ...
```
