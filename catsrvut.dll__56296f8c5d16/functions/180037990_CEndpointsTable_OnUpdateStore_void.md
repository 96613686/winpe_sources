# CEndpointsTable::OnUpdateStore(void)

- ea: `0x180037990`
- end: `0x180038127`
- name: `?OnUpdateStore@CEndpointsTable@@UEAAJXZ`
- size: `1943`
- prototype: `__int64 __fastcall(CEndpointsTable *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001e60`
- `0x180003fd0`
- `0x1800065f0`
- `0x180006770`
- `0x180006980`
- `0x180007328`
- `0x180014ec8`
- `0x180014f58`
- `0x180023834`
- `0x180023aa8`
- `0x1800351c0`
- `0x1800351e0`
- `0x1800370bc`
- `0x180037990`
- `0x180039660`
- `0x180053e18`
- `0x180053f3c`
- `0x180054424`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037fba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003805f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003808e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037fba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003805f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003808e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800380ce`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180037f4a`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180037f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037c65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037ebc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037c65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037ebc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037ffb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037ffb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038029`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038029`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800380de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800380de`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CEndpointsTable::OnUpdateStore(CEndpointsTable *this)
{
  __int64 v2; // rdi
  unsigned int v3; // esi
  int updated; // ebx
  BYTE *v5; // r13
  unsigned int v6; // r15d
  unsigned int v7; // r14d
  CSimpleDataTableCursor *v8; // r12
  _DWORD *v9; // r14
  __int64 v10; // rax
  _DWORD *v11; // rdi
  _OWORD *v12; // rax
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // r13
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rdx
  unsigned int v18; // edi
  __int64 v19; // r14
  int v20; // eax
  __int64 v21; // r15
  _DWORD *v22; // rbx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rax
  _QWORD *v26; // rdi
  _QWORD *v27; // rbx
  signed __int32 v28; // ett
  __int64 v29; // rdx
  unsigned int v30; // ecx
  unsigned __int64 v31; // r14
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rcx
  unsigned __int64 v34; // rdx
  unsigned int i; // edi
  unsigned int v36; // r10d
  LSTATUS v37; // r15d
  unsigned int j; // edi
  LPVOID *v39; // rax
  LPVOID *v40; // rdi
  unsigned int v42; // [rsp+54h] [rbp-ACh]
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v45; // [rsp+64h] [rbp-9Ch]
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  void *v47; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v48; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v49; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 *v50; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v51; // [rsp+88h] [rbp-78h] BYREF
  __int64 v52; // [rsp+90h] [rbp-70h]
  void *v53; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v54; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h]
  _QWORD *v57; // [rsp+B8h] [rbp-48h]
  _QWORD v58[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-30h]
  HKEY hKey; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v61[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v62; // [rsp+F0h] [rbp-10h]
  IID rclsid; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  v55 = 0;
  v56 = 17;
  v57 = 0;
  v58[1] = v58;
  v58[0] = v58;
  Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary((__int64)&v55);
  v51 = 0;
  v52 = 0;
  v3 = 0;
  v61[0] = &EnumMap<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::`vftable';
  v61[1] = &v55;
  v62 = v58;
  hKey = 0;
  dwDisposition = 0;
  v53 = 0;
  v54 = 0;
  rclsid = 0;
  if ( *((_DWORD *)this + 37) )
  {
    updated = CCustomDataTable::UpdateStore(this);
    goto LABEL_110;
  }
  v5 = 0;
  lpsz = 0;
  v6 = 0;
  v42 = 0;
  v7 = 0;
  v45 = 0;
  v8 = (CEndpointsTable *)((char *)this + 40);
  updated = CSimpleDataTableCursor::InternalRestartWriteRow((CEndpointsTable *)((char *)this + 40));
  if ( updated < 0 )
    goto LABEL_88;
  while ( 1 )
  {
    updated = CSimpleDataTableCursor::InternalMoveToNextWriteRow(v8, &dwDisposition);
    if ( updated )
      break;
    v50 = 0;
    v47 = 0;
    v59 = ++v2;
    if ( dwDisposition == 1 || dwDisposition == 2 )
    {
      updated = CSimpleDataTableCursor::InternalGetWriteColumn(v8, 0, &v44, &v49, &v48, &v53);
      if ( updated < 0 )
        goto LABEL_44;
      v9 = v53;
      if ( !v53 )
      {
LABEL_43:
        updated = -2147418113;
LABEL_44:
        v5 = 0;
LABEL_88:
        v37 = 0;
        goto LABEL_89;
      }
      updated = CSimpleDataTableCursor::InternalGetWriteColumn(v8, 1u, &v44, &v49, &v48, (void **)&v50);
      if ( updated < 0 )
        goto LABEL_44;
      updated = CSimpleDataTableCursor::InternalGetWriteColumn(v8, 3u, &v44, &v49, &v48, (void **)&v54);
      if ( updated < 0 )
        goto LABEL_44;
      updated = CSimpleDataTableCursor::InternalGetWriteColumn(v8, 2u, &v44, &v49, &v48, &v47);
      if ( updated < 0 )
        goto LABEL_44;
      if ( v2 == 1 )
      {
        rclsid = *(IID *)v47;
      }
      else
      {
        v10 = *(_QWORD *)&rclsid.Data1 - *(_QWORD *)v47;
        if ( *(_QWORD *)&rclsid.Data1 == *(_QWORD *)v47 )
          v10 = *(_QWORD *)rclsid.Data4 - *((_QWORD *)v47 + 1);
        if ( v10 )
          goto LABEL_43;
      }
      v47 = 0;
      if ( (unsigned int)Map<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::find(&v55, v9, &v47) )
      {
        v44 = 0;
        v11 = *(_DWORD **)(*(_QWORD *)v47 + 32LL);
      }
      else
      {
        v12 = CoTaskMemAlloc(0x10u);
        v11 = v12;
        if ( v12 )
          *v12 = 0;
        else
          v11 = 0;
        *(_OWORD *)v11 = 0;
        if ( !v11 )
          updated = -2147024882;
        v42 = v6 + 1;
        v44 = 1;
      }
      v47 = v11;
      if ( v11 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v50[v13] );
        v14 = v13 + 1;
        v15 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v14, 2u));
        updated = StringCchCopyW(v15, v14, v50);
        if ( updated < 0 )
        {
          CoTaskMemFree(v15);
          if ( !*(_QWORD *)v11 )
            CoTaskMemFree(v11);
          v5 = (BYTE *)lpsz;
          goto LABEL_88;
        }
        if ( *(_QWORD *)v11 )
          CoTaskMemFree(*(LPVOID *)v11);
        *(_QWORD *)v11 = v15;
        v11[2] = *v9;
        v16 = v54;
        v11[3] = *(_DWORD *)v54;
        if ( v44
          && (int)Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary((__int64)&v55) >= 0 )
        {
          v50 = 0;
          if ( (unsigned int)Map<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::find(&v55, v9, &v50) )
          {
            v17 = v50;
            *(_DWORD *)(*(_QWORD *)v50 + 28LL) = *v9;
            *(_QWORD *)(*(_QWORD *)v17 + 32LL) = v11;
          }
          else
          {
            Map<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::newAssoc(&v55, v9, &v47, v50);
          }
        }
        v7 = v45;
        v2 = v59;
        v6 = v42;
        if ( v45 < *(_DWORD *)v16 )
        {
          v7 = *(_DWORD *)v16;
          v45 = *(_DWORD *)v16;
        }
      }
      else
      {
        v7 = v45;
        v6 = v42;
        if ( updated < 0 )
          break;
        v2 = v59;
      }
    }
  }
  v5 = 0;
  if ( updated < 0 )
    goto LABEL_88;
  EnumMap<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::reset(v61);
  updated = Array<MyDataEntry *>::setSize(&v51, v6);
  if ( updated < 0 )
  {
    v3 = v52;
    goto LABEL_88;
  }
  v18 = v7 + 1;
  v19 = 0;
  v20 = EnumMap<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::next(v61);
  v3 = v52;
  v21 = -1;
  while ( v20 )
  {
    v22 = (_DWORD *)v62[4];
    if ( !v22 )
      goto LABEL_61;
    if ( v22[3] < v42 && v42 == v18 )
    {
      if ( v22[3] >= v3 )
        goto LABEL_58;
      v23 = (unsigned int)v22[3];
    }
    else
    {
      v24 = Array<MyDataEntry *>::setSize(&v51, v3 + 1);
      v3 = v52;
      if ( v24 < 0 || !(_DWORD)v52 )
        goto LABEL_58;
      v23 = (unsigned int)(v52 - 1);
    }
    v51[v23] = *(_QWORD *)v22;
LABEL_58:
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*(_QWORD *)v22 + 2 * v25) );
    v19 += v25 + 1;
    *(_QWORD *)v22 = 0;
    CoTaskMemFree(v22);
LABEL_61:
    v20 = EnumMap<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::next(v61);
  }
  v26 = (_QWORD *)v58[0];
  while ( v26 != v58 )
  {
    v27 = v26;
    v26 = (_QWORD *)*v26;
    do
      v28 = *((_DWORD *)v27 + 6);
    while ( v28 != _InterlockedCompareExchange((volatile signed __int32 *)v27 + 6, v28 & 0x7FFFFFFF, v28) );
    if ( !*((_DWORD *)v27 + 6) )
    {
      Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::Assoc::`scalar deleting destructor'(v27, 0);
      v27[2] = v57;
      v57 = v27;
    }
  }
  v29 = v55;
  if ( v55 )
  {
    v30 = 0;
    if ( (_DWORD)v56 )
    {
      while ( 1 )
      {
        *(_QWORD *)(v29 + 8LL * v30++) = 0;
        if ( v30 >= (unsigned int)v56 )
          break;
        v29 = v55;
      }
    }
  }
  HIDWORD(v56) = 0;
  v31 = v19 + 2;
  updated = -2147024882;
  v32 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v31, 2u));
  v5 = (BYTE *)v32;
  if ( !v32 )
    goto LABEL_88;
  v33 = v32;
  v54 = v32;
  v34 = v31;
  v53 = (void *)v31;
  for ( i = 0; i < v42; ++i )
  {
    if ( i >= v3 )
      goto LABEL_78;
    updated = StringCchCopyExW(v33, v34, (const unsigned __int16 *)v51[i], &v54, (unsigned __int64 *)&v53, 0);
    if ( updated < 0 )
      goto LABEL_88;
    v33 = v54;
    v34 = (unsigned __int64)v53;
  }
  if ( v34 < 3 )
  {
LABEL_78:
    updated = -2147418113;
    goto LABEL_88;
  }
  *(_DWORD *)(v33 + 1) = 0;
  lpsz = 0;
  updated = StringFromIID(&rclsid, &lpsz);
  if ( updated < 0 )
    goto LABEL_88;
  do
    ++v21;
  while ( lpsz[v21] );
  if ( !v21 )
    goto LABEL_88;
  updated = StringCchCopyW(SubKey, 0x104u, L"Software\\Classes\\AppID\\");
  if ( updated < 0 )
    goto LABEL_88;
  updated = StringCchCatW(SubKey, v36, lpsz);
  if ( updated < 0 )
    goto LABEL_88;
  CoTaskMemFree(lpsz);
  dwDisposition = 0;
  v37 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( !v37 )
    v37 = RegSetValueExW(hKey, L"Endpoints", 0, 7u, v5, 2 * v31);
LABEL_89:
  for ( j = 0; j < v3; ++j )
  {
    v39 = 0;
    if ( j < v3 )
      v39 = (LPVOID *)&v51[j];
    if ( *v39 )
      CoTaskMemFree(*v39);
  }
  EnumMap<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::reset(v61);
  while ( (unsigned int)EnumMap<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::next(v61) )
  {
    v40 = (LPVOID *)v62[4];
    if ( v40 )
    {
      if ( *v40 )
        CoTaskMemFree(*v40);
      CoTaskMemFree(v40);
    }
  }
  if ( updated >= 0 && v37 )
  {
    if ( v37 > 0 )
      updated = (unsigned __int16)v37 | 0x80070000;
    else
      updated = v37;
  }
  if ( v5 )
    CoTaskMemFree(v5);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_110:
  EnumMap<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>::~EnumMap<unsigned long,MyDataEntry *,HashULONG,EmptyMapBase>(v61);
  Array<unsigned short *>::~Array<unsigned short *>((void **)&v51);
  Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>((__int64)&v55);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180037990  push    rbp
0x180037992  push    rbx
0x180037993  push    rsi
0x180037994  push    rdi
0x180037995  push    r12
0x180037997  push    r13
0x180037999  push    r14
0x18003799b  push    r15
0x18003799d  lea     rbp, [rsp-238h]
0x1800379a5  sub     rsp, 338h
0x1800379ac  mov     rax, cs:__security_cookie
0x1800379b3  xor     rax, rsp
0x1800379b6  mov     [rbp+270h+var_50], rax
0x1800379bd  mov     rbx, rcx
0x1800379c0  xor     edi, edi
0x1800379c2  mov     [rbp+270h+var_2C8], rdi
0x1800379c6  mov     [rbp+270h+var_2C0], 11h
0x1800379ce  mov     [rbp+270h+var_2B8], rdi
0x1800379d2  lea     rax, [rbp+270h+var_2B0]
0x1800379d6  mov     [rbp+270h+var_2A8], rax
0x1800379da  lea     rax, [rbp+270h+var_2B0]
0x1800379de  mov     [rbp+270h+var_2B0], rax
0x1800379e2  lea     rcx, [rbp+270h+var_2C8]
0x1800379e6  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x1800379eb  nop
0x1800379ec  mov     [rbp+270h+var_2E8], rdi
0x1800379f0  mov     [rbp+270h+var_2E0], rdi
0x1800379f4  mov     esi, edi
0x1800379f6  lea     rax, ??_7?$EnumMap@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@6B@; const EnumMap<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::`vftable'
0x1800379fd  mov     [rbp+270h+var_290], rax
0x180037a01  lea     rax, [rbp+270h+var_2C8]
0x180037a05  mov     [rbp+270h+var_288], rax
0x180037a09  lea     rax, [rbp+270h+var_2B0]
0x180037a0d  mov     [rbp+270h+var_280], rax
0x180037a11  mov     [rbp+270h+hKey], rdi
0x180037a15  mov     [rsp+370h+dwDisposition], edi
0x180037a19  mov     [rbp+270h+var_2D8], rdi
0x180037a1d  mov     [rbp+270h+var_2D0], rdi
0x180037a21  xorps   xmm0, xmm0
0x180037a24  movups  xmmword ptr [rbp+270h+rclsid.Data1], xmm0
0x180037a28  cmp     [rbx+94h], edi
0x180037a2e  jz      short loc_180037A3F
0x180037a30  mov     rcx, rbx; this
0x180037a33  call    ?UpdateStore@CCustomDataTable@@UEAAJXZ; CCustomDataTable::UpdateStore(void)
0x180037a38  mov     ebx, eax
0x180037a3a  jmp     loc_1800380E5
0x180037a3f  mov     [rsp+370h+var_320], edi
0x180037a43  mov     r13, rdi
0x180037a46  mov     [rsp+370h+lpsz], rdi
0x180037a4b  mov     r15d, edi
0x180037a4e  mov     [rsp+370h+var_31C], edi
0x180037a52  mov     r14d, edi
0x180037a55  mov     [rsp+370h+var_30C], edi
0x180037a59  lea     r12, [rbx+28h]
0x180037a5d  mov     rcx, r12; this
0x180037a60  call    ?InternalRestartWriteRow@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InternalRestartWriteRow(void)
0x180037a65  mov     ebx, eax
0x180037a67  xor     edx, edx
0x180037a69  test    eax, eax
0x180037a6b  js      loc_18003803B
0x180037a71  or      r13, 0FFFFFFFFFFFFFFFFh
0x180037a75  lea     rdx, [rsp+370h+dwDisposition]; unsigned int *
0x180037a7a  mov     rcx, r12; this
0x180037a7d  call    ?InternalMoveToNextWriteRow@CSimpleDataTableCursor@@QEAAJPEAK@Z; CSimpleDataTableCursor::InternalMoveToNextWriteRow(ulong *)
0x180037a82  mov     ebx, eax
0x180037a84  xor     eax, eax
0x180037a86  test    ebx, ebx
0x180037a88  jnz     loc_180037D78
0x180037a8e  mov     [rbp+270h+var_2F0], rax
0x180037a92  mov     [rsp+370h+var_300], rax
0x180037a97  inc     rdi
0x180037a9a  mov     [rbp+270h+var_2A0], rdi
0x180037a9e  mov     eax, [rsp+370h+dwDisposition]
0x180037aa2  sub     eax, 1
0x180037aa5  jz      short loc_180037AAC
0x180037aa7  cmp     eax, 1
0x180037aaa  jnz     short loc_180037A75
0x180037aac  lea     rax, [rbp+270h+var_2D8]
0x180037ab0  mov     qword ptr [rsp+370h+samDesired], rax; void **
0x180037ab5  lea     rax, [rsp+370h+var_2F8]
0x180037aba  mov     qword ptr [rsp+370h+dwOptions], rax; unsigned int *
0x180037abf  lea     r9, [rsp+370h+var_2F4]; unsigned int *
0x180037ac4  lea     r8, [rsp+370h+var_310]; unsigned int *
0x180037ac9  xor     edx, edx; unsigned int
0x180037acb  mov     rcx, r12; this
0x180037ace  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x180037ad3  mov     ebx, eax
0x180037ad5  xor     edx, edx
0x180037ad7  test    eax, eax
0x180037ad9  js      loc_180037D70
0x180037adf  mov     r14, [rbp+270h+var_2D8]
0x180037ae3  test    r14, r14
0x180037ae6  jz      loc_180037D6B
0x180037aec  lea     rax, [rbp+270h+var_2F0]
0x180037af0  mov     qword ptr [rsp+370h+samDesired], rax; void **
0x180037af5  lea     rax, [rsp+370h+var_2F8]
0x180037afa  mov     qword ptr [rsp+370h+dwOptions], rax; unsigned int *
0x180037aff  lea     r9, [rsp+370h+var_2F4]; unsigned int *
0x180037b04  lea     r8, [rsp+370h+var_310]; unsigned int *
0x180037b09  mov     edx, 1; unsigned int
0x180037b0e  mov     rcx, r12; this
0x180037b11  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x180037b16  mov     ebx, eax
0x180037b18  xor     edx, edx
0x180037b1a  test    eax, eax
0x180037b1c  js      loc_180037D70
0x180037b22  lea     rax, [rbp+270h+var_2D0]
0x180037b26  mov     qword ptr [rsp+370h+samDesired], rax; void **
0x180037b2b  lea     rax, [rsp+370h+var_2F8]
0x180037b30  mov     qword ptr [rsp+370h+dwOptions], rax; unsigned int *
0x180037b35  lea     r9, [rsp+370h+var_2F4]; unsigned int *
0x180037b3a  lea     r8, [rsp+370h+var_310]; unsigned int *
0x180037b3f  mov     edx, 3; unsigned int
0x180037b44  mov     rcx, r12; this
0x180037b47  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x180037b4c  mov     ebx, eax
0x180037b4e  xor     edx, edx
0x180037b50  test    eax, eax
0x180037b52  js      loc_180037D70
0x180037b58  lea     rax, [rsp+370h+var_300]
0x180037b5d  mov     qword ptr [rsp+370h+samDesired], rax; void **
0x180037b62  lea     rax, [rsp+370h+var_2F8]
0x180037b67  mov     qword ptr [rsp+370h+dwOptions], rax; unsigned int *
0x180037b6c  lea     r9, [rsp+370h+var_2F4]; unsigned int *
0x180037b71  lea     r8, [rsp+370h+var_310]; unsigned int *
0x180037b76  mov     edx, 2; unsigned int
0x180037b7b  mov     rcx, r12; this
0x180037b7e  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x180037b83  mov     ebx, eax
0x180037b85  xor     edx, edx
0x180037b87  test    eax, eax
0x180037b89  js      loc_180037D70
0x180037b8f  cmp     rdi, 1
0x180037b93  jnz     short loc_180037BA4
0x180037b95  mov     rax, [rsp+370h+var_300]
0x180037b9a  movups  xmm0, xmmword ptr [rax]
0x180037b9d  movdqu  xmmword ptr [rbp+270h+rclsid.Data1], xmm0
0x180037ba2  jmp     short loc_180037BC3
0x180037ba4  mov     rcx, [rsp+370h+var_300]
0x180037ba9  mov     rax, qword ptr [rbp+270h+rclsid.Data1]
0x180037bad  sub     rax, [rcx]
0x180037bb0  jnz     short loc_180037BBA
0x180037bb2  mov     rax, qword ptr [rbp+270h+rclsid.Data4]
0x180037bb6  sub     rax, [rcx+8]
0x180037bba  test    rax, rax
0x180037bbd  jnz     loc_180037D6B
0x180037bc3  mov     [rsp+370h+var_300], rdx
0x180037bc8  lea     r8, [rsp+370h+var_300]
0x180037bcd  mov     rdx, r14
0x180037bd0  lea     rcx, [rbp+270h+var_2C8]
0x180037bd4  call    ?find@?$Map@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@AEBAHAEBKPEAPEAPEAVAssoc@1@@Z; Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::find(ulong const &,Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::Assoc * * *)
0x180037bd9  xor     edx, edx
0x180037bdb  test    eax, eax
0x180037bdd  jz      short loc_180037BF1
0x180037bdf  mov     [rsp+370h+var_310], edx
0x180037be3  mov     rax, [rsp+370h+var_300]
0x180037be8  mov     rcx, [rax]
0x180037beb  mov     rdi, [rcx+20h]
0x180037bef  jmp     short loc_180037C32
0x180037bf1  mov     ecx, 10h; cb
0x180037bf6  call    cs:__imp_CoTaskMemAlloc
0x180037bfc  mov     rdi, rax
0x180037bff  xor     edx, edx
0x180037c01  test    rax, rax
0x180037c04  jz      short loc_180037C0E
0x180037c06  xorps   xmm0, xmm0
0x180037c09  movups  xmmword ptr [rax], xmm0
0x180037c0c  jmp     short loc_180037C11
0x180037c0e  mov     rdi, rdx
0x180037c11  xorps   xmm0, xmm0
0x180037c14  movups  xmmword ptr [rdi], xmm0
0x180037c17  test    rdi, rdi
0x180037c1a  mov     eax, 8007000Eh
0x180037c1f  cmovz   ebx, eax
0x180037c22  inc     r15d
0x180037c25  mov     [rsp+370h+var_31C], r15d
0x180037c2a  mov     [rsp+370h+var_310], 1
0x180037c32  mov     r15, rdi
0x180037c35  mov     [rsp+370h+var_300], rdi
0x180037c3a  test    rdi, rdi
0x180037c3d  jz      loc_180037D30
0x180037c43  mov     rbx, r13
0x180037c46  mov     rax, [rbp+270h+var_2F0]
0x180037c4a  inc     rbx
0x180037c4d  cmp     [rax+rbx*2], dx
0x180037c51  jnz     short loc_180037C4A
0x180037c53  inc     rbx
0x180037c56  mov     eax, 2
0x180037c5b  mul     rbx
0x180037c5e  cmovb   rax, r13
0x180037c62  mov     rcx, rax; cb
0x180037c65  call    cs:__imp_CoTaskMemAlloc
0x180037c6b  mov     r13, rax
0x180037c6e  mov     r8, [rbp+270h+var_2F0]; unsigned __int16 *
0x180037c72  mov     rdx, rbx; unsigned __int64
0x180037c75  mov     rcx, rax; unsigned __int16 *
0x180037c78  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037c7d  mov     ebx, eax
0x180037c7f  test    eax, eax
0x180037c81  js      loc_180037D47
0x180037c87  mov     rcx, [rdi]; pv
0x180037c8a  xor     r15d, r15d
0x180037c8d  test    rcx, rcx
0x180037c90  jz      short loc_180037C99
0x180037c92  call    cs:__imp_CoTaskMemFree
0x180037c98  nop
0x180037c99  mov     [rdi], r13
0x180037c9c  mov     eax, [r14]
0x180037c9f  mov     [rdi+8], eax
0x180037ca2  mov     rbx, [rbp+270h+var_2D0]
0x180037ca6  mov     eax, [rbx]
0x180037ca8  mov     [rdi+0Ch], eax
0x180037cab  cmp     [rsp+370h+var_310], r15d
0x180037cb0  jz      short loc_180037D02
0x180037cb2  lea     rcx, [rbp+270h+var_2C8]
0x180037cb6  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x180037cbb  test    eax, eax
0x180037cbd  js      short loc_180037D02
0x180037cbf  mov     [rbp+270h+var_2F0], r15
0x180037cc3  lea     r8, [rbp+270h+var_2F0]
0x180037cc7  mov     rdx, r14
0x180037cca  lea     rcx, [rbp+270h+var_2C8]
0x180037cce  call    ?find@?$Map@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@AEBAHAEBKPEAPEAPEAVAssoc@1@@Z; Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::find(ulong const &,Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::Assoc * * *)
0x180037cd3  test    eax, eax
0x180037cd5  jz      short loc_180037CED
0x180037cd7  mov     rdx, [rbp+270h+var_2F0]
0x180037cdb  mov     rcx, [rdx]
0x180037cde  mov     eax, [r14]
0x180037ce1  mov     [rcx+1Ch], eax
0x180037ce4  mov     rax, [rdx]
0x180037ce7  mov     [rax+20h], rdi
0x180037ceb  jmp     short loc_180037D02
0x180037ced  mov     r9, [rbp+270h+var_2F0]
0x180037cf1  lea     r8, [rsp+370h+var_300]
0x180037cf6  mov     rdx, r14
0x180037cf9  lea     rcx, [rbp+270h+var_2C8]
0x180037cfd  call    ?newAssoc@?$Map@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@AEAAJAEBKAEBQEAUMyDataEntry@@PEAPEAVAssoc@1@@Z; Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::newAssoc(ulong const &,MyDataEntry * const &,Map<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::Assoc * *)
0x180037d02  mov     r14d, [rsp+370h+var_30C]
0x180037d07  cmp     r14d, [rbx]
0x180037d0a  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180037d11  mov     rdi, [rbp+270h+var_2A0]
0x180037d15  mov     r15d, [rsp+370h+var_31C]
0x180037d1a  jnb     loc_180037A75
0x180037d20  mov     r14d, [rbx]
0x180037d23  mov     [rsp+370h+var_30C], r14d
0x180037d28  or      r13, r13
0x180037d2b  jmp     loc_180037A75
0x180037d30  mov     r14d, [rsp+370h+var_30C]
0x180037d35  mov     r15d, [rsp+370h+var_31C]
0x180037d3a  test    ebx, ebx
0x180037d3c  js      short loc_180037D78
0x180037d3e  mov     rdi, [rbp+270h+var_2A0]
0x180037d42  jmp     loc_180037A75
0x180037d47  mov     rcx, r13; pv
0x180037d4a  call    cs:__imp_CoTaskMemFree
0x180037d50  nop
0x180037d51  cmp     qword ptr [rdi], 0
0x180037d55  jnz     short loc_180037D61
0x180037d57  mov     rcx, r15; pv
0x180037d5a  call    cs:__imp_CoTaskMemFree
0x180037d60  nop
0x180037d61  mov     r13, [rsp+370h+lpsz]
0x180037d66  jmp     loc_180038039
0x180037d6b  mov     ebx, 8000FFFFh
0x180037d70  mov     r13, rdx
0x180037d73  jmp     loc_18003803B
0x180037d78  xor     r13d, r13d
0x180037d7b  test    ebx, ebx
0x180037d7d  js      loc_180038039
0x180037d83  lea     rcx, [rbp+270h+var_290]
0x180037d87  call    ?reset@?$EnumMap@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@UEAAXXZ; EnumMap<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::reset(void)
0x180037d8c  mov     edx, r15d
0x180037d8f  lea     rcx, [rbp+270h+var_2E8]
0x180037d93  call    ?setSize@?$Array@PEAUMyDataEntry@@@@QEAAJI@Z; Array<MyDataEntry *>::setSize(uint)
0x180037d98  mov     ebx, eax
0x180037d9a  test    eax, eax
0x180037d9c  js      loc_180038036
0x180037da2  lea     edi, [r14+1]
0x180037da6  mov     r14d, r13d
0x180037da9  lea     rcx, [rbp+270h+var_290]
0x180037dad  call    ?next@?$EnumMap@KPEAUMyDataEntry@@VHashULONG@@VEmptyMapBase@@@@UEAAHXZ; EnumMap<ulong,MyDataEntry *,HashULONG,EmptyMapBase>::next(void)
0x180037db2  mov     esi, dword ptr [rbp+270h+var_2E0]
0x180037db5  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037db9  mov     r12d, [rsp+370h+var_31C]
0x180037dbe  test    eax, eax
0x180037dc0  jz      short loc_180037E39
0x180037dc2  mov     rax, [rbp+270h+var_280]
0x180037dc6  mov     rbx, [rax+20h]
0x180037dca  test    rbx, rbx
0x180037dcd  jz      short loc_180037E2E
0x180037dcf  cmp     [rbx+0Ch], r12d
0x180037dd3  jnb     short loc_180037DE4
0x180037dd5  cmp     r12d, edi
0x180037dd8  jnz     short loc_180037DE4
0x180037dda  cmp     [rbx+0Ch], esi
0x180037ddd  jnb     short loc_180037E0B
0x180037ddf  mov     edx, [rbx+0Ch]
0x180037de2  jmp     short loc_180037E00
0x180037de4  lea     edx, [rsi+1]
0x180037de7  lea     rcx, [rbp+270h+var_2E8]
  ... truncated ...
```
