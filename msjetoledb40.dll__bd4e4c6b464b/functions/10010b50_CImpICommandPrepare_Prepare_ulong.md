# CImpICommandPrepare::Prepare(ulong)

- ea: `0x10010b50`
- end: `0x10010f76`
- name: `?Prepare@CImpICommandPrepare@@UAGJK@Z`
- size: `1062`
- prototype: `int(CImpICommandPrepare *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba50`
- `0x1000ba90`
- `0x1000d4a0`
- `0x10010b50`
- `0x100147f0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001e8b0`
- `0x1001f2d0`
- `0x1001fb20`
- `0x1001fd10`
- `0x10049580`
- `0x1004ab50`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10010f50`
- `KERNEL32!LeaveCriticalSection` at `0x10010f50`
- `KERNEL32!EnterCriticalSection` at `0x10010bb3`
- `KERNEL32!EnterCriticalSection` at `0x10010bb3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10010ba0`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10010ba0`
- `msjet40!__imp__JetCloseTable@8` at `0x10010ea1`
- `msjet40!__imp__JetCloseTable@8` at `0x10010f3b`
- `msjet40!__imp__JetCloseTable@8` at `0x10010ea1`
- `msjet40!__imp__JetCloseTable@8` at `0x10010f3b`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10010f0b`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10010f0b`
- `msjet40!__imp__JetCreateQuery@16` at `0x10010d56`
- `msjet40!__imp__JetCreateQuery@16` at `0x10010d56`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x10010d33`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x10010d33`
- `msjet40!__imp__JetGetTempQueryParameterInfo@24` at `0x10010e70`
- `msjet40!__imp__JetGetTempQueryParameterInfo@24` at `0x10010e70`

## pseudocode

```c
int __stdcall CImpICommandPrepare::Prepare(CImpICommandPrepare *this, unsigned int a2)
{
  CImpICommandPrepare *v2; // edi
  int v3; // eax
  int v4; // eax
  JET_SESID v5; // ecx
  int v6; // eax
  struct _RTL_CRITICAL_SECTION *v7; // esi
  int v8; // ecx
  bool v9; // zf
  _WORD *v10; // edx
  _DWORD *v11; // ecx
  int v12; // eax
  int v13; // eax
  int JetParameterInfo; // ebx
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  int v18; // ecx
  BOOL v19; // eax
  int v20; // ecx
  _WORD *v21; // ecx
  _WORD *v22; // edx
  int v24; // eax
  int v25; // edx
  unsigned __int16 *v26; // ecx
  int v27; // eax
  int v28; // ecx
  signed int QueryParameterInfo; // eax
  unsigned __int16 *Query; // eax
  unsigned int v31; // ebx
  int v32; // edx
  _WORD *v33; // ecx
  unsigned int v35; // ecx
  unsigned __int16 *v36; // eax
  CTransactionState *v37; // ecx
  volatile signed __int32 *v38; // eax
  unsigned int v39; // eax
  int v40; // eax
  int v41; // eax
  CCommand *v43; // [esp+0h] [ebp-78h]
  struct _GUID *v44; // [esp+4h] [ebp-74h]
  char v45[4]; // [esp+14h] [ebp-64h] BYREF
  int v46; // [esp+18h] [ebp-60h]
  unsigned __int16 *v47; // [esp+1Ch] [ebp-5Ch] BYREF
  unsigned __int16 *v48; // [esp+20h] [ebp-58h] BYREF
  _WORD *v49; // [esp+24h] [ebp-54h]
  JET_SESID sesid; // [esp+28h] [ebp-50h]
  unsigned int v51; // [esp+2Ch] [ebp-4Ch] BYREF
  JET_COLUMNLIST v52; // [esp+30h] [ebp-48h] BYREF
  int v53; // [esp+74h] [ebp-4h]

  v2 = this;
  v51 = (unsigned int)this;
  v3 = *((_DWORD *)this + 2);
  v47 = 0;
  v4 = *(_DWORD *)(v3 + 52);
  v5 = *(_DWORD *)(v4 + 16);
  v6 = *(_DWORD *)(v4 + 20);
  sesid = v5;
  v46 = v6;
  SetErrorInfo(0, 0);
  v7 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
  EnterCriticalSection(v7);
  v53 = 0;
  v8 = *((_DWORD *)this + 2);
  v9 = *(_DWORD *)(v8 + 96) == 0;
  v10 = *(_WORD **)(v8 + 20);
  v49 = v10;
  if ( v9 )
  {
    CCommand::CheckForZombieCommandAndFix(v43);
    v10 = v49;
  }
  v11 = (_DWORD *)*((_DWORD *)this + 2);
  v52.tableid = -1;
  v12 = v11[15];
  if ( (v12 & 0x20) == 0 )
  {
    v13 = v11[13];
    JetParameterInfo = -2147217908;
    v15 = *(_DWORD *)(v13 + 20);
    v16 = *(_DWORD *)(v13 + 16);
    goto LABEL_58;
  }
  if ( v11[20] && (v12 & 0x100) == 0 )
  {
    v17 = v11[13];
    JetParameterInfo = -2147217915;
    v15 = *(_DWORD *)(v17 + 20);
    v16 = *(_DWORD *)(v17 + 16);
LABEL_58:
    if ( !JetGetDatabaseInfo(v16, v15, &v48, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_ICommandPrepare, 0, (const struct _GUID *)v43, (int)v44);
LABEL_60:
    if ( JetParameterInfo >= 0 )
      goto LABEL_64;
    goto LABEL_61;
  }
  JetParameterInfo = 0;
  if ( JoltProperties::BinarySearch(*((JoltProperties **)v10 + 6), 0x102u, (unsigned int *)&v48) >= 0
    && (v18 = *(_DWORD *)(*((_DWORD *)v49 + 6) + 16) + 48 * (_DWORD)v48, *(_WORD *)(v18 + 16) == 11) )
  {
    v19 = *(_WORD *)(v18 + 24) == 0xFFFF;
  }
  else
  {
    JetParameterInfo = -2147467259;
    v19 = 0;
  }
  v20 = *((_DWORD *)this + 2);
  if ( (*(_BYTE *)(v20 + 60) & 0x10) == 0 && v19 )
  {
    if ( *(_DWORD *)(v20 + 76) )
    {
      System::Free((void *)v20);
      *(_DWORD *)(*((_DWORD *)this + 2) + 76) = 0;
    }
    v21 = *(_WORD **)(*((_DWORD *)this + 2) + 108);
    v22 = v21 + 1;
    while ( *v21++ )
      ;
    v48 = (unsigned __int16 *)(2 * (v21 - v22) + 2);
    v24 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
            *(_DWORD *)(*(_DWORD *)Sys + 12),
            Sys,
            v48);
    v2 = (CImpICommandPrepare *)v51;
    *(_DWORD *)(*(_DWORD *)(v51 + 8) + 76) = v24;
    v25 = *((_DWORD *)v2 + 2);
    v26 = *(unsigned __int16 **)(v25 + 76);
    if ( !v26 )
    {
      JetParameterInfo = -2147024882;
      goto LABEL_61;
    }
    WCSCPY(*(unsigned __int16 **)(v25 + 108), v26, v48, (const unsigned __int16 *)v43, (unsigned int)v44);
    *(_DWORD *)(*((_DWORD *)v2 + 2) + 60) |= 0x10u;
    *(_DWORD *)(*((_DWORD *)v2 + 2) + 72) = 1;
  }
  v27 = *((_DWORD *)v2 + 2);
  v28 = *(_DWORD *)(v27 + 60);
  if ( *(_DWORD *)(v27 + 72) == 1 )
  {
    *(_DWORD *)(v27 + 60) = v28 | 0x10;
    QueryParameterInfo = JetGetQueryParameterInfo(sesid, v46, *(_DWORD *)(*((_DWORD *)v2 + 2) + 76), &v52, 56, v45);
LABEL_45:
    v51 = QueryParameterInfo;
    if ( QueryParameterInfo < 0 )
    {
      v52.tableid = -1;
      goto LABEL_56;
    }
    JetParameterInfo = CJetParameterList::GetJetParameterInfo(
                         (CJetParameterList *)(*((_DWORD *)v2 + 2) + 84),
                         sesid,
                         &v52);
    if ( JetParameterInfo < 0 && v52.tableid != -1 )
    {
      JetCloseTable(sesid, v52.tableid);
      v52.tableid = -1;
    }
    goto LABEL_49;
  }
  if ( (v28 & 0x10) != 0 )
  {
LABEL_44:
    *(_DWORD *)(*((_DWORD *)v2 + 2) + 60) |= 0x10u;
    QueryParameterInfo = JetGetTempQueryParameterInfo(sesid, v46, *(_DWORD *)(*((_DWORD *)v2 + 2) + 100), &v52, 56, v45);
    goto LABEL_45;
  }
  Query = (unsigned __int16 *)JetCreateQuery(sesid, v46, &word_100046A0, v27 + 100);
  v51 = (unsigned int)Query;
  v48 = Query;
  if ( Query == (unsigned __int16 *)-1907 )
  {
    JetParameterInfo = -2147217911;
    goto LABEL_49;
  }
  if ( Query == (unsigned __int16 *)-1011 )
  {
    JetParameterInfo = -2147024882;
    goto LABEL_49;
  }
  if ( Query )
  {
    JetParameterInfo = -2147467259;
LABEL_49:
    v39 = v51;
    goto LABEL_50;
  }
  JoltProperties::IsbPropertySet(*((JoltProperties **)v49 + 6), 0xFDu, (int *)&v51);
  if ( v51 == 1 )
  {
    v31 = 1;
    JoltProperties::GetStrValue(*((JoltProperties **)v49 + 6), 0xF2u, &v47);
    JoltProperties::IsbPropertySet(*((JoltProperties **)v49 + 6), 0x119u, (int *)&v51);
    if ( v51 == 1 )
      v31 = 3;
    if ( !v47 )
      v31 = 0;
  }
  else
  {
    v31 = 0;
  }
  v32 = *((_DWORD *)v2 + 2);
  v33 = *(_WORD **)(v32 + 108);
  v49 = v33 + 1;
  while ( *v33++ )
    ;
  v35 = v33 - v49;
  v36 = 0;
  if ( v31 )
    v36 = v47;
  JetParameterInfo = CJOLT::JOLTJetSetQoSql(
                       *(_DWORD *)(v32 + 108),
                       v35,
                       v36,
                       v31,
                       (const unsigned __int16 *)&v48,
                       (unsigned int)v43,
                       (int *)v44);
  if ( JetParameterInfo >= 0 )
  {
    v37 = *(CTransactionState **)(*((_DWORD *)v2 + 2) + 56);
    if ( v37 )
      CTransactionState::Release(v37);
    *(_DWORD *)(*((_DWORD *)v2 + 2) + 56) = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v2 + 2) + 52) + 88);
    v38 = *(volatile signed __int32 **)(*((_DWORD *)v2 + 2) + 56);
    if ( v38 )
      _InterlockedIncrement(v38);
    goto LABEL_44;
  }
  v39 = (unsigned int)v48;
LABEL_50:
  if ( v39 )
  {
    CExtError::SendJetErrortoOLEAuto(v39, (int)&IID_ICommandPrepare, (int)v43, v44);
    goto LABEL_60;
  }
LABEL_56:
  if ( JetParameterInfo >= 0 )
    goto LABEL_64;
  v40 = *(_DWORD *)(*((_DWORD *)v2 + 2) + 52);
  v15 = *(_DWORD *)(v40 + 20);
  v16 = *(_DWORD *)(v40 + 16);
  if ( JetParameterInfo != -2147024882 )
    goto LABEL_58;
LABEL_61:
  v41 = *((_DWORD *)v2 + 2);
  if ( *(_DWORD *)(v41 + 100) != -1 && (*(_BYTE *)(v41 + 60) & 0x10) == 0 )
  {
    JetCloseTable(sesid, *(_DWORD *)(v41 + 100));
    *(_DWORD *)(*((_DWORD *)v2 + 2) + 100) = -1;
  }
LABEL_64:
  if ( v7 )
    LeaveCriticalSection(v7);
  return JetParameterInfo;
}

```

## disassembly

```asm
0x10010b50  mov     edi, edi
0x10010b52  push    ebp
0x10010b53  mov     ebp, esp
0x10010b55  push    0FFFFFFFFh
0x10010b57  push    offset ?Prepare@CImpICommandPrepare@@UAGJK@Z_SEH
0x10010b5c  mov     eax, large fs:0
0x10010b62  push    eax
0x10010b63  sub     esp, 5Ch
0x10010b66  mov     eax, ___security_cookie
0x10010b6b  xor     eax, ebp
0x10010b6d  mov     [ebp+var_48.columnidBaseTableName], eax
0x10010b70  push    ebx
0x10010b71  push    esi
0x10010b72  push    edi; int
0x10010b73  push    eax; struct _GUID *
0x10010b74  lea     eax, [ebp+var_48.columnidBaseColumnName]
0x10010b77  mov     large fs:0, eax
0x10010b7d  mov     edi, [ebp+this]
0x10010b80  push    0; perrinfo
0x10010b82  push    0; dwReserved
0x10010b84  mov     [ebp+var_4C], edi
0x10010b87  mov     eax, [edi+8]
0x10010b8a  mov     [ebp+var_5C], 0
0x10010b91  mov     eax, [eax+34h]
0x10010b94  mov     ecx, [eax+10h]
0x10010b97  mov     eax, [eax+14h]
0x10010b9a  mov     [ebp+sesid], ecx
0x10010b9d  mov     [ebp+var_60], eax
0x10010ba0  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10010ba6  mov     esi, [edi+8]
0x10010ba9  add     esi, 0F8h
0x10010baf  push    esi; lpCriticalSection
0x10010bb0  mov     [ebp+var_68], esi
0x10010bb3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10010bb9  mov     [ebp+var_4], 0
0x10010bc0  mov     ecx, [edi+8]
0x10010bc3  cmp     dword ptr [ecx+60h], 0
0x10010bc7  mov     edx, [ecx+14h]
0x10010bca  mov     [ebp+var_54], edx
0x10010bcd  jnz     short loc_10010BD7
0x10010bcf  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x10010bd4  mov     edx, [ebp+var_54]
0x10010bd7  mov     ecx, [edi+8]
0x10010bda  mov     [ebp+var_48.tableid], 0FFFFFFFFh
0x10010be1  mov     eax, [ecx+3Ch]
0x10010be4  test    al, 20h
0x10010be6  jnz     short loc_10010BFB
0x10010be8  mov     eax, [ecx+34h]
0x10010beb  mov     ebx, 80040E0Ch
0x10010bf0  mov     ecx, [eax+14h]
0x10010bf3  mov     eax, [eax+10h]
0x10010bf6  jmp     loc_10010F01
0x10010bfb  cmp     dword ptr [ecx+50h], 0
0x10010bff  jbe     short loc_10010C1B
0x10010c01  test    eax, 100h
0x10010c06  jnz     short loc_10010C1B
0x10010c08  mov     eax, [ecx+34h]
0x10010c0b  mov     ebx, 80040E05h
0x10010c10  mov     ecx, [eax+14h]
0x10010c13  mov     eax, [eax+10h]
0x10010c16  jmp     loc_10010F01
0x10010c1b  mov     ecx, [edx+18h]; this
0x10010c1e  lea     eax, [ebp+var_58]
0x10010c21  push    eax; unsigned int *
0x10010c22  push    102h; unsigned int
0x10010c27  xor     ebx, ebx
0x10010c29  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10010c2e  test    eax, eax
0x10010c30  js      short loc_10010C5D
0x10010c32  mov     eax, [ebp+var_58]
0x10010c35  mov     edx, [ebp+var_54]
0x10010c38  lea     ecx, [eax+eax*2]
0x10010c3b  mov     eax, [edx+18h]
0x10010c3e  shl     ecx, 4
0x10010c41  add     ecx, [eax+10h]
0x10010c44  mov     eax, 0Bh
0x10010c49  cmp     ax, [ecx+10h]
0x10010c4d  jnz     short loc_10010C5D
0x10010c4f  or      edx, 0FFFFFFFFh
0x10010c52  xor     eax, eax
0x10010c54  cmp     dx, [ecx+18h]
0x10010c58  setz    al
0x10010c5b  jmp     short loc_10010C64
0x10010c5d  mov     ebx, 80004005h
0x10010c62  xor     eax, eax
0x10010c64  mov     ecx, [edi+8]; void *
0x10010c67  test    byte ptr [ecx+3Ch], 10h
0x10010c6b  jnz     loc_10010D0B
0x10010c71  cmp     eax, 1
0x10010c74  jnz     loc_10010D0B
0x10010c7a  mov     eax, [ecx+4Ch]
0x10010c7d  test    eax, eax
0x10010c7f  jz      short loc_10010C91
0x10010c81  push    eax
0x10010c82  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10010c87  mov     eax, [edi+8]
0x10010c8a  mov     dword ptr [eax+4Ch], 0
0x10010c91  mov     eax, [edi+8]
0x10010c94  mov     ecx, [eax+6Ch]
0x10010c97  lea     edx, [ecx+2]
0x10010c9a  nop     word ptr [eax+eax+00h]
0x10010ca0  mov     ax, [ecx]
0x10010ca3  add     ecx, 2
0x10010ca6  test    ax, ax
0x10010ca9  jnz     short loc_10010CA0
0x10010cab  sub     ecx, edx
0x10010cad  sar     ecx, 1
0x10010caf  lea     edx, ds:2[ecx*2]
0x10010cb6  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10010cbc  push    edx
0x10010cbd  push    ecx
0x10010cbe  mov     [ebp+var_58], edx
0x10010cc1  mov     eax, [ecx]
0x10010cc3  mov     edi, [eax+0Ch]
0x10010cc6  mov     ecx, edi
0x10010cc8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10010cce  call    edi
0x10010cd0  mov     edi, [ebp+var_4C]
0x10010cd3  mov     ecx, eax
0x10010cd5  mov     eax, [edi+8]
0x10010cd8  mov     [eax+4Ch], ecx
0x10010cdb  mov     edx, [edi+8]
0x10010cde  mov     ecx, [edx+4Ch]
0x10010ce1  test    ecx, ecx
0x10010ce3  jnz     short loc_10010CEF
0x10010ce5  mov     ebx, 8007000Eh
0x10010cea  jmp     loc_10010F26
0x10010cef  push    [ebp+var_58]; unsigned __int16 *
0x10010cf2  mov     edx, [edx+6Ch]
0x10010cf5  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x10010cfa  mov     eax, [edi+8]
0x10010cfd  or      dword ptr [eax+3Ch], 10h
0x10010d01  mov     eax, [edi+8]
0x10010d04  mov     dword ptr [eax+48h], 1
0x10010d0b  mov     eax, [edi+8]
0x10010d0e  cmp     dword ptr [eax+48h], 1
0x10010d12  mov     ecx, [eax+3Ch]
0x10010d15  jnz     short loc_10010D3E
0x10010d17  or      ecx, 10h
0x10010d1a  mov     [eax+3Ch], ecx
0x10010d1d  lea     eax, [ebp+var_64]
0x10010d20  push    eax
0x10010d21  push    38h ; '8'
0x10010d23  lea     eax, [ebp+var_48]
0x10010d26  push    eax
0x10010d27  mov     eax, [edi+8]
0x10010d2a  push    dword ptr [eax+4Ch]
0x10010d2d  push    [ebp+var_60]
0x10010d30  push    [ebp+sesid]
0x10010d33  call    ds:__imp__JetGetQueryParameterInfo@24; JetGetQueryParameterInfo(x,x,x,x,x,x)
0x10010d39  jmp     loc_10010E76
0x10010d3e  test    cl, 10h
0x10010d41  jnz     loc_10010E53
0x10010d47  add     eax, 64h ; 'd'
0x10010d4a  push    eax
0x10010d4b  push    offset word_100046A0
0x10010d50  push    [ebp+var_60]
0x10010d53  push    [ebp+sesid]
0x10010d56  call    ds:__imp__JetCreateQuery@16; JetCreateQuery(x,x,x,x)
0x10010d5c  mov     ebx, eax
0x10010d5e  mov     [ebp+var_4C], ebx
0x10010d61  mov     [ebp+var_58], ebx
0x10010d64  cmp     ebx, 0FFFFF88Dh
0x10010d6a  jz      loc_10010ED9
0x10010d70  cmp     ebx, 0FFFFFC0Dh
0x10010d76  jz      loc_10010ED2
0x10010d7c  test    ebx, ebx
0x10010d7e  jz      short loc_10010D8A
0x10010d80  mov     ebx, 80004005h
0x10010d85  jmp     loc_10010EAE
0x10010d8a  lea     eax, [ebp+var_4C]
0x10010d8d  push    eax; int *
0x10010d8e  mov     eax, [ebp+var_54]
0x10010d91  push    0FDh; unsigned int
0x10010d96  mov     ecx, [eax+18h]; this
0x10010d99  call    ?IsbPropertySet@JoltProperties@@QBEJKAAH@Z; JoltProperties::IsbPropertySet(ulong,int &)
0x10010d9e  cmp     [ebp+var_4C], 1
0x10010da2  jnz     short loc_10010DE6
0x10010da4  lea     eax, [ebp+var_5C]
0x10010da7  mov     ebx, 1
0x10010dac  push    eax; unsigned __int16 **
0x10010dad  mov     eax, [ebp+var_54]
0x10010db0  push    0F2h; unsigned int
0x10010db5  mov     ecx, [eax+18h]; this
0x10010db8  call    ?GetStrValue@JoltProperties@@QBEJKAAPAG@Z; JoltProperties::GetStrValue(ulong,ushort * &)
0x10010dbd  lea     eax, [ebp+var_4C]
0x10010dc0  push    eax; int *
0x10010dc1  mov     eax, [ebp+var_54]
0x10010dc4  push    119h; unsigned int
0x10010dc9  mov     ecx, [eax+18h]; this
0x10010dcc  call    ?IsbPropertySet@JoltProperties@@QBEJKAAH@Z; JoltProperties::IsbPropertySet(ulong,int &)
0x10010dd1  cmp     [ebp+var_4C], ebx
0x10010dd4  mov     eax, 3
0x10010dd9  cmovz   ebx, eax
0x10010ddc  xor     eax, eax
0x10010dde  cmp     [ebp+var_5C], eax
0x10010de1  cmovz   ebx, eax
0x10010de4  jmp     short loc_10010DE8
0x10010de6  xor     ebx, ebx
0x10010de8  mov     edx, [edi+8]
0x10010deb  mov     ecx, [edx+6Ch]
0x10010dee  lea     eax, [ecx+2]
0x10010df1  mov     [ebp+var_54], eax
0x10010df4  mov     ax, [ecx]
0x10010df7  add     ecx, 2
0x10010dfa  test    ax, ax
0x10010dfd  jnz     short loc_10010DF4
0x10010dff  sub     ecx, [ebp+var_54]
0x10010e02  lea     eax, [ebp+var_58]
0x10010e05  push    eax; unsigned __int16 *
0x10010e06  sar     ecx, 1
0x10010e08  xor     eax, eax
0x10010e0a  push    ebx; unsigned int
0x10010e0b  test    ebx, ebx
0x10010e0d  cmovnz  eax, [ebp+var_5C]
0x10010e11  push    eax; unsigned __int16 *
0x10010e12  push    ecx; unsigned int
0x10010e13  push    dword ptr [edx+6Ch]; unsigned int
0x10010e16  mov     edx, [edx+64h]
0x10010e19  mov     ecx, [ebp+sesid]
0x10010e1c  call    ?JOLTJetSetQoSql@CJOLT@@SGJKKPAGKPBGKAAJ@Z; CJOLT::JOLTJetSetQoSql(ulong,ulong,ushort *,ulong,ushort const *,ulong,long &)
0x10010e21  mov     ebx, eax
0x10010e23  test    ebx, ebx
0x10010e25  js      loc_10010ECD
0x10010e2b  mov     eax, [edi+8]
0x10010e2e  mov     ecx, [eax+38h]; this
0x10010e31  test    ecx, ecx
0x10010e33  jz      short loc_10010E3A
0x10010e35  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x10010e3a  mov     ecx, [edi+8]
0x10010e3d  mov     eax, [ecx+34h]
0x10010e40  mov     eax, [eax+58h]
0x10010e43  mov     [ecx+38h], eax
0x10010e46  mov     eax, [edi+8]
0x10010e49  mov     eax, [eax+38h]
0x10010e4c  test    eax, eax
0x10010e4e  jz      short loc_10010E53
0x10010e50  lock inc dword ptr [eax]
0x10010e53  mov     eax, [edi+8]
0x10010e56  or      dword ptr [eax+3Ch], 10h
0x10010e5a  lea     eax, [ebp+var_64]
0x10010e5d  push    eax
0x10010e5e  push    38h ; '8'
0x10010e60  lea     eax, [ebp+var_48]
0x10010e63  push    eax
0x10010e64  mov     eax, [edi+8]
0x10010e67  push    dword ptr [eax+64h]
0x10010e6a  push    [ebp+var_60]
0x10010e6d  push    [ebp+sesid]
0x10010e70  call    ds:__imp__JetGetTempQueryParameterInfo@24; JetGetTempQueryParameterInfo(x,x,x,x,x,x)
0x10010e76  mov     [ebp+var_4C], eax
0x10010e79  test    eax, eax
0x10010e7b  js      short loc_10010EE0
0x10010e7d  mov     ecx, [edi+8]
0x10010e80  lea     eax, [ebp+var_48]
0x10010e83  push    eax; struct JET_COLUMNLIST *
0x10010e84  push    [ebp+sesid]; unsigned int
0x10010e87  add     ecx, 54h ; 'T'; this
0x10010e8a  call    ?GetJetParameterInfo@CJetParameterList@@QAEJKAAUJET_COLUMNLIST@@@Z; CJetParameterList::GetJetParameterInfo(ulong,JET_COLUMNLIST &)
0x10010e8f  mov     ebx, eax
0x10010e91  test    ebx, ebx
0x10010e93  jns     short loc_10010EAE
0x10010e95  mov     eax, [ebp+var_48.tableid]
0x10010e98  cmp     eax, 0FFFFFFFFh
0x10010e9b  jz      short loc_10010EAE
0x10010e9d  push    eax; tableid
0x10010e9e  push    [ebp+sesid]; sesid
0x10010ea1  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10010ea7  mov     [ebp+var_48.tableid], 0FFFFFFFFh
0x10010eae  mov     eax, [ebp+var_4C]
0x10010eb1  test    eax, eax
0x10010eb3  jz      short loc_10010EE7
0x10010eb5  push    offset _IID_ICommandPrepare; int
0x10010eba  push    eax; unsigned int
0x10010ebb  mov     eax, [edi+8]
0x10010ebe  mov     edx, ebx
0x10010ec0  mov     ecx, [eax+34h]
0x10010ec3  mov     ecx, [ecx+10h]
0x10010ec6  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10010ecb  jmp     short loc_10010F22
0x10010ecd  mov     eax, [ebp+var_58]
0x10010ed0  jmp     short loc_10010EB1
0x10010ed2  mov     ebx, 8007000Eh
0x10010ed7  jmp     short loc_10010EAE
0x10010ed9  mov     ebx, 80040E09h
0x10010ede  jmp     short loc_10010EAE
0x10010ee0  mov     [ebp+var_48.tableid], 0FFFFFFFFh
0x10010ee7  mov     edx, ebx
0x10010ee9  test    ebx, ebx
0x10010eeb  jns     short loc_10010F4B
0x10010eed  mov     eax, [edi+8]
0x10010ef0  mov     eax, [eax+34h]
0x10010ef3  mov     ecx, [eax+14h]
0x10010ef6  mov     eax, [eax+10h]
0x10010ef9  cmp     edx, 8007000Eh
0x10010eff  jz      short loc_10010F26
0x10010f01  push    3
0x10010f03  push    4
0x10010f05  lea     edx, [ebp+var_58]
0x10010f08  push    edx
  ... truncated ...
```
