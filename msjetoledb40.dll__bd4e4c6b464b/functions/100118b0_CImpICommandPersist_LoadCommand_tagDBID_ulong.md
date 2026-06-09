# CImpICommandPersist::LoadCommand(tagDBID *,ulong)

- ea: `0x100118b0`
- end: `0x10011d2e`
- name: `?LoadCommand@CImpICommandPersist@@UAGJPAUtagDBID@@K@Z`
- size: `1150`
- prototype: `int(CImpICommandPersist *__hidden this, struct tagDBID *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1000ba50`
- `0x1000ba90`
- `0x100118b0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x100201c0`
- `0x100255a0`
- `0x10049580`
- `0x1004d406`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10011d03`
- `KERNEL32!LeaveCriticalSection` at `0x10011d03`
- `KERNEL32!EnterCriticalSection` at `0x10011916`
- `KERNEL32!EnterCriticalSection` at `0x10011916`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10011c24`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10011c24`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10011c10`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10011c10`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10011900`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10011900`
- `msjet40!__imp__JetCloseTable@8` at `0x100119d5`
- `msjet40!__imp__JetCloseTable@8` at `0x10011cee`
- `msjet40!__imp__JetCloseTable@8` at `0x100119d5`
- `msjet40!__imp__JetCloseTable@8` at `0x10011cee`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10011cb6`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10011cb6`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x10011a00`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x10011a00`
- `msjet40!__imp__JetRetrieveQoSql@36` at `0x10011a91`
- `msjet40!__imp__JetRetrieveQoSql@36` at `0x10011a91`

## pseudocode

```c
int __stdcall CImpICommandPersist::LoadCommand(CImpICommandPersist *this, struct tagDBID *a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // edi
  _DWORD *v5; // ecx
  _DWORD *v6; // eax
  int v7; // eax
  bool v8; // zf
  int v9; // edx
  int v10; // eax
  JET_TABLEID v11; // ecx
  signed int Def; // eax
  int v13; // eax
  CTransactionState *v14; // ecx
  volatile signed __int32 *v15; // eax
  _WORD *v16; // edi
  int *v17; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // ecx
  int v25; // edi
  struct JoltProperty *RowbyProp; // edi
  OLECHAR *v27; // eax
  BSTR v28; // eax
  int v29; // edi
  int v30; // eax
  JET_TABLEID v31; // ecx
  const unsigned __int16 *v33; // [esp+0h] [ebp-244h]
  struct _GUID *v34; // [esp+4h] [ebp-240h]
  _BYTE v35[4]; // [esp+10h] [ebp-234h] BYREF
  LPCRITICAL_SECTION v36; // [esp+14h] [ebp-230h]
  unsigned int v37; // [esp+18h] [ebp-22Ch] BYREF
  int v38; // [esp+1Ch] [ebp-228h]
  int v39; // [esp+20h] [ebp-224h]
  int v40; // [esp+24h] [ebp-220h] BYREF
  int v41; // [esp+28h] [ebp-21Ch] BYREF
  int v42; // [esp+2Ch] [ebp-218h]
  struct tagDBID *String; // [esp+30h] [ebp-214h]
  OLECHAR psz[256]; // [esp+34h] [ebp-210h] BYREF
  int v45; // [esp+240h] [ebp-4h]

  String = a2;
  v41 = 0;
  v42 = 0;
  SetErrorInfo(0, 0);
  v36 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v3 = v36;
  EnterCriticalSection(v36);
  v45 = 0;
  if ( !a2 || a2->eKind != 2 || a3 )
  {
    v4 = -2147024809;
    goto LABEL_50;
  }
  if ( !a2->uName.ulPropid )
  {
    v4 = -2147217802;
LABEL_50:
    v7 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
    goto LABEL_51;
  }
  v5 = (_DWORD *)*((_DWORD *)this + 2);
  v6 = v5 + 15;
  if ( v5[20] && (*v6 & 0x100) == 0 )
  {
    v7 = v5[13];
    v4 = -2147217915;
LABEL_51:
    v21 = *(_DWORD *)(v7 + 20);
    v22 = *(_DWORD *)(v7 + 16);
    goto LABEL_52;
  }
  v8 = (*(_BYTE *)v6 & 0x10) == 0;
  v38 = v5[5];
  if ( !v8 )
  {
    v4 = -2147467259;
    goto LABEL_50;
  }
  v39 = 1024;
  v40 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, 2048);
  if ( !v40 )
  {
    v4 = -2147024882;
    v9 = 0;
    goto LABEL_56;
  }
  v10 = *((_DWORD *)this + 2);
  v11 = *(_DWORD *)(v10 + 100);
  if ( v11 != -1 )
  {
    JetCloseTable(*(_DWORD *)(*(_DWORD *)(v10 + 52) + 16), v11);
    *(_DWORD *)(*((_DWORD *)this + 2) + 100) = -1;
  }
  Def = JetOpenQueryDef(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 20),
          String->uName.ulPropid,
          *((_DWORD *)this + 2) + 100);
  if ( Def == -1305 )
  {
    v4 = -2147217802;
    goto LABEL_48;
  }
  if ( Def < 0 )
  {
LABEL_17:
    v4 = -2147467259;
LABEL_48:
    CExtError::SendJetErrortoOLEAuto(
      v4,
      *(char **)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 16),
      Def,
      (int)&IID_ICommandPersist,
      (int)v33,
      v34);
    goto LABEL_54;
  }
  v13 = *((_DWORD *)this + 2);
  v42 = 1;
  v14 = *(CTransactionState **)(v13 + 56);
  if ( v14 )
    CTransactionState::Release(v14);
  *(_DWORD *)(*((_DWORD *)this + 2) + 56) = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 88);
  v15 = *(volatile signed __int32 **)(*((_DWORD *)this + 2) + 56);
  if ( v15 )
    _InterlockedIncrement(v15);
  v16 = (_WORD *)v40;
  while ( 1 )
  {
    *v16 = 0;
    Def = JetRetrieveQoSql(
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 16),
            *(_DWORD *)(*((_DWORD *)this + 2) + 100),
            v16,
            v39,
            v35,
            psz,
            256,
            &v37,
            &v41);
    v40 = Def;
    if ( Def != -3515 )
      break;
LABEL_26:
    v17 = (int *)Sys;
    if ( Sys )
    {
      (*(void (__thiscall **)(_DWORD, int, _WORD *))(*(_DWORD *)Sys + 20))(*(_DWORD *)(*(_DWORD *)Sys + 20), Sys, v16);
      v17 = (int *)Sys;
    }
    v18 = *v17;
    v39 *= 2;
    v16 = (_WORD *)(*(int (__thiscall **)(_DWORD, int *, int))(v18 + 12))(*(_DWORD *)(v18 + 12), v17, 2 * v39);
    if ( !v16 )
    {
      v4 = -2147024882;
      Def = v40;
      v19 = -2147024882;
      if ( v40 )
        goto LABEL_48;
      goto LABEL_30;
    }
  }
  if ( Def )
  {
    if ( Def != 1006 )
      goto LABEL_17;
    goto LABEL_26;
  }
  v23 = 256;
  if ( v37 < 0x100 )
    v23 = v37;
  v24 = v23;
  if ( v24 >= 256 )
    __report_rangecheckfailure();
  psz[v24] = 0;
  if ( *(_DWORD *)(*((_DWORD *)this + 2) + 108) )
    System::Free((void *)(v24 * 2));
  *(_DWORD *)(*((_DWORD *)this + 2) + 108) = v16;
  *(_DWORD *)(*((_DWORD *)this + 2) + 72) = 1;
  if ( *(_DWORD *)(*((_DWORD *)this + 2) + 76) )
    System::Free((void *)(v24 * 2));
  String = (struct tagDBID *)CopyAndAllocateString(v33, (unsigned __int16 **)v34);
  v25 = -((v41 & 1) != 0);
  *((_WORD *)JoltProperties::GetRowbyProp(*(JoltProperties **)(v38 + 24), 0xFDu) + 12) = v25;
  if ( (v41 & 1) != 0 )
  {
    RowbyProp = JoltProperties::GetRowbyProp(*(JoltProperties **)(v38 + 24), 0xF2u);
    v27 = (OLECHAR *)*((_DWORD *)RowbyProp + 6);
    if ( v27 )
    {
      SysFreeString(v27);
      *((_DWORD *)RowbyProp + 6) = 0;
    }
    v28 = SysAllocString(psz);
    *((_DWORD *)RowbyProp + 6) = v28;
    if ( !v28 )
    {
      v4 = -2147024882;
      goto LABEL_55;
    }
    String = 0;
    v29 = -((v41 & 2) != 0);
    *((_WORD *)JoltProperties::GetRowbyProp(*(JoltProperties **)(v38 + 24), 0x119u) + 12) = v29;
  }
  v19 = (int)String;
  *(_DWORD *)(*((_DWORD *)this + 2) + 60) |= 0x20u;
LABEL_30:
  v9 = v42;
  v4 = v19;
  String = (struct tagDBID *)v19;
  if ( v19 >= 0 )
    goto LABEL_59;
  v20 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
  v21 = *(_DWORD *)(v20 + 20);
  v22 = *(_DWORD *)(v20 + 16);
  if ( v4 == -2147024882 )
  {
LABEL_56:
    v30 = *((_DWORD *)this + 2);
    v31 = *(_DWORD *)(v30 + 100);
    if ( v31 != -1 && v9 == 1 )
    {
      JetCloseTable(*(_DWORD *)(*(_DWORD *)(v30 + 52) + 16), v31);
      *(_DWORD *)(*((_DWORD *)this + 2) + 100) = -1;
    }
  }
  else
  {
LABEL_52:
    if ( !JetGetDatabaseInfo(v22, v21, &v40, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_ICommandPersist, 0, (const struct _GUID *)v33, (int)v34);
LABEL_54:
    if ( v4 < 0 )
    {
LABEL_55:
      v9 = v42;
      goto LABEL_56;
    }
  }
LABEL_59:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v4;
}

```

## disassembly

```asm
0x100118b0  mov     edi, edi
0x100118b2  push    ebp
0x100118b3  mov     ebp, esp
0x100118b5  push    0FFFFFFFFh
0x100118b7  push    offset ?LoadCommand@CImpICommandPersist@@UAGJPAUtagDBID@@K@Z_SEH
0x100118bc  mov     eax, large fs:0
0x100118c2  push    eax
0x100118c3  sub     esp, 228h
0x100118c9  mov     eax, ___security_cookie
0x100118ce  xor     eax, ebp
0x100118d0  mov     [ebp+var_10], eax
0x100118d3  push    ebx
0x100118d4  push    esi
0x100118d5  push    edi; int
0x100118d6  push    eax; struct _GUID *
0x100118d7  lea     eax, [ebp+var_C]
0x100118da  mov     large fs:0, eax
0x100118e0  mov     edi, [ebp+arg_4]
0x100118e3  xor     eax, eax
0x100118e5  mov     ebx, [ebp+this]
0x100118e8  push    eax; perrinfo
0x100118e9  push    eax; dwReserved
0x100118ea  mov     [ebp+var_214], edi
0x100118f0  mov     [ebp+var_21C], 0
0x100118fa  mov     [ebp+var_218], eax
0x10011900  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10011906  mov     esi, [ebx+8]
0x10011909  add     esi, 0F8h
0x1001190f  push    esi; lpCriticalSection
0x10011910  mov     [ebp+var_230], esi
0x10011916  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001191c  mov     [ebp+var_4], 0
0x10011923  test    edi, edi
0x10011925  jz      loc_10011C98
0x1001192b  cmp     dword ptr [edi+10h], 2
0x1001192f  jnz     loc_10011C98
0x10011935  cmp     [ebp+arg_8], 0
0x10011939  jnz     loc_10011C98
0x1001193f  cmp     dword ptr [edi+14h], 0
0x10011943  jnz     short loc_1001194F
0x10011945  mov     edi, 80040E76h
0x1001194a  jmp     loc_10011C9D
0x1001194f  mov     ecx, [ebx+8]
0x10011952  cmp     dword ptr [ecx+50h], 0
0x10011956  lea     eax, [ecx+3Ch]
0x10011959  jbe     short loc_10011970
0x1001195b  test    dword ptr [eax], 100h
0x10011961  jnz     short loc_10011970
0x10011963  mov     eax, [ecx+34h]
0x10011966  mov     edi, 80040E05h
0x1001196b  jmp     loc_10011CA3
0x10011970  test    byte ptr [eax], 10h
0x10011973  mov     ecx, [ecx+14h]
0x10011976  mov     [ebp+var_228], ecx
0x1001197c  jz      short loc_10011988
0x1001197e  mov     edi, 80004005h
0x10011983  jmp     loc_10011C9D
0x10011988  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1001198e  push    800h
0x10011993  push    ecx
0x10011994  mov     [ebp+var_224], 400h
0x1001199e  mov     eax, [ecx]
0x100119a0  mov     edi, [eax+0Ch]
0x100119a3  mov     ecx, edi
0x100119a5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100119ab  call    edi
0x100119ad  mov     [ebp+var_220], eax
0x100119b3  test    eax, eax
0x100119b5  jnz     short loc_100119C3
0x100119b7  mov     edi, 8007000Eh
0x100119bc  xor     edx, edx
0x100119be  jmp     loc_10011CD7
0x100119c3  mov     eax, [ebx+8]
0x100119c6  mov     ecx, [eax+64h]
0x100119c9  cmp     ecx, 0FFFFFFFFh
0x100119cc  jz      short loc_100119E5
0x100119ce  mov     eax, [eax+34h]
0x100119d1  push    ecx; tableid
0x100119d2  push    dword ptr [eax+10h]; sesid
0x100119d5  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x100119db  mov     eax, [ebx+8]
0x100119de  mov     dword ptr [eax+64h], 0FFFFFFFFh
0x100119e5  mov     ecx, [ebx+8]
0x100119e8  mov     eax, [ecx+34h]
0x100119eb  mov     edx, [eax+14h]
0x100119ee  mov     edi, [eax+10h]
0x100119f1  lea     eax, [ecx+64h]
0x100119f4  push    eax
0x100119f5  mov     eax, [ebp+var_214]
0x100119fb  push    dword ptr [eax+14h]
0x100119fe  push    edx
0x100119ff  push    edi
0x10011a00  call    ds:__imp__JetOpenQueryDef@16; JetOpenQueryDef(x,x,x,x)
0x10011a06  cmp     eax, 0FFFFFAE7h
0x10011a0b  jz      loc_10011C7B
0x10011a11  test    eax, eax
0x10011a13  jns     short loc_10011A1F
0x10011a15  mov     edi, 80004005h
0x10011a1a  jmp     loc_10011C80
0x10011a1f  mov     eax, [ebx+8]
0x10011a22  mov     [ebp+var_218], 1
0x10011a2c  mov     ecx, [eax+38h]; this
0x10011a2f  test    ecx, ecx
0x10011a31  jz      short loc_10011A38
0x10011a33  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x10011a38  mov     ecx, [ebx+8]
0x10011a3b  mov     eax, [ecx+34h]
0x10011a3e  mov     eax, [eax+58h]
0x10011a41  mov     [ecx+38h], eax
0x10011a44  mov     eax, [ebx+8]
0x10011a47  mov     eax, [eax+38h]
0x10011a4a  test    eax, eax
0x10011a4c  jz      short loc_10011A51
0x10011a4e  lock inc dword ptr [eax]
0x10011a51  mov     edi, [ebp+var_220]
0x10011a57  lea     edx, [ebp+var_21C]
0x10011a5d  xor     eax, eax
0x10011a5f  push    edx
0x10011a60  lea     edx, [ebp+var_22C]
0x10011a66  mov     [edi], ax
0x10011a69  mov     eax, [ebx+8]
0x10011a6c  push    edx
0x10011a6d  push    100h
0x10011a72  lea     edx, [ebp+psz]
0x10011a78  mov     ecx, [eax+64h]
0x10011a7b  mov     eax, [eax+34h]
0x10011a7e  push    edx
0x10011a7f  lea     edx, [ebp+var_234]
0x10011a85  push    edx
0x10011a86  push    [ebp+var_224]
0x10011a8c  push    edi
0x10011a8d  push    ecx
0x10011a8e  push    dword ptr [eax+10h]
0x10011a91  call    ds:__imp__JetRetrieveQoSql@36; JetRetrieveQoSql(x,x,x,x,x,x,x,x,x)
0x10011a97  mov     [ebp+var_220], eax
0x10011a9d  cmp     eax, 0FFFFF245h
0x10011aa2  jz      short loc_10011AB7
0x10011aa4  test    eax, eax
0x10011aa6  jz      loc_10011B50
0x10011aac  cmp     eax, 3EEh
0x10011ab1  jnz     loc_10011A15
0x10011ab7  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x10011abc  test    eax, eax
0x10011abe  jz      short loc_10011AD6
0x10011ac0  mov     ecx, [eax]
0x10011ac2  push    edi
0x10011ac3  push    eax
0x10011ac4  mov     edi, [ecx+14h]
0x10011ac7  mov     ecx, edi
0x10011ac9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10011acf  call    edi
0x10011ad1  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x10011ad6  mov     edx, [ebp+var_224]
0x10011adc  mov     ecx, [eax]
0x10011ade  add     edx, edx
0x10011ae0  mov     [ebp+var_224], edx
0x10011ae6  mov     edi, [ecx+0Ch]
0x10011ae9  lea     ecx, [edx+edx]
0x10011aec  push    ecx
0x10011aed  push    eax
0x10011aee  mov     ecx, edi
0x10011af0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10011af6  call    edi
0x10011af8  mov     edi, eax
0x10011afa  test    edi, edi
0x10011afc  jnz     loc_10011A57
0x10011b02  mov     edi, 8007000Eh
0x10011b07  mov     eax, [ebp+var_220]
0x10011b0d  mov     ecx, edi
0x10011b0f  test    eax, eax
0x10011b11  jnz     loc_10011C80
0x10011b17  mov     edx, [ebp+var_218]
0x10011b1d  mov     edi, ecx
0x10011b1f  mov     [ebp+var_214], edi
0x10011b25  mov     [ebp+var_218], edx
0x10011b2b  test    ecx, ecx
0x10011b2d  jns     loc_10011CFE
0x10011b33  mov     eax, [ebx+8]
0x10011b36  mov     eax, [eax+34h]
0x10011b39  mov     ecx, [eax+14h]
0x10011b3c  mov     eax, [eax+10h]
0x10011b3f  cmp     edi, 8007000Eh
0x10011b45  jz      loc_10011CD7
0x10011b4b  jmp     loc_10011CA9
0x10011b50  mov     ecx, 100h
0x10011b55  cmp     [ebp+var_22C], ecx
0x10011b5b  cmovb   ecx, [ebp+var_22C]
0x10011b62  add     ecx, ecx; void *
0x10011b64  cmp     ecx, 200h
0x10011b6a  jnb     loc_10011D29
0x10011b70  xor     eax, eax
0x10011b72  mov     [ebp+ecx+psz], ax
0x10011b7a  mov     eax, [ebx+8]
0x10011b7d  mov     eax, [eax+6Ch]
0x10011b80  test    eax, eax
0x10011b82  jz      short loc_10011B8A
0x10011b84  push    eax
0x10011b85  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10011b8a  mov     eax, [ebx+8]
0x10011b8d  mov     [eax+6Ch], edi
0x10011b90  mov     eax, [ebx+8]
0x10011b93  mov     dword ptr [eax+48h], 1
0x10011b9a  mov     eax, [ebx+8]
0x10011b9d  mov     eax, [eax+4Ch]
0x10011ba0  test    eax, eax
0x10011ba2  jz      short loc_10011BAA
0x10011ba4  push    eax
0x10011ba5  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10011baa  mov     eax, [ebp+var_214]
0x10011bb0  mov     edx, [ebx+8]
0x10011bb3  add     edx, 4Ch ; 'L'
0x10011bb6  mov     ecx, [eax+14h]
0x10011bb9  call    ?CopyAndAllocateString@@YGJPBGPAPAG@Z; CopyAndAllocateString(ushort const *,ushort * *)
0x10011bbe  mov     ecx, [ebp+var_228]
0x10011bc4  mov     [ebp+var_214], eax
0x10011bca  mov     eax, [ebp+var_21C]
0x10011bd0  and     al, 1
0x10011bd2  mov     ecx, [ecx+18h]; this
0x10011bd5  movzx   edi, al
0x10011bd8  neg     edi
0x10011bda  push    0FDh; unsigned int
0x10011bdf  sbb     edi, edi
0x10011be1  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x10011be6  mov     [eax+18h], di
0x10011bea  test    byte ptr [ebp+var_21C], 1
0x10011bf1  jz      short loc_10011C69
0x10011bf3  mov     eax, [ebp+var_228]
0x10011bf9  push    0F2h; unsigned int
0x10011bfe  mov     ecx, [eax+18h]; this
0x10011c01  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x10011c06  mov     edi, eax
0x10011c08  mov     eax, [edi+18h]
0x10011c0b  test    eax, eax
0x10011c0d  jz      short loc_10011C1D
0x10011c0f  push    eax; bstrString
0x10011c10  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10011c16  mov     dword ptr [edi+18h], 0
0x10011c1d  lea     eax, [ebp+psz]
0x10011c23  push    eax; psz
0x10011c24  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10011c2a  mov     [edi+18h], eax
0x10011c2d  test    eax, eax
0x10011c2f  jnz     short loc_10011C3B
0x10011c31  mov     edi, 8007000Eh
0x10011c36  jmp     loc_10011CD1
0x10011c3b  xor     eax, eax
0x10011c3d  mov     [ebp+var_214], eax
0x10011c43  mov     eax, [ebp+var_21C]
0x10011c49  and     al, 2
0x10011c4b  movzx   edi, al
0x10011c4e  mov     eax, [ebp+var_228]
0x10011c54  neg     edi
0x10011c56  push    119h; unsigned int
0x10011c5b  sbb     edi, edi
0x10011c5d  mov     ecx, [eax+18h]; this
0x10011c60  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x10011c65  mov     [eax+18h], di
0x10011c69  mov     eax, [ebx+8]
0x10011c6c  mov     ecx, [ebp+var_214]
0x10011c72  or      dword ptr [eax+3Ch], 20h
0x10011c76  jmp     loc_10011B17
0x10011c7b  mov     edi, 80040E76h
0x10011c80  push    offset _IID_ICommandPersist; int
0x10011c85  push    eax; unsigned int
0x10011c86  mov     eax, [ebx+8]
0x10011c89  mov     edx, edi
0x10011c8b  mov     ecx, [eax+34h]
0x10011c8e  mov     ecx, [ecx+10h]
0x10011c91  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10011c96  jmp     short loc_10011CCD
0x10011c98  mov     edi, 80070057h
0x10011c9d  mov     eax, [ebx+8]
0x10011ca0  mov     eax, [eax+34h]
0x10011ca3  mov     ecx, [eax+14h]
0x10011ca6  mov     eax, [eax+10h]
0x10011ca9  push    3
0x10011cab  push    4
0x10011cad  lea     edx, [ebp+var_220]
0x10011cb3  push    edx
0x10011cb4  push    ecx
0x10011cb5  push    eax
0x10011cb6  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10011cbc  test    eax, eax
0x10011cbe  jnz     short loc_10011CCD
0x10011cc0  push    eax; int
0x10011cc1  push    offset _IID_ICommandPersist; int
0x10011cc6  mov     edx, edi
0x10011cc8  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10011ccd  test    edi, edi
0x10011ccf  jns     short loc_10011CFE
0x10011cd1  mov     edx, [ebp+var_218]
0x10011cd7  mov     eax, [ebx+8]
0x10011cda  mov     ecx, [eax+64h]
0x10011cdd  cmp     ecx, 0FFFFFFFFh
0x10011ce0  jz      short loc_10011CFE
0x10011ce2  cmp     edx, 1
0x10011ce5  jnz     short loc_10011CFE
0x10011ce7  mov     eax, [eax+34h]
0x10011cea  push    ecx; tableid
0x10011ceb  push    dword ptr [eax+10h]; sesid
  ... truncated ...
```
