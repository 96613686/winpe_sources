# CImpIAlterTable::AlterTable(tagDBID *,tagDBID *,ulong,tagDBPROPSET * const)

- ea: `0x10046bb0`
- end: `0x1004705d`
- name: `?AlterTable@CImpIAlterTable@@UAGJPAUtagDBID@@0KQAUtagDBPROPSET@@@Z`
- size: `1197`
- prototype: `int(CImpIAlterTable *__hidden this, struct tagDBID *, struct tagDBID *, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x10014a70`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x10020410`
- `0x100207d0`
- `0x10022990`
- `0x10022a90`
- `0x10023030`
- `0x10046bb0`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1004703a`
- `KERNEL32!LeaveCriticalSection` at `0x1004703a`
- `KERNEL32!EnterCriticalSection` at `0x10046c12`
- `KERNEL32!EnterCriticalSection` at `0x10046c12`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10046bfc`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10046bfc`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1004701e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1004701e`
- `msjet40!__imp__JetRenameTable@16` at `0x10046f29`
- `msjet40!__imp__JetRenameTable@16` at `0x10046f29`
- `msjet40!__imp__JetRefreshLink@20` at `0x10046ea0`
- `msjet40!__imp__JetRefreshLink@20` at `0x10046ea0`

## pseudocode

```c
int __stdcall CImpIAlterTable::AlterTable(
        CImpIAlterTable *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        unsigned int a4,
        struct tagDBPROPSET *const a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // esi
  struct tagDBID *v6; // eax
  int v7; // edi
  int v8; // ecx
  char *v9; // eax
  struct tagDBPROPSET *v10; // ecx
  unsigned int v11; // esi
  GUID *p_guidPropertySet; // edx
  unsigned int *v13; // edx
  int *v14; // ecx
  bool v15; // cf
  unsigned int *v16; // edx
  const GUID *v17; // ecx
  _DWORD *v18; // edi
  int v19; // ecx
  int refreshed; // eax
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  JoltProperties *v24; // ecx
  int v25; // eax
  const struct _GUID *v27; // [esp+0h] [ebp-4Ch]
  const struct _GUID *v28; // [esp+4h] [ebp-48h]
  JoltProperties *v29[2]; // [esp+Ch] [ebp-40h] BYREF
  JoltProperties *v30; // [esp+14h] [ebp-38h]
  JoltProperties *v31; // [esp+18h] [ebp-34h]
  struct _RTL_CRITICAL_SECTION *v32; // [esp+1Ch] [ebp-30h]
  unsigned int v33; // [esp+20h] [ebp-2Ch] BYREF
  struct tagDBPROPSET *v34; // [esp+24h] [ebp-28h]
  unsigned int *v35; // [esp+28h] [ebp-24h]
  int v36; // [esp+2Ch] [ebp-20h]
  int v37; // [esp+30h] [ebp-1Ch]
  int v38; // [esp+34h] [ebp-18h]
  unsigned int v39; // [esp+38h] [ebp-14h]
  int v40; // [esp+3Ch] [ebp-10h] BYREF
  int v41; // [esp+48h] [ebp-4h]

  v29[0] = (JoltProperties *)&CAlterTableTableProperties::`vftable';
  v36 = 0;
  v40 = 0;
  v38 = 0;
  v37 = 0;
  v29[1] = 0;
  v30 = 0;
  v31 = 0;
  v41 = 0;
  SetErrorInfo(0, 0);
  v5 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  v33 = (unsigned int)v5;
  v32 = v5;
  EnterCriticalSection(v5);
  v6 = a2;
  LOBYTE(v41) = 1;
  if ( !a2 )
    goto LABEL_2;
  if ( a4 )
  {
    if ( !a5 )
    {
      v7 = -2147024809;
      goto LABEL_78;
    }
    v8 = 0;
    while ( !a5[v8].cProperties || a5[v8].rgProperties )
    {
      if ( ++v8 >= a4 )
      {
        v6 = a2;
        goto LABEL_11;
      }
    }
LABEL_2:
    v7 = -2147024809;
LABEL_78:
    v25 = *((_DWORD *)this + 2);
    v22 = *(_DWORD *)(v25 + 20);
    v23 = *(_DWORD *)(v25 + 16);
LABEL_79:
    if ( !JetGetDatabaseInfo(v23, v22, &v33, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IAlterTable, 0, v27, (int)v28);
    goto LABEL_81;
  }
LABEL_11:
  if ( v6->eKind != 2 || a3 && a3->eKind != 2 )
  {
    v7 = -2147217865;
    goto LABEL_78;
  }
  v9 = (char *)operator new(0x28u);
  v39 = (unsigned int)v9;
  v7 = 0;
  if ( !v9 )
  {
    v31 = 0;
    do
    {
      v24 = *(&v30 + v7);
      if ( v24 )
      {
        JoltProperties::`scalar deleting destructor'(v24, (unsigned int)*(&v30 + v7));
        *(&v30 + v7) = 0;
      }
      ++v7;
    }
    while ( (unsigned int)v7 < 2 );
    v7 = -2147024882;
    goto LABEL_81;
  }
  *(_DWORD *)v9 = &JoltProperties::`vftable';
  *((_DWORD *)v9 + 1) = 0;
  *((_DWORD *)v9 + 2) = 0;
  *((_DWORD *)v9 + 3) = 0;
  *((_DWORD *)v9 + 4) = 0;
  *((_DWORD *)v9 + 9) = 0;
  *(GUID *)(v9 + 20) = DBPROPSET_ROWSET;
  v31 = (JoltProperties *)v9;
  if ( !a4 )
  {
    refreshed = 0;
    goto LABEL_48;
  }
  v7 = (**(int (__thiscall ***)(unsigned int, const struct DBInfoProps *const *, _DWORD, _DWORD, int, int, int, int, int *, int))v9)(
         v39,
         &rgDBInfoProps,
         0,
         0,
         -431176196,
         298885106,
         -1073693282,
         -524107185,
         dword_1000549C,
         5);
  if ( v7 < 0 )
    goto LABEL_70;
  v7 = CAlterTableTableProperties::SetJetPropertiesToJoltProperties(
         v29,
         *(_DWORD *)(*((_DWORD *)this + 2) + 16),
         (unsigned int)a2,
         *(_DWORD *)(*((_DWORD *)this + 2) + 20),
         a2->uName.pwszName);
  if ( v7 < 0 )
    goto LABEL_70;
  v10 = a5;
  v11 = 0;
  p_guidPropertySet = &a5->guidPropertySet;
  do
  {
    v39 = 12;
    v13 = &p_guidPropertySet->Data1 + 6 * v11;
    v34 = &v10[v11];
    v14 = dword_10008D40;
    v35 = v13;
    while ( *v14 == *v13 )
    {
      ++v14;
      ++v13;
      v15 = v39 < 4;
      v39 -= 4;
      if ( v15 )
      {
LABEL_26:
        v7 = CSettableProperties::SetProperties((CSettableProperties *)v29, 1u, v34, 0);
        goto LABEL_27;
      }
    }
    v16 = v35;
    v17 = &DBPROPSET_TABLE;
    v39 = 12;
    while ( v17->Data1 == *v16 )
    {
      v17 = (const GUID *)((char *)v17 + 4);
      ++v16;
      v15 = v39 < 4;
      v39 -= 4;
      if ( v15 )
        goto LABEL_26;
    }
LABEL_27:
    if ( v7 < 0 || v7 == 265946 )
      v38 = 1;
    else
      v37 = 1;
    v10 = a5;
    ++v11;
    p_guidPropertySet = &a5->guidPropertySet;
  }
  while ( v11 < a4 );
  v5 = (struct _RTL_CRITICAL_SECTION *)v33;
  v18 = (_DWORD *)((char *)v31 + 16);
  if ( JoltProperties::BinarySearch(v31, 0xF4u, &v33) >= 0 && (*(_DWORD *)(*v18 + 48 * v33 + 40) & 1) != 0
    || JoltProperties::BinarySearch(v31, 0xF5u, &v33) >= 0 && (*(_DWORD *)(*v18 + 48 * v33 + 40) & 1) != 0 )
  {
    v39 = JoltProperties::BinarySearch(v31, 0xF5u, &v33) < 0 ? 0 : *(_DWORD *)(*v18 + 48 * v33 + 24);
    v19 = JoltProperties::BinarySearch(v31, 0xF4u, &v33) < 0 ? 0 : *(_DWORD *)(*v18 + 48 * v33 + 24);
    refreshed = JetRefreshLink(
                  *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                  *(_DWORD *)(*((_DWORD *)this + 2) + 20),
                  a2->uName.ulPropid,
                  v19,
                  v39);
    v36 = refreshed;
    v40 = refreshed;
    if ( refreshed < 0 )
    {
      v7 = -2147467259;
      goto LABEL_67;
    }
  }
  v7 = CTableProperties::SetPropertiesToJetPropertyManager(
         (CTableProperties *)v29,
         *(_DWORD *)(*((_DWORD *)this + 2) + 16),
         (unsigned int)a2,
         *(_DWORD *)(*((_DWORD *)this + 2) + 20),
         a2->uName.pwszName);
  if ( v7 < 0 )
  {
    refreshed = v36;
    goto LABEL_67;
  }
  v7 = CTableProperties::SetPropertiesInMSysObjects(
         v29,
         *(_DWORD *)(*((_DWORD *)this + 2) + 16),
         *(_DWORD *)(*((_DWORD *)this + 2) + 20),
         a2->uName.pwszName,
         &v40);
  refreshed = v40;
  if ( v7 >= 0 )
  {
LABEL_48:
    if ( a3 )
    {
      refreshed = JetRenameTable(
                    *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                    *(_DWORD *)(*((_DWORD *)this + 2) + 20),
                    a2->uName.ulPropid,
                    a3->uName.ulPropid);
      if ( refreshed <= -1305 )
      {
        if ( refreshed != -1305 )
        {
          if ( refreshed == -1809 )
          {
            v7 = -2147217911;
            goto LABEL_67;
          }
          goto LABEL_60;
        }
LABEL_61:
        v7 = -2147217865;
        goto LABEL_67;
      }
      if ( refreshed <= -1302 )
      {
        if ( refreshed == -1302 || refreshed == -1304 )
          v7 = -2147217856;
        else
          v7 = -2147217857;
        goto LABEL_67;
      }
      if ( refreshed == -1002 )
        goto LABEL_61;
      if ( refreshed )
      {
LABEL_60:
        v7 = -2147467259;
        goto LABEL_67;
      }
    }
    if ( v38 == 1 )
    {
      v7 = -2147217887;
      if ( v37 == 1 )
        v7 = 265946;
    }
  }
LABEL_67:
  if ( refreshed )
  {
    CExtError::SendJetErrortoOLEAuto(
      v7,
      *(char **)(*((_DWORD *)this + 2) + 16),
      refreshed,
      (int)&IID_IAlterTable,
      (int)v27,
      v28);
    goto LABEL_81;
  }
  if ( v7 < 0 )
  {
LABEL_70:
    v21 = *((_DWORD *)this + 2);
    v22 = *(_DWORD *)(v21 + 20);
    v23 = *(_DWORD *)(v21 + 16);
    if ( v7 == -2147024882 )
      goto LABEL_81;
    goto LABEL_79;
  }
LABEL_81:
  if ( v5 )
    LeaveCriticalSection(v5);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v29);
  return v7;
}

```

## disassembly

```asm
0x10046bb0  mov     edi, edi
0x10046bb2  push    ebp
0x10046bb3  mov     ebp, esp
0x10046bb5  push    0FFFFFFFFh
0x10046bb7  push    offset ?AlterTable@CImpIAlterTable@@UAGJPAUtagDBID@@0KQAUtagDBPROPSET@@@Z_SEH
0x10046bbc  mov     eax, large fs:0
0x10046bc2  push    eax
0x10046bc3  sub     esp, 34h
0x10046bc6  push    esi
0x10046bc7  push    edi; int
0x10046bc8  mov     eax, ___security_cookie
0x10046bcd  xor     eax, ebp
0x10046bcf  push    eax; struct _GUID *
0x10046bd0  lea     eax, [ebp+var_C]
0x10046bd3  mov     large fs:0, eax
0x10046bd9  xor     eax, eax
0x10046bdb  mov     [ebp+var_40], offset ??_7CAlterTableTableProperties@@6B@; const CAlterTableTableProperties::`vftable'
0x10046be2  mov     [ebp+var_20], eax
0x10046be5  mov     [ebp+var_10], eax
0x10046be8  mov     [ebp+var_18], eax
0x10046beb  mov     [ebp+var_1C], eax
0x10046bee  mov     [ebp+var_3C], eax
0x10046bf1  mov     [ebp+var_38], eax
0x10046bf4  mov     [ebp+var_34], eax
0x10046bf7  push    eax; perrinfo
0x10046bf8  push    eax; dwReserved
0x10046bf9  mov     [ebp+var_4], eax
0x10046bfc  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10046c02  mov     esi, [ebp+this]
0x10046c05  mov     esi, [esi+8]
0x10046c08  add     esi, 68h ; 'h'
0x10046c0b  push    esi; lpCriticalSection
0x10046c0c  mov     [ebp+var_2C], esi
0x10046c0f  mov     [ebp+var_30], esi
0x10046c12  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10046c18  mov     eax, [ebp+arg_4]
0x10046c1b  mov     byte ptr [ebp+var_4], 1
0x10046c1f  test    eax, eax
0x10046c21  jnz     short loc_10046C2D
0x10046c23  mov     edi, 80070057h
0x10046c28  jmp     loc_10047008
0x10046c2d  mov     edx, [ebp+arg_C]
0x10046c30  test    edx, edx
0x10046c32  jz      short loc_10046C68
0x10046c34  mov     edi, [ebp+arg_10]
0x10046c37  test    edi, edi
0x10046c39  jnz     short loc_10046C45
0x10046c3b  mov     edi, 80070057h
0x10046c40  jmp     loc_10047008
0x10046c45  xor     ecx, ecx
0x10046c47  nop     word ptr [eax+eax+00000000h]
0x10046c50  lea     eax, [ecx+ecx*2]
0x10046c53  cmp     dword ptr [edi+eax*8+4], 0
0x10046c58  jz      short loc_10046C60
0x10046c5a  cmp     dword ptr [edi+eax*8], 0
0x10046c5e  jz      short loc_10046C23
0x10046c60  inc     ecx
0x10046c61  cmp     ecx, edx
0x10046c63  jb      short loc_10046C50
0x10046c65  mov     eax, [ebp+arg_4]
0x10046c68  cmp     dword ptr [eax+10h], 2
0x10046c6c  jnz     loc_10047003
0x10046c72  mov     eax, [ebp+arg_8]
0x10046c75  test    eax, eax
0x10046c77  jz      short loc_10046C83
0x10046c79  cmp     dword ptr [eax+10h], 2
0x10046c7d  jnz     loc_10047003
0x10046c83  push    28h ; '('; Size
0x10046c85  call    ??2@YAPAXI@Z; operator new(uint)
0x10046c8a  add     esp, 4
0x10046c8d  mov     [ebp+var_14], eax
0x10046c90  xor     edi, edi
0x10046c92  test    eax, eax
0x10046c94  jz      loc_10046FD6
0x10046c9a  mov     dword ptr [eax], offset ??_7JoltProperties@@6B@; const JoltProperties::`vftable'
0x10046ca0  mov     [eax+4], edi
0x10046ca3  mov     [eax+8], edi
0x10046ca6  mov     [eax+0Ch], edi
0x10046ca9  mov     [eax+10h], edi
0x10046cac  movups  xmm0, xmmword ptr ds:_DBPROPSET_ROWSET.Data1
0x10046cb3  mov     [eax+24h], edi
0x10046cb6  movups  xmmword ptr [eax+14h], xmm0
0x10046cba  mov     [ebp+var_34], eax
0x10046cbd  cmp     [ebp+arg_C], edi
0x10046cc0  jz      loc_10046F0B
0x10046cc6  mov     eax, [eax]
0x10046cc8  movups  xmm0, ds:xmmword_10005440
0x10046ccf  mov     edi, [eax]
0x10046cd1  push    5
0x10046cd3  push    offset dword_1000549C
0x10046cd8  sub     esp, 10h
0x10046cdb  mov     ecx, edi
0x10046cdd  mov     eax, esp
0x10046cdf  push    0
0x10046ce1  push    0
0x10046ce3  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10046ce8  movups  xmmword ptr [eax], xmm0
0x10046ceb  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10046cf1  mov     ecx, [ebp+var_14]
0x10046cf4  call    edi
0x10046cf6  mov     edi, eax
0x10046cf8  test    edi, edi
0x10046cfa  js      loc_10046FC0
0x10046d00  mov     eax, [ebp+this]
0x10046d03  mov     ecx, [ebp+arg_4]
0x10046d06  mov     eax, [eax+8]
0x10046d09  push    dword ptr [ecx+14h]; unsigned __int16 *
0x10046d0c  push    dword ptr [eax+14h]; unsigned int
0x10046d0f  push    ecx; unsigned int
0x10046d10  push    dword ptr [eax+10h]; sesid
0x10046d13  lea     ecx, [ebp+var_40]; this
0x10046d16  call    ?SetJetPropertiesToJoltProperties@CAlterTableTableProperties@@QAEJKKKPAG@Z; CAlterTableTableProperties::SetJetPropertiesToJoltProperties(ulong,ulong,ulong,ushort *)
0x10046d1b  mov     edi, eax
0x10046d1d  test    edi, edi
0x10046d1f  js      loc_10046FC0
0x10046d25  cmp     [ebp+arg_C], 0
0x10046d29  jbe     loc_10046DD5
0x10046d2f  mov     ecx, [ebp+arg_10]
0x10046d32  xor     esi, esi
0x10046d34  lea     edx, [ecx+8]
0x10046d37  nop     word ptr [eax+eax+00000000h]
0x10046d40  lea     eax, [esi+esi*2]
0x10046d43  mov     [ebp+var_14], 0Ch
0x10046d4a  shl     eax, 3
0x10046d4d  add     ecx, eax
0x10046d4f  add     edx, eax
0x10046d51  mov     [ebp+var_28], ecx
0x10046d54  mov     ecx, offset dword_10008D40
0x10046d59  mov     [ebp+var_24], edx
0x10046d5c  nop     dword ptr [eax+00h]
0x10046d60  mov     eax, [ecx]
0x10046d62  cmp     eax, [edx]
0x10046d64  jnz     short loc_10046D74
0x10046d66  add     ecx, 4
0x10046d69  add     edx, 4
0x10046d6c  sub     [ebp+var_14], 4
0x10046d70  jnb     short loc_10046D60
0x10046d72  jmp     short loc_10046D95
0x10046d74  mov     edx, [ebp+var_24]
0x10046d77  mov     ecx, offset _DBPROPSET_TABLE
0x10046d7c  mov     [ebp+var_14], 0Ch
0x10046d83  mov     eax, [ecx]
0x10046d85  cmp     eax, [edx]
0x10046d87  jnz     short loc_10046DA6
0x10046d89  add     ecx, 4
0x10046d8c  add     edx, 4
0x10046d8f  sub     [ebp+var_14], 4
0x10046d93  jnb     short loc_10046D83
0x10046d95  push    0; struct CDBSession *
0x10046d97  push    [ebp+var_28]; struct tagDBPROPSET *
0x10046d9a  lea     ecx, [ebp+var_40]; this
0x10046d9d  push    1; unsigned int
0x10046d9f  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x10046da4  mov     edi, eax
0x10046da6  test    edi, edi
0x10046da8  js      short loc_10046DBB
0x10046daa  cmp     edi, 40EDAh
0x10046db0  jz      short loc_10046DBB
0x10046db2  mov     [ebp+var_1C], 1
0x10046db9  jmp     short loc_10046DC2
0x10046dbb  mov     [ebp+var_18], 1
0x10046dc2  mov     ecx, [ebp+arg_10]
0x10046dc5  inc     esi
0x10046dc6  lea     edx, [ecx+8]
0x10046dc9  cmp     esi, [ebp+arg_C]
0x10046dcc  jb      loc_10046D40
0x10046dd2  mov     esi, [ebp+var_2C]
0x10046dd5  mov     eax, [ebp+var_34]
0x10046dd8  lea     ecx, [ebp+var_2C]
0x10046ddb  push    ecx; unsigned int *
0x10046ddc  push    0F4h; unsigned int
0x10046de1  mov     ecx, eax; this
0x10046de3  lea     edi, [eax+10h]
0x10046de6  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10046deb  test    eax, eax
0x10046ded  js      short loc_10046E03
0x10046def  mov     eax, [ebp+var_2C]
0x10046df2  lea     ecx, [eax+eax*2]
0x10046df5  mov     eax, [edi]
0x10046df7  add     ecx, ecx
0x10046df9  test    dword ptr [eax+ecx*8+28h], 1
0x10046e01  jnz     short loc_10046E34
0x10046e03  mov     ecx, [ebp+var_34]; this
0x10046e06  lea     eax, [ebp+var_2C]
0x10046e09  push    eax; unsigned int *
0x10046e0a  push    0F5h; unsigned int
0x10046e0f  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10046e14  test    eax, eax
0x10046e16  js      loc_10046EBA
0x10046e1c  mov     eax, [ebp+var_2C]
0x10046e1f  lea     ecx, [eax+eax*2]
0x10046e22  mov     eax, [edi]
0x10046e24  add     ecx, ecx
0x10046e26  test    dword ptr [eax+ecx*8+28h], 1
0x10046e2e  jz      loc_10046EBA
0x10046e34  mov     ecx, [ebp+var_34]; this
0x10046e37  lea     eax, [ebp+var_2C]
0x10046e3a  push    eax; unsigned int *
0x10046e3b  push    0F5h; unsigned int
0x10046e40  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10046e45  test    eax, eax
0x10046e47  js      short loc_10046E5C
0x10046e49  mov     eax, [ebp+var_2C]
0x10046e4c  lea     ecx, [eax+eax*2]
0x10046e4f  mov     eax, [edi]
0x10046e51  add     ecx, ecx
0x10046e53  mov     eax, [eax+ecx*8+18h]
0x10046e57  mov     [ebp+var_14], eax
0x10046e5a  jmp     short loc_10046E63
0x10046e5c  mov     [ebp+var_14], 0
0x10046e63  mov     ecx, [ebp+var_34]; this
0x10046e66  lea     eax, [ebp+var_2C]
0x10046e69  push    eax; unsigned int *
0x10046e6a  push    0F4h; unsigned int
0x10046e6f  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10046e74  test    eax, eax
0x10046e76  js      short loc_10046E88
0x10046e78  mov     eax, [ebp+var_2C]
0x10046e7b  lea     ecx, [eax+eax*2]
0x10046e7e  mov     eax, [edi]
0x10046e80  add     ecx, ecx
0x10046e82  mov     ecx, [eax+ecx*8+18h]
0x10046e86  jmp     short loc_10046E8A
0x10046e88  xor     ecx, ecx
0x10046e8a  push    [ebp+var_14]
0x10046e8d  mov     eax, [ebp+this]
0x10046e90  push    ecx
0x10046e91  mov     ecx, [ebp+arg_4]
0x10046e94  mov     eax, [eax+8]
0x10046e97  push    dword ptr [ecx+14h]
0x10046e9a  push    dword ptr [eax+14h]
0x10046e9d  push    dword ptr [eax+10h]
0x10046ea0  call    ds:__imp__JetRefreshLink@20; JetRefreshLink(x,x,x,x,x)
0x10046ea6  mov     [ebp+var_20], eax
0x10046ea9  mov     [ebp+var_10], eax
0x10046eac  test    eax, eax
0x10046eae  jns     short loc_10046EBA
0x10046eb0  mov     edi, 80004005h
0x10046eb5  jmp     loc_10046FA0
0x10046eba  mov     eax, [ebp+this]
0x10046ebd  mov     ecx, [ebp+arg_4]
0x10046ec0  mov     eax, [eax+8]
0x10046ec3  push    dword ptr [ecx+14h]; unsigned __int16 *
0x10046ec6  push    dword ptr [eax+14h]; unsigned int
0x10046ec9  push    ecx; unsigned int
0x10046eca  push    dword ptr [eax+10h]; unsigned int
0x10046ecd  lea     ecx, [ebp+var_40]; this
0x10046ed0  call    ?SetPropertiesToJetPropertyManager@CTableProperties@@QAEJKKKPAG@Z; CTableProperties::SetPropertiesToJetPropertyManager(ulong,ulong,ulong,ushort *)
0x10046ed5  mov     edi, eax
0x10046ed7  test    edi, edi
0x10046ed9  js      loc_10046F9D
0x10046edf  mov     eax, [ebp+this]
0x10046ee2  lea     ecx, [ebp+var_10]
0x10046ee5  push    ecx; int *
0x10046ee6  mov     ecx, [ebp+arg_4]
0x10046ee9  mov     eax, [eax+8]
0x10046eec  push    dword ptr [ecx+14h]; unsigned __int16 *
0x10046eef  lea     ecx, [ebp+var_40]; this
0x10046ef2  push    dword ptr [eax+14h]; unsigned int
0x10046ef5  push    dword ptr [eax+10h]; sesid
0x10046ef8  call    ?SetPropertiesInMSysObjects@CTableProperties@@QAEJKKPAGAAJ@Z; CTableProperties::SetPropertiesInMSysObjects(ulong,ulong,ushort *,long &)
0x10046efd  mov     edi, eax
0x10046eff  mov     eax, [ebp+var_10]
0x10046f02  test    edi, edi
0x10046f04  jns     short loc_10046F0D
0x10046f06  jmp     loc_10046FA0
0x10046f0b  xor     eax, eax
0x10046f0d  mov     ecx, [ebp+arg_8]
0x10046f10  test    ecx, ecx
0x10046f12  jz      short loc_10046F84
0x10046f14  push    dword ptr [ecx+14h]
0x10046f17  mov     eax, [ebp+this]
0x10046f1a  mov     ecx, [ebp+arg_4]
0x10046f1d  mov     eax, [eax+8]
0x10046f20  push    dword ptr [ecx+14h]
0x10046f23  push    dword ptr [eax+14h]
0x10046f26  push    dword ptr [eax+10h]
0x10046f29  call    ds:__imp__JetRenameTable@16; JetRenameTable(x,x,x,x)
0x10046f2f  cmp     eax, 0FFFFFAE7h
0x10046f34  jg      short loc_10046F46
0x10046f36  jz      short loc_10046F7D
0x10046f38  cmp     eax, 0FFFFF8EFh
0x10046f3d  jnz     short loc_10046F76
0x10046f3f  mov     edi, 80040E09h
0x10046f44  jmp     short loc_10046FA0
0x10046f46  cmp     eax, 0FFFFFAEAh
0x10046f4b  jg      short loc_10046F6B
0x10046f4d  jz      short loc_10046F64
0x10046f4f  cmp     eax, 0FFFFFAE8h
0x10046f54  jz      short loc_10046F64
0x10046f56  cmp     eax, 0FFFFFAE9h
0x10046f5b  jnz     short loc_10046F76
0x10046f5d  mov     edi, 80040E3Fh
0x10046f62  jmp     short loc_10046FA0
0x10046f64  mov     edi, 80040E40h
0x10046f69  jmp     short loc_10046FA0
0x10046f6b  cmp     eax, 0FFFFFC16h
0x10046f70  jz      short loc_10046F7D
0x10046f72  test    eax, eax
0x10046f74  jz      short loc_10046F84
  ... truncated ...
```
