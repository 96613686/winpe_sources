# CSessionBaseRW::CleanupFileRecord(SmartPtr<CFileRecord>,int,int)

- ea: `0x18000c450`
- end: `0x18000caf5`
- name: `?CleanupFileRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCFileRecord@@@@HH@Z`
- size: `1701`
- prototype: `__int64 __fastcall(__int64, CFileRecord ***, int, int)`
- caller_count: `6`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d4f4`
- `0x180010844`
- `0x180010de8`
- `0x180012b44`
- `0x180013e14`
- `0x18001cb74`

## callees

- `0x1800025b0`
- `0x180002c24`
- `0x1800062d0`
- `0x180007818`
- `0x180007970`
- `0x180007a9c`
- `0x180007c08`
- `0x180007efc`
- `0x18000815c`
- `0x180009008`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x180009560`
- `0x180009a80`
- `0x180009d70`
- `0x18000c360`
- `0x18000c450`
- `0x1800124a0`
- `0x1800127b0`
- `0x180030790`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c6e1`
- `KERNEL32!GetLastError` at `0x18000c715`
- `KERNEL32!GetLastError` at `0x18000c6e1`
- `KERNEL32!GetLastError` at `0x18000c715`
- `KERNEL32!ResetEvent` at `0x18000c61a`
- `KERNEL32!ResetEvent` at `0x18000c61a`
- `KERNEL32!SetEvent` at `0x18000c75c`
- `KERNEL32!SetEvent` at `0x18000c75c`
- `KERNEL32!GetFileAttributesW` at `0x18000c6b8`
- `KERNEL32!GetFileAttributesW` at `0x18000c6b8`

## string_xrefs

- `0x18000c5ac`: `Deletion of staged files should not fail during File Record cleanup`
- `0x18000c5b8`: `(hr == HRESULT_FROM_WIN32(ERROR_PATH_NOT_FOUND) || hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::CleanupFileRecord(__int64 a1, CFileRecord ***a2, int a3, int a4)
{
  CFileRecord **v8; // rax
  CFileRecord *v9; // r8
  unsigned int v10; // r8d
  int v11; // eax
  int Name; // edi
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  int v15; // eax
  int v16; // ebx
  PVOID *v17; // rcx
  CFileRecord **v18; // rax
  CFileRecord **v19; // rdx
  unsigned int v20; // r8d
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  signed int LastError; // eax
  void (__fastcall *v26)(__int64, _QWORD); // rbx
  signed int v27; // eax
  CFileRecord **v28; // rax
  CFileRecord *v29; // rcx
  __int16 v30; // r15
  CFileRecord *v31; // rax
  CFileRecord **v32; // rbx
  CFileRecord *v33; // rax
  __int64 v34; // rdx
  CFileRecord *v35; // rax
  int v36; // edx
  CFileRecord *v37; // rax
  int v38; // edx
  CFileRecord *v39; // rax
  int v40; // edx
  CFileRecord *v41; // rax
  CFileRecord *v42; // rdi
  _QWORD *v43; // rax
  _QWORD *v44; // rcx
  int v45; // edx
  CFileRecord **v46; // rax
  CFileRecord *v47; // rcx
  CFileRecord *v48; // rcx
  CFileRecord **v50; // [rsp+30h] [rbp-28h] BYREF
  __int64 v51; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v52[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v53; // [rsp+A8h] [rbp+50h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v53);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v51);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
      *((unsigned int *)**a2 + 4));
  v8 = *a2;
  v9 = **a2;
  if ( (*((_BYTE *)v9 + 42) & 0x10) != 0 )
  {
    v10 = *((_DWORD *)v9 + 15);
    v50 = *a2;
    ++*((_DWORD *)v8 + 2);
    v11 = CSessionBaseRO::ConstructStagingPath(a1 + 8, (__int64)&v50, v10, &v53);
    Name = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          *((unsigned int *)**a2 + 4),
          v11);
      goto LABEL_86;
    }
    v13 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            v52,
            (_QWORD *)(a1 + 56));
    v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v50,
            &v53);
    v15 = FheFileOperations::DeleteFileWithEmptyParents(v14, v13);
    v16 = v15;
    if ( v15 < 0 )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          v53,
          v15);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (unsigned int)(v16 + 2147024894) > 1 && v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
        WPP_SF_ss(
          (unsigned int)v17[2],
          91,
          (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)"(hr == HRESULT_FROM_WIN32(ERROR_PATH_NOT_FOUND) || hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))",
          (__int64)"Deletion of staged files should not fail during File Record cleanup");
    }
    v18 = *a2;
    v50 = v18;
    if ( v18 )
      ++*((_DWORD *)v18 + 2);
    CSessionBaseRW::ChangeFileRecordStatus(a1, &v50, 16);
  }
  if ( a4 && (*((_BYTE *)**a2 + 42) & 8) != 0 )
  {
    ResetEvent(*(HANDLE *)(a1 + 160));
    if ( *(_DWORD *)(a1 + 148) )
    {
      v19 = *a2;
      v20 = *((_DWORD *)**a2 + 15);
      v50 = v19;
      if ( v19 )
        ++*((_DWORD *)v19 + 2);
      Name = CSessionBaseRO::ConstructTargetPath(a1 + 8, &v50, v20, (__int64)&v53, &v51);
      if ( Name < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_86;
        v22 = 92;
        goto LABEL_85;
      }
      v23 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v52,
              &v51);
      v24 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v50,
              &v53);
      if ( (int)FheFileOperations::DeleteFileWithEmptyParents(v24, v23) < 0
        && GetFileAttributesW(*(LPCWSTR *)(a1 + 72)) == -1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            93,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)LastError);
        }
        v26 = **(void (__fastcall ***)(__int64, _QWORD))a1;
        v27 = GetLastError();
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        v26(a1, (unsigned int)v27);
      }
      else
      {
        v28 = *a2;
        v50 = v28;
        if ( v28 )
          ++*((_DWORD *)v28 + 2);
        CSessionBaseRW::ChangeFileRecordStatus(a1, &v50, 8);
      }
    }
    SetEvent(*(HANDLE *)(a1 + 160));
  }
  v29 = **a2;
  v30 = 6;
  if ( a3 )
  {
    if ( (*((_BYTE *)v29 + 42) & 0x18) != 0 )
    {
      SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v50);
      v31 = (CFileRecord *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v31 )
        v31 = CFileRecord::CFileRecord(v31, (__int64 *)(a1 + 16), a1 + 24);
      SmartPtr<CFileRecord>::operator=(&v50, v31);
      v32 = v50;
      if ( !v50 || !*v50 )
      {
        Name = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            "newFileRecord");
        goto LABEL_73;
      }
      v33 = *v50;
      *((_DWORD *)v33 + 19) = 1;
      *((_WORD *)v33 + 20) = 6;
      v34 = *((_QWORD *)**a2 + 6);
      v35 = *v32;
      *((_DWORD *)v35 + 19) = 1;
      *((_QWORD *)v35 + 6) = v34;
      v52[0] = v32;
      if ( v32 )
        ++*((_DWORD *)v32 + 2);
      CSessionBaseRW::ChangeFileRecordStatus(a1, v52, 0);
      v36 = *((_DWORD *)**a2 + 14);
      v37 = *v32;
      *((_DWORD *)v37 + 19) = 1;
      *((_DWORD *)v37 + 14) = v36;
      v38 = *((_DWORD *)**a2 + 15);
      v39 = *v32;
      *((_DWORD *)v39 + 19) = 1;
      *((_DWORD *)v39 + 15) = v38;
      v40 = *((_DWORD *)**a2 + 16);
      v41 = *v32;
      *((_DWORD *)v41 + 19) = 1;
      *((_DWORD *)v41 + 16) = v40;
      Name = CFileRecord::GetName(**a2, &v53);
      if ( Name < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            *((unsigned int *)**a2 + 4),
            Name);
        goto LABEL_73;
      }
      v42 = *v32;
      v43 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v52,
              &v53);
      Name = CFileRecord::SetName(v42, v43);
      if ( Name < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_73;
        v45 = 96;
LABEL_59:
        WPP_SF_Sd(v44[2], v45, (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v53, Name);
LABEL_73:
        SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v50);
        goto LABEL_86;
      }
      Name = CFileRecord::Commit(*v32);
      if ( Name < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_73;
        v45 = 97;
        goto LABEL_59;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          98,
          (int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          *((_DWORD *)*v32 + 4),
          v53);
      v46 = *a2;
      v52[0] = v46;
      if ( v46 )
        ++*((_DWORD *)v46 + 2);
      CSessionBaseRW::ChangeFileRecordStatus(a1, v52, 56);
      v47 = **a2;
      *((_DWORD *)v47 + 19) = 1;
      *((_DWORD *)v47 + 15) = 0;
      SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v50);
    }
  }
  else if ( (*((_BYTE *)v29 + 42) & 0x18) == 0 )
  {
    Name = CFileRecord::Delete(v29);
    if ( Name >= 0 )
      goto LABEL_86;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_86;
    v22 = 99;
LABEL_85:
    WPP_SF_dd(v21[2], v22, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, *((unsigned int *)**a2 + 4), Name);
    goto LABEL_86;
  }
  v48 = **a2;
  if ( a3 )
    v30 = 1;
  *((_DWORD *)v48 + 19) = 1;
  *((_WORD *)v48 + 20) = v30;
  Name = CFileRecord::Commit(**a2);
  if ( Name < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 100;
      goto LABEL_85;
    }
  }
LABEL_86:
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v53 - 24));
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(a2);
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x18000c450  push    rbp
0x18000c452  push    rbx
0x18000c453  push    rsi
0x18000c454  push    rdi
0x18000c455  push    r12
0x18000c457  push    r13
0x18000c459  push    r14
0x18000c45b  push    r15
0x18000c45d  mov     rbp, rsp
0x18000c460  sub     rsp, 58h
0x18000c464  mov     r12d, r9d
0x18000c467  mov     r13d, r8d
0x18000c46a  mov     rsi, rdx
0x18000c46d  mov     r14, rcx
0x18000c470  lea     rcx, [rbp+arg_8]
0x18000c474  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c479  lea     rcx, [rbp+var_20]
0x18000c47d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c482  lea     rbx, WPP_GLOBAL_Control
0x18000c489  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c490  cmp     rcx, rbx
0x18000c493  jz      short loc_18000C4BA
0x18000c495  test    byte ptr [rcx+1Ch], 8
0x18000c499  jz      short loc_18000C4BA
0x18000c49b  mov     rax, [rsi]
0x18000c49e  mov     r9, [rax]
0x18000c4a1  mov     edx, 58h ; 'X'
0x18000c4a6  mov     r9d, [r9+10h]
0x18000c4aa  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c4b1  mov     rcx, [rcx+10h]
0x18000c4b5  call    WPP_SF_d
0x18000c4ba  mov     rax, [rsi]
0x18000c4bd  mov     r8, [rax]
0x18000c4c0  test    byte ptr [r8+2Ah], 10h
0x18000c4c5  jz      loc_18000C5FA
0x18000c4cb  mov     r8d, [r8+3Ch]
0x18000c4cf  mov     [rbp+var_28], rax
0x18000c4d3  inc     dword ptr [rax+8]
0x18000c4d6  lea     r9, [rbp+arg_8]
0x18000c4da  lea     rdx, [rbp+var_28]
0x18000c4de  lea     rcx, [r14+8]
0x18000c4e2  call    ?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000c4e7  mov     edi, eax
0x18000c4e9  test    eax, eax
0x18000c4eb  jns     short loc_18000C51B
0x18000c4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4f4  cmp     rcx, rbx
0x18000c4f7  jz      loc_18000CAC0
0x18000c4fd  test    byte ptr [rcx+1Ch], 1
0x18000c501  jz      loc_18000CAC0
0x18000c507  mov     rdx, [rsi]
0x18000c50a  mov     r9, [rdx]
0x18000c50d  mov     edx, 59h ; 'Y'
0x18000c512  mov     dword ptr [rsp+58h+var_38], eax
0x18000c516  jmp     loc_18000CAAC
0x18000c51b  lea     rdx, [r14+38h]
0x18000c51f  lea     rcx, [rbp+var_18]
0x18000c523  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c528  mov     rbx, rax
0x18000c52b  lea     rdx, [rbp+arg_8]
0x18000c52f  lea     rcx, [rbp+var_28]
0x18000c533  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c538  mov     rdx, rbx
0x18000c53b  mov     rcx, rax
0x18000c53e  call    ?DeleteFileWithEmptyParents@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; FheFileOperations::DeleteFileWithEmptyParents(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000c543  mov     ebx, eax
0x18000c545  test    eax, eax
0x18000c547  jns     loc_18000C5D1
0x18000c54d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c554  lea     rdx, WPP_GLOBAL_Control
0x18000c55b  cmp     rcx, rdx
0x18000c55e  jz      short loc_18000C58A
0x18000c560  test    byte ptr [rcx+1Ch], 2
0x18000c564  jz      short loc_18000C58A
0x18000c566  mov     edx, 5Ah ; 'Z'
0x18000c56b  mov     dword ptr [rsp+58h+var_38], eax
0x18000c56f  mov     r9, [rbp+arg_8]
0x18000c573  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c57a  mov     rcx, [rcx+10h]
0x18000c57e  call    WPP_SF_Sd
0x18000c583  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c58a  lea     eax, [rbx+7FF8FFFEh]
0x18000c590  cmp     eax, 1
0x18000c593  jbe     short loc_18000C5D1
0x18000c595  lea     rbx, WPP_GLOBAL_Control
0x18000c59c  cmp     rcx, rbx
0x18000c59f  jz      short loc_18000C5D8
0x18000c5a1  test    byte ptr [rcx+1Ch], 4
0x18000c5a5  jz      short loc_18000C5D8
0x18000c5a7  mov     edx, 5Bh ; '['
0x18000c5ac  lea     rax, aDeletionOfStag; "Deletion of staged files should not fai"...
0x18000c5b3  mov     [rsp+58h+var_38], rax
0x18000c5b8  lea     r9, aHrHresultFromW_1; "(hr == HRESULT_FROM_WIN32(ERROR_PATH_NO"...
0x18000c5bf  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c5c6  mov     rcx, [rcx+10h]
0x18000c5ca  call    WPP_SF_ss
0x18000c5cf  jmp     short loc_18000C5D8
0x18000c5d1  lea     rbx, WPP_GLOBAL_Control
0x18000c5d8  mov     rax, [rsi]
0x18000c5db  mov     [rbp+var_28], rax
0x18000c5df  test    rax, rax
0x18000c5e2  jz      short loc_18000C5E7
0x18000c5e4  inc     dword ptr [rax+8]
0x18000c5e7  xor     r9d, r9d
0x18000c5ea  lea     r8d, [r9+10h]
0x18000c5ee  lea     rdx, [rbp+var_28]
0x18000c5f2  mov     rcx, r14
0x18000c5f5  call    ?ChangeFileRecordStatus@CSessionBaseRW@@IEAAXV?$SmartPtr@VCFileRecord@@@@GG@Z; CSessionBaseRW::ChangeFileRecordStatus(SmartPtr<CFileRecord>,ushort,ushort)
0x18000c5fa  test    r12d, r12d
0x18000c5fd  jz      loc_18000C762
0x18000c603  mov     rax, [rsi]
0x18000c606  mov     rcx, [rax]
0x18000c609  test    byte ptr [rcx+2Ah], 8
0x18000c60d  jz      loc_18000C762
0x18000c613  mov     rcx, [r14+0A0h]; hEvent
0x18000c61a  call    cs:__imp_ResetEvent
0x18000c620  cmp     dword ptr [r14+94h], 0
0x18000c628  jz      loc_18000C755
0x18000c62e  mov     rdx, [rsi]
0x18000c631  mov     rax, [rdx]
0x18000c634  mov     r8d, [rax+3Ch]
0x18000c638  mov     [rbp+var_28], rdx
0x18000c63c  test    rdx, rdx
0x18000c63f  jz      short loc_18000C644
0x18000c641  inc     dword ptr [rdx+8]
0x18000c644  lea     rax, [rbp+var_20]
0x18000c648  mov     [rsp+58h+var_38], rax
0x18000c64d  lea     r9, [rbp+arg_8]
0x18000c651  lea     rdx, [rbp+var_28]
0x18000c655  lea     rcx, [r14+8]
0x18000c659  call    ?ConstructTargetPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; CSessionBaseRO::ConstructTargetPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18000c65e  mov     edi, eax
0x18000c660  test    eax, eax
0x18000c662  jns     short loc_18000C688
0x18000c664  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c66b  cmp     rcx, rbx
0x18000c66e  jz      loc_18000CAC0
0x18000c674  test    byte ptr [rcx+1Ch], 1
0x18000c678  jz      loc_18000CAC0
0x18000c67e  mov     edx, 5Ch ; '\'
0x18000c683  jmp     loc_18000CAA2
0x18000c688  lea     rdx, [rbp+var_20]
0x18000c68c  lea     rcx, [rbp+var_18]
0x18000c690  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c695  mov     rbx, rax
0x18000c698  lea     rdx, [rbp+arg_8]
0x18000c69c  lea     rcx, [rbp+var_28]
0x18000c6a0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c6a5  mov     rdx, rbx
0x18000c6a8  mov     rcx, rax
0x18000c6ab  call    ?DeleteFileWithEmptyParents@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; FheFileOperations::DeleteFileWithEmptyParents(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000c6b0  test    eax, eax
0x18000c6b2  jns     short loc_18000C733
0x18000c6b4  mov     rcx, [r14+48h]; lpFileName
0x18000c6b8  call    cs:__imp_GetFileAttributesW
0x18000c6be  cmp     eax, 0FFFFFFFFh
0x18000c6c1  jnz     short loc_18000C733
0x18000c6c3  mov     edi, 80070000h
0x18000c6c8  mov     rax, cs:WPP_GLOBAL_Control
0x18000c6cf  lea     rdx, WPP_GLOBAL_Control
0x18000c6d6  cmp     rax, rdx
0x18000c6d9  jz      short loc_18000C70F
0x18000c6db  test    byte ptr [rax+1Ch], 8
0x18000c6df  jz      short loc_18000C70F
0x18000c6e1  call    cs:__imp_GetLastError
0x18000c6e7  test    eax, eax
0x18000c6e9  jle     short loc_18000C6F0
0x18000c6eb  movzx   eax, ax
0x18000c6ee  or      eax, edi
0x18000c6f0  mov     edx, 5Dh ; ']'
0x18000c6f5  mov     r9d, eax
0x18000c6f8  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c706  mov     rcx, [rcx+10h]
0x18000c70a  call    WPP_SF_d
0x18000c70f  mov     rax, [r14]
0x18000c712  mov     rbx, [rax]
0x18000c715  call    cs:__imp_GetLastError
0x18000c71b  test    eax, eax
0x18000c71d  jle     short loc_18000C724
0x18000c71f  movzx   eax, ax
0x18000c722  or      eax, edi
0x18000c724  mov     edx, eax
0x18000c726  mov     rcx, r14
0x18000c729  mov     rax, rbx
0x18000c72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c731  jmp     short loc_18000C755
0x18000c733  mov     rax, [rsi]
0x18000c736  mov     [rbp+var_28], rax
0x18000c73a  test    rax, rax
0x18000c73d  jz      short loc_18000C742
0x18000c73f  inc     dword ptr [rax+8]
0x18000c742  xor     r9d, r9d
0x18000c745  lea     r8d, [r9+8]
0x18000c749  lea     rdx, [rbp+var_28]
0x18000c74d  mov     rcx, r14
0x18000c750  call    ?ChangeFileRecordStatus@CSessionBaseRW@@IEAAXV?$SmartPtr@VCFileRecord@@@@GG@Z; CSessionBaseRW::ChangeFileRecordStatus(SmartPtr<CFileRecord>,ushort,ushort)
0x18000c755  mov     rcx, [r14+0A0h]; hEvent
0x18000c75c  call    cs:__imp_SetEvent
0x18000c762  mov     rax, [rsi]
0x18000c765  mov     rcx, [rax]; this
0x18000c768  mov     r15d, 6
0x18000c76e  test    r13d, r13d
0x18000c771  jz      loc_18000CA1E
0x18000c777  test    byte ptr [rcx+2Ah], 18h
0x18000c77b  jz      loc_18000CA53
0x18000c781  lea     rcx, [rbp+var_28]
0x18000c785  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000c78a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c791  lea     ecx, [r15+4Ah]; unsigned __int64
0x18000c795  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c79a  test    rax, rax
0x18000c79d  jz      short loc_18000C7AF
0x18000c79f  lea     r8, [r14+18h]
0x18000c7a3  lea     rdx, [r14+10h]
0x18000c7a7  mov     rcx, rax; this
0x18000c7aa  call    ??0CFileRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CFileRecord::CFileRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18000c7af  mov     rdx, rax
0x18000c7b2  lea     rcx, [rbp+var_28]
0x18000c7b6  call    ??4?$SmartPtr@VCFileRecord@@@@QEAAAEAV0@PEAVCFileRecord@@@Z; SmartPtr<CFileRecord>::operator=(CFileRecord *)
0x18000c7bb  mov     rbx, [rbp+var_28]
0x18000c7bf  test    rbx, rbx
0x18000c7c2  jz      loc_18000C9D6
0x18000c7c8  cmp     qword ptr [rbx], 0
0x18000c7cc  jz      loc_18000C9D6
0x18000c7d2  mov     rax, [rbx]
0x18000c7d5  mov     r12d, 1
0x18000c7db  mov     [rax+4Ch], r12d
0x18000c7df  mov     [rax+28h], r15w
0x18000c7e4  mov     rax, [rsi]
0x18000c7e7  mov     rcx, [rax]
0x18000c7ea  mov     rdx, [rcx+30h]
0x18000c7ee  mov     rax, [rbx]
0x18000c7f1  mov     [rax+4Ch], r12d
0x18000c7f5  mov     [rax+30h], rdx
0x18000c7f9  mov     rax, [rsi]
0x18000c7fc  mov     rcx, [rax]
0x18000c7ff  movzx   r9d, word ptr [rcx+2Ah]
0x18000c804  and     r9w, 18h
0x18000c809  mov     [rbp+var_18], rbx
0x18000c80d  test    rbx, rbx
0x18000c810  jz      short loc_18000C816
0x18000c812  add     [rbx+8], r12d
0x18000c816  xor     r8d, r8d
0x18000c819  lea     rdx, [rbp+var_18]
0x18000c81d  mov     rcx, r14
0x18000c820  call    ?ChangeFileRecordStatus@CSessionBaseRW@@IEAAXV?$SmartPtr@VCFileRecord@@@@GG@Z; CSessionBaseRW::ChangeFileRecordStatus(SmartPtr<CFileRecord>,ushort,ushort)
0x18000c825  mov     rax, [rsi]
0x18000c828  mov     rcx, [rax]
0x18000c82b  mov     edx, [rcx+38h]
0x18000c82e  mov     rax, [rbx]
0x18000c831  mov     [rax+4Ch], r12d
0x18000c835  mov     [rax+38h], edx
0x18000c838  mov     rax, [rsi]
0x18000c83b  mov     rcx, [rax]
0x18000c83e  mov     edx, [rcx+3Ch]
0x18000c841  mov     rax, [rbx]
0x18000c844  mov     [rax+4Ch], r12d
0x18000c848  mov     [rax+3Ch], edx
0x18000c84b  mov     rax, [rsi]
0x18000c84e  mov     rcx, [rax]
0x18000c851  mov     edx, [rcx+40h]
0x18000c854  mov     rax, [rbx]
0x18000c857  mov     [rax+4Ch], r12d
0x18000c85b  mov     [rax+40h], edx
0x18000c85e  mov     rcx, [rsi]
0x18000c861  lea     rdx, [rbp+arg_8]
0x18000c865  mov     rcx, [rcx]
0x18000c868  call    ?GetName@CFileRecord@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileRecord::GetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000c86d  mov     edi, eax
0x18000c86f  test    eax, eax
0x18000c871  jns     short loc_18000C8BC
0x18000c873  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c87a  lea     rax, WPP_GLOBAL_Control
0x18000c881  cmp     rcx, rax
0x18000c884  jz      loc_18000CA10
0x18000c88a  test    [rcx+1Ch], r12b
0x18000c88e  jz      loc_18000CA10
0x18000c894  mov     rax, [rsi]
0x18000c897  mov     r9, [rax]
0x18000c89a  mov     edx, 5Fh ; '_'
0x18000c89f  mov     dword ptr [rsp+58h+var_38], edi
0x18000c8a3  mov     r9d, [r9+10h]
0x18000c8a7  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000c8ae  mov     rcx, [rcx+10h]
0x18000c8b2  call    WPP_SF_dd
0x18000c8b7  jmp     loc_18000CA10
0x18000c8bc  mov     rdi, [rbx]
0x18000c8bf  lea     rdx, [rbp+arg_8]
0x18000c8c3  lea     rcx, [rbp+var_18]
0x18000c8c7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000c8cc  mov     rdx, rax
0x18000c8cf  mov     rcx, rdi
0x18000c8d2  call    ?SetName@CFileRecord@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileRecord::SetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000c8d7  mov     edi, eax
0x18000c8d9  test    eax, eax
0x18000c8db  jns     short loc_18000C920
0x18000c8dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8e4  lea     rax, WPP_GLOBAL_Control
0x18000c8eb  cmp     rcx, rax
  ... truncated ...
```
