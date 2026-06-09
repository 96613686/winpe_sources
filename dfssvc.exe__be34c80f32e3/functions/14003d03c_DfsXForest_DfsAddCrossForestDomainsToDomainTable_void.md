# DfsXForest::DfsAddCrossForestDomainsToDomainTable(void)

- ea: `0x14003d03c`
- end: `0x14003d1e5`
- name: `?DfsAddCrossForestDomainsToDomainTable@DfsXForest@@AEAAKXZ`
- size: `425`
- prototype: `unsigned int __fastcall(DfsXForest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003d500`

## callees

- `0x140005b90`
- `0x14003d03c`
- `0x14003d1ec`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14003d12e`
- `ntdll!RtlInitUnicodeString` at `0x14003d12e`
- `ntdll!RtlNtStatusToDosError` at `0x14003d158`
- `ntdll!RtlNtStatusToDosError` at `0x14003d158`
- `logoncli!DsEnumerateDomainTrustsW` at `0x14003d106`
- `logoncli!DsEnumerateDomainTrustsW` at `0x14003d106`
- `logoncli!DsGetDcNameW` at `0x14003d088`
- `logoncli!DsGetDcNameW` at `0x14003d088`
- `netutils!NetApiBufferFree` at `0x14003d1bd`
- `netutils!NetApiBufferFree` at `0x14003d1cd`
- `netutils!NetApiBufferFree` at `0x14003d1bd`
- `netutils!NetApiBufferFree` at `0x14003d1cd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14003d1ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14003d1ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x14003d14a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x14003d14a`

## pseudocode

```c
__int64 __fastcall DfsXForest::DfsAddCrossForestDomainsToDomainTable(DfsXForest *this)
{
  const WCHAR *v1; // rdx
  ULONG v2; // ebx
  DWORD DcNameW; // edi
  NTSTATUS v5; // eax
  ULONG v6; // ecx
  struct _DS_DOMAIN_TRUSTSW *v7; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  ULONG DomainCount; // [rsp+A0h] [rbp+28h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+A8h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+B0h] [rbp+38h] BYREF
  PDS_DOMAIN_TRUSTSW Domains; // [rsp+B8h] [rbp+40h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 1);
  v2 = 0;
  DomainCount = 0;
  Domains = 0;
  DomainControllerInfo = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DcNameW = DsGetDcNameW(0, v1, 0, 0, 0x11u, &DomainControllerInfo);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (DcNameW != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_SD(
      *((_QWORD *)pWppControl + 2),
      16,
      (unsigned int)WPP_5e4bfb9fc74e396487028932ae6e6e2a_Traceguids,
      *((_QWORD *)this + 1),
      DcNameW);
  }
  if ( !DcNameW )
  {
    DcNameW = DsEnumerateDomainTrustsW(DomainControllerInfo->DomainControllerName, 0x20u, &Domains, &DomainCount);
    if ( !DcNameW )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, DomainControllerInfo->DomainControllerName);
      v5 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 1u, &PolicyHandle);
      DcNameW = RtlNtStatusToDosError(v5);
      if ( !DcNameW )
      {
        v6 = DomainCount;
        if ( DomainCount )
        {
          do
          {
            v7 = &Domains[v2];
            if ( (v7->Flags & 1) == 0 && v7->TrustType != 3 && (v7->TrustAttributes & 8) != 0 )
            {
              DfsXForest::DfsAddForestDomainsToDomainTable(this, PolicyHandle, v7->DnsDomainName);
              v6 = DomainCount;
            }
            ++v2;
          }
          while ( v2 < v6 );
        }
        LsaClose(PolicyHandle);
      }
      NetApiBufferFree(Domains);
    }
    NetApiBufferFree(DomainControllerInfo);
  }
  return DcNameW;
}

```

## disassembly

```asm
0x14003d03c  push    rbp
0x14003d03e  push    rbx
0x14003d03f  push    rsi
0x14003d040  push    rdi
0x14003d041  mov     rbp, rsp
0x14003d044  sub     rsp, 78h
0x14003d048  mov     rdx, [rcx+8]; DomainName
0x14003d04c  lea     rax, [rbp+arg_8]
0x14003d050  xor     ebx, ebx
0x14003d052  mov     [rsp+78h+DomainControllerInfo], rax; DomainControllerInfo
0x14003d057  xorps   xmm0, xmm0
0x14003d05a  mov     [rsp+78h+Flags], 11h; Flags
0x14003d062  mov     rsi, rcx
0x14003d065  mov     [rbp+DomainCount], ebx
0x14003d068  xor     r9d, r9d; SiteName
0x14003d06b  mov     [rbp+Domains], rbx
0x14003d06f  xor     r8d, r8d; DomainGuid
0x14003d072  mov     [rbp+arg_8], rbx
0x14003d076  xor     ecx, ecx; ComputerName
0x14003d078  mov     [rbp+PolicyHandle], rbx
0x14003d07c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003d080  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003d084  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003d088  call    cs:__imp_DsGetDcNameW
0x14003d08f  nop     dword ptr [rax+rax+00h]
0x14003d094  mov     edi, eax
0x14003d096  lea     rax, WPP_GLOBAL_Control
0x14003d09d  cmp     cs:WPP_GLOBAL_Control, rax
0x14003d0a4  jz      short loc_14003D0EC
0x14003d0a6  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003d0ad  test    r10, r10
0x14003d0b0  jz      short loc_14003D0EC
0x14003d0b2  mov     ecx, edi
0x14003d0b4  lea     eax, [rbx+20h]
0x14003d0b7  neg     ecx
0x14003d0b9  sbb     edx, edx
0x14003d0bb  and     edx, 0FFFFFFECh
0x14003d0be  add     edx, 1Fh
0x14003d0c1  bts     eax, edx
0x14003d0c4  test    [r10+1Ch], eax
0x14003d0c8  jz      short loc_14003D0EC
0x14003d0ca  cmp     byte ptr [r10+19h], 2
0x14003d0cf  jb      short loc_14003D0EC
0x14003d0d1  mov     r9, [rsi+8]
0x14003d0d5  lea     edx, [rbx+10h]
0x14003d0d8  mov     rcx, [r10+10h]
0x14003d0dc  lea     r8, WPP_5e4bfb9fc74e396487028932ae6e6e2a_Traceguids
0x14003d0e3  mov     [rsp+78h+Flags], edi
0x14003d0e7  call    WPP_SF_SD
0x14003d0ec  test    edi, edi
0x14003d0ee  jnz     loc_14003D1D9
0x14003d0f4  mov     rcx, [rbp+arg_8]
0x14003d0f8  lea     r9, [rbp+DomainCount]; DomainCount
0x14003d0fc  lea     r8, [rbp+Domains]; Domains
0x14003d100  lea     edx, [rdi+20h]; Flags
0x14003d103  mov     rcx, [rcx]; ServerName
0x14003d106  call    cs:__imp_DsEnumerateDomainTrustsW
0x14003d10d  nop     dword ptr [rax+rax+00h]
0x14003d112  mov     edi, eax
0x14003d114  test    eax, eax
0x14003d116  jnz     loc_14003D1C9
0x14003d11c  mov     rdx, [rbp+arg_8]
0x14003d120  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003d124  xorps   xmm0, xmm0
0x14003d127  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14003d12b  mov     rdx, [rdx]; SourceString
0x14003d12e  call    cs:__imp_RtlInitUnicodeString
0x14003d135  nop     dword ptr [rax+rax+00h]
0x14003d13a  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x14003d13e  lea     r8d, [rdi+1]; DesiredAccess
0x14003d142  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x14003d146  lea     rcx, [rbp+DestinationString]; SystemName
0x14003d14a  call    cs:__imp_LsaOpenPolicy
0x14003d151  nop     dword ptr [rax+rax+00h]
0x14003d156  mov     ecx, eax; Status
0x14003d158  call    cs:__imp_RtlNtStatusToDosError
0x14003d15f  nop     dword ptr [rax+rax+00h]
0x14003d164  mov     edi, eax
0x14003d166  test    eax, eax
0x14003d168  jnz     short loc_14003D1B9
0x14003d16a  mov     ecx, [rbp+DomainCount]
0x14003d16d  test    ecx, ecx
0x14003d16f  jz      short loc_14003D1A9
0x14003d171  mov     eax, ebx
0x14003d173  imul    r8, rax, 38h ; '8'
0x14003d177  add     r8, [rbp+Domains]
0x14003d17b  test    byte ptr [r8+10h], 1
0x14003d180  jnz     short loc_14003D1A3
0x14003d182  cmp     dword ptr [r8+18h], 3
0x14003d187  jz      short loc_14003D1A3
0x14003d189  test    byte ptr [r8+1Ch], 8
0x14003d18e  jz      short loc_14003D1A3
0x14003d190  mov     r8, [r8+8]; SourceString
0x14003d194  mov     rcx, rsi; this
0x14003d197  mov     rdx, [rbp+PolicyHandle]; PolicyHandle
0x14003d19b  call    ?DfsAddForestDomainsToDomainTable@DfsXForest@@AEAAKPEAXPEAG@Z; DfsXForest::DfsAddForestDomainsToDomainTable(void *,ushort *)
0x14003d1a0  mov     ecx, [rbp+DomainCount]
0x14003d1a3  inc     ebx
0x14003d1a5  cmp     ebx, ecx
0x14003d1a7  jb      short loc_14003D171
0x14003d1a9  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x14003d1ad  call    cs:__imp_LsaClose
0x14003d1b4  nop     dword ptr [rax+rax+00h]
0x14003d1b9  mov     rcx, [rbp+Domains]; Buffer
0x14003d1bd  call    cs:__imp_NetApiBufferFree
0x14003d1c4  nop     dword ptr [rax+rax+00h]
0x14003d1c9  mov     rcx, [rbp+arg_8]; Buffer
0x14003d1cd  call    cs:__imp_NetApiBufferFree
0x14003d1d4  nop     dword ptr [rax+rax+00h]
0x14003d1d9  mov     eax, edi
0x14003d1db  add     rsp, 78h
0x14003d1df  pop     rdi
0x14003d1e0  pop     rsi
0x14003d1e1  pop     rbx
0x14003d1e2  pop     rbp
0x14003d1e3  retn
```
