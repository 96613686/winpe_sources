# CImpITrusteeAdmin::CreateTrustee(_TRUSTEE_W *,ulong,tagDBPROPSET * const)

- ea: `0x100407e0`
- end: `0x10040a9b`
- name: `?CreateTrustee@CImpITrusteeAdmin@@UAGJPAU_TRUSTEE_W@@KQAUtagDBPROPSET@@@Z`
- size: `699`
- prototype: `int(CImpITrusteeAdmin *__hidden this, struct _TRUSTEE_W *, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x100196e0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001fae0`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x10023e00`
- `0x100407e0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!rand` at `0x100409a0`
- `msvcrt!rand` at `0x100409a0`
- `msvcrt!srand` at `0x1004098d`
- `msvcrt!srand` at `0x1004098d`
- `KERNEL32!LeaveCriticalSection` at `0x10040a6d`
- `KERNEL32!LeaveCriticalSection` at `0x10040a6d`
- `KERNEL32!EnterCriticalSection` at `0x10040849`
- `KERNEL32!EnterCriticalSection` at `0x10040849`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10040839`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10040839`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x10040984`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x10040984`
- `msjet40!__imp__JetCreateGroup@12` at `0x100409e8`
- `msjet40!__imp__JetCreateGroup@12` at `0x100409e8`
- `msjet40!__imp__JetCreateUser@16` at `0x100409de`
- `msjet40!__imp__JetCreateUser@16` at `0x100409de`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10040916`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10040916`

## pseudocode

```c
int __stdcall CImpITrusteeAdmin::CreateTrustee(
        CImpITrusteeAdmin *this,
        struct _TRUSTEE_W *a2,
        unsigned int a3,
        struct tagDBPROPSET *const a4)
{
  unsigned int v4; // ebx
  struct _TRUSTEE_W *v5; // edi
  struct _RTL_CRITICAL_SECTION *v6; // esi
  int v7; // ecx
  TRUSTEE_TYPE TrusteeType; // eax
  int v9; // edx
  CDataSource *v10; // ecx
  int v11; // edi
  const struct DBInfoProps *v12; // ecx
  unsigned __int16 *v13; // edx
  unsigned int i; // edi
  int v15; // eax
  int User; // eax
  bool v17; // zf
  const struct _GUID *v19; // [esp+0h] [ebp-88h]
  const struct _GUID *v20; // [esp+4h] [ebp-84h]
  _DWORD v21[2]; // [esp+14h] [ebp-74h] BYREF
  JoltProperties *v22; // [esp+1Ch] [ebp-6Ch]
  JoltProperties *v23; // [esp+20h] [ebp-68h]
  _DWORD *v24; // [esp+24h] [ebp-64h]
  unsigned int v25; // [esp+28h] [ebp-60h] BYREF
  unsigned __int16 *WCHAR; // [esp+2Ch] [ebp-5Ch] BYREF
  CImpITrusteeAdmin *v27; // [esp+30h] [ebp-58h]
  struct _TRUSTEE_W *v28; // [esp+34h] [ebp-54h]
  struct tagDBPROPSET *v29; // [esp+38h] [ebp-50h]
  GUID pguid; // [esp+3Ch] [ebp-4Ch] BYREF
  _WORD v31[22]; // [esp+4Ch] [ebp-3Ch] BYREF
  int v32; // [esp+84h] [ebp-4h]

  v4 = 0;
  v5 = a2;
  v27 = this;
  v28 = a2;
  v29 = a4;
  v25 = 0;
  v21[1] = 0;
  v22 = 0;
  v23 = 0;
  v21[0] = &CTrusteeProperties::`vftable';
  v32 = 0;
  SetErrorInfo(0, 0);
  v6 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v6);
  LOBYTE(v32) = 1;
  if ( !a2 || a3 && !v29 )
  {
LABEL_44:
    v11 = -2147024809;
    goto LABEL_45;
  }
  v7 = 0;
  if ( a3 )
  {
    do
    {
      v5 = v28;
      if ( !v29[v7].rgProperties )
      {
        v5 = v28;
        if ( v29[v7].cProperties )
          goto LABEL_44;
      }
    }
    while ( ++v7 < a3 );
  }
  if ( !v5->pMultipleTrustee && v5->MultipleTrusteeOperation == NO_MULTIPLE_TRUSTEE )
  {
    TrusteeType = v5->TrusteeType;
    if ( (TrusteeType == TRUSTEE_IS_USER || TrusteeType == TRUSTEE_IS_GROUP)
      && v5->TrusteeForm == TRUSTEE_IS_NAME
      && v5->ptstrName )
    {
      v9 = *((_DWORD *)v27 + 2);
      v17 = *(_DWORD *)(v9 + 68) == -1;
      v10 = *(CDataSource **)(v9 + 80);
      WCHAR = (unsigned __int16 *)*((_DWORD *)v10 + 24);
      v24 = (_DWORD *)(v9 + 68);
      if ( v17 )
      {
        v11 = CDataSource::JETBeginSession(v10, (unsigned int *)(v9 + 68), (int *)&v25);
        if ( v11 < 0 )
        {
          v4 = v25;
          *v24 = -1;
LABEL_34:
          v17 = v4 == 0;
          goto LABEL_35;
        }
        v4 = JetSetSystemParameter(&WCHAR, *v24, 59, 1, 0);
      }
      v11 = CSettableProperties::FInit((CSettableProperties *)v21);
      if ( v11 < 0 )
        goto LABEL_34;
      v11 = CTrusteeProperties::CopyPropertiesFromStaticTable((CTrusteeProperties *)v21, v12);
      if ( v11 < 0 )
        goto LABEL_34;
      v11 = CSettableProperties::SetProperties((CSettableProperties *)v21, a3, v29, 0);
      if ( v11 < 0 )
        goto LABEL_34;
      WCHAR = JoltProperties::GetWCHAR(v22, 0xF2u);
      v13 = JoltProperties::GetWCHAR(v23, 0x105u);
      if ( !v13 )
      {
        CoCreateGuid(&pguid);
        _srand(pguid.Data1);
        for ( i = 0; i < 0xA; ++i )
          v31[i] = _rand() % 223 + 32;
        v13 = v31;
        v31[i] = 0;
        v11 = 0;
      }
      v15 = *(_DWORD *)(*((_DWORD *)v27 + 2) + 68);
      if ( v28->TrusteeType == TRUSTEE_IS_USER )
        User = JetCreateUser(v15, v28->ptstrName, WCHAR, v13);
      else
        User = JetCreateGroup(v15, v28->ptstrName, v13);
      v4 = User;
      if ( User > -1809 )
      {
        if ( User == -1802 )
        {
LABEL_33:
          v11 = -2147217911;
          goto LABEL_34;
        }
        v17 = User == 0;
        if ( !User )
          goto LABEL_41;
        if ( User >= 0 )
        {
LABEL_35:
          if ( !v17 )
          {
            CExtError::SendJetErrortoOLEAuto(v4, (int)&IID_ITrusteeAdmin, (int)v19, v20);
            goto LABEL_46;
          }
LABEL_41:
          if ( v11 >= 0 )
            goto LABEL_46;
          goto LABEL_45;
        }
      }
      else if ( User == -1809 || User != -1911 && (User == -1910 || User == -1907) )
      {
        goto LABEL_33;
      }
      v11 = -2147467259;
      goto LABEL_34;
    }
  }
  v11 = -2147217814;
LABEL_45:
  CExtError::SendHRtoOLEAuto((int)&IID_ITrusteeAdmin, 0, v19, (int)v20);
LABEL_46:
  if ( v6 )
    LeaveCriticalSection(v6);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v21);
  return v11;
}

```

## disassembly

```asm
0x100407e0  mov     edi, edi
0x100407e2  push    ebp
0x100407e3  mov     ebp, esp
0x100407e5  push    0FFFFFFFFh
0x100407e7  push    offset ?CreateTrustee@CImpITrusteeAdmin@@UAGJPAU_TRUSTEE_W@@KQAUtagDBPROPSET@@@Z_SEH
0x100407ec  mov     eax, large fs:0
0x100407f2  push    eax
0x100407f3  sub     esp, 6Ch
0x100407f6  mov     eax, ___security_cookie
0x100407fb  xor     eax, ebp
0x100407fd  mov     [ebp+var_10], eax
0x10040800  push    ebx
0x10040801  push    esi
0x10040802  push    edi; int
0x10040803  push    eax; struct _GUID *
0x10040804  lea     eax, [ebp+var_C]
0x10040807  mov     large fs:0, eax
0x1004080d  mov     esi, [ebp+this]
0x10040810  xor     ebx, ebx
0x10040812  mov     edi, [ebp+arg_4]
0x10040815  mov     eax, [ebp+arg_C]
0x10040818  mov     [ebp+var_58], esi
0x1004081b  mov     [ebp+var_54], edi
0x1004081e  mov     [ebp+var_50], eax
0x10040821  mov     [ebp+var_60], ebx
0x10040824  mov     [ebp+var_70], ebx
0x10040827  mov     [ebp+var_6C], ebx
0x1004082a  mov     [ebp+var_68], ebx
0x1004082d  mov     [ebp+var_74], offset ??_7CTrusteeProperties@@6B@; const CTrusteeProperties::`vftable'
0x10040834  push    ebx; perrinfo
0x10040835  push    ebx; dwReserved
0x10040836  mov     [ebp+var_4], ebx
0x10040839  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004083f  mov     esi, [esi+8]
0x10040842  add     esi, 64h ; 'd'
0x10040845  push    esi; lpCriticalSection
0x10040846  mov     [ebp+var_78], esi
0x10040849  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004084f  mov     byte ptr [ebp+var_4], 1
0x10040853  test    edi, edi
0x10040855  jz      loc_10040A55
0x1004085b  mov     edx, [ebp+arg_8]
0x1004085e  test    edx, edx
0x10040860  jz      short loc_1004086B
0x10040862  cmp     [ebp+var_50], ebx
0x10040865  jz      loc_10040A55
0x1004086b  xor     ecx, ecx
0x1004086d  test    edx, edx
0x1004086f  jz      short loc_10040896
0x10040871  mov     edi, [ebp+var_50]
0x10040874  lea     eax, [ecx+ecx*2]
0x10040877  cmp     dword ptr [edi+eax*8], 0
0x1004087b  mov     edi, [ebp+var_54]
0x1004087e  jnz     short loc_10040891
0x10040880  mov     edi, [ebp+var_50]
0x10040883  cmp     dword ptr [edi+eax*8+4], 0
0x10040888  mov     edi, [ebp+var_54]
0x1004088b  jnz     loc_10040A55
0x10040891  inc     ecx
0x10040892  cmp     ecx, edx
0x10040894  jb      short loc_10040871
0x10040896  cmp     dword ptr [edi], 0
0x10040899  jnz     loc_10040A4E
0x1004089f  cmp     dword ptr [edi+4], 0
0x100408a3  jnz     loc_10040A4E
0x100408a9  mov     eax, [edi+0Ch]
0x100408ac  cmp     eax, 1
0x100408af  jz      short loc_100408BA
0x100408b1  cmp     eax, 2
0x100408b4  jnz     loc_10040A4E
0x100408ba  cmp     dword ptr [edi+8], 1
0x100408be  jnz     loc_10040A4E
0x100408c4  cmp     dword ptr [edi+10h], 0
0x100408c8  jz      loc_10040A4E
0x100408ce  mov     edx, [ebp+var_58]
0x100408d1  mov     edx, [edx+8]
0x100408d4  cmp     dword ptr [edx+44h], 0FFFFFFFFh
0x100408d8  mov     ecx, [edx+50h]; this
0x100408db  mov     eax, [ecx+60h]
0x100408de  mov     [ebp+var_5C], eax
0x100408e1  lea     eax, [edx+44h]
0x100408e4  mov     [ebp+var_64], eax
0x100408e7  jnz     short loc_1004091E
0x100408e9  lea     edx, [ebp+var_60]
0x100408ec  push    edx; int *
0x100408ed  push    eax; unsigned int *
0x100408ee  call    ?JETBeginSession@CDataSource@@QAEJAAKAAJ@Z; CDataSource::JETBeginSession(ulong &,long &)
0x100408f3  mov     edi, eax
0x100408f5  mov     eax, [ebp+var_64]
0x100408f8  test    edi, edi
0x100408fa  jns     short loc_1004090A
0x100408fc  mov     ebx, [ebp+var_60]
0x100408ff  mov     dword ptr [eax], 0FFFFFFFFh
0x10040905  jmp     loc_10040A17
0x1004090a  push    0
0x1004090c  push    1
0x1004090e  push    3Bh ; ';'
0x10040910  push    dword ptr [eax]
0x10040912  lea     eax, [ebp+var_5C]
0x10040915  push    eax
0x10040916  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x1004091c  mov     ebx, eax
0x1004091e  lea     ecx, [ebp+var_74]; this
0x10040921  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x10040926  mov     edi, eax
0x10040928  test    edi, edi
0x1004092a  js      loc_10040A17
0x10040930  push    ecx; struct DBInfoProps *
0x10040931  lea     ecx, [ebp+var_74]; this
0x10040934  call    ?CopyPropertiesFromStaticTable@CTrusteeProperties@@QAEJPBUDBInfoProps@@@Z; CTrusteeProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x10040939  mov     edi, eax
0x1004093b  test    edi, edi
0x1004093d  js      loc_10040A17
0x10040943  push    0; struct CDBSession *
0x10040945  push    [ebp+var_50]; struct tagDBPROPSET *
0x10040948  lea     ecx, [ebp+var_74]; this
0x1004094b  push    [ebp+arg_8]; unsigned int
0x1004094e  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x10040953  mov     edi, eax
0x10040955  test    edi, edi
0x10040957  js      loc_10040A17
0x1004095d  mov     ecx, [ebp+var_6C]; this
0x10040960  push    0F2h; unsigned int
0x10040965  call    ?GetWCHAR@JoltProperties@@QAEQAGK@Z; JoltProperties::GetWCHAR(ulong)
0x1004096a  mov     ecx, [ebp+var_68]; this
0x1004096d  push    105h; unsigned int
0x10040972  mov     [ebp+var_5C], eax
0x10040975  call    ?GetWCHAR@JoltProperties@@QAEQAGK@Z; JoltProperties::GetWCHAR(ulong)
0x1004097a  mov     edx, eax
0x1004097c  test    edx, edx
0x1004097e  jnz     short loc_100409C3
0x10040980  lea     eax, [ebp+pguid]
0x10040983  push    eax; pguid
0x10040984  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x1004098a  push    [ebp+pguid.Data1]; Seed
0x1004098d  call    ds:__imp__srand
0x10040993  add     esp, 4
0x10040996  mov     ebx, 0DFh
0x1004099b  xor     edi, edi
0x1004099d  nop     dword ptr [eax]
0x100409a0  call    ds:__imp__rand
0x100409a6  cdq
0x100409a7  idiv    ebx
0x100409a9  add     edx, 20h ; ' '
0x100409ac  mov     [ebp+edi*2+var_3C], dx
0x100409b1  inc     edi
0x100409b2  cmp     edi, 0Ah
0x100409b5  jb      short loc_100409A0
0x100409b7  xor     eax, eax
0x100409b9  lea     edx, [ebp+var_3C]
0x100409bc  mov     [ebp+edi*2+var_3C], ax
0x100409c1  xor     edi, edi
0x100409c3  mov     eax, [ebp+var_58]
0x100409c6  mov     ecx, [ebp+var_54]
0x100409c9  push    edx
0x100409ca  mov     eax, [eax+8]
0x100409cd  cmp     dword ptr [ecx+0Ch], 1
0x100409d1  mov     ebx, [ecx+10h]
0x100409d4  mov     eax, [eax+44h]
0x100409d7  jnz     short loc_100409E6
0x100409d9  push    [ebp+var_5C]
0x100409dc  push    ebx
0x100409dd  push    eax
0x100409de  call    ds:__imp__JetCreateUser@16; JetCreateUser(x,x,x,x)
0x100409e4  jmp     short loc_100409EE
0x100409e6  push    ebx
0x100409e7  push    eax
0x100409e8  call    ds:__imp__JetCreateGroup@12; JetCreateGroup(x,x,x)
0x100409ee  mov     ebx, eax
0x100409f0  cmp     ebx, 0FFFFF8EFh
0x100409f6  jg      short loc_10040A33
0x100409f8  jz      short loc_10040A12
0x100409fa  cmp     ebx, 0FFFFF889h
0x10040a00  jz      short loc_10040A41
0x10040a02  cmp     ebx, 0FFFFF88Ah
0x10040a08  jz      short loc_10040A12
0x10040a0a  cmp     ebx, 0FFFFF88Dh
0x10040a10  jnz     short loc_10040A41
0x10040a12  mov     edi, 80040E09h
0x10040a17  test    ebx, ebx
0x10040a19  jz      short loc_10040A48
0x10040a1b  mov     eax, [ebp+var_58]
0x10040a1e  mov     edx, edi
0x10040a20  push    offset _IID_ITrusteeAdmin; int
0x10040a25  push    ebx; unsigned int
0x10040a26  mov     ecx, [eax+8]
0x10040a29  mov     ecx, [ecx+44h]
0x10040a2c  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10040a31  jmp     short loc_10040A68
0x10040a33  cmp     ebx, 0FFFFF8F6h
0x10040a39  jz      short loc_10040A12
0x10040a3b  test    ebx, ebx
0x10040a3d  jz      short loc_10040A48
0x10040a3f  jns     short loc_10040A19
0x10040a41  mov     edi, 80004005h
0x10040a46  jmp     short loc_10040A17
0x10040a48  test    edi, edi
0x10040a4a  jns     short loc_10040A68
0x10040a4c  jmp     short loc_10040A5A
0x10040a4e  mov     edi, 80040E6Ah
0x10040a53  jmp     short loc_10040A5A
0x10040a55  mov     edi, 80070057h
0x10040a5a  push    0; int
0x10040a5c  push    offset _IID_ITrusteeAdmin; int
0x10040a61  mov     edx, edi
0x10040a63  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10040a68  test    esi, esi
0x10040a6a  jz      short loc_10040A73
0x10040a6c  push    esi; lpCriticalSection
0x10040a6d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10040a73  lea     ecx, [ebp+var_74]; this
0x10040a76  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10040a7b  mov     eax, edi
0x10040a7d  mov     ecx, [ebp+var_C]
0x10040a80  mov     large fs:0, ecx
0x10040a87  pop     ecx
0x10040a88  pop     edi
0x10040a89  pop     esi
0x10040a8a  pop     ebx
0x10040a8b  mov     ecx, [ebp+var_10]
0x10040a8e  xor     ecx, ebp; StackCookie
0x10040a90  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10040a95  mov     esp, ebp
0x10040a97  pop     ebp
0x10040a98  retn    10h
0x1004ee80  lea     ecx, [ebp+var_74]; this
0x1004ee83  jmp     ??1CTableProperties@@UAE@XZ; CTableProperties::~CTableProperties(void)
0x1004ee88  lea     ecx, [ebp+var_78]; this
0x1004ee8b  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004ee95  nop
0x1004ee96  nop
0x1004ee97  mov     edx, [esp-4+arg_4]
0x1004ee9b  lea     eax, [edx+0Ch]
0x1004ee9e  mov     ecx, [edx-7Ch]
0x1004eea1  xor     ecx, eax; StackCookie
0x1004eea3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004eea8  mov     ecx, [edx-4]
0x1004eeab  xor     ecx, eax; StackCookie
0x1004eead  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004eeb2  mov     eax, offset stru_10050038
0x1004eeb7  jmp     ___CxxFrameHandler3
```
