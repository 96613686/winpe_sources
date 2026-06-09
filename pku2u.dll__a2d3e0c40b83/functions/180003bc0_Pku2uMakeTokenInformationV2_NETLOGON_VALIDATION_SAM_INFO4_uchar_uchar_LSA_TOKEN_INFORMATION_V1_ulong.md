# Pku2uMakeTokenInformationV2(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar,uchar,_LSA_TOKEN_INFORMATION_V1 * *,ulong *)

- ea: `0x180003bc0`
- end: `0x1800041c4`
- name: `?Pku2uMakeTokenInformationV2@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@EEPEAPEAU_LSA_TOKEN_INFORMATION_V1@@PEAK@Z`
- size: `1540`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int8, unsigned __int8, struct _LSA_TOKEN_INFORMATION_V1 **, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001bf0`
- `0x18002d5f8`

## callees

- `0x180003bc0`
- `0x1800057f0`
- `0x18001fe88`
- `0x1800210f0`
- `0x180021a54`
- `0x180023ce0`
- `0x18002b408`
- `0x180038e0c`
- `0x180039908`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000406f`
- `ntdll!RtlCopySid` at `0x1800040d8`
- `ntdll!RtlCopySid` at `0x18000406f`
- `ntdll!RtlCopySid` at `0x1800040d8`
- `ntdll!RtlEqualSid` at `0x180003c21`
- `ntdll!RtlEqualSid` at `0x180003d96`
- `ntdll!RtlEqualSid` at `0x180003c21`
- `ntdll!RtlEqualSid` at `0x180003d96`
- `ntdll!RtlLengthSid` at `0x180003e6f`
- `ntdll!RtlLengthSid` at `0x180003ea9`
- `ntdll!RtlLengthSid` at `0x180003ecc`
- `ntdll!RtlLengthSid` at `0x180003f02`
- `ntdll!RtlLengthSid` at `0x180003f0d`
- `ntdll!RtlLengthSid` at `0x180004058`
- `ntdll!RtlLengthSid` at `0x1800040c0`
- `ntdll!RtlLengthSid` at `0x180003e6f`
- `ntdll!RtlLengthSid` at `0x180003ea9`
- `ntdll!RtlLengthSid` at `0x180003ecc`
- `ntdll!RtlLengthSid` at `0x180003f02`
- `ntdll!RtlLengthSid` at `0x180003f0d`
- `ntdll!RtlLengthSid` at `0x180004058`
- `ntdll!RtlLengthSid` at `0x1800040c0`
- `LSASRV!LsaIGetTokenInformationForLocalUser` at `0x180003cf8`
- `LSASRV!LsaIGetTokenInformationForLocalUser` at `0x180003cf8`

## pseudocode

```c
__int64 __fastcall Pku2uMakeTokenInformationV2(
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a1,
        __int64 a2,
        __int64 a3,
        struct _LSA_TOKEN_INFORMATION_V1 **a4,
        unsigned int *a5)
{
  unsigned int v5; // esi
  struct _LSA_TOKEN_INFORMATION_V1 *v8; // r15
  void *v9; // rdx
  int v10; // eax
  int ContainerUserToken; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  _WORD *v15; // rax
  _WORD *v16; // rdi
  __int64 v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct _LSA_TOKEN_INFO_AND_TYPE *v20; // rcx
  unsigned int v21; // edi
  ULONG v22; // r13d
  int v23; // eax
  basessp::BaseSSP *v24; // rcx
  void *v25; // rdi
  ULONG v26; // esi
  ULONG v27; // eax
  unsigned __int64 v28; // rsi
  struct _LSA_TOKEN_INFORMATION_V1 *v29; // rax
  SID_AND_ATTRIBUTES *v31; // r13
  bool v32; // zf
  __int64 v33; // rdi
  char *i; // r13
  unsigned int v35; // eax
  unsigned int v36; // r14d
  ULONG v37; // eax
  __int64 v38; // rdi
  ULONG v39; // eax
  __int64 v40; // rdi
  struct _LSA_TOKEN_INFO_AND_TYPE *v41; // [rsp+30h] [rbp-40h] BYREF
  TOKEN_USER *p_User; // [rsp+38h] [rbp-38h]
  __int128 v43; // [rsp+40h] [rbp-30h]
  _DWORD Sid1[4]; // [rsp+50h] [rbp-20h] BYREF

  v5 = 0;
  v41 = 0;
  Sid1[0] = 257;
  Sid1[1] = 83886080;
  *a5 = 0;
  v8 = 0;
  v9 = (void *)*((_QWORD *)a1 + 28);
  v43 = 0;
  Sid1[2] = 21;
  if ( RtlEqualSid(Sid1, v9) && *((_DWORD *)a1 + 37) == 42 )
  {
    v10 = *((unsigned __int16 *)a1 + 24);
    if ( !(_WORD)v10 )
    {
      ContainerUserToken = -1073741726;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_61;
      v13 = 30;
      v14 = 3221225570LL;
      goto LABEL_7;
    }
    if ( *((_QWORD *)a1 + 7) )
    {
      if ( (unsigned __int16)v10 > 0xFFFCu )
      {
        ContainerUserToken = -1073741562;
        goto LABEL_61;
      }
      v15 = (_WORD *)((__int64 (__fastcall *)(_QWORD))Pku2uGlobalLsaFunctions->AllocateLsaHeap)((unsigned int)(v10 + 2));
      *((_QWORD *)&v43 + 1) = v15;
      v16 = v15;
      if ( !v15 )
      {
        ContainerUserToken = -1073741670;
        goto LABEL_61;
      }
      memcpy_0(v15, *((const void **)a1 + 7), *((unsigned __int16 *)a1 + 24));
      v16[(unsigned __int64)*((unsigned __int16 *)a1 + 24) >> 1] = 0;
    }
    else
    {
      *((_QWORD *)&v43 + 1) = 0;
    }
    ContainerUserToken = LsaIGetTokenInformationForLocalUser(*((_QWORD *)&v43 + 1), &v41);
    if ( ContainerUserToken < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_61;
      v13 = 31;
      v14 = (unsigned int)ContainerUserToken;
LABEL_7:
      WPP_SF_d(v12[2], v13, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids, v14);
      goto LABEL_61;
    }
    v17 = *(unsigned int *)v41;
    if ( (_DWORD)v17 != 2 )
    {
      ContainerUserToken = -1073741726;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_61;
      v19 = 32;
      goto LABEL_23;
    }
    goto LABEL_35;
  }
  if ( RtlEqualSid(Sid1, *((PSID *)a1 + 28)) && *((_DWORD *)a1 + 37) == 43 )
  {
    ContainerUserToken = Pku2uGetContainerUserToken(&v41);
    if ( ContainerUserToken < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
          (unsigned int)ContainerUserToken);
      goto LABEL_61;
    }
    v17 = *(unsigned int *)v41;
    if ( (_DWORD)v17 != 2 )
    {
      ContainerUserToken = -1073741726;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_61;
      v19 = 34;
LABEL_23:
      WPP_SF_dd(v18[2], v19, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids, v17, -1073741726);
      goto LABEL_61;
    }
    *a5 |= 1u;
LABEL_35:
    v20 = v41;
    ContainerUserToken = 0;
    *a4 = (struct _LSA_TOKEN_INFORMATION_V1 *)*((_QWORD *)v41 + 1);
    *((_QWORD *)v20 + 1) = 0;
    goto LABEL_61;
  }
  v21 = *((_DWORD *)a1 + 39);
  v22 = 88;
  LODWORD(p_User) = v21;
  if ( v21 )
    v22 = v21 * (RtlLengthSid(*((PSID *)a1 + 28)) + 4) + 88;
  if ( (*((_BYTE *)a1 + 168) & 0x20) != 0 )
  {
    v23 = *((_DWORD *)a1 + 68);
    v21 += v23;
    LODWORD(p_User) = v21;
    if ( v23 )
    {
      do
        v22 += RtlLengthSid(*(PSID *)(*((_QWORD *)a1 + 35) + 16LL * v5++));
      while ( v5 < *((_DWORD *)a1 + 68) );
    }
  }
  if ( *((_DWORD *)a1 + 37) )
  {
    v24 = (basessp::BaseSSP *)(v22 + 2 * RtlLengthSid(*((PSID *)a1 + 28)) + 8);
  }
  else
  {
    if ( !*((_DWORD *)a1 + 68) )
    {
      ContainerUserToken = -1073741232;
      goto LABEL_61;
    }
    v25 = (void *)**((_QWORD **)a1 + 35);
    v26 = RtlLengthSid(*((PSID *)a1 + 28));
    v27 = RtlLengthSid(v25);
    v21 = (unsigned int)p_User;
    v24 = (basessp::BaseSSP *)(v22 + v27 + v26 + 4);
  }
  v28 = (unsigned int)v24 + 16 * (v21 - 1);
  v29 = (struct _LSA_TOKEN_INFORMATION_V1 *)basessp::BaseSSP::WSTAllocate2(v24, v28);
  v8 = v29;
  if ( !v29 )
    return 3221225495LL;
  memset_0(v29, 0, v28);
  v8->Groups = (PTOKEN_GROUPS)&v8[1];
  v31 = &v8[1].User.User + v21;
  v8[1].ExpirationTime.LowPart = 0;
  v8->ExpirationTime.LowPart = *((_DWORD *)a1 + 4);
  v8->ExpirationTime.HighPart = *((_DWORD *)a1 + 5);
  v32 = *((_DWORD *)a1 + 37) == 0;
  p_User = &v8->User;
  if ( v32 )
  {
    p_User = &v8->User;
  }
  else
  {
    v8->User.User.Sid = v31;
    v31 = (SID_AND_ATTRIBUTES *)((char *)v31
                               + KerbCopyDomainRelativeSid(
                                   &v8[1].User.User + v21,
                                   *((PSID *)a1 + 28),
                                   *((_DWORD *)a1 + 37)));
  }
  v8->PrimaryGroup.PrimaryGroup = v31;
  v33 = 0;
  for ( i = (char *)v31 + KerbCopyDomainRelativeSid(v31, *((PSID *)a1 + 28), *((_DWORD *)a1 + 38));
        (unsigned int)v33 < *((_DWORD *)a1 + 39);
        ++v8->Groups->GroupCount )
  {
    v8->Groups->Groups[v8->Groups->GroupCount].Attributes = *(_DWORD *)(8 * v33 + *((_QWORD *)a1 + 20) + 4);
    v8->Groups->Groups[v8->Groups->GroupCount].Sid = i;
    v35 = KerbCopyDomainRelativeSid(i, *((PSID *)a1 + 28), *(_DWORD *)(8 * v33 + *((_QWORD *)a1 + 20)));
    v33 = (unsigned int)(v33 + 1);
    i += v35;
  }
  if ( (*((_BYTE *)a1 + 168) & 0x20) != 0 )
  {
    v36 = 0;
    if ( !v8->User.User.Sid )
    {
      v8->User.User.Sid = i;
      v37 = RtlLengthSid(**((PSID **)a1 + 35));
      v38 = v37;
      RtlCopySid(v37, i, **((PSID **)a1 + 35));
      i += v38;
      v36 = 1;
    }
    for ( ; v36 < *((_DWORD *)a1 + 68); ++v8->Groups->GroupCount )
    {
      v8->Groups->Groups[v8->Groups->GroupCount].Attributes = *(_DWORD *)(*((_QWORD *)a1 + 35) + 16LL * v36 + 8);
      v8->Groups->Groups[v8->Groups->GroupCount].Sid = i;
      v39 = RtlLengthSid(*(PSID *)(*((_QWORD *)a1 + 35) + 16LL * v36));
      v40 = v39;
      RtlCopySid(v39, i, *(PSID *)(*((_QWORD *)a1 + 35) + 16LL * v36));
      i += v40;
      ++v36;
    }
  }
  if ( p_User->User.Sid )
  {
    v8->Privileges = 0;
    v8->Owner.Owner = 0;
    v8->DefaultDacl.DefaultDacl = 0;
    *a4 = v8;
    v8 = 0;
    ContainerUserToken = 0;
  }
  else
  {
    ContainerUserToken = -1073741232;
  }
LABEL_61:
  if ( *((_QWORD *)&v43 + 1) )
    ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
  if ( v41 )
  {
    if ( *((_QWORD *)v41 + 1) )
      ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
    if ( *((_QWORD *)v41 + 2) )
      ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
    ((void (__fastcall *)(struct _LSA_TOKEN_INFO_AND_TYPE *))Pku2uGlobalLsaFunctions->FreeLsaHeap)(v41);
  }
  if ( v8 )
    Pku2uFree(v8);
  return (unsigned int)ContainerUserToken;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp-38h+arg_8], rbx
0x180003bc5  push    rbp
0x180003bc6  push    rsi
0x180003bc7  push    rdi
0x180003bc8  push    r12
0x180003bca  push    r13
0x180003bcc  push    r14
0x180003bce  push    r15
0x180003bd0  mov     rbp, rsp
0x180003bd3  sub     rsp, 70h
0x180003bd7  mov     rax, cs:__security_cookie
0x180003bde  xor     rax, rsp
0x180003be1  mov     [rbp+var_10], rax
0x180003be5  mov     rdi, [rbp+arg_20]
0x180003be9  xor     esi, esi
0x180003beb  mov     rbx, rcx
0x180003bee  mov     [rbp+var_40], rsi
0x180003bf2  xorps   xmm0, xmm0
0x180003bf5  mov     [rbp+Sid1], 101h
0x180003bfc  mov     r12, r9
0x180003bff  mov     [rbp+var_1C], 5000000h
0x180003c06  mov     [rdi], esi
0x180003c08  mov     r15d, esi
0x180003c0b  mov     rdx, [rcx+0E0h]; Sid2
0x180003c12  lea     rcx, [rbp+Sid1]; Sid1
0x180003c16  movups  [rbp+var_30], xmm0
0x180003c1a  mov     [rbp+var_18], 15h
0x180003c21  call    cs:__imp_RtlEqualSid
0x180003c27  test    al, al
0x180003c29  jz      loc_180003D8B
0x180003c2f  cmp     dword ptr [rbx+94h], 2Ah ; '*'
0x180003c36  jnz     loc_180003D8B
0x180003c3c  movzx   eax, word ptr [rbx+30h]
0x180003c40  test    ax, ax
0x180003c43  jnz     short loc_180003C8B
0x180003c45  mov     ebx, 0C0000062h
0x180003c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c51  lea     rax, WPP_GLOBAL_Control
0x180003c58  cmp     rcx, rax
0x180003c5b  jz      loc_180004125
0x180003c61  test    byte ptr [rcx+1Ch], 1
0x180003c65  jz      loc_180004125
0x180003c6b  mov     edx, 1Eh
0x180003c70  mov     r9d, 0C0000062h
0x180003c76  mov     rcx, [rcx+10h]
0x180003c7a  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180003c81  call    WPP_SF_d
0x180003c86  jmp     loc_180004125
0x180003c8b  cmp     [rbx+38h], rsi
0x180003c8f  jz      short loc_180003CEC
0x180003c91  mov     ecx, 0FFFCh
0x180003c96  cmp     ax, cx
0x180003c99  jbe     short loc_180003CA5
0x180003c9b  mov     ebx, 0C0000106h
0x180003ca0  jmp     loc_180004125
0x180003ca5  lea     ecx, [rax+2]
0x180003ca8  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180003caf  mov     rax, [rax+28h]
0x180003cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb8  mov     qword ptr [rbp+var_30+8], rax
0x180003cbc  mov     rdi, rax
0x180003cbf  test    rax, rax
0x180003cc2  jnz     short loc_180003CCE
0x180003cc4  mov     ebx, 0C000009Ah
0x180003cc9  jmp     loc_180004125
0x180003cce  movzx   r8d, word ptr [rbx+30h]; Size
0x180003cd3  mov     rcx, rdi; void *
0x180003cd6  mov     rdx, [rbx+38h]; Src
0x180003cda  call    memcpy_0
0x180003cdf  movzx   ecx, word ptr [rbx+30h]
0x180003ce3  shr     rcx, 1
0x180003ce6  mov     [rdi+rcx*2], si
0x180003cea  jmp     short loc_180003CF0
0x180003cec  mov     qword ptr [rbp+var_30+8], rsi
0x180003cf0  mov     rcx, qword ptr [rbp+var_30+8]
0x180003cf4  lea     rdx, [rbp+var_40]
0x180003cf8  call    cs:__imp_LsaIGetTokenInformationForLocalUser
0x180003cfe  mov     ebx, eax
0x180003d00  test    eax, eax
0x180003d02  jns     short loc_180003D32
0x180003d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d0b  lea     rax, WPP_GLOBAL_Control
0x180003d12  cmp     rcx, rax
0x180003d15  jz      loc_180004125
0x180003d1b  test    byte ptr [rcx+1Ch], 1
0x180003d1f  jz      loc_180004125
0x180003d25  mov     edx, 1Fh
0x180003d2a  mov     r9d, ebx
0x180003d2d  jmp     loc_180003C76
0x180003d32  mov     rax, [rbp+var_40]
0x180003d36  mov     r9d, [rax]
0x180003d39  cmp     r9d, 2
0x180003d3d  jz      loc_180003E3E
0x180003d43  mov     ebx, 0C0000062h
0x180003d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d4f  lea     rax, WPP_GLOBAL_Control
0x180003d56  cmp     rcx, rax
0x180003d59  jz      loc_180004125
0x180003d5f  test    byte ptr [rcx+1Ch], 1
0x180003d63  jz      loc_180004125
0x180003d69  mov     edx, 20h ; ' '
0x180003d6e  mov     rcx, [rcx+10h]
0x180003d72  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180003d79  mov     [rsp+70h+var_50], 0C0000062h
0x180003d81  call    WPP_SF_dd
0x180003d86  jmp     loc_180004125
0x180003d8b  mov     rdx, [rbx+0E0h]; Sid2
0x180003d92  lea     rcx, [rbp+Sid1]; Sid1
0x180003d96  call    cs:__imp_RtlEqualSid
0x180003d9c  test    al, al
0x180003d9e  jz      loc_180003E55
0x180003da4  cmp     dword ptr [rbx+94h], 2Bh ; '+'
0x180003dab  jnz     loc_180003E55
0x180003db1  lea     rcx, [rbp+var_40]; struct _LSA_TOKEN_INFO_AND_TYPE **
0x180003db5  call    ?Pku2uGetContainerUserToken@@YAJPEAPEAU_LSA_TOKEN_INFO_AND_TYPE@@@Z; Pku2uGetContainerUserToken(_LSA_TOKEN_INFO_AND_TYPE * *)
0x180003dba  mov     ebx, eax
0x180003dbc  test    eax, eax
0x180003dbe  jns     short loc_180003DFE
0x180003dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dc7  lea     rax, WPP_GLOBAL_Control
0x180003dce  cmp     rcx, rax
0x180003dd1  jz      loc_180004125
0x180003dd7  test    byte ptr [rcx+1Ch], 1
0x180003ddb  jz      loc_180004125
0x180003de1  mov     rcx, [rcx+10h]
0x180003de5  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180003dec  mov     edx, 21h ; '!'
0x180003df1  mov     r9d, ebx
0x180003df4  call    WPP_SF_d
0x180003df9  jmp     loc_180004125
0x180003dfe  mov     rax, [rbp+var_40]
0x180003e02  mov     r9d, [rax]
0x180003e05  cmp     r9d, 2
0x180003e09  jz      short loc_180003E3B
0x180003e0b  mov     ebx, 0C0000062h
0x180003e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e17  lea     rax, WPP_GLOBAL_Control
0x180003e1e  cmp     rcx, rax
0x180003e21  jz      loc_180004125
0x180003e27  test    byte ptr [rcx+1Ch], 1
0x180003e2b  jz      loc_180004125
0x180003e31  mov     edx, 22h ; '"'
0x180003e36  jmp     loc_180003D6E
0x180003e3b  or      dword ptr [rdi], 1
0x180003e3e  mov     rcx, [rbp+var_40]
0x180003e42  mov     ebx, esi
0x180003e44  mov     rax, [rcx+8]
0x180003e48  mov     [r12], rax
0x180003e4c  mov     [rcx+8], rsi
0x180003e50  jmp     loc_180004125
0x180003e55  mov     edi, [rbx+9Ch]
0x180003e5b  mov     r13d, 58h ; 'X'
0x180003e61  mov     dword ptr [rbp+var_38], edi
0x180003e64  test    edi, edi
0x180003e66  jz      short loc_180003E81
0x180003e68  mov     rcx, [rbx+0E0h]; Sid
0x180003e6f  call    cs:__imp_RtlLengthSid
0x180003e75  lea     r13d, [rax+4]
0x180003e79  imul    r13d, edi
0x180003e7d  add     r13d, 58h ; 'X'
0x180003e81  test    byte ptr [rbx+0A8h], 20h
0x180003e88  jz      short loc_180003EBC
0x180003e8a  mov     eax, [rbx+110h]
0x180003e90  add     edi, eax
0x180003e92  mov     dword ptr [rbp+var_38], edi
0x180003e95  test    eax, eax
0x180003e97  jz      short loc_180003EBC
0x180003e99  mov     rcx, [rbx+118h]
0x180003ea0  mov     eax, esi
0x180003ea2  add     rax, rax
0x180003ea5  mov     rcx, [rcx+rax*8]; Sid
0x180003ea9  call    cs:__imp_RtlLengthSid
0x180003eaf  add     r13d, eax
0x180003eb2  inc     esi
0x180003eb4  cmp     esi, [rbx+110h]
0x180003eba  jb      short loc_180003E99
0x180003ebc  cmp     [rbx+94h], r15d
0x180003ec3  jz      short loc_180003EDE
0x180003ec5  mov     rcx, [rbx+0E0h]; Sid
0x180003ecc  call    cs:__imp_RtlLengthSid
0x180003ed2  lea     ecx, ds:8[rax*2]
0x180003ed9  add     ecx, r13d
0x180003edc  jmp     short loc_180003F1E
0x180003ede  cmp     [rbx+110h], r15d
0x180003ee5  ja      short loc_180003EF1
0x180003ee7  mov     ebx, 0C0000250h
0x180003eec  jmp     loc_180004125
0x180003ef1  mov     rax, [rbx+118h]
0x180003ef8  mov     rcx, [rbx+0E0h]; Sid
0x180003eff  mov     rdi, [rax]
0x180003f02  call    cs:__imp_RtlLengthSid
0x180003f08  mov     rcx, rdi; Sid
0x180003f0b  mov     esi, eax
0x180003f0d  call    cs:__imp_RtlLengthSid
0x180003f13  mov     edi, dword ptr [rbp+var_38]
0x180003f16  lea     ecx, [rsi+4]
0x180003f19  add     eax, r13d
0x180003f1c  add     ecx, eax; this
0x180003f1e  lea     eax, [rdi-1]
0x180003f21  shl     eax, 4
0x180003f24  add     eax, ecx
0x180003f26  mov     edx, eax; unsigned __int64
0x180003f28  mov     esi, eax
0x180003f2a  call    ?WSTAllocate2@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate2(unsigned __int64)
0x180003f2f  mov     r15, rax
0x180003f32  test    rax, rax
0x180003f35  jnz     short loc_180003F41
0x180003f37  mov     eax, 0C0000017h
0x180003f3c  jmp     loc_1800041A0
0x180003f41  mov     r8, rsi; Size
0x180003f44  xor     edx, edx; Val
0x180003f46  mov     rcx, r15; void *
0x180003f49  call    memset_0
0x180003f4e  lea     rcx, [r15+40h]
0x180003f52  mov     eax, edi
0x180003f54  shl     rax, 4
0x180003f58  lea     r13, [rcx+8]
0x180003f5c  mov     [r15+18h], rcx
0x180003f60  add     r13, rax
0x180003f63  mov     dword ptr [rcx], 0
0x180003f69  mov     eax, [rbx+10h]
0x180003f6c  mov     [r15], eax
0x180003f6f  mov     eax, [rbx+14h]
0x180003f72  mov     [r15+4], eax
0x180003f76  lea     rax, [r15+8]
0x180003f7a  cmp     dword ptr [rbx+94h], 0
0x180003f81  mov     [rbp+var_38], rax
0x180003f85  jz      short loc_180003FA7
0x180003f87  mov     [rax], r13
0x180003f8a  mov     rcx, r13; Sid
0x180003f8d  mov     r8d, [rbx+94h]; unsigned int
0x180003f94  mov     rdx, [rbx+0E0h]; SourceSid
0x180003f9b  call    ?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z; KerbCopyDomainRelativeSid(void *,void *,ulong)
0x180003fa0  mov     eax, eax
0x180003fa2  add     r13, rax
0x180003fa5  jmp     short loc_180003FAB
0x180003fa7  mov     [rbp+var_38], rax
0x180003fab  mov     [r15+20h], r13
0x180003faf  mov     rcx, r13; Sid
0x180003fb2  mov     r8d, [rbx+98h]; unsigned int
0x180003fb9  mov     rdx, [rbx+0E0h]; SourceSid
0x180003fc0  call    ?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z; KerbCopyDomainRelativeSid(void *,void *,ulong)
0x180003fc5  mov     eax, eax
0x180003fc7  xor     edi, edi
0x180003fc9  add     r13, rax
0x180003fcc  cmp     [rbx+9Ch], edi
0x180003fd2  jbe     short loc_180004034
0x180003fd4  mov     rdx, [r15+18h]
0x180003fd8  lea     r9, ds:0[rdi*8]
0x180003fe0  mov     rax, [rbx+0A0h]
0x180003fe7  mov     ecx, [rdx]
0x180003fe9  mov     eax, [r9+rax+4]
0x180003fee  inc     rcx
0x180003ff1  add     rcx, rcx
0x180003ff4  mov     [rdx+rcx*8], eax
0x180003ff7  mov     rcx, [r15+18h]
0x180003ffb  mov     eax, [rcx]
0x180003ffd  add     rax, rax
0x180004000  mov     [rcx+rax*8+8], r13
0x180004005  mov     rcx, r13; Sid
0x180004008  mov     r8, [rbx+0A0h]
0x18000400f  mov     rdx, [rbx+0E0h]; SourceSid
0x180004016  mov     r8d, [r9+r8]; unsigned int
0x18000401a  call    ?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z; KerbCopyDomainRelativeSid(void *,void *,ulong)
0x18000401f  mov     eax, eax
0x180004021  inc     edi
0x180004023  add     r13, rax
0x180004026  mov     rax, [r15+18h]
0x18000402a  inc     dword ptr [rax]
0x18000402c  cmp     edi, [rbx+9Ch]
0x180004032  jb      short loc_180003FD4
0x180004034  test    byte ptr [rbx+0A8h], 20h
0x18000403b  jz      loc_1800040F3
0x180004041  xor     r14d, r14d
0x180004044  cmp     [r15+8], r14
0x180004048  jnz     short loc_18000407E
0x18000404a  mov     [r15+8], r13
0x18000404e  mov     rcx, [rbx+118h]
0x180004055  mov     rcx, [rcx]; Sid
0x180004058  call    cs:__imp_RtlLengthSid
0x18000405e  mov     r8, [rbx+118h]
0x180004065  mov     rdx, r13; DestinationSid
0x180004068  mov     ecx, eax; DestinationSidLength
0x18000406a  mov     edi, eax
0x18000406c  mov     r8, [r8]; SourceSid
0x18000406f  call    cs:__imp_RtlCopySid
0x180004075  add     r13, rdi
0x180004078  mov     r14d, 1
0x18000407e  cmp     r14d, [rbx+110h]
0x180004085  jnb     short loc_1800040F3
0x180004087  mov     rax, [rbx+118h]
0x18000408e  mov     rdx, [r15+18h]
0x180004092  mov     esi, r14d
0x180004095  add     rsi, rsi
0x180004098  mov     ecx, [rdx]
0x18000409a  inc     rcx
0x18000409d  mov     eax, [rax+rsi*8+8]
0x1800040a1  add     rcx, rcx
0x1800040a4  mov     [rdx+rcx*8], eax
0x1800040a7  mov     rcx, [r15+18h]
  ... truncated ...
```
