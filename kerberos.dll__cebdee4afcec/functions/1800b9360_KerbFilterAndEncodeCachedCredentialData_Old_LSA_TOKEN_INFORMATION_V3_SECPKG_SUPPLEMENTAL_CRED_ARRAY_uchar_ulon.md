# KerbFilterAndEncodeCachedCredentialData_Old(_LSA_TOKEN_INFORMATION_V3 *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *,uchar * *,ulong *)

- ea: `0x1800b9360`
- end: `0x1800b969b`
- name: `?KerbFilterAndEncodeCachedCredentialData_Old@@YAJPEAU_LSA_TOKEN_INFORMATION_V3@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z`
- size: `827`
- prototype: `int(struct _LSA_TOKEN_INFORMATION_V3 *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b8ef4`

## callees

- `0x1800069a0`
- `0x180032964`
- `0x180033540`
- `0x1800644b8`
- `0x18008b70c`
- `0x1800b9360`
- `0x1800ba968`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800b9404`
- `ntdll!RtlEqualUnicodeString` at `0x1800b9404`
- `LSASRV!LsaICheckProtectedUserByTokenInfo` at `0x1800b9507`
- `LSASRV!LsaICheckProtectedUserByTokenInfo` at `0x1800b9507`
- `LSASRV!LsaIDeriveCredentialKey` at `0x1800b95a5`
- `LSASRV!LsaIDeriveCredentialKey` at `0x1800b95a5`

## string_xrefs

- `0x1800b9513`: `LsaICheckProtectedUserByTokenInfo failed: %#x\n`
- `0x1800b93d0`: `KerbFilterAndEncodeCachedCredentialData_Old`
- `0x1800b9426`: `KerbFilterAndEncodeCachedCredentialData_Old`
- `0x1800b945e`: `KerbFilterAndEncodeCachedCredentialData_Old`
- `0x1800b9564`: `KerbFilterAndEncodeCachedCredentialData_Old`

## pseudocode

```c
__int64 __fastcall KerbFilterAndEncodeCachedCredentialData_Old(
        struct _LSA_TOKEN_INFORMATION_V3 *a1,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  PUCHAR v5; // rsi
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v6; // r14
  int v7; // ebx
  unsigned int v8; // ebx
  __int64 v9; // r15
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  const char *v13; // r9
  _DWORD *Credentials; // rax
  _BYTE *v16; // r15
  __int64 v17; // r12
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  char v21; // r9
  __int64 i; // r8
  char v23; // cl
  char v24; // al
  int v25; // eax
  unsigned int *v26; // r15
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v27; // r8
  unsigned int v28; // edx
  unsigned __int8 *v29; // rcx
  __int64 v30; // [rsp+20h] [rbp-69h]
  char v31; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int8 v32[7]; // [rsp+41h] [rbp-48h] BYREF
  __int64 v33; // [rsp+48h] [rbp-41h] BYREF
  struct _LSA_TOKEN_INFORMATION_V3 *v34; // [rsp+50h] [rbp-39h]
  unsigned int *v35; // [rsp+58h] [rbp-31h]
  void (*v36)(void); // [rsp+60h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-21h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v38; // [rsp+78h] [rbp-11h]
  __int128 v39; // [rsp+80h] [rbp-9h]
  int v40; // [rsp+90h] [rbp+7h]

  v34 = a1;
  v35 = a4;
  String2.Buffer = (PWSTR)L"NTLM";
  *a3 = 0;
  v5 = 0;
  *a4 = 0;
  v6 = *a2;
  v38 = a2;
  *(_QWORD *)&String2.Length = 655368;
  v32[0] = 0;
  v31 = 0;
  v33 = 0;
  v36 = 0;
  if ( v6 )
  {
    v8 = 0;
    if ( !v6->CredentialCount )
      goto LABEL_7;
    while ( 1 )
    {
      v9 = v8;
      if ( RtlEqualUnicodeString(&v6->Credentials[v9].PackageName, &String2, 1u) )
        break;
      if ( ++v8 >= v6->CredentialCount )
        goto LABEL_7;
    }
    Credentials = v6->Credentials[v9].Credentials;
    if ( !Credentials )
      goto LABEL_7;
    if ( (*Credentials & 0xFFFFFFFD) != 0 )
    {
      if ( *Credentials != 4 )
        goto LABEL_7;
    }
    else
    {
      v7 = KerbUpgradeNtlmSuppCred(&v6->Credentials[v9].PackageName, v32);
      if ( v7 < 0 )
      {
        KerbTracerT::Log(
          1,
          "KerbFilterAndEncodeCachedCredentialData_Old",
          6498,
          "Failed to upgrade NTLM supplemental credentials\n");
        goto LABEL_11;
      }
    }
    if ( v6->Credentials[v9].CredentialSize >= 0x44 )
    {
      v5 = v6->Credentials[v9].Credentials;
      if ( v5 )
      {
        if ( (v5[4] & 2) != 0 )
        {
          v11 = LsaICheckProtectedUserByTokenInfo(v34, 2, &v31);
          v7 = v11;
          if ( v11 < 0 )
          {
            v13 = "LsaICheckProtectedUserByTokenInfo failed: %#x\n";
            v12 = 6561;
            goto LABEL_10;
          }
          if ( v31 )
          {
            KerbTracerT::Log(
              8,
              "KerbFilterAndEncodeCachedCredentialData_Old",
              6571,
              "calling LSA to derive credential keys from NTOWF.\n");
            v16 = v5 + 12;
            v17 = 16;
            v11 = LsaIDeriveCredentialKey(0, v34, v5 + 12, 16, 3, &v33, &v36);
            v7 = v11;
            if ( v11 < 0 )
            {
              v13 = "LsaIDeriveCredentialKeys failed: %#x\n";
              v12 = 6585;
              goto LABEL_10;
            }
            do
            {
              *v16++ = 0;
              --v17;
            }
            while ( v17 );
            *((_DWORD *)v5 + 1) &= ~2u;
            *((_DWORD *)v5 + 1) |= 4u;
            if ( (*(_BYTE *)(v33 + 4) & 4) != 0 && *(_DWORD *)(v33 + 12) == 40 )
            {
              v18 = *(unsigned int *)(v33 + 8);
              v19 = 0;
              v40 = 0;
              v39 = 0;
              v20 = v33 + v18;
              do
                ++v19;
              while ( v19 != 20 );
              v21 = 0;
              for ( i = 0; i != 20; ++i )
              {
                v23 = *(_BYTE *)(i + v20 + 20);
                v24 = *((_BYTE *)&v39 + i);
                v21 |= v24 ^ v23;
              }
              if ( v21 )
              {
                *(_OWORD *)(v5 + 28) = *(_OWORD *)(v20 + 20);
                v25 = *(_DWORD *)(v20 + 36);
                *((_DWORD *)v5 + 1) |= 8u;
                *((_DWORD *)v5 + 11) = v25;
                *((_DWORD *)v5 + 2) = 4;
              }
            }
          }
          v26 = v35;
          v11 = PAC_EncodeCredentialData(v6, a3, v35);
          v7 = v11;
          if ( v11 >= 0 )
          {
            v27 = v38;
            v28 = *v26;
            v29 = *a3;
            *v38 = 0;
            v11 = PAC_DecodeCredentialData(v29, v28, v27);
            v7 = v11;
            if ( v11 >= 0 )
              goto LABEL_11;
            v13 = "PAC_UnmarshallCredentials failed: %#x\n";
            v12 = 6647;
LABEL_10:
            LODWORD(v30) = v11;
            KerbTracerT::Log(1, "KerbFilterAndEncodeCachedCredentialData_Old", v12, v13, v30);
            goto LABEL_11;
          }
          v12 = 6636;
LABEL_9:
          v13 = "PAC_EncodeCredentialData failed: %#x\n";
          goto LABEL_10;
        }
      }
    }
LABEL_7:
    KerbTracerT::Log(1, "KerbFilterAndEncodeCachedCredentialData_Old", 6537, "No NTOWF found.\n");
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    v11 = PAC_EncodeCredentialData(v6, a3, v35);
    v6 = 0;
    v7 = v11;
    if ( v11 >= 0 )
      goto LABEL_11;
    v12 = 6552;
    goto LABEL_9;
  }
  v7 = -1073741595;
  KerbTracerT::Log(1, "KerbFilterAndEncodeCachedCredentialData_Old", 6475, "Missing SupplementalCredentials");
LABEL_11:
  if ( v33 )
    v36();
  if ( v6 )
    KerbFree(v6);
  if ( v5 && v32[0] )
    KerbFree(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b9360  push    rbp
0x1800b9362  push    rbx
0x1800b9363  push    rsi
0x1800b9364  push    rdi
0x1800b9365  push    r12
0x1800b9367  push    r13
0x1800b9369  push    r14
0x1800b936b  push    r15
0x1800b936d  lea     rbp, [rsp-1Fh]
0x1800b9372  sub     rsp, 0A8h
0x1800b9379  mov     [rbp+57h+var_90], rcx
0x1800b937d  mov     r13, r8
0x1800b9380  lea     rcx, aNtlm; "NTLM"
0x1800b9387  mov     [rbp+57h+var_88], r9
0x1800b938b  mov     [rbp+57h+String2.Buffer], rcx
0x1800b938f  xor     ecx, ecx
0x1800b9391  mov     [r8], rcx
0x1800b9394  mov     esi, ecx
0x1800b9396  mov     [r9], ecx
0x1800b9399  mov     r14, [rdx]
0x1800b939c  mov     [rbp+57h+var_68], rdx
0x1800b93a0  mov     qword ptr [rbp+57h+String2.Length], 0A0008h
0x1800b93a8  mov     [rbp+57h+var_9F], cl
0x1800b93ab  mov     [rbp+57h+var_A0], cl
0x1800b93ae  mov     [rbp+57h+var_98], rcx
0x1800b93b2  mov     [rbp+57h+var_80], rcx
0x1800b93b6  test    r14, r14
0x1800b93b9  jnz     short loc_1800B93E1
0x1800b93bb  mov     ebx, 0C00000E5h
0x1800b93c0  lea     r9, aMissingSupplem; "Missing SupplementalCredentials"
0x1800b93c7  mov     r8d, 194Bh
0x1800b93cd  lea     ecx, [rsi+1]
0x1800b93d0  lea     rdx, aKerbfilterande_0; "KerbFilterAndEncodeCachedCredentialData"...
0x1800b93d7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b93dc  jmp     loc_1800B9470
0x1800b93e1  mov     ebx, ecx
0x1800b93e3  mov     edi, 1
0x1800b93e8  cmp     [r14], ecx
0x1800b93eb  jbe     short loc_1800B9419
0x1800b93ed  mov     r15d, ebx
0x1800b93f0  lea     rdx, [rbp+57h+String2]; String2
0x1800b93f4  shl     r15, 5
0x1800b93f8  mov     r8b, dil; CaseInsensitive
0x1800b93fb  lea     r12, [r15+r14]
0x1800b93ff  lea     rcx, [r12+8]; String1
0x1800b9404  call    cs:__imp_RtlEqualUnicodeString
0x1800b940a  test    al, al
0x1800b940c  jnz     loc_1800B94B8
0x1800b9412  add     ebx, edi
0x1800b9414  cmp     ebx, [r14]
0x1800b9417  jb      short loc_1800B93ED
0x1800b9419  lea     r9, aNoNtowfFound; "No NTOWF found.\n"
0x1800b9420  mov     r8d, 1989h
0x1800b9426  lea     rdx, aKerbfilterande_0; "KerbFilterAndEncodeCachedCredentialData"...
0x1800b942d  mov     ecx, edi
0x1800b942f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9434  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b9439  mov     r8, [rbp+57h+var_88]; unsigned int *
0x1800b943d  mov     rdx, r13; unsigned __int8 **
0x1800b9440  mov     rcx, r14; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *
0x1800b9443  call    ?PAC_EncodeCredentialData@@YAJPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z; PAC_EncodeCredentialData(_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,uchar * *,ulong *)
0x1800b9448  xor     r14d, r14d
0x1800b944b  mov     ebx, eax
0x1800b944d  test    eax, eax
0x1800b944f  jns     short loc_1800B9470
0x1800b9451  mov     r8d, 1998h
0x1800b9457  lea     r9, aPacEncodecrede; "PAC_EncodeCredentialData failed: %#x\n"
0x1800b945e  lea     rdx, aKerbfilterande_0; "KerbFilterAndEncodeCachedCredentialData"...
0x1800b9465  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800b9469  mov     ecx, edi
0x1800b946b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9470  mov     rcx, [rbp+57h+var_98]
0x1800b9474  test    rcx, rcx
0x1800b9477  jz      short loc_1800B9482
0x1800b9479  mov     rax, [rbp+57h+var_80]
0x1800b947d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9482  test    r14, r14
0x1800b9485  jz      short loc_1800B948F
0x1800b9487  mov     rcx, r14
0x1800b948a  call    KerbFree
0x1800b948f  test    rsi, rsi
0x1800b9492  jz      short loc_1800B94A2
0x1800b9494  cmp     [rbp+57h+var_9F], 0
0x1800b9498  jz      short loc_1800B94A2
0x1800b949a  mov     rcx, rsi
0x1800b949d  call    KerbFree
0x1800b94a2  mov     eax, ebx
0x1800b94a4  add     rsp, 0A8h
0x1800b94ab  pop     r15
0x1800b94ad  pop     r14
0x1800b94af  pop     r13
0x1800b94b1  pop     r12
0x1800b94b3  pop     rdi
0x1800b94b4  pop     rsi
0x1800b94b5  pop     rbx
0x1800b94b6  pop     rbp
0x1800b94b7  retn
0x1800b94b8  mov     rax, [r15+r14+20h]
0x1800b94bd  test    rax, rax
0x1800b94c0  jz      loc_1800B9419
0x1800b94c6  test    dword ptr [rax], 0FFFFFFFDh
0x1800b94cc  jz      short loc_1800B9525
0x1800b94ce  cmp     dword ptr [rax], 4
0x1800b94d1  jnz     loc_1800B9419
0x1800b94d7  cmp     dword ptr [r15+r14+18h], 44h ; 'D'
0x1800b94dd  jb      loc_1800B9419
0x1800b94e3  mov     rsi, [r15+r14+20h]
0x1800b94e8  test    rsi, rsi
0x1800b94eb  jz      loc_1800B9419
0x1800b94f1  mov     edx, 2
0x1800b94f6  test    [rsi+4], dl
0x1800b94f9  jz      loc_1800B9419
0x1800b94ff  mov     rcx, [rbp+57h+var_90]
0x1800b9503  lea     r8, [rbp+57h+var_A0]
0x1800b9507  call    cs:__imp_LsaICheckProtectedUserByTokenInfo
0x1800b950d  mov     ebx, eax
0x1800b950f  test    eax, eax
0x1800b9511  jns     short loc_1800B954D
0x1800b9513  lea     r9, aLsaicheckprote_0; "LsaICheckProtectedUserByTokenInfo faile"...
0x1800b951a  mov     r8d, 19A1h
0x1800b9520  jmp     loc_1800B945E
0x1800b9525  lea     rdx, [rbp+57h+var_9F]; unsigned __int8 *
0x1800b9529  lea     rcx, [r12+8]; String2
0x1800b952e  call    ?KerbUpgradeNtlmSuppCred@@YAJPEAU_SECPKG_SUPPLEMENTAL_CRED@@PEAE@Z; KerbUpgradeNtlmSuppCred(_SECPKG_SUPPLEMENTAL_CRED *,uchar *)
0x1800b9533  mov     ebx, eax
0x1800b9535  test    eax, eax
0x1800b9537  jns     short loc_1800B94D7
0x1800b9539  lea     r9, aFailedToUpgrad; "Failed to upgrade NTLM supplemental cre"...
0x1800b9540  mov     r8d, 1962h
0x1800b9546  mov     ecx, edi
0x1800b9548  jmp     loc_1800B93D0
0x1800b954d  cmp     [rbp+57h+var_A0], 0
0x1800b9551  jz      loc_1800B9645
0x1800b9557  lea     r9, aCallingLsaToDe; "calling LSA to derive credential keys f"...
0x1800b955e  mov     r8d, 19ABh
0x1800b9564  lea     rdx, aKerbfilterande_0; "KerbFilterAndEncodeCachedCredentialData"...
0x1800b956b  mov     ecx, 8
0x1800b9570  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9575  mov     rdx, [rbp+57h+var_90]
0x1800b9579  lea     rax, [rbp+57h+var_80]
0x1800b957d  mov     [rsp+0E0h+var_B0], rax
0x1800b9582  lea     r15, [rsi+0Ch]
0x1800b9586  lea     rax, [rbp+57h+var_98]
0x1800b958a  mov     r12d, 10h
0x1800b9590  mov     [rsp+0E0h+var_B8], rax
0x1800b9595  mov     r9d, r12d
0x1800b9598  mov     r8, r15
0x1800b959b  mov     dword ptr [rsp+0E0h+var_C0], 3
0x1800b95a3  xor     ecx, ecx
0x1800b95a5  call    cs:__imp_LsaIDeriveCredentialKey
0x1800b95ab  mov     ebx, eax
0x1800b95ad  test    eax, eax
0x1800b95af  jns     short loc_1800B95C3
0x1800b95b1  lea     r9, aLsaiderivecred_0; "LsaIDeriveCredentialKeys failed: %#x\n"
0x1800b95b8  mov     r8d, 19B9h
0x1800b95be  jmp     loc_1800B945E
0x1800b95c3  mov     byte ptr [r15], 0
0x1800b95c7  add     r15, rdi
0x1800b95ca  sub     r12, rdi
0x1800b95cd  jnz     short loc_1800B95C3
0x1800b95cf  and     dword ptr [rsi+4], 0FFFFFFFDh
0x1800b95d3  or      dword ptr [rsi+4], 4
0x1800b95d7  mov     rax, [rbp+57h+var_98]
0x1800b95db  test    byte ptr [rax+4], 4
0x1800b95df  jz      short loc_1800B9645
0x1800b95e1  cmp     dword ptr [rax+0Ch], 28h ; '('
0x1800b95e5  jnz     short loc_1800B9645
0x1800b95e7  mov     edx, [rax+8]
0x1800b95ea  xor     ecx, ecx
0x1800b95ec  xorps   xmm0, xmm0
0x1800b95ef  mov     [rbp+57h+var_50], ecx
0x1800b95f2  movups  [rbp+57h+var_60], xmm0
0x1800b95f6  add     rdx, rax
0x1800b95f9  mov     al, [rcx+rdx]
0x1800b95fc  mov     al, byte ptr [rbp+rcx+57h+var_60]
0x1800b9600  add     rcx, rdi
0x1800b9603  cmp     rcx, 14h
0x1800b9607  jnz     short loc_1800B95F9
0x1800b9609  xor     r9b, r9b
0x1800b960c  xor     r8d, r8d
0x1800b960f  mov     cl, [r8+rdx+14h]
0x1800b9614  mov     al, byte ptr [rbp+r8+57h+var_60]
0x1800b9619  add     r8, rdi
0x1800b961c  xor     cl, al
0x1800b961e  or      r9b, cl
0x1800b9621  cmp     r8, 14h
0x1800b9625  jnz     short loc_1800B960F
0x1800b9627  test    r9b, r9b
0x1800b962a  jz      short loc_1800B9645
0x1800b962c  movups  xmm0, xmmword ptr [rdx+14h]
0x1800b9630  movups  xmmword ptr [rsi+1Ch], xmm0
0x1800b9634  mov     eax, [rdx+24h]
0x1800b9637  or      dword ptr [rsi+4], 8
0x1800b963b  mov     [rsi+2Ch], eax
0x1800b963e  mov     dword ptr [rsi+8], 4
0x1800b9645  mov     r15, [rbp+57h+var_88]
0x1800b9649  mov     rdx, r13; unsigned __int8 **
0x1800b964c  mov     r8, r15; unsigned int *
0x1800b964f  mov     rcx, r14; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *
0x1800b9652  call    ?PAC_EncodeCredentialData@@YAJPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z; PAC_EncodeCredentialData(_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,uchar * *,ulong *)
0x1800b9657  mov     ebx, eax
0x1800b9659  test    eax, eax
0x1800b965b  jns     short loc_1800B9668
0x1800b965d  mov     r8d, 19ECh
0x1800b9663  jmp     loc_1800B9457
0x1800b9668  mov     r8, [rbp+57h+var_68]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x1800b966c  mov     edx, [r15]; unsigned int
0x1800b966f  mov     rcx, [r13+0]; unsigned __int8 *
0x1800b9673  mov     qword ptr [r8], 0
0x1800b967a  call    ?PAC_DecodeCredentialData@@YAJPEAEKPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; PAC_DecodeCredentialData(uchar *,ulong,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x1800b967f  mov     ebx, eax
0x1800b9681  test    eax, eax
0x1800b9683  jns     loc_1800B9470
0x1800b9689  lea     r9, aPacUnmarshallc; "PAC_UnmarshallCredentials failed: %#x\n"
0x1800b9690  mov     r8d, 19F7h
0x1800b9696  jmp     loc_1800B945E
```
