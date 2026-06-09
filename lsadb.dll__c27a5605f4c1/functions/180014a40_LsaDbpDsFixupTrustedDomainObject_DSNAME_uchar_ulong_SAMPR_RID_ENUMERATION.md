# LsaDbpDsFixupTrustedDomainObject(_DSNAME *,uchar,ulong,_SAMPR_RID_ENUMERATION *)

- ea: `0x180014a40`
- end: `0x180014dea`
- name: `?LsaDbpDsFixupTrustedDomainObject@@YAJPEAU_DSNAME@@EKPEAU_SAMPR_RID_ENUMERATION@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(struct _DSNAME *, unsigned __int8, unsigned int, struct _SAMPR_RID_ENUMERATION *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180014df0`

## callees

- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x180011f90`
- `0x180014a40`
- `0x180015748`
- `0x180015790`
- `0x18001819c`
- `0x180018eb0`
- `0x1800194a8`

## import_xrefs

- `LSASRV!LsapOpenSam` at `0x180014c45`
- `LSASRV!LsapOpenSam` at `0x180014c45`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x180014d51`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x180014d51`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180014c9c`
- `LSASRV!LsapGetAccountDomainHandle` at `0x180014c9c`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180014da7`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180014da7`
- `ntdll!RtlPrefixUnicodeString` at `0x180014bf8`
- `ntdll!RtlPrefixUnicodeString` at `0x180014bf8`
- `SAMSRV!SamrOpenUser` at `0x180014cb2`
- `SAMSRV!SamrOpenUser` at `0x180014cb2`
- `SAMSRV!SamrCloseHandle` at `0x180014cea`
- `SAMSRV!SamrCloseHandle` at `0x180014cea`

## pseudocode

```c
__int64 __fastcall LsaDbpDsFixupTrustedDomainObject(
        struct _DSNAME *a1,
        __int64 a2,
        unsigned int a3,
        struct _SAMPR_RID_ENUMERATION *a4)
{
  int v4; // edi
  int v5; // ebx
  UNICODE_STRING *v6; // r15
  unsigned int i; // r9d
  unsigned int v11; // ebx
  const UNICODE_STRING *v12; // rdx
  unsigned int *v13; // rsi
  int v14; // eax
  int v15; // ebx
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 AccountDomainHandle; // rax
  int v19; // ebx
  __int64 *v20; // rcx
  int TrustedDomainInfo; // ebx
  UNICODE_STRING *p_String1; // r8
  void *v24[2]; // [rsp+30h] [rbp-99h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-89h] BYREF
  __int128 v26; // [rsp+50h] [rbp-79h] BYREF
  __int128 v27; // [rsp+60h] [rbp-69h] BYREF
  _TRUSTED_DOMAIN_FULL_INFORMATION v28; // [rsp+70h] [rbp-59h] BYREF
  int v29; // [rsp+138h] [rbp+6Fh] BYREF

  v29 = 0;
  HIDWORD(v24[0]) = 0;
  LOBYTE(v4) = 0;
  v27 = 0;
  LOBYTE(v5) = 0;
  v6 = 0;
  v26 = 0;
  String1 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
        ((unsigned __int64)a1 + 56) & -(__int64)(a1 != 0));
  }
  LODWORD(v24[0]) = 11;
  v24[1] = &LsaDbpDsTrustedDomainFixupAttributes;
  v29 = LsaDbpDsReadByDsName(a1, 0, (struct _ATTRBLOCKSIMPLE *)v24, (struct _ATTRBLOCKSIMPLE *)&v27);
  if ( v29 >= 0 )
  {
    for ( i = 0; i < (unsigned int)v27; ++i )
    {
      if ( *(_DWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i) == 589956 )
      {
        v5 = **(_DWORD **)(*(_QWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i + 16) + 8LL);
      }
      else if ( *(_DWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i) == 589957 )
      {
        v6 = (UNICODE_STRING *)&v26;
        LOWORD(v26) = **(_WORD **)(*((_QWORD *)&v27 + 1) + 24LL * i + 16);
        WORD1(v26) = v26;
        *((_QWORD *)&v26 + 1) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i + 16) + 8LL);
      }
      else if ( *(_DWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i) != 589960 )
      {
        if ( *(_DWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i) == 590294 )
        {
          v4 = **(_DWORD **)(*(_QWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i + 16) + 8LL);
        }
        else if ( *(_DWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i) == 590335 )
        {
          String1.Length = **(_WORD **)(*((_QWORD *)&v27 + 1) + 24LL * i + 16);
          String1.MaximumLength = String1.Length;
          String1.Buffer = *(PWSTR *)(*(_QWORD *)(*((_QWORD *)&v27 + 1) + 24LL * i + 16) + 8LL);
        }
      }
    }
  }
  if ( v29 >= 0 && (v5 & 1) != 0 )
  {
    v11 = 0;
    if ( !a3 )
      goto LABEL_22;
    while ( 1 )
    {
      v12 = (const UNICODE_STRING *)((char *)a4 + 24 * v11 + 8);
      if ( String1.Length + 2LL == v12->Length )
      {
        v13 = (unsigned int *)((char *)a4 + 24 * v11);
        if ( RtlPrefixUnicodeString(&String1, v12, 1u) )
          break;
      }
      if ( ++v11 >= a3 )
        goto LABEL_22;
    }
    if ( !v13 )
    {
LABEL_22:
      memset_0(&v28, 0, sizeof(v28));
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
      v14 = LsapOpenSam();
      v15 = v14;
      if ( v14 >= 0 )
      {
        memset_0(&v28, 0, sizeof(v28));
        TrustedDomainInfo = LsaDbpDsGetTrustedDomainInfoEx(
                              a1,
                              0,
                              TrustedDomainFullInformation,
                              (union _LSAPR_TRUSTED_DOMAIN_INFO *)&v28,
                              0);
        if ( TrustedDomainInfo >= 0 )
          TrustedDomainInfo = LsaDbpDsCreateSetITAForTrustInfo(&v28);
        _fgu__LSAPR_TRUSTED_DOMAIN_INFO(&v28, 8);
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
            (unsigned int)TrustedDomainInfo);
        v29 = TrustedDomainInfo;
        if ( TrustedDomainInfo >= 0 )
          goto LABEL_45;
      }
      else
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
            (unsigned int)v14);
        v29 = v15;
      }
      v20 = LSAEVENT_ITA_FOR_TRUST_NOT_CREATED;
      goto LABEL_42;
    }
    if ( (v4 & 0x20) == 0 )
    {
      LsaDbpSaveDsThreadState();
      v16 = *v13;
      v24[0] = 0;
      AccountDomainHandle = LsapGetAccountDomainHandle(v17);
      v19 = SamrOpenUser(AccountDomainHandle, 985087, v16, v24);
      if ( v19 >= 0 )
        v19 = LsaDbpDsFixupTrustAccountPrimaryGroupIDWorker(v24[0], *v13, ((v4 & 8) == 0) | 0x210u);
      if ( v24[0] )
        SamrCloseHandle(v24);
      v29 = v19;
      LsaDbpRestoreDsThreadState();
      if ( v29 < 0 )
      {
        v20 = LSAEVENT_TRUST_PRIMARYGROUP_NOT_SET;
LABEL_42:
        p_String1 = &String1;
        if ( v6 )
          p_String1 = v6;
        SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)v20, L"ub", p_String1, 4, &v29);
      }
    }
  }
LABEL_45:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
      (unsigned int)v29);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180014a40  mov     byte ptr [rsp-8+arg_8], dl
0x180014a44  push    rbp
0x180014a45  push    rbx
0x180014a46  push    rsi
0x180014a47  push    rdi
0x180014a48  push    r12
0x180014a4a  push    r13
0x180014a4c  push    r14
0x180014a4e  push    r15
0x180014a50  lea     rbp, [rsp-1Fh]
0x180014a55  sub     rsp, 0E8h
0x180014a5c  xor     esi, esi
0x180014a5e  xorps   xmm0, xmm0
0x180014a61  xorps   xmm1, xmm1
0x180014a64  mov     [rbp+57h+arg_8], esi
0x180014a67  mov     dword ptr [rsp+120h+var_F0+4], esi
0x180014a6b  mov     edi, esi
0x180014a6d  movups  [rbp+57h+var_C0], xmm0
0x180014a71  mov     ebx, esi
0x180014a73  mov     r15d, esi
0x180014a76  movups  [rbp+57h+var_D0], xmm0
0x180014a7a  mov     r12, r9
0x180014a7d  mov     r14d, r8d
0x180014a80  movups  xmmword ptr [rsp+120h+String1.Length], xmm1
0x180014a85  mov     r13, rcx
0x180014a88  mov     r10, cs:WPP_GLOBAL_Control
0x180014a8f  test    byte ptr [r10+1Ch], 4
0x180014a94  jz      short loc_180014ADA
0x180014a96  mov     rcx, [r10+10h]
0x180014a9a  lea     edx, [rsi+16h]
0x180014a9d  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014aa4  call    WPP_SF_
0x180014aa9  mov     r10, cs:WPP_GLOBAL_Control
0x180014ab0  test    byte ptr [r10+1Ch], 4
0x180014ab5  jz      short loc_180014ADA
0x180014ab7  lea     rcx, [r13+38h]
0x180014abb  mov     rax, r13
0x180014abe  neg     rax
0x180014ac1  lea     edx, [rsi+17h]
0x180014ac4  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014acb  sbb     r9, r9
0x180014ace  and     r9, rcx
0x180014ad1  mov     rcx, [r10+10h]
0x180014ad5  call    WPP_SF_S
0x180014ada  lea     rax, ?LsaDbpDsTrustedDomainFixupAttributes@@3PAU_ATTRSIMPLE@@A; _ATTRSIMPLE near * LsaDbpDsTrustedDomainFixupAttributes
0x180014ae1  mov     dword ptr [rsp+120h+var_F0], 0Bh
0x180014ae9  lea     r9, [rbp+57h+var_C0]; struct _ATTRBLOCKSIMPLE *
0x180014aed  mov     [rsp+120h+var_E8], rax
0x180014af2  lea     r8, [rsp+120h+var_F0]; struct _ATTRBLOCKSIMPLE *
0x180014af7  xor     edx, edx; unsigned int
0x180014af9  mov     rcx, r13; struct _DSNAME *
0x180014afc  call    ?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z; LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)
0x180014b01  mov     [rbp+57h+arg_8], eax
0x180014b04  test    eax, eax
0x180014b06  js      loc_180014BB3
0x180014b0c  mov     r10d, dword ptr [rbp+57h+var_C0]
0x180014b10  mov     r9d, esi
0x180014b13  test    r10d, r10d
0x180014b16  jz      loc_180014BB3
0x180014b1c  mov     r8, qword ptr [rbp+57h+var_C0+8]
0x180014b20  mov     eax, r9d
0x180014b23  lea     rdx, [rax+rax*2]
0x180014b27  mov     ecx, [r8+rdx*8]
0x180014b2b  sub     ecx, 90084h
0x180014b31  jz      short loc_180014B9C
0x180014b33  sub     ecx, 1
0x180014b36  jz      short loc_180014B79
0x180014b38  sub     ecx, 3
0x180014b3b  jz      short loc_180014BA7
0x180014b3d  sub     ecx, 14Eh
0x180014b43  jz      short loc_180014B6C
0x180014b45  sub     ecx, 29h ; ')'
0x180014b48  jnz     short loc_180014BA7
0x180014b4a  mov     rax, [r8+rdx*8+10h]
0x180014b4f  movzx   ecx, word ptr [rax]
0x180014b52  mov     [rsp+120h+String1.Length], cx
0x180014b57  mov     [rsp+120h+String1.MaximumLength], cx
0x180014b5c  mov     rax, [r8+rdx*8+10h]
0x180014b61  mov     rcx, [rax+8]
0x180014b65  mov     [rsp+120h+String1.Buffer], rcx
0x180014b6a  jmp     short loc_180014BA7
0x180014b6c  mov     rax, [r8+rdx*8+10h]
0x180014b71  mov     rcx, [rax+8]
0x180014b75  mov     edi, [rcx]
0x180014b77  jmp     short loc_180014BA7
0x180014b79  mov     rax, [r8+rdx*8+10h]
0x180014b7e  lea     r15, [rbp+57h+var_D0]
0x180014b82  movzx   ecx, word ptr [rax]
0x180014b85  mov     word ptr [rbp+57h+var_D0], cx
0x180014b89  mov     word ptr [rbp+57h+var_D0+2], cx
0x180014b8d  mov     rax, [r8+rdx*8+10h]
0x180014b92  mov     rcx, [rax+8]
0x180014b96  mov     qword ptr [rbp+57h+var_D0+8], rcx
0x180014b9a  jmp     short loc_180014BA7
0x180014b9c  mov     rax, [r8+rdx*8+10h]
0x180014ba1  mov     rcx, [rax+8]
0x180014ba5  mov     ebx, [rcx]
0x180014ba7  inc     r9d
0x180014baa  cmp     r9d, r10d
0x180014bad  jb      loc_180014B20
0x180014bb3  cmp     [rbp+57h+arg_8], esi
0x180014bb6  jl      loc_180014DAD
0x180014bbc  test    bl, 1
0x180014bbf  jz      loc_180014DAD
0x180014bc5  mov     ebx, esi
0x180014bc7  test    r14d, r14d
0x180014bca  jz      short loc_180014C09
0x180014bcc  movzx   ecx, [rsp+120h+String1.Length]
0x180014bd1  lea     rdx, [r12+8]
0x180014bd6  mov     eax, ebx
0x180014bd8  add     rcx, 2
0x180014bdc  lea     r8, [rax+rax*2]
0x180014be0  lea     rdx, [rdx+r8*8]; String2
0x180014be4  movzx   eax, word ptr [rdx]
0x180014be7  cmp     rcx, rax
0x180014bea  jnz     short loc_180014C02
0x180014bec  lea     rsi, [r12+r8*8]
0x180014bf0  mov     r8b, 1; CaseInsensitive
0x180014bf3  lea     rcx, [rsp+120h+String1]; String1
0x180014bf8  call    cs:__imp_RtlPrefixUnicodeString
0x180014bfe  test    al, al
0x180014c00  jnz     short loc_180014C7D
0x180014c02  inc     ebx
0x180014c04  cmp     ebx, r14d
0x180014c07  jb      short loc_180014BCC
0x180014c09  mov     r14d, 70h ; 'p'
0x180014c0f  lea     rcx, [rbp+57h+var_B0]; void *
0x180014c13  mov     r8d, r14d; Size
0x180014c16  xor     edx, edx; Val
0x180014c18  call    memset_0
0x180014c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c24  lea     rsi, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180014c2b  mov     edi, 100h
0x180014c30  test    [rcx+1Ch], edi
0x180014c33  jz      short loc_180014C45
0x180014c35  mov     rcx, [rcx+10h]
0x180014c39  lea     edx, [r14-40h]
0x180014c3d  mov     r8, rsi
0x180014c40  call    WPP_SF_
0x180014c45  call    cs:__imp_LsapOpenSam
0x180014c4b  mov     ebx, eax
0x180014c4d  test    eax, eax
0x180014c4f  jns     loc_180014D0B
0x180014c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c5c  test    [rcx+1Ch], edi
0x180014c5f  jz      short loc_180014C75
0x180014c61  mov     rcx, [rcx+10h]
0x180014c65  mov     edx, 31h ; '1'
0x180014c6a  mov     r9d, eax
0x180014c6d  mov     r8, rsi
0x180014c70  call    WPP_SF_d
0x180014c75  mov     [rbp+57h+arg_8], ebx
0x180014c78  jmp     loc_180014D7E
0x180014c7d  test    rsi, rsi
0x180014c80  jz      short loc_180014C09
0x180014c82  test    dil, 20h
0x180014c86  jnz     loc_180014DAD
0x180014c8c  call    ?LsaDbpSaveDsThreadState@@YAXXZ; LsaDbpSaveDsThreadState(void)
0x180014c91  mov     ebx, [rsi]
0x180014c93  mov     [rsp+120h+var_F0], 0
0x180014c9c  call    cs:__imp_LsapGetAccountDomainHandle
0x180014ca2  lea     r9, [rsp+120h+var_F0]
0x180014ca7  mov     r8d, ebx
0x180014caa  mov     rcx, rax
0x180014cad  mov     edx, 0F07FFh
0x180014cb2  call    cs:__imp_SamrOpenUser
0x180014cb8  mov     ebx, eax
0x180014cba  test    eax, eax
0x180014cbc  js      short loc_180014CDD
0x180014cbe  mov     edx, [rsi]; unsigned int
0x180014cc0  mov     rcx, [rsp+120h+var_F0]; void *
0x180014cc5  shr     edi, 3
0x180014cc8  not     edi
0x180014cca  and     edi, 1
0x180014ccd  or      edi, 210h
0x180014cd3  mov     r8d, edi; unsigned int
0x180014cd6  call    ?LsaDbpDsFixupTrustAccountPrimaryGroupIDWorker@@YAJPEAXKK@Z; LsaDbpDsFixupTrustAccountPrimaryGroupIDWorker(void *,ulong,ulong)
0x180014cdb  mov     ebx, eax
0x180014cdd  cmp     [rsp+120h+var_F0], 0
0x180014ce3  jz      short loc_180014CF0
0x180014ce5  lea     rcx, [rsp+120h+var_F0]
0x180014cea  call    cs:__imp_SamrCloseHandle
0x180014cf0  mov     [rbp+57h+arg_8], ebx
0x180014cf3  call    ?LsaDbpRestoreDsThreadState@@YAXXZ; LsaDbpRestoreDsThreadState(void)
0x180014cf8  cmp     [rbp+57h+arg_8], 0
0x180014cfc  jge     loc_180014DAD
0x180014d02  lea     rcx, LSAEVENT_TRUST_PRIMARYGROUP_NOT_SET
0x180014d09  jmp     short loc_180014D85
0x180014d0b  mov     r8, r14; Size
0x180014d0e  lea     rcx, [rbp+57h+var_B0]; void *
0x180014d12  xor     edx, edx; Val
0x180014d14  call    memset_0
0x180014d19  mov     r14d, 8
0x180014d1f  mov     [rsp+120h+var_100], 0; unsigned int *
0x180014d28  mov     r8d, r14d; enum _TRUSTED_INFORMATION_CLASS
0x180014d2b  lea     r9, [rbp+57h+var_B0]; union _LSAPR_TRUSTED_DOMAIN_INFO *
0x180014d2f  xor     edx, edx; unsigned int
0x180014d31  mov     rcx, r13; struct _DSNAME *
0x180014d34  call    ?LsaDbpDsGetTrustedDomainInfoEx@@YAJPEAU_DSNAME@@KW4_TRUSTED_INFORMATION_CLASS@@PEAT_LSAPR_TRUSTED_DOMAIN_INFO@@PEAK@Z; LsaDbpDsGetTrustedDomainInfoEx(_DSNAME *,ulong,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO *,ulong *)
0x180014d39  mov     ebx, eax
0x180014d3b  test    eax, eax
0x180014d3d  js      short loc_180014D4A
0x180014d3f  lea     rcx, [rbp+57h+var_B0]; struct _TRUSTED_DOMAIN_FULL_INFORMATION *
0x180014d43  call    ?LsaDbpDsCreateSetITAForTrustInfo@@YAJPEAU_TRUSTED_DOMAIN_FULL_INFORMATION@@@Z; LsaDbpDsCreateSetITAForTrustInfo(_TRUSTED_DOMAIN_FULL_INFORMATION *)
0x180014d48  mov     ebx, eax
0x180014d4a  mov     edx, r14d
0x180014d4d  lea     rcx, [rbp+57h+var_B0]
0x180014d51  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x180014d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d5e  test    [rcx+1Ch], edi
0x180014d61  jz      short loc_180014D77
0x180014d63  mov     rcx, [rcx+10h]
0x180014d67  mov     edx, 32h ; '2'
0x180014d6c  mov     r9d, ebx
0x180014d6f  mov     r8, rsi
0x180014d72  call    WPP_SF_d
0x180014d77  mov     [rbp+57h+arg_8], ebx
0x180014d7a  test    ebx, ebx
0x180014d7c  jns     short loc_180014DAD
0x180014d7e  lea     rcx, LSAEVENT_ITA_FOR_TRUST_NOT_CREATED
0x180014d85  test    r15, r15
0x180014d88  lea     rax, [rbp+57h+arg_8]
0x180014d8c  lea     r8, [rsp+120h+String1]
0x180014d91  mov     [rsp+120h+var_100], rax
0x180014d96  cmovnz  r8, r15
0x180014d9a  lea     rdx, aUb; "ub"
0x180014da1  mov     r9d, 4
0x180014da7  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180014dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180014db4  test    byte ptr [rcx+1Ch], 4
0x180014db8  jz      short loc_180014DD3
0x180014dba  mov     r9d, [rbp+57h+arg_8]
0x180014dbe  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014dc5  mov     rcx, [rcx+10h]
0x180014dc9  mov     edx, 18h
0x180014dce  call    WPP_SF_d
0x180014dd3  mov     eax, [rbp+57h+arg_8]
0x180014dd6  add     rsp, 0E8h
0x180014ddd  pop     r15
0x180014ddf  pop     r14
0x180014de1  pop     r13
0x180014de3  pop     r12
0x180014de5  pop     rdi
0x180014de6  pop     rsi
0x180014de7  pop     rbx
0x180014de8  pop     rbp
0x180014de9  retn
```
