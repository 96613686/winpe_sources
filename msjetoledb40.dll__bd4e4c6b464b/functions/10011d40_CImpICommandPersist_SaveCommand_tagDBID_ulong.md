# CImpICommandPersist::SaveCommand(tagDBID *,ulong)

- ea: `0x10011d40`
- end: `0x100121ee`
- name: `?SaveCommand@CImpICommandPersist@@UAGJPAUtagDBID@@K@Z`
- size: `1198`
- prototype: `int(CImpICommandPersist *__hidden this, struct tagDBID *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1000ba50`
- `0x1000ba90`
- `0x1000d4a0`
- `0x10011d40`
- `0x10016e10`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001e8b0`
- `0x1001fb20`
- `0x1001fd10`
- `0x100255a0`
- `0x10025750`
- `0x10049580`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100121d2`
- `KERNEL32!LeaveCriticalSection` at `0x100121d2`
- `KERNEL32!EnterCriticalSection` at `0x10011db0`
- `KERNEL32!EnterCriticalSection` at `0x10011db0`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10011d9d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10011d9d`
- `msjet40!__imp__JetCloseTable@8` at `0x10012163`
- `msjet40!__imp__JetCloseTable@8` at `0x10012163`
- `msjet40!__imp__JetDeleteTable@12` at `0x10012197`
- `msjet40!__imp__JetDeleteTable@12` at `0x10012197`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10012134`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10012134`
- `msjet40!__imp__JetCreateQuery@16` at `0x10011f47`
- `msjet40!__imp__JetCreateQuery@16` at `0x10011f47`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x100120bd`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x100120bd`

## pseudocode

```c
int __stdcall CImpICommandPersist::SaveCommand(unsigned int **this, struct tagDBID *a2, unsigned int a3)
{
  CImpICommandPersist *v3; // edi
  struct tagDBID *v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // esi
  unsigned int *v6; // ecx
  unsigned int v7; // eax
  int String; // ebx
  int v9; // ecx
  int v10; // edx
  LPOLESTR pwszName; // eax
  unsigned int v12; // eax
  const unsigned __int16 *v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  unsigned __int16 *v18; // eax
  unsigned __int16 *v19; // edx
  int v20; // edx
  int v21; // ecx
  int v22; // eax
  signed int v23; // eax
  CTransactionState *v24; // ecx
  volatile signed __int32 *v25; // eax
  JoltProperties *v26; // ebx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  _WORD *v29; // edx
  unsigned int v31; // edx
  unsigned __int16 *v32; // eax
  void *v33; // ecx
  int v34; // eax
  int v35; // eax
  struct tagDBID *v36; // edi
  struct _GUID *v38; // [esp+0h] [ebp-5Ch]
  struct _GUID *v39; // [esp+4h] [ebp-58h]
  _BYTE v40[16]; // [esp+10h] [ebp-4Ch] BYREF
  int v41; // [esp+20h] [ebp-3Ch]
  unsigned __int16 *v42; // [esp+24h] [ebp-38h]
  LPCRITICAL_SECTION v43; // [esp+28h] [ebp-34h]
  unsigned int v44; // [esp+2Ch] [ebp-30h]
  int v45; // [esp+30h] [ebp-2Ch]
  JET_TABLEID tableid; // [esp+34h] [ebp-28h] BYREF
  unsigned __int16 v47[2]; // [esp+38h] [ebp-24h] BYREF
  unsigned int v48; // [esp+3Ch] [ebp-20h] BYREF
  int v49; // [esp+40h] [ebp-1Ch] BYREF
  int v50; // [esp+44h] [ebp-18h]
  struct tagDBID *v51; // [esp+48h] [ebp-14h]
  CDBSession *v52[4]; // [esp+4Ch] [ebp-10h] BYREF

  v3 = (CImpICommandPersist *)this;
  v4 = a2;
  v49 = (int)this;
  v51 = a2;
  tableid = -1;
  v45 = 0;
  v44 = 0;
  v52[0] = 0;
  v50 = 0;
  SetErrorInfo(0, 0);
  v43 = (LPCRITICAL_SECTION)(this[2] + 62);
  v5 = v43;
  EnterCriticalSection(v43);
  v52[3] = 0;
  v6 = this[2];
  v48 = v6[5];
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v7 = v6[13];
    String = -2147024809;
    v9 = *(_DWORD *)(v7 + 20);
    v10 = *(_DWORD *)(v7 + 16);
    goto LABEL_69;
  }
  if ( a2 )
  {
    if ( a2->eKind != 2 || (pwszName = a2->uName.pwszName) == 0 || !*pwszName )
    {
      v12 = v6[13];
      String = -2147217802;
      v9 = *(_DWORD *)(v12 + 20);
      v10 = *(_DWORD *)(v12 + 16);
      goto LABEL_69;
    }
  }
  v13 = (const unsigned __int16 *)v6[19];
  if ( v13 && a2 )
  {
    v14 = wcscmp(v13, a2->uName.pwszName);
    if ( v14 )
      v14 = v14 < 0 ? -1 : 1;
    if ( v14 )
    {
      String = -2147217802;
      v15 = this[2][13];
      v9 = *(_DWORD *)(v15 + 20);
      v10 = *(_DWORD *)(v15 + 16);
      goto LABEL_69;
    }
    v6 = this[2];
  }
  if ( !v6[27] )
  {
    String = -2147217908;
    v16 = this[2][13];
    v9 = *(_DWORD *)(v16 + 20);
    v10 = *(_DWORD *)(v16 + 16);
LABEL_69:
    if ( !JetGetDatabaseInfo(v10, v9, &v48, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_ICommandPersist, 0, v38, (int)v39);
    goto LABEL_71;
  }
  if ( !a2 )
  {
    v4 = (struct tagDBID *)v40;
    v51 = (struct tagDBID *)v40;
    v17 = *(_DWORD *)Sys;
    v41 = 2;
    v18 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, int))(v17 + 12))(*(_DWORD *)(v17 + 12), Sys, 130);
    v3 = (CImpICommandPersist *)v49;
    v42 = v18;
    if ( !v18 )
    {
      String = -2147024882;
      goto LABEL_71;
    }
    v19 = *(unsigned __int16 **)(*(_DWORD *)(v49 + 8) + 76);
    if ( v19 )
    {
      WCSCPY(v19, v18, (unsigned __int16 *)0x82, (const unsigned __int16 *)v38, (unsigned int)v39);
      v20 = 1;
      goto LABEL_24;
    }
    v45 = 1;
    GenerateRandomName((unsigned __int16 *)v38, (unsigned int)v39);
  }
  v20 = 0;
LABEL_24:
  if ( (a3 & 1) == 0 )
  {
    v21 = *((_DWORD *)v3 + 2);
    v22 = *(_DWORD *)(v21 + 52);
    if ( v20 )
    {
      v23 = JetOpenQueryDef(*(_DWORD *)(v22 + 16), *(_DWORD *)(v22 + 20), *(_DWORD *)(v21 + 76), &tableid);
      *(_DWORD *)v47 = v23;
      if ( v23 < 0 )
      {
        String = -2147467259;
        goto LABEL_65;
      }
    }
    else
    {
      v23 = JetCreateQuery(*(_DWORD *)(v22 + 16), *(_DWORD *)(v22 + 20), v4->uName.ulPropid, &tableid);
      *(_DWORD *)v47 = v23;
      if ( v23 <= -1011 )
      {
        switch ( v23 )
        {
          case -1011:
            String = -2147024882;
            goto LABEL_65;
          case -1907:
            String = -2147217911;
            goto LABEL_65;
          case -1314:
          case -1303:
            String = -2147217816;
            goto LABEL_65;
        }
        goto LABEL_40;
      }
      if ( v23 == -1002 )
      {
        String = -2147217802;
        goto LABEL_65;
      }
      if ( v23 )
      {
LABEL_40:
        String = -2147467259;
        goto LABEL_65;
      }
      v50 = 1;
    }
    v24 = *(CTransactionState **)(*((_DWORD *)v3 + 2) + 56);
    if ( v24 )
      CTransactionState::Release(v24);
    *(_DWORD *)(*((_DWORD *)v3 + 2) + 56) = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v3 + 2) + 52) + 88);
    v25 = *(volatile signed __int32 **)(*((_DWORD *)v3 + 2) + 56);
    if ( v25 )
      _InterlockedIncrement(v25);
    v26 = *(JoltProperties **)(v48 + 24);
    JoltProperties::IsbPropertySet(v26, 0xFDu, &v49);
    if ( v49 == 1 )
    {
      JoltProperties::GetStrValue(v26, 0xF2u, (unsigned __int16 **)v52);
      JoltProperties::IsbPropertySet(v26, 0x119u, &v49);
      v27 = 1;
      if ( v49 == 1 )
        v27 = 3;
      if ( !v52[0] )
        v27 = 0;
      v44 = v27;
    }
    v28 = *(_DWORD *)(*((_DWORD *)v3 + 2) + 108);
    v29 = (_WORD *)v28;
    v48 = v28 + 2;
    while ( *v29++ )
      ;
    v31 = (int)((int)v29 - v48) >> 1;
    v32 = 0;
    if ( v44 )
      v32 = (unsigned __int16 *)v52[0];
    String = CJOLT::JOLTJetSetQoSql(v28, v31, v32, v44, v47, (unsigned int)v38, (int *)v39);
    if ( String >= 0 )
    {
      *(_DWORD *)(*((_DWORD *)v3 + 2) + 72) = 1;
      if ( *(_DWORD *)(*((_DWORD *)v3 + 2) + 76) )
        System::Free(v33);
      String = CopyAndAllocateString((const unsigned __int16 *)v38, (unsigned __int16 **)v39);
    }
    v23 = *(_DWORD *)v47;
    goto LABEL_65;
  }
  if ( *(_DWORD *)(*((_DWORD *)v3 + 2) + 76) )
    System::Free(v6);
  String = CopyAndAllocateString((const unsigned __int16 *)v38, (unsigned __int16 **)v39);
  if ( String >= 0 )
  {
    *(_DWORD *)(*((_DWORD *)v3 + 2) + 72) = 0;
    goto LABEL_71;
  }
  v23 = 0;
LABEL_65:
  if ( v23 )
  {
    CExtError::SendJetErrortoOLEAuto(v23, (int)&IID_ICommandPersist, (int)v38, v39);
    goto LABEL_71;
  }
  v52[0] = (CDBSession *)String;
  if ( String < 0 )
  {
    v34 = *(_DWORD *)(*((_DWORD *)v3 + 2) + 52);
    v9 = *(_DWORD *)(v34 + 20);
    v10 = *(_DWORD *)(v34 + 16);
    if ( String != -2147024882 )
      goto LABEL_69;
  }
LABEL_71:
  v48 = tableid;
  if ( tableid != -1 )
  {
    v52[0] = *(CDBSession **)(*((_DWORD *)v3 + 2) + 52);
    if ( JetCloseTable(*((_DWORD *)v52[0] + 4), tableid) == -1108 )
      CDBSession::AddJetTableId(v52[0], v48);
  }
  if ( String < 0 && v50 == 1 )
  {
    v35 = *((_DWORD *)v3 + 2);
    v36 = v51;
    JetDeleteTable(
      *(_DWORD *)(*(_DWORD *)(v35 + 52) + 16),
      *(_DWORD *)(*(_DWORD *)(v35 + 52) + 20),
      v51->uName.ulPropid);
  }
  else
  {
    v36 = v51;
  }
  if ( v45 == 1 && v36 && v36->uName.ulPropid && Sys )
    (*(void (__thiscall **)(_DWORD, int, ULONG))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v36->uName.ulPropid);
  if ( v5 )
    LeaveCriticalSection(v5);
  return String;
}

```

## disassembly

```asm
0x10011d40  mov     edi, edi
0x10011d42  push    ebp
0x10011d43  mov     ebp, esp
0x10011d45  push    0FFFFFFFFh
0x10011d47  push    offset ?SaveCommand@CImpICommandPersist@@UAGJPAUtagDBID@@K@Z_SEH
0x10011d4c  mov     eax, large fs:0
0x10011d52  push    eax
0x10011d53  sub     esp, 40h
0x10011d56  push    ebx
0x10011d57  push    esi
0x10011d58  push    edi; int
0x10011d59  mov     eax, ___security_cookie
0x10011d5e  xor     eax, ebp
0x10011d60  push    eax; struct _GUID *
0x10011d61  lea     eax, [ebp+var_C]
0x10011d64  mov     large fs:0, eax
0x10011d6a  mov     edi, [ebp+this]
0x10011d6d  mov     ebx, [ebp+arg_4]
0x10011d70  push    0; perrinfo
0x10011d72  push    0; dwReserved
0x10011d74  mov     [ebp+var_1C], edi
0x10011d77  mov     [ebp+var_14], ebx
0x10011d7a  mov     [ebp+tableid], 0FFFFFFFFh
0x10011d81  mov     [ebp+var_2C], 0
0x10011d88  mov     [ebp+var_30], 0
0x10011d8f  mov     [ebp+var_10], 0
0x10011d96  mov     [ebp+var_18], 0
0x10011d9d  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10011da3  mov     esi, [edi+8]
0x10011da6  add     esi, 0F8h
0x10011dac  push    esi; lpCriticalSection
0x10011dad  mov     [ebp+var_34], esi
0x10011db0  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10011db6  test    [ebp+arg_8], 0FFFFFFFEh
0x10011dbd  mov     [ebp+var_4], 0
0x10011dc4  mov     ecx, [edi+8]
0x10011dc7  mov     eax, [ecx+14h]
0x10011dca  mov     [ebp+var_20], eax
0x10011dcd  jz      short loc_10011DE2
0x10011dcf  mov     eax, [ecx+34h]
0x10011dd2  mov     ebx, 80070057h
0x10011dd7  mov     ecx, [eax+14h]
0x10011dda  mov     edx, [eax+10h]
0x10011ddd  jmp     loc_1001212A
0x10011de2  test    ebx, ebx
0x10011de4  jz      short loc_10011E0D
0x10011de6  cmp     dword ptr [ebx+10h], 2
0x10011dea  jnz     short loc_10011DFA
0x10011dec  mov     eax, [ebx+14h]
0x10011def  test    eax, eax
0x10011df1  jz      short loc_10011DFA
0x10011df3  xor     edx, edx
0x10011df5  cmp     dx, [eax]
0x10011df8  jnz     short loc_10011E0D
0x10011dfa  mov     eax, [ecx+34h]
0x10011dfd  mov     ebx, 80040E76h
0x10011e02  mov     ecx, [eax+14h]
0x10011e05  mov     edx, [eax+10h]
0x10011e08  jmp     loc_1001212A
0x10011e0d  mov     eax, [ecx+4Ch]
0x10011e10  test    eax, eax
0x10011e12  jz      short loc_10011E68
0x10011e14  test    ebx, ebx
0x10011e16  jz      short loc_10011E68
0x10011e18  mov     ecx, [ebx+14h]
0x10011e1b  nop     dword ptr [eax+eax+00h]
0x10011e20  mov     dx, [eax]
0x10011e23  cmp     dx, [ecx]
0x10011e26  jnz     short loc_10011E46
0x10011e28  test    dx, dx
0x10011e2b  jz      short loc_10011E42
0x10011e2d  mov     dx, [eax+2]
0x10011e31  cmp     dx, [ecx+2]
0x10011e35  jnz     short loc_10011E46
0x10011e37  add     eax, 4
0x10011e3a  add     ecx, 4
0x10011e3d  test    dx, dx
0x10011e40  jnz     short loc_10011E20
0x10011e42  xor     eax, eax
0x10011e44  jmp     short loc_10011E4B
0x10011e46  sbb     eax, eax
0x10011e48  or      eax, 1
0x10011e4b  test    eax, eax
0x10011e4d  jz      short loc_10011E65
0x10011e4f  mov     eax, [edi+8]
0x10011e52  mov     ebx, 80040E76h
0x10011e57  mov     eax, [eax+34h]
0x10011e5a  mov     ecx, [eax+14h]
0x10011e5d  mov     edx, [eax+10h]
0x10011e60  jmp     loc_1001212A
0x10011e65  mov     ecx, [edi+8]
0x10011e68  cmp     dword ptr [ecx+6Ch], 0
0x10011e6c  jnz     short loc_10011E84
0x10011e6e  mov     eax, [edi+8]
0x10011e71  mov     ebx, 80040E0Ch
0x10011e76  mov     eax, [eax+34h]
0x10011e79  mov     ecx, [eax+14h]
0x10011e7c  mov     edx, [eax+10h]
0x10011e7f  jmp     loc_1001212A
0x10011e84  test    ebx, ebx
0x10011e86  jnz     short loc_10011EED
0x10011e88  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10011e8e  lea     ebx, [ebp+var_4C]
0x10011e91  push    82h
0x10011e96  push    ecx
0x10011e97  mov     [ebp+var_14], ebx
0x10011e9a  mov     eax, [ecx]
0x10011e9c  mov     [ebp+var_3C], 2
0x10011ea3  mov     edi, [eax+0Ch]
0x10011ea6  mov     ecx, edi
0x10011ea8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10011eae  call    edi
0x10011eb0  mov     edi, [ebp+var_1C]
0x10011eb3  mov     ecx, eax
0x10011eb5  mov     [ebp+var_38], ecx
0x10011eb8  test    ecx, ecx
0x10011eba  jnz     short loc_10011EC6
0x10011ebc  mov     ebx, 8007000Eh
0x10011ec1  jmp     loc_1001214B
0x10011ec6  mov     eax, [edi+8]
0x10011ec9  mov     edx, [eax+4Ch]
0x10011ecc  test    edx, edx
0x10011ece  jz      short loc_10011EE1
0x10011ed0  push    82h; unsigned __int16 *
0x10011ed5  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x10011eda  mov     edx, 1
0x10011edf  jmp     short loc_10011EEF
0x10011ee1  mov     [ebp+var_2C], 1
0x10011ee8  call    ?GenerateRandomName@@YGJPAGK@Z; GenerateRandomName(ushort *,ulong)
0x10011eed  xor     edx, edx
0x10011eef  test    byte ptr [ebp+arg_8], 1
0x10011ef3  jz      short loc_10011F2C
0x10011ef5  mov     eax, [edi+8]
0x10011ef8  mov     eax, [eax+4Ch]
0x10011efb  test    eax, eax
0x10011efd  jz      short loc_10011F05
0x10011eff  push    eax
0x10011f00  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10011f05  mov     edx, [edi+8]
0x10011f08  mov     ecx, [ebx+14h]
0x10011f0b  add     edx, 4Ch ; 'L'
0x10011f0e  call    ?CopyAndAllocateString@@YGJPBGPAPAG@Z; CopyAndAllocateString(ushort const *,ushort * *)
0x10011f13  mov     ebx, eax
0x10011f15  test    ebx, ebx
0x10011f17  js      loc_100120D5
0x10011f1d  mov     eax, [edi+8]
0x10011f20  mov     dword ptr [eax+48h], 0
0x10011f27  jmp     loc_1001214B
0x10011f2c  mov     ecx, [edi+8]
0x10011f2f  mov     eax, [ecx+34h]
0x10011f32  test    edx, edx
0x10011f34  jnz     loc_100120B0
0x10011f3a  lea     ecx, [ebp+tableid]
0x10011f3d  push    ecx
0x10011f3e  push    dword ptr [ebx+14h]
0x10011f41  push    dword ptr [eax+14h]
0x10011f44  push    dword ptr [eax+10h]
0x10011f47  call    ds:__imp__JetCreateQuery@16; JetCreateQuery(x,x,x,x)
0x10011f4d  mov     dword ptr [ebp+var_24], eax
0x10011f50  cmp     eax, 0FFFFFC0Dh
0x10011f55  jg      short loc_10011F8C
0x10011f57  jz      short loc_10011F82
0x10011f59  cmp     eax, 0FFFFF88Dh
0x10011f5e  jz      short loc_10011F78
0x10011f60  cmp     eax, 0FFFFFADEh
0x10011f65  jz      short loc_10011F6E
0x10011f67  cmp     eax, 0FFFFFAE9h
0x10011f6c  jnz     short loc_10011F9B
0x10011f6e  mov     ebx, 80040E68h
0x10011f73  jmp     loc_100120D7
0x10011f78  mov     ebx, 80040E09h
0x10011f7d  jmp     loc_100120D7
0x10011f82  mov     ebx, 8007000Eh
0x10011f87  jmp     loc_100120D7
0x10011f8c  cmp     eax, 0FFFFFC16h
0x10011f91  jz      loc_100120A9
0x10011f97  test    eax, eax
0x10011f99  jz      short loc_10011FA5
0x10011f9b  mov     ebx, 80004005h
0x10011fa0  jmp     loc_100120D7
0x10011fa5  mov     [ebp+var_18], 1
0x10011fac  mov     eax, [edi+8]
0x10011faf  mov     ecx, [eax+38h]; this
0x10011fb2  test    ecx, ecx
0x10011fb4  jz      short loc_10011FBB
0x10011fb6  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x10011fbb  mov     ecx, [edi+8]
0x10011fbe  mov     eax, [ecx+34h]
0x10011fc1  mov     eax, [eax+58h]
0x10011fc4  mov     [ecx+38h], eax
0x10011fc7  mov     eax, [edi+8]
0x10011fca  mov     eax, [eax+38h]
0x10011fcd  test    eax, eax
0x10011fcf  jz      short loc_10011FD4
0x10011fd1  lock inc dword ptr [eax]
0x10011fd4  mov     ebx, [ebp+var_20]
0x10011fd7  lea     eax, [ebp+var_1C]
0x10011fda  push    eax; int *
0x10011fdb  push    0FDh; unsigned int
0x10011fe0  mov     ebx, [ebx+18h]
0x10011fe3  mov     ecx, ebx; this
0x10011fe5  call    ?IsbPropertySet@JoltProperties@@QBEJKAAH@Z; JoltProperties::IsbPropertySet(ulong,int &)
0x10011fea  cmp     [ebp+var_1C], 1
0x10011fee  jnz     short loc_1001202C
0x10011ff0  lea     eax, [ebp+var_10]
0x10011ff3  mov     ecx, ebx; this
0x10011ff5  push    eax; unsigned __int16 **
0x10011ff6  push    0F2h; unsigned int
0x10011ffb  call    ?GetStrValue@JoltProperties@@QBEJKAAPAG@Z; JoltProperties::GetStrValue(ulong,ushort * &)
0x10012000  lea     eax, [ebp+var_1C]
0x10012003  mov     ecx, ebx; this
0x10012005  push    eax; int *
0x10012006  push    119h; unsigned int
0x1001200b  call    ?IsbPropertySet@JoltProperties@@QBEJKAAH@Z; JoltProperties::IsbPropertySet(ulong,int &)
0x10012010  cmp     [ebp+var_1C], 1
0x10012014  mov     ecx, 3
0x10012019  mov     eax, 1
0x1001201e  cmovz   eax, ecx
0x10012021  xor     ecx, ecx
0x10012023  cmp     [ebp+var_10], ecx
0x10012026  cmovz   eax, ecx
0x10012029  mov     [ebp+var_30], eax
0x1001202c  mov     ecx, [edi+8]
0x1001202f  mov     ebx, [ecx+6Ch]
0x10012032  mov     edx, ebx
0x10012034  lea     eax, [edx+2]
0x10012037  mov     [ebp+var_20], eax
0x1001203a  nop     word ptr [eax+eax+00h]
0x10012040  mov     ax, [edx]
0x10012043  add     edx, 2
0x10012046  test    ax, ax
0x10012049  jnz     short loc_10012040
0x1001204b  mov     eax, [ecx+34h]
0x1001204e  sub     edx, [ebp+var_20]
0x10012051  sar     edx, 1
0x10012053  mov     ecx, [eax+10h]
0x10012056  lea     eax, [ebp+var_24]
0x10012059  push    eax; unsigned __int16 *
0x1001205a  push    [ebp+var_30]; unsigned int
0x1001205d  xor     eax, eax
0x1001205f  cmp     [ebp+var_30], eax
0x10012062  cmovnz  eax, [ebp+var_10]
0x10012066  push    eax; unsigned __int16 *
0x10012067  push    edx; unsigned int
0x10012068  mov     edx, [ebp+tableid]
0x1001206b  push    ebx; unsigned int
0x1001206c  call    ?JOLTJetSetQoSql@CJOLT@@SGJKKPAGKPBGKAAJ@Z; CJOLT::JOLTJetSetQoSql(ulong,ulong,ushort *,ulong,ushort const *,ulong,long &)
0x10012071  mov     ebx, eax
0x10012073  test    ebx, ebx
0x10012075  js      short loc_100120A4
0x10012077  mov     eax, [edi+8]
0x1001207a  mov     dword ptr [eax+48h], 1
0x10012081  mov     eax, [edi+8]
0x10012084  mov     eax, [eax+4Ch]
0x10012087  test    eax, eax
0x10012089  jz      short loc_10012091
0x1001208b  push    eax
0x1001208c  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10012091  mov     ecx, [ebp+var_14]
0x10012094  mov     edx, [edi+8]
0x10012097  add     edx, 4Ch ; 'L'
0x1001209a  mov     ecx, [ecx+14h]
0x1001209d  call    ?CopyAndAllocateString@@YGJPBGPAPAG@Z; CopyAndAllocateString(ushort const *,ushort * *)
0x100120a2  mov     ebx, eax
0x100120a4  mov     eax, dword ptr [ebp+var_24]
0x100120a7  jmp     short loc_100120D7
0x100120a9  mov     ebx, 80040E76h
0x100120ae  jmp     short loc_100120D7
0x100120b0  lea     edx, [ebp+tableid]
0x100120b3  push    edx
0x100120b4  push    dword ptr [ecx+4Ch]
0x100120b7  push    dword ptr [eax+14h]
0x100120ba  push    dword ptr [eax+10h]
0x100120bd  call    ds:__imp__JetOpenQueryDef@16; JetOpenQueryDef(x,x,x,x)
0x100120c3  mov     dword ptr [ebp+var_24], eax
0x100120c6  test    eax, eax
0x100120c8  jns     loc_10011FAC
0x100120ce  mov     ebx, 80004005h
0x100120d3  jmp     short loc_100120D7
0x100120d5  xor     eax, eax
0x100120d7  mov     ecx, ebx
0x100120d9  test    eax, eax
0x100120db  jz      short loc_100120F5
0x100120dd  push    offset _IID_ICommandPersist; int
0x100120e2  push    eax; unsigned int
0x100120e3  mov     eax, [edi+8]
0x100120e6  mov     edx, ebx
0x100120e8  mov     ecx, [eax+34h]
0x100120eb  mov     ecx, [ecx+10h]
0x100120ee  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100120f3  jmp     short loc_1001214B
0x100120f5  mov     eax, [ebp+var_18]
0x100120f8  mov     ebx, ecx
0x100120fa  mov     [ebp+var_10], ebx
0x100120fd  mov     [ebp+var_18], eax
0x10012100  test    ecx, ecx
0x10012102  jns     short loc_1001214B
0x10012104  mov     eax, [edi+8]
0x10012107  mov     eax, [eax+34h]
0x1001210a  mov     ecx, [eax+14h]
  ... truncated ...
```
