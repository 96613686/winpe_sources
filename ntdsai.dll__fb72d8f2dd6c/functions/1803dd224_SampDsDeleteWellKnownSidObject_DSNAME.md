# SampDsDeleteWellKnownSidObject(_DSNAME *)

- ea: `0x1803dd224`
- end: `0x1803dd4f0`
- name: `?SampDsDeleteWellKnownSidObject@@YAJPEAU_DSNAME@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(struct _DSNAME *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803ddd84`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180032114`
- `0x180052780`
- `0x180074594`
- `0x18015456c`
- `0x180166f10`
- `0x1803b0860`
- `0x1803dd224`
- `0x1803debcc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x1803dd49c`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x1803dd49c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1803dd3ce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1803dd3ce`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1803dd2da`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1803dd2da`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1803dd32e`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1803dd32e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803dd36c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803dd37d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803dd3a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803dd36c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803dd37d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803dd3a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803dd31c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803dd358`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803dd38f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803dd31c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803dd358`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803dd38f`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1803dd341`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1803dd341`
- `ntdll!RtlLengthSid` at `0x1803dd2f9`
- `ntdll!RtlLengthSid` at `0x1803dd2f9`

## pseudocode

```c
__int64 __fastcall SampDsDeleteWellKnownSidObject(struct _DSNAME *a1)
{
  int v2; // ebx
  ULONG v3; // eax
  BYTE v4; // bl
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // rax
  unsigned int i; // edi
  DWORD v7; // ebx
  PDWORD SidSubAuthority; // rax
  DWORD LengthSid; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rcx
  BOOL pfEqual; // [rsp+20h] [rbp-E0h] BYREF
  DWORD cbDomainSid; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h]
  __int128 v21; // [rsp+58h] [rbp-A8h]
  struct _DSNAME *v22; // [rsp+70h] [rbp-90h] BYREF
  __int16 v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+80h] [rbp-80h]
  __int16 v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+90h] [rbp-70h]
  int v27; // [rsp+94h] [rbp-6Ch]
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  __int128 *v30; // [rsp+A0h] [rbp-60h]
  _BYTE v31[224]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v32[4]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v33[192]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE pSid[68]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE Sid[68]; // [rsp+2B4h] [rbp+1B4h] BYREF

  memset_0(&v22, 0, 0x118u);
  v17 = 0;
  memset_0(v32, 0, 0xE0u);
  v18 = 0;
  cbDomainSid = 0;
  pfEqual = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v2 = SampDoImplicitTransactionStart(1);
  if ( v2 )
    goto LABEL_15;
  cbDomainSid = 68;
  if ( !EqualDomainSid(SampBuiltinDomainSid, (char *)a1 + 24, &pfEqual) || pfEqual == v2 )
  {
    if ( !GetWindowsAccountDomainSid((char *)a1 + 24, pSid, &cbDomainSid) )
      goto LABEL_13;
  }
  else
  {
    v3 = RtlLengthSid(SampBuiltinDomainSid);
    memcpy_0(pSid, SampBuiltinDomainSid, v3);
  }
  v4 = *GetSidSubAuthorityCount(pSid) + 1;
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( !InitializeSid(Sid, SidIdentifierAuthority, v4) )
  {
LABEL_13:
    v2 = -1073741801;
    goto LABEL_15;
  }
  for ( i = 0; i < *GetSidSubAuthorityCount(pSid); *SidSubAuthority = v7 )
  {
    v7 = *GetSidSubAuthority(pSid, i);
    SidSubAuthority = GetSidSubAuthority(Sid, i++);
  }
  *GetSidSubAuthority(Sid, i) = 0;
  v25 = 67;
  v22 = a1;
  v24 = 0;
  LengthSid = GetLengthSid(Sid);
  v26 = 589970;
  LODWORD(v19) = LengthSid;
  *((_QWORD *)&v19 + 1) = Sid;
  v27 = DWORD1(v21);
  v29 = DWORD1(v20);
  v30 = &v19;
  v28 = 1;
  v23 = 1;
  BuildStdCommArg(v31);
  LOBYTE(v10) = 1;
  SampSetDsa(v10);
  v11 = DirModifyEntry(&v22, &v17);
  if ( !v17 )
  {
LABEL_11:
    v2 = -1073741670;
    goto LABEL_15;
  }
  v2 = SampMapDsErrorToNTStatus(v11, v17);
  if ( v2 >= 0 )
  {
    memset_0(v32, 0, 0xE0u);
    BuildStdCommArg(v33);
    v32[0] = a1;
    v12 = DirRemoveEntryNative(v32, &v18);
    if ( v18 )
    {
      v2 = SampMapDsErrorToNTStatus(v12, v18);
      goto LABEL_15;
    }
    goto LABEL_11;
  }
LABEL_15:
  THClearErrors();
  LOBYTE(v13) = 1;
  SampSetDsa(v13);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1803dd224  mov     [rsp-8+arg_8], rbx
0x1803dd229  mov     [rsp-8+arg_10], rsi
0x1803dd22e  push    rbp
0x1803dd22f  push    rdi
0x1803dd230  push    r15
0x1803dd232  lea     rbp, [rsp-200h]
0x1803dd23a  sub     rsp, 300h
0x1803dd241  mov     rax, cs:__security_cookie
0x1803dd248  xor     rax, rsp
0x1803dd24b  mov     [rbp+210h+var_18], rax
0x1803dd252  mov     rsi, rcx
0x1803dd255  xor     edx, edx; Val
0x1803dd257  lea     rcx, [rsp+310h+var_2A0]; void *
0x1803dd25c  mov     r8d, 118h; Size
0x1803dd262  call    memset_0
0x1803dd267  xor     edx, edx; Val
0x1803dd269  mov     [rsp+310h+var_2E8], 0
0x1803dd272  mov     r8d, 0E0h; Size
0x1803dd278  lea     rcx, [rbp+210h+var_180]; void *
0x1803dd27f  call    memset_0
0x1803dd284  xor     eax, eax
0x1803dd286  mov     [rsp+310h+var_2E0], 0
0x1803dd28f  xorps   xmm0, xmm0
0x1803dd292  mov     [rsp+310h+cbDomainSid], eax
0x1803dd296  xorps   xmm1, xmm1
0x1803dd299  mov     [rsp+310h+pfEqual], eax
0x1803dd29d  movups  [rsp+310h+var_2B8], xmm0
0x1803dd2a2  lea     r15d, [rax+1]
0x1803dd2a6  mov     ecx, r15d
0x1803dd2a9  movups  [rsp+310h+var_2D8], xmm0
0x1803dd2ae  movups  [rsp+310h+var_2C8], xmm1
0x1803dd2b3  call    SampDoImplicitTransactionStart
0x1803dd2b8  mov     ebx, eax
0x1803dd2ba  test    eax, eax
0x1803dd2bc  jnz     loc_1803DD4BA
0x1803dd2c2  mov     rcx, cs:SampBuiltinDomainSid; pSid1
0x1803dd2c9  lea     r8, [rsp+310h+pfEqual]; pfEqual
0x1803dd2ce  lea     rdx, [rsi+18h]; pSid2
0x1803dd2d2  mov     [rsp+310h+cbDomainSid], 44h ; 'D'
0x1803dd2da  call    cs:__imp_EqualDomainSid
0x1803dd2e0  test    eax, eax
0x1803dd2e2  jz      loc_1803DD48C
0x1803dd2e8  cmp     [rsp+310h+pfEqual], ebx
0x1803dd2ec  jz      loc_1803DD48C
0x1803dd2f2  mov     rcx, cs:SampBuiltinDomainSid; Sid
0x1803dd2f9  call    cs:__imp_RtlLengthSid
0x1803dd2ff  mov     rdx, cs:SampBuiltinDomainSid; Src
0x1803dd306  lea     rcx, [rbp+210h+pSid]; void *
0x1803dd30d  mov     r8d, eax; Size
0x1803dd310  call    memcpy_0
0x1803dd315  lea     rcx, [rbp+210h+pSid]; pSid
0x1803dd31c  call    cs:__imp_GetSidSubAuthorityCount
0x1803dd322  lea     rcx, [rbp+210h+pSid]; pSid
0x1803dd329  mov     bl, [rax]
0x1803dd32b  add     bl, r15b
0x1803dd32e  call    cs:__imp_GetSidIdentifierAuthority
0x1803dd334  mov     r8b, bl; nSubAuthorityCount
0x1803dd337  lea     rcx, [rbp+210h+Sid]; Sid
0x1803dd33e  mov     rdx, rax; pIdentifierAuthority
0x1803dd341  call    cs:__imp_InitializeSid
0x1803dd347  test    eax, eax
0x1803dd349  jz      loc_1803DD4AA
0x1803dd34f  lea     rcx, [rbp+210h+pSid]; pSid
0x1803dd356  xor     edi, edi
0x1803dd358  call    cs:__imp_GetSidSubAuthorityCount
0x1803dd35e  cmp     [rax], dil
0x1803dd361  jbe     short loc_1803DD39C
0x1803dd363  mov     edx, edi; nSubAuthority
0x1803dd365  lea     rcx, [rbp+210h+pSid]; pSid
0x1803dd36c  call    cs:__imp_GetSidSubAuthority
0x1803dd372  mov     edx, edi; nSubAuthority
0x1803dd374  lea     rcx, [rbp+210h+Sid]; pSid
0x1803dd37b  mov     ebx, [rax]
0x1803dd37d  call    cs:__imp_GetSidSubAuthority
0x1803dd383  lea     rcx, [rbp+210h+pSid]; pSid
0x1803dd38a  add     edi, r15d
0x1803dd38d  mov     [rax], ebx
0x1803dd38f  call    cs:__imp_GetSidSubAuthorityCount
0x1803dd395  movzx   ecx, byte ptr [rax]
0x1803dd398  cmp     edi, ecx
0x1803dd39a  jb      short loc_1803DD363
0x1803dd39c  mov     edx, edi; nSubAuthority
0x1803dd39e  lea     rcx, [rbp+210h+Sid]; pSid
0x1803dd3a5  call    cs:__imp_GetSidSubAuthority
0x1803dd3ab  lea     rcx, [rbp+210h+Sid]; pSid
0x1803dd3b2  mov     dword ptr [rax], 0
0x1803dd3b8  mov     eax, 43h ; 'C'
0x1803dd3bd  mov     [rbp+210h+var_288], ax
0x1803dd3c1  mov     [rsp+310h+var_2A0], rsi
0x1803dd3c6  mov     [rbp+210h+var_290], 0
0x1803dd3ce  call    cs:__imp_GetLengthSid
0x1803dd3d4  lea     rcx, [rbp+210h+var_260]
0x1803dd3d8  mov     [rbp+210h+var_280], 90092h
0x1803dd3df  mov     dword ptr [rsp+310h+var_2D8], eax
0x1803dd3e3  lea     rax, [rbp+210h+Sid]
0x1803dd3ea  mov     qword ptr [rsp+310h+var_2D8+8], rax
0x1803dd3ef  mov     eax, dword ptr [rsp+310h+var_2B8+4]
0x1803dd3f3  mov     [rbp+210h+var_27C], eax
0x1803dd3f6  mov     eax, dword ptr [rsp+310h+var_2C8+4]
0x1803dd3fa  mov     [rbp+210h+var_274], eax
0x1803dd3fd  lea     rax, [rsp+310h+var_2D8]
0x1803dd402  mov     [rbp+210h+var_270], rax
0x1803dd406  mov     [rbp+210h+var_278], r15d
0x1803dd40a  mov     [rsp+310h+var_298], r15w
0x1803dd410  call    BuildStdCommArg
0x1803dd415  mov     cl, r15b
0x1803dd418  call    SampSetDsa
0x1803dd41d  lea     rdx, [rsp+310h+var_2E8]
0x1803dd422  lea     rcx, [rsp+310h+var_2A0]
0x1803dd427  call    DirModifyEntry
0x1803dd42c  mov     rdx, [rsp+310h+var_2E8]
0x1803dd431  test    rdx, rdx
0x1803dd434  jz      short loc_1803DD485
0x1803dd436  mov     ecx, eax
0x1803dd438  call    SampMapDsErrorToNTStatus
0x1803dd43d  mov     ebx, eax
0x1803dd43f  test    eax, eax
0x1803dd441  js      short loc_1803DD4BA
0x1803dd443  xor     edx, edx; Val
0x1803dd445  lea     rcx, [rbp+210h+var_180]; void *
0x1803dd44c  mov     r8d, 0E0h; Size
0x1803dd452  call    memset_0
0x1803dd457  lea     rcx, [rbp+210h+var_160]
0x1803dd45e  call    BuildStdCommArg
0x1803dd463  lea     rdx, [rsp+310h+var_2E0]
0x1803dd468  mov     [rbp+210h+var_180], rsi
0x1803dd46f  lea     rcx, [rbp+210h+var_180]
0x1803dd476  call    DirRemoveEntryNative
0x1803dd47b  mov     rdx, [rsp+310h+var_2E0]
0x1803dd480  test    rdx, rdx
0x1803dd483  jnz     short loc_1803DD4B1
0x1803dd485  mov     ebx, 0C000009Ah
0x1803dd48a  jmp     short loc_1803DD4BA
0x1803dd48c  lea     r8, [rsp+310h+cbDomainSid]; cbDomainSid
0x1803dd491  lea     rdx, [rbp+210h+pSid]; pDomainSid
0x1803dd498  lea     rcx, [rsi+18h]; pSid
0x1803dd49c  call    cs:__imp_GetWindowsAccountDomainSid
0x1803dd4a2  test    eax, eax
0x1803dd4a4  jnz     loc_1803DD315
0x1803dd4aa  mov     ebx, 0C0000017h
0x1803dd4af  jmp     short loc_1803DD4BA
0x1803dd4b1  mov     ecx, eax
0x1803dd4b3  call    SampMapDsErrorToNTStatus
0x1803dd4b8  mov     ebx, eax
0x1803dd4ba  call    THClearErrors
0x1803dd4bf  mov     cl, r15b
0x1803dd4c2  call    SampSetDsa
0x1803dd4c7  mov     eax, ebx
0x1803dd4c9  mov     rcx, [rbp+210h+var_18]
0x1803dd4d0  xor     rcx, rsp; StackCookie
0x1803dd4d3  call    __security_check_cookie
0x1803dd4d8  lea     r11, [rsp+310h+var_10]
0x1803dd4e0  mov     rbx, [r11+28h]
0x1803dd4e4  mov     rsi, [r11+30h]
0x1803dd4e8  mov     rsp, r11
0x1803dd4eb  pop     r15
0x1803dd4ed  pop     rdi
0x1803dd4ee  pop     rbp
0x1803dd4ef  retn
```
