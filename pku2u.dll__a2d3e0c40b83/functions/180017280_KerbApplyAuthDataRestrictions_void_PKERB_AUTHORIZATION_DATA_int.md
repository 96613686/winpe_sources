# KerbApplyAuthDataRestrictions(void * *,PKERB_AUTHORIZATION_DATA *,int *)

- ea: `0x180017280`
- end: `0x180017686`
- name: `?KerbApplyAuthDataRestrictions@@YAJPEAPEAXPEAUPKERB_AUTHORIZATION_DATA@@PEAH@Z`
- size: `1030`
- prototype: `__int64 __fastcall(void **, struct PKERB_AUTHORIZATION_DATA *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180001bf0`

## callees

- `0x180007dc8`
- `0x180017280`
- `0x18001a1d0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `MSASN1!ASN1_CreateDecoder` at `0x18001734f`
- `MSASN1!ASN1_CreateDecoder` at `0x18001734f`
- `MSASN1!ASN1_CloseDecoder` at `0x1800174cd`
- `MSASN1!ASN1_CloseDecoder` at `0x1800174cd`
- `MSASN1!ASN1_CreateModule` at `0x180017323`
- `MSASN1!ASN1_CreateModule` at `0x180017323`
- `MSASN1!ASN1_Decode` at `0x1800173fa`
- `MSASN1!ASN1_Decode` at `0x1800173fa`
- `LSASRV!LsaISetSupplementalTokenInfo` at `0x180017567`
- `LSASRV!LsaISetSupplementalTokenInfo` at `0x1800175d7`
- `LSASRV!LsaISetSupplementalTokenInfo` at `0x180017567`
- `LSASRV!LsaISetSupplementalTokenInfo` at `0x1800175d7`

## pseudocode

```c
__int64 __fastcall KerbApplyAuthDataRestrictions(void **a1, struct PKERB_AUTHORIZATION_DATA *a2, int *a3)
{
  int v3; // edi
  __int64 v5; // rbx
  __int64 Module; // rax
  unsigned int v7; // eax
  PVOID *v8; // rcx
  int v9; // esi
  int v10; // eax
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  _DWORD *v13; // rbx
  unsigned int v14; // esi
  __int64 *i; // rdi
  _DWORD *v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v20; // [rsp+88h] [rbp+10h] BYREF
  void *v21; // [rsp+90h] [rbp+18h] BYREF

  v21 = a3;
  v3 = *((_DWORD *)a2 + 4);
  v21 = 0;
  v20 = 0;
  if ( !v3 || (v5 = *((_QWORD *)a2 + 3)) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
    v9 = 60;
    goto LABEL_54;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v7 = ASN1_CreateDecoder(Module, &v20, 0, 0, 0);
  if ( v7 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 60;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v7);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        WPP_SF_d(v8[2], 80, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 60);
    }
LABEL_54:
    v14 = KerbMapKerbError(v9);
    goto LABEL_55;
  }
  v9 = 0;
  v21 = 0;
  v10 = ASN1_Decode(v20, &v21, 29, 8, v5, v3);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v10);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 == -1009 || v11 == -1002 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
        WPP_SF_d(v12[2], 82, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 29);
      v9 = -2147483647;
    }
    else
    {
      if ( v11 != -1011 && v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
        WPP_SF_d(v12[2], 83, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v11);
      v9 = 60;
    }
    v21 = 0;
  }
  if ( v20 )
    ASN1_CloseDecoder();
  if ( v9 )
    goto LABEL_54;
  v13 = 0;
  v14 = 0;
  for ( i = *(__int64 **)v21; i; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i + 4) <= 0xFFFFu )
    {
      if ( v13 )
        ((void (__fastcall *)(_DWORD *))Pku2uGlobalLsaFunctions->FreePrivateHeap)(v13);
      v16 = (_DWORD *)((__int64 (__fastcall *)(__int64))Pku2uGlobalLsaFunctions->AllocatePrivateHeap)(*((unsigned int *)i + 4) + 8LL);
      v13 = v16;
      if ( !v16 )
      {
        v14 = -1073741801;
        goto LABEL_55;
      }
      v16[1] = *((_DWORD *)i + 2);
      *v16 = *((_DWORD *)i + 4) + 8;
      memcpy_0(v16 + 2, (const void *)i[3], *((unsigned int *)i + 4));
      v17 = LsaISetSupplementalTokenInfo(a1, v13, 0);
      v14 = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
            (unsigned int)v17);
        goto LABEL_43;
      }
    }
  }
  if ( v13 )
  {
LABEL_43:
    ((void (__fastcall *)(_DWORD *))Pku2uGlobalLsaFunctions->FreePrivateHeap)(v13);
    goto LABEL_55;
  }
  v18 = LsaISetSupplementalTokenInfo(a1, 0, 0);
  v14 = v18;
  if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
      (unsigned int)v18);
LABEL_55:
  if ( v21 )
    KerbFreeData(0x1Du, v21);
  return v14;
}

```

## disassembly

```asm
0x180017280  mov     r11, rsp
0x180017283  mov     [r11+18h], r8
0x180017287  push    rsi
0x180017288  sub     rsp, 70h
0x18001728c  mov     [r11+8], rbx
0x180017290  mov     [r11-10h], rbp
0x180017294  mov     [r11-18h], rdi
0x180017298  mov     edi, [rdx+10h]
0x18001729b  mov     [r11-20h], r14
0x18001729f  mov     r14, rcx
0x1800172a2  mov     [r11-28h], r15
0x1800172a6  xor     r15d, r15d
0x1800172a9  mov     [r11+18h], r15
0x1800172ad  mov     [r11+10h], r15
0x1800172b1  test    edi, edi
0x1800172b3  jz      loc_18001760F
0x1800172b9  mov     rbx, [rdx+18h]
0x1800172bd  test    rbx, rbx
0x1800172c0  jz      loc_18001760F
0x1800172c6  cmp     cs:?fKRB5ModuleStarted@@3HA, r15d; int fKRB5ModuleStarted
0x1800172cd  jnz     short loc_180017332
0x1800172cf  mov     [rsp+78h+var_38], 32756B70h
0x1800172d7  lea     rax, qword_180049F80
0x1800172de  mov     [r11-40h], rax
0x1800172e2  mov     edx, 400h
0x1800172e7  lea     rax, off_180047030
0x1800172ee  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x1800172f8  mov     [r11-48h], rax
0x1800172fc  mov     ecx, 10000h
0x180017301  lea     rax, off_1800471C0
0x180017308  mov     r9d, 31h ; '1'
0x18001730e  mov     [r11-50h], rax
0x180017312  mov     r8d, 1000h
0x180017318  lea     rax, off_180047350
0x18001731f  mov     [r11-58h], rax
0x180017323  call    cs:__imp_ASN1_CreateModule
0x180017329  mov     cs:PKU2UMSG_Module, rax
0x180017330  jmp     short loc_180017339
0x180017332  mov     rax, cs:PKU2UMSG_Module
0x180017339  xor     r9d, r9d
0x18001733c  mov     [rsp+78h+var_58], r15
0x180017341  xor     r8d, r8d
0x180017344  lea     rdx, [rsp+78h+arg_8]
0x18001734c  mov     rcx, rax
0x18001734f  call    cs:__imp_ASN1_CreateDecoder
0x180017355  test    eax, eax
0x180017357  jz      short loc_1800173CA
0x180017359  mov     rcx, cs:WPP_GLOBAL_Control
0x180017360  lea     rbp, WPP_GLOBAL_Control
0x180017367  mov     esi, 3Ch ; '<'
0x18001736c  cmp     rcx, rbp
0x18001736f  jz      loc_180017642
0x180017375  test    byte ptr [rcx+1Ch], 1
0x180017379  jz      short loc_18001739A
0x18001737b  mov     rcx, [rcx+10h]
0x18001737f  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180017386  mov     edx, 4Dh ; 'M'
0x18001738b  mov     r9d, eax
0x18001738e  call    WPP_SF_d
0x180017393  mov     rcx, cs:WPP_GLOBAL_Control
0x18001739a  cmp     rcx, rbp
0x18001739d  jz      loc_180017642
0x1800173a3  test    byte ptr [rcx+1Ch], 1
0x1800173a7  jz      loc_180017642
0x1800173ad  mov     rcx, [rcx+10h]
0x1800173b1  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800173b8  mov     edx, 50h ; 'P'
0x1800173bd  mov     r9d, esi
0x1800173c0  call    WPP_SF_d
0x1800173c5  jmp     loc_180017642
0x1800173ca  mov     rcx, [rsp+78h+arg_8]
0x1800173d2  lea     rdx, [rsp+78h+arg_10]
0x1800173da  mov     [rsp+78h+var_50], edi
0x1800173de  mov     r9d, 8
0x1800173e4  mov     r8d, 1Dh
0x1800173ea  mov     [rsp+78h+var_58], rbx
0x1800173ef  mov     esi, r15d
0x1800173f2  mov     [rsp+78h+arg_10], r15
0x1800173fa  call    cs:__imp_ASN1_Decode
0x180017400  mov     ebx, eax
0x180017402  test    eax, eax
0x180017404  jns     loc_1800174B9
0x18001740a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017411  lea     rbp, WPP_GLOBAL_Control
0x180017418  cmp     rcx, rbp
0x18001741b  jz      short loc_180017442
0x18001741d  test    byte ptr [rcx+1Ch], 4
0x180017421  jz      short loc_180017442
0x180017423  mov     rcx, [rcx+10h]
0x180017427  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18001742e  mov     edx, 51h ; 'Q'
0x180017433  mov     r9d, eax
0x180017436  call    WPP_SF_d
0x18001743b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017442  cmp     ebx, 0FFFFFC0Fh
0x180017448  jz      short loc_180017484
0x18001744a  cmp     ebx, 0FFFFFC16h
0x180017450  jz      short loc_180017484
0x180017452  cmp     ebx, 0FFFFFC0Dh
0x180017458  jz      short loc_18001747D
0x18001745a  cmp     rcx, rbp
0x18001745d  jz      short loc_18001747D
0x18001745f  test    byte ptr [rcx+1Ch], 1
0x180017463  jz      short loc_18001747D
0x180017465  mov     rcx, [rcx+10h]
0x180017469  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180017470  mov     edx, 53h ; 'S'
0x180017475  mov     r9d, ebx
0x180017478  call    WPP_SF_d
0x18001747d  mov     esi, 3Ch ; '<'
0x180017482  jmp     short loc_1800174AF
0x180017484  cmp     rcx, rbp
0x180017487  jz      short loc_1800174AA
0x180017489  test    byte ptr [rcx+1Ch], 4
0x18001748d  jz      short loc_1800174AA
0x18001748f  mov     rcx, [rcx+10h]
0x180017493  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18001749a  mov     edx, 52h ; 'R'
0x18001749f  mov     r9d, 1Dh
0x1800174a5  call    WPP_SF_d
0x1800174aa  mov     esi, 80000001h
0x1800174af  mov     [rsp+78h+arg_10], r15
0x1800174b7  jmp     short loc_1800174C0
0x1800174b9  lea     rbp, WPP_GLOBAL_Control
0x1800174c0  mov     rcx, [rsp+78h+arg_8]
0x1800174c8  test    rcx, rcx
0x1800174cb  jz      short loc_1800174D3
0x1800174cd  call    cs:__imp_ASN1_CloseDecoder
0x1800174d3  test    esi, esi
0x1800174d5  jnz     loc_180017642
0x1800174db  mov     rax, [rsp+78h+arg_10]
0x1800174e3  mov     rbx, r15
0x1800174e6  mov     esi, r15d
0x1800174e9  mov     rdi, [rax]
0x1800174ec  test    rdi, rdi
0x1800174ef  jz      loc_1800175CA
0x1800174f5  cmp     dword ptr [rdi+10h], 0FFFFh
0x1800174fc  ja      short loc_180017573
0x1800174fe  test    rbx, rbx
0x180017501  jz      short loc_180017519
0x180017503  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001750a  mov     rcx, rbx
0x18001750d  mov     rax, [rax+188h]
0x180017514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017519  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180017520  mov     ecx, [rdi+10h]
0x180017523  add     rcx, 8
0x180017527  mov     rax, [rax+180h]
0x18001752e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017533  mov     rbx, rax
0x180017536  test    rax, rax
0x180017539  jz      loc_1800175C0
0x18001753f  mov     eax, [rdi+8]
0x180017542  lea     rcx, [rbx+8]; void *
0x180017546  mov     [rbx+4], eax
0x180017549  mov     eax, [rdi+10h]
0x18001754c  add     eax, 8
0x18001754f  mov     [rbx], eax
0x180017551  mov     r8d, [rdi+10h]; Size
0x180017555  mov     rdx, [rdi+18h]; Src
0x180017559  call    memcpy_0
0x18001755e  xor     r8d, r8d
0x180017561  mov     rdx, rbx
0x180017564  mov     rcx, r14
0x180017567  call    cs:__imp_LsaISetSupplementalTokenInfo
0x18001756d  mov     esi, eax
0x18001756f  test    eax, eax
0x180017571  js      short loc_18001757B
0x180017573  mov     rdi, [rdi]
0x180017576  jmp     loc_1800174EC
0x18001757b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017582  cmp     rcx, rbp
0x180017585  jz      short loc_1800175A5
0x180017587  test    byte ptr [rcx+1Ch], 1
0x18001758b  jz      short loc_1800175A5
0x18001758d  mov     rcx, [rcx+10h]
0x180017591  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180017598  mov     edx, 23h ; '#'
0x18001759d  mov     r9d, eax
0x1800175a0  call    WPP_SF_d
0x1800175a5  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x1800175ac  mov     rcx, rbx
0x1800175af  mov     rax, [rax+188h]
0x1800175b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175bb  jmp     loc_18001764B
0x1800175c0  mov     esi, 0C0000017h
0x1800175c5  jmp     loc_18001764B
0x1800175ca  test    rbx, rbx
0x1800175cd  jnz     short loc_1800175A5
0x1800175cf  xor     r8d, r8d
0x1800175d2  xor     edx, edx
0x1800175d4  mov     rcx, r14
0x1800175d7  call    cs:__imp_LsaISetSupplementalTokenInfo
0x1800175dd  mov     esi, eax
0x1800175df  test    eax, eax
0x1800175e1  jns     short loc_18001764B
0x1800175e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175ea  cmp     rcx, rbp
0x1800175ed  jz      short loc_18001764B
0x1800175ef  test    byte ptr [rcx+1Ch], 1
0x1800175f3  jz      short loc_18001764B
0x1800175f5  mov     rcx, [rcx+10h]
0x1800175f9  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180017600  mov     edx, 24h ; '$'
0x180017605  mov     r9d, eax
0x180017608  call    WPP_SF_d
0x18001760d  jmp     short loc_18001764B
0x18001760f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017616  lea     rbp, WPP_GLOBAL_Control
0x18001761d  cmp     rcx, rbp
0x180017620  jz      short loc_18001763D
0x180017622  test    byte ptr [rcx+1Ch], 1
0x180017626  jz      short loc_18001763D
0x180017628  mov     rcx, [rcx+10h]
0x18001762c  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180017633  mov     edx, 4Fh ; 'O'
0x180017638  call    WPP_SF_
0x18001763d  mov     esi, 3Ch ; '<'
0x180017642  mov     ecx, esi; int
0x180017644  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x180017649  mov     esi, eax
0x18001764b  mov     rdx, [rsp+78h+arg_10]; void *
0x180017653  mov     r15, [rsp+78h+var_28]
0x180017658  mov     r14, [rsp+78h+var_20]
0x18001765d  mov     rdi, [rsp+78h+var_18]
0x180017662  mov     rbp, [rsp+78h+var_10]
0x180017667  mov     rbx, [rsp+78h+arg_0]
0x18001766f  test    rdx, rdx
0x180017672  jz      short loc_18001767E
0x180017674  mov     ecx, 1Dh; unsigned int
0x180017679  call    ?KerbFreeData@@YAXKPEAX@Z; KerbFreeData(ulong,void *)
0x18001767e  mov     eax, esi
0x180017680  add     rsp, 70h
0x180017684  pop     rsi
0x180017685  retn
```
