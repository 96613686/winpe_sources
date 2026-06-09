# CSimpleTable4ui::Initialize(__MIDL___MIDL_itf_stable_0000_0000_0002 *,ulong)

- ea: `0x1800034b0`
- end: `0x180003d6b`
- name: `?Initialize@CSimpleTable4ui@@QEAAJPEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@K@Z`
- size: `2235`
- prototype: `__int64 __fastcall(CSimpleTable4ui *__hidden this, struct __MIDL___MIDL_itf_stable_0000_0000_0002 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008840`

## callees

- `0x1800034b0`
- `0x180003d80`
- `0x180039a90`
- `0x18005550e`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180003523`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180003523`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180003c29`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180003c29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000373a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000375d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000385d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800038a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800038c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000391c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800035fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000373a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000375d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000385d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800038a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800038c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000391c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bd7`

## string_xrefs

- `0x180003b68`: `COMReg.Dex_Col%x`

## pseudocode

```c
__int64 __fastcall CSimpleTable4ui::Initialize(
        CSimpleTable4ui *this,
        struct __MIDL___MIDL_itf_stable_0000_0000_0002 *a2,
        unsigned int a3)
{
  unsigned int v3; // r13d
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v4; // r14
  int SimpleTableDispenser; // ebx
  unsigned int *v7; // r12
  __int64 i; // rsi
  int v9; // eax
  _DWORD *v10; // rdi
  int v11; // ecx
  LPVOID v12; // rax
  unsigned __int64 v13; // rcx
  LPVOID v14; // rax
  bool v15; // zf
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rcx
  CSimpleDataTableCache *v19; // rcx
  bool v20; // cc
  struct __MIDL___MIDL_itf_stable_0000_0000_0002 *v21; // rsi
  __int64 j; // rdi
  unsigned int v23; // eax
  LPVOID v24; // rax
  unsigned __int64 v25; // rcx
  LPVOID v26; // rax
  unsigned __int64 v27; // rcx
  LPVOID v28; // rax
  unsigned __int64 v29; // rcx
  LPVOID v30; // rax
  void *v31; // rax
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // r13
  char *v35; // rsi
  int v36; // ecx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  unsigned int v46; // eax
  _DWORD *v47; // rax
  int v48; // r9d
  SIZE_T v49; // rcx
  void *v50; // rcx
  __int64 k; // rdi
  void *v52; // rcx
  __int64 v53; // [rsp+58h] [rbp-9h] BYREF
  __int128 v54; // [rsp+60h] [rbp-1h] BYREF
  __int64 v55; // [rsp+70h] [rbp+Fh]
  __int64 v56; // [rsp+C8h] [rbp+67h] BYREF
  struct __MIDL___MIDL_itf_stable_0000_0000_0002 *v57; // [rsp+D0h] [rbp+6Fh]
  unsigned int v58; // [rsp+D8h] [rbp+77h]
  _DWORD *v59; // [rsp+E0h] [rbp+7Fh] BYREF

  v58 = a3;
  v57 = a2;
  v3 = a3;
  v4 = 0;
  v53 = 0;
  v55 = 0;
  v59 = 0;
  *((_QWORD *)this + 39) = a2;
  v56 = 0;
  v54 = 0;
  *((_DWORD *)this + 80) = a3;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v53);
  if ( SimpleTableDispenser >= 0 )
  {
    *(_QWORD *)&v54 = (char *)this + 276;
    *((_QWORD *)&v54 + 1) = 0xF000000600000000uLL;
    v55 = 0x1000000048LL;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, char *, __int64 *, __int128 *, __int64, int, int, __int64 *))(*(_QWORD *)v53 + 24LL))(
                             v53,
                             (char *)this + 292,
                             tidMETA_EXTENDED,
                             &v54,
                             1,
                             1,
                             3,
                             &v56);
    if ( SimpleTableDispenser >= 0 )
    {
      v7 = (unsigned int *)((char *)this + 92);
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)v56 + 72LL))(
                               v56,
                               0,
                               0,
                               0,
                               0,
                               0,
                               0,
                               (char *)this + 92,
                               0);
      if ( SimpleTableDispenser >= 0 )
      {
        v4 = (struct __MIDL___MIDL_itf_stable_0000_0000_0001 *)CoTaskMemAlloc(saturated_mul(*v7, 0xCu));
        if ( !v4 )
          goto LABEL_89;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 32LL))(v56);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_43;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 40LL))(v56);
          SimpleTableDispenser = v9;
          if ( v9 == -2146367487 )
            break;
          if ( v9 < 0 )
            goto LABEL_43;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v56 + 64LL))(
                                   v56,
                                   1,
                                   0,
                                   0,
                                   &v59);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_43;
          v10 = (_DWORD *)((char *)v4 + 12 * i);
          *v10 = *v59;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v56 + 64LL))(
                                   v56,
                                   2,
                                   0,
                                   0,
                                   &v59);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_43;
          v10[1] = *v59;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v56 + 64LL))(
                                   v56,
                                   3,
                                   0,
                                   0,
                                   &v59);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_43;
          v11 = *v59;
          v10[2] = *v59;
          if ( (v11 & 1) != 0 )
            ++*((_DWORD *)this + 56);
        }
        if ( *v7 != (_DWORD)i )
        {
          SimpleTableDispenser = -2147418113;
          goto LABEL_43;
        }
        v12 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 56), 4u));
        v13 = *((unsigned int *)this + 56);
        *((_QWORD *)this + 29) = v12;
        v14 = CoTaskMemAlloc(saturated_mul(v13, 2u));
        v15 = *((_QWORD *)this + 29) == 0;
        *((_QWORD *)this + 30) = v14;
        if ( v15 || !v14 )
        {
LABEL_89:
          SimpleTableDispenser = -2147024882;
          goto LABEL_43;
        }
        v16 = 0;
        v17 = 0;
        if ( *v7 )
        {
          do
          {
            v18 = 3 * v17;
            v17 = (unsigned int)(v17 + 1);
            if ( (*((_BYTE *)v4 + 4 * v18 + 8) & 1) != 0 )
            {
              *(_DWORD *)(*((_QWORD *)this + 29) + 4 * v16) = v17;
              *(_WORD *)(*((_QWORD *)this + 30) + 2 * v16) = *((_WORD *)v4 + 2 * v18);
              v16 = (unsigned int)(v16 + 1);
              if ( (_DWORD)v16 == *((_DWORD *)this + 56) )
                break;
            }
          }
          while ( (unsigned int)v17 < *((_DWORD *)this + 23) );
        }
        v19 = (CSimpleDataTableCache *)*((_QWORD *)this + 3);
        if ( (*((_BYTE *)v19 + 40) & 1) != 0 )
        {
          SimpleTableDispenser = -2146367483;
        }
        else if ( *v7 )
        {
          SimpleTableDispenser = CSimpleDataTableCache::SetupMeta(v19, *((_DWORD *)this + 24), *v7, v4);
          if ( SimpleTableDispenser >= 0 )
          {
            v15 = *((_DWORD *)this + 56) == 1;
            v20 = *((_DWORD *)this + 56) <= 1u;
            *((_DWORD *)this + 62) = 0;
            if ( v15 )
            {
              *((_DWORD *)this + 64) = **((_DWORD **)this + 29);
            }
            else if ( !v20 )
            {
              *((_DWORD *)this + 64) = -1;
            }
            v21 = v57;
            for ( j = 0; (unsigned int)j < v3; j = (unsigned int)(j + 1) )
            {
              v46 = *((_DWORD *)v21 + 6 * j + 3);
              if ( v46 == -268435452 )
              {
                v47 = CoTaskMemAlloc(0x10u);
                *((_QWORD *)this + 13) = v47;
                if ( !v47 )
                  goto LABEL_89;
                v48 = **((_DWORD **)v21 + 3 * j);
                if ( v48 == -268435449 )
                {
                  *v47 = 0;
                  *(_DWORD *)(*((_QWORD *)this + 13) + 8LL) = *((_DWORD *)this + 64);
                }
                else
                {
                  SimpleTableDispenser = StringCchPrintfA((char *)this + 112, 0x40u, "COMReg.Dex_Col%x", v48);
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_43;
                  **((_DWORD **)this + 13) = 1;
                  *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) = (char *)this + 112;
                  v21 = v57;
                }
              }
              else if ( v46 < 0xF0000000 )
              {
                ++*((_DWORD *)this + 44);
              }
            }
            v23 = *((_DWORD *)this + 44);
            if ( !v23 )
              goto LABEL_37;
            v24 = CoTaskMemAlloc(saturated_mul(v23, 4u));
            v25 = *((unsigned int *)this + 44);
            *((_QWORD *)this + 23) = v24;
            v26 = CoTaskMemAlloc(saturated_mul(v25, 4u));
            v27 = *((unsigned int *)this + 44);
            *((_QWORD *)this + 26) = v26;
            v28 = CoTaskMemAlloc(saturated_mul(v27, 2u));
            v29 = *((unsigned int *)this + 44);
            *((_QWORD *)this + 27) = v28;
            v30 = CoTaskMemAlloc(saturated_mul(v29, 4u));
            v15 = *((_QWORD *)this + 23) == 0;
            *((_QWORD *)this + 24) = v30;
            if ( !v15 )
            {
              if ( *((_QWORD *)this + 26) )
              {
                if ( *((_QWORD *)this + 27) )
                {
                  if ( v30 )
                  {
                    v31 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 44), 8u));
                    *((_QWORD *)this + 25) = v31;
                    if ( v31 )
                    {
                      v32 = 0;
                      memset_0(v31, 0, 8LL * *((unsigned int *)this + 44));
                      v33 = 0;
                      while ( (unsigned int)v33 < v3 )
                      {
                        v34 = *((int *)v21 + 6 * v33 + 3);
                        v35 = (char *)v21 + 24 * v33;
                        if ( (unsigned int)v34 < 0xF0000000 )
                        {
                          *(_DWORD *)(*((_QWORD *)this + 23) + 4 * v32) = v34 + 1;
                          *(_DWORD *)(*((_QWORD *)this + 26) + 4 * v32) = *((_DWORD *)v35 + 5);
                          *(_WORD *)(*((_QWORD *)this + 27) + 2 * v32) = *((_WORD *)v35 + 8);
                          v36 = *((_DWORD *)v35 + 2);
                          if ( v36 )
                          {
                            if ( v36 != 1 )
                              goto LABEL_42;
                            *(_DWORD *)(*((_QWORD *)this + 24) + 4 * v32) = 7;
                          }
                          else
                          {
                            *(_DWORD *)(*((_QWORD *)this + 24) + 4 * v32) = 2;
                          }
                          v49 = *(unsigned int *)(*((_QWORD *)this + 26) + 4 * v32);
                          if ( (_DWORD)v49 && *(_QWORD *)v35 )
                          {
                            *(_QWORD *)(*((_QWORD *)this + 25) + 8 * v32) = CoTaskMemAlloc(v49);
                            v50 = *(void **)(*((_QWORD *)this + 25) + 8 * v32);
                            if ( !v50 )
                              goto LABEL_89;
                            memcpy_0(v50, *(const void **)v35, *(unsigned int *)(*((_QWORD *)this + 26) + 4 * v32));
                            if ( (*((_BYTE *)v4 + 12 * v34 + 8) & 0x20) != 0 )
                              CharLowerW(*(LPWSTR *)(*((_QWORD *)this + 25) + 8 * v32));
                          }
                          else
                          {
                            *(_WORD *)(*((_QWORD *)this + 27) + 2 * v32) = 1;
                          }
                          v32 = (unsigned int)(v32 + 1);
                        }
                        v3 = v58;
                        v33 = (unsigned int)(v33 + 1);
                        v21 = v57;
                      }
LABEL_37:
                      *((_DWORD *)this + 68) = 1;
                      SimpleTableDispenser = 0;
LABEL_38:
                      CoTaskMemFree(v4);
                      goto LABEL_61;
                    }
                  }
                }
              }
            }
            goto LABEL_89;
          }
        }
        else
        {
LABEL_42:
          SimpleTableDispenser = -2147024809;
        }
      }
    }
  }
LABEL_43:
  v15 = *((_QWORD *)this + 25) == 0;
  *((_DWORD *)this + 68) = 0;
  if ( !v15 )
  {
    for ( k = 0; (unsigned int)k < *((_DWORD *)this + 44); k = (unsigned int)(k + 1) )
    {
      v52 = *(void **)(8 * k + *((_QWORD *)this + 25));
      if ( v52 )
      {
        CoTaskMemFree(v52);
        *(_QWORD *)(8 * k + *((_QWORD *)this + 25)) = 0;
      }
    }
  }
  v37 = (void *)*((_QWORD *)this + 23);
  if ( v37 )
  {
    CoTaskMemFree(v37);
    *((_QWORD *)this + 23) = 0;
  }
  v38 = (void *)*((_QWORD *)this + 25);
  if ( v38 )
  {
    CoTaskMemFree(v38);
    *((_QWORD *)this + 25) = 0;
  }
  v39 = (void *)*((_QWORD *)this + 26);
  if ( v39 )
  {
    CoTaskMemFree(v39);
    *((_QWORD *)this + 26) = 0;
  }
  v40 = (void *)*((_QWORD *)this + 27);
  if ( v40 )
  {
    CoTaskMemFree(v40);
    *((_QWORD *)this + 27) = 0;
  }
  v41 = (void *)*((_QWORD *)this + 24);
  if ( v41 )
  {
    CoTaskMemFree(v41);
    *((_QWORD *)this + 24) = 0;
  }
  v42 = (void *)*((_QWORD *)this + 29);
  if ( v42 )
  {
    CoTaskMemFree(v42);
    *((_QWORD *)this + 29) = 0;
  }
  v43 = (void *)*((_QWORD *)this + 30);
  if ( v43 )
  {
    CoTaskMemFree(v43);
    *((_QWORD *)this + 30) = 0;
  }
  v44 = (void *)*((_QWORD *)this + 13);
  if ( v44 )
  {
    CoTaskMemFree(v44);
    *((_QWORD *)this + 13) = 0;
  }
  if ( v4 )
    goto LABEL_38;
LABEL_61:
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x1800034b0  mov     rax, rsp
0x1800034b3  mov     [rax+18h], r8d
0x1800034b7  mov     [rax+10h], rdx
0x1800034bb  push    rbp
0x1800034bc  push    rbx
0x1800034bd  lea     rbp, [rax-5Fh]
0x1800034c1  sub     rsp, 0A8h
0x1800034c8  mov     [rax-18h], rsi
0x1800034cc  xorps   xmm0, xmm0
0x1800034cf  mov     [rax-20h], rdi
0x1800034d3  mov     [rax-28h], r12
0x1800034d7  mov     [rax-30h], r13
0x1800034db  mov     r13d, r8d
0x1800034de  mov     [rax-38h], r14
0x1800034e2  xor     r14d, r14d
0x1800034e5  mov     [rax-40h], r15
0x1800034e9  mov     r15, rcx
0x1800034ec  xor     ecx, ecx
0x1800034ee  mov     [rbp+57h+var_60], 0
0x1800034f6  mov     [rbp+57h+var_48], rcx
0x1800034fa  mov     [rbp+57h+arg_18], rcx
0x1800034fe  lea     rcx, IID_ISimpleTableDispenser
0x180003505  mov     [r15+138h], rdx
0x18000350c  lea     rdx, [rbp+57h+var_60]
0x180003510  mov     [rbp+57h+arg_0], 0
0x180003518  movups  [rbp+57h+var_58], xmm0
0x18000351c  mov     [r15+140h], r8d
0x180003523  call    cs:__imp_GetSimpleTableDispenser
0x180003529  mov     ebx, eax
0x18000352b  test    eax, eax
0x18000352d  js      loc_1800039C8
0x180003533  mov     rcx, [rbp+57h+var_60]
0x180003537  lea     rax, [r15+114h]
0x18000353e  mov     qword ptr [rbp+57h+var_58], rax
0x180003542  lea     r8, [rbp+57h+arg_0]
0x180003546  mov     [rsp+0B0h+var_78], r8
0x18000354b  lea     rdx, [r15+124h]
0x180003552  mov     dword ptr [rbp+57h+var_58+8], r14d
0x180003556  lea     r9, [rbp+57h+var_58]
0x18000355a  mov     dword ptr [rbp+57h+var_58+0Ch], 0F0000006h
0x180003561  lea     r8, tidMETA_EXTENDED
0x180003568  mov     dword ptr [rbp+57h+var_48], 48h ; 'H'
0x18000356f  mov     edi, 1
0x180003574  mov     dword ptr [rbp+57h+var_48+4], 10h
0x18000357b  mov     rax, [rcx]
0x18000357e  mov     dword ptr [rsp+0B0h+var_80], 3
0x180003586  mov     dword ptr [rsp+0B0h+var_88], edi
0x18000358a  mov     [rsp+0B0h+var_90], rdi
0x18000358f  mov     rax, [rax+18h]
0x180003593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003598  mov     ebx, eax
0x18000359a  test    eax, eax
0x18000359c  js      loc_1800039C8
0x1800035a2  mov     rcx, [rbp+57h+arg_0]
0x1800035a6  lea     r12, [r15+5Ch]
0x1800035aa  mov     [rsp+40h], r14
0x1800035af  xor     r9d, r9d
0x1800035b2  mov     [rsp+0B0h+var_78], r12
0x1800035b7  xor     r8d, r8d
0x1800035ba  mov     [rsp+0B0h+var_80], r14
0x1800035bf  xor     edx, edx
0x1800035c1  mov     rax, [rcx]
0x1800035c4  mov     [rsp+0B0h+var_88], r14
0x1800035c9  mov     [rsp+0B0h+var_90], r14
0x1800035ce  mov     rax, [rax+48h]
0x1800035d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d7  mov     ebx, eax
0x1800035d9  test    eax, eax
0x1800035db  js      loc_1800039C8
0x1800035e1  mov     ecx, [r12]
0x1800035e5  mov     eax, 0Ch
0x1800035ea  mul     rcx
0x1800035ed  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800035f4  cmovb   rax, rcx
0x1800035f8  mov     rcx, rax; cb
0x1800035fb  call    cs:__imp_CoTaskMemAlloc
0x180003601  mov     r14, rax
0x180003604  test    rax, rax
0x180003607  jz      loc_180003C4F
0x18000360d  mov     rcx, [rbp+57h+arg_0]
0x180003611  mov     rax, [rcx]
0x180003614  mov     rax, [rax+20h]
0x180003618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000361d  mov     ebx, eax
0x18000361f  test    eax, eax
0x180003621  js      loc_1800039C8
0x180003627  xor     esi, esi
0x180003629  nop     dword ptr [rax+00000000h]
0x180003630  mov     rcx, [rbp+57h+arg_0]
0x180003634  mov     rax, [rcx]
0x180003637  mov     rax, [rax+28h]
0x18000363b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003640  mov     ebx, eax
0x180003642  cmp     eax, 80110801h
0x180003647  jz      loc_180003713
0x18000364d  test    eax, eax
0x18000364f  js      loc_1800039C8
0x180003655  mov     rcx, [rbp+57h+arg_0]
0x180003659  lea     rdx, [rbp+57h+arg_18]
0x18000365d  mov     [rsp+0B0h+var_90], rdx
0x180003662  xor     r9d, r9d
0x180003665  xor     r8d, r8d
0x180003668  mov     edx, edi
0x18000366a  mov     rax, [rcx]
0x18000366d  mov     rax, [rax+40h]
0x180003671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003676  mov     ebx, eax
0x180003678  test    eax, eax
0x18000367a  js      loc_1800039C8
0x180003680  mov     rax, [rbp+57h+arg_18]
0x180003684  lea     rcx, [rsi+rsi*2]
0x180003688  lea     rdi, [r14+rcx*4]
0x18000368c  xor     r9d, r9d
0x18000368f  lea     rdx, [rbp+57h+arg_18]
0x180003693  xor     r8d, r8d
0x180003696  mov     [rsp+0B0h+var_90], rdx
0x18000369b  mov     edx, 2
0x1800036a0  mov     ecx, [rax]
0x1800036a2  mov     [rdi], ecx
0x1800036a4  mov     rcx, [rbp+57h+arg_0]
0x1800036a8  mov     rax, [rcx]
0x1800036ab  mov     rax, [rax+40h]
0x1800036af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b4  mov     ebx, eax
0x1800036b6  test    eax, eax
0x1800036b8  js      loc_1800039C8
0x1800036be  mov     rax, [rbp+57h+arg_18]
0x1800036c2  lea     rdx, [rbp+57h+arg_18]
0x1800036c6  mov     [rsp+0B0h+var_90], rdx
0x1800036cb  xor     r9d, r9d
0x1800036ce  xor     r8d, r8d
0x1800036d1  mov     edx, 3
0x1800036d6  mov     ecx, [rax]
0x1800036d8  mov     [rdi+4], ecx
0x1800036db  mov     rcx, [rbp+57h+arg_0]
0x1800036df  mov     rax, [rcx]
0x1800036e2  mov     rax, [rax+40h]
0x1800036e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036eb  mov     ebx, eax
0x1800036ed  test    eax, eax
0x1800036ef  js      loc_1800039C8
0x1800036f5  mov     rax, [rbp+57h+arg_18]
0x1800036f9  mov     ecx, [rax]
0x1800036fb  mov     [rdi+8], ecx
0x1800036fe  test    cl, 1
0x180003701  jnz     loc_180003AE9
0x180003707  inc     esi
0x180003709  mov     edi, 1
0x18000370e  jmp     loc_180003630
0x180003713  cmp     [r12], esi
0x180003717  jnz     loc_180003AF5
0x18000371d  mov     ecx, [r15+0E0h]
0x180003724  mov     eax, 4
0x180003729  mul     rcx
0x18000372c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003733  cmovb   rax, rbx
0x180003737  mov     rcx, rax; cb
0x18000373a  call    cs:__imp_CoTaskMemAlloc
0x180003740  mov     ecx, [r15+0E0h]
0x180003747  mov     [r15+0E8h], rax
0x18000374e  mov     eax, 2
0x180003753  mul     rcx
0x180003756  cmovb   rax, rbx
0x18000375a  mov     rcx, rax; cb
0x18000375d  call    cs:__imp_CoTaskMemAlloc
0x180003763  cmp     qword ptr [r15+0E8h], 0
0x18000376b  mov     [r15+0F0h], rax
0x180003772  jz      loc_180003C4F
0x180003778  test    rax, rax
0x18000377b  jz      loc_180003C4F
0x180003781  xor     r9d, r9d
0x180003784  xor     r8d, r8d
0x180003787  cmp     [r12], r8d
0x18000378b  jbe     short loc_1800037CD
0x18000378d  lea     rcx, [r8+r8*2]
0x180003791  inc     r8d
0x180003794  test    byte ptr [r14+rcx*4+8], 1
0x18000379a  lea     r10, [r14+rcx*4]
0x18000379e  jz      short loc_1800037C7
0x1800037a0  mov     rax, [r15+0E8h]
0x1800037a7  mov     [rax+r9*4], r8d
0x1800037ab  mov     rcx, [r15+0F0h]
0x1800037b2  movzx   eax, word ptr [r10]
0x1800037b6  mov     [rcx+r9*2], ax
0x1800037bb  inc     r9d
0x1800037be  cmp     r9d, [r15+0E0h]
0x1800037c5  jz      short loc_1800037CD
0x1800037c7  cmp     r8d, [r15+5Ch]
0x1800037cb  jb      short loc_18000378D
0x1800037cd  mov     rcx, [r15+18h]; this
0x1800037d1  test    byte ptr [rcx+28h], 1
0x1800037d5  jnz     loc_180003AFF
0x1800037db  mov     r8d, [r12]; unsigned int
0x1800037df  test    r8d, r8d
0x1800037e2  jz      loc_1800039C3
0x1800037e8  mov     edx, [r15+60h]; unsigned int
0x1800037ec  mov     r9, r14; struct __MIDL___MIDL_itf_stable_0000_0000_0001 *
0x1800037ef  call    ?SetupMeta@CSimpleDataTableCache@@IEAAJKKPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@@Z; CSimpleDataTableCache::SetupMeta(ulong,ulong,__MIDL___MIDL_itf_stable_0000_0000_0001 *)
0x1800037f4  mov     ebx, eax
0x1800037f6  test    eax, eax
0x1800037f8  js      loc_1800039C8
0x1800037fe  cmp     dword ptr [r15+0E0h], 1
0x180003806  mov     dword ptr [r15+0F8h], 0
0x180003811  jnz     loc_180003B09
0x180003817  mov     rax, [r15+0E8h]
0x18000381e  mov     ecx, [rax]
0x180003820  mov     [r15+100h], ecx
0x180003827  mov     rsi, [rbp+57h+arg_8]
0x18000382b  xor     edi, edi
0x18000382d  cmp     edi, r13d
0x180003830  jb      loc_180003AC4
0x180003836  mov     eax, [r15+0B0h]
0x18000383d  test    eax, eax
0x18000383f  jz      loc_180003950
0x180003845  mov     ecx, eax
0x180003847  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000384e  mov     eax, 4
0x180003853  mul     rcx
0x180003856  cmovb   rax, rbx
0x18000385a  mov     rcx, rax; cb
0x18000385d  call    cs:__imp_CoTaskMemAlloc
0x180003863  mov     ecx, [r15+0B0h]
0x18000386a  mov     [r15+0B8h], rax
0x180003871  mov     eax, 4
0x180003876  mul     rcx
0x180003879  cmovb   rax, rbx
0x18000387d  mov     rcx, rax; cb
0x180003880  call    cs:__imp_CoTaskMemAlloc
0x180003886  mov     ecx, [r15+0B0h]
0x18000388d  mov     [r15+0D0h], rax
0x180003894  mov     eax, 2
0x180003899  mul     rcx
0x18000389c  cmovb   rax, rbx
0x1800038a0  mov     rcx, rax; cb
0x1800038a3  call    cs:__imp_CoTaskMemAlloc
0x1800038a9  mov     ecx, [r15+0B0h]
0x1800038b0  mov     [r15+0D8h], rax
0x1800038b7  mov     eax, 4
0x1800038bc  mul     rcx
0x1800038bf  cmovb   rax, rbx
0x1800038c3  mov     rcx, rax; cb
0x1800038c6  call    cs:__imp_CoTaskMemAlloc
0x1800038cc  cmp     qword ptr [r15+0B8h], 0
0x1800038d4  mov     [r15+0C0h], rax
0x1800038db  jz      loc_180003C4F
0x1800038e1  cmp     qword ptr [r15+0D0h], 0
0x1800038e9  jz      loc_180003C4F
0x1800038ef  cmp     qword ptr [r15+0D8h], 0
0x1800038f7  jz      loc_180003C4F
0x1800038fd  test    rax, rax
0x180003900  jz      loc_180003C4F
0x180003906  mov     ecx, [r15+0B0h]
0x18000390d  mov     eax, 8
0x180003912  mul     rcx
0x180003915  cmovb   rax, rbx
0x180003919  mov     rcx, rax; cb
0x18000391c  call    cs:__imp_CoTaskMemAlloc
0x180003922  mov     [r15+0C8h], rax
0x180003929  test    rax, rax
0x18000392c  jz      loc_180003C4F
0x180003932  mov     r8d, [r15+0B0h]
0x180003939  xor     edx, edx; Val
0x18000393b  shl     r8, 3; Size
0x18000393f  mov     rcx, rax; void *
0x180003942  xor     edi, edi
0x180003944  call    memset_0
0x180003949  xor     ebx, ebx
0x18000394b  cmp     ebx, r13d
0x18000394e  jb      short loc_18000396B
0x180003950  mov     dword ptr [r15+110h], 1
0x18000395b  xor     ebx, ebx
0x18000395d  mov     rcx, r14; pv
0x180003960  call    cs:__imp_CoTaskMemFree
0x180003966  jmp     loc_180003A67
0x18000396b  lea     rcx, [rbx+rbx*2]
0x18000396f  movsxd  r13, dword ptr [rsi+rcx*8+0Ch]
0x180003974  lea     rsi, [rsi+rcx*8]
0x180003978  cmp     r13d, 0F0000000h
0x18000397f  jnb     loc_180003C40
0x180003985  mov     rax, [r15+0B8h]
0x18000398c  lea     ecx, [r13+1]
0x180003990  mov     [rax+rdi*4], ecx
0x180003993  mov     rcx, [r15+0D0h]
0x18000399a  mov     eax, [rsi+14h]
0x18000399d  mov     [rcx+rdi*4], eax
0x1800039a0  mov     rcx, [r15+0D8h]
0x1800039a7  movzx   eax, word ptr [rsi+10h]
0x1800039ab  mov     [rcx+rdi*2], ax
0x1800039af  mov     ecx, [rsi+8]
0x1800039b2  test    ecx, ecx
0x1800039b4  jz      loc_180003BB5
0x1800039ba  cmp     ecx, 1
0x1800039bd  jz      loc_180003BA5
0x1800039c3  mov     ebx, 80070057h
0x1800039c8  cmp     qword ptr [r15+0C8h], 0
0x1800039d0  mov     dword ptr [r15+110h], 0
0x1800039db  jnz     loc_180003C59
0x1800039e1  mov     rcx, [r15+0B8h]; pv
0x1800039e8  test    rcx, rcx
0x1800039eb  jnz     loc_180003CA5
  ... truncated ...
```
