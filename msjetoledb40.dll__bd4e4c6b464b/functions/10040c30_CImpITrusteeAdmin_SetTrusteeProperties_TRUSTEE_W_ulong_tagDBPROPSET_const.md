# CImpITrusteeAdmin::SetTrusteeProperties(_TRUSTEE_W *,ulong,tagDBPROPSET * const)

- ea: `0x10040c30`
- end: `0x10040ea9`
- name: `?SetTrusteeProperties@CImpITrusteeAdmin@@UAGJPAU_TRUSTEE_W@@KQAUtagDBPROPSET@@@Z`
- size: `633`
- prototype: `int(CImpITrusteeAdmin *__hidden this, struct _TRUSTEE_W *, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x100196e0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001fae0`
- `0x100201c0`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x10023e00`
- `0x10040c30`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10040e85`
- `KERNEL32!LeaveCriticalSection` at `0x10040e85`
- `KERNEL32!EnterCriticalSection` at `0x10040c87`
- `KERNEL32!EnterCriticalSection` at `0x10040c87`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10040c74`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10040c74`
- `msjet40!__imp__JetChangeUserPassword@16` at `0x10040dff`
- `msjet40!__imp__JetChangeUserPassword@16` at `0x10040dff`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10040d13`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10040d13`

## pseudocode

```c
int __stdcall CImpITrusteeAdmin::SetTrusteeProperties(
        CImpITrusteeAdmin *this,
        struct _TRUSTEE_W *a2,
        unsigned int a3,
        struct tagDBPROPSET *const a4)
{
  unsigned int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // esi
  int v6; // ecx
  int v7; // edx
  int v8; // ecx
  int v9; // ebx
  TRUSTEE_TYPE TrusteeType; // ecx
  const struct DBInfoProps *v11; // ecx
  unsigned __int16 *WCHAR; // edi
  unsigned __int16 *v13; // eax
  int v14; // eax
  bool v15; // zf
  const struct _GUID *v17; // [esp+0h] [ebp-3Ch]
  const struct _GUID *v18; // [esp+4h] [ebp-38h]
  _DWORD v19[2]; // [esp+10h] [ebp-2Ch] BYREF
  JoltProperties *v20; // [esp+18h] [ebp-24h]
  int v21; // [esp+1Ch] [ebp-20h]
  LPCRITICAL_SECTION v22; // [esp+20h] [ebp-1Ch]
  int v23; // [esp+24h] [ebp-18h] BYREF
  _DWORD *v24; // [esp+28h] [ebp-14h]
  int v25; // [esp+2Ch] [ebp-10h] BYREF
  int v26; // [esp+38h] [ebp-4h]

  v4 = 0;
  v19[0] = &CExistingTrusteeProperties::`vftable';
  v25 = 0;
  v19[1] = 0;
  v20 = 0;
  v21 = 0;
  v26 = 0;
  SetErrorInfo(0, 0);
  v22 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 100);
  v5 = v22;
  EnterCriticalSection(v22);
  LOBYTE(v26) = 1;
  if ( a2 && (!a3 || a4) )
  {
    v6 = 0;
    if ( a3 )
    {
      while ( a4[v6].rgProperties || !a4[v6].cProperties )
      {
        if ( ++v6 >= a3 )
          goto LABEL_8;
      }
      goto LABEL_39;
    }
LABEL_8:
    v7 = *((_DWORD *)this + 2);
    v15 = *(_DWORD *)(v7 + 68) == -1;
    v8 = *(_DWORD *)(v7 + 80);
    v23 = *(_DWORD *)(v8 + 96);
    v24 = (_DWORD *)(v7 + 68);
    if ( v15 )
    {
      v9 = CDataSource::JETBeginSession((JoltProperties **)v8, (unsigned int *)(v7 + 68), &v25);
      if ( v9 < 0 )
      {
        v4 = v25;
        *v24 = -1;
        goto LABEL_34;
      }
      v4 = JetSetSystemParameter(&v23, *v24, 59, 1, 0);
    }
    if ( a2->pMultipleTrustee
      || a2->MultipleTrusteeOperation
      || (TrusteeType = a2->TrusteeType, TrusteeType != TRUSTEE_IS_USER) && TrusteeType != TRUSTEE_IS_GROUP
      || a2->TrusteeForm != TRUSTEE_IS_NAME
      || !a2->ptstrName )
    {
      v9 = -2147217814;
      goto LABEL_34;
    }
    v9 = CSettableProperties::FInit((CSettableProperties *)v19);
    if ( v9 < 0 )
      goto LABEL_34;
    v9 = CTrusteeProperties::CopyPropertiesFromStaticTable((CTrusteeProperties *)v19, v11);
    if ( v9 < 0 )
      goto LABEL_34;
    v9 = CSettableProperties::SetProperties((CSettableProperties *)v19, a3, a4, 0);
    if ( v9 < 0 )
      goto LABEL_34;
    if ( a2->TrusteeType == TRUSTEE_IS_USER )
    {
      if ( (*((_DWORD *)JoltProperties::GetRowbyProp(v20, 0xF2u) + 10) & 1) == 0
        || (*((_DWORD *)JoltProperties::GetRowbyProp(v20, 0xF3u) + 10) & 1) == 0 )
      {
        goto LABEL_34;
      }
      WCHAR = JoltProperties::GetWCHAR(v20, 0xF2u);
      v13 = JoltProperties::GetWCHAR(v20, 0xF3u);
      v14 = JetChangeUserPassword(*(_DWORD *)(*((_DWORD *)this + 2) + 68), a2->ptstrName, WCHAR, v13);
      v4 = v14;
      if ( v14 > -1809 )
      {
        if ( v14 != -1802 )
        {
          v15 = v14 == 0;
          if ( !v14 )
            goto LABEL_37;
          if ( v14 >= 0 )
          {
LABEL_35:
            if ( !v15 )
            {
              CExtError::SendJetErrortoOLEAuto(
                v9,
                *(char **)(*((_DWORD *)this + 2) + 68),
                v4,
                (int)&IID_ITrusteeAdmin,
                (int)v17,
                v18);
              goto LABEL_41;
            }
LABEL_37:
            if ( v9 >= 0 )
              goto LABEL_41;
            goto LABEL_40;
          }
LABEL_31:
          v9 = -2147467259;
LABEL_34:
          v15 = v4 == 0;
          goto LABEL_35;
        }
      }
      else if ( v14 != -1809 )
      {
        switch ( v14 )
        {
          case -1907:
          case -1905:
          case -1904:
            goto LABEL_32;
          case -1903:
            v9 = -2147217813;
            break;
          default:
            goto LABEL_31;
        }
        goto LABEL_34;
      }
    }
LABEL_32:
    v9 = -2147217911;
    goto LABEL_34;
  }
LABEL_39:
  v9 = -2147024809;
LABEL_40:
  CExtError::SendHRtoOLEAuto(v9, (__int128 *)&IID_ITrusteeAdmin, 0, v17, (int)v18);
LABEL_41:
  if ( v5 )
    LeaveCriticalSection(v5);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v19);
  return v9;
}

```

## disassembly

```asm
0x10040c30  mov     edi, edi
0x10040c32  push    ebp
0x10040c33  mov     ebp, esp
0x10040c35  push    0FFFFFFFFh
0x10040c37  push    offset ?SetTrusteeProperties@CImpITrusteeAdmin@@UAGJPAU_TRUSTEE_W@@KQAUtagDBPROPSET@@@Z_SEH
0x10040c3c  mov     eax, large fs:0
0x10040c42  push    eax
0x10040c43  sub     esp, 20h
0x10040c46  push    ebx
0x10040c47  push    esi
0x10040c48  push    edi; int
0x10040c49  mov     eax, ___security_cookie
0x10040c4e  xor     eax, ebp
0x10040c50  push    eax; struct _GUID *
0x10040c51  lea     eax, [ebp+var_C]
0x10040c54  mov     large fs:0, eax
0x10040c5a  xor     edi, edi
0x10040c5c  mov     [ebp+var_2C], offset ??_7CExistingTrusteeProperties@@6B@; const CExistingTrusteeProperties::`vftable'
0x10040c63  mov     [ebp+var_10], edi
0x10040c66  mov     [ebp+var_28], edi
0x10040c69  mov     [ebp+var_24], edi
0x10040c6c  mov     [ebp+var_20], edi
0x10040c6f  push    edi; perrinfo
0x10040c70  push    edi; dwReserved
0x10040c71  mov     [ebp+var_4], edi
0x10040c74  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10040c7a  mov     esi, [ebp+this]
0x10040c7d  mov     esi, [esi+8]
0x10040c80  add     esi, 64h ; 'd'
0x10040c83  push    esi; lpCriticalSection
0x10040c84  mov     [ebp+var_1C], esi
0x10040c87  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10040c8d  mov     byte ptr [ebp+var_4], 1
0x10040c91  cmp     [ebp+arg_4], edi
0x10040c94  jz      loc_10040E6D
0x10040c9a  mov     edx, [ebp+arg_8]
0x10040c9d  mov     ebx, [ebp+arg_C]
0x10040ca0  test    edx, edx
0x10040ca2  jz      short loc_10040CAC
0x10040ca4  test    ebx, ebx
0x10040ca6  jz      loc_10040E6D
0x10040cac  xor     ecx, ecx
0x10040cae  test    edx, edx
0x10040cb0  jz      short loc_10040CCB
0x10040cb2  lea     eax, [ecx+ecx*2]
0x10040cb5  cmp     dword ptr [ebx+eax*8], 0
0x10040cb9  jnz     short loc_10040CC6
0x10040cbb  cmp     dword ptr [ebx+eax*8+4], 0
0x10040cc0  jnz     loc_10040E6D
0x10040cc6  inc     ecx
0x10040cc7  cmp     ecx, edx
0x10040cc9  jb      short loc_10040CB2
0x10040ccb  mov     eax, [ebp+this]
0x10040cce  mov     edx, [eax+8]
0x10040cd1  cmp     dword ptr [edx+44h], 0FFFFFFFFh
0x10040cd5  mov     ecx, [edx+50h]; this
0x10040cd8  mov     eax, [ecx+60h]
0x10040cdb  mov     [ebp+var_18], eax
0x10040cde  lea     eax, [edx+44h]
0x10040ce1  mov     [ebp+var_14], eax
0x10040ce4  jnz     short loc_10040D1B
0x10040ce6  lea     edx, [ebp+var_10]
0x10040ce9  push    edx; int *
0x10040cea  push    eax; unsigned int *
0x10040ceb  call    ?JETBeginSession@CDataSource@@QAEJAAKAAJ@Z; CDataSource::JETBeginSession(ulong &,long &)
0x10040cf0  mov     ebx, eax
0x10040cf2  mov     eax, [ebp+var_14]
0x10040cf5  test    ebx, ebx
0x10040cf7  jns     short loc_10040D07
0x10040cf9  mov     edi, [ebp+var_10]
0x10040cfc  mov     dword ptr [eax], 0FFFFFFFFh
0x10040d02  jmp     loc_10040E4B
0x10040d07  push    0
0x10040d09  push    1
0x10040d0b  push    3Bh ; ';'
0x10040d0d  push    dword ptr [eax]
0x10040d0f  lea     eax, [ebp+var_18]
0x10040d12  push    eax
0x10040d13  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x10040d19  mov     edi, eax
0x10040d1b  mov     eax, [ebp+arg_4]
0x10040d1e  cmp     dword ptr [eax], 0
0x10040d21  jnz     loc_10040E46
0x10040d27  cmp     dword ptr [eax+4], 0
0x10040d2b  jnz     loc_10040E46
0x10040d31  mov     ecx, [eax+0Ch]
0x10040d34  cmp     ecx, 1
0x10040d37  jz      short loc_10040D42
0x10040d39  cmp     ecx, 2
0x10040d3c  jnz     loc_10040E46
0x10040d42  cmp     dword ptr [eax+8], 1
0x10040d46  jnz     loc_10040E46
0x10040d4c  cmp     dword ptr [eax+10h], 0
0x10040d50  jz      loc_10040E46
0x10040d56  lea     ecx, [ebp+var_2C]; this
0x10040d59  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x10040d5e  mov     ebx, eax
0x10040d60  test    ebx, ebx
0x10040d62  js      loc_10040E4B
0x10040d68  push    ecx; struct DBInfoProps *
0x10040d69  lea     ecx, [ebp+var_2C]; this
0x10040d6c  call    ?CopyPropertiesFromStaticTable@CTrusteeProperties@@QAEJPBUDBInfoProps@@@Z; CTrusteeProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x10040d71  mov     ebx, eax
0x10040d73  test    ebx, ebx
0x10040d75  js      loc_10040E4B
0x10040d7b  push    0; struct CDBSession *
0x10040d7d  push    [ebp+arg_C]; struct tagDBPROPSET *
0x10040d80  lea     ecx, [ebp+var_2C]; this
0x10040d83  push    [ebp+arg_8]; unsigned int
0x10040d86  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x10040d8b  mov     ebx, eax
0x10040d8d  test    ebx, ebx
0x10040d8f  js      loc_10040E4B
0x10040d95  mov     eax, [ebp+arg_4]
0x10040d98  cmp     dword ptr [eax+0Ch], 1
0x10040d9c  jnz     loc_10040E3F; jumptable 10040E1C cases -1907,-1905,-1904
0x10040da2  mov     ecx, [ebp+var_24]; this
0x10040da5  push    0F2h; unsigned int
0x10040daa  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x10040daf  test    dword ptr [eax+28h], 1
0x10040db6  jz      loc_10040E4B
0x10040dbc  mov     ecx, [ebp+var_24]; this
0x10040dbf  push    0F3h; unsigned int
0x10040dc4  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x10040dc9  test    dword ptr [eax+28h], 1
0x10040dd0  jz      short loc_10040E4B
0x10040dd2  mov     ecx, [ebp+var_24]; this
0x10040dd5  push    0F2h; unsigned int
0x10040dda  call    ?GetWCHAR@JoltProperties@@QAEQAGK@Z; JoltProperties::GetWCHAR(ulong)
0x10040ddf  mov     ecx, [ebp+var_24]; this
0x10040de2  mov     edi, eax
0x10040de4  push    0F3h; unsigned int
0x10040de9  call    ?GetWCHAR@JoltProperties@@QAEQAGK@Z; JoltProperties::GetWCHAR(ulong)
0x10040dee  push    eax
0x10040def  mov     eax, [ebp+arg_4]
0x10040df2  push    edi
0x10040df3  push    dword ptr [eax+10h]
0x10040df6  mov     eax, [ebp+this]
0x10040df9  mov     eax, [eax+8]
0x10040dfc  push    dword ptr [eax+44h]
0x10040dff  call    ds:__imp__JetChangeUserPassword@16; JetChangeUserPassword(x,x,x,x)
0x10040e05  mov     edi, eax
0x10040e07  cmp     edi, 0FFFFF8EFh
0x10040e0d  jg      short loc_10040E2A
0x10040e0f  jz      short loc_10040E3F; jumptable 10040E1C cases -1907,-1905,-1904
0x10040e11  lea     eax, [edi+773h]; switch 5 cases
0x10040e17  cmp     eax, 4
0x10040e1a  ja      short def_10040E1C; jumptable 10040E1C default case, case -1906
0x10040e1c  jmp     ds:jpt_10040E1C[eax*4]; switch jump
0x10040e23  mov     ebx, 80040E6Bh; jumptable 10040E1C case -1903
0x10040e28  jmp     short loc_10040E4B
0x10040e2a  cmp     edi, 0FFFFF8F6h
0x10040e30  jz      short loc_10040E3F; jumptable 10040E1C cases -1907,-1905,-1904
0x10040e32  test    edi, edi
0x10040e34  jz      short loc_10040E67
0x10040e36  jns     short loc_10040E4D
0x10040e38  mov     ebx, 80004005h; jumptable 10040E1C default case, case -1906
0x10040e3d  jmp     short loc_10040E4B
0x10040e3f  mov     ebx, 80040E09h; jumptable 10040E1C cases -1907,-1905,-1904
0x10040e44  jmp     short loc_10040E4B
0x10040e46  mov     ebx, 80040E6Ah
0x10040e4b  test    edi, edi
0x10040e4d  jz      short loc_10040E67
0x10040e4f  mov     eax, [ebp+this]
0x10040e52  mov     edx, ebx
0x10040e54  push    offset _IID_ITrusteeAdmin; int
0x10040e59  push    edi; unsigned int
0x10040e5a  mov     ecx, [eax+8]
0x10040e5d  mov     ecx, [ecx+44h]
0x10040e60  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10040e65  jmp     short loc_10040E80
0x10040e67  test    ebx, ebx
0x10040e69  jns     short loc_10040E80
0x10040e6b  jmp     short loc_10040E72
0x10040e6d  mov     ebx, 80070057h
0x10040e72  push    0; int
0x10040e74  push    offset _IID_ITrusteeAdmin; int
0x10040e79  mov     edx, ebx
0x10040e7b  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10040e80  test    esi, esi
0x10040e82  jz      short loc_10040E8B
0x10040e84  push    esi; lpCriticalSection
0x10040e85  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10040e8b  lea     ecx, [ebp+var_2C]; this
0x10040e8e  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10040e93  mov     eax, ebx
0x10040e95  mov     ecx, [ebp+var_C]
0x10040e98  mov     large fs:0, ecx
0x10040e9f  pop     ecx
0x10040ea0  pop     edi
0x10040ea1  pop     esi
0x10040ea2  pop     ebx
0x10040ea3  mov     esp, ebp
0x10040ea5  pop     ebp
0x10040ea6  retn    10h
0x1004eed0  lea     ecx, [ebp+var_2C]; this
0x1004eed3  jmp     ??1CTableProperties@@UAE@XZ; CTableProperties::~CTableProperties(void)
0x1004eed8  lea     ecx, [ebp+var_1C]; this
0x1004eedb  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004eee5  nop
0x1004eee6  nop
0x1004eee7  mov     edx, [esp-4+arg_4]
0x1004eeeb  lea     eax, [edx+0Ch]
0x1004eeee  mov     ecx, [edx-30h]
0x1004eef1  xor     ecx, eax; StackCookie
0x1004eef3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004eef8  mov     eax, offset stru_1005006C
0x1004eefd  jmp     ___CxxFrameHandler3
```
