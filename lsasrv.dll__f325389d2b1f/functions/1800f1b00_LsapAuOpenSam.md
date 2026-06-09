# LsapAuOpenSam

- ea: `0x1800f1b00`
- end: `0x1800f1ffc`
- name: `LsapAuOpenSam`
- size: `1276`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad714`

## callees

- `0x18000c300`
- `0x18000d3b0`
- `0x180016f70`
- `0x18001ecf0`
- `0x18001f290`
- `0x1800364d0`
- `0x180038020`
- `0x18005faf0`
- `0x1800f1b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1dfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1f1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1fd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1f1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1fd9`
- `ntdll!RtlCopySid` at `0x1800f1c14`
- `ntdll!RtlCopySid` at `0x1800f1c50`
- `ntdll!RtlCopySid` at `0x1800f1cfa`
- `ntdll!RtlCopySid` at `0x1800f1d94`
- `ntdll!RtlCopySid` at `0x1800f1eab`
- `ntdll!RtlCopySid` at `0x1800f1c14`
- `ntdll!RtlCopySid` at `0x1800f1c50`
- `ntdll!RtlCopySid` at `0x1800f1cfa`
- `ntdll!RtlCopySid` at `0x1800f1d94`
- `ntdll!RtlCopySid` at `0x1800f1eab`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1b4e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1ba0`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1c27`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1c63`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1ca7`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1d0d`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1e58`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1ebe`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1b4e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1ba0`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1c27`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1c63`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1ca7`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1d0d`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1e58`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f1ebe`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1b67`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1bb9`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1cc0`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1e71`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1b67`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1bb9`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1cc0`
- `ntdll!RtlLengthRequiredSid` at `0x1800f1e71`
- `ntdll!RtlLengthSid` at `0x1800f1d62`
- `ntdll!RtlLengthSid` at `0x1800f1d62`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f1dc8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f1dc8`

## pseudocode

```c
__int64 __fastcall LsapAuOpenSam(unsigned __int8 a1)
{
  signed int InformationPolicy; // ebx
  PUCHAR v3; // rax
  PSID v4; // rdx
  ULONG v5; // ecx
  PUCHAR v6; // rax
  void *v7; // rax
  PUCHAR v8; // rax
  void *v9; // rdx

  if ( LsapNullSidAuthority.SubAuthority[0] == 1 )
    return 0;
  InformationPolicy = LsapOpenSamEx(a1);
  if ( InformationPolicy >= 0 )
  {
    LsapBuiltinDomainSubCount = *RtlSubAuthorityCountSid(*((PSID *)WellKnownSids + 84)) + 1;
    LsapBuiltinDomainMemberSidLength = RtlLengthRequiredSid(LsapBuiltinDomainSubCount);
    InformationPolicy = LsarQueryInformationPolicy(LsapPolicyHandle, PolicyAccountDomainInformation);
    if ( InformationPolicy >= 0 )
    {
      LsapAccountDomainSubCount = *RtlSubAuthorityCountSid(MEMORY[0x10]) + 1;
      LsapAccountDomainMemberSidLength = RtlLengthRequiredSid(LsapAccountDomainSubCount);
      LsapAccountDomainMemberSid = (PSID)LsapAllocate(LsapAccountDomainMemberSidLength);
      if ( !LsapAccountDomainMemberSid
        || (LsapBuiltinDomainMemberSid = (PSID)LsapAllocate(LsapBuiltinDomainMemberSidLength)) == 0 )
      {
LABEL_6:
        InformationPolicy = -1073741801;
        goto LABEL_21;
      }
      RtlCopySid(LsapAccountDomainMemberSidLength, LsapAccountDomainMemberSid, MEMORY[0x10]);
      v3 = RtlSubAuthorityCountSid(LsapAccountDomainMemberSid);
      v4 = LsapBuiltinDomainMemberSid;
      v5 = LsapBuiltinDomainMemberSidLength;
      ++*v3;
      RtlCopySid(v5, v4, *((PSID *)WellKnownSids + 84));
      v6 = RtlSubAuthorityCountSid(LsapBuiltinDomainMemberSid);
      ++*v6;
      if ( LsapProductType != NtProductLanManNt )
      {
        LsapLocalAccountDomainMemberSidLength = 0;
        LsapLocalAccountDomainSubCount = 0;
        LsapLocalAccountDomainMemberSid = 0;
LABEL_13:
        InformationPolicy = LsarQueryInformationPolicy(LsapPolicyHandle, PolicyPrimaryDomainInformation);
        if ( InformationPolicy >= 0 )
        {
          if ( ConvertStringSidToSidW(L"S-1-5-21-2702878673-795188819-444038987-2781", &LsapDefAppsSid) )
          {
            if ( LsapProductType == NtProductLanManNt )
            {
              InformationPolicy = LsarQueryInformationPolicy(LsapPolicyHandle, PolicyLocalAccountDomainInformation);
            }
            else
            {
              LsapDSRMDomainMemberSidLength = 0;
              LsapDSRMDomainSubCount = 0;
              LsapDSRMAccountDomainSid = 0;
            }
          }
          else if ( (int)GetLastError() > 0 )
          {
            InformationPolicy = (unsigned __int16)GetLastError() | 0xC0070000;
          }
          else
          {
            InformationPolicy = GetLastError();
          }
        }
        goto LABEL_21;
      }
      InformationPolicy = LsarQueryInformationPolicy(LsapPolicyHandle, PolicyLocalAccountDomainInformation);
      if ( InformationPolicy >= 0 )
      {
        LsapLocalAccountDomainSubCount = *RtlSubAuthorityCountSid(MEMORY[0x10]) + 1;
        LsapLocalAccountDomainMemberSidLength = RtlLengthRequiredSid(LsapLocalAccountDomainSubCount);
        v7 = (void *)LsapAllocate(LsapLocalAccountDomainMemberSidLength);
        LsapLocalAccountDomainMemberSid = v7;
        if ( v7 )
        {
          RtlCopySid(LsapLocalAccountDomainMemberSidLength, v7, MEMORY[0x10]);
          v8 = RtlSubAuthorityCountSid(LsapLocalAccountDomainMemberSid);
          ++*v8;
          goto LABEL_13;
        }
        goto LABEL_6;
      }
    }
  }
LABEL_21:
  v9 = 0;
  if ( InformationPolicy < 0 )
  {
    if ( LsapAccountDomainMemberSid )
    {
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)LsapAccountDomainMemberSid, 0);
      LsapAccountDomainMemberSid = 0;
    }
    if ( LsapLocalAccountDomainMemberSid )
    {
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)LsapLocalAccountDomainMemberSid, v9);
      LsapLocalAccountDomainMemberSid = 0;
    }
    if ( LsapBuiltinDomainMemberSid )
    {
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)LsapBuiltinDomainMemberSid, v9);
      LsapBuiltinDomainMemberSid = 0;
    }
    if ( LsapPrimaryDomainSid )
    {
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)LsapPrimaryDomainSid, v9);
      LsapPrimaryDomainSid = 0;
    }
    if ( qword_18019ECB0 )
    {
      LsapFreeString(&LsapPrimaryDomainName);
      LsapPrimaryDomainName = 0;
    }
    if ( LsapDefAppsSid )
    {
      LocalFree(LsapDefAppsSid);
      LsapDefAppsSid = 0;
    }
  }
  else
  {
    LsapNullSidAuthority.SubAuthority[0] = 1;
  }
  return (unsigned int)InformationPolicy;
}

```

## disassembly

```asm
0x1800f1b00  mov     [rsp-18h+arg_0], rbx
0x1800f1b05  push    rbp
0x1800f1b06  push    rsi
0x1800f1b07  push    rdi
0x1800f1b08  mov     rbp, rsp
0x1800f1b0b  sub     rsp, 30h
0x1800f1b0f  xor     esi, esi
0x1800f1b11  cmp     cs:?LsapNullSidAuthority@@3U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority, 1; _SID_IDENTIFIER_AUTHORITY LsapNullSidAuthority ...
0x1800f1b18  mov     [rbp+arg_18], rsi
0x1800f1b1c  mov     [rbp+hMem], rsi
0x1800f1b20  mov     [rbp+arg_8], rsi
0x1800f1b24  mov     [rbp+arg_10], rsi
0x1800f1b28  jnz     short loc_1800F1B31
0x1800f1b2a  xor     eax, eax
0x1800f1b2c  jmp     loc_1800F1FEE
0x1800f1b31  call    ?LsapOpenSamEx@@YAJE@Z; LsapOpenSamEx(uchar)
0x1800f1b36  mov     ebx, eax
0x1800f1b38  test    eax, eax
0x1800f1b3a  js      loc_1800F1EE2
0x1800f1b40  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800f1b47  mov     rcx, [rcx+2A0h]; Sid
0x1800f1b4e  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1b55  nop     dword ptr [rax+rax+00h]
0x1800f1b5a  mov     cl, [rax]
0x1800f1b5c  inc     cl
0x1800f1b5e  movzx   ecx, cl; SubAuthorityCount
0x1800f1b61  mov     cs:?LsapBuiltinDomainSubCount@@3EA, cl; uchar LsapBuiltinDomainSubCount
0x1800f1b67  call    cs:__imp_RtlLengthRequiredSid
0x1800f1b6e  nop     dword ptr [rax+rax+00h]
0x1800f1b73  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; struct _LSAP_DB_HANDLE *
0x1800f1b7a  lea     r8, [rbp+arg_18]
0x1800f1b7e  mov     edx, 5; enum _POLICY_INFORMATION_CLASS
0x1800f1b83  mov     cs:?LsapBuiltinDomainMemberSidLength@@3KA, eax; ulong LsapBuiltinDomainMemberSidLength
0x1800f1b89  call    LsarQueryInformationPolicy
0x1800f1b8e  mov     ebx, eax
0x1800f1b90  test    eax, eax
0x1800f1b92  js      loc_1800F1EE2
0x1800f1b98  mov     rcx, [rbp+arg_18]
0x1800f1b9c  mov     rcx, [rcx+10h]; Sid
0x1800f1ba0  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1ba7  nop     dword ptr [rax+rax+00h]
0x1800f1bac  mov     cl, [rax]
0x1800f1bae  inc     cl
0x1800f1bb0  movzx   ecx, cl; SubAuthorityCount
0x1800f1bb3  mov     cs:?LsapAccountDomainSubCount@@3EA, cl; uchar LsapAccountDomainSubCount
0x1800f1bb9  call    cs:__imp_RtlLengthRequiredSid
0x1800f1bc0  nop     dword ptr [rax+rax+00h]
0x1800f1bc5  mov     ecx, eax
0x1800f1bc7  mov     cs:?LsapAccountDomainMemberSidLength@@3KA, ecx; ulong LsapAccountDomainMemberSidLength
0x1800f1bcd  call    LsapAllocate
0x1800f1bd2  mov     cs:?LsapAccountDomainMemberSid@@3PEAXEA, rax; void * LsapAccountDomainMemberSid
0x1800f1bd9  test    rax, rax
0x1800f1bdc  jnz     short loc_1800F1BE8
0x1800f1bde  mov     ebx, 0C0000017h
0x1800f1be3  jmp     loc_1800F1EE2
0x1800f1be8  mov     ecx, cs:?LsapBuiltinDomainMemberSidLength@@3KA; ulong LsapBuiltinDomainMemberSidLength
0x1800f1bee  call    LsapAllocate
0x1800f1bf3  mov     cs:?LsapBuiltinDomainMemberSid@@3PEAXEA, rax; void * LsapBuiltinDomainMemberSid
0x1800f1bfa  test    rax, rax
0x1800f1bfd  jz      short loc_1800F1BDE
0x1800f1bff  mov     r8, [rbp+arg_18]
0x1800f1c03  mov     rdx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; DestinationSid
0x1800f1c0a  mov     ecx, cs:?LsapAccountDomainMemberSidLength@@3KA; DestinationSidLength
0x1800f1c10  mov     r8, [r8+10h]; SourceSid
0x1800f1c14  call    cs:__imp_RtlCopySid
0x1800f1c1b  nop     dword ptr [rax+rax+00h]
0x1800f1c20  mov     rcx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Sid
0x1800f1c27  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1c2e  nop     dword ptr [rax+rax+00h]
0x1800f1c33  mov     rdx, cs:?LsapBuiltinDomainMemberSid@@3PEAXEA; DestinationSid
0x1800f1c3a  mov     ecx, cs:?LsapBuiltinDomainMemberSidLength@@3KA; DestinationSidLength
0x1800f1c40  inc     byte ptr [rax]
0x1800f1c42  mov     r8, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800f1c49  mov     r8, [r8+2A0h]; SourceSid
0x1800f1c50  call    cs:__imp_RtlCopySid
0x1800f1c57  nop     dword ptr [rax+rax+00h]
0x1800f1c5c  mov     rcx, cs:?LsapBuiltinDomainMemberSid@@3PEAXEA; Sid
0x1800f1c63  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1c6a  nop     dword ptr [rax+rax+00h]
0x1800f1c6f  mov     edi, 0Eh
0x1800f1c74  inc     byte ptr [rax]
0x1800f1c76  cmp     cs:LsapProductType, 2
0x1800f1c7d  jnz     loc_1800F1D1D
0x1800f1c83  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; struct _LSAP_DB_HANDLE *
0x1800f1c8a  lea     r8, [rbp+hMem]
0x1800f1c8e  mov     edx, edi; enum _POLICY_INFORMATION_CLASS
0x1800f1c90  call    LsarQueryInformationPolicy
0x1800f1c95  mov     ebx, eax
0x1800f1c97  test    eax, eax
0x1800f1c99  js      loc_1800F1EE2
0x1800f1c9f  mov     rcx, [rbp+hMem]
0x1800f1ca3  mov     rcx, [rcx+10h]; Sid
0x1800f1ca7  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1cae  nop     dword ptr [rax+rax+00h]
0x1800f1cb3  mov     cl, [rax]
0x1800f1cb5  inc     cl
0x1800f1cb7  movzx   ecx, cl; SubAuthorityCount
0x1800f1cba  mov     cs:?LsapLocalAccountDomainSubCount@@3EA, cl; uchar LsapLocalAccountDomainSubCount
0x1800f1cc0  call    cs:__imp_RtlLengthRequiredSid
0x1800f1cc7  nop     dword ptr [rax+rax+00h]
0x1800f1ccc  mov     ecx, eax
0x1800f1cce  mov     cs:?LsapLocalAccountDomainMemberSidLength@@3KA, ecx; ulong LsapLocalAccountDomainMemberSidLength
0x1800f1cd4  call    LsapAllocate
0x1800f1cd9  mov     cs:?LsapLocalAccountDomainMemberSid@@3PEAXEA, rax; void * LsapLocalAccountDomainMemberSid
0x1800f1ce0  test    rax, rax
0x1800f1ce3  jz      loc_1800F1BDE
0x1800f1ce9  mov     r8, [rbp+hMem]
0x1800f1ced  mov     rdx, rax; DestinationSid
0x1800f1cf0  mov     ecx, cs:?LsapLocalAccountDomainMemberSidLength@@3KA; DestinationSidLength
0x1800f1cf6  mov     r8, [r8+10h]; SourceSid
0x1800f1cfa  call    cs:__imp_RtlCopySid
0x1800f1d01  nop     dword ptr [rax+rax+00h]
0x1800f1d06  mov     rcx, cs:?LsapLocalAccountDomainMemberSid@@3PEAXEA; Sid
0x1800f1d0d  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1d14  nop     dword ptr [rax+rax+00h]
0x1800f1d19  inc     byte ptr [rax]
0x1800f1d1b  jmp     short loc_1800F1D31
0x1800f1d1d  mov     cs:?LsapLocalAccountDomainMemberSidLength@@3KA, esi; ulong LsapLocalAccountDomainMemberSidLength
0x1800f1d23  mov     cs:?LsapLocalAccountDomainSubCount@@3EA, sil; uchar LsapLocalAccountDomainSubCount
0x1800f1d2a  mov     cs:?LsapLocalAccountDomainMemberSid@@3PEAXEA, rsi; void * LsapLocalAccountDomainMemberSid
0x1800f1d31  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; struct _LSAP_DB_HANDLE *
0x1800f1d38  lea     r8, [rbp+arg_8]
0x1800f1d3c  mov     edx, 3; enum _POLICY_INFORMATION_CLASS
0x1800f1d41  call    LsarQueryInformationPolicy
0x1800f1d46  mov     ebx, eax
0x1800f1d48  test    eax, eax
0x1800f1d4a  js      loc_1800F1EE2
0x1800f1d50  mov     rax, [rbp+arg_8]
0x1800f1d54  test    rax, rax
0x1800f1d57  jz      short loc_1800F1DBA
0x1800f1d59  mov     rcx, [rax+10h]; Sid
0x1800f1d5d  test    rcx, rcx
0x1800f1d60  jz      short loc_1800F1DBA
0x1800f1d62  call    cs:__imp_RtlLengthSid
0x1800f1d69  nop     dword ptr [rax+rax+00h]
0x1800f1d6e  mov     ecx, eax
0x1800f1d70  mov     ebx, eax
0x1800f1d72  call    LsapAllocate
0x1800f1d77  mov     cs:?LsapPrimaryDomainSid@@3PEAXEA, rax; void * LsapPrimaryDomainSid
0x1800f1d7e  test    rax, rax
0x1800f1d81  jz      loc_1800F1BDE
0x1800f1d87  mov     r8, [rbp+arg_8]
0x1800f1d8b  mov     rdx, rax; DestinationSid
0x1800f1d8e  mov     ecx, ebx; DestinationSidLength
0x1800f1d90  mov     r8, [r8+10h]; SourceSid
0x1800f1d94  call    cs:__imp_RtlCopySid
0x1800f1d9b  nop     dword ptr [rax+rax+00h]
0x1800f1da0  mov     rdx, [rbp+arg_8]
0x1800f1da4  lea     rcx, ?LsapPrimaryDomainName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsapPrimaryDomainName
0x1800f1dab  call    LsapDuplicateString
0x1800f1db0  mov     ebx, eax
0x1800f1db2  test    eax, eax
0x1800f1db4  js      loc_1800F1EE2
0x1800f1dba  lea     rdx, ?LsapDefAppsSid@@3PEAXEA; Sid
0x1800f1dc1  lea     rcx, StringSid; "S-1-5-21-2702878673-795188819-444038987"...
0x1800f1dc8  call    cs:__imp_ConvertStringSidToSidW
0x1800f1dcf  nop     dword ptr [rax+rax+00h]
0x1800f1dd4  test    eax, eax
0x1800f1dd6  jnz     short loc_1800F1E15
0x1800f1dd8  call    cs:__imp_GetLastError
0x1800f1ddf  nop     dword ptr [rax+rax+00h]
0x1800f1de4  test    eax, eax
0x1800f1de6  jg      short loc_1800F1DFB
0x1800f1de8  call    cs:__imp_GetLastError
0x1800f1def  nop     dword ptr [rax+rax+00h]
0x1800f1df4  mov     ebx, eax
0x1800f1df6  jmp     loc_1800F1EE2
0x1800f1dfb  call    cs:__imp_GetLastError
0x1800f1e02  nop     dword ptr [rax+rax+00h]
0x1800f1e07  movzx   ebx, ax
0x1800f1e0a  or      ebx, 0C0070000h
0x1800f1e10  jmp     loc_1800F1EE2
0x1800f1e15  cmp     cs:LsapProductType, 2
0x1800f1e1c  jnz     loc_1800F1ECE
0x1800f1e22  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; struct _LSAP_DB_HANDLE *
0x1800f1e29  lea     r8, [rbp+arg_10]
0x1800f1e2d  mov     edx, edi; enum _POLICY_INFORMATION_CLASS
0x1800f1e2f  call    LsarQueryInformationPolicy
0x1800f1e34  mov     ebx, eax
0x1800f1e36  test    eax, eax
0x1800f1e38  js      loc_1800F1EE2
0x1800f1e3e  mov     rdx, [rbp+arg_10]
0x1800f1e42  test    rdx, rdx
0x1800f1e45  jz      loc_1800F1EF5
0x1800f1e4b  mov     rcx, [rdx+10h]; Sid
0x1800f1e4f  test    rcx, rcx
0x1800f1e52  jz      loc_1800F1EE2
0x1800f1e58  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1e5f  nop     dword ptr [rax+rax+00h]
0x1800f1e64  mov     cl, [rax]
0x1800f1e66  inc     cl
0x1800f1e68  movzx   ecx, cl; SubAuthorityCount
0x1800f1e6b  mov     cs:?LsapDSRMDomainSubCount@@3EA, cl; uchar LsapDSRMDomainSubCount
0x1800f1e71  call    cs:__imp_RtlLengthRequiredSid
0x1800f1e78  nop     dword ptr [rax+rax+00h]
0x1800f1e7d  mov     ecx, eax
0x1800f1e7f  mov     cs:?LsapDSRMDomainMemberSidLength@@3KA, ecx; ulong LsapDSRMDomainMemberSidLength
0x1800f1e85  call    LsapAllocate
0x1800f1e8a  mov     cs:?LsapDSRMAccountDomainSid@@3PEAXEA, rax; void * LsapDSRMAccountDomainSid
0x1800f1e91  test    rax, rax
0x1800f1e94  jz      loc_1800F1BDE
0x1800f1e9a  mov     r8, [rbp+arg_10]
0x1800f1e9e  mov     rdx, rax; DestinationSid
0x1800f1ea1  mov     ecx, cs:?LsapDSRMDomainMemberSidLength@@3KA; DestinationSidLength
0x1800f1ea7  mov     r8, [r8+10h]; SourceSid
0x1800f1eab  call    cs:__imp_RtlCopySid
0x1800f1eb2  nop     dword ptr [rax+rax+00h]
0x1800f1eb7  mov     rcx, cs:?LsapDSRMAccountDomainSid@@3PEAXEA; Sid
0x1800f1ebe  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f1ec5  nop     dword ptr [rax+rax+00h]
0x1800f1eca  inc     byte ptr [rax]
0x1800f1ecc  jmp     short loc_1800F1EE2
0x1800f1ece  mov     cs:?LsapDSRMDomainMemberSidLength@@3KA, esi; ulong LsapDSRMDomainMemberSidLength
0x1800f1ed4  mov     cs:?LsapDSRMDomainSubCount@@3EA, sil; uchar LsapDSRMDomainSubCount
0x1800f1edb  mov     cs:?LsapDSRMAccountDomainSid@@3PEAXEA, rsi; void * LsapDSRMAccountDomainSid
0x1800f1ee2  mov     rdx, [rbp+arg_10]
0x1800f1ee6  test    rdx, rdx
0x1800f1ee9  jz      short loc_1800F1EF5
0x1800f1eeb  mov     ecx, 5
0x1800f1ef0  call    LsaIFree_LSAPR_POLICY_INFORMATION
0x1800f1ef5  mov     rdx, [rbp+arg_18]
0x1800f1ef9  test    rdx, rdx
0x1800f1efc  jz      short loc_1800F1F08
0x1800f1efe  mov     ecx, 5
0x1800f1f03  call    LsaIFree_LSAPR_POLICY_INFORMATION
0x1800f1f08  mov     rdi, [rbp+hMem]
0x1800f1f0c  test    rdi, rdi
0x1800f1f0f  jz      short loc_1800F1F28
0x1800f1f11  mov     rcx, rdi; struct _LSAPR_POLICY_ACCOUNT_DOM_INFO *
0x1800f1f14  call    ?_fgs__LSAPR_POLICY_ACCOUNT_DOM_INFO@@YAXPEAU_LSAPR_POLICY_ACCOUNT_DOM_INFO@@@Z; _fgs__LSAPR_POLICY_ACCOUNT_DOM_INFO(_LSAPR_POLICY_ACCOUNT_DOM_INFO *)
0x1800f1f19  mov     rcx, rdi; hMem
0x1800f1f1c  call    cs:__imp_LocalFree
0x1800f1f23  nop     dword ptr [rax+rax+00h]
0x1800f1f28  mov     rdx, [rbp+arg_8]
0x1800f1f2c  test    rdx, rdx
0x1800f1f2f  jz      short loc_1800F1F3B
0x1800f1f31  mov     ecx, 3
0x1800f1f36  call    LsaIFree_LSAPR_POLICY_INFORMATION
0x1800f1f3b  test    ebx, ebx
0x1800f1f3d  js      short loc_1800F1F4E
0x1800f1f3f  mov     cs:?LsapNullSidAuthority@@3U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority, 1; _SID_IDENTIFIER_AUTHORITY LsapNullSidAuthority ...
0x1800f1f49  jmp     loc_1800F1FEC
0x1800f1f4e  mov     rcx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; struct _RTL_BALANCED_NODE *
0x1800f1f55  test    rcx, rcx
0x1800f1f58  jz      short loc_1800F1F66
0x1800f1f5a  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f1f5f  mov     cs:?LsapAccountDomainMemberSid@@3PEAXEA, rsi; void * LsapAccountDomainMemberSid
0x1800f1f66  mov     rcx, cs:?LsapLocalAccountDomainMemberSid@@3PEAXEA; struct _RTL_BALANCED_NODE *
0x1800f1f6d  test    rcx, rcx
0x1800f1f70  jz      short loc_1800F1F7E
0x1800f1f72  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f1f77  mov     cs:?LsapLocalAccountDomainMemberSid@@3PEAXEA, rsi; void * LsapLocalAccountDomainMemberSid
0x1800f1f7e  mov     rcx, cs:?LsapBuiltinDomainMemberSid@@3PEAXEA; struct _RTL_BALANCED_NODE *
0x1800f1f85  test    rcx, rcx
0x1800f1f88  jz      short loc_1800F1F96
0x1800f1f8a  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f1f8f  mov     cs:?LsapBuiltinDomainMemberSid@@3PEAXEA, rsi; void * LsapBuiltinDomainMemberSid
0x1800f1f96  mov     rcx, cs:?LsapPrimaryDomainSid@@3PEAXEA; struct _RTL_BALANCED_NODE *
0x1800f1f9d  test    rcx, rcx
0x1800f1fa0  jz      short loc_1800F1FAE
0x1800f1fa2  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f1fa7  mov     cs:?LsapPrimaryDomainSid@@3PEAXEA, rsi; void * LsapPrimaryDomainSid
0x1800f1fae  cmp     cs:qword_18019ECB0, rsi
0x1800f1fb5  jz      short loc_1800F1FCD
0x1800f1fb7  lea     rcx, ?LsapPrimaryDomainName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsapPrimaryDomainName
0x1800f1fbe  call    LsapFreeString
0x1800f1fc3  xorps   xmm0, xmm0
0x1800f1fc6  movups  xmmword ptr cs:?LsapPrimaryDomainName@@3U_UNICODE_STRING@@A, xmm0; _UNICODE_STRING LsapPrimaryDomainName
0x1800f1fcd  mov     rcx, cs:?LsapDefAppsSid@@3PEAXEA; hMem
0x1800f1fd4  test    rcx, rcx
0x1800f1fd7  jz      short loc_1800F1FEC
0x1800f1fd9  call    cs:__imp_LocalFree
0x1800f1fe0  nop     dword ptr [rax+rax+00h]
0x1800f1fe5  mov     cs:?LsapDefAppsSid@@3PEAXEA, rsi; void * LsapDefAppsSid
0x1800f1fec  mov     eax, ebx
0x1800f1fee  mov     rbx, [rsp+30h+arg_0]
0x1800f1ff3  add     rsp, 30h
0x1800f1ff7  pop     rdi
0x1800f1ff8  pop     rsi
0x1800f1ff9  pop     rbp
0x1800f1ffa  retn
```
