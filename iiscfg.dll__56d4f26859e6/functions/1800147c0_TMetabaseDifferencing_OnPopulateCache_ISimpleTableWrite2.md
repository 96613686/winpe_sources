# TMetabaseDifferencing::OnPopulateCache(ISimpleTableWrite2 *)

- ea: `0x1800147c0`
- end: `0x180014e70`
- name: `?OnPopulateCache@TMetabaseDifferencing@@UEAAJPEAUISimpleTableWrite2@@@Z`
- size: `1712`
- prototype: `int(TMetabaseDifferencing *__hidden this, struct ISimpleTableWrite2 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001f70`
- `0x180002b50`
- `0x180014230`
- `0x1800142dc`
- `0x180014364`
- `0x18001443c`
- `0x1800147c0`
- `0x18002e0a6`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014949`
- `msvcrt!_wcsicmp` at `0x1800149e8`
- `msvcrt!_wcsicmp` at `0x180014949`
- `msvcrt!_wcsicmp` at `0x1800149e8`

## pseudocode

```c
__int64 __fastcall TMetabaseDifferencing::OnPopulateCache(TMetabaseDifferencing *this, struct ISimpleTableWrite2 *a2)
{
  int inserted; // ebx
  __int64 v5; // rcx
  TMetabaseDifferencing *v6; // rcx
  TMetabaseDifferencing *v7; // rcx
  unsigned int v8; // edi
  unsigned int v9; // esi
  unsigned int v10; // r12d
  bool v11; // zf
  int v12; // eax
  TMetabaseDifferencing *v13; // rcx
  unsigned int v14; // r13d
  TMetabaseDifferencing *v15; // rcx
  int v16; // eax
  TMetabaseDifferencing *v17; // rcx
  unsigned int *v18; // rdx
  unsigned int *v19; // rcx
  __int64 v20; // rax
  bool v21; // zf
  unsigned int *v22; // r9
  struct ISimpleTableWrite2 *v23; // rdx
  unsigned int v24; // r8d
  wchar_t **v25; // rax
  TMetabaseDifferencing *v26; // rcx
  _DWORD *v27; // rax
  int v28; // r13d
  unsigned int *v29; // rax
  unsigned int v30; // esi
  TMetabaseDifferencing *v32; // rcx
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v35; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v37[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v38[3]; // [rsp+60h] [rbp-A0h] BYREF
  void *Buf1; // [rsp+78h] [rbp-88h]
  wchar_t *String1; // [rsp+80h] [rbp-80h]
  unsigned int *v41; // [rsp+88h] [rbp-78h]
  _DWORD *v42; // [rsp+90h] [rbp-70h]
  unsigned int *v43; // [rsp+98h] [rbp-68h]
  _DWORD *v44; // [rsp+A8h] [rbp-58h]
  wchar_t *v45[3]; // [rsp+B0h] [rbp-50h] BYREF
  void *Buf2; // [rsp+C8h] [rbp-38h]
  wchar_t *String2; // [rsp+D0h] [rbp-30h]
  _DWORD *v48; // [rsp+D8h] [rbp-28h]
  _DWORD *v49; // [rsp+E0h] [rbp-20h]
  _DWORD *v50; // [rsp+E8h] [rbp-18h]
  unsigned int *v51; // [rsp+F0h] [rbp-10h]
  _DWORD *v52; // [rsp+F8h] [rbp-8h]
  size_t Size[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v54; // [rsp+110h] [rbp+10h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  unsigned int v56[4]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v57; // [rsp+138h] [rbp+38h]
  __int64 v58; // [rsp+148h] [rbp+48h]

  ATL::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>(
    v37,
    a2);
  if ( v37[0] )
  {
    inserted = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37[0] + 72LL))(v37[0], 0);
    if ( inserted >= 0 )
    {
      v5 = *((_QWORD *)this + 2);
      v55 = 0;
      v58 = 0;
      v33 = 0;
      v34 = 0;
      *(_OWORD *)Size = 0;
      v54 = 0;
      *(_OWORD *)v56 = 0;
      v57 = 0;
      inserted = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v5 + 40LL))(
                   v5,
                   0,
                   0,
                   &v33,
                   0);
      if ( inserted >= 0 )
      {
        inserted = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(**((_QWORD **)this + 3)
                                                                                             + 40LL))(
                     *((_QWORD *)this + 3),
                     0,
                     0,
                     &v34,
                     0);
        if ( inserted >= 0 )
        {
          memset_0(v38, 0, 0x50u);
          if ( !v33
            || (inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                             v6,
                             *((struct ISimpleTableWrite2 **)this + 2),
                             0,
                             (unsigned int *const)Size,
                             (struct tMBPropertyDiffRow *)v38),
                inserted >= 0) )
          {
            memset_0(v45, 0, 0x50u);
            if ( !v34
              || (inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                               v7,
                               *((struct ISimpleTableWrite2 **)this + 3),
                               0,
                               v56,
                               (struct tMBPropertyDiffRow *)v45),
                  inserted >= 0) )
            {
              v8 = 0;
              v9 = 0;
              v10 = 0;
LABEL_11:
              while ( 1 )
              {
                v11 = v8 == v33;
                if ( v8 >= v33 )
                  break;
                if ( v9 >= v34 )
                {
                  v11 = v8 == v33;
                  break;
                }
                v12 = _wcsicmp(String1, String2);
                if ( v12 )
                {
                  if ( v12 >= 0 )
                  {
                    v27 = v50;
                    v7 = (TMetabaseDifferencing *)&TMetabaseDifferencing::m_kInsert;
                    v28 = *v50;
                    v51 = &TMetabaseDifferencing::m_kInsert;
                    while ( v28 == *v27 )
                    {
                      inserted = TMetabaseDifferencing::InsertRow(v7, (struct tMBPropertyDiffRow *)v45, v56, a2);
                      if ( inserted < 0 )
                        goto LABEL_91;
                      if ( ++v9 == v34 )
                        break;
                      inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                   v7,
                                   *((struct ISimpleTableWrite2 **)this + 3),
                                   v9,
                                   v56,
                                   (struct tMBPropertyDiffRow *)v45);
                      if ( inserted < 0 )
                        goto LABEL_91;
                      v27 = v50;
                    }
                  }
                  else
                  {
                    inserted = TMetabaseDifferencing::DeleteNodeRow(
                                 v13,
                                 (struct tMBPropertyDiffRow *)v38,
                                 (unsigned int *)Size,
                                 a2);
                    if ( inserted < 0 )
                      goto LABEL_91;
                    v10 = *v43;
                    while ( v10 == *v43 )
                    {
                      if ( ++v8 >= v33 )
                        break;
                      inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                   v7,
                                   *((struct ISimpleTableWrite2 **)this + 2),
                                   v8,
                                   (unsigned int *const)Size,
                                   (struct tMBPropertyDiffRow *)v38);
                      if ( inserted < 0 )
                        goto LABEL_91;
                    }
                  }
                }
                else
                {
                  v14 = *v43;
                  v35 = *v50;
                  do
                  {
                    while ( 1 )
                    {
                      while ( 1 )
                      {
                        while ( 1 )
                        {
                          v7 = (TMetabaseDifferencing *)v35;
                          if ( *v43 == v14 )
                            break;
                          if ( *v50 != v35 )
                            goto LABEL_11;
                          while ( *v50 == v35 )
                          {
                            inserted = TMetabaseDifferencing::InsertRow(
                                         (TMetabaseDifferencing *)v35,
                                         (struct tMBPropertyDiffRow *)v45,
                                         v56,
                                         a2);
                            if ( inserted < 0 )
                              goto LABEL_91;
                            if ( ++v9 == v34 )
                              break;
                            inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                         v15,
                                         *((struct ISimpleTableWrite2 **)this + 3),
                                         v9,
                                         v56,
                                         (struct tMBPropertyDiffRow *)v45);
                            if ( inserted < 0 )
                              goto LABEL_91;
                          }
                        }
                        if ( *v50 == v35 )
                          break;
                        while ( *v43 == v14 )
                        {
                          v43 = &v35;
                          inserted = TMetabaseDifferencing::DeleteRow(
                                       v7,
                                       (struct tMBPropertyDiffRow *)v38,
                                       (unsigned int *)Size,
                                       a2);
                          if ( inserted < 0 )
                            goto LABEL_91;
                          if ( ++v8 == v33 )
                            break;
                          v10 = *v43;
                          inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                       v26,
                                       *((struct ISimpleTableWrite2 **)this + 2),
                                       v8,
                                       (unsigned int *const)Size,
                                       (struct tMBPropertyDiffRow *)v38);
                          if ( inserted < 0 )
                            goto LABEL_91;
                        }
                      }
                      v16 = _wcsicmp(v38[0], v45[0]);
                      if ( !v16 )
                        break;
                      if ( v16 >= 0 )
                      {
                        inserted = TMetabaseDifferencing::InsertRow(v17, (struct tMBPropertyDiffRow *)v45, v56, a2);
                        if ( inserted < 0 )
                          goto LABEL_91;
                        if ( ++v9 == v34 )
                          goto LABEL_11;
                        v23 = (struct ISimpleTableWrite2 *)*((_QWORD *)this + 3);
                        v25 = v45;
                        v22 = v56;
                        v24 = v9;
                      }
                      else
                      {
                        v43 = v50;
                        inserted = TMetabaseDifferencing::DeleteRow(
                                     v17,
                                     (struct tMBPropertyDiffRow *)v38,
                                     (unsigned int *)Size,
                                     a2);
                        if ( inserted < 0 )
                          goto LABEL_91;
                        if ( ++v8 == v33 )
                          goto LABEL_11;
                        v22 = (unsigned int *)Size;
                        v23 = (struct ISimpleTableWrite2 *)*((_QWORD *)this + 2);
                        v24 = v8;
                        v10 = *v43;
                        v25 = v38;
                      }
                      inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                   v7,
                                   v23,
                                   v24,
                                   v22,
                                   (struct tMBPropertyDiffRow *)v25);
                      if ( inserted < 0 )
                        goto LABEL_91;
                    }
                    if ( *(_DWORD *)v38[1] != *(_DWORD *)v45[1]
                      || *(_DWORD *)v38[2] != *(_DWORD *)v45[2]
                      || *v44 != *v52
                      || *v41 != *v48
                      || *v42 != *v49
                      || HIDWORD(Size[1]) != v56[3] )
                    {
                      goto LABEL_98;
                    }
                    v18 = &TMetabaseDifferencing::m_kZero;
                    v19 = &TMetabaseDifferencing::m_kZero;
                    if ( Buf2 )
                      v18 = (unsigned int *)Buf2;
                    if ( Buf1 )
                      v19 = (unsigned int *)Buf1;
                    if ( memcmp_0(v19, v18, HIDWORD(Size[1])) )
                    {
LABEL_98:
                      v20 = *(_QWORD *)a2;
                      v36 = 0;
                      inserted = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, unsigned int *))(v20 + 72))(
                                   a2,
                                   &v36);
                      if ( inserted < 0 )
                        goto LABEL_91;
                      v51 = &TMetabaseDifferencing::m_kUpdate;
                      inserted = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, _QWORD, __int64))(*(_QWORD *)a2 + 88LL))(
                                   a2,
                                   v36,
                                   10);
                      if ( inserted < 0 )
                        goto LABEL_91;
                    }
                    if ( ++v8 < v33 )
                    {
                      v10 = *v43;
                      inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                   v7,
                                   *((struct ISimpleTableWrite2 **)this + 2),
                                   v8,
                                   (unsigned int *const)Size,
                                   (struct tMBPropertyDiffRow *)v38);
                      if ( inserted < 0 )
                        goto LABEL_91;
                    }
                    v21 = ++v9 == v34;
                    if ( v9 < v34 )
                    {
                      inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                   v7,
                                   *((struct ISimpleTableWrite2 **)this + 3),
                                   v9,
                                   v56,
                                   (struct tMBPropertyDiffRow *)v45);
                      if ( inserted < 0 )
                        goto LABEL_91;
                      v21 = v9 == v34;
                    }
                  }
                  while ( !v21 && v8 != v33 );
                }
              }
              if ( v11 )
              {
                if ( v9 == v34 )
                {
LABEL_90:
                  inserted = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37[0] + 80LL))(v37[0]);
                }
                else
                {
                  do
                  {
                    inserted = TMetabaseDifferencing::InsertRow(v7, (struct tMBPropertyDiffRow *)v45, v56, a2);
                    if ( inserted < 0 )
                      break;
                    if ( ++v9 >= v34 )
                      goto LABEL_90;
                    inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                 v32,
                                 *((struct ISimpleTableWrite2 **)this + 3),
                                 v9,
                                 v56,
                                 (struct tMBPropertyDiffRow *)v45);
                  }
                  while ( inserted >= 0 );
                }
              }
              else
              {
                if ( v10 != *v43 )
                  goto LABEL_82;
                while ( 1 )
                {
                  inserted = TMetabaseDifferencing::DeleteRow(
                               v7,
                               (struct tMBPropertyDiffRow *)v38,
                               (unsigned int *)Size,
                               a2);
                  if ( inserted < 0 )
                    break;
                  if ( ++v8 >= v33 )
                    goto LABEL_90;
                  if ( v10 != *v43 )
                    goto LABEL_82;
                  inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                               v7,
                               *((struct ISimpleTableWrite2 **)this + 2),
                               v8,
                               (unsigned int *const)Size,
                               (struct tMBPropertyDiffRow *)v38);
                  if ( inserted < 0 )
                    break;
                  if ( v10 != *v43 )
                  {
LABEL_82:
                    while ( v8 < v33 )
                    {
                      v41 = &TMetabaseDifferencing::m_kZero;
                      inserted = TMetabaseDifferencing::DeleteNodeRow(
                                   v7,
                                   (struct tMBPropertyDiffRow *)v38,
                                   (unsigned int *)Size,
                                   a2);
                      if ( inserted < 0 )
                        goto LABEL_91;
                      v29 = v43;
                      v30 = *v43;
                      while ( v30 == *v29 )
                      {
                        if ( ++v8 >= v33 )
                          break;
                        inserted = TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(
                                     v7,
                                     *((struct ISimpleTableWrite2 **)this + 2),
                                     v8,
                                     (unsigned int *const)Size,
                                     (struct tMBPropertyDiffRow *)v38);
                        if ( inserted < 0 )
                          goto LABEL_91;
                        v29 = v43;
                      }
                    }
                    goto LABEL_90;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    inserted = -2147418113;
  }
LABEL_91:
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(v37);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800147c0  mov     [rsp-8+arg_10], rbx
0x1800147c5  push    rbp
0x1800147c6  push    rsi
0x1800147c7  push    rdi
0x1800147c8  push    r12
0x1800147ca  push    r13
0x1800147cc  push    r14
0x1800147ce  push    r15
0x1800147d0  lea     rbp, [rsp-60h]
0x1800147d5  sub     rsp, 160h
0x1800147dc  mov     rax, cs:__security_cookie
0x1800147e3  xor     rax, rsp
0x1800147e6  mov     [rbp+90h+var_40], rax
0x1800147ea  mov     r15, rcx
0x1800147ed  mov     r14, rdx
0x1800147f0  lea     rcx, [rsp+190h+var_140]
0x1800147f5  call    ??0?$CComQIPtr@UISimpleTableController@@$1?IID_ISimpleTableController@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>(IUnknown *)
0x1800147fa  mov     rcx, [rsp+190h+var_140]
0x1800147ff  test    rcx, rcx
0x180014802  jnz     short loc_18001480E
0x180014804  mov     ebx, 8000FFFFh
0x180014809  jmp     loc_180014DFE
0x18001480e  mov     rax, [rcx]
0x180014811  xor     edx, edx
0x180014813  mov     rax, [rax+48h]
0x180014817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001481c  mov     ebx, eax
0x18001481e  test    eax, eax
0x180014820  js      loc_180014DFE
0x180014826  mov     rcx, [r15+10h]
0x18001482a  lea     r9, [rsp+190h+var_150]
0x18001482f  xor     eax, eax
0x180014831  mov     [rsp+190h+var_170], 0
0x18001483a  xorps   xmm0, xmm0
0x18001483d  mov     [rbp+90h+var_70], rax
0x180014841  xorps   xmm1, xmm1
0x180014844  mov     [rbp+90h+var_48], rax
0x180014848  mov     [rsp+190h+var_150], eax
0x18001484c  xor     r8d, r8d
0x18001484f  mov     [rsp+190h+var_14C], eax
0x180014853  xor     edx, edx
0x180014855  movups  xmmword ptr [rbp+90h+Size], xmm0
0x180014859  movups  [rbp+90h+var_80], xmm0
0x18001485d  movups  xmmword ptr [rbp+90h+var_68], xmm1
0x180014861  movups  [rbp+90h+var_58], xmm1
0x180014865  mov     rax, [rcx]
0x180014868  mov     rax, [rax+28h]
0x18001486c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014871  mov     ebx, eax
0x180014873  test    eax, eax
0x180014875  js      loc_180014DFE
0x18001487b  mov     rcx, [r15+18h]
0x18001487f  lea     r9, [rsp+190h+var_14C]
0x180014884  xor     r8d, r8d
0x180014887  mov     [rsp+190h+var_170], 0
0x180014890  xor     edx, edx
0x180014892  mov     rax, [rcx]
0x180014895  mov     rax, [rax+28h]
0x180014899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001489e  mov     ebx, eax
0x1800148a0  test    eax, eax
0x1800148a2  js      loc_180014DFE
0x1800148a8  mov     edi, 50h ; 'P'
0x1800148ad  lea     rcx, [rsp+190h+var_130]; void *
0x1800148b2  mov     r8d, edi; Size
0x1800148b5  xor     edx, edx; Val
0x1800148b7  call    memset_0
0x1800148bc  cmp     [rsp+190h+var_150], 0
0x1800148c1  jbe     short loc_1800148E7
0x1800148c3  mov     rdx, [r15+10h]; struct ISimpleTableWrite2 *
0x1800148c7  lea     rax, [rsp+190h+var_130]
0x1800148cc  lea     r9, [rbp+90h+Size]; unsigned int *
0x1800148d0  mov     [rsp+190h+var_170], rax; struct tMBPropertyDiffRow *
0x1800148d5  xor     r8d, r8d; unsigned int
0x1800148d8  call    ?GetColumnValues_AsMBPropertyDiff@TMetabaseDifferencing@@AEAAJPEAUISimpleTableWrite2@@KQEAKAEAUtMBPropertyDiffRow@@@Z; TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(ISimpleTableWrite2 *,ulong,ulong * const,tMBPropertyDiffRow &)
0x1800148dd  mov     ebx, eax
0x1800148df  test    eax, eax
0x1800148e1  js      loc_180014DFE
0x1800148e7  mov     r8, rdi; Size
0x1800148ea  lea     rcx, [rbp+90h+var_E0]; void *
0x1800148ee  xor     edx, edx; Val
0x1800148f0  call    memset_0
0x1800148f5  cmp     [rsp+190h+var_14C], 0
0x1800148fa  jbe     short loc_18001491F
0x1800148fc  mov     rdx, [r15+18h]; struct ISimpleTableWrite2 *
0x180014900  lea     rax, [rbp+90h+var_E0]
0x180014904  lea     r9, [rbp+90h+var_68]; unsigned int *
0x180014908  mov     [rsp+190h+var_170], rax; struct tMBPropertyDiffRow *
0x18001490d  xor     r8d, r8d; unsigned int
0x180014910  call    ?GetColumnValues_AsMBPropertyDiff@TMetabaseDifferencing@@AEAAJPEAUISimpleTableWrite2@@KQEAKAEAUtMBPropertyDiffRow@@@Z; TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(ISimpleTableWrite2 *,ulong,ulong * const,tMBPropertyDiffRow &)
0x180014915  mov     ebx, eax
0x180014917  test    eax, eax
0x180014919  js      loc_180014DFE
0x18001491f  xor     edi, edi
0x180014921  xor     esi, esi
0x180014923  xor     r12d, r12d
0x180014926  lea     rbx, ?m_kZero@TMetabaseDifferencing@@0KA; ulong TMetabaseDifferencing::m_kZero
0x18001492d  cmp     edi, [rsp+190h+var_150]
0x180014931  jnb     loc_180014D19
0x180014937  cmp     esi, [rsp+190h+var_14C]
0x18001493b  jnb     loc_180014D15
0x180014941  mov     rdx, [rbp+90h+String2]; String2
0x180014945  mov     rcx, [rbp+90h+String1]; String1
0x180014949  call    cs:__imp__wcsicmp
0x18001494f  test    eax, eax
0x180014951  jnz     loc_180014C49
0x180014957  mov     rax, [rbp+90h+var_F8]
0x18001495b  mov     r13d, [rax]
0x18001495e  mov     rax, [rbp+90h+var_A8]
0x180014962  mov     ecx, [rax]
0x180014964  mov     dword ptr [rsp+190h+var_148], ecx
0x180014968  mov     rax, [rbp+90h+var_F8]
0x18001496c  mov     ecx, dword ptr [rsp+190h+var_148]; this
0x180014970  cmp     [rax], r13d
0x180014973  mov     rax, [rbp+90h+var_A8]
0x180014977  jz      short loc_1800149D7
0x180014979  cmp     [rax], ecx
0x18001497b  jnz     short loc_18001492D
0x18001497d  mov     rax, [rbp+90h+var_A8]
0x180014981  mov     ecx, dword ptr [rsp+190h+var_148]; this
0x180014985  cmp     [rax], ecx
0x180014987  jnz     loc_180014BDC
0x18001498d  mov     r9, r14; struct ISimpleTableWrite2 *
0x180014990  lea     r8, [rbp+90h+var_68]; unsigned int *
0x180014994  lea     rdx, [rbp+90h+var_E0]; struct tMBPropertyDiffRow *
0x180014998  call    ?InsertRow@TMetabaseDifferencing@@AEAAJAEAUtMBPropertyDiffRow@@PEAKPEAUISimpleTableWrite2@@@Z; TMetabaseDifferencing::InsertRow(tMBPropertyDiffRow &,ulong *,ISimpleTableWrite2 *)
0x18001499d  mov     ebx, eax
0x18001499f  test    eax, eax
0x1800149a1  js      loc_180014DFE
0x1800149a7  inc     esi
0x1800149a9  cmp     esi, [rsp+190h+var_14C]
0x1800149ad  jz      loc_180014BDC
0x1800149b3  mov     rdx, [r15+18h]; struct ISimpleTableWrite2 *
0x1800149b7  lea     rax, [rbp+90h+var_E0]
0x1800149bb  lea     r9, [rbp+90h+var_68]; unsigned int *
0x1800149bf  mov     [rsp+190h+var_170], rax; struct tMBPropertyDiffRow *
0x1800149c4  mov     r8d, esi; unsigned int
0x1800149c7  call    ?GetColumnValues_AsMBPropertyDiff@TMetabaseDifferencing@@AEAAJPEAUISimpleTableWrite2@@KQEAKAEAUtMBPropertyDiffRow@@@Z; TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(ISimpleTableWrite2 *,ulong,ulong * const,tMBPropertyDiffRow &)
0x1800149cc  mov     ebx, eax
0x1800149ce  test    eax, eax
0x1800149d0  jns     short loc_18001497D
0x1800149d2  jmp     loc_180014DFE
0x1800149d7  cmp     [rax], ecx
0x1800149d9  jnz     loc_180014BE8
0x1800149df  mov     rdx, [rbp+90h+var_E0]; String2
0x1800149e3  mov     rcx, [rsp+190h+var_130]; String1
0x1800149e8  call    cs:__imp__wcsicmp
0x1800149ee  test    eax, eax
0x1800149f0  jnz     loc_180014B4C
0x1800149f6  mov     rax, [rbp+90h+var_D8]
0x1800149fa  mov     ecx, [rax]
0x1800149fc  mov     rax, [rsp+190h+var_128]
0x180014a01  cmp     [rax], ecx
0x180014a03  jnz     short loc_180014A6E
0x180014a05  mov     rax, [rbp+90h+var_D0]
0x180014a09  mov     ecx, [rax]
0x180014a0b  mov     rax, [rsp+190h+var_120]
0x180014a10  cmp     [rax], ecx
0x180014a12  jnz     short loc_180014A6E
0x180014a14  mov     rax, [rbp+90h+var_98]
0x180014a18  mov     ecx, [rax]
0x180014a1a  mov     rax, [rbp+90h+var_E8]
0x180014a1e  cmp     [rax], ecx
0x180014a20  jnz     short loc_180014A6E
0x180014a22  mov     rax, [rbp+90h+var_B8]
0x180014a26  mov     ecx, [rax]
0x180014a28  mov     rax, [rbp+90h+var_108]
0x180014a2c  cmp     [rax], ecx
0x180014a2e  jnz     short loc_180014A6E
0x180014a30  mov     rax, [rbp+90h+var_B0]
0x180014a34  mov     ecx, [rax]
0x180014a36  mov     rax, [rbp+90h+var_100]
0x180014a3a  cmp     [rax], ecx
0x180014a3c  jnz     short loc_180014A6E
0x180014a3e  mov     r8d, dword ptr [rbp+90h+Size+0Ch]; Size
0x180014a42  cmp     r8d, [rbp+90h+var_68+0Ch]
0x180014a46  jnz     short loc_180014A6E
0x180014a48  mov     rax, [rbp+90h+Buf2]
0x180014a4c  mov     rdx, rbx
0x180014a4f  test    rax, rax
0x180014a52  mov     rcx, rbx
0x180014a55  cmovnz  rdx, rax; Buf2
0x180014a59  mov     rax, [rsp+190h+Buf1]
0x180014a5e  test    rax, rax
0x180014a61  cmovnz  rcx, rax; Buf1
0x180014a65  call    memcmp_0
0x180014a6a  test    eax, eax
0x180014a6c  jz      short loc_180014AD5
0x180014a6e  mov     rax, [r14]
0x180014a71  lea     rdx, [rsp+190h+var_148+4]
0x180014a76  mov     rcx, r14
0x180014a79  mov     dword ptr [rsp+190h+var_148+4], 0
0x180014a81  mov     rax, [rax+48h]
0x180014a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a8a  mov     ebx, eax
0x180014a8c  test    eax, eax
0x180014a8e  js      loc_180014DFE
0x180014a94  mov     edx, dword ptr [rsp+190h+var_148+4]
0x180014a98  lea     rax, ?m_kUpdate@TMetabaseDifferencing@@0KA; ulong TMetabaseDifferencing::m_kUpdate
0x180014a9f  mov     [rbp+90h+var_A0], rax
0x180014aa3  lea     rcx, [rbp+90h+var_E0]
0x180014aa7  mov     rax, [r14]
0x180014aaa  xor     r9d, r9d
0x180014aad  mov     [rsp+190h+var_168], rcx
0x180014ab2  lea     rcx, [rbp+90h+var_68]
0x180014ab6  mov     [rsp+190h+var_170], rcx
0x180014abb  mov     rcx, r14
0x180014abe  mov     rax, [rax+58h]
0x180014ac2  lea     r8d, [r9+0Ah]
0x180014ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014acb  mov     ebx, eax
0x180014acd  test    eax, eax
0x180014acf  js      loc_180014DFE
0x180014ad5  inc     edi
0x180014ad7  cmp     edi, [rsp+190h+var_150]
0x180014adb  jnb     short loc_180014B08
0x180014add  mov     rax, [rbp+90h+var_F8]
0x180014ae1  lea     r9, [rbp+90h+Size]; unsigned int *
0x180014ae5  mov     rdx, [r15+10h]; struct ISimpleTableWrite2 *
0x180014ae9  mov     r8d, edi; unsigned int
0x180014aec  mov     r12d, [rax]
0x180014aef  lea     rax, [rsp+190h+var_130]
0x180014af4  mov     [rsp+190h+var_170], rax; struct tMBPropertyDiffRow *
0x180014af9  call    ?GetColumnValues_AsMBPropertyDiff@TMetabaseDifferencing@@AEAAJPEAUISimpleTableWrite2@@KQEAKAEAUtMBPropertyDiffRow@@@Z; TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(ISimpleTableWrite2 *,ulong,ulong * const,tMBPropertyDiffRow &)
0x180014afe  mov     ebx, eax
0x180014b00  test    eax, eax
0x180014b02  js      loc_180014DFE
0x180014b08  inc     esi
0x180014b0a  cmp     esi, [rsp+190h+var_14C]
0x180014b0e  jnb     short loc_180014B37
0x180014b10  mov     rdx, [r15+18h]; struct ISimpleTableWrite2 *
0x180014b14  lea     rax, [rbp+90h+var_E0]
0x180014b18  lea     r9, [rbp+90h+var_68]; unsigned int *
0x180014b1c  mov     [rsp+190h+var_170], rax; struct tMBPropertyDiffRow *
0x180014b21  mov     r8d, esi; unsigned int
0x180014b24  call    ?GetColumnValues_AsMBPropertyDiff@TMetabaseDifferencing@@AEAAJPEAUISimpleTableWrite2@@KQEAKAEAUtMBPropertyDiffRow@@@Z; TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(ISimpleTableWrite2 *,ulong,ulong * const,tMBPropertyDiffRow &)
0x180014b29  mov     ebx, eax
0x180014b2b  test    eax, eax
0x180014b2d  js      loc_180014DFE
0x180014b33  cmp     esi, [rsp+190h+var_14C]
0x180014b37  jz      loc_180014926
0x180014b3d  cmp     edi, [rsp+190h+var_150]
0x180014b41  jz      loc_180014926
0x180014b47  jmp     loc_180014BDC
0x180014b4c  mov     r9, r14; struct ISimpleTableWrite2 *
0x180014b4f  jns     short loc_180014B96
0x180014b51  mov     rax, [rbp+90h+var_A8]
0x180014b55  lea     r8, [rbp+90h+Size]; unsigned int *
0x180014b59  lea     rdx, [rsp+190h+var_130]; struct tMBPropertyDiffRow *
0x180014b5e  mov     [rbp+90h+var_F8], rax
0x180014b62  call    ?DeleteRow@TMetabaseDifferencing@@AEAAJAEAUtMBPropertyDiffRow@@PEAKPEAUISimpleTableWrite2@@@Z; TMetabaseDifferencing::DeleteRow(tMBPropertyDiffRow &,ulong *,ISimpleTableWrite2 *)
0x180014b67  mov     ebx, eax
0x180014b69  test    eax, eax
0x180014b6b  js      loc_180014DFE
0x180014b71  inc     edi
0x180014b73  cmp     edi, [rsp+190h+var_150]
0x180014b77  jz      loc_180014926
0x180014b7d  mov     rax, [rbp+90h+var_F8]
0x180014b81  lea     r9, [rbp+90h+Size]
0x180014b85  mov     rdx, [r15+10h]
0x180014b89  mov     r8d, edi
0x180014b8c  mov     r12d, [rax]
0x180014b8f  lea     rax, [rsp+190h+var_130]
0x180014b94  jmp     short loc_180014BC8
0x180014b96  lea     r8, [rbp+90h+var_68]; unsigned int *
0x180014b9a  lea     rdx, [rbp+90h+var_E0]; struct tMBPropertyDiffRow *
0x180014b9e  call    ?InsertRow@TMetabaseDifferencing@@AEAAJAEAUtMBPropertyDiffRow@@PEAKPEAUISimpleTableWrite2@@@Z; TMetabaseDifferencing::InsertRow(tMBPropertyDiffRow &,ulong *,ISimpleTableWrite2 *)
0x180014ba3  mov     ebx, eax
0x180014ba5  test    eax, eax
0x180014ba7  js      loc_180014DFE
0x180014bad  inc     esi
0x180014baf  cmp     esi, [rsp+190h+var_14C]
0x180014bb3  jz      loc_180014926
0x180014bb9  mov     rdx, [r15+18h]; struct ISimpleTableWrite2 *
0x180014bbd  lea     rax, [rbp+90h+var_E0]
0x180014bc1  lea     r9, [rbp+90h+var_68]; unsigned int *
0x180014bc5  mov     r8d, esi; unsigned int
0x180014bc8  mov     [rsp+190h+var_170], rax; struct tMBPropertyDiffRow *
0x180014bcd  call    ?GetColumnValues_AsMBPropertyDiff@TMetabaseDifferencing@@AEAAJPEAUISimpleTableWrite2@@KQEAKAEAUtMBPropertyDiffRow@@@Z; TMetabaseDifferencing::GetColumnValues_AsMBPropertyDiff(ISimpleTableWrite2 *,ulong,ulong * const,tMBPropertyDiffRow &)
0x180014bd2  mov     ebx, eax
0x180014bd4  test    eax, eax
0x180014bd6  js      loc_180014DFE
0x180014bdc  lea     rbx, ?m_kZero@TMetabaseDifferencing@@0KA; ulong TMetabaseDifferencing::m_kZero
0x180014be3  jmp     loc_180014968
0x180014be8  mov     rax, [rbp+90h+var_F8]
0x180014bec  cmp     [rax], r13d
0x180014bef  jnz     short loc_180014BDC
0x180014bf1  lea     rax, [rsp+190h+var_148]
0x180014bf6  mov     r9, r14; struct ISimpleTableWrite2 *
0x180014bf9  lea     r8, [rbp+90h+Size]; unsigned int *
0x180014bfd  mov     [rbp+90h+var_F8], rax
0x180014c01  lea     rdx, [rsp+190h+var_130]; struct tMBPropertyDiffRow *
0x180014c06  call    ?DeleteRow@TMetabaseDifferencing@@AEAAJAEAUtMBPropertyDiffRow@@PEAKPEAUISimpleTableWrite2@@@Z; TMetabaseDifferencing::DeleteRow(tMBPropertyDiffRow &,ulong *,ISimpleTableWrite2 *)
0x180014c0b  mov     ebx, eax
0x180014c0d  test    eax, eax
0x180014c0f  js      loc_180014DFE
0x180014c15  inc     edi
0x180014c17  cmp     edi, [rsp+190h+var_150]
0x180014c1b  jz      short loc_180014BDC
0x180014c1d  mov     rax, [rbp+90h+var_F8]
  ... truncated ...
```
