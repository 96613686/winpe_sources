# CSessionBaseRW::DeleteFileVersion(SmartPtr<CFileRecord>,int)

- ea: `0x18000d4f4`
- end: `0x18000dc81`
- name: `?DeleteFileVersion@CSessionBaseRW@@IEAAJV?$SmartPtr@VCFileRecord@@@@H@Z`
- size: `1933`
- prototype: `__int64 __fastcall(CSessionBaseRW *this, _QWORD *)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cafc`
- `0x180013e14`

## callees

- `0x1800025b0`
- `0x180002c24`
- `0x1800031b0`
- `0x1800062d0`
- `0x180007818`
- `0x180007a1c`
- `0x180007a9c`
- `0x180007c08`
- `0x180007d5c`
- `0x1800081d0`
- `0x18000835c`
- `0x1800086d4`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x180009528`
- `0x18000960c`
- `0x18000a4ac`
- `0x18000c450`
- `0x18000d0fc`
- `0x18000d4f4`
- `0x180010914`
- `0x180012278`
- `0x180012418`
- `0x1800125b8`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::DeleteFileVersion(CSessionBaseRW *this, _QWORD *a2)
{
  __int64 *v3; // r15
  CNamespaceRecord *v4; // rax
  CNamespaceRecord *v5; // rax
  _QWORD *v6; // rdi
  CNamespaceRecord *v7; // rax
  CNamespaceRecord *v8; // rax
  CNamespaceRecord **v9; // rsi
  int v10; // r14d
  int Name; // r12d
  int v12; // r8d
  unsigned __int16 *v13; // rbx
  CNamespaceRecord *v14; // rcx
  __int16 v15; // ax
  unsigned int v16; // eax
  int v17; // r14d
  _QWORD *v18; // rax
  __int64 ***v19; // r14
  __int64 **v20; // rax
  CNamespaceRecord **v21; // r15
  PVOID *v22; // r11
  ATL::CStringData *v23; // rcx
  _QWORD *v24; // rcx
  int v25; // edx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rbx
  __int64 v29; // rax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  const char *v32; // r9
  unsigned __int16 *v34; // [rsp+58h] [rbp-29h] BYREF
  CNamespaceRecord **v35; // [rsp+60h] [rbp-21h] BYREF
  __int64 ***v36; // [rsp+68h] [rbp-19h] BYREF
  __int64 v37; // [rsp+70h] [rbp-11h] BYREF
  CNamespaceRecord **v38; // [rsp+78h] [rbp-9h] BYREF
  _QWORD v39[2]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v40; // [rsp+90h] [rbp+Fh] BYREF
  _QWORD v41[8]; // [rsp+98h] [rbp+17h] BYREF
  CFileRecord **v44; // [rsp+100h] [rbp+7Fh] BYREF

  v3 = (__int64 *)this;
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(v39);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v38);
  v37 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      105,
      &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
      *(unsigned int *)(*(_QWORD *)*a2 + 16LL));
  v4 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v5 = CNamespaceRecord::CNamespaceRecord(v4, v3 + 2, (__int64)(v3 + 3));
  else
    v5 = 0;
  SmartPtr<CNamespaceRecord>::operator=(v39, v5);
  v6 = (_QWORD *)v39[0];
  if ( !v39[0] || !*(_QWORD *)v39[0] )
  {
    Name = -2147024882;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_97;
    v31 = 106;
    v32 = "namespaceRecord";
    goto LABEL_96;
  }
  v7 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v8 = CNamespaceRecord::CNamespaceRecord(v7, v3 + 2, (__int64)(v3 + 3));
  else
    v8 = 0;
  SmartPtr<CNamespaceRecord>::operator=(&v38, v8);
  v9 = v38;
  if ( !v38 || !*v38 )
  {
    Name = -2147024882;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_97;
    v31 = 107;
    v32 = "prevNamespaceRecord";
LABEL_96:
    WPP_SF_s(v30[2], v31, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v32);
LABEL_97:
    v28 = a2;
    goto LABEL_98;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v3[2] + 240LL))(
          v3[2],
          *(unsigned int *)(*(_QWORD *)*a2 + 16LL),
          &v37);
  while ( v10 >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v34);
    Name = CNamespaceRecord::LoadCurrentFromEnum(*v6, &v37);
    if ( Name < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)Name);
      goto LABEL_71;
    }
    v39[1] = v6;
    ++*((_DWORD *)v6 + 2);
    Name = CSessionBaseRW::RemoveNamespaceRecord((CSessionBaseRW *)v3);
    if ( Name < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = 109;
LABEL_70:
        WPP_SF_dd(v26[2], v27, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, *(unsigned int *)(*v6 + 16LL), Name);
      }
LABEL_71:
      v23 = (ATL::CStringData *)(v34 - 12);
      goto LABEL_51;
    }
    Name = CNamespaceRecord::GetName(*v6, &v34);
    if ( Name < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = 110;
        goto LABEL_70;
      }
      goto LABEL_71;
    }
    v12 = *(_DWORD *)(*v6 + 76LL);
    v13 = v34;
    if ( v12 > 1 && CNamespaceRecord::LoadFromCatalog(*v9, v34, v12 - 1) >= 0 )
    {
      v14 = *v9;
      if ( *((_DWORD *)*v9 + 20) + 1 == *(_DWORD *)(*v6 + 76LL) && (*((_BYTE *)v14 + 40) & 2) == 0 )
      {
        *((_DWORD *)v14 + 20) = *(_DWORD *)(*v6 + 80LL);
        if ( *(_DWORD *)(*v6 + 80LL) == -1 )
        {
          v15 = *((_WORD *)*v9 + 20);
          if ( (v15 & 1) != 0 )
            *((_WORD *)*v9 + 20) = v15 & 0xFFFE;
        }
        Name = CNamespaceRecord::Commit(*v9);
        if ( Name < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              *((unsigned int *)*v9 + 4),
              Name);
LABEL_50:
          v23 = (ATL::CStringData *)(v13 - 12);
LABEL_51:
          ATL::CStringData::Release(v23);
          goto LABEL_97;
        }
      }
    }
    if ( *(_DWORD *)(*v6 + 80LL) == -1 )
    {
      SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v44);
      v16 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                            &v40,
                            &v34);
      Name = CSessionBaseRO::GetLastNamespaceRecord((int)v3 + 8, v16, (unsigned int)&v44, 0, 1);
      if ( Name < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)v13,
            Name);
        goto LABEL_57;
      }
      if ( !v44 || !*v44 || (*((_BYTE *)*v44 + 40) & 0x10) == 0 )
      {
        SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v36);
        SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v35);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v13);
        v17 = *(_DWORD *)(*v6 + 76LL);
        v18 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                v41,
                &v34);
        Name = CSessionBaseRW::CreateNamespaceFilePair((__int64)v3, v18, v17, (__int64 **)&v35, (__int64 **)&v36);
        if ( Name < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v25 = 114;
LABEL_55:
            WPP_SF_Sd(v24[2], v25, (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, (_DWORD)v13, Name);
          }
LABEL_56:
          SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v35);
          SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v36);
LABEL_57:
          SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v44);
          goto LABEL_50;
        }
        v19 = v36;
        v20 = *v36;
        *((_DWORD *)v20 + 19) = 1;
        *((_WORD *)v20 + 21) |= 4u;
        Name = CFileRecord::Commit(*v19);
        if ( Name < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v25 = 115;
            goto LABEL_55;
          }
          goto LABEL_56;
        }
        v21 = v35;
        *((_QWORD *)*v35 + 6) = *(_QWORD *)(*v6 + 48LL);
        *(_QWORD *)((char *)*v21 + 68) = *(_QWORD *)(*v6 + 48LL);
        *((_DWORD *)*v21 + 21) = *((_DWORD *)*v19 + 4);
        Name = CNamespaceRecord::Commit(*v21);
        if ( Name < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v25 = 116;
            goto LABEL_55;
          }
          goto LABEL_56;
        }
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_ddDddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              *((unsigned int *)*v19 + 4),
              *((unsigned __int16 *)*v19 + 20),
              *((unsigned __int16 *)*v19 + 21),
              *((_DWORD *)*v19 + 14),
              *((_DWORD *)*v19 + 15),
              *((_DWORD *)*v19 + 16));
            v22 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 8) != 0 )
            WPP_SF_dDddid(
              v22[2],
              118,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              *((unsigned int *)*v21 + 4),
              *((unsigned __int16 *)*v21 + 20),
              *((_DWORD *)*v21 + 19),
              *((_DWORD *)*v21 + 20),
              *((_QWORD *)*v21 + 6),
              *((_DWORD *)*v21 + 21));
        }
        SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v35);
        SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v36);
        v3 = (__int64 *)this;
      }
      SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v44);
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
  }
  Name = 0;
  if ( v10 != -2147023728 )
    Name = v10;
  if ( Name >= 0 )
  {
    v28 = a2;
    v29 = *a2;
    v44 = (CFileRecord **)v29;
    if ( v29 )
      ++*(_DWORD *)(v29 + 8);
    Name = CSessionBaseRW::CleanupFileRecord((__int64)v3, &v44, 0, 1);
    if ( Name < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        (unsigned int)Name);
  }
  else
  {
    v28 = a2;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        *(unsigned int *)(*(_QWORD *)*a2 + 16LL),
        Name);
  }
LABEL_98:
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v37);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v38);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(v39);
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(v28);
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x18000d4f4  mov     rax, rsp
0x18000d4f7  mov     [rax+18h], rbx
0x18000d4fb  mov     [rax+10h], rdx
0x18000d4ff  mov     [rax+8], rcx
0x18000d503  push    rbp
0x18000d504  push    rsi
0x18000d505  push    rdi
0x18000d506  push    r12
0x18000d508  push    r13
0x18000d50a  push    r14
0x18000d50c  push    r15
0x18000d50e  lea     rbp, [rax-5Fh]
0x18000d512  sub     rsp, 0A0h
0x18000d519  mov     r12, rdx
0x18000d51c  mov     r15, rcx
0x18000d51f  lea     rcx, [rbp+57h+var_58]
0x18000d523  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000d528  lea     rcx, [rbp+57h+var_60]
0x18000d52c  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000d531  xor     r14d, r14d
0x18000d534  mov     [rbp+57h+var_68], r14
0x18000d538  lea     r13, WPP_GLOBAL_Control
0x18000d53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d546  cmp     rcx, r13
0x18000d549  jz      short loc_18000D570
0x18000d54b  test    byte ptr [rcx+1Ch], 8
0x18000d54f  jz      short loc_18000D570
0x18000d551  mov     rax, [r12]
0x18000d555  mov     r9, [rax]
0x18000d558  lea     edx, [r14+69h]
0x18000d55c  mov     r9d, [r9+10h]
0x18000d560  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d567  mov     rcx, [rcx+10h]
0x18000d56b  call    WPP_SF_d
0x18000d570  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d577  mov     ebx, 58h ; 'X'
0x18000d57c  mov     ecx, ebx; unsigned __int64
0x18000d57e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d583  test    rax, rax
0x18000d586  jz      short loc_18000D59A
0x18000d588  lea     r8, [r15+18h]
0x18000d58c  lea     rdx, [r15+10h]
0x18000d590  mov     rcx, rax; this
0x18000d593  call    ??0CNamespaceRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CNamespaceRecord::CNamespaceRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18000d598  jmp     short loc_18000D59D
0x18000d59a  mov     rax, r14
0x18000d59d  mov     rdx, rax
0x18000d5a0  lea     rcx, [rbp+57h+var_58]
0x18000d5a4  call    ??4?$SmartPtr@VCNamespaceRecord@@@@QEAAAEAV0@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::operator=(CNamespaceRecord *)
0x18000d5a9  mov     rdi, [rbp+57h+var_58]
0x18000d5ad  test    rdi, rdi
0x18000d5b0  jz      loc_18000DC03
0x18000d5b6  cmp     [rdi], r14
0x18000d5b9  jz      loc_18000DC03
0x18000d5bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d5c6  mov     rcx, rbx; unsigned __int64
0x18000d5c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d5ce  test    rax, rax
0x18000d5d1  jz      short loc_18000D5E5
0x18000d5d3  lea     r8, [r15+18h]
0x18000d5d7  lea     rdx, [r15+10h]
0x18000d5db  mov     rcx, rax; this
0x18000d5de  call    ??0CNamespaceRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CNamespaceRecord::CNamespaceRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18000d5e3  jmp     short loc_18000D5E8
0x18000d5e5  mov     rax, r14
0x18000d5e8  mov     rdx, rax
0x18000d5eb  lea     rcx, [rbp+57h+var_60]
0x18000d5ef  call    ??4?$SmartPtr@VCNamespaceRecord@@@@QEAAAEAV0@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::operator=(CNamespaceRecord *)
0x18000d5f4  mov     rsi, [rbp+57h+var_60]
0x18000d5f8  test    rsi, rsi
0x18000d5fb  jz      loc_18000DBD8
0x18000d601  cmp     [rsi], r14
0x18000d604  jz      loc_18000DBD8
0x18000d60a  mov     rcx, [r15+10h]
0x18000d60e  mov     r8, [rcx]
0x18000d611  mov     rax, [r12]
0x18000d615  mov     rdx, [rax]
0x18000d618  mov     rax, [r8+0F0h]
0x18000d61f  lea     r8, [rbp+57h+var_68]
0x18000d623  mov     edx, [rdx+10h]
0x18000d626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d62b  mov     r14d, eax
0x18000d62e  mov     r13d, 1
0x18000d634  test    r14d, r14d
0x18000d637  js      loc_18000DB0B
0x18000d63d  lea     rcx, [rbp+57h+var_80]
0x18000d641  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000d646  lea     rdx, [rbp+57h+var_68]
0x18000d64a  mov     rcx, [rdi]
0x18000d64d  call    ?LoadCurrentFromEnum@CNamespaceRecord@@QEAAJAEBV?$CComPtr@UIFhNamespaceRecordEnum@@@ATL@@@Z; CNamespaceRecord::LoadCurrentFromEnum(ATL::CComPtr<IFhNamespaceRecordEnum> const &)
0x18000d652  mov     r12d, eax
0x18000d655  test    eax, eax
0x18000d657  js      loc_18000DAD8
0x18000d65d  mov     [rbp+57h+var_50], rdi
0x18000d661  add     [rdi+8], r13d
0x18000d665  xor     r9d, r9d
0x18000d668  xor     r8d, r8d
0x18000d66b  lea     rdx, [rbp+57h+var_50]
0x18000d66f  mov     rcx, r15; this
0x18000d672  call    ?RemoveNamespaceRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCNamespaceRecord@@@@HJ@Z; CSessionBaseRW::RemoveNamespaceRecord(SmartPtr<CNamespaceRecord>,int,long)
0x18000d677  mov     r12d, eax
0x18000d67a  test    eax, eax
0x18000d67c  js      loc_18000DAB8
0x18000d682  lea     rdx, [rbp+57h+var_80]
0x18000d686  mov     rcx, [rdi]
0x18000d689  call    ?GetName@CNamespaceRecord@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CNamespaceRecord::GetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000d68e  mov     r12d, eax
0x18000d691  test    eax, eax
0x18000d693  js      loc_18000DA71
0x18000d699  mov     rax, [rdi]
0x18000d69c  mov     r8d, [rax+4Ch]
0x18000d6a0  mov     rbx, [rbp+57h+var_80]
0x18000d6a4  cmp     r8d, r13d
0x18000d6a7  jle     short loc_18000D70C
0x18000d6a9  dec     r8d; int
0x18000d6ac  mov     rdx, rbx; unsigned __int16 *
0x18000d6af  mov     rcx, [rsi]; this
0x18000d6b2  call    ?LoadFromCatalog@CNamespaceRecord@@QEAAJPEBGJ@Z; CNamespaceRecord::LoadFromCatalog(ushort const *,long)
0x18000d6b7  test    eax, eax
0x18000d6b9  js      short loc_18000D70C
0x18000d6bb  mov     rdx, [rdi]
0x18000d6be  mov     rcx, [rsi]
0x18000d6c1  mov     eax, [rcx+50h]
0x18000d6c4  add     eax, r13d
0x18000d6c7  cmp     eax, [rdx+4Ch]
0x18000d6ca  jnz     short loc_18000D70C
0x18000d6cc  test    byte ptr [rcx+28h], 2
0x18000d6d0  jnz     short loc_18000D70C
0x18000d6d2  mov     eax, [rdx+50h]
0x18000d6d5  mov     [rcx+50h], eax
0x18000d6d8  mov     rax, [rdi]
0x18000d6db  cmp     dword ptr [rax+50h], 0FFFFFFFFh
0x18000d6df  jnz     short loc_18000D6F9
0x18000d6e1  mov     rcx, [rsi]
0x18000d6e4  movzx   eax, word ptr [rcx+28h]
0x18000d6e8  test    r13b, al
0x18000d6eb  jz      short loc_18000D6F9
0x18000d6ed  mov     edx, 0FFFEh
0x18000d6f2  and     ax, dx
0x18000d6f5  mov     [rcx+28h], ax
0x18000d6f9  mov     rcx, [rsi]; this
0x18000d6fc  call    ?Commit@CNamespaceRecord@@QEAAJXZ; CNamespaceRecord::Commit(void)
0x18000d701  mov     r12d, eax
0x18000d704  test    eax, eax
0x18000d706  js      loc_18000D95B
0x18000d70c  mov     rax, [rdi]
0x18000d70f  cmp     dword ptr [rax+50h], 0FFFFFFFFh
0x18000d713  jnz     loc_18000D93A
0x18000d719  lea     rcx, [rbp+57h+arg_18]
0x18000d71d  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000d722  lea     rdx, [rbp+57h+var_80]
0x18000d726  lea     rcx, [rbp+57h+var_48]
0x18000d72a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000d72f  mov     rdx, rax
0x18000d732  lea     rcx, [r15+8]
0x18000d736  mov     [rsp+0D0h+var_B0], r13d
0x18000d73b  xor     r9d, r9d
0x18000d73e  lea     r8, [rbp+57h+arg_18]
0x18000d742  call    ?GetLastNamespaceRecord@CSessionBaseRO@@IEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCNamespaceRecord@@@@HH@Z; CSessionBaseRO::GetLastNamespaceRecord(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CNamespaceRecord> &,int,int)
0x18000d747  mov     r12d, eax
0x18000d74a  test    eax, eax
0x18000d74c  js      loc_18000DA36
0x18000d752  mov     rax, [rbp+57h+arg_18]
0x18000d756  test    rax, rax
0x18000d759  jz      short loc_18000D76E
0x18000d75b  cmp     qword ptr [rax], 0
0x18000d75f  jz      short loc_18000D76E
0x18000d761  mov     rcx, [rax]
0x18000d764  test    byte ptr [rcx+28h], 10h
0x18000d768  jnz     loc_18000D931
0x18000d76e  lea     rcx, [rbp+57h+var_70]
0x18000d772  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000d777  lea     rcx, [rbp+57h+var_78]
0x18000d77b  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000d780  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d787  lea     rax, WPP_GLOBAL_Control
0x18000d78e  cmp     rcx, rax
0x18000d791  jz      short loc_18000D7B1
0x18000d793  test    byte ptr [rcx+1Ch], 8
0x18000d797  jz      short loc_18000D7B1
0x18000d799  mov     edx, 71h ; 'q'
0x18000d79e  mov     r9, rbx
0x18000d7a1  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d7a8  mov     rcx, [rcx+10h]
0x18000d7ac  call    WPP_SF_S
0x18000d7b1  mov     rax, [rdi]
0x18000d7b4  mov     r14d, [rax+4Ch]
0x18000d7b8  lea     rdx, [rbp+57h+var_80]
0x18000d7bc  lea     rcx, [rbp+57h+var_40]
0x18000d7c0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000d7c5  lea     rcx, [rbp+57h+var_70]
0x18000d7c9  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18000d7ce  lea     r9, [rbp+57h+var_78]
0x18000d7d2  mov     r8d, r14d
0x18000d7d5  mov     rdx, rax
0x18000d7d8  mov     rcx, r15
0x18000d7db  call    ?CreateNamespaceFilePair@CSessionBaseRW@@IEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@JAEAV?$SmartPtr@VCNamespaceRecord@@@@AEAV?$SmartPtr@VCFileRecord@@@@@Z; CSessionBaseRW::CreateNamespaceFilePair(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,long,SmartPtr<CNamespaceRecord> &,SmartPtr<CFileRecord> &)
0x18000d7e0  mov     r12d, eax
0x18000d7e3  test    eax, eax
0x18000d7e5  js      loc_18000DA16
0x18000d7eb  mov     r14, [rbp+57h+var_70]
0x18000d7ef  mov     rax, [r14]
0x18000d7f2  mov     [rax+4Ch], r13d
0x18000d7f6  or      word ptr [rax+2Ah], 4
0x18000d7fb  mov     rcx, [r14]; this
0x18000d7fe  call    ?Commit@CFileRecord@@QEAAJXZ; CFileRecord::Commit(void)
0x18000d803  mov     r12d, eax
0x18000d806  test    eax, eax
0x18000d808  js      loc_18000D9F6
0x18000d80e  mov     rax, [rdi]
0x18000d811  mov     r15, [rbp+57h+var_78]
0x18000d815  mov     rcx, [r15]
0x18000d818  mov     rax, [rax+30h]
0x18000d81c  mov     [rcx+30h], rax
0x18000d820  mov     rax, [rdi]
0x18000d823  mov     rcx, [rax+30h]
0x18000d827  sar     rcx, 20h
0x18000d82b  mov     rax, [r15]
0x18000d82e  mov     [rax+48h], ecx
0x18000d831  mov     rax, [rdi]
0x18000d834  mov     rcx, [r15]
0x18000d837  mov     eax, [rax+30h]
0x18000d83a  mov     [rcx+44h], eax
0x18000d83d  mov     rax, [r14]
0x18000d840  mov     rcx, [r15]
0x18000d843  mov     eax, [rax+10h]
0x18000d846  mov     [rcx+54h], eax
0x18000d849  mov     rcx, [r15]; this
0x18000d84c  call    ?Commit@CNamespaceRecord@@QEAAJXZ; CNamespaceRecord::Commit(void)
0x18000d851  mov     r12d, eax
0x18000d854  test    eax, eax
0x18000d856  js      loc_18000D9A3
0x18000d85c  mov     r11, cs:WPP_GLOBAL_Control
0x18000d863  lea     r12, WPP_GLOBAL_Control
0x18000d86a  cmp     r11, r12
0x18000d86d  jz      loc_18000D91B
0x18000d873  test    byte ptr [r11+1Ch], 8
0x18000d878  jz      short loc_18000D8C9
0x18000d87a  mov     r9, [r14]
0x18000d87d  movzx   r8d, word ptr [r9+2Ah]
0x18000d882  movzx   r10d, word ptr [r9+28h]
0x18000d887  mov     edx, 75h ; 'u'
0x18000d88c  mov     eax, [r9+40h]
0x18000d890  mov     [rsp+40h], eax
0x18000d894  mov     eax, [r9+3Ch]
0x18000d898  mov     [rsp+0D0h+var_98], eax
0x18000d89c  mov     eax, [r9+38h]
0x18000d8a0  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18000d8a4  mov     [rsp+0D0h+var_A8], r8d
0x18000d8a9  mov     [rsp+0D0h+var_B0], r10d
0x18000d8ae  mov     r9d, [r9+10h]
0x18000d8b2  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d8b9  mov     rcx, [r11+10h]
0x18000d8bd  call    WPP_SF_ddDddd
0x18000d8c2  mov     r11, cs:WPP_GLOBAL_Control
0x18000d8c9  cmp     r11, r12
0x18000d8cc  jz      short loc_18000D91B
0x18000d8ce  test    byte ptr [r11+1Ch], 8
0x18000d8d3  jz      short loc_18000D91B
0x18000d8d5  mov     r9, [r15]
0x18000d8d8  movzx   ecx, word ptr [r9+28h]
0x18000d8dd  mov     edx, 76h ; 'v'
0x18000d8e2  mov     eax, [r9+54h]
0x18000d8e6  mov     [rsp+40h], eax
0x18000d8ea  mov     rax, [r9+30h]
0x18000d8ee  mov     qword ptr [rsp+0D0h+var_98], rax
0x18000d8f3  mov     eax, [r9+50h]
0x18000d8f7  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18000d8fb  mov     eax, [r9+4Ch]
0x18000d8ff  mov     [rsp+0D0h+var_A8], eax
0x18000d903  mov     [rsp+0D0h+var_B0], ecx
0x18000d907  mov     r9d, [r9+10h]
0x18000d90b  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d912  mov     rcx, [r11+10h]
0x18000d916  call    WPP_SF_dDddid
0x18000d91b  lea     rcx, [rbp+57h+var_78]
0x18000d91f  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x18000d924  lea     rcx, [rbp+57h+var_70]
0x18000d928  call    ??1?$SmartPtr@VCFileRecord@@@@QEAA@XZ; SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(void)
0x18000d92d  mov     r15, [rbp+57h+arg_0]
0x18000d931  lea     rcx, [rbp+57h+arg_18]
0x18000d935  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x18000d93a  mov     rcx, [rbp+57h+var_68]
0x18000d93e  mov     rax, [rcx]
0x18000d941  mov     rax, [rax+20h]
0x18000d945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d94a  mov     r14d, eax
0x18000d94d  lea     rcx, [rbx-18h]; this
0x18000d951  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d956  jmp     loc_18000D634
0x18000d95b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d962  lea     rax, WPP_GLOBAL_Control
0x18000d969  cmp     rcx, rax
0x18000d96c  jz      short loc_18000D995
0x18000d96e  test    [rcx+1Ch], r13b
0x18000d972  jz      short loc_18000D995
0x18000d974  mov     r9, [rsi]
0x18000d977  mov     edx, 6Fh ; 'o'
0x18000d97c  mov     [rsp+0D0h+var_B0], r12d
0x18000d981  mov     r9d, [r9+10h]
  ... truncated ...
```
