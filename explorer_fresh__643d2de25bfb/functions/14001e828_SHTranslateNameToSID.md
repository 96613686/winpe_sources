# SHTranslateNameToSID

- ea: `0x14001e828`
- end: `0x14001e9b4`
- name: `SHTranslateNameToSID`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001e6a8`

## callees

- `0x14001c330`
- `0x14001e828`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001e8aa`
- `ntdll!RtlInitUnicodeString` at `0x14001e8aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001e957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001e957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001e913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001e913`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001e934`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001e934`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001e903`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001e903`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x14001e8db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x14001e8db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14001e995`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14001e995`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14001e975`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14001e985`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14001e975`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14001e985`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x14001e86d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x14001e86d`

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
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
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
0x14001e828  mov     [rsp-18h+arg_18], rbx
0x14001e82d  mov     [rsp-18h+arg_0], rcx
0x14001e832  push    rbp
0x14001e833  push    rsi
0x14001e834  push    rdi
0x14001e835  mov     rbp, rsp
0x14001e838  sub     rsp, 70h
0x14001e83c  xorps   xmm0, xmm0
0x14001e83f  mov     qword ptr [rdx], 0
0x14001e846  mov     rsi, rdx
0x14001e849  mov     [rbp+PolicyHandle], 0
0x14001e851  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x14001e855  mov     r8d, 800h; DesiredAccess
0x14001e85b  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x14001e85f  xor     ecx, ecx; SystemName
0x14001e861  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001e865  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001e869  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001e86d  call    cs:__imp_LsaOpenPolicy
0x14001e874  nop     dword ptr [rax+rax+00h]
0x14001e879  mov     ebx, eax
0x14001e87b  mov     edi, 10000000h
0x14001e880  or      ebx, edi
0x14001e882  jl      loc_14001E9A1
0x14001e888  xorps   xmm0, xmm0
0x14001e88b  mov     [rbp+arg_10], 0
0x14001e893  lea     rdx, SourceString; "CDFAccount"
0x14001e89a  mov     [rbp+arg_0], 0
0x14001e8a2  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001e8a6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001e8aa  call    cs:__imp_RtlInitUnicodeString
0x14001e8b1  nop     dword ptr [rax+rax+00h]
0x14001e8b6  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x14001e8ba  lea     rax, [rbp+arg_0]
0x14001e8be  mov     [rsp+70h+Sids], rax; Sids
0x14001e8c3  lea     r9, [rbp+DestinationString]; Names
0x14001e8c7  lea     rax, [rbp+arg_10]
0x14001e8cb  mov     edx, 80000000h; Flags
0x14001e8d0  mov     r8d, 1; Count
0x14001e8d6  mov     [rsp+70h+ReferencedDomains], rax; ReferencedDomains
0x14001e8db  call    cs:__imp_LsaLookupNames2
0x14001e8e2  nop     dword ptr [rax+rax+00h]
0x14001e8e7  mov     ebx, eax
0x14001e8e9  or      ebx, edi
0x14001e8eb  jl      loc_14001E971
0x14001e8f1  mov     rcx, [rbp+arg_0]
0x14001e8f5  mov     eax, [rcx]
0x14001e8f7  sub     eax, 7
0x14001e8fa  cmp     eax, 1
0x14001e8fd  jbe     short loc_14001E96C
0x14001e8ff  mov     rcx, [rcx+8]; pSid
0x14001e903  call    cs:__imp_GetLengthSid
0x14001e90a  nop     dword ptr [rax+rax+00h]
0x14001e90f  mov     ecx, eax; cb
0x14001e911  mov     ebx, eax
0x14001e913  call    cs:__imp_CoTaskMemAlloc
0x14001e91a  nop     dword ptr [rax+rax+00h]
0x14001e91f  mov     rdi, rax
0x14001e922  test    rax, rax
0x14001e925  jz      short loc_14001E965
0x14001e927  mov     r8, [rbp+arg_0]
0x14001e92b  mov     rdx, rax; pDestinationSid
0x14001e92e  mov     ecx, ebx; nDestinationSidLength
0x14001e930  mov     r8, [r8+8]; pSourceSid
0x14001e934  call    cs:__imp_CopySid
0x14001e93b  nop     dword ptr [rax+rax+00h]
0x14001e940  test    eax, eax
0x14001e942  jz      short loc_14001E94D
0x14001e944  mov     [rsi], rdi
0x14001e947  xor     edi, edi
0x14001e949  xor     ebx, ebx
0x14001e94b  jmp     short loc_14001E954
0x14001e94d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001e952  mov     ebx, eax
0x14001e954  mov     rcx, rdi; pv
0x14001e957  call    cs:__imp_CoTaskMemFree
0x14001e95e  nop     dword ptr [rax+rax+00h]
0x14001e963  jmp     short loc_14001E971
0x14001e965  mov     ebx, 8007000Eh
0x14001e96a  jmp     short loc_14001E971
0x14001e96c  mov     ebx, 80004005h
0x14001e971  mov     rcx, [rbp+arg_10]; Buffer
0x14001e975  call    cs:__imp_LsaFreeMemory
0x14001e97c  nop     dword ptr [rax+rax+00h]
0x14001e981  mov     rcx, [rbp+arg_0]; Buffer
0x14001e985  call    cs:__imp_LsaFreeMemory
0x14001e98c  nop     dword ptr [rax+rax+00h]
0x14001e991  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x14001e995  call    cs:__imp_LsaClose
0x14001e99c  nop     dword ptr [rax+rax+00h]
0x14001e9a1  mov     eax, ebx
0x14001e9a3  mov     rbx, [rsp+70h+arg_18]
0x14001e9ab  add     rsp, 70h
0x14001e9af  pop     rdi
0x14001e9b0  pop     rsi
0x14001e9b1  pop     rbp
0x14001e9b2  retn
```
