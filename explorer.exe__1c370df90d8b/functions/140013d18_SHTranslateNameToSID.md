# SHTranslateNameToSID

- ea: `0x140013d18`
- end: `0x140013e63`
- name: `SHTranslateNameToSID`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140013bb4`

## callees

- `0x140013d18`
- `0x140016b10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140013d94`
- `ntdll!RtlInitUnicodeString` at `0x140013d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140013de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140013de7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140013ddd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140013ddd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140013e02`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140013e02`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x140013dbf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x140013dbf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140013e4b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140013e4b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140013e37`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140013e41`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140013e37`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140013e41`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x140013d5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x140013d5d`

## pseudocode

```c
__int64 __fastcall SHTranslateNameToSID(struct _LSA_TRANSLATED_SID2 *a1, _QWORD *a2)
{
  NTSTATUS v3; // eax
  unsigned int Error; // ebx
  NTSTATUS v5; // eax
  DWORD LengthSid; // ebx
  void *v7; // rax
  void *v8; // rdi
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+90h] [rbp+20h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+28h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+A0h] [rbp+30h] BYREF

  Sids = a1;
  *a2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  Error = v3 | 0x10000000;
  if ( v3 >= 0 )
  {
    ReferencedDomains = 0;
    Sids = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"CDFAccount");
    v5 = LsaLookupNames2(
           PolicyHandle,
           0x80000000,
           1u,
           (PLSA_UNICODE_STRING)&DestinationString,
           &ReferencedDomains,
           &Sids);
    Error = v5 | 0x10000000;
    if ( v5 >= 0 )
    {
      if ( (unsigned int)(Sids->Use - 7) <= 1 )
      {
        Error = -2147467259;
      }
      else
      {
        LengthSid = GetLengthSid(Sids->Sid);
        v7 = CoTaskMemAlloc(LengthSid);
        v8 = v7;
        if ( v7 )
        {
          if ( CopySid(LengthSid, v7, Sids->Sid) )
          {
            *a2 = v8;
            v8 = 0;
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
          CoTaskMemFree(v8);
        }
        else
        {
          Error = -2147024882;
        }
      }
    }
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Sids);
    LsaClose(PolicyHandle);
  }
  return Error;
}

```

## disassembly

```asm
0x140013d18  mov     [rsp-18h+arg_18], rbx
0x140013d1d  mov     [rsp-18h+arg_0], rcx
0x140013d22  push    rbp
0x140013d23  push    rsi
0x140013d24  push    rdi
0x140013d25  mov     rbp, rsp
0x140013d28  sub     rsp, 70h
0x140013d2c  xorps   xmm0, xmm0
0x140013d2f  mov     qword ptr [rdx], 0
0x140013d36  mov     rsi, rdx
0x140013d39  mov     [rbp+PolicyHandle], 0
0x140013d41  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x140013d45  mov     r8d, 800h; DesiredAccess
0x140013d4b  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x140013d4f  xor     ecx, ecx; SystemName
0x140013d51  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140013d55  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140013d59  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013d5d  call    cs:__imp_LsaOpenPolicy
0x140013d63  mov     ebx, eax
0x140013d65  mov     edi, 10000000h
0x140013d6a  or      ebx, edi
0x140013d6c  jl      loc_140013E51
0x140013d72  xorps   xmm0, xmm0
0x140013d75  mov     [rbp+arg_10], 0
0x140013d7d  lea     rdx, SourceString; "CDFAccount"
0x140013d84  mov     [rbp+arg_0], 0
0x140013d8c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140013d90  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140013d94  call    cs:__imp_RtlInitUnicodeString
0x140013d9a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x140013d9e  lea     rax, [rbp+arg_0]
0x140013da2  mov     [rsp+70h+Sids], rax; Sids
0x140013da7  lea     r9, [rbp+DestinationString]; Names
0x140013dab  lea     rax, [rbp+arg_10]
0x140013daf  mov     edx, 80000000h; Flags
0x140013db4  mov     r8d, 1; Count
0x140013dba  mov     [rsp+70h+ReferencedDomains], rax; ReferencedDomains
0x140013dbf  call    cs:__imp_LsaLookupNames2
0x140013dc5  mov     ebx, eax
0x140013dc7  or      ebx, edi
0x140013dc9  jl      short loc_140013E33
0x140013dcb  mov     rcx, [rbp+arg_0]
0x140013dcf  mov     eax, [rcx]
0x140013dd1  sub     eax, 7
0x140013dd4  cmp     eax, 1
0x140013dd7  jbe     short loc_140013E2E
0x140013dd9  mov     rcx, [rcx+8]; pSid
0x140013ddd  call    cs:__imp_GetLengthSid
0x140013de3  mov     ecx, eax; cb
0x140013de5  mov     ebx, eax
0x140013de7  call    cs:__imp_CoTaskMemAlloc
0x140013ded  mov     rdi, rax
0x140013df0  test    rax, rax
0x140013df3  jz      short loc_140013E27
0x140013df5  mov     r8, [rbp+arg_0]
0x140013df9  mov     rdx, rax; pDestinationSid
0x140013dfc  mov     ecx, ebx; nDestinationSidLength
0x140013dfe  mov     r8, [r8+8]; pSourceSid
0x140013e02  call    cs:__imp_CopySid
0x140013e08  test    eax, eax
0x140013e0a  jz      short loc_140013E15
0x140013e0c  mov     [rsi], rdi
0x140013e0f  xor     edi, edi
0x140013e11  xor     ebx, ebx
0x140013e13  jmp     short loc_140013E1C
0x140013e15  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140013e1a  mov     ebx, eax
0x140013e1c  mov     rcx, rdi; pv
0x140013e1f  call    cs:__imp_CoTaskMemFree
0x140013e25  jmp     short loc_140013E33
0x140013e27  mov     ebx, 8007000Eh
0x140013e2c  jmp     short loc_140013E33
0x140013e2e  mov     ebx, 80004005h
0x140013e33  mov     rcx, [rbp+arg_10]; Buffer
0x140013e37  call    cs:__imp_LsaFreeMemory
0x140013e3d  mov     rcx, [rbp+arg_0]; Buffer
0x140013e41  call    cs:__imp_LsaFreeMemory
0x140013e47  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x140013e4b  call    cs:__imp_LsaClose
0x140013e51  mov     eax, ebx
0x140013e53  mov     rbx, [rsp+70h+arg_18]
0x140013e5b  add     rsp, 70h
0x140013e5f  pop     rdi
0x140013e60  pop     rsi
0x140013e61  pop     rbp
0x140013e62  retn
```
