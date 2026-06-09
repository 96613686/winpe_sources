# LsaIAuditLogonUsingExplicitCreds

- ea: `0x180079830`
- end: `0x180079d72`
- name: `LsaIAuditLogonUsingExplicitCreds`
- size: `1346`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008d590`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x18000c300`
- `0x180078d7c`
- `0x180079830`
- `0x180079d78`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc040`
- `0x1800bc2c4`
- `0x1800ce940`

## import_xrefs

- `LSAADT!__imp_LsapAdtWriteLog` at `0x180079cee`
- `LSAADT!__imp_LsapAdtWriteLog` at `0x180079cee`
- `LSAADT!__imp_LsapAuditFailed` at `0x180079d38`
- `LSAADT!__imp_LsapAuditFailed` at `0x180079d38`
- `LSAADT!__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A` at `0x180079c9c`
- `LSAADT!__imp_?LsapIsLocalOrNetworkServiceOrIUser@@YAHPEAU_UNICODE_STRING@@0@Z` at `0x180079b16`
- `LSAADT!__imp_?LsapIsLocalOrNetworkServiceOrIUser@@YAHPEAU_UNICODE_STRING@@0@Z` at `0x180079b16`
- `LSAADT!__imp_?LsapIsAnonymous@@YAHPEAU_UNICODE_STRING@@0@Z` at `0x180079b8d`
- `LSAADT!__imp_?LsapIsAnonymous@@YAHPEAU_UNICODE_STRING@@0@Z` at `0x180079b8d`
- `LSAADT!__imp_?LsapIsLocalSystem@@YAJPEAU_UNICODE_STRING@@0@Z` at `0x180079afd`
- `LSAADT!__imp_?LsapIsLocalSystem@@YAJPEAU_UNICODE_STRING@@0@Z` at `0x180079afd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079935`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079935`
- `ntdll!RtlEqualUnicodeString` at `0x180079a5a`
- `ntdll!RtlEqualUnicodeString` at `0x180079a7a`
- `ntdll!RtlEqualUnicodeString` at `0x180079a5a`
- `ntdll!RtlEqualUnicodeString` at `0x180079a7a`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180079979`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180079979`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180079cd8`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180079cd8`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapGetImageNameFromProcessId` at `0x180079bac`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapGetImageNameFromProcessId` at `0x180079bac`

## pseudocode

```c
__int64 __fastcall LsaIAuditLogonUsingExplicitCreds(
        unsigned __int16 a1,
        struct _LUID *a2,
        unsigned __int64 *a3,
        __int64 a4,
        UNICODE_STRING *a5,
        UNICODE_STRING *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  struct _RTL_BALANCED_NODE *v11; // rdx
  int v12; // r9d
  int v13; // ebx
  char *Value; // rax
  __int64 v15; // rcx
  __int128 *v16; // r13
  char v17; // al
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  PWSTR Buffer; // rcx
  __int64 v22; // rdx
  UNICODE_STRING *p_String1; // rsi
  PWSTR v24; // rcx
  __int64 v25; // rdx
  UNICODE_STRING *v26; // rbx
  struct _LSAP_LOGON_SESSION *LogonSession; // rax
  struct _LSAP_LOGON_SESSION *v28; // rdi
  __int64 v29; // r15
  __int64 v30; // r8
  unsigned __int64 v31; // xmm6_8
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  char v38[2]; // [rsp+F8h] [rbp-80h] BYREF
  unsigned __int16 v39; // [rsp+FAh] [rbp-7Eh]
  struct _RTL_BALANCED_NODE *v40; // [rsp+100h] [rbp-78h] BYREF
  __int64 v41; // [rsp+108h] [rbp-70h]
  UNICODE_STRING String1; // [rsp+110h] [rbp-68h] BYREF
  UNICODE_STRING v43; // [rsp+120h] [rbp-58h] BYREF
  __int64 v44; // [rsp+130h] [rbp-48h]
  __int64 v45; // [rsp+138h] [rbp-40h]
  __int64 v46; // [rsp+140h] [rbp-38h]
  __int128 v47; // [rsp+148h] [rbp-30h] BYREF
  _BYTE v48[1056]; // [rsp+158h] [rbp-20h] BYREF
  _BYTE v49[544]; // [rsp+578h] [rbp+400h] BYREF

  v39 = a1;
  v46 = a7;
  v45 = a8;
  v44 = a9;
  v41 = a4;
  memset_0(v48, 0, 0x418u);
  v38[0] = 0;
  String1 = 0;
  v43 = 0;
  v47 = 0;
  memset_0(v49, 0, 0x21Au);
  v40 = (struct _RTL_BALANCED_NODE *)v49;
  if ( !(unsigned __int8)AdtpIsCorrectlyFormedUnicodeString(a5)
    || !(unsigned __int8)AdtpIsCorrectlyFormedUnicodeString(a6)
    || !(unsigned __int8)AdtpIsCorrectlyFormedUnicodeString(a8)
    || !(unsigned __int8)AdtpIsCorrectlyFormedUnicodeString(a9) )
  {
    v13 = -1073741811;
    goto LABEL_64;
  }
  v13 = v12;
  Value = (char *)TlsGetValue(dwCallInfo);
  if ( Value )
  {
    v16 = (__int128 *)(Value + 224);
  }
  else
  {
    v16 = &v47;
    LOWORD(v47) = 2;
  }
  v17 = IsLsapAdtInitializeCrashOnAuditFailPresent(v15);
  v19 = 0;
  if ( v17 )
  {
    v20 = LsapAdtAuditingEnabledByLogonId(105, a2, v39, v38);
    v19 = 0;
    v13 = v20;
    if ( v20 < 0 )
      goto LABEL_62;
  }
  if ( !v38[0] )
    goto LABEL_62;
  if ( a5 )
  {
    Buffer = a5->Buffer;
    v22 = WORD1(*(_QWORD *)&a5->Length);
    String1 = *a5;
    String1.Length = AdtpSafeWcslen(Buffer, v22, v18, 0);
  }
  p_String1 = &String1;
  if ( a6 )
  {
    v24 = a6->Buffer;
    v25 = WORD1(*(_QWORD *)&a6->Length);
    v43 = *a6;
    v43.Length = AdtpSafeWcslen(v24, v25, v18, v19);
  }
  v26 = &v43;
  LogonSession = LsapLocateLogonSession(a2);
  v28 = LogonSession;
  if ( LogonSession )
  {
    if ( !String1.Buffer && !v43.Buffer )
    {
      if ( *((_DWORD *)LogonSession + 58) != 9 )
        goto LABEL_39;
      p_String1 = (UNICODE_STRING *)((char *)LogonSession + 544);
      v26 = (UNICODE_STRING *)((char *)LogonSession + 560);
    }
    v29 = *((_QWORD *)LogonSession + 28);
    if ( !p_String1->Buffer )
      p_String1 = (UNICODE_STRING *)((char *)LogonSession + 160);
    if ( !v26->Buffer )
      v26 = (UNICODE_STRING *)((char *)LogonSession + 176);
    if ( !RtlEqualUnicodeString(p_String1, (PCUNICODE_STRING)LogonSession + 10, 1u)
      || !RtlEqualUnicodeString(v26, (PCUNICODE_STRING)v28 + 11, 1u) )
    {
      if ( !a3 )
        goto LABEL_40;
      v31 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v32 = *a3;
      if ( !*a3 )
        v32 = a3[1] - v31;
      if ( v32 )
      {
        v33 = *(_QWORD *)((char *)v28 + 516);
        if ( !v33 )
          v33 = *(_QWORD *)((char *)v28 + 524) - v31;
        if ( !v33 )
          LsaISetLogonGuidInLogonSession(a2, a3, v30, 0);
      }
      else
      {
LABEL_40:
        a3 = (unsigned __int64 *)((char *)v28 + 516);
      }
      goto LABEL_34;
    }
LABEL_39:
    v13 = 0;
LABEL_61:
    LsapReleaseLogonSession(v28);
    goto LABEL_62;
  }
  v29 = 0;
  if ( a2->LowPart == 998 )
  {
    if ( !a2->HighPart )
      v29 = *((_QWORD *)WellKnownSids + 108);
    goto LABEL_44;
  }
LABEL_34:
  if ( a2->LowPart == 999
    && !a2->HighPart
    && (LsapIsLocalSystem(p_String1, v26) || LsapIsLocalOrNetworkServiceOrIUser(p_String1, v26)) )
  {
LABEL_38:
    v13 = 0;
    goto LABEL_60;
  }
LABEL_44:
  if ( a2->LowPart == 998
    && !a2->HighPart
    && ((!p_String1 || !p_String1->Length) && (!v26 || !v26->Length) || LsapIsAnonymous(p_String1, v26)) )
  {
    goto LABEL_38;
  }
  if ( (int)LsapGetImageNameFromProcessId((unsigned int)v41, 538, &v40) < 0 || !LOWORD(v40->Children[0]) )
    v40 = 0;
  if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(0, v34, v35) )
  {
    if ( !v29 )
      v29 = *((_QWORD *)WellKnownSids + 90);
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _WORD, _WORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD))LsapAdtInitParametersArray)(
            v48,
            2,
            4648,
            105,
            v39,
            12,
            4,
            v29,
            1,
            *(_QWORD *)&LsapSubsystemName.Length,
            5,
            *a2,
            13,
            a3,
            1,
            p_String1,
            1,
            v26,
            13,
            v46,
            1,
            v45,
            1,
            v44,
            11,
            v41,
            1,
            v40,
            23,
            v16);
    if ( v13 >= 0 )
      LsapAdtWriteLog(v48, v36);
  }
  else
  {
    v13 = -1073741822;
  }
LABEL_60:
  if ( v28 )
    goto LABEL_61;
LABEL_62:
  v11 = v40;
LABEL_64:
  if ( v11 && v11 != (struct _RTL_BALANCED_NODE *)v49 )
    LsapSubProv_FreeRoutine(v11, v11);
  if ( v13 < 0 )
    LsapAuditFailed((unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180079830  mov     rax, rsp
0x180079833  push    rbp
0x180079834  push    rbx
0x180079835  push    rsi
0x180079836  push    rdi
0x180079837  push    r12
0x180079839  push    r13
0x18007983b  push    r14
0x18007983d  push    r15
0x18007983f  lea     rbp, [rax-688h]
0x180079846  sub     rsp, 7B8h
0x18007984d  movaps  xmmword ptr [rax-58h], xmm6
0x180079851  mov     rax, cs:__security_cookie
0x180079858  xor     rax, rsp
0x18007985b  mov     [rbp+680h+var_60], rax
0x180079862  mov     rax, [rbp+680h+arg_30]
0x180079869  mov     r12, r8
0x18007986c  mov     rbx, [rbp+680h+arg_38]
0x180079873  mov     r14, rdx
0x180079876  mov     r15, [rbp+680h+arg_40]
0x18007987d  xor     edx, edx; Val
0x18007987f  mov     rsi, [rbp+680h+arg_20]
0x180079886  mov     r8d, 418h; Size
0x18007988c  mov     rdi, [rbp+680h+arg_28]
0x180079893  mov     [rbp+680h+var_6FE], cx
0x180079897  lea     rcx, [rbp+680h+var_6A0]; void *
0x18007989b  mov     [rbp+680h+var_6B8], rax
0x18007989f  mov     [rbp+680h+var_6C0], rbx
0x1800798a3  mov     [rbp+680h+var_6C8], r15
0x1800798a7  mov     [rbp+680h+var_6F0], r9
0x1800798ab  call    memset_0
0x1800798b0  xor     ecx, ecx
0x1800798b2  xorps   xmm0, xmm0
0x1800798b5  mov     [rbp+680h+var_700], cl
0x1800798b8  xorps   xmm1, xmm1
0x1800798bb  lea     rcx, [rbp+680h+var_280]; void *
0x1800798c2  xor     edx, edx; Val
0x1800798c4  mov     r8d, 21Ah; Size
0x1800798ca  xorps   xmm6, xmm6
0x1800798cd  movups  xmmword ptr [rbp+680h+String1.Length], xmm0
0x1800798d1  movups  xmmword ptr [rbp+680h+var_6D8.Length], xmm1
0x1800798d5  movups  [rbp+680h+var_6B0], xmm0
0x1800798d9  call    memset_0
0x1800798de  lea     rdx, [rbp+680h+var_280]
0x1800798e5  mov     rcx, rsi
0x1800798e8  mov     [rbp+680h+var_6F8], rdx
0x1800798ec  call    AdtpIsCorrectlyFormedUnicodeString
0x1800798f1  xor     r9d, r9d
0x1800798f4  test    al, al
0x1800798f6  jz      loc_180079D14
0x1800798fc  mov     rcx, rdi
0x1800798ff  call    AdtpIsCorrectlyFormedUnicodeString
0x180079904  test    al, al
0x180079906  jz      loc_180079D14
0x18007990c  mov     rcx, rbx
0x18007990f  call    AdtpIsCorrectlyFormedUnicodeString
0x180079914  test    al, al
0x180079916  jz      loc_180079D14
0x18007991c  mov     rcx, r15
0x18007991f  call    AdtpIsCorrectlyFormedUnicodeString
0x180079924  test    al, al
0x180079926  jz      loc_180079D14
0x18007992c  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180079932  mov     ebx, r9d
0x180079935  call    cs:__imp_TlsGetValue
0x18007993c  nop     dword ptr [rax+rax+00h]
0x180079941  mov     edx, 2
0x180079946  test    rax, rax
0x180079949  jnz     short loc_180079955
0x18007994b  lea     r13, [rbp+680h+var_6B0]
0x18007994f  mov     word ptr [rbp+680h+var_6B0], dx
0x180079953  jmp     short loc_18007995C
0x180079955  lea     r13, [rax+0E0h]
0x18007995c  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x180079961  xor     r9d, r9d
0x180079964  test    al, al
0x180079966  jz      short loc_180079992
0x180079968  movzx   r8d, [rbp+680h+var_6FE]
0x18007996d  lea     r9, [rbp+680h+var_700]
0x180079971  mov     rdx, r14
0x180079974  mov     ecx, 69h ; 'i'
0x180079979  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180079980  nop     dword ptr [rax+rax+00h]
0x180079985  xor     r9d, r9d
0x180079988  mov     ebx, eax
0x18007998a  test    eax, eax
0x18007998c  js      loc_180079D0E
0x180079992  cmp     [rbp+680h+var_700], r9b
0x180079996  jz      loc_180079D0E
0x18007999c  test    rsi, rsi
0x18007999f  jz      short loc_1800799C1
0x1800799a1  movups  xmm0, xmmword ptr [rsi]
0x1800799a4  mov     rcx, [rsi+8]
0x1800799a8  movq    rax, xmm0
0x1800799ad  shr     rax, 10h
0x1800799b1  movzx   edx, ax
0x1800799b4  movups  xmmword ptr [rbp+680h+String1.Length], xmm0
0x1800799b8  call    AdtpSafeWcslen
0x1800799bd  mov     [rbp+680h+String1.Length], ax
0x1800799c1  lea     rsi, [rbp+680h+String1]
0x1800799c5  test    rdi, rdi
0x1800799c8  jz      short loc_1800799EA
0x1800799ca  movups  xmm0, xmmword ptr [rdi]
0x1800799cd  mov     rcx, [rdi+8]
0x1800799d1  movq    rax, xmm0
0x1800799d6  shr     rax, 10h
0x1800799da  movzx   edx, ax
0x1800799dd  movups  xmmword ptr [rbp+680h+var_6D8.Length], xmm0
0x1800799e1  call    AdtpSafeWcslen
0x1800799e6  mov     [rbp+680h+var_6D8.Length], ax
0x1800799ea  mov     rcx, r14; struct _LUID *
0x1800799ed  lea     rbx, [rbp+680h+var_6D8]
0x1800799f1  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800799f6  xor     r9d, r9d
0x1800799f9  mov     rdi, rax
0x1800799fc  test    rax, rax
0x1800799ff  jz      loc_180079B42
0x180079a05  cmp     [rbp+680h+String1.Buffer], r9
0x180079a09  jnz     short loc_180079A2C
0x180079a0b  cmp     [rbp+680h+var_6D8.Buffer], r9
0x180079a0f  jnz     short loc_180079A2C
0x180079a11  cmp     dword ptr [rax+0E8h], 9
0x180079a18  jnz     loc_180079B31
0x180079a1e  lea     rsi, [rax+220h]
0x180079a25  lea     rbx, [rax+230h]
0x180079a2c  mov     r15, [rax+0E0h]
0x180079a33  cmp     [rsi+8], r9
0x180079a37  jnz     short loc_180079A40
0x180079a39  lea     rsi, [rax+0A0h]
0x180079a40  cmp     [rbx+8], r9
0x180079a44  jnz     short loc_180079A4D
0x180079a46  lea     rbx, [rax+0B0h]
0x180079a4d  lea     rdx, [rax+0A0h]; String2
0x180079a54  mov     r8b, 1; CaseInsensitive
0x180079a57  mov     rcx, rsi; String1
0x180079a5a  call    cs:__imp_RtlEqualUnicodeString
0x180079a61  nop     dword ptr [rax+rax+00h]
0x180079a66  xor     r9d, r9d
0x180079a69  test    al, al
0x180079a6b  jz      short loc_180079A91
0x180079a6d  lea     rdx, [rdi+0B0h]; String2
0x180079a74  mov     r8b, 1; CaseInsensitive
0x180079a77  mov     rcx, rbx; String1
0x180079a7a  call    cs:__imp_RtlEqualUnicodeString
0x180079a81  nop     dword ptr [rax+rax+00h]
0x180079a86  xor     r9d, r9d
0x180079a89  test    al, al
0x180079a8b  jnz     loc_180079B31
0x180079a91  test    r12, r12
0x180079a94  jz      loc_180079B39
0x180079a9a  mov     rax, [r12]
0x180079a9e  movq    rdx, xmm6
0x180079aa3  psrldq  xmm6, 8
0x180079aa8  movq    rcx, xmm6
0x180079aad  sub     rax, rdx
0x180079ab0  jnz     short loc_180079ABA
0x180079ab2  mov     rax, [r12+8]
0x180079ab7  sub     rax, rcx
0x180079aba  test    rax, rax
0x180079abd  jz      short loc_180079B39
0x180079abf  mov     rax, [rdi+204h]
0x180079ac6  sub     rax, rdx
0x180079ac9  jnz     short loc_180079AD5
0x180079acb  mov     rax, [rdi+20Ch]
0x180079ad2  sub     rax, rcx
0x180079ad5  test    rax, rax
0x180079ad8  jnz     short loc_180079AE8
0x180079ada  mov     rdx, r12
0x180079add  mov     rcx, r14
0x180079ae0  call    LsaISetLogonGuidInLogonSession
0x180079ae5  xor     r9d, r9d
0x180079ae8  cmp     dword ptr [r14], 3E7h
0x180079aef  jnz     short loc_180079B62
0x180079af1  cmp     [r14+4], r9d
0x180079af5  jnz     short loc_180079B62
0x180079af7  mov     rdx, rbx
0x180079afa  mov     rcx, rsi
0x180079afd  call    cs:__imp_?LsapIsLocalSystem@@YAJPEAU_UNICODE_STRING@@0@Z; LsapIsLocalSystem(_UNICODE_STRING *,_UNICODE_STRING *)
0x180079b04  nop     dword ptr [rax+rax+00h]
0x180079b09  xor     r9d, r9d
0x180079b0c  test    eax, eax
0x180079b0e  jnz     short loc_180079B29
0x180079b10  mov     rdx, rbx
0x180079b13  mov     rcx, rsi
0x180079b16  call    cs:__imp_?LsapIsLocalOrNetworkServiceOrIUser@@YAHPEAU_UNICODE_STRING@@0@Z; LsapIsLocalOrNetworkServiceOrIUser(_UNICODE_STRING *,_UNICODE_STRING *)
0x180079b1d  nop     dword ptr [rax+rax+00h]
0x180079b22  xor     r9d, r9d
0x180079b25  test    eax, eax
0x180079b27  jz      short loc_180079B62
0x180079b29  mov     ebx, r9d
0x180079b2c  jmp     loc_180079D01
0x180079b31  mov     ebx, r9d
0x180079b34  jmp     loc_180079D06
0x180079b39  lea     r12, [rdi+204h]
0x180079b40  jmp     short loc_180079AE8
0x180079b42  cmp     dword ptr [r14], 3E6h
0x180079b49  mov     r15, r9
0x180079b4c  jnz     short loc_180079AE8
0x180079b4e  cmp     [r14+4], r9d
0x180079b52  jnz     short loc_180079B62
0x180079b54  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180079b5b  mov     r15, [rax+360h]
0x180079b62  cmp     dword ptr [r14], 3E6h
0x180079b69  jnz     short loc_180079BA0
0x180079b6b  cmp     [r14+4], r9d
0x180079b6f  jnz     short loc_180079BA0
0x180079b71  test    rsi, rsi
0x180079b74  jz      short loc_180079B7C
0x180079b76  cmp     [rsi], r9w
0x180079b7a  jnz     short loc_180079B87
0x180079b7c  test    rbx, rbx
0x180079b7f  jz      short loc_180079B29
0x180079b81  cmp     [rbx], r9w
0x180079b85  jz      short loc_180079B29
0x180079b87  mov     rdx, rbx
0x180079b8a  mov     rcx, rsi
0x180079b8d  call    cs:__imp_?LsapIsAnonymous@@YAHPEAU_UNICODE_STRING@@0@Z; LsapIsAnonymous(_UNICODE_STRING *,_UNICODE_STRING *)
0x180079b94  nop     dword ptr [rax+rax+00h]
0x180079b99  xor     r9d, r9d
0x180079b9c  test    eax, eax
0x180079b9e  jnz     short loc_180079B29
0x180079ba0  mov     ecx, dword ptr [rbp+680h+var_6F0]
0x180079ba3  lea     r8, [rbp+680h+var_6F8]
0x180079ba7  mov     edx, 21Ah
0x180079bac  call    cs:__imp_LsapGetImageNameFromProcessId
0x180079bb3  nop     dword ptr [rax+rax+00h]
0x180079bb8  xor     ecx, ecx
0x180079bba  test    eax, eax
0x180079bbc  js      short loc_180079BC7
0x180079bbe  mov     rax, [rbp+680h+var_6F8]
0x180079bc2  cmp     [rax], cx
0x180079bc5  jnz     short loc_180079BCB
0x180079bc7  mov     [rbp+680h+var_6F8], rcx
0x180079bcb  call    IsLsapAdtInitParametersArrayPresent
0x180079bd0  test    al, al
0x180079bd2  jz      loc_180079CFC
0x180079bd8  mov     rax, [r14]
0x180079bdb  test    r15, r15
0x180079bde  jnz     short loc_180079BEE
0x180079be0  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180079be7  mov     r15, [rcx+2D0h]
0x180079bee  mov     rcx, [rbp+680h+var_6F8]
0x180079bf2  mov     edx, 1
0x180079bf7  mov     [rsp+0E8h], r13
0x180079bff  mov     r8d, 1228h
0x180079c05  mov     dword ptr [rsp+7F0h+var_710], 17h
0x180079c10  mov     qword ptr [rsp+7F0h+var_718], rcx
0x180079c18  mov     rcx, [rbp+680h+var_6F0]
0x180079c1c  mov     dword ptr [rsp+7F0h+var_720], edx
0x180079c23  mov     qword ptr [rsp+7F0h+var_728], rcx
0x180079c2b  mov     rcx, [rbp+680h+var_6C8]
0x180079c2f  mov     dword ptr [rsp+7F0h+var_730], 0Bh
0x180079c3a  mov     qword ptr [rsp+7F0h+var_738], rcx
0x180079c42  mov     rcx, [rbp+680h+var_6C0]
0x180079c46  mov     dword ptr [rsp+7F0h+var_740], edx
0x180079c4d  mov     qword ptr [rsp+7F0h+var_748], rcx
0x180079c55  mov     rcx, [rbp+680h+var_6B8]
0x180079c59  mov     dword ptr [rsp+7F0h+var_750], edx
0x180079c60  mov     qword ptr [rsp+7F0h+var_758], rcx
0x180079c68  lea     ecx, [rdx+0Ch]
0x180079c6b  mov     dword ptr [rsp+7F0h+var_760], ecx
0x180079c72  mov     qword ptr [rsp+7F0h+var_768], rbx
0x180079c7a  lea     r9d, [rcx+5Ch]
0x180079c7e  mov     dword ptr [rsp+7F0h+var_770], edx
0x180079c85  mov     qword ptr [rsp+7F0h+var_778], rsi
0x180079c8a  mov     dword ptr [rsp+7F0h+var_780], edx
0x180079c8e  mov     qword ptr [rsp+7F0h+var_788], r12
0x180079c93  mov     dword ptr [rsp+7F0h+var_790], ecx
0x180079c97  mov     qword ptr [rsp+7F0h+var_798], rax
0x180079c9c  mov     rax, cs:__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsapSubsystemName
0x180079ca3  mov     dword ptr [rsp+7F0h+var_7A0], 5
0x180079cab  mov     qword ptr [rsp+7F0h+var_7A8], rax
0x180079cb0  movzx   eax, [rbp+680h+var_6FE]
0x180079cb4  mov     dword ptr [rsp+7F0h+var_7B0], edx
0x180079cb8  lea     edx, [rcx-0Bh]
0x180079cbb  mov     qword ptr [rsp+7F0h+var_7B8], r15
0x180079cc0  lea     rcx, [rbp+680h+var_6A0]
0x180079cc4  mov     dword ptr [rsp+7F0h+var_7C0], 4
0x180079ccc  mov     word ptr [rsp+7F0h+var_7C8], 0Ch
0x180079cd3  mov     [rsp+7F0h+var_7D0], ax
0x180079cd8  call    cs:__imp_LsapAdtInitParametersArray
0x180079cdf  nop     dword ptr [rax+rax+00h]
0x180079ce4  mov     ebx, eax
0x180079ce6  test    eax, eax
0x180079ce8  js      short loc_180079D01
0x180079cea  lea     rcx, [rbp+680h+var_6A0]
0x180079cee  call    cs:__imp_LsapAdtWriteLog
0x180079cf5  nop     dword ptr [rax+rax+00h]
0x180079cfa  jmp     short loc_180079D01
0x180079cfc  mov     ebx, 0C0000002h
0x180079d01  test    rdi, rdi
0x180079d04  jz      short loc_180079D0E
0x180079d06  mov     rcx, rdi; struct _LSAP_LOGON_SESSION *
0x180079d09  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x180079d0e  mov     rdx, [rbp+680h+var_6F8]
0x180079d12  jmp     short loc_180079D19
0x180079d14  mov     ebx, 0C000000Dh
0x180079d19  test    rdx, rdx
0x180079d1c  jz      short loc_180079D32
0x180079d1e  lea     rax, [rbp+680h+var_280]
  ... truncated ...
```
