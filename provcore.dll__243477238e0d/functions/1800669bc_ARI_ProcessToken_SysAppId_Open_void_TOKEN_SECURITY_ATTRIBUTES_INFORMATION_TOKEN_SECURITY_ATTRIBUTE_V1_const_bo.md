# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800669bc`
- end: `0x180066b0c`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `int __fastcall(void *token, _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **attributes, const _TOKEN_SECURITY_ATTRIBUTE_V1 **sysAppId, bool *token)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006675c`

## callees

- `0x1800032dc`
- `0x180066110`
- `0x1800663e8`
- `0x1800669bc`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800669f9`
- `ntdll!NtQueryInformationToken` at `0x180066a6c`
- `ntdll!NtQueryInformationToken` at `0x1800669f9`
- `ntdll!NtQueryInformationToken` at `0x180066a6c`
- `ntdll!RtlCompareUnicodeString` at `0x180066ac8`
- `ntdll!RtlCompareUnicodeString` at `0x180066ac8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180066a16`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180066a78`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180066a16`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180066a78`
- `ntdll!RtlInitUnicodeString` at `0x180066a9c`
- `ntdll!RtlInitUnicodeString` at `0x180066a9c`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        void *token,
        _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **attributes,
        const _TOKEN_SECURITY_ATTRIBUTE_V1 **sysAppId,
        bool *a4)
{
  NTSTATUS v7; // eax
  _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v9; // rax
  _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v10; // rbx
  int v11; // ebx
  int v12; // eax
  ULONG v13; // edi
  __int64 v14; // rdi
  const _TOKEN_SECURITY_ATTRIBUTE_V1 *v15; // rsi
  _UNICODE_STRING attributeNameSYSAPPID; // [rsp+30h] [rbp-38h] BYREF
  _UNICODE_STRING attributeNamePKG; // [rsp+40h] [rbp-28h]
  unsigned int n; // [rsp+88h] [rbp+20h] BYREF
  int v19; // [rsp+8Ch] [rbp+24h]

  v19 = HIDWORD(a4);
  n = 0;
  v7 = NtQueryInformationToken(token, TokenSecurityAttributes, 0, 0, &n);
  if ( v7 == -1073741789 )
  {
    v9 = ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(n);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, n);
      v12 = NtQueryInformationToken(token, TokenSecurityAttributes, v10, n, &n);
      if ( v12 >= 0 )
      {
        if ( v10->AttributeCount )
        {
          attributeNameSYSAPPID = 0;
          RtlInitUnicodeString(&attributeNameSYSAPPID, L"WIN://SYSAPPID");
          v14 = 0;
          attributeNamePKG = 0;
          while ( (unsigned int)v14 < v10->AttributeCount )
          {
            v15 = &v10->Attribute.pAttributeV1[v14];
            if ( !RtlCompareUnicodeString(&attributeNameSYSAPPID, &v15->Name, 1u) )
            {
              *sysAppId = v15;
              *attributes = v10;
              v11 = 0;
              goto LABEL_15;
            }
            v14 = (unsigned int)(v14 + 1);
          }
        }
        v13 = 1168;
      }
      else
      {
        v13 = RtlNtStatusToDosErrorNoTeb(v12);
      }
      ARI::Free(v10);
      return v13;
    }
    else
    {
      v11 = 8;
LABEL_15:
      ARI::Free(0);
      return v11;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1800669bc  mov     rax, rsp
0x1800669bf  mov     [rax+8], rbx
0x1800669c3  mov     [rax+10h], rsi
0x1800669c7  mov     [rax+20h], r9
0x1800669cb  push    rdi
0x1800669cc  push    r14
0x1800669ce  push    r15
0x1800669d0  sub     rsp, 50h
0x1800669d4  xor     r9d, r9d; TokenInformationLength
0x1800669d7  mov     dword ptr [rax+20h], 0
0x1800669de  mov     r14, sysAppId
0x1800669e1  lea     rax, [rax+20h]
0x1800669e5  mov     r15, attributes
0x1800669e8  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800669ed  xor     r8d, r8d; TokenInformation
0x1800669f0  mov     rdi, token
0x1800669f3  lea     esi, [r9+27h]
0x1800669f7  mov     edx, esi; TokenInformationClass
0x1800669f9  call    cs:__imp_NtQueryInformationToken
0x1800669ff  cmp     eax, 0C0000023h
0x180066a04  jz      short loc_180066A21
0x180066a06  test    eax, eax
0x180066a08  jnz     short loc_180066A14
0x180066a0a  mov     eax, 54Fh
0x180066a0f  jmp     loc_180066AF8
0x180066a14  mov     ecx, eax; Status
0x180066a16  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180066a1c  jmp     loc_180066AF8
0x180066a21  mov     ecx, [rsp+68h+n]; n
0x180066a28  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180066a2d  mov     rbx, rax
0x180066a30  test    rax, rax
0x180066a33  jnz     short loc_180066A3D
0x180066a35  lea     ebx, [rax+8]
0x180066a38  jmp     loc_180066ADE
0x180066a3d  mov     r8d, [rsp+68h+n]; Size
0x180066a45  xor     edx, edx; Val
0x180066a47  mov     token, rbx; void *
0x180066a4a  call    memset_0
0x180066a4f  mov     r9d, [rsp+68h+n]; TokenInformationLength
0x180066a57  lea     rax, [rsp+68h+n]
0x180066a5f  mov     sysAppId, rbx; TokenInformation
0x180066a62  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180066a67  mov     edx, esi; TokenInformationClass
0x180066a69  mov     token, rdi; TokenHandle
0x180066a6c  call    cs:__imp_NtQueryInformationToken
0x180066a72  test    eax, eax
0x180066a74  jns     short loc_180066A82
0x180066a76  mov     ecx, eax; Status
0x180066a78  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180066a7e  mov     edi, eax
0x180066a80  jmp     short loc_180066AEE
0x180066a82  cmp     dword ptr [rbx+4], 0
0x180066a86  jbe     short loc_180066AE9
0x180066a88  xorps   xmm0, xmm0
0x180066a8b  lea     attributes, aWinSysappid; "WIN://SYSAPPID"
0x180066a92  lea     token, [rsp+68h+attributeNameSYSAPPID]; DestinationString
0x180066a97  movups  xmmword ptr [rsp+68h+attributeNameSYSAPPID.Length], xmm0
0x180066a9c  call    cs:__imp_RtlInitUnicodeString
0x180066aa2  xorps   xmm0, xmm0
0x180066aa5  xor     edi, edi
0x180066aa7  movups  xmmword ptr [rsp+68h+attributeNamePKG.Length], xmm0
0x180066aac  cmp     edi, [rbx+4]
0x180066aaf  jnb     short loc_180066AE9
0x180066ab1  mov     rax, [rbx+8]
0x180066ab5  lea     token, [rdi+rdi*4]
0x180066ab9  mov     r8b, 1; CaseInsensitive
0x180066abc  lea     rsi, [rax+token*8]
0x180066ac0  mov     attributes, rsi; String2
0x180066ac3  lea     token, [rsp+68h+attributeNameSYSAPPID]; String1
0x180066ac8  call    cs:__imp_RtlCompareUnicodeString
0x180066ace  test    eax, eax
0x180066ad0  jz      short loc_180066AD6
0x180066ad2  inc     edi
0x180066ad4  jmp     short loc_180066AAC
0x180066ad6  mov     [r14], rsi
0x180066ad9  mov     [r15], rbx
0x180066adc  xor     ebx, ebx
0x180066ade  xor     ecx, ecx; p
0x180066ae0  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180066ae5  mov     eax, ebx
0x180066ae7  jmp     short loc_180066AF8
0x180066ae9  mov     edi, 490h
0x180066aee  mov     token, rbx; p
0x180066af1  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180066af6  mov     eax, edi
0x180066af8  mov     rbx, [rsp+68h+arg_0]
0x180066afd  mov     rsi, [rsp+68h+arg_8]
0x180066b02  add     rsp, 50h
0x180066b06  pop     r15
0x180066b08  pop     r14
0x180066b0a  pop     rdi
0x180066b0b  retn
```
