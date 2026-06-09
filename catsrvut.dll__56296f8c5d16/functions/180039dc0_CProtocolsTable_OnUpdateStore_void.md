# CProtocolsTable::OnUpdateStore(void)

- ea: `0x180039dc0`
- end: `0x18003a5ce`
- name: `?OnUpdateStore@CProtocolsTable@@UEAAJXZ`
- size: `2062`
- prototype: `__int64 __fastcall(CProtocolsTable *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001e60`
- `0x180006540`
- `0x1800065f0`
- `0x180006770`
- `0x180007328`
- `0x180014f58`
- `0x180023834`
- `0x1800351c0`
- `0x180036ec0`
- `0x1800370bc`
- `0x1800397a8`
- `0x1800397dc`
- `0x180039dc0`
- `0x18003a6d0`
- `0x18003a750`
- `0x18003a780`
- `0x180053e18`
- `0x180053f3c`
- `0x180054424`
- `0x18005583a`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a50e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a50e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a16c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a3a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a16c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a3a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a47e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a47e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a4c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a4c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a51e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a51e`

## string_xrefs

- `0x18003a4bb`: `DCOM Protocols`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CProtocolsTable::OnUpdateStore(CProtocolsTable *this)
{
  unsigned int v2; // r13d
  int v3; // ebx
  int v5; // ebx
  int v6; // r14d
  CProtocolsTable *v7; // rcx
  signed int v8; // edi
  _OWORD *v9; // rax
  _DWORD *v10; // rdi
  __int64 v11; // rax
  unsigned __int64 v12; // r15
  unsigned __int16 *v13; // rax
  __int64 v14; // r10
  void *v15; // rsi
  CSimpleDataTableCursor *v16; // r15
  __int64 v17; // rsi
  unsigned __int16 *v18; // r12
  int v19; // esi
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rsi
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // r14
  __int64 v26; // r15
  __int64 v27; // r14
  __int64 v28; // rsi
  int v29; // eax
  _QWORD *v30; // r12
  __int64 v31; // rax
  unsigned __int64 v32; // r15
  __int64 *v33; // rsi
  __int64 *v34; // r14
  __int64 v35; // rdx
  unsigned int v36; // ecx
  int v37; // r9d
  __int64 v38; // rcx
  _QWORD *v39; // rdx
  _QWORD *v40; // r8
  __int64 v41; // r10
  unsigned __int16 *v42; // rax
  wchar_t *v43; // r14
  unsigned __int16 *v44; // r12
  unsigned int v45; // esi
  wchar_t *v46; // rdx
  LSTATUS v47; // eax
  LSTATUS v48; // eax
  void *v49; // rbx
  unsigned int v50; // ebx
  _QWORD *v51; // rdi
  LPVOID **v52; // rsi
  BYTE *lpData; // [rsp+30h] [rbp-69h]
  unsigned __int16 *v54; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v55[2]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD *v56; // [rsp+48h] [rbp-51h] BYREF
  __int64 v57; // [rsp+50h] [rbp-49h]
  __int64 v58; // [rsp+58h] [rbp-41h] BYREF
  __int64 v59; // [rsp+60h] [rbp-39h]
  __int64 *v60; // [rsp+68h] [rbp-31h]
  _QWORD v61[2]; // [rsp+70h] [rbp-29h] BYREF
  struct CProtocolsTable::PrEnumInfo *v62; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v63[2]; // [rsp+88h] [rbp-11h] BYREF
  _QWORD *v64; // [rsp+98h] [rbp-1h]
  int v65; // [rsp+A0h] [rbp+7h]
  HKEY hKey; // [rsp+A8h] [rbp+Fh] BYREF
  void *v67; // [rsp+B0h] [rbp+17h] BYREF
  struct CProtocolsTable::PrEnumInfo *v68; // [rsp+B8h] [rbp+1Fh]
  _OWORD *v69; // [rsp+108h] [rbp+6Fh] BYREF
  unsigned __int16 *v70; // [rsp+110h] [rbp+77h] BYREF
  unsigned __int16 *v71; // [rsp+118h] [rbp+7Fh] BYREF

  v58 = 0;
  v59 = 17;
  v60 = 0;
  v61[1] = v61;
  v61[0] = v61;
  Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary((__int64)&v58);
  v63[0] = &EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::`vftable';
  v63[1] = &v58;
  v64 = v61;
  v56 = 0;
  v57 = 0;
  v2 = 0;
  hKey = 0;
  LODWORD(v70) = 0;
  v67 = 0;
  v62 = 0;
  v3 = (*(__int64 (__fastcall **)(CProtocolsTable *, struct CProtocolsTable::PrEnumInfo **))(*(_QWORD *)this + 192LL))(
         this,
         &v62);
  if ( v3 < 0 )
  {
    Array<unsigned short *>::~Array<unsigned short *>((void **)&v56);
    EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>(v63);
    Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>((__int64)&v58);
    return (unsigned int)v3;
  }
  v5 = 0;
  v65 = 0;
  lpData = 0;
  v6 = 0;
  v68 = v62;
  while ( v62 )
  {
    v71 = 0;
    v8 = (*(__int64 (__fastcall **)(CProtocolsTable *, struct CProtocolsTable::PrEnumInfo **, unsigned __int16 **))(*(_QWORD *)this + 184LL))(
           this,
           &v62,
           &v71);
    LODWORD(v69) = v8;
    if ( v8 < 0 )
      goto LABEL_13;
    if ( (unsigned int)utIsValidProtseq(v71) )
    {
      ++v6;
      v69 = 0;
      if ( !(unsigned int)Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(&v58, &v71, &v69) )
      {
        v9 = CoTaskMemAlloc(0x10u);
        v10 = v9;
        if ( !v9 )
        {
          v8 = -2147024882;
          LODWORD(v69) = -2147024882;
LABEL_13:
          v15 = 0;
          goto LABEL_14;
        }
        *v9 = 0;
        v69 = v9;
        v11 = -1;
        do
          ++v11;
        while ( v71[v11] );
        v12 = v11 + 1;
        v13 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v11 + 1, 2u));
        v54 = v13;
        if ( !v13 )
        {
          CoTaskMemFree(v10);
          v8 = -2147024882;
          goto LABEL_21;
        }
        StringCchCopyW(v13, v12, v71);
        *(_QWORD *)v10 = v14;
        v10[2] = v6;
        v8 = Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::add(&v58, &v54, &v69);
        LODWORD(v69) = v8;
        if ( v8 < 0 )
          goto LABEL_13;
      }
    }
  }
  v16 = (CProtocolsTable *)((char *)this + 40);
  v8 = CSimpleDataTableCursor::InternalRestartWriteRow((CProtocolsTable *)((char *)this + 40));
  LODWORD(v69) = v8;
  while ( v8 >= 0 && !(unsigned int)CSimpleDataTableCursor::InternalMoveToNextWriteRow(v16, (unsigned int *)&v70) )
  {
    v54 = 0;
    if ( (_DWORD)v70 == 1 || (_DWORD)v70 == 2 )
    {
      v8 = CSimpleDataTableCursor::InternalGetWriteColumn(
             v16,
             0,
             v55,
             (unsigned int *)&v71,
             (unsigned int *)&v69,
             (void **)&v54);
      LODWORD(v69) = v8;
      if ( v8 >= 0 )
      {
        v8 = CSimpleDataTableCursor::InternalGetWriteColumn(
               v16,
               1u,
               v55,
               (unsigned int *)&v71,
               (unsigned int *)&v69,
               &v67);
        LODWORD(v69) = v8;
        if ( v8 >= 0 )
        {
          v18 = v54;
          if ( !(unsigned int)utIsValidProtseq(v54) )
          {
            v8 = -2146368510;
            goto LABEL_50;
          }
          v19 = *(_DWORD *)v67;
          LODWORD(v71) = *(_DWORD *)v67;
          *(_QWORD *)v55 = 0;
          if ( (unsigned int)Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(&v58, &v54, v55) )
          {
            v54 = *(unsigned __int16 **)(**(_QWORD **)v55 + 40LL);
            *((_DWORD *)v54 + 2) = v19;
          }
          else
          {
            v20 = (unsigned __int16 *)CoTaskMemAlloc(0x10u);
            v21 = v20;
            if ( !v20 )
            {
              v8 = -2147024882;
LABEL_50:
              LODWORD(v69) = v8;
              goto LABEL_13;
            }
            *(_OWORD *)v20 = 0;
            v54 = v20;
            v22 = -1;
            do
              ++v22;
            while ( v18[v22] );
            v23 = v22 + 1;
            v24 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v22 + 1, 2u));
            v25 = v24;
            *(_QWORD *)v55 = v24;
            if ( !v24 )
            {
              CoTaskMemFree(v21);
              v8 = -2147024882;
              LODWORD(v69) = -2147024882;
LABEL_48:
              v15 = lpData;
              goto LABEL_14;
            }
            v8 = StringCchCopyW(v24, v23, v18);
            LODWORD(v69) = v8;
            if ( v8 < 0 )
            {
              CoTaskMemFree(v21);
              CoTaskMemFree(v25);
              goto LABEL_22;
            }
            *(_QWORD *)v21 = v25;
            *((_DWORD *)v21 + 2) = (_DWORD)v71;
            Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::add(&v58, v55, &v54);
          }
        }
      }
    }
    else if ( (_DWORD)v70 == 3 )
    {
      v8 = CSimpleDataTableCursor::InternalGetWriteColumn(
             v16,
             0,
             v55,
             (unsigned int *)&v71,
             (unsigned int *)&v69,
             (void **)&v54);
      LODWORD(v69) = v8;
      if ( v8 >= 0 )
      {
        v71 = 0;
        if ( (unsigned int)Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(&v58, &v54, &v71) )
        {
          v17 = *(_QWORD *)v71;
          *(_QWORD *)v71 = *(_QWORD *)(*(_QWORD *)v71 + 16LL);
          Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc::clearPresent(v17);
          if ( !*(_DWORD *)(v17 + 24) )
          {
            Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::Assoc::`scalar deleting destructor'(
              (__int64 *)v17,
              0);
            *(_QWORD *)(v17 + 16) = v60;
            v60 = (__int64 *)v17;
          }
          --HIDWORD(v59);
        }
      }
    }
  }
  v26 = 0;
  EnumMap<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::reset(v63);
  if ( (unsigned int)EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::next(v63) )
  {
    do
    {
      v27 = v64[4];
      v28 = v64[5];
      v29 = Array<MyDataEntry *>::setSize(&v56, v2 + 1);
      v2 = v57;
      v30 = v56;
      if ( v29 >= 0 && (_DWORD)v57 )
        v56[(unsigned int)(v57 - 1)] = v28;
      v31 = -1;
      do
        ++v31;
      while ( *(_WORD *)(v27 + 2 * v31) );
      v26 += v31 + 1;
    }
    while ( (unsigned int)EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::next(v63) );
    v8 = (int)v69;
    v5 = v65;
  }
  else
  {
    v30 = v56;
  }
  v32 = v26 + 2;
  v33 = (__int64 *)v61[0];
  if ( (_QWORD *)v61[0] != v61 )
  {
    do
    {
      v34 = v33;
      v33 = (__int64 *)*v33;
      Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc::clearPresent(v34);
      if ( !*((_DWORD *)v34 + 6) )
      {
        Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::Assoc::`scalar deleting destructor'(v34, 0);
        v34[2] = (__int64)v60;
        v60 = v34;
      }
    }
    while ( v33 != v61 );
    v30 = v56;
  }
  v35 = v58;
  if ( v58 )
  {
    v36 = 0;
    if ( (_DWORD)v59 )
    {
      while ( 1 )
      {
        *(_QWORD *)(v35 + 8LL * v36++) = 0;
        if ( v36 >= (unsigned int)v59 )
          break;
        v35 = v58;
      }
    }
  }
  HIDWORD(v59) = 0;
  if ( v2 )
  {
    do
    {
      v37 = 0;
      LODWORD(v38) = 0;
      if ( v2 == 1 )
        break;
      do
      {
        v39 = 0;
        v40 = 0;
        if ( (unsigned int)v38 < v2 )
          v39 = &v30[(unsigned int)v38];
        v38 = (unsigned int)(v38 + 1);
        if ( (unsigned int)v38 < v2 )
          v40 = &v30[v38];
        v41 = *v40;
        if ( *(_DWORD *)(*v39 + 8LL) > *(_DWORD *)(*v40 + 8LL) )
        {
          *v40 = *v39;
          *v39 = v41;
          ++v37;
        }
      }
      while ( (unsigned int)v38 < v2 - 1 );
    }
    while ( v37 > 0 );
    v8 = (int)v69;
  }
  v42 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v32, 2u));
  v15 = v42;
  lpData = (BYTE *)v42;
  if ( !v42 )
  {
    v8 = -2147024882;
    goto LABEL_96;
  }
  v43 = v42;
  v70 = v42;
  v44 = (unsigned __int16 *)v32;
  v71 = (unsigned __int16 *)v32;
  memset_0(v42, 0, 2 * v32);
  v45 = 0;
  v7 = (CProtocolsTable *)v32;
  v46 = v43;
  while ( v45 < v2 )
  {
    v8 = StringCchCopyExW(
           v43,
           (unsigned __int64)v44,
           *(const unsigned __int16 **)v56[v45],
           &v70,
           (unsigned __int64 *)&v71,
           0);
    LODWORD(v69) = v8;
    v43 = v70 + 1;
    v70 = v43;
    v46 = v43;
    v44 = (unsigned __int16 *)((char *)v71 - 1);
    v71 = v44;
    v7 = (CProtocolsTable *)v44;
    if ( v8 < 0 )
      goto LABEL_48;
    ++v45;
  }
  if ( (unsigned __int64)v7 >= 2 )
  {
    *v43 = 0;
    v46[1] = 0;
    v47 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RPC", 0, 0x20006u, &hKey);
    v5 = v47;
    if ( v47 )
    {
      if ( v47 > 0 )
        v8 = (unsigned __int16)v47 | 0x80070000;
      else
        v8 = v47;
      goto LABEL_21;
    }
    v15 = lpData;
    v48 = RegSetValueExW(hKey, L"DCOM Protocols", 0, 7u, lpData, 2 * v32);
    v5 = v48;
    if ( !v48 )
      goto LABEL_14;
    if ( v48 <= 0 )
    {
      v8 = v48;
      LODWORD(v69) = v48;
      goto LABEL_14;
    }
    v8 = (unsigned __int16)v48 | 0x80070000;
LABEL_96:
    LODWORD(v69) = v8;
    goto LABEL_14;
  }
  v8 = -2147418113;
LABEL_21:
  LODWORD(v69) = v8;
LABEL_22:
  v15 = lpData;
LABEL_14:
  if ( v68 )
    CProtocolsTable::CleanupPrEnumInfo(v7, (LPVOID *)v68);
  if ( v8 >= 0 && v5 )
  {
    if ( v5 > 0 )
    {
      v8 = (unsigned __int16)v5 | 0x80070000;
      LODWORD(v69) = v8;
    }
    else
    {
      v8 = v5;
      LODWORD(v69) = v5;
    }
  }
  if ( v15 )
    CoTaskMemFree(v15);
  if ( hKey )
    RegCloseKey(hKey);
  EnumMap<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::reset(v63);
  while ( (unsigned int)EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::next(v63) )
  {
    v49 = (void *)v64[5];
    CoTaskMemFree((LPVOID)v64[4]);
    CoTaskMemFree(v49);
  }
  v50 = 0;
  if ( v2 )
  {
    v51 = v56;
    do
    {
      v52 = 0;
      if ( v50 < v2 )
        v52 = (LPVOID **)&v51[v50];
      CoTaskMemFree(**v52);
      CoTaskMemFree(*v52);
      ++v50;
    }
    while ( v50 < v2 );
    v8 = (int)v69;
  }
  Array<unsigned short *>::~Array<unsigned short *>((void **)&v56);
  EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~EnumMap<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>(v63);
  Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>((__int64)&v58);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039dc0  mov     [rsp-8+arg_0], rbx
0x180039dc5  push    rbp
0x180039dc6  push    rsi
0x180039dc7  push    rdi
0x180039dc8  push    r12
0x180039dca  push    r13
0x180039dcc  push    r14
0x180039dce  push    r15
0x180039dd0  lea     rbp, [rsp-27h]
0x180039dd5  sub     rsp, 0C0h
0x180039ddc  mov     rsi, rcx
0x180039ddf  xor     ebx, ebx
0x180039de1  mov     [rbp+57h+var_98], rbx
0x180039de5  mov     [rbp+57h+var_90], 11h
0x180039ded  mov     [rbp+57h+var_88], rbx
0x180039df1  lea     rax, [rbp+57h+var_80]
0x180039df5  mov     [rbp+57h+var_78], rax
0x180039df9  lea     rax, [rbp+57h+var_80]
0x180039dfd  mov     [rbp+57h+var_80], rax
0x180039e01  lea     rcx, [rbp+57h+var_98]
0x180039e05  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x180039e0a  nop
0x180039e0b  lea     rax, ??_7?$EnumMap@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@6B@; const EnumMap<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::`vftable'
0x180039e12  mov     [rbp+57h+var_68], rax
0x180039e16  lea     rax, [rbp+57h+var_98]
0x180039e1a  mov     [rbp+57h+var_60], rax
0x180039e1e  lea     rax, [rbp+57h+var_80]
0x180039e22  mov     [rbp+57h+var_58], rax
0x180039e26  mov     [rbp+57h+var_A8], rbx
0x180039e2a  xor     r12d, r12d
0x180039e2d  mov     [rbp+57h+var_A0], r12
0x180039e31  mov     r13d, r12d
0x180039e34  mov     [rbp+57h+hKey], r12
0x180039e38  mov     dword ptr [rbp+57h+arg_10], r12d
0x180039e3c  mov     [rbp+57h+var_40], r12
0x180039e40  mov     [rbp+57h+var_70], r12
0x180039e44  mov     rax, [rsi]
0x180039e47  lea     rdx, [rbp+57h+var_70]
0x180039e4b  mov     rcx, rsi
0x180039e4e  mov     rax, [rax+0C0h]
0x180039e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e5a  mov     ebx, eax
0x180039e5c  test    eax, eax
0x180039e5e  jns     short loc_180039E84
0x180039e60  lea     rcx, [rbp+57h+var_A8]
0x180039e64  call    ??1?$Array@PEAG@@QEAA@XZ; Array<ushort *>::~Array<ushort *>(void)
0x180039e69  nop
0x180039e6a  lea     rcx, [rbp+57h+var_68]
0x180039e6e  call    ??1?$EnumMap@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@QEAA@XZ; EnumMap<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~EnumMap<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>(void)
0x180039e73  nop
0x180039e74  lea     rcx, [rbp+57h+var_98]
0x180039e78  call    ??1?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@QEAA@XZ; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>(void)
0x180039e7d  mov     eax, ebx
0x180039e7f  jmp     loc_18003A5B3
0x180039e84  mov     ebx, r12d
0x180039e87  mov     [rbp+57h+var_50], ebx
0x180039e8a  mov     [rbp+57h+lpData], r12
0x180039e8e  mov     r14d, r12d
0x180039e91  mov     rax, [rbp+57h+var_70]
0x180039e95  mov     [rbp+57h+var_38], rax
0x180039e99  or      r15, 0FFFFFFFFFFFFFFFFh
0x180039e9d  cmp     [rbp+57h+var_70], r12
0x180039ea1  jz      loc_180039FE1
0x180039ea7  mov     [rbp+57h+arg_18], r12
0x180039eab  mov     rax, [rsi]
0x180039eae  lea     r8, [rbp+57h+arg_18]
0x180039eb2  lea     rdx, [rbp+57h+var_70]
0x180039eb6  mov     rcx, rsi
0x180039eb9  mov     rax, [rax+0B8h]
0x180039ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ec5  mov     edi, eax
0x180039ec7  mov     dword ptr [rbp+57h+arg_8], eax
0x180039eca  test    eax, eax
0x180039ecc  js      loc_180039F8B
0x180039ed2  mov     rcx, [rbp+57h+arg_18]; unsigned __int16 *
0x180039ed6  call    ?utIsValidProtseq@@YAHPEBG@Z; utIsValidProtseq(ushort const *)
0x180039edb  test    eax, eax
0x180039edd  jz      short loc_180039E9D
0x180039edf  inc     r14d
0x180039ee2  mov     [rbp+57h+arg_8], r12
0x180039ee6  lea     r8, [rbp+57h+arg_8]
0x180039eea  lea     rdx, [rbp+57h+arg_18]
0x180039eee  lea     rcx, [rbp+57h+var_98]
0x180039ef2  call    ?find@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(ushort const * const &,Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc * * *)
0x180039ef7  test    eax, eax
0x180039ef9  jnz     short loc_180039E9D
0x180039efb  lea     ecx, [rax+10h]; cb
0x180039efe  call    cs:__imp_CoTaskMemAlloc
0x180039f04  mov     rdi, rax
0x180039f07  test    rax, rax
0x180039f0a  jz      loc_180039FD7
0x180039f10  xorps   xmm0, xmm0
0x180039f13  movups  xmmword ptr [rax], xmm0
0x180039f16  mov     [rbp+57h+arg_8], rax
0x180039f1a  mov     rcx, [rbp+57h+arg_18]
0x180039f1e  mov     rax, r15
0x180039f21  inc     rax
0x180039f24  cmp     [rcx+rax*2], r12w
0x180039f29  jnz     short loc_180039F21
0x180039f2b  lea     r15, [rax+1]
0x180039f2f  mov     eax, 2
0x180039f34  mul     r15
0x180039f37  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180039f3e  cmovb   rax, rcx
0x180039f42  mov     rcx, rax; cb
0x180039f45  call    cs:__imp_CoTaskMemAlloc
0x180039f4b  mov     r10, rax
0x180039f4e  mov     [rbp+57h+var_B8], rax
0x180039f52  test    rax, rax
0x180039f55  jz      short loc_180039FBF
0x180039f57  mov     r8, [rbp+57h+arg_18]; unsigned __int16 *
0x180039f5b  mov     rdx, r15; unsigned __int64
0x180039f5e  mov     rcx, rax; unsigned __int16 *
0x180039f61  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039f66  mov     [rdi], r10
0x180039f69  mov     [rdi+8], r14d
0x180039f6d  lea     r8, [rbp+57h+arg_8]
0x180039f71  lea     rdx, [rbp+57h+var_B8]
0x180039f75  lea     rcx, [rbp+57h+var_98]
0x180039f79  call    ?add@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@QEAAJAEBQEBGAEBQEAUMyDataEntry@@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::add(ushort const * const &,MyDataEntry * const &)
0x180039f7e  mov     edi, eax
0x180039f80  mov     dword ptr [rbp+57h+arg_8], eax
0x180039f83  test    eax, eax
0x180039f85  jns     loc_180039E99
0x180039f8b  mov     rsi, rbx
0x180039f8e  mov     rax, [rbp+57h+var_38]
0x180039f92  test    rax, rax
0x180039f95  jz      short loc_180039F9F
0x180039f97  mov     rdx, rax; struct CProtocolsTable::PrEnumInfo *
0x180039f9a  call    ?CleanupPrEnumInfo@CProtocolsTable@@AEAAXPEAUPrEnumInfo@1@@Z; CProtocolsTable::CleanupPrEnumInfo(CProtocolsTable::PrEnumInfo *)
0x180039f9f  test    edi, edi
0x180039fa1  js      loc_18003A506
0x180039fa7  test    ebx, ebx
0x180039fa9  jz      loc_18003A506
0x180039faf  jg      loc_18003A4FA
0x180039fb5  mov     edi, ebx
0x180039fb7  mov     dword ptr [rbp+57h+arg_8], ebx
0x180039fba  jmp     loc_18003A506
0x180039fbf  mov     rcx, rdi; pv
0x180039fc2  call    cs:__imp_CoTaskMemFree
0x180039fc8  nop
0x180039fc9  mov     edi, 8007000Eh
0x180039fce  mov     dword ptr [rbp+57h+arg_8], edi
0x180039fd1  mov     rsi, [rbp+57h+lpData]
0x180039fd5  jmp     short loc_180039F8E
0x180039fd7  mov     edi, 8007000Eh
0x180039fdc  mov     dword ptr [rbp+57h+arg_8], edi
0x180039fdf  jmp     short loc_180039F8B
0x180039fe1  lea     r15, [rsi+28h]
0x180039fe5  mov     rcx, r15; this
0x180039fe8  call    ?InternalRestartWriteRow@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InternalRestartWriteRow(void)
0x180039fed  mov     edi, eax
0x180039fef  mov     dword ptr [rbp+57h+arg_8], eax
0x180039ff2  test    edi, edi
0x180039ff4  js      loc_18003A245
0x180039ffa  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x180039ffe  mov     rcx, r15; this
0x18003a001  call    ?InternalMoveToNextWriteRow@CSimpleDataTableCursor@@QEAAJPEAK@Z; CSimpleDataTableCursor::InternalMoveToNextWriteRow(ulong *)
0x18003a006  test    eax, eax
0x18003a008  jnz     loc_18003A245
0x18003a00e  mov     [rbp+57h+var_B8], r12
0x18003a012  mov     eax, dword ptr [rbp+57h+arg_10]
0x18003a015  sub     eax, 1
0x18003a018  jz      loc_18003A0AF
0x18003a01e  sub     eax, 1
0x18003a021  jz      loc_18003A0AF
0x18003a027  cmp     eax, 1
0x18003a02a  jnz     short loc_180039FF2
0x18003a02c  lea     rax, [rbp+57h+var_B8]
0x18003a030  mov     qword ptr [rsp+0F0h+cbData], rax; void **
0x18003a035  lea     rax, [rbp+57h+arg_8]
0x18003a039  mov     [rsp+0F0h+phkResult], rax; unsigned int *
0x18003a03e  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18003a042  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x18003a046  xor     edx, edx; unsigned int
0x18003a048  mov     rcx, r15; this
0x18003a04b  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x18003a050  mov     edi, eax
0x18003a052  mov     dword ptr [rbp+57h+arg_8], eax
0x18003a055  test    eax, eax
0x18003a057  js      short loc_180039FF2
0x18003a059  mov     [rbp+57h+arg_18], r12
0x18003a05d  lea     r8, [rbp+57h+arg_18]
0x18003a061  lea     rdx, [rbp+57h+var_B8]
0x18003a065  lea     rcx, [rbp+57h+var_98]
0x18003a069  call    ?find@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(ushort const * const &,Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc * * *)
0x18003a06e  test    eax, eax
0x18003a070  jz      short loc_180039FF2
0x18003a072  mov     rcx, [rbp+57h+arg_18]
0x18003a076  mov     rsi, [rcx]
0x18003a079  mov     rax, [rsi+10h]
0x18003a07d  mov     [rcx], rax
0x18003a080  mov     rcx, rsi
0x18003a083  call    ?clearPresent@Assoc@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEAAXXZ; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc::clearPresent(void)
0x18003a088  mov     r10d, [rsi+18h]
0x18003a08c  test    r10d, r10d
0x18003a08f  jnz     short loc_18003A0A7
0x18003a091  xor     edx, edx
0x18003a093  mov     rcx, rsi
0x18003a096  call    ??_GAssoc@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@QEAAPEAXI@Z; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::Assoc::`scalar deleting destructor'(uint)
0x18003a09b  mov     rax, [rbp+57h+var_88]
0x18003a09f  mov     [rsi+10h], rax
0x18003a0a3  mov     [rbp+57h+var_88], rsi
0x18003a0a7  dec     dword ptr [rbp+57h+var_90+4]
0x18003a0aa  jmp     loc_180039FF2
0x18003a0af  lea     rax, [rbp+57h+var_B8]
0x18003a0b3  mov     qword ptr [rsp+0F0h+cbData], rax; void **
0x18003a0b8  lea     rax, [rbp+57h+arg_8]
0x18003a0bc  mov     [rsp+0F0h+phkResult], rax; unsigned int *
0x18003a0c1  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18003a0c5  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x18003a0c9  xor     edx, edx; unsigned int
0x18003a0cb  mov     rcx, r15; this
0x18003a0ce  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x18003a0d3  mov     edi, eax
0x18003a0d5  mov     dword ptr [rbp+57h+arg_8], eax
0x18003a0d8  test    eax, eax
0x18003a0da  js      loc_180039FF2
0x18003a0e0  lea     rax, [rbp+57h+var_40]
0x18003a0e4  mov     qword ptr [rsp+0F0h+cbData], rax; void **
0x18003a0e9  lea     rax, [rbp+57h+arg_8]
0x18003a0ed  mov     [rsp+0F0h+phkResult], rax; unsigned int *
0x18003a0f2  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18003a0f6  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x18003a0fa  mov     edx, 1; unsigned int
0x18003a0ff  mov     rcx, r15; this
0x18003a102  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x18003a107  mov     edi, eax
0x18003a109  mov     dword ptr [rbp+57h+arg_8], eax
0x18003a10c  test    eax, eax
0x18003a10e  js      loc_180039FF2
0x18003a114  mov     r12, [rbp+57h+var_B8]
0x18003a118  mov     rcx, r12; unsigned __int16 *
0x18003a11b  call    ?utIsValidProtseq@@YAHPEBG@Z; utIsValidProtseq(ushort const *)
0x18003a120  xor     r14d, r14d
0x18003a123  test    eax, eax
0x18003a125  jz      loc_18003A23E
0x18003a12b  mov     rax, [rbp+57h+var_40]
0x18003a12f  mov     esi, [rax]
0x18003a131  mov     dword ptr [rbp+57h+arg_18], esi
0x18003a134  mov     qword ptr [rbp+57h+var_B0], r14
0x18003a138  lea     r8, [rbp+57h+var_B0]
0x18003a13c  lea     rdx, [rbp+57h+var_B8]
0x18003a140  lea     rcx, [rbp+57h+var_98]
0x18003a144  call    ?find@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::find(ushort const * const &,Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::Assoc * * *)
0x18003a149  test    eax, eax
0x18003a14b  jz      short loc_18003A167
0x18003a14d  mov     rax, qword ptr [rbp+57h+var_B0]
0x18003a151  mov     rcx, [rax]
0x18003a154  mov     rax, [rcx+28h]
0x18003a158  mov     [rbp+57h+var_B8], rax
0x18003a15c  mov     [rax+8], esi
0x18003a15f  xor     r12d, r12d
0x18003a162  jmp     loc_180039FF2
0x18003a167  mov     ecx, 10h; cb
0x18003a16c  call    cs:__imp_CoTaskMemAlloc
0x18003a172  mov     rsi, rax
0x18003a175  test    rax, rax
0x18003a178  jz      loc_18003A22E
0x18003a17e  xorps   xmm0, xmm0
0x18003a181  movups  xmmword ptr [rax], xmm0
0x18003a184  mov     [rbp+57h+var_B8], rax
0x18003a188  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a18c  mov     rax, rcx
0x18003a18f  inc     rax
0x18003a192  cmp     [r12+rax*2], r14w
0x18003a197  jnz     short loc_18003A18F
0x18003a199  lea     rdi, [rax+1]
0x18003a19d  mov     eax, 2
0x18003a1a2  mul     rdi
0x18003a1a5  cmovb   rax, rcx
0x18003a1a9  mov     rcx, rax; cb
0x18003a1ac  call    cs:__imp_CoTaskMemAlloc
0x18003a1b2  mov     r14, rax
0x18003a1b5  mov     qword ptr [rbp+57h+var_B0], rax
0x18003a1b9  test    rax, rax
0x18003a1bc  jz      short loc_18003A210
0x18003a1be  mov     r8, r12; unsigned __int16 *
0x18003a1c1  mov     rdx, rdi; unsigned __int64
0x18003a1c4  mov     rcx, rax; unsigned __int16 *
0x18003a1c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a1cc  mov     edi, eax
0x18003a1ce  mov     dword ptr [rbp+57h+arg_8], eax
0x18003a1d1  xor     r12d, r12d
0x18003a1d4  test    eax, eax
0x18003a1d6  js      short loc_18003A1F7
0x18003a1d8  mov     [rsi], r14
0x18003a1db  mov     eax, dword ptr [rbp+57h+arg_18]
0x18003a1de  mov     [rsi+8], eax
0x18003a1e1  lea     r8, [rbp+57h+var_B8]
0x18003a1e5  lea     rdx, [rbp+57h+var_B0]
0x18003a1e9  lea     rcx, [rbp+57h+var_98]
0x18003a1ed  call    ?add@?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@QEAAJAEBQEBGAEBQEAUMyDataEntry@@@Z; Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::add(ushort const * const &,MyDataEntry * const &)
0x18003a1f2  jmp     loc_180039FF2
0x18003a1f7  mov     rcx, rsi; pv
0x18003a1fa  call    cs:__imp_CoTaskMemFree
0x18003a200  nop
0x18003a201  mov     rcx, r14; pv
0x18003a204  call    cs:__imp_CoTaskMemFree
0x18003a20a  nop
  ... truncated ...
```
