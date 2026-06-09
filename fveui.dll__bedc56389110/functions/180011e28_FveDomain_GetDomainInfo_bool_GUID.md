# FveDomain::GetDomainInfo(bool *,_GUID *)

- ea: `0x180011e28`
- end: `0x180011f42`
- name: `?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(bool *, struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007360`
- `0x180017c9c`
- `0x180027800`

## callees

- `0x1800037a0`
- `0x18000ff64`
- `0x180011e28`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180011f1e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180011f1e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180011f2d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180011f2d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180011eca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180011eca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180011e73`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180011e73`

## pseudocode

```c
__int64 __fastcall FveDomain::GetDomainInfo(bool *a1, struct _GUID *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  struct _GUID *v8; // rcx
  int v9; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp+38h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ObjectAttributes.Length = 48;
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v4 < 0 )
  {
    v5 = FromNtStatus(v4);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_6;
    v7 = 10;
LABEL_5:
    WPP_SF_d(v6[2], v7, WPP_251a3021e63d3c6493de6f296bf5551c_Traceguids, v5);
LABEL_6:
    v8 = (struct _GUID *)Buffer;
    goto LABEL_13;
  }
  v9 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v9 < 0 )
  {
    v5 = FromNtStatus(v9);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_6;
    v7 = 11;
    goto LABEL_5;
  }
  v8 = (struct _GUID *)Buffer;
  v5 = 0;
  *a1 = *((_QWORD *)Buffer + 8) != 0;
  if ( a2 )
    *a2 = v8[3];
LABEL_13:
  if ( v8 )
    LsaFreeMemory(v8);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x180011e28  mov     [rsp-18h+arg_0], rbx
0x180011e2d  push    rbp
0x180011e2e  push    rsi
0x180011e2f  push    rdi
0x180011e30  mov     rbp, rsp
0x180011e33  sub     rsp, 50h
0x180011e37  xorps   xmm0, xmm0
0x180011e3a  mov     [rbp+PolicyHandle], 0
0x180011e42  mov     rdi, rdx
0x180011e45  mov     [rbp+Buffer], 0
0x180011e4d  mov     rsi, rcx
0x180011e50  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180011e54  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180011e58  mov     r8d, 1; DesiredAccess
0x180011e5e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180011e65  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180011e69  xor     ecx, ecx; SystemName
0x180011e6b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180011e6f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180011e73  call    cs:__imp_LsaOpenPolicy
0x180011e79  test    eax, eax
0x180011e7b  jns     short loc_180011EBD
0x180011e7d  mov     ecx, eax; int
0x180011e7f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180011e84  mov     ebx, eax
0x180011e86  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e8d  lea     rax, WPP_GLOBAL_Control
0x180011e94  cmp     rcx, rax
0x180011e97  jz      short loc_180011EB7
0x180011e99  test    byte ptr [rcx+1Ch], 40h
0x180011e9d  jz      short loc_180011EB7
0x180011e9f  mov     edx, 0Ah
0x180011ea4  mov     rcx, [rcx+10h]
0x180011ea8  lea     r8, WPP_251a3021e63d3c6493de6f296bf5551c_Traceguids
0x180011eaf  mov     r9d, ebx
0x180011eb2  call    WPP_SF_d
0x180011eb7  mov     rcx, [rbp+Buffer]
0x180011ebb  jmp     short loc_180011F19
0x180011ebd  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180011ec1  lea     r8, [rbp+Buffer]; Buffer
0x180011ec5  mov     edx, 0Ch; InformationClass
0x180011eca  call    cs:__imp_LsaQueryInformationPolicy
0x180011ed0  test    eax, eax
0x180011ed2  jns     short loc_180011EFD
0x180011ed4  mov     ecx, eax; int
0x180011ed6  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180011edb  mov     ebx, eax
0x180011edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ee4  lea     rax, WPP_GLOBAL_Control
0x180011eeb  cmp     rcx, rax
0x180011eee  jz      short loc_180011EB7
0x180011ef0  test    byte ptr [rcx+1Ch], 40h
0x180011ef4  jz      short loc_180011EB7
0x180011ef6  mov     edx, 0Bh
0x180011efb  jmp     short loc_180011EA4
0x180011efd  mov     rcx, [rbp+Buffer]; Buffer
0x180011f01  xor     ebx, ebx
0x180011f03  cmp     [rcx+40h], rbx
0x180011f07  setnz   al
0x180011f0a  mov     [rsi], al
0x180011f0c  test    rdi, rdi
0x180011f0f  jz      short loc_180011F19
0x180011f11  movups  xmm0, xmmword ptr [rcx+30h]
0x180011f15  movdqu  xmmword ptr [rdi], xmm0
0x180011f19  test    rcx, rcx
0x180011f1c  jz      short loc_180011F24
0x180011f1e  call    cs:__imp_LsaFreeMemory
0x180011f24  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180011f28  test    rcx, rcx
0x180011f2b  jz      short loc_180011F33
0x180011f2d  call    cs:__imp_LsaClose
0x180011f33  mov     eax, ebx
0x180011f35  mov     rbx, [rsp+50h+arg_0]
0x180011f3a  add     rsp, 50h
0x180011f3e  pop     rdi
0x180011f3f  pop     rsi
0x180011f40  pop     rbp
0x180011f41  retn
```
