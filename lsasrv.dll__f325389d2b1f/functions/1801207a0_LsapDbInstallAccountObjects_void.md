# LsapDbInstallAccountObjects(void)

- ea: `0x1801207a0`
- end: `0x180120e9b`
- name: `?LsapDbInstallAccountObjects@@YAJXZ`
- size: `1787`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18011ff64`

## callees

- `0x180011278`
- `0x1800b86d0`
- `0x1801206c0`
- `0x1801207a0`
- `0x180120ea4`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180120a5e`
- `ntdll!RtlSubAuthoritySid` at `0x180120adc`
- `ntdll!RtlSubAuthoritySid` at `0x180120b4e`
- `ntdll!RtlSubAuthoritySid` at `0x180120b8f`
- `ntdll!RtlSubAuthoritySid` at `0x180120bd0`
- `ntdll!RtlSubAuthoritySid` at `0x180120c15`
- `ntdll!RtlSubAuthoritySid` at `0x180120c66`
- `ntdll!RtlSubAuthoritySid` at `0x180120c9e`
- `ntdll!RtlSubAuthoritySid` at `0x180120cef`
- `ntdll!RtlSubAuthoritySid` at `0x180120d30`
- `ntdll!RtlSubAuthoritySid` at `0x180120a5e`
- `ntdll!RtlSubAuthoritySid` at `0x180120adc`
- `ntdll!RtlSubAuthoritySid` at `0x180120b4e`
- `ntdll!RtlSubAuthoritySid` at `0x180120b8f`
- `ntdll!RtlSubAuthoritySid` at `0x180120bd0`
- `ntdll!RtlSubAuthoritySid` at `0x180120c15`
- `ntdll!RtlSubAuthoritySid` at `0x180120c66`
- `ntdll!RtlSubAuthoritySid` at `0x180120c9e`
- `ntdll!RtlSubAuthoritySid` at `0x180120cef`
- `ntdll!RtlSubAuthoritySid` at `0x180120d30`
- `ntdll!RtlFreeSid` at `0x180120e36`
- `ntdll!RtlFreeSid` at `0x180120e47`
- `ntdll!RtlFreeSid` at `0x180120e58`
- `ntdll!RtlFreeSid` at `0x180120e69`
- `ntdll!RtlFreeSid` at `0x180120e36`
- `ntdll!RtlFreeSid` at `0x180120e47`
- `ntdll!RtlFreeSid` at `0x180120e58`
- `ntdll!RtlFreeSid` at `0x180120e69`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012083e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180120890`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801208d6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012091c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012083e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180120890`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801208d6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012091c`

## pseudocode

```c
__int64 LsapDbInstallAccountObjects(void)
{
  __int64 v0; // rcx
  __int64 v1; // rax
  int v2; // edi
  NTSTATUS updated; // ebx
  unsigned int v4; // r8d
  int v5; // eax
  int v6; // eax
  PULONG v7; // rax
  unsigned int v8; // r8d
  PULONG v9; // rax
  PSID v11; // [rsp+60h] [rbp-A0h] BYREF
  PSID v12; // [rsp+68h] [rbp-98h] BYREF
  PSID v13; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v17[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v18; // [rsp+98h] [rbp-68h]
  int v19; // [rsp+A0h] [rbp-60h]
  __int64 v20; // [rsp+A4h] [rbp-5Ch]
  int v21; // [rsp+ACh] [rbp-54h]
  __int64 v22; // [rsp+B0h] [rbp-50h]
  __int64 v23; // [rsp+BCh] [rbp-44h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  __int64 v25; // [rsp+D4h] [rbp-2Ch]
  __int64 v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+ECh] [rbp-14h]
  __int64 v28; // [rsp+F8h] [rbp-8h]
  __int64 v29; // [rsp+104h] [rbp+4h]
  __int64 v30; // [rsp+110h] [rbp+10h]
  __int64 v31; // [rsp+11Ch] [rbp+1Ch]
  __int64 v32; // [rsp+128h] [rbp+28h]
  __int64 v33; // [rsp+134h] [rbp+34h]
  __int64 v34; // [rsp+140h] [rbp+40h]
  __int64 v35; // [rsp+14Ch] [rbp+4Ch]
  __int64 v36; // [rsp+158h] [rbp+58h]
  __int64 v37; // [rsp+164h] [rbp+64h]
  __int64 v38; // [rsp+170h] [rbp+70h]
  __int64 v39; // [rsp+17Ch] [rbp+7Ch]
  __int64 v40; // [rsp+188h] [rbp+88h]
  __int64 v41; // [rsp+194h] [rbp+94h]
  __int64 v42; // [rsp+1A0h] [rbp+A0h]
  __int64 v43; // [rsp+1ACh] [rbp+ACh]

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v0 = 0;
  *(_DWORD *)v15.Value = 0;
  *(_WORD *)&v15.Value[4] = 1280;
  Sid = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  v17[1] = 0;
  do
  {
    v1 = 3 * v0++;
    *(&v19 + v1) = 0;
  }
  while ( v0 != 36 );
  v2 = 2;
  updated = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( updated >= 0 )
  {
    updated = RtlAllocateAndInitializeSid(&v15, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v11);
    if ( updated >= 0 )
    {
      updated = RtlAllocateAndInitializeSid(&v15, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &v13);
      if ( updated >= 0 )
      {
        updated = RtlAllocateAndInitializeSid(&v15, 2u, 0x63u, 0, 0, 0, 0, 0, 0, 0, &v12);
        if ( updated >= 0 )
        {
          v4 = 2;
          v18 = 23;
          v19 = 3;
          v17[0] = 1;
          if ( LsapProductType == NtProductWinNt )
          {
            v4 = 1027;
            v20 = 19;
            v21 = 3;
            v17[0] = 2;
          }
          v5 = LsapDbInitializeAccount(Sid, (struct _LSAPR_PRIVILEGE_SET *)v17, v4);
          updated = v5;
          v19 = 0;
          if ( v17[0] == 2 )
            v21 = 0;
          if ( v5 >= 0 )
          {
            v25 = 24;
            v17[0] = 24;
            v18 = 8;
            v20 = 17;
            v22 = 18;
            v23 = 12;
            v24 = 19;
            v26 = 9;
            v27 = 20;
            v28 = 22;
            v29 = 11;
            v30 = 13;
            v31 = 14;
            v32 = 10;
            v33 = 15;
            v34 = 5;
            v35 = 25;
            v36 = 28;
            v37 = 29;
            v38 = 30;
            v39 = 33;
            v40 = 34;
            v41 = 35;
            v42 = 23;
            v43 = 36;
            *RtlSubAuthoritySid(v11, 1u) = 544;
            v6 = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 7u);
            updated = v6;
            if ( v6 < 0 )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  10,
                  WPP_cbb2005f17923cdf8e072379aa1bb2c9_Traceguids,
                  (unsigned int)v6);
              goto LABEL_40;
            }
            v18 = 17;
            v20 = 18;
            v22 = 19;
            v17[0] = 3;
            *RtlSubAuthoritySid(v11, 1u) = 551;
            updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 1u);
          }
        }
      }
    }
  }
  if ( updated < 0 )
    goto LABEL_40;
  if ( LsapProductType == NtProductLanManNt )
  {
    v18 = 17;
    v20 = 18;
    v22 = 12;
    v23 = 19;
    v24 = 24;
    v17[0] = 5;
    *RtlSubAuthoritySid(v11, 1u) = 549;
    updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 1u);
    if ( updated < 0 )
      goto LABEL_40;
    v18 = 19;
    v17[0] = 1;
    *RtlSubAuthoritySid(v11, 1u) = 548;
    updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 1u);
    if ( updated < 0 )
      goto LABEL_40;
    v18 = 19;
    v17[0] = 1;
    v7 = RtlSubAuthoritySid(v11, 1u);
    v8 = 1;
    *v7 = 550;
    goto LABEL_28;
  }
  v18 = 23;
  v20 = 33;
  if ( LsapProductType == NtProductWinNt )
  {
    v22 = 19;
    v2 = 3;
  }
  v17[0] = v2;
  *RtlSubAuthoritySid(v11, 1u) = 545;
  updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 3u);
  if ( updated >= 0 )
  {
    v18 = 23;
    v20 = 33;
    v22 = 34;
    v17[0] = 3;
    *RtlSubAuthoritySid(v11, 1u) = 581;
    updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 3u);
    if ( updated >= 0 )
    {
      v17[0] = 0;
      *RtlSubAuthoritySid(v11, 1u) = 546;
      updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 1u);
      if ( updated >= 0 )
      {
        v18 = 23;
        v20 = 33;
        v22 = 34;
        v17[0] = 3;
        *RtlSubAuthoritySid(v11, 1u) = 583;
        updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, 3u);
        if ( updated >= 0 )
        {
          v18 = 23;
          v17[0] = 1;
          v9 = RtlSubAuthoritySid(v11, 1u);
          v8 = 0;
          *v9 = 584;
LABEL_28:
          updated = LsapDbInitializeAccount(v11, (struct _LSAPR_PRIVILEGE_SET *)v17, v8);
          if ( updated >= 0 )
          {
            v18 = 14;
            v17[0] = 1;
            updated = LsapDbInitializeAccount(v13, (struct _LSAPR_PRIVILEGE_SET *)v17, 1u);
            if ( updated >= 0 )
            {
              v17[0] = 0;
              updated = LsapDbInitializeAccount(v12, (struct _LSAPR_PRIVILEGE_SET *)v17, 0x10u);
              if ( updated >= 0 )
              {
                updated = LsapUpdatePrivilegeAssignments(0x10009u);
                if ( updated >= 0 )
                {
                  updated = LsapUpdatePrivilegeAssignments(0x1000Au);
                  if ( updated >= 0 )
                  {
                    updated = LsapUpdatePrivilegeAssignments(0x1000Cu);
                    if ( updated >= 0 )
                    {
                      updated = LsapUpdatePrivilegeAssignments(0x1000Du);
                      if ( updated >= 0 )
                      {
                        updated = LsapUpdatePrivilegeAssignments(0x1000Eu);
                        if ( updated >= 0 )
                        {
                          updated = LsapUpdatePrivilegeAssignments(0x10010u);
                          if ( updated >= 0 )
                          {
                            updated = LsapUpdatePrivilegeAssignments(0x10011u);
                            if ( updated >= 0 )
                            {
                              updated = LsapUpdatePrivilegeAssignments(0x10013u);
                              if ( updated >= 0 )
                                updated = LsapUpdatePrivilegeAssignments(0x10014u);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_40:
  RtlFreeSid(v12);
  RtlFreeSid(v13);
  RtlFreeSid(Sid);
  RtlFreeSid(v11);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1801207a0  push    rbp
0x1801207a2  push    rbx
0x1801207a3  push    rsi
0x1801207a4  push    rdi
0x1801207a5  push    r12
0x1801207a7  push    r13
0x1801207a9  push    r14
0x1801207ab  push    r15
0x1801207ad  lea     rbp, [rsp-178h]
0x1801207b5  sub     rsp, 278h
0x1801207bc  mov     rax, cs:__security_cookie
0x1801207c3  xor     rax, rsp
0x1801207c6  mov     [rbp+1B0h+var_50], rax
0x1801207cd  xor     esi, esi
0x1801207cf  mov     word ptr [rbp+1B0h+IdentifierAuthority.Value+4], 100h
0x1801207d5  mov     dword ptr [rbp+1B0h+IdentifierAuthority.Value], esi
0x1801207d8  mov     ecx, esi
0x1801207da  mov     dword ptr [rbp+1B0h+var_230.Value], esi
0x1801207dd  mov     word ptr [rbp+1B0h+var_230.Value+4], 500h
0x1801207e3  lea     r14d, [rsi+1]
0x1801207e7  mov     [rsp+2B0h+var_238], rsi
0x1801207ec  mov     [rsp+2B0h+var_250], rsi
0x1801207f1  mov     [rsp+2B0h+var_240], rsi
0x1801207f6  mov     [rsp+2B0h+var_248], rsi
0x1801207fb  mov     [rbp+1B0h+var_21C], esi
0x1801207fe  lea     rax, [rcx+rcx*2]
0x180120802  add     rcx, r14
0x180120805  mov     [rbp+rax*4+1B0h+var_210], esi
0x180120809  cmp     rcx, 24h ; '$'
0x18012080d  jnz     short loc_1801207FE
0x18012080f  lea     rax, [rsp+2B0h+var_238]
0x180120814  xor     r9d, r9d; SubAuthority1
0x180120817  mov     [rsp+2B0h+Sid], rax; Sid
0x18012081c  lea     rcx, [rbp+1B0h+IdentifierAuthority]; IdentifierAuthority
0x180120820  mov     [rsp+2B0h+SubAuthority7], esi; SubAuthority7
0x180120824  xor     r8d, r8d; SubAuthority0
0x180120827  mov     [rsp+2B0h+SubAuthority6], esi; SubAuthority6
0x18012082b  mov     dl, r14b; SubAuthorityCount
0x18012082e  mov     [rsp+2B0h+SubAuthority5], esi; SubAuthority5
0x180120832  mov     [rsp+2B0h+SubAuthority4], esi; SubAuthority4
0x180120836  mov     [rsp+2B0h+SubAuthority3], esi; SubAuthority3
0x18012083a  mov     [rsp+2B0h+SubAuthority2], esi; SubAuthority2
0x18012083e  call    cs:__imp_RtlAllocateAndInitializeSid
0x180120845  nop     dword ptr [rax+rax+00h]
0x18012084a  mov     edi, 2
0x18012084f  mov     ebx, eax
0x180120851  lea     r15d, [rdi+1]
0x180120855  test    eax, eax
0x180120857  js      loc_180120B01
0x18012085d  lea     rax, [rsp+2B0h+var_250]
0x180120862  mov     r9d, 220h; SubAuthority1
0x180120868  mov     [rsp+2B0h+Sid], rax; Sid
0x18012086d  lea     r8d, [rdi+1Eh]; SubAuthority0
0x180120871  mov     [rsp+2B0h+SubAuthority7], esi; SubAuthority7
0x180120875  lea     rcx, [rbp+1B0h+var_230]; IdentifierAuthority
0x180120879  mov     [rsp+2B0h+SubAuthority6], esi; SubAuthority6
0x18012087d  mov     dl, dil; SubAuthorityCount
0x180120880  mov     [rsp+2B0h+SubAuthority5], esi; SubAuthority5
0x180120884  mov     [rsp+2B0h+SubAuthority4], esi; SubAuthority4
0x180120888  mov     [rsp+2B0h+SubAuthority3], esi; SubAuthority3
0x18012088c  mov     [rsp+2B0h+SubAuthority2], esi; SubAuthority2
0x180120890  call    cs:__imp_RtlAllocateAndInitializeSid
0x180120897  nop     dword ptr [rax+rax+00h]
0x18012089c  mov     ebx, eax
0x18012089e  test    eax, eax
0x1801208a0  js      loc_180120B01
0x1801208a6  lea     rax, [rsp+2B0h+var_240]
0x1801208ab  xor     r9d, r9d; SubAuthority1
0x1801208ae  mov     [rsp+2B0h+Sid], rax; Sid
0x1801208b3  lea     r8d, [rdi+58h]; SubAuthority0
0x1801208b7  mov     [rsp+2B0h+SubAuthority7], esi; SubAuthority7
0x1801208bb  lea     rcx, [rbp+1B0h+var_230]; IdentifierAuthority
0x1801208bf  mov     [rsp+2B0h+SubAuthority6], esi; SubAuthority6
0x1801208c3  mov     dl, dil; SubAuthorityCount
0x1801208c6  mov     [rsp+2B0h+SubAuthority5], esi; SubAuthority5
0x1801208ca  mov     [rsp+2B0h+SubAuthority4], esi; SubAuthority4
0x1801208ce  mov     [rsp+2B0h+SubAuthority3], esi; SubAuthority3
0x1801208d2  mov     [rsp+2B0h+SubAuthority2], esi; SubAuthority2
0x1801208d6  call    cs:__imp_RtlAllocateAndInitializeSid
0x1801208dd  nop     dword ptr [rax+rax+00h]
0x1801208e2  mov     ebx, eax
0x1801208e4  test    eax, eax
0x1801208e6  js      loc_180120B01
0x1801208ec  lea     rax, [rsp+2B0h+var_248]
0x1801208f1  xor     r9d, r9d; SubAuthority1
0x1801208f4  mov     [rsp+2B0h+Sid], rax; Sid
0x1801208f9  lea     r8d, [rdi+61h]; SubAuthority0
0x1801208fd  mov     [rsp+2B0h+SubAuthority7], esi; SubAuthority7
0x180120901  lea     rcx, [rbp+1B0h+var_230]; IdentifierAuthority
0x180120905  mov     [rsp+2B0h+SubAuthority6], esi; SubAuthority6
0x180120909  mov     dl, dil; SubAuthorityCount
0x18012090c  mov     [rsp+2B0h+SubAuthority5], esi; SubAuthority5
0x180120910  mov     [rsp+2B0h+SubAuthority4], esi; SubAuthority4
0x180120914  mov     [rsp+2B0h+SubAuthority3], esi; SubAuthority3
0x180120918  mov     [rsp+2B0h+SubAuthority2], esi; SubAuthority2
0x18012091c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180120923  nop     dword ptr [rax+rax+00h]
0x180120928  mov     ebx, eax
0x18012092a  test    eax, eax
0x18012092c  js      loc_180120B01
0x180120932  cmp     cs:LsapProductType, r14d
0x180120939  mov     r8d, edi
0x18012093c  mov     [rbp+1B0h+var_218], 17h
0x180120944  mov     [rbp+1B0h+var_210], r15d
0x180120948  mov     [rbp+1B0h+var_220], r14d
0x18012094c  jnz     short loc_180120963
0x18012094e  mov     r8d, 403h; unsigned int
0x180120954  mov     [rbp+1B0h+var_20C], 13h
0x18012095c  mov     [rbp+1B0h+var_204], r15d
0x180120960  mov     [rbp+1B0h+var_220], edi
0x180120963  mov     rcx, [rsp+2B0h+var_238]; Sid
0x180120968  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x18012096c  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120971  mov     ebx, eax
0x180120973  mov     [rbp+1B0h+var_210], esi
0x180120976  cmp     [rbp+1B0h+var_220], edi
0x180120979  jnz     short loc_18012097E
0x18012097b  mov     [rbp+1B0h+var_204], esi
0x18012097e  test    eax, eax
0x180120980  js      loc_180120B01
0x180120986  mov     rcx, [rsp+2B0h+var_250]; Sid
0x18012098b  mov     eax, 18h
0x180120990  mov     edx, r14d; SubAuthority
0x180120993  mov     [rbp+1B0h+var_1DC], rax
0x180120997  mov     [rbp+1B0h+var_220], eax
0x18012099a  mov     [rbp+1B0h+var_218], 8
0x1801209a2  mov     [rbp+1B0h+var_20C], 11h
0x1801209aa  mov     [rbp+1B0h+var_200], 12h
0x1801209b2  mov     [rbp+1B0h+var_1F4], 0Ch
0x1801209ba  mov     [rbp+1B0h+var_1E8], 13h
0x1801209c2  mov     [rbp+1B0h+var_1D0], 9
0x1801209ca  mov     [rbp+1B0h+var_1C4], 14h
0x1801209d2  mov     [rbp+1B0h+var_1B8], 16h
0x1801209da  mov     [rbp+1B0h+var_1AC], 0Bh
0x1801209e2  mov     [rbp+1B0h+var_1A0], 0Dh
0x1801209ea  mov     [rbp+1B0h+var_194], 0Eh
0x1801209f2  mov     [rbp+1B0h+var_188], 0Ah
0x1801209fa  mov     [rbp+1B0h+var_17C], 0Fh
0x180120a02  mov     [rbp+1B0h+var_170], 5
0x180120a0a  mov     [rbp+1B0h+var_164], 19h
0x180120a12  mov     [rbp+1B0h+var_158], 1Ch
0x180120a1a  mov     [rbp+1B0h+var_14C], 1Dh
0x180120a22  mov     [rbp+1B0h+var_140], 1Eh
0x180120a2a  mov     [rbp+1B0h+var_134], 21h ; '!'
0x180120a32  mov     [rbp+1B0h+var_128], 22h ; '"'
0x180120a3d  mov     [rbp+1B0h+var_11C], 23h ; '#'
0x180120a48  mov     [rbp+1B0h+var_110], 17h
0x180120a53  mov     [rbp+1B0h+var_104], 24h ; '$'
0x180120a5e  call    cs:__imp_RtlSubAuthoritySid
0x180120a65  nop     dword ptr [rax+rax+00h]
0x180120a6a  mov     r8d, 7; unsigned int
0x180120a70  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120a74  mov     dword ptr [rax], 220h
0x180120a7a  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120a7f  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120a84  mov     ebx, eax
0x180120a86  test    eax, eax
0x180120a88  jns     short loc_180120AB8
0x180120a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180120a91  test    [rcx+6Ch], r14b
0x180120a95  jz      loc_180120E31
0x180120a9b  mov     rcx, [rcx+60h]
0x180120a9f  lea     r8, WPP_cbb2005f17923cdf8e072379aa1bb2c9_Traceguids
0x180120aa6  mov     edx, 0Ah
0x180120aab  mov     r9d, eax
0x180120aae  call    WPP_SF_d
0x180120ab3  jmp     loc_180120E31
0x180120ab8  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120abd  mov     edx, r14d; SubAuthority
0x180120ac0  mov     [rbp+1B0h+var_218], 11h
0x180120ac8  mov     [rbp+1B0h+var_20C], 12h
0x180120ad0  mov     [rbp+1B0h+var_200], 13h
0x180120ad8  mov     [rbp+1B0h+var_220], r15d
0x180120adc  call    cs:__imp_RtlSubAuthoritySid
0x180120ae3  nop     dword ptr [rax+rax+00h]
0x180120ae8  mov     r8d, r14d; unsigned int
0x180120aeb  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120aef  mov     dword ptr [rax], 227h
0x180120af5  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120afa  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120aff  mov     ebx, eax
0x180120b01  test    ebx, ebx
0x180120b03  js      loc_180120E31
0x180120b09  mov     eax, cs:LsapProductType
0x180120b0f  cmp     eax, edi
0x180120b11  jnz     loc_180120BEA
0x180120b17  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120b1c  mov     edx, r14d; SubAuthority
0x180120b1f  mov     [rbp+1B0h+var_218], 11h
0x180120b27  mov     [rbp+1B0h+var_20C], 12h
0x180120b2f  mov     [rbp+1B0h+var_200], 0Ch
0x180120b37  mov     [rbp+1B0h+var_1F4], 13h
0x180120b3f  mov     [rbp+1B0h+var_1E8], 18h
0x180120b47  mov     [rbp+1B0h+var_220], 5
0x180120b4e  call    cs:__imp_RtlSubAuthoritySid
0x180120b55  nop     dword ptr [rax+rax+00h]
0x180120b5a  mov     r8d, r14d; unsigned int
0x180120b5d  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120b61  mov     dword ptr [rax], 225h
0x180120b67  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120b6c  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120b71  mov     ebx, eax
0x180120b73  test    eax, eax
0x180120b75  js      loc_180120E31
0x180120b7b  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120b80  mov     edx, r14d; SubAuthority
0x180120b83  mov     [rbp+1B0h+var_218], 13h
0x180120b8b  mov     [rbp+1B0h+var_220], r14d
0x180120b8f  call    cs:__imp_RtlSubAuthoritySid
0x180120b96  nop     dword ptr [rax+rax+00h]
0x180120b9b  mov     r8d, r14d; unsigned int
0x180120b9e  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120ba2  mov     dword ptr [rax], 224h
0x180120ba8  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120bad  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120bb2  mov     ebx, eax
0x180120bb4  test    eax, eax
0x180120bb6  js      loc_180120E31
0x180120bbc  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120bc1  mov     edx, r14d; SubAuthority
0x180120bc4  mov     [rbp+1B0h+var_218], 13h
0x180120bcc  mov     [rbp+1B0h+var_220], r14d
0x180120bd0  call    cs:__imp_RtlSubAuthoritySid
0x180120bd7  nop     dword ptr [rax+rax+00h]
0x180120bdc  mov     r8d, r14d
0x180120bdf  mov     dword ptr [rax], 226h
0x180120be5  jmp     loc_180120D45
0x180120bea  mov     [rbp+1B0h+var_218], 17h
0x180120bf2  mov     [rbp+1B0h+var_20C], 21h ; '!'
0x180120bfa  cmp     eax, r14d
0x180120bfd  jnz     short loc_180120C0A
0x180120bff  mov     [rbp+1B0h+var_200], 13h
0x180120c07  mov     edi, r15d
0x180120c0a  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120c0f  mov     edx, r14d; SubAuthority
0x180120c12  mov     [rbp+1B0h+var_220], edi
0x180120c15  call    cs:__imp_RtlSubAuthoritySid
0x180120c1c  nop     dword ptr [rax+rax+00h]
0x180120c21  mov     r8d, r15d; unsigned int
0x180120c24  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120c28  mov     dword ptr [rax], 221h
0x180120c2e  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120c33  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120c38  mov     ebx, eax
0x180120c3a  test    eax, eax
0x180120c3c  js      loc_180120E31
0x180120c42  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120c47  mov     edx, r14d; SubAuthority
0x180120c4a  mov     [rbp+1B0h+var_218], 17h
0x180120c52  mov     [rbp+1B0h+var_20C], 21h ; '!'
0x180120c5a  mov     [rbp+1B0h+var_200], 22h ; '"'
0x180120c62  mov     [rbp+1B0h+var_220], r15d
0x180120c66  call    cs:__imp_RtlSubAuthoritySid
0x180120c6d  nop     dword ptr [rax+rax+00h]
0x180120c72  mov     r8d, r15d; unsigned int
0x180120c75  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120c79  mov     dword ptr [rax], 245h
0x180120c7f  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120c84  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120c89  mov     ebx, eax
0x180120c8b  test    eax, eax
0x180120c8d  js      loc_180120E31
0x180120c93  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120c98  mov     edx, r14d; SubAuthority
0x180120c9b  mov     [rbp+1B0h+var_220], esi
0x180120c9e  call    cs:__imp_RtlSubAuthoritySid
0x180120ca5  nop     dword ptr [rax+rax+00h]
0x180120caa  mov     r8d, r14d; unsigned int
0x180120cad  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120cb1  mov     dword ptr [rax], 222h
0x180120cb7  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120cbc  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120cc1  mov     ebx, eax
0x180120cc3  test    eax, eax
0x180120cc5  js      loc_180120E31
0x180120ccb  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120cd0  mov     edx, r14d; SubAuthority
0x180120cd3  mov     [rbp+1B0h+var_218], 17h
0x180120cdb  mov     [rbp+1B0h+var_20C], 21h ; '!'
0x180120ce3  mov     [rbp+1B0h+var_200], 22h ; '"'
0x180120ceb  mov     [rbp+1B0h+var_220], r15d
0x180120cef  call    cs:__imp_RtlSubAuthoritySid
0x180120cf6  nop     dword ptr [rax+rax+00h]
0x180120cfb  mov     r8d, r15d; unsigned int
0x180120cfe  lea     rdx, [rbp+1B0h+var_220]; struct _LSAPR_PRIVILEGE_SET *
0x180120d02  mov     dword ptr [rax], 247h
0x180120d08  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120d0d  call    ?LsapDbInitializeAccount@@YAJPEAXPEAU_LSAPR_PRIVILEGE_SET@@K@Z; LsapDbInitializeAccount(void *,_LSAPR_PRIVILEGE_SET *,ulong)
0x180120d12  mov     ebx, eax
0x180120d14  test    eax, eax
0x180120d16  js      loc_180120E31
0x180120d1c  mov     rcx, [rsp+2B0h+var_250]; Sid
0x180120d21  mov     edx, r14d; SubAuthority
0x180120d24  mov     [rbp+1B0h+var_218], 17h
0x180120d2c  mov     [rbp+1B0h+var_220], r14d
0x180120d30  call    cs:__imp_RtlSubAuthoritySid
0x180120d37  nop     dword ptr [rax+rax+00h]
0x180120d3c  xor     r8d, r8d; unsigned int
0x180120d3f  mov     dword ptr [rax], 248h
0x180120d45  mov     rcx, [rsp+2B0h+var_250]; Sid
  ... truncated ...
```
