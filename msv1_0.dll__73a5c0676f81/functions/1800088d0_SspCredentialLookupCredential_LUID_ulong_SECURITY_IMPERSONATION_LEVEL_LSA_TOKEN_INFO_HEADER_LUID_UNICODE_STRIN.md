# SspCredentialLookupCredential(_LUID *,ulong,_SECURITY_IMPERSONATION_LEVEL,_LSA_TOKEN_INFO_HEADER *,_LUID *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800088d0`
- end: `0x180008d0e`
- name: `?SspCredentialLookupCredential@@YAPEAU_SSP_CREDENTIAL@@PEAU_LUID@@KW4_SECURITY_IMPERSONATION_LEVEL@@PEAU_LSA_TOKEN_INFO_HEADER@@0PEAU_UNICODE_STRING@@33@Z`
- size: `1086`
- prototype: `struct _SSP_CREDENTIAL *__fastcall(struct _LUID *, unsigned int, enum _SECURITY_IMPERSONATION_LEVEL, struct _LSA_TOKEN_INFO_HEADER *, struct _LUID *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008180`

## callees

- `0x180006c50`
- `0x1800088d0`
- `0x18002f014`
- `0x180030844`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `NtlmShared!NtLmAlterRtlEqualUnicodeString` at `0x180008a1b`
- `NtlmShared!NtLmAlterRtlEqualUnicodeString` at `0x180008a30`
- `NtlmShared!NtLmAlterRtlEqualUnicodeString` at `0x180008a1b`
- `NtlmShared!NtLmAlterRtlEqualUnicodeString` at `0x180008a30`
- `ntdll!RtlReleaseResource` at `0x180008aa2`
- `ntdll!RtlReleaseResource` at `0x180008aa2`
- `ntdll!RtlAcquireResourceShared` at `0x1800089b0`
- `ntdll!RtlAcquireResourceShared` at `0x1800089b0`
- `LSASRV!LsaIEqualSupplementalTokenInfo` at `0x1800089f6`
- `LSASRV!LsaIEqualSupplementalTokenInfo` at `0x1800089f6`

## pseudocode

```c
struct _LIST_ENTRY *__fastcall SspCredentialLookupCredential(
        struct _LUID *a1,
        int a2,
        enum _SECURITY_IMPERSONATION_LEVEL a3,
        struct _LSA_TOKEN_INFO_HEADER *a4,
        struct _LUID *a5,
        struct _UNICODE_STRING *a6,
        struct _UNICODE_STRING *a7,
        struct _UNICODE_STRING *a8)
{
  unsigned __int16 v12; // cx
  struct _LIST_ENTRY *v13; // r14
  _QWORD *v14; // rax
  struct _LIST_ENTRY *i; // rbx
  void **v16; // rdx
  bool v17; // zf
  _QWORD *v18; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  void *v22; // rax
  size_t MaximumLength; // r8
  PWSTR Buffer; // rdx
  int v25; // [rsp+30h] [rbp-30h] BYREF
  void *v26[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v27; // [rsp+48h] [rbp-18h] BYREF
  __int64 v28; // [rsp+58h] [rbp-8h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
  v28 = 0;
  v27 = 0;
  *(_OWORD *)v26 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v27) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v21 = 13;
    goto LABEL_56;
  }
  v26[0] = 0;
  v12 = 0;
  v26[1] = 0;
  if ( !a8 || !a8->Buffer )
    goto LABEL_5;
  v22 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)(a8->MaximumLength);
  v26[1] = v22;
  if ( v22 )
  {
    MaximumLength = a8->MaximumLength;
    Buffer = a8->Buffer;
    LOWORD(v26[0]) = a8->Length;
    WORD1(v26[0]) = MaximumLength;
    memcpy_0(v22, Buffer, MaximumLength);
    v12 = WORD1(v26[0]);
LABEL_5:
    v13 = 0;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ced0880886a53ec11230ac267b1eff8e_Traceguids);
      v12 = WORD1(v26[0]);
      v14 = WPP_GLOBAL_Control;
    }
    if ( LOWORD(v26[0]) && v12 )
    {
      ((void (__fastcall *)(void *, _QWORD))LsaFunctions->LsaProtectMemory)(v26[1], v12);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x200) != 0 )
      WPP_SF_(v14[2], 11, WPP_ced0880886a53ec11230ac267b1eff8e_Traceguids);
    RtlAcquireResourceShared(&SspCredentialCritSect, 1u);
    for ( i = SspCredentialList.Flink; i != &SspCredentialList; i = i->Flink )
    {
      if ( a1->LowPart == LODWORD(i[1].Blink)
        && a1->HighPart == HIDWORD(i[1].Blink)
        && LODWORD(i[2].Flink) == (_DWORD)v27
        && LODWORD(i[2].Blink) == a3
        && (unsigned int)LsaIEqualSupplementalTokenInfo(i[6].Blink, a4)
        && ((BYTE8(v27) & 1) == 0 || BYTE1(i[6].Flink))
        && a2 == HIDWORD(i[1].Flink)
        && (unsigned __int8)NtLmAlterRtlEqualUnicodeString(a6, &i[4], 0)
        && (unsigned __int8)NtLmAlterRtlEqualUnicodeString(a7, &i[3], 0) )
      {
        v16 = v26;
        v17 = BYTE2(i[6].Flink) == 0;
        v25 = 0;
        if ( !v17 )
          v16 = (void **)a8;
        if ( (*(int (__fastcall **)(struct NtlmCredIsoApi *, void **, struct _LIST_ENTRY *, int *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj
                                                                                                  + 184LL))(
               LocalhostNtLmCredIsoObj::IsoObj,
               v16,
               i,
               &v25) < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
        }
        else if ( v25 && a5->LowPart == LODWORD(i[7].Blink) && a5->HighPart == HIDWORD(i[7].Blink) )
        {
          _InterlockedIncrement((volatile signed __int32 *)&i[1]);
          v13 = i;
          break;
        }
      }
    }
    RtlReleaseResource(&SspCredentialCritSect);
    if ( v26[1] )
    {
      memset_0(v26[1], 0, LOWORD(v26[0]));
      NtLmFree(v26[1]);
    }
    if ( !v13 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      {
LABEL_35:
        if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x200) != 0 )
          WPP_SF_(v18[2], 17, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
        return v13;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
    }
    v18 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
    {
      v21 = 14;
LABEL_56:
      WPP_SF_(v20[2], v21, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp-28h+arg_10], rdi
0x1800088d5  push    rbp
0x1800088d6  push    r12
0x1800088d8  push    r13
0x1800088da  push    r14
0x1800088dc  push    r15
0x1800088de  mov     rbp, rsp
0x1800088e1  sub     rsp, 60h
0x1800088e5  mov     r13, r9
0x1800088e8  mov     r15d, r8d
0x1800088eb  mov     r12d, edx
0x1800088ee  mov     rdi, rcx
0x1800088f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088f8  lea     r14, WPP_GLOBAL_Control
0x1800088ff  cmp     rcx, r14
0x180008902  jnz     loc_180008B03
0x180008908  xor     eax, eax
0x18000890a  mov     [rsp+60h+arg_0], rbx
0x180008912  mov     [rbp+var_8], rax
0x180008916  lea     rcx, [rbp+var_18]
0x18000891a  mov     rax, cs:LsaFunctions
0x180008921  xorps   xmm0, xmm0
0x180008924  movups  [rbp+var_18], xmm0
0x180008928  mov     [rsp+60h+arg_8], rsi
0x180008930  movups  xmmword ptr [rbp+var_28], xmm0
0x180008934  mov     rax, [rax+0C0h]
0x18000893b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008940  test    al, al
0x180008942  jz      loc_180008B60
0x180008948  mov     rsi, [rbp+arg_38]
0x18000894c  xor     ebx, ebx
0x18000894e  mov     [rbp+var_28], rbx
0x180008952  mov     ecx, ebx
0x180008954  mov     [rbp+var_28+8], rbx
0x180008958  test    rsi, rsi
0x18000895b  jz      short loc_180008967
0x18000895d  cmp     [rsi+8], rcx
0x180008961  jnz     loc_180008B88
0x180008967  mov     r14, rbx
0x18000896a  mov     rax, cs:WPP_GLOBAL_Control
0x180008971  lea     rbx, WPP_GLOBAL_Control
0x180008978  cmp     rax, rbx
0x18000897b  jz      short loc_18000898A
0x18000897d  test    dword ptr [rax+1Ch], 200h
0x180008984  jnz     loc_180008C22
0x18000898a  cmp     word ptr [rbp+var_28], r14w
0x18000898f  jnz     loc_180008C47
0x180008995  cmp     rax, rbx
0x180008998  jz      short loc_1800089A7
0x18000899a  test    dword ptr [rax+1Ch], 200h
0x1800089a1  jnz     loc_180008C76
0x1800089a7  mov     dl, 1; Wait
0x1800089a9  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x1800089b0  call    cs:__imp_RtlAcquireResourceShared
0x1800089b6  mov     rbx, cs:?SspCredentialList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SspCredentialList
0x1800089bd  lea     rax, ?SspCredentialList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SspCredentialList
0x1800089c4  cmp     rbx, rax
0x1800089c7  jz      loc_180008A9B
0x1800089cd  mov     eax, [rbx+18h]
0x1800089d0  cmp     [rdi], eax
0x1800089d2  jz      short loc_1800089D9
0x1800089d4  mov     rbx, [rbx]
0x1800089d7  jmp     short loc_1800089BD
0x1800089d9  mov     eax, [rbx+1Ch]
0x1800089dc  cmp     [rdi+4], eax
0x1800089df  jnz     short loc_1800089D4
0x1800089e1  mov     eax, dword ptr [rbp+var_18]
0x1800089e4  cmp     [rbx+20h], eax
0x1800089e7  jnz     short loc_1800089D4
0x1800089e9  cmp     [rbx+28h], r15d
0x1800089ed  jnz     short loc_1800089D4
0x1800089ef  mov     rcx, [rbx+68h]
0x1800089f3  mov     rdx, r13
0x1800089f6  call    cs:__imp_LsaIEqualSupplementalTokenInfo
0x1800089fc  test    eax, eax
0x1800089fe  jz      short loc_1800089D4
0x180008a00  test    byte ptr [rbp+var_18+8], 1
0x180008a04  jnz     loc_180008C90
0x180008a0a  cmp     r12d, [rbx+14h]
0x180008a0e  jnz     short loc_1800089D4
0x180008a10  mov     rcx, [rbp+arg_28]
0x180008a14  lea     rdx, [rbx+40h]
0x180008a18  xor     r8d, r8d
0x180008a1b  call    cs:__imp_NtLmAlterRtlEqualUnicodeString
0x180008a21  test    al, al
0x180008a23  jz      short loc_1800089D4
0x180008a25  mov     rcx, [rbp+arg_30]
0x180008a29  lea     rdx, [rbx+30h]
0x180008a2d  xor     r8d, r8d
0x180008a30  call    cs:__imp_NtLmAlterRtlEqualUnicodeString
0x180008a36  test    al, al
0x180008a38  jz      short loc_1800089D4
0x180008a3a  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x180008a41  lea     rdx, [rbp+var_28]
0x180008a45  cmp     [rbx+62h], r14b
0x180008a49  lea     r9, [rbp+var_30]
0x180008a4d  mov     [rbp+var_30], r14d
0x180008a51  mov     r8, rbx
0x180008a54  cmovnz  rdx, rsi
0x180008a58  mov     rax, [rcx]
0x180008a5b  mov     rax, [rax+0B8h]
0x180008a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a67  test    eax, eax
0x180008a69  js      loc_180008C9F
0x180008a6f  cmp     [rbp+var_30], r14d
0x180008a73  jz      loc_1800089D4
0x180008a79  mov     rcx, [rbp+arg_20]
0x180008a7d  mov     eax, [rbx+78h]
0x180008a80  cmp     [rcx], eax
0x180008a82  jnz     loc_1800089D4
0x180008a88  mov     eax, [rbx+7Ch]
0x180008a8b  cmp     [rcx+4], eax
0x180008a8e  jnz     loc_1800089D4
0x180008a94  lock inc dword ptr [rbx+10h]
0x180008a98  mov     r14, rbx
0x180008a9b  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x180008aa2  call    cs:__imp_RtlReleaseResource
0x180008aa8  mov     rcx, [rbp+var_28+8]; void *
0x180008aac  test    rcx, rcx
0x180008aaf  jnz     loc_180008CDA
0x180008ab5  test    r14, r14
0x180008ab8  jz      short loc_180008B2A
0x180008aba  lea     rbx, WPP_GLOBAL_Control
0x180008ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ac8  cmp     rcx, rbx
0x180008acb  jz      short loc_180008ADA
0x180008acd  test    dword ptr [rcx+1Ch], 200h
0x180008ad4  jnz     loc_180008CF4
0x180008ada  mov     rax, r14
0x180008add  mov     rsi, [rsp+60h+arg_8]
0x180008ae5  mov     rbx, [rsp+60h+arg_0]
0x180008aed  mov     rdi, [rsp+60h+arg_10]
0x180008af5  add     rsp, 60h
0x180008af9  pop     r15
0x180008afb  pop     r14
0x180008afd  pop     r13
0x180008aff  pop     r12
0x180008b01  pop     rbp
0x180008b02  retn
0x180008b03  test    dword ptr [rcx+1Ch], 200h
0x180008b0a  jz      loc_180008908
0x180008b10  mov     rcx, [rcx+10h]
0x180008b14  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008b1b  mov     edx, 0Ch
0x180008b20  call    WPP_SF_
0x180008b25  jmp     loc_180008908
0x180008b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b31  lea     rbx, WPP_GLOBAL_Control
0x180008b38  cmp     rcx, rbx
0x180008b3b  jz      short loc_180008ADA
0x180008b3d  test    dword ptr [rcx+1Ch], 200h
0x180008b44  jz      short loc_180008AC8
0x180008b46  mov     rcx, [rcx+10h]
0x180008b4a  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008b51  mov     edx, 10h
0x180008b56  call    WPP_SF_
0x180008b5b  jmp     loc_180008AC1
0x180008b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b67  cmp     rcx, r14
0x180008b6a  jz      short loc_180008B81
0x180008b6c  test    byte ptr [rcx+1Ch], 1
0x180008b70  jz      short loc_180008B81
0x180008b72  mov     edx, 0Dh
0x180008b77  jmp     loc_180008C0D
0x180008b7c  cmp     rcx, r14
0x180008b7f  jnz     short loc_180008BFE
0x180008b81  xor     eax, eax
0x180008b83  jmp     loc_180008ADD
0x180008b88  mov     rax, cs:LsaFunctions
0x180008b8f  movzx   ecx, word ptr [rsi+2]
0x180008b93  mov     rax, [rax+180h]
0x180008b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9f  mov     [rbp+var_28+8], rax
0x180008ba3  test    rax, rax
0x180008ba6  jnz     short loc_180008BD8
0x180008ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008baf  cmp     rcx, r14
0x180008bb2  jz      short loc_180008B81
0x180008bb4  test    byte ptr [rcx+1Ch], 1
0x180008bb8  jz      short loc_180008B7C
0x180008bba  mov     rcx, [rcx+10h]
0x180008bbe  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x180008bc5  mov     edx, 10h
0x180008bca  call    WPP_SF_
0x180008bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bd6  jmp     short loc_180008B7C
0x180008bd8  movzx   ecx, word ptr [rsi]
0x180008bdb  movzx   r8d, word ptr [rsi+2]; Size
0x180008be0  mov     rdx, [rsi+8]; Src
0x180008be4  mov     word ptr [rbp+var_28], cx
0x180008be8  mov     rcx, rax; void *
0x180008beb  mov     word ptr [rbp+var_28+2], r8w
0x180008bf0  call    memcpy_0
0x180008bf5  movzx   ecx, word ptr [rbp+var_28+2]
0x180008bf9  jmp     loc_180008967
0x180008bfe  test    byte ptr [rcx+1Ch], 1
0x180008c02  jz      loc_180008B81
0x180008c08  mov     edx, 0Eh
0x180008c0d  mov     rcx, [rcx+10h]
0x180008c11  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008c18  call    WPP_SF_
0x180008c1d  jmp     loc_180008B81
0x180008c22  mov     rcx, [rax+10h]
0x180008c26  lea     r8, WPP_ced0880886a53ec11230ac267b1eff8e_Traceguids
0x180008c2d  mov     edx, 0Ah
0x180008c32  call    WPP_SF_
0x180008c37  movzx   ecx, word ptr [rbp+var_28+2]
0x180008c3b  mov     rax, cs:WPP_GLOBAL_Control
0x180008c42  jmp     loc_18000898A
0x180008c47  test    cx, cx
0x180008c4a  jz      loc_180008995
0x180008c50  mov     rax, cs:LsaFunctions
0x180008c57  movzx   edx, cx
0x180008c5a  mov     rcx, [rbp+var_28+8]
0x180008c5e  mov     rax, [rax+160h]
0x180008c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c6a  mov     rax, cs:WPP_GLOBAL_Control
0x180008c71  jmp     loc_180008995
0x180008c76  mov     rcx, [rax+10h]
0x180008c7a  lea     r8, WPP_ced0880886a53ec11230ac267b1eff8e_Traceguids
0x180008c81  mov     edx, 0Bh
0x180008c86  call    WPP_SF_
0x180008c8b  jmp     loc_1800089A7
0x180008c90  cmp     [rbx+61h], r14b
0x180008c94  jz      loc_1800089D4
0x180008c9a  jmp     loc_180008A0A
0x180008c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ca6  lea     rax, WPP_GLOBAL_Control
0x180008cad  cmp     rcx, rax
0x180008cb0  jz      loc_1800089D4
0x180008cb6  test    byte ptr [rcx+1Ch], 1
0x180008cba  jz      loc_1800089D4
0x180008cc0  mov     rcx, [rcx+10h]
0x180008cc4  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008ccb  mov     edx, 0Fh
0x180008cd0  call    WPP_SF_
0x180008cd5  jmp     loc_1800089D4
0x180008cda  movzx   r8d, word ptr [rbp+var_28]; Size
0x180008cdf  xor     edx, edx; Val
0x180008ce1  call    memset_0
0x180008ce6  mov     rcx, [rbp+var_28+8]
0x180008cea  call    NtLmFree
0x180008cef  jmp     loc_180008AB5
0x180008cf4  mov     rcx, [rcx+10h]
0x180008cf8  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008cff  mov     edx, 11h
0x180008d04  call    WPP_SF_
0x180008d09  jmp     loc_180008ADA
```
