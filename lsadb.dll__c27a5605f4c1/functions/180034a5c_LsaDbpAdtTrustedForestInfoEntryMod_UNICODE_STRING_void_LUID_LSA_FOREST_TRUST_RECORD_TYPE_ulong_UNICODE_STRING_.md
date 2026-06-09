# LsaDbpAdtTrustedForestInfoEntryMod(_UNICODE_STRING *,void *,_LUID *,LSA_FOREST_TRUST_RECORD_TYPE,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *)

- ea: `0x180034a5c`
- end: `0x180034e71`
- name: `?LsaDbpAdtTrustedForestInfoEntryMod@@YAJPEAU_UNICODE_STRING@@PEAXPEAU_LUID@@W4LSA_FOREST_TRUST_RECORD_TYPE@@K0001K0001@Z`
- size: `1045`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, struct _LUID *, enum LSA_FOREST_TRUST_RECORD_TYPE, unsigned int, struct _UNICODE_STRING *, PCUNICODE_STRING, PCUNICODE_STRING, void *, unsigned int, PCUNICODE_STRING String2, PCUNICODE_STRING, PCUNICODE_STRING, PSID Sid2)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020bc8`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x180034a5c`

## import_xrefs

- `LSASRV!LsapFreeLsaHeap` at `0x180034e3a`
- `LSASRV!LsapFreeLsaHeap` at `0x180034e3a`
- `LSASRV!LsapAdtWriteLog` at `0x180034e2a`
- `LSASRV!LsapAdtWriteLog` at `0x180034e2a`
- `LSASRV!LsapAuditFailed` at `0x180034e46`
- `LSASRV!LsapAuditFailed` at `0x180034e46`
- `LSASRV!LsapQueryClientInfo` at `0x180034b8c`
- `LSASRV!LsapQueryClientInfo` at `0x180034b8c`
- `ntdll!RtlLengthSid` at `0x180034c0e`
- `ntdll!RtlLengthSid` at `0x180034c33`
- `ntdll!RtlLengthSid` at `0x180034ca7`
- `ntdll!RtlLengthSid` at `0x180034cbe`
- `ntdll!RtlLengthSid` at `0x180034def`
- `ntdll!RtlLengthSid` at `0x180034e12`
- `ntdll!RtlLengthSid` at `0x180034c0e`
- `ntdll!RtlLengthSid` at `0x180034c33`
- `ntdll!RtlLengthSid` at `0x180034ca7`
- `ntdll!RtlLengthSid` at `0x180034cbe`
- `ntdll!RtlLengthSid` at `0x180034def`
- `ntdll!RtlLengthSid` at `0x180034e12`
- `ntdll!RtlEqualUnicodeString` at `0x180034d27`
- `ntdll!RtlEqualUnicodeString` at `0x180034d62`
- `ntdll!RtlEqualUnicodeString` at `0x180034d9c`
- `ntdll!RtlEqualUnicodeString` at `0x180034d27`
- `ntdll!RtlEqualUnicodeString` at `0x180034d62`
- `ntdll!RtlEqualUnicodeString` at `0x180034d9c`
- `ntdll!RtlEqualSid` at `0x180034dd8`
- `ntdll!RtlEqualSid` at `0x180034dd8`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180034bc0`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180034bc0`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedForestInfoEntryMod(
        struct _UNICODE_STRING *a1,
        void *a2,
        struct _LUID *a3,
        enum LSA_FOREST_TRUST_RECORD_TYPE a4,
        unsigned int a5,
        struct _UNICODE_STRING *a6,
        PCUNICODE_STRING a7,
        PCUNICODE_STRING a8,
        void *a9,
        unsigned int a10,
        PCUNICODE_STRING String2,
        PCUNICODE_STRING a12,
        PCUNICODE_STRING a13,
        PSID Sid2)
{
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  ULONG v18; // eax
  int Length; // eax
  int v20; // eax
  int v21; // eax
  ULONG v22; // eax
  _BYTE v24[8]; // [rsp+20h] [rbp-E0h] BYREF
  PSID *v25; // [rsp+28h] [rbp-D8h] BYREF
  enum LSA_FOREST_TRUST_RECORD_TYPE v26; // [rsp+30h] [rbp-D0h]
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING *v28; // [rsp+40h] [rbp-C0h]
  PSID Sid; // [rsp+48h] [rbp-B8h]
  struct _LUID *v30; // [rsp+50h] [rbp-B0h]
  PCUNICODE_STRING String1; // [rsp+58h] [rbp-A8h]
  PSID Sid1; // [rsp+60h] [rbp-A0h]
  _DWORD v33[7]; // [rsp+70h] [rbp-90h] BYREF
  ULONG v34; // [rsp+8Ch] [rbp-74h]
  __int16 *v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  struct _UNICODE_STRING *v38; // [rsp+C0h] [rbp-40h]
  int v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+CCh] [rbp-34h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  int v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+ECh] [rbp-14h]
  struct _UNICODE_STRING *v44; // [rsp+100h] [rbp+0h]
  int v45; // [rsp+108h] [rbp+8h]
  ULONG v46; // [rsp+10Ch] [rbp+Ch]
  __int16 *v47; // [rsp+120h] [rbp+20h]
  int v48; // [rsp+128h] [rbp+28h]
  int v49; // [rsp+12Ch] [rbp+2Ch]
  struct _LUID v50; // [rsp+130h] [rbp+30h]
  int v51; // [rsp+148h] [rbp+48h]
  int v52; // [rsp+14Ch] [rbp+4Ch]
  __int64 v53; // [rsp+150h] [rbp+50h]
  int v54; // [rsp+168h] [rbp+68h]
  int v55; // [rsp+16Ch] [rbp+6Ch]
  __int64 v56; // [rsp+170h] [rbp+70h]
  int v57; // [rsp+188h] [rbp+88h]
  int v58; // [rsp+18Ch] [rbp+8Ch]
  PCUNICODE_STRING v59; // [rsp+1A0h] [rbp+A0h]
  int v60; // [rsp+1A8h] [rbp+A8h]
  int v61; // [rsp+1ACh] [rbp+ACh]
  PCUNICODE_STRING v62; // [rsp+1C0h] [rbp+C0h]
  int v63; // [rsp+1C8h] [rbp+C8h]
  int v64; // [rsp+1CCh] [rbp+CCh]
  PCUNICODE_STRING v65; // [rsp+1E0h] [rbp+E0h]
  int v66; // [rsp+1E8h] [rbp+E8h]
  ULONG v67; // [rsp+1ECh] [rbp+ECh]
  __int16 *v68; // [rsp+200h] [rbp+100h]

  v30 = a3;
  Sid = a2;
  v28 = a1;
  String1 = a6;
  Sid1 = a9;
  v26 = a4;
  v27 = 0;
  v25 = 0;
  memset_0(v33, 0, 0x418u);
  v24[0] = 0;
  if ( v28 && v28->MaximumLength < v28->Length
    || a6 && a6->MaximumLength < a6->Length
    || a7 && a7->MaximumLength < a7->Length
    || a8 && a8->MaximumLength < a8->Length
    || String2 && String2->MaximumLength < String2->Length
    || a12 && a12->MaximumLength < a12->Length
    || a13 && a13->MaximumLength < a13->Length )
  {
    v14 = -1073741811;
LABEL_47:
    LsapAuditFailed((unsigned int)v14);
    return (unsigned int)v14;
  }
  v14 = LsapQueryClientInfo(&v25, &v27);
  if ( v14 >= 0 )
  {
    if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent()
      || (v14 = LsapAdtAuditingEnabledByLogonId(141, &v27, 8, v24), v14 >= 0) )
    {
      if ( v24[0] )
      {
        v33[0] = 6;
        v33[4] = 524429;
        v33[1] = 4867;
        v33[2] = 12;
        v33[6] = 4;
        if ( *v25 )
        {
          v34 = RtlLengthSid(*v25);
          v35 = (__int16 *)*v25;
        }
        else
        {
          v34 = RtlLengthSid(&AdtpNullSid);
          v35 = &AdtpNullSid;
        }
        v36 = 1;
        v37 = LsaDbpSubsystemName.Length + 16;
        v38 = &LsaDbpSubsystemName;
        v41 = v27;
        v42 = 1;
        v39 = 5;
        v40 = 8;
        v44 = v28;
        v17 = v28->Length + 16;
        v45 = 4;
        v43 = v17;
        if ( Sid )
        {
          v18 = RtlLengthSid(Sid);
          v47 = (__int16 *)Sid;
          v46 = v18;
        }
        else
        {
          v46 = RtlLengthSid(&AdtpNullSid);
          v47 = &AdtpNullSid;
        }
        v51 = 27;
        v54 = 27;
        v48 = 14;
        v50 = *v30;
        v53 = (unsigned int)v26;
        v56 = a10;
        v49 = 8;
        v52 = 4;
        v55 = 4;
        if ( String1 && String2 && !RtlEqualUnicodeString(String1, String2, 1u) )
        {
          Length = String2->Length;
          v57 = 1;
          v58 = Length + 16;
          v59 = String2;
        }
        if ( a7 && a12 && !RtlEqualUnicodeString(a7, a12, 1u) )
        {
          v20 = a12->Length;
          v60 = 1;
          v61 = v20 + 16;
          v62 = a12;
        }
        if ( a8 && a13 && !RtlEqualUnicodeString(a8, a13, 1u) )
        {
          v21 = a13->Length;
          v63 = 1;
          v64 = v21 + 16;
          v65 = a13;
        }
        if ( Sid1 && Sid2 && !RtlEqualSid(Sid1, Sid2) )
        {
          v66 = 4;
          v22 = RtlLengthSid(Sid2);
          v68 = (__int16 *)Sid2;
        }
        else
        {
          v66 = 4;
          v22 = RtlLengthSid(&AdtpNullSid);
          v68 = &AdtpNullSid;
        }
        v67 = v22;
        LsapAdtWriteLog(v33);
      }
    }
  }
  if ( v25 )
    LsapFreeLsaHeap(v25, v15, v16);
  if ( v14 < 0 )
    goto LABEL_47;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180034a5c  push    rbp
0x180034a5e  push    rbx
0x180034a5f  push    rsi
0x180034a60  push    rdi
0x180034a61  push    r12
0x180034a63  push    r13
0x180034a65  push    r14
0x180034a67  push    r15
0x180034a69  lea     rbp, [rsp-3A8h]
0x180034a71  sub     rsp, 4A8h
0x180034a78  mov     rax, cs:__security_cookie
0x180034a7f  xor     rax, rsp
0x180034a82  mov     [rbp+3E0h+var_50], rax
0x180034a89  mov     rax, [rbp+3E0h+arg_40]
0x180034a90  mov     rbx, [rbp+3E0h+arg_28]
0x180034a97  mov     rdi, [rbp+3E0h+arg_60]
0x180034a9e  mov     rsi, [rbp+3E0h+arg_58]
0x180034aa5  mov     r14, [rbp+3E0h+String2]
0x180034aac  mov     r12, [rbp+3E0h+arg_38]
0x180034ab3  mov     r13, [rbp+3E0h+arg_30]
0x180034aba  mov     r15, [rbp+3E0h+Sid2]
0x180034ac1  mov     [rsp+4E0h+var_490], r8
0x180034ac6  mov     r8d, 418h; Size
0x180034acc  mov     [rsp+4E0h+Sid], rdx
0x180034ad1  xor     edx, edx; Val
0x180034ad3  mov     [rsp+4E0h+var_4A0], rcx
0x180034ad8  lea     rcx, [rsp+4E0h+var_470]; void *
0x180034add  mov     [rsp+4E0h+String1], rbx
0x180034ae2  mov     [rsp+4E0h+Sid1], rax
0x180034ae7  mov     [rsp+4E0h+var_4B0], r9d
0x180034aec  mov     [rsp+4E0h+var_4A8], 0
0x180034af5  mov     [rsp+4E0h+var_4B8], 0
0x180034afe  call    memset_0
0x180034b03  mov     rcx, [rsp+4E0h+var_4A0]
0x180034b08  mov     [rsp+4E0h+var_4C0], 0
0x180034b0d  test    rcx, rcx
0x180034b10  jz      short loc_180034B1B
0x180034b12  movzx   eax, word ptr [rcx]
0x180034b15  cmp     [rcx+2], ax
0x180034b19  jb      short loc_180034B78
0x180034b1b  test    rbx, rbx
0x180034b1e  jz      short loc_180034B29
0x180034b20  movzx   eax, word ptr [rbx]
0x180034b23  cmp     [rbx+2], ax
0x180034b27  jb      short loc_180034B78
0x180034b29  test    r13, r13
0x180034b2c  jz      short loc_180034B3A
0x180034b2e  movzx   eax, word ptr [r13+0]
0x180034b33  cmp     [r13+2], ax
0x180034b38  jb      short loc_180034B78
0x180034b3a  test    r12, r12
0x180034b3d  jz      short loc_180034B4C
0x180034b3f  movzx   eax, word ptr [r12]
0x180034b44  cmp     [r12+2], ax
0x180034b4a  jb      short loc_180034B78
0x180034b4c  test    r14, r14
0x180034b4f  jz      short loc_180034B5C
0x180034b51  movzx   eax, word ptr [r14]
0x180034b55  cmp     [r14+2], ax
0x180034b5a  jb      short loc_180034B78
0x180034b5c  test    rsi, rsi
0x180034b5f  jz      short loc_180034B6A
0x180034b61  movzx   eax, word ptr [rsi]
0x180034b64  cmp     [rsi+2], ax
0x180034b68  jb      short loc_180034B78
0x180034b6a  test    rdi, rdi
0x180034b6d  jz      short loc_180034B82
0x180034b6f  movzx   eax, word ptr [rdi]
0x180034b72  cmp     [rdi+2], ax
0x180034b76  jnb     short loc_180034B82
0x180034b78  mov     ebx, 0C000000Dh
0x180034b7d  jmp     loc_180034E44
0x180034b82  lea     rdx, [rsp+4E0h+var_4A8]
0x180034b87  lea     rcx, [rsp+4E0h+var_4B8]
0x180034b8c  call    cs:__imp_LsapQueryClientInfo
0x180034b92  mov     ebx, eax
0x180034b94  test    eax, eax
0x180034b96  js      loc_180034E30
0x180034b9c  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180034ba1  mov     ecx, 8
0x180034ba6  mov     r10d, 8Dh
0x180034bac  test    al, al
0x180034bae  jz      short loc_180034BD0
0x180034bb0  mov     r8d, ecx
0x180034bb3  lea     r9, [rsp+4E0h+var_4C0]
0x180034bb8  mov     ecx, r10d
0x180034bbb  lea     rdx, [rsp+4E0h+var_4A8]
0x180034bc0  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180034bc6  mov     ebx, eax
0x180034bc8  test    eax, eax
0x180034bca  js      loc_180034E30
0x180034bd0  cmp     [rsp+4E0h+var_4C0], 0
0x180034bd5  jz      loc_180034E30
0x180034bdb  mov     rax, [rsp+4E0h+var_4B8]
0x180034be0  mov     [rsp+4E0h+var_470], 6
0x180034be8  mov     [rbp+3E0h+var_460], 8008Dh
0x180034bef  mov     [rsp+4E0h+var_46C], 1303h
0x180034bf7  mov     [rsp+4E0h+var_468], 0Ch
0x180034bff  mov     [rbp+3E0h+var_458], 4
0x180034c06  mov     rcx, [rax]; Sid
0x180034c09  test    rcx, rcx
0x180034c0c  jz      short loc_180034C2C
0x180034c0e  call    cs:__imp_RtlLengthSid
0x180034c14  mov     [rbp+3E0h+var_454], eax
0x180034c17  lea     rdx, AdtpNullSid
0x180034c1e  mov     rax, [rsp+4E0h+var_4B8]
0x180034c23  mov     rcx, [rax]
0x180034c26  mov     [rbp+3E0h+var_440], rcx
0x180034c2a  jmp     short loc_180034C47
0x180034c2c  lea     rcx, AdtpNullSid; Sid
0x180034c33  call    cs:__imp_RtlLengthSid
0x180034c39  lea     rdx, AdtpNullSid
0x180034c40  mov     [rbp+3E0h+var_454], eax
0x180034c43  mov     [rbp+3E0h+var_440], rdx
0x180034c47  movzx   eax, cs:?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsaDbpSubsystemName ...
0x180034c4e  mov     ecx, 1
0x180034c53  add     eax, 10h
0x180034c56  mov     [rbp+3E0h+var_438], ecx
0x180034c59  mov     [rbp+3E0h+var_434], eax
0x180034c5c  lea     rax, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x180034c63  mov     [rbp+3E0h+var_420], rax
0x180034c67  mov     rax, [rsp+4E0h+var_4A8]
0x180034c6c  mov     [rbp+3E0h+var_410], rax
0x180034c70  mov     [rbp+3E0h+var_3F8], ecx
0x180034c73  mov     rcx, [rsp+4E0h+var_4A0]
0x180034c78  mov     [rbp+3E0h+var_418], 5
0x180034c7f  mov     [rbp+3E0h+var_414], 8
0x180034c86  mov     [rbp+3E0h+var_3E0], rcx
0x180034c8a  movzx   eax, word ptr [rcx]
0x180034c8d  add     eax, 10h
0x180034c90  mov     [rbp+3E0h+var_3D8], 4
0x180034c97  mov     [rbp+3E0h+var_3F4], eax
0x180034c9a  mov     rax, [rsp+4E0h+Sid]
0x180034c9f  test    rax, rax
0x180034ca2  jz      short loc_180034CBB
0x180034ca4  mov     rcx, rax; Sid
0x180034ca7  call    cs:__imp_RtlLengthSid
0x180034cad  mov     rdx, [rsp+4E0h+Sid]
0x180034cb2  mov     [rbp+3E0h+var_3C0], rdx
0x180034cb6  mov     [rbp+3E0h+var_3D4], eax
0x180034cb9  jmp     short loc_180034CD2
0x180034cbb  mov     rcx, rdx; Sid
0x180034cbe  call    cs:__imp_RtlLengthSid
0x180034cc4  mov     [rbp+3E0h+var_3D4], eax
0x180034cc7  lea     rax, AdtpNullSid
0x180034cce  mov     [rbp+3E0h+var_3C0], rax
0x180034cd2  mov     rax, [rsp+4E0h+var_490]
0x180034cd7  mov     ecx, 1Bh
0x180034cdc  mov     [rbp+3E0h+var_398], ecx
0x180034cdf  mov     [rbp+3E0h+var_378], ecx
0x180034ce2  mov     [rbp+3E0h+var_3B8], 0Eh
0x180034ce9  mov     rax, [rax]
0x180034cec  lea     edx, [rcx-17h]
0x180034cef  mov     rcx, [rsp+4E0h+String1]; String1
0x180034cf4  mov     [rbp+3E0h+var_3B0], rax
0x180034cf8  mov     eax, [rsp+4E0h+var_4B0]
0x180034cfc  mov     [rbp+3E0h+var_390], rax
0x180034d00  mov     eax, [rbp+3E0h+arg_48]
0x180034d06  mov     [rbp+3E0h+var_370], rax
0x180034d0a  mov     [rbp+3E0h+var_3B4], 8
0x180034d11  mov     [rbp+3E0h+var_394], edx
0x180034d14  mov     [rbp+3E0h+var_374], edx
0x180034d17  test    rcx, rcx
0x180034d1a  jz      short loc_180034D4F
0x180034d1c  test    r14, r14
0x180034d1f  jz      short loc_180034D4F
0x180034d21  mov     r8b, 1; CaseInsensitive
0x180034d24  mov     rdx, r14; String2
0x180034d27  call    cs:__imp_RtlEqualUnicodeString
0x180034d2d  test    al, al
0x180034d2f  jnz     short loc_180034D4F
0x180034d31  movzx   eax, word ptr [r14]
0x180034d35  add     eax, 10h
0x180034d38  mov     [rbp+3E0h+var_358], 1
0x180034d42  mov     [rbp+3E0h+var_354], eax
0x180034d48  mov     [rbp+3E0h+var_340], r14
0x180034d4f  test    r13, r13
0x180034d52  jz      short loc_180034D89
0x180034d54  test    rsi, rsi
0x180034d57  jz      short loc_180034D89
0x180034d59  mov     r8b, 1; CaseInsensitive
0x180034d5c  mov     rdx, rsi; String2
0x180034d5f  mov     rcx, r13; String1
0x180034d62  call    cs:__imp_RtlEqualUnicodeString
0x180034d68  test    al, al
0x180034d6a  jnz     short loc_180034D89
0x180034d6c  movzx   eax, word ptr [rsi]
0x180034d6f  add     eax, 10h
0x180034d72  mov     [rbp+3E0h+var_338], 1
0x180034d7c  mov     [rbp+3E0h+var_334], eax
0x180034d82  mov     [rbp+3E0h+var_320], rsi
0x180034d89  test    r12, r12
0x180034d8c  jz      short loc_180034DC3
0x180034d8e  test    rdi, rdi
0x180034d91  jz      short loc_180034DC3
0x180034d93  mov     r8b, 1; CaseInsensitive
0x180034d96  mov     rdx, rdi; String2
0x180034d99  mov     rcx, r12; String1
0x180034d9c  call    cs:__imp_RtlEqualUnicodeString
0x180034da2  test    al, al
0x180034da4  jnz     short loc_180034DC3
0x180034da6  movzx   eax, word ptr [rdi]
0x180034da9  add     eax, 10h
0x180034dac  mov     [rbp+3E0h+var_318], 1
0x180034db6  mov     [rbp+3E0h+var_314], eax
0x180034dbc  mov     [rbp+3E0h+var_300], rdi
0x180034dc3  mov     rax, [rsp+4E0h+Sid1]
0x180034dc8  test    rax, rax
0x180034dcb  jz      short loc_180034DFE
0x180034dcd  test    r15, r15
0x180034dd0  jz      short loc_180034DFE
0x180034dd2  mov     rdx, r15; Sid2
0x180034dd5  mov     rcx, rax; Sid1
0x180034dd8  call    cs:__imp_RtlEqualSid
0x180034dde  test    al, al
0x180034de0  jnz     short loc_180034DFE
0x180034de2  mov     rcx, r15; Sid
0x180034de5  mov     [rbp+3E0h+var_2F8], 4
0x180034def  call    cs:__imp_RtlLengthSid
0x180034df5  mov     [rbp+3E0h+var_2E0], r15
0x180034dfc  jmp     short loc_180034E1F
0x180034dfe  lea     rdi, AdtpNullSid
0x180034e05  mov     [rbp+3E0h+var_2F8], 4
0x180034e0f  mov     rcx, rdi; Sid
0x180034e12  call    cs:__imp_RtlLengthSid
0x180034e18  mov     [rbp+3E0h+var_2E0], rdi
0x180034e1f  lea     rcx, [rsp+4E0h+var_470]
0x180034e24  mov     [rbp+3E0h+var_2F4], eax
0x180034e2a  call    cs:__imp_LsapAdtWriteLog
0x180034e30  mov     rcx, [rsp+4E0h+var_4B8]
0x180034e35  test    rcx, rcx
0x180034e38  jz      short loc_180034E40
0x180034e3a  call    cs:__imp_LsapFreeLsaHeap
0x180034e40  test    ebx, ebx
0x180034e42  jns     short loc_180034E4C
0x180034e44  mov     ecx, ebx
0x180034e46  call    cs:__imp_LsapAuditFailed
0x180034e4c  mov     eax, ebx
0x180034e4e  mov     rcx, [rbp+3E0h+var_50]
0x180034e55  xor     rcx, rsp; StackCookie
0x180034e58  call    __security_check_cookie
0x180034e5d  add     rsp, 4A8h
0x180034e64  pop     r15
0x180034e66  pop     r14
0x180034e68  pop     r13
0x180034e6a  pop     r12
0x180034e6c  pop     rdi
0x180034e6d  pop     rsi
0x180034e6e  pop     rbx
0x180034e6f  pop     rbp
0x180034e70  retn
```
