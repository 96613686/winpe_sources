# LsaDbpDsCreateSetITAForTrustInfo(_TRUSTED_DOMAIN_FULL_INFORMATION *)

- ea: `0x18001819c`
- end: `0x180018633`
- name: `?LsaDbpDsCreateSetITAForTrustInfo@@YAJPEAU_TRUSTED_DOMAIN_FULL_INFORMATION@@@Z`
- size: `1175`
- prototype: `__int64 __fastcall(struct _TRUSTED_DOMAIN_FULL_INFORMATION *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014a40`
- `0x180018084`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x180012fa4`
- `0x180015748`
- `0x180015790`
- `0x18001819c`
- `0x180018eb0`
- `0x180019c64`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapOpenSam` at `0x180018273`
- `LSASRV!LsapOpenSam` at `0x180018273`
- `LSASRV!LsapGetAccountDomainHandle` at `0x1800183f2`
- `LSASRV!LsapGetAccountDomainHandle` at `0x1800185d1`
- `LSASRV!LsapGetAccountDomainHandle` at `0x1800183f2`
- `LSASRV!LsapGetAccountDomainHandle` at `0x1800185d1`
- `ntdll!RtlInitUnicodeString` at `0x1800183b9`
- `ntdll!RtlInitUnicodeString` at `0x1800183b9`
- `SAMSRV!SamrSetInformationUser` at `0x1800184aa`
- `SAMSRV!SamrSetInformationUser` at `0x1800184aa`
- `SAMSRV!SamrCloseHandle` at `0x18001848b`
- `SAMSRV!SamrCloseHandle` at `0x18001854d`
- `SAMSRV!SamrCloseHandle` at `0x18001848b`
- `SAMSRV!SamrCloseHandle` at `0x18001854d`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x180018478`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x180018478`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180018463`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180018463`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x180018429`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x180018429`
- `SAMSRV!SamrCreateUser2InDomain` at `0x180018609`
- `SAMSRV!SamrCreateUser2InDomain` at `0x180018609`

## pseudocode

```c
__int64 __fastcall LsaDbpDsCreateSetITAForTrustInfo(struct _TRUSTED_DOMAIN_FULL_INFORMATION *a1)
{
  _QWORD *v2; // rcx
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  ULONG IncomingAuthInfos; // edx
  unsigned int v8; // r12d
  char v9; // r15
  PLSA_AUTH_INFORMATION IncomingAuthenticationInformation; // rsi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rcx
  size_t Length; // rbx
  enum _SECPKG_NAME_TYPE v15; // edx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  ULONG TrustAttributes; // edi
  unsigned int v21; // edi
  _QWORD *v22; // rcx
  int v23; // edx
  __int64 AccountDomainHandle; // rax
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  void *v26; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v32[14]; // [rsp+90h] [rbp-70h] BYREF
  __int16 AuthInfoLength; // [rsp+170h] [rbp+70h]
  __int16 v34; // [rsp+172h] [rbp+72h]
  PUCHAR AuthInfo; // [rsp+178h] [rbp+78h]
  int v36; // [rsp+1A8h] [rbp+A8h]
  int v37; // [rsp+1ACh] [rbp+ACh]
  char v38; // [rsp+1C9h] [rbp+C9h]
  WCHAR SourceString[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v26 = 0;
  v28 = 0;
  LOWORD(v32[0]) = 0;
  v25 = 0;
  memset_0((char *)v32 + 2, 0, 0x34Eu);
  DestinationString = 0;
  v2 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1->Information.FlatName.Length <= 0x200u )
  {
    v4 = LsapOpenSam();
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        return (unsigned int)v4;
      v6 = 39;
LABEL_45:
      WPP_SF_d(v5[2], v6, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids, (unsigned int)v4);
      return (unsigned int)v4;
    }
    IncomingAuthInfos = a1->AuthInformation.IncomingAuthInfos;
    v8 = 0;
    v9 = 0;
    if ( IncomingAuthInfos )
    {
      IncomingAuthenticationInformation = a1->AuthInformation.IncomingAuthenticationInformation;
      v11 = 0;
      do
      {
        v12 = v11;
        if ( IncomingAuthenticationInformation[v11].AuthType == 2 )
        {
          memset_0(v32, 0, 0x13Cu);
          v8 = 21;
          AuthInfo = IncomingAuthenticationInformation[v12].AuthInfo;
          AuthInfoLength = IncomingAuthenticationInformation[v12].AuthInfoLength;
          v34 = AuthInfoLength;
          v38 = 1;
          v37 = 17825792;
          v36 = 68;
          goto LABEL_20;
        }
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < IncomingAuthInfos );
      v13 = 0;
      while ( IncomingAuthenticationInformation[v13].AuthType != 1 )
      {
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= IncomingAuthInfos )
          goto LABEL_21;
      }
      memset(v32, 0, 35);
      v8 = 18;
      v32[0] = *(_OWORD *)IncomingAuthenticationInformation[v13].AuthInfo;
      LOBYTE(v32[2]) = 1;
LABEL_20:
      v9 = 1;
    }
LABEL_21:
    LsaDbpSaveDsThreadState();
    memset_0(SourceString, 0, 0x204u);
    Length = a1->Information.FlatName.Length;
    memcpy_0(SourceString, a1->Information.FlatName.Buffer, Length);
    SourceString[Length >> 1] = 36;
    RtlInitUnicodeString(&DestinationString, SourceString);
    v16 = LsaDbpDsOpenSamUser(&DestinationString, v15, &v26);
    v4 = v16;
    if ( v16 < 0 )
    {
      if ( v16 != -1073741724 && v16 != -1073741709 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_41;
        v23 = 41;
LABEL_40:
        WPP_SF_ZD(
          v22[2],
          v23,
          (unsigned int)&WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
          (unsigned int)&DestinationString,
          v16);
LABEL_41:
        if ( v26 )
          SamrCloseHandle(&v26);
        LsaDbpRestoreDsThreadState();
        v5 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          return (unsigned int)v4;
        v6 = 44;
        goto LABEL_45;
      }
      AccountDomainHandle = LsapGetAccountDomainHandle(v17);
      v16 = SamrCreateUser2InDomain(AccountDomainHandle, &DestinationString, 64, 0x2000000, &v26, &v28, &v25);
      v4 = v16;
      if ( v16 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_41;
        v23 = 40;
        goto LABEL_40;
      }
    }
    else
    {
      v29 = 0;
      v31 = 0;
      v30 = 0;
      v18 = LsapGetAccountDomainHandle(v17);
      v4 = SamIGetUserLogonInformationEx(v18, 520, &DestinationString, 1048580, &v29, &v31, &v30);
      if ( v4 < 0 )
        goto LABEL_41;
      v19 = v29;
      v25 = *(_DWORD *)(v29 + 272);
      if ( (*(_BYTE *)(v29 + 280) & 0x40) == 0 )
        v4 = -1073741725;
      if ( *((_QWORD *)&v31 + 1) )
      {
        SamIFreeSidAndAttributesList(&v31);
        v19 = v29;
      }
      if ( v19 )
        SamIFree_SAMPR_USER_INFO_BUFFER(v19, 21);
      if ( v30 )
        SamrCloseHandle(&v30);
      if ( v4 < 0 )
        goto LABEL_41;
    }
    if ( v9 )
    {
      v4 = SamrSetInformationUser(v26, v8, v32);
      if ( v4 < 0 )
        goto LABEL_41;
    }
    TrustAttributes = a1->Information.TrustAttributes;
    if ( (TrustAttributes & 0x20) != 0 )
      goto LABEL_41;
    v21 = ((TrustAttributes & 8) == 0) | 0x210;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_ZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
        (unsigned int)&DestinationString,
        v25);
    v16 = LsaDbpDsFixupTrustAccountPrimaryGroupIDWorker(v26, v25, v21);
    v4 = v16;
    if ( v16 >= 0 )
      goto LABEL_41;
    v22 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_41;
    v23 = 43;
    goto LABEL_40;
  }
  if ( (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    WPP_SF_ZD(v2[2], 38, (unsigned int)&WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids, (_DWORD)a1 + 16, 51);
  return 3221225523LL;
}

```

## disassembly

```asm
0x18001819c  mov     [rsp-8+arg_8], rbx
0x1800181a1  mov     [rsp-8+arg_10], rsi
0x1800181a6  push    rbp
0x1800181a7  push    rdi
0x1800181a8  push    r12
0x1800181aa  push    r14
0x1800181ac  push    r15
0x1800181ae  lea     rbp, [rsp-500h]
0x1800181b6  sub     rsp, 600h
0x1800181bd  mov     rax, cs:__security_cookie
0x1800181c4  xor     rax, rsp
0x1800181c7  mov     [rbp+520h+var_30], rax
0x1800181ce  mov     rdi, rcx
0x1800181d1  mov     [rsp+620h+var_5D8], 0
0x1800181da  xor     eax, eax
0x1800181dc  mov     [rsp+620h+var_5C0], 0
0x1800181e4  lea     rcx, [rbp+520h+var_590+2]; void *
0x1800181e8  mov     word ptr [rbp+520h+var_590], ax
0x1800181ec  xor     edx, edx; Val
0x1800181ee  mov     [rsp+620h+var_5E0], 0
0x1800181f6  mov     r8d, 34Eh; Size
0x1800181fc  call    memset_0
0x180018201  xorps   xmm0, xmm0
0x180018204  movups  xmmword ptr [rsp+620h+DestinationString.Length], xmm0
0x180018209  mov     rcx, cs:WPP_GLOBAL_Control
0x180018210  lea     r15, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180018217  mov     esi, 100h
0x18001821c  test    [rcx+1Ch], esi
0x18001821f  jz      short loc_180018239
0x180018221  mov     rcx, [rcx+10h]
0x180018225  mov     edx, 25h ; '%'
0x18001822a  mov     r8, r15
0x18001822d  call    WPP_SF_
0x180018232  mov     rcx, cs:WPP_GLOBAL_Control
0x180018239  lea     r14, [rdi+10h]
0x18001823d  mov     eax, 200h
0x180018242  cmp     [r14], ax
0x180018246  jbe     short loc_180018273
0x180018248  test    [rcx+1Ch], esi
0x18001824b  jz      short loc_180018269
0x18001824d  mov     rcx, [rcx+10h]
0x180018251  mov     edx, 26h ; '&'
0x180018256  mov     r9, r14
0x180018259  mov     dword ptr [rsp+620h+var_600], 0C0000033h
0x180018261  mov     r8, r15
0x180018264  call    WPP_SF_ZD
0x180018269  mov     eax, 0C0000033h
0x18001826e  jmp     loc_18001857E
0x180018273  call    cs:__imp_LsapOpenSam
0x180018279  mov     ebx, eax
0x18001827b  test    eax, eax
0x18001827d  jns     short loc_18001829C
0x18001827f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018286  test    [rcx+1Ch], esi
0x180018289  jz      loc_18001857C
0x18001828f  mov     edx, 27h ; '''
0x180018294  mov     r8, r15
0x180018297  jmp     loc_180018570
0x18001829c  mov     edx, [rdi+40h]
0x18001829f  xor     r12d, r12d
0x1800182a2  xor     r15b, r15b
0x1800182a5  test    edx, edx
0x1800182a7  jz      loc_18001836D
0x1800182ad  mov     rsi, [rdi+48h]
0x1800182b1  xor     ecx, ecx
0x1800182b3  lea     rbx, [rcx+rcx*2]
0x1800182b7  cmp     dword ptr [rsi+rbx*8+8], 2
0x1800182bc  jz      short loc_18001831D
0x1800182be  inc     ecx
0x1800182c0  cmp     ecx, edx
0x1800182c2  jb      short loc_1800182B3
0x1800182c4  xor     ecx, ecx
0x1800182c6  lea     r8, [rcx+rcx*2]
0x1800182ca  cmp     dword ptr [rsi+r8*8+8], 1
0x1800182d0  jz      short loc_1800182DD
0x1800182d2  inc     ecx
0x1800182d4  cmp     ecx, edx
0x1800182d6  jb      short loc_1800182C6
0x1800182d8  jmp     loc_180018368
0x1800182dd  xor     eax, eax
0x1800182df  xorps   xmm0, xmm0
0x1800182e2  movups  [rbp+520h+var_590], xmm0
0x1800182e6  mov     r12d, 12h
0x1800182ec  movups  [rbp+520h+var_580], xmm0
0x1800182f0  mov     dword ptr [rbp+520h+var_580+0Fh], eax
0x1800182f3  mov     rcx, [rsi+r8*8+10h]
0x1800182f8  movzx   eax, word ptr [rcx]
0x1800182fb  mov     word ptr [rbp+520h+var_590], ax
0x1800182ff  movsd   xmm0, qword ptr [rcx+2]
0x180018304  movsd   qword ptr [rbp+520h+var_590+2], xmm0
0x180018309  mov     eax, [rcx+0Ah]
0x18001830c  mov     dword ptr [rbp+520h+var_590+0Ah], eax
0x18001830f  movzx   eax, word ptr [rcx+0Eh]
0x180018313  mov     word ptr [rbp+520h+var_590+0Eh], ax
0x180018317  mov     [rbp+520h+var_570], 1
0x18001831b  jmp     short loc_180018365
0x18001831d  xor     edx, edx; Val
0x18001831f  lea     rcx, [rbp+520h+var_590]; void *
0x180018323  mov     r8d, 13Ch; Size
0x180018329  call    memset_0
0x18001832e  mov     rax, [rsi+rbx*8+10h]
0x180018333  mov     r12d, 15h
0x180018339  mov     [rbp+520h+var_4A8], rax
0x18001833d  movzx   eax, word ptr [rsi+rbx*8+0Ch]
0x180018342  mov     [rbp+520h+var_4B0], ax
0x180018346  mov     [rbp+520h+var_4AE], ax
0x18001834a  mov     [rbp+520h+var_457], 1
0x180018351  mov     [rbp+520h+var_474], 1100000h
0x18001835b  mov     [rbp+520h+var_478], 44h ; 'D'
0x180018365  mov     r15b, 1
0x180018368  mov     esi, 100h
0x18001836d  call    ?LsaDbpSaveDsThreadState@@YAXXZ; LsaDbpSaveDsThreadState(void)
0x180018372  xor     edx, edx; Val
0x180018374  lea     rcx, [rbp+520h+SourceString]; void *
0x18001837b  mov     r8d, 204h; Size
0x180018381  call    memset_0
0x180018386  movzx   ebx, word ptr [r14]
0x18001838a  lea     rcx, [rbp+520h+SourceString]; void *
0x180018391  mov     rdx, [r14+8]; Src
0x180018395  mov     r8d, ebx; Size
0x180018398  call    memcpy_0
0x18001839d  mov     eax, 24h ; '$'
0x1800183a2  shr     rbx, 1
0x1800183a5  lea     rdx, [rbp+520h+SourceString]; SourceString
0x1800183ac  lea     rcx, [rsp+620h+DestinationString]; DestinationString
0x1800183b1  mov     [rbp+rbx*2+520h+SourceString], ax
0x1800183b9  call    cs:__imp_RtlInitUnicodeString
0x1800183bf  lea     r8, [rsp+620h+var_5D8]; void **
0x1800183c4  lea     rcx, [rsp+620h+DestinationString]; struct _UNICODE_STRING *
0x1800183c9  call    ?LsaDbpDsOpenSamUser@@YAJPEAU_UNICODE_STRING@@W4_SECPKG_NAME_TYPE@@PEAPEAX@Z; LsaDbpDsOpenSamUser(_UNICODE_STRING *,_SECPKG_NAME_TYPE,void * *)
0x1800183ce  mov     ebx, eax
0x1800183d0  test    eax, eax
0x1800183d2  js      loc_1800185A9
0x1800183d8  xorps   xmm0, xmm0
0x1800183db  mov     [rsp+620h+var_5B8], 0
0x1800183e4  movups  [rsp+620h+var_5A8], xmm0
0x1800183e9  mov     [rsp+620h+var_5B0], 0
0x1800183f2  call    cs:__imp_LsapGetAccountDomainHandle
0x1800183f8  mov     r9d, 100004h
0x1800183fe  lea     r8, [rsp+620h+DestinationString]
0x180018403  mov     rcx, rax
0x180018406  mov     edx, 208h
0x18001840b  lea     rax, [rsp+620h+var_5B0]
0x180018410  mov     [rsp+620h+var_5F0], rax
0x180018415  lea     rax, [rsp+620h+var_5A8]
0x18001841a  mov     [rsp+620h+var_5F8], rax
0x18001841f  lea     rax, [rsp+620h+var_5B8]
0x180018424  mov     [rsp+620h+var_600], rax
0x180018429  call    cs:__imp_SamIGetUserLogonInformationEx
0x18001842f  mov     ebx, eax
0x180018431  test    eax, eax
0x180018433  js      loc_180018540
0x180018439  mov     rcx, [rsp+620h+var_5B8]
0x18001843e  mov     eax, [rcx+110h]
0x180018444  mov     [rsp+620h+var_5E0], eax
0x180018448  mov     eax, 0C0000063h
0x18001844d  test    byte ptr [rcx+118h], 40h
0x180018454  cmovz   ebx, eax
0x180018457  cmp     qword ptr [rbp+520h+var_5A8+8], 0
0x18001845c  jz      short loc_18001846E
0x18001845e  lea     rcx, [rsp+620h+var_5A8]
0x180018463  call    cs:__imp_SamIFreeSidAndAttributesList
0x180018469  mov     rcx, [rsp+620h+var_5B8]
0x18001846e  test    rcx, rcx
0x180018471  jz      short loc_18001847E
0x180018473  mov     edx, 15h
0x180018478  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x18001847e  cmp     [rsp+620h+var_5B0], 0
0x180018484  jz      short loc_180018491
0x180018486  lea     rcx, [rsp+620h+var_5B0]
0x18001848b  call    cs:__imp_SamrCloseHandle
0x180018491  test    ebx, ebx
0x180018493  js      loc_180018540
0x180018499  test    r15b, r15b
0x18001849c  jz      short loc_1800184BA
0x18001849e  mov     rcx, [rsp+620h+var_5D8]
0x1800184a3  lea     r8, [rbp+520h+var_590]
0x1800184a7  mov     edx, r12d
0x1800184aa  call    cs:__imp_SamrSetInformationUser
0x1800184b0  mov     ebx, eax
0x1800184b2  test    eax, eax
0x1800184b4  js      loc_180018540
0x1800184ba  mov     edi, [rdi+30h]
0x1800184bd  test    dil, 20h
0x1800184c1  jnz     short loc_180018540
0x1800184c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184ca  shr     edi, 3
0x1800184cd  not     edi
0x1800184cf  and     edi, 1
0x1800184d2  or      edi, 210h
0x1800184d8  test    [rcx+1Ch], esi
0x1800184db  jz      short loc_1800184FF
0x1800184dd  mov     eax, [rsp+620h+var_5E0]
0x1800184e1  lea     r9, [rsp+620h+DestinationString]
0x1800184e6  mov     rcx, [rcx+10h]
0x1800184ea  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800184f1  mov     edx, 2Ah ; '*'
0x1800184f6  mov     dword ptr [rsp+620h+var_600], eax
0x1800184fa  call    WPP_SF_ZD
0x1800184ff  mov     edx, [rsp+620h+var_5E0]; unsigned int
0x180018503  mov     r8d, edi; unsigned int
0x180018506  mov     rcx, [rsp+620h+var_5D8]; void *
0x18001850b  call    ?LsaDbpDsFixupTrustAccountPrimaryGroupIDWorker@@YAJPEAXKK@Z; LsaDbpDsFixupTrustAccountPrimaryGroupIDWorker(void *,ulong,ulong)
0x180018510  mov     ebx, eax
0x180018512  test    eax, eax
0x180018514  jns     short loc_180018540
0x180018516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001851d  test    [rcx+1Ch], esi
0x180018520  jz      short loc_180018540
0x180018522  mov     edx, 2Bh ; '+'
0x180018527  mov     rcx, [rcx+10h]
0x18001852b  lea     r9, [rsp+620h+DestinationString]
0x180018530  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180018537  mov     dword ptr [rsp+620h+var_600], eax
0x18001853b  call    WPP_SF_ZD
0x180018540  cmp     [rsp+620h+var_5D8], 0
0x180018546  jz      short loc_180018553
0x180018548  lea     rcx, [rsp+620h+var_5D8]
0x18001854d  call    cs:__imp_SamrCloseHandle
0x180018553  call    ?LsaDbpRestoreDsThreadState@@YAXXZ; LsaDbpRestoreDsThreadState(void)
0x180018558  mov     rcx, cs:WPP_GLOBAL_Control
0x18001855f  test    [rcx+1Ch], esi
0x180018562  jz      short loc_18001857C
0x180018564  mov     edx, 2Ch ; ','
0x180018569  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180018570  mov     rcx, [rcx+10h]
0x180018574  mov     r9d, ebx
0x180018577  call    WPP_SF_d
0x18001857c  mov     eax, ebx
0x18001857e  mov     rcx, [rbp+520h+var_30]
0x180018585  xor     rcx, rsp; StackCookie
0x180018588  call    __security_check_cookie
0x18001858d  lea     r11, [rsp+620h+var_20]
0x180018595  mov     rbx, [r11+38h]
0x180018599  mov     rsi, [r11+40h]
0x18001859d  mov     rsp, r11
0x1800185a0  pop     r15
0x1800185a2  pop     r14
0x1800185a4  pop     r12
0x1800185a6  pop     rdi
0x1800185a7  pop     rbp
0x1800185a8  retn
0x1800185a9  cmp     eax, 0C0000064h
0x1800185ae  jz      short loc_1800185D1
0x1800185b0  cmp     eax, 0C0000073h
0x1800185b5  jz      short loc_1800185D1
0x1800185b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185be  test    [rcx+1Ch], esi
0x1800185c1  jz      loc_180018540
0x1800185c7  mov     edx, 29h ; ')'
0x1800185cc  jmp     loc_180018527
0x1800185d1  call    cs:__imp_LsapGetAccountDomainHandle
0x1800185d7  mov     r9d, 2000000h
0x1800185dd  lea     rdx, [rsp+620h+DestinationString]
0x1800185e2  mov     rcx, rax
0x1800185e5  mov     r8d, 40h ; '@'
0x1800185eb  lea     rax, [rsp+620h+var_5E0]
0x1800185f0  mov     [rsp+620h+var_5F0], rax
0x1800185f5  lea     rax, [rsp+620h+var_5C0]
0x1800185fa  mov     [rsp+620h+var_5F8], rax
0x1800185ff  lea     rax, [rsp+620h+var_5D8]
0x180018604  mov     [rsp+620h+var_600], rax
0x180018609  call    cs:__imp_SamrCreateUser2InDomain
0x18001860f  mov     ebx, eax
0x180018611  test    eax, eax
0x180018613  jns     loc_180018499
0x180018619  mov     rcx, cs:WPP_GLOBAL_Control
0x180018620  test    [rcx+1Ch], esi
0x180018623  jz      loc_180018540
0x180018629  mov     edx, 28h ; '('
0x18001862e  jmp     loc_180018527
```
