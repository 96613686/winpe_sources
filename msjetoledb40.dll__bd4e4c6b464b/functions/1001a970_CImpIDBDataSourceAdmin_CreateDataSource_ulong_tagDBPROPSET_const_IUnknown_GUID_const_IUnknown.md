# CImpIDBDataSourceAdmin::CreateDataSource(ulong,tagDBPROPSET * const,IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x1001a970`
- end: `0x1001ae94`
- name: `?CreateDataSource@CImpIDBDataSourceAdmin@@UAGJKQAUtagDBPROPSET@@PAUIUnknown@@ABU_GUID@@PAPAU3@@Z`
- size: `1316`
- prototype: `int(CImpIDBDataSourceAdmin *__hidden this, unsigned int, struct tagDBPROPSET *const, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x10015c70`
- `0x10015dc0`
- `0x10016690`
- `0x10019070`
- `0x100196e0`
- `0x10019cd0`
- `0x1001a2a0`
- `0x1001a5e0`
- `0x1001a970`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x1001fd10`
- `0x10020410`
- `0x100204c0`
- `0x100205d0`
- `0x100207d0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001ae71`
- `KERNEL32!LeaveCriticalSection` at `0x1001ae71`
- `KERNEL32!EnterCriticalSection` at `0x1001a9fc`
- `KERNEL32!EnterCriticalSection` at `0x1001a9fc`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001a9dc`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001a9dc`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001ad03`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001ae1d`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001ad03`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001ae1d`
- `msjet40!__imp__JetCreateDatabase@20` at `0x1001ace7`
- `msjet40!__imp__JetCreateDatabase@20` at `0x1001ace7`
- `msjet40!__imp__JetEndSession@8` at `0x1001ad1e`
- `msjet40!__imp__JetEndSession@8` at `0x1001ae2e`
- `msjet40!__imp__JetEndSession@8` at `0x1001ad1e`
- `msjet40!__imp__JetEndSession@8` at `0x1001ae2e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001adf4`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001adf4`
- `msjet40!__imp__JetCreateSystemDatabase@24` at `0x1001ac9a`
- `msjet40!__imp__JetCreateSystemDatabase@24` at `0x1001ac9a`

## pseudocode

```c
int __stdcall CImpIDBDataSourceAdmin::CreateDataSource(
        CImpIDBDataSourceAdmin *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3,
        struct IUnknown *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  struct _GUID *v6; // esi
  JET_DBID v7; // eax
  int v8; // edi
  JET_SESID v9; // ecx
  int v10; // ecx
  LPARAM v11; // eax
  LPARAM v12; // edi
  CDataSource *v13; // ecx
  __int128 *v14; // edx
  const GUID *v15; // ecx
  unsigned int v16; // edi
  bool v17; // cf
  LPCRITICAL_SECTION v18; // eax
  unsigned int v19; // ecx
  int v20; // eax
  unsigned int v21; // eax
  bool v22; // zf
  int v23; // eax
  unsigned int SystemDatabase; // eax
  unsigned int v25; // eax
  CDBSession *v26; // eax
  CDBSession *v27; // eax
  const struct _GUID *v29; // [esp+0h] [ebp-6Ch]
  const struct _GUID *v30; // [esp+4h] [ebp-68h]
  __int128 v31; // [esp+Ch] [ebp-60h] BYREF
  _DWORD v32[4]; // [esp+1Ch] [ebp-50h] BYREF
  struct _GUID *v33; // [esp+2Ch] [ebp-40h]
  unsigned int v34; // [esp+30h] [ebp-3Ch] BYREF
  int v35; // [esp+34h] [ebp-38h]
  int v36; // [esp+38h] [ebp-34h]
  unsigned __int16 *v37; // [esp+3Ch] [ebp-30h] BYREF
  unsigned __int16 *v38; // [esp+40h] [ebp-2Ch] BYREF
  LPARAM dwInitParam; // [esp+44h] [ebp-28h]
  void *Block; // [esp+48h] [ebp-24h]
  JoltProperties *v41; // [esp+4Ch] [ebp-20h]
  int v42; // [esp+50h] [ebp-1Ch]
  unsigned int v43; // [esp+54h] [ebp-18h] BYREF
  JET_DBID dbid; // [esp+58h] [ebp-14h] BYREF
  JET_SESID sesid; // [esp+5Ch] [ebp-10h] BYREF
  int v46; // [esp+68h] [ebp-4h]

  v43 = 0;
  dwInitParam = 0;
  Block = 0;
  sesid = -1;
  dbid = -1;
  memset(&v32[1], 0, 12);
  v32[0] = &CDBDataSourceAdmin::`vftable';
  v46 = 0;
  v37 = 0;
  v38 = 0;
  v35 = 1;
  SetErrorInfo(0, 0);
  if ( a6 )
    *a6 = 0;
  v33 = (struct _GUID *)(*((_DWORD *)this + 2) + 100);
  v6 = v33;
  EnterCriticalSection((LPCRITICAL_SECTION)v33);
  LOBYTE(v46) = 1;
  if ( a2 && !a3 )
  {
LABEL_5:
    v7 = dbid;
    v8 = -2147024809;
    v9 = sesid;
    goto LABEL_68;
  }
  v10 = 0;
  if ( a2 )
  {
    while ( !a3[v10].cProperties || a3[v10].rgProperties )
    {
      if ( ++v10 >= a2 )
        goto LABEL_10;
    }
    goto LABEL_5;
  }
LABEL_10:
  v8 = CSettableProperties::FInit((CSettableProperties *)v32);
  if ( v8 < 0 )
    goto LABEL_67;
  v11 = *((_DWORD *)this + 2);
  dwInitParam = v11;
  if ( *(_DWORD *)(v11 + 128) == 1 )
  {
    v7 = dbid;
    v8 = -2147217838;
    v9 = sesid;
    goto LABEL_68;
  }
  v35 = 0;
  v8 = CSettableProperties::CopyFrom((CSettableProperties *)v32, (const struct CSettableProperties *)(v11 + 152));
  if ( v8 < 0 )
    goto LABEL_67;
  v8 = CSettableProperties::SetProperties((CSettableProperties *)v32, a2, a3, 0);
  if ( v8 < 0 )
    goto LABEL_67;
  v8 = CSettableProperties::CopyFrom(
         (CSettableProperties *)(dwInitParam + 152),
         (const struct CSettableProperties *)v32);
  if ( v8 < 0 )
    goto LABEL_67;
  v12 = dwInitParam;
  if ( CDataSource::UtilInitialize(dwInitParam, 0, (int *)&v43) >= 0 )
  {
    JoltProperties::GetStrValue(*(JoltProperties **)(*((_DWORD *)this + 2) + 160), 0x3Bu, &v37);
    v8 = CDataSource::BuildConnectString(v13, &v38, (struct CDBInitProperties *)(v12 + 152));
    if ( v8 < 0 )
      goto LABEL_49;
    if ( CDataSource::JETBeginSession((JoltProperties **)dwInitParam, &sesid, (int *)&v43) < 0 )
    {
      v8 = -2147217843;
      goto LABEL_49;
    }
    v14 = &v31;
    v36 = 0;
    v15 = &DBPROPSET_DBINIT;
    v42 = 0;
    v16 = 12;
    v31 = *(_OWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 160) + 20);
    do
    {
      if ( v15->Data1 != *(_DWORD *)v14 )
        goto LABEL_48;
      v15 = (const GUID *)((char *)v15 + 4);
      v14 = (__int128 *)((char *)v14 + 4);
      v17 = v16 < 4;
      v16 -= 4;
    }
    while ( !v17 );
    v8 = 0;
    v41 = *(JoltProperties **)(*((_DWORD *)this + 2) + 164);
    if ( JoltProperties::BinarySearch(v41, 0x103u, &v34) < 0 )
    {
      v18 = (LPCRITICAL_SECTION)v33;
      v8 = -2147467259;
    }
    else
    {
      v18 = (LPCRITICAL_SECTION)(48 * v34 + *((_DWORD *)v41 + 4) + 16);
    }
    switch ( v18->RecursionCount )
    {
      case 0:
      case 5:
        break;
      case 1:
        v42 = 2;
        break;
      case 2:
        v42 = 4;
        break;
      case 3:
        v42 = 32;
        break;
      case 4:
        v42 = 512;
        break;
      default:
        v36 = 1;
        break;
    }
    if ( JoltProperties::BinarySearch(v41, 0x10Eu, &v34) < 0 )
      v19 = 0;
    else
      v19 = *((_DWORD *)v41 + 4) + 48 * v34;
    v20 = v42 | 0x80;
    if ( *(_WORD *)(v19 + 24) != 0xFFFF )
      v20 = v42;
    v42 = v20;
    if ( JoltProperties::BinarySearch(v41, 0x10Fu, &v34) < 0 )
      v21 = 0;
    else
      v21 = *((_DWORD *)v41 + 4) + 48 * v34;
    v22 = *(_WORD *)(v21 + 24) == 0xFFFF;
    v23 = v42;
    if ( v22 )
      v23 = v42 | 1;
    if ( v36 == 1 )
    {
LABEL_48:
      v8 = -2147467259;
      goto LABEL_49;
    }
    if ( v8 < 0 )
      goto LABEL_49;
    if ( (v23 & 0x80u) == 0 )
    {
      v25 = JetCreateDatabase(sesid, v37, v38, &dbid, v23);
      v43 = v25;
      if ( v25 != -1201 )
      {
        if ( v25 )
          goto LABEL_48;
        v43 = JetCloseDatabase(sesid, dbid, 1u);
        if ( v43 )
          goto LABEL_48;
        dbid = -1;
        goto LABEL_56;
      }
    }
    else
    {
      SystemDatabase = JetCreateSystemDatabase(v37, v38, L"Serial", L"User", L"Org", v23);
      v43 = SystemDatabase;
      if ( SystemDatabase != -1201 )
      {
        if ( SystemDatabase )
          goto LABEL_48;
LABEL_56:
        v8 = 0;
        JetEndSession(sesid, 1u);
        sesid = -1;
        if ( !a6 )
          goto LABEL_49;
        v8 = CDataSource::OpenSessionAndDatabase(*((CDataSource **)this + 2), 0, v6, (int *)&v43);
        v34 = v8;
        if ( v8 < 0 )
          goto LABEL_49;
        v26 = (CDBSession *)operator new(0x9Cu);
        v36 = (int)v26;
        if ( v26 )
        {
          v27 = CDBSession::CDBSession(v26, a4);
          Block = v27;
          if ( v27 )
          {
            if ( CDBSession::FInit(
                   v27,
                   *((struct CDataSource **)this + 2),
                   *(_DWORD *)(*((_DWORD *)this + 2) + 144),
                   *(_DWORD *)(*((_DWORD *)this + 2) + 148)) >= 0 )
            {
              (**(void (__thiscall ***)(_DWORD, void *, const struct _GUID *, struct IUnknown **))Block)(
                **(_DWORD **)Block,
                Block,
                a5,
                a6);
              if ( *a6 )
                v8 = v34;
              else
                v8 = -2147467262;
              goto LABEL_49;
            }
            goto LABEL_48;
          }
        }
        else
        {
          Block = 0;
        }
        v8 = -2147024882;
        goto LABEL_49;
      }
    }
    v8 = -2147217897;
    goto LABEL_49;
  }
  v8 = -2147217843;
LABEL_49:
  if ( v43 )
  {
    CExtError::SendJetErrortoOLEAuto(v43, (int)&IID_IDBDataSourceAdmin, (int)v29, v30);
    goto LABEL_70;
  }
  if ( v8 >= 0 )
    goto LABEL_79;
LABEL_67:
  v7 = dbid;
  v9 = sesid;
  if ( v8 != -2147024882 )
  {
LABEL_68:
    if ( !JetGetDatabaseInfo(v9, v7, &v34, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBDataSourceAdmin, 0, v29, (int)v30);
  }
LABEL_70:
  if ( v8 < 0 )
  {
    if ( dbid != -1 )
      JetCloseDatabase(sesid, dbid, 1u);
    if ( sesid != -1 )
      JetEndSession(sesid, 1u);
    if ( Block )
    {
      CDBSession::~CDBSession((CDBSession *)Block);
      operator delete(Block);
    }
    if ( !v35 )
      CDataSource::UtilUninitialize((CDataSource *)dwInitParam);
  }
LABEL_79:
  if ( v38 )
    operator delete(v38);
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v32);
  return v8;
}

```

## disassembly

```asm
0x1001a970  mov     edi, edi
0x1001a972  push    ebp
0x1001a973  mov     ebp, esp
0x1001a975  push    0FFFFFFFFh
0x1001a977  push    offset ?CreateDataSource@CImpIDBDataSourceAdmin@@UAGJKQAUtagDBPROPSET@@PAUIUnknown@@ABU_GUID@@PAPAU3@@Z_SEH
0x1001a97c  mov     eax, large fs:0
0x1001a982  push    eax
0x1001a983  sub     esp, 54h
0x1001a986  push    esi
0x1001a987  push    edi; int
0x1001a988  mov     eax, ___security_cookie
0x1001a98d  xor     eax, ebp
0x1001a98f  push    eax; struct _GUID *
0x1001a990  lea     eax, [ebp+var_C]
0x1001a993  mov     large fs:0, eax
0x1001a999  xor     eax, eax
0x1001a99b  mov     [ebp+var_18], 0
0x1001a9a2  mov     [ebp+dwInitParam], 0
0x1001a9a9  mov     [ebp+Block], eax
0x1001a9ac  mov     [ebp+sesid], 0FFFFFFFFh
0x1001a9b3  mov     [ebp+dbid], 0FFFFFFFFh
0x1001a9ba  mov     [ebp+var_4C], eax
0x1001a9bd  mov     [ebp+var_48], eax
0x1001a9c0  mov     [ebp+var_44], eax
0x1001a9c3  mov     [ebp+var_50], offset ??_7CDBDataSourceAdmin@@6B@; const CDBDataSourceAdmin::`vftable'
0x1001a9ca  push    eax; perrinfo
0x1001a9cb  mov     [ebp+var_4], eax
0x1001a9ce  push    eax; dwReserved
0x1001a9cf  mov     [ebp+var_30], eax
0x1001a9d2  mov     [ebp+var_2C], eax
0x1001a9d5  mov     [ebp+var_38], 1
0x1001a9dc  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001a9e2  mov     eax, [ebp+arg_14]
0x1001a9e5  test    eax, eax
0x1001a9e7  jz      short loc_1001A9EF
0x1001a9e9  mov     dword ptr [eax], 0
0x1001a9ef  mov     ecx, [ebp+this]
0x1001a9f2  mov     esi, [ecx+8]
0x1001a9f5  add     esi, 64h ; 'd'
0x1001a9f8  push    esi; lpCriticalSection
0x1001a9f9  mov     [ebp+var_40], esi
0x1001a9fc  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001aa02  mov     edx, [ebp+arg_4]
0x1001aa05  mov     edi, [ebp+arg_8]
0x1001aa08  mov     byte ptr [ebp+var_4], 1
0x1001aa0c  test    edx, edx
0x1001aa0e  jz      short loc_1001AA24
0x1001aa10  test    edi, edi
0x1001aa12  jnz     short loc_1001AA24
0x1001aa14  mov     eax, [ebp+dbid]
0x1001aa17  mov     edi, 80070057h
0x1001aa1c  mov     ecx, [ebp+sesid]
0x1001aa1f  jmp     loc_1001ADEA
0x1001aa24  xor     ecx, ecx
0x1001aa26  test    edx, edx
0x1001aa28  jz      short loc_1001AA45
0x1001aa2a  nop     word ptr [eax+eax+00h]
0x1001aa30  lea     eax, [ecx+ecx*2]
0x1001aa33  cmp     dword ptr [edi+eax*8+4], 0
0x1001aa38  jz      short loc_1001AA40
0x1001aa3a  cmp     dword ptr [edi+eax*8], 0
0x1001aa3e  jz      short loc_1001AA14
0x1001aa40  inc     ecx
0x1001aa41  cmp     ecx, edx
0x1001aa43  jb      short loc_1001AA30
0x1001aa45  lea     ecx, [ebp+var_50]; this
0x1001aa48  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x1001aa4d  mov     edi, eax
0x1001aa4f  test    edi, edi
0x1001aa51  js      loc_1001ADDC
0x1001aa57  mov     eax, [ebp+this]
0x1001aa5a  mov     eax, [eax+8]
0x1001aa5d  mov     [ebp+dwInitParam], eax
0x1001aa60  cmp     dword ptr [eax+80h], 1
0x1001aa67  jnz     short loc_1001AA79
0x1001aa69  mov     eax, [ebp+dbid]
0x1001aa6c  mov     edi, 80040E52h
0x1001aa71  mov     ecx, [ebp+sesid]
0x1001aa74  jmp     loc_1001ADEA
0x1001aa79  add     eax, 98h
0x1001aa7e  mov     [ebp+var_38], 0
0x1001aa85  push    eax; struct CSettableProperties *
0x1001aa86  lea     ecx, [ebp+var_50]; this
0x1001aa89  call    ?CopyFrom@CSettableProperties@@QAEJABV1@@Z; CSettableProperties::CopyFrom(CSettableProperties const &)
0x1001aa8e  mov     edi, eax
0x1001aa90  test    edi, edi
0x1001aa92  js      loc_1001ADDC
0x1001aa98  push    0; struct CDBSession *
0x1001aa9a  push    [ebp+arg_8]; struct tagDBPROPSET *
0x1001aa9d  lea     ecx, [ebp+var_50]; this
0x1001aaa0  push    [ebp+arg_4]; unsigned int
0x1001aaa3  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1001aaa8  mov     edi, eax
0x1001aaaa  test    edi, edi
0x1001aaac  js      loc_1001ADDC
0x1001aab2  mov     ecx, [ebp+dwInitParam]
0x1001aab5  lea     eax, [ebp+var_50]
0x1001aab8  push    eax; struct CSettableProperties *
0x1001aab9  lea     ecx, [ecx+98h]; this
0x1001aabf  call    ?CopyFrom@CSettableProperties@@QAEJABV1@@Z; CSettableProperties::CopyFrom(CSettableProperties const &)
0x1001aac4  mov     edi, eax
0x1001aac6  test    edi, edi
0x1001aac8  js      loc_1001ADDC
0x1001aace  mov     edi, [ebp+dwInitParam]
0x1001aad1  lea     eax, [ebp+var_18]
0x1001aad4  push    eax; int *
0x1001aad5  push    0; int
0x1001aad7  mov     ecx, edi; dwInitParam
0x1001aad9  call    ?UtilInitialize@CDataSource@@QAEJHAAJ@Z; CDataSource::UtilInitialize(int,long &)
0x1001aade  test    eax, eax
0x1001aae0  jns     short loc_1001AAEC
0x1001aae2  mov     edi, 80040E4Dh
0x1001aae7  jmp     loc_1001ACB3
0x1001aaec  lea     eax, [ebp+var_30]
0x1001aaef  push    eax; unsigned __int16 **
0x1001aaf0  mov     eax, [ebp+this]
0x1001aaf3  push    3Bh ; ';'; unsigned int
0x1001aaf5  mov     ecx, [eax+8]
0x1001aaf8  mov     ecx, [ecx+0A0h]; this
0x1001aafe  call    ?GetStrValue@JoltProperties@@QBEJKAAPAG@Z; JoltProperties::GetStrValue(ulong,ushort * &)
0x1001ab03  lea     eax, [edi+98h]
0x1001ab09  push    eax; struct CDBInitProperties *
0x1001ab0a  lea     eax, [ebp+var_2C]
0x1001ab0d  push    eax; unsigned __int16 **
0x1001ab0e  call    ?BuildConnectString@CDataSource@@QAEJAAPAGAAVCDBInitProperties@@@Z; CDataSource::BuildConnectString(ushort * &,CDBInitProperties &)
0x1001ab13  mov     edi, eax
0x1001ab15  test    edi, edi
0x1001ab17  js      loc_1001ACB3
0x1001ab1d  mov     ecx, [ebp+dwInitParam]; this
0x1001ab20  lea     eax, [ebp+var_18]
0x1001ab23  push    eax; int *
0x1001ab24  lea     eax, [ebp+sesid]
0x1001ab27  push    eax; unsigned int *
0x1001ab28  call    ?JETBeginSession@CDataSource@@QAEJAAKAAJ@Z; CDataSource::JETBeginSession(ulong &,long &)
0x1001ab2d  test    eax, eax
0x1001ab2f  jns     short loc_1001AB3B
0x1001ab31  mov     edi, 80040E4Dh
0x1001ab36  jmp     loc_1001ACB3
0x1001ab3b  mov     eax, [ebp+this]
0x1001ab3e  lea     edx, [ebp+var_60]
0x1001ab41  mov     [ebp+var_34], 0
0x1001ab48  mov     ecx, offset _DBPROPSET_DBINIT
0x1001ab4d  mov     [ebp+var_1C], 0
0x1001ab54  mov     edi, 0Ch
0x1001ab59  mov     eax, [eax+8]
0x1001ab5c  mov     eax, [eax+0A0h]
0x1001ab62  movups  xmm0, xmmword ptr [eax+14h]
0x1001ab66  movups  [ebp+var_60], xmm0
0x1001ab6a  nop     word ptr [eax+eax+00h]
0x1001ab70  mov     eax, [ecx]
0x1001ab72  cmp     eax, [edx]
0x1001ab74  jnz     loc_1001ACAE
0x1001ab7a  add     ecx, 4
0x1001ab7d  add     edx, 4
0x1001ab80  sub     edi, 4
0x1001ab83  jnb     short loc_1001AB70
0x1001ab85  mov     ecx, [ebp+this]
0x1001ab88  xor     edi, edi
0x1001ab8a  mov     eax, [ecx+8]
0x1001ab8d  lea     ecx, [ebp+var_3C]
0x1001ab90  push    ecx; unsigned int *
0x1001ab91  push    103h; unsigned int
0x1001ab96  mov     eax, [eax+0A4h]
0x1001ab9c  mov     ecx, eax; this
0x1001ab9e  mov     [ebp+var_20], eax
0x1001aba1  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001aba6  mov     edx, [ebp+var_20]
0x1001aba9  test    eax, eax
0x1001abab  js      short loc_1001ABC0
0x1001abad  mov     eax, [ebp+var_3C]
0x1001abb0  lea     ecx, [eax+eax*2]
0x1001abb3  mov     eax, [edx+10h]
0x1001abb6  shl     ecx, 4
0x1001abb9  add     eax, 10h
0x1001abbc  add     eax, ecx
0x1001abbe  jmp     short loc_1001ABC8
0x1001abc0  mov     eax, [ebp+var_40]
0x1001abc3  mov     edi, 80004005h
0x1001abc8  mov     eax, [eax+8]
0x1001abcb  cmp     eax, 5; switch 6 cases
0x1001abce  ja      short def_1001ABD0; jumptable 1001ABD0 default case
0x1001abd0  jmp     ds:jpt_1001ABD0[eax*4]; switch jump
0x1001abd7  mov     [ebp+var_1C], 2; jumptable 1001ABD0 case 1
0x1001abde  jmp     short loc_1001AC02; jumptable 1001ABD0 cases 0,5
0x1001abe0  mov     [ebp+var_1C], 4; jumptable 1001ABD0 case 2
0x1001abe7  jmp     short loc_1001AC02; jumptable 1001ABD0 cases 0,5
0x1001abe9  mov     [ebp+var_1C], 20h ; ' '; jumptable 1001ABD0 case 3
0x1001abf0  jmp     short loc_1001AC02; jumptable 1001ABD0 cases 0,5
0x1001abf2  mov     [ebp+var_1C], 200h; jumptable 1001ABD0 case 4
0x1001abf9  jmp     short loc_1001AC02; jumptable 1001ABD0 cases 0,5
0x1001abfb  mov     [ebp+var_34], 1; jumptable 1001ABD0 default case
0x1001ac02  lea     eax, [ebp+var_3C]; jumptable 1001ABD0 cases 0,5
0x1001ac05  mov     ecx, edx; this
0x1001ac07  push    eax; unsigned int *
0x1001ac08  push    10Eh; unsigned int
0x1001ac0d  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001ac12  test    eax, eax
0x1001ac14  js      short loc_1001AC27
0x1001ac16  mov     eax, [ebp+var_3C]
0x1001ac19  mov     edx, [ebp+var_20]
0x1001ac1c  lea     ecx, [eax+eax*2]
0x1001ac1f  shl     ecx, 4
0x1001ac22  add     ecx, [edx+10h]
0x1001ac25  jmp     short loc_1001AC29
0x1001ac27  xor     ecx, ecx
0x1001ac29  mov     eax, [ebp+var_1C]
0x1001ac2c  or      edx, 0FFFFFFFFh
0x1001ac2f  or      eax, 80h
0x1001ac34  cmp     dx, [ecx+18h]
0x1001ac38  mov     ecx, [ebp+var_20]; this
0x1001ac3b  cmovnz  eax, [ebp+var_1C]
0x1001ac3f  mov     [ebp+var_1C], eax
0x1001ac42  lea     eax, [ebp+var_3C]
0x1001ac45  push    eax; unsigned int *
0x1001ac46  push    10Fh; unsigned int
0x1001ac4b  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001ac50  test    eax, eax
0x1001ac52  js      short loc_1001AC65
0x1001ac54  mov     eax, [ebp+var_3C]
0x1001ac57  mov     edx, [ebp+var_20]
0x1001ac5a  lea     eax, [eax+eax*2]
0x1001ac5d  shl     eax, 4
0x1001ac60  add     eax, [edx+10h]
0x1001ac63  jmp     short loc_1001AC67
0x1001ac65  xor     eax, eax
0x1001ac67  or      ecx, 0FFFFFFFFh
0x1001ac6a  cmp     cx, [eax+18h]
0x1001ac6e  mov     eax, [ebp+var_1C]
0x1001ac71  jnz     short loc_1001AC76
0x1001ac73  or      eax, 1
0x1001ac76  cmp     [ebp+var_34], 1
0x1001ac7a  jz      short loc_1001ACAE
0x1001ac7c  test    edi, edi
0x1001ac7e  js      short loc_1001ACB3
0x1001ac80  push    eax
0x1001ac81  test    al, al
0x1001ac83  jns     short loc_1001ACDA
0x1001ac85  push    offset aOrg; "Org"
0x1001ac8a  push    offset aUser; "User"
0x1001ac8f  push    offset aSerial; "Serial"
0x1001ac94  push    [ebp+var_2C]
0x1001ac97  push    [ebp+var_30]
0x1001ac9a  call    ds:__imp__JetCreateSystemDatabase@24; JetCreateSystemDatabase(x,x,x,x,x,x)
0x1001aca0  mov     [ebp+var_18], eax
0x1001aca3  cmp     eax, 0FFFFFB4Fh
0x1001aca8  jz      short loc_1001ACD3
0x1001acaa  test    eax, eax
0x1001acac  jz      short loc_1001AD17
0x1001acae  mov     edi, 80004005h
0x1001acb3  mov     eax, [ebp+var_18]
0x1001acb6  test    eax, eax
0x1001acb8  jz      loc_1001ADD4
0x1001acbe  mov     ecx, [ebp+sesid]
0x1001acc1  mov     edx, edi
0x1001acc3  push    offset _IID_IDBDataSourceAdmin; int
0x1001acc8  push    eax; unsigned int
0x1001acc9  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1001acce  jmp     loc_1001AE0B
0x1001acd3  mov     edi, 80040E17h
0x1001acd8  jmp     short loc_1001ACB3
0x1001acda  lea     eax, [ebp+dbid]
0x1001acdd  push    eax
0x1001acde  push    [ebp+var_2C]
0x1001ace1  push    [ebp+var_30]
0x1001ace4  push    [ebp+sesid]
0x1001ace7  call    ds:__imp__JetCreateDatabase@20; JetCreateDatabase(x,x,x,x,x)
0x1001aced  mov     [ebp+var_18], eax
0x1001acf0  cmp     eax, 0FFFFFB4Fh
0x1001acf5  jz      short loc_1001ACD3
0x1001acf7  test    eax, eax
0x1001acf9  jnz     short loc_1001ACAE
0x1001acfb  push    1; grbit
0x1001acfd  push    [ebp+dbid]; dbid
0x1001ad00  push    [ebp+sesid]; sesid
0x1001ad03  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x1001ad09  mov     [ebp+var_18], eax
0x1001ad0c  test    eax, eax
0x1001ad0e  jnz     short loc_1001ACAE
0x1001ad10  mov     [ebp+dbid], 0FFFFFFFFh
0x1001ad17  push    1; grbit
0x1001ad19  push    [ebp+sesid]; sesid
0x1001ad1c  xor     edi, edi
0x1001ad1e  call    ds:__imp__JetEndSession@8; JetEndSession(x,x)
0x1001ad24  mov     [ebp+sesid], 0FFFFFFFFh
0x1001ad2b  cmp     [ebp+arg_14], edi
0x1001ad2e  jz      short loc_1001ACB3
0x1001ad30  lea     eax, [ebp+var_18]
0x1001ad33  push    eax; int *
0x1001ad34  mov     eax, [ebp+this]
0x1001ad37  mov     ecx, [eax+8]; this
0x1001ad3a  call    ?OpenSessionAndDatabase@CDataSource@@QAEJAAJ@Z; CDataSource::OpenSessionAndDatabase(long &)
0x1001ad3f  mov     edi, eax
0x1001ad41  mov     [ebp+var_3C], edi
0x1001ad44  test    edi, edi
0x1001ad46  js      loc_1001ACB3
0x1001ad4c  push    9Ch; Size
0x1001ad51  call    ??2@YAPAXI@Z; operator new(uint)
0x1001ad56  add     esp, 4
0x1001ad59  mov     [ebp+var_34], eax
0x1001ad5c  test    eax, eax
  ... truncated ...
```
