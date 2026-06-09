# FveDomain::GetDomainInfo(bool *,_GUID *)

- ea: `0x1800da1a0`
- end: `0x1800da2ce`
- name: `?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(bool *, struct _GUID *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b1450`
- `0x1800b5aa0`
- `0x1800bce18`
- `0x1800cbe60`
- `0x1800ef9ac`

## callees

- `0x1800090c0`
- `0x180018b10`
- `0x1800da1a0`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800da2af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800da2af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800da29a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800da29a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800da249`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800da249`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800da1f0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800da1f0`

## pseudocode

```c
__int64 __fastcall FveDomain::GetDomainInfo(bool *a1, struct _GUID *a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp+18h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ObjectAttributes.Length = 48;
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v3 >= 0 )
  {
    v7 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v7 >= 0 )
    {
      v4 = 0;
      *a1 = *((_QWORD *)Buffer + 8) != 0;
    }
    else
    {
      v4 = FromNtStatus(v7);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v6 = 11;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = FromNtStatus(v3);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v6 = 10;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_251a3021e63d3c6493de6f296bf5551c_Traceguids, v4);
    }
  }
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v4;
}

```

## disassembly

```asm
0x1800da1a0  mov     [rsp-8+arg_0], rbx
0x1800da1a5  mov     [rsp-8+arg_18], rdi
0x1800da1aa  mov     [rsp-8+Buffer], rdx
0x1800da1af  push    rbp
0x1800da1b0  mov     rbp, rsp
0x1800da1b3  sub     rsp, 50h
0x1800da1b7  xorps   xmm0, xmm0
0x1800da1ba  mov     [rbp+PolicyHandle], 0
0x1800da1c2  mov     rdi, rcx
0x1800da1c5  mov     [rbp+Buffer], 0
0x1800da1cd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800da1d1  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800da1d5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800da1dc  mov     r8d, 1; DesiredAccess
0x1800da1e2  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800da1e6  xor     ecx, ecx; SystemName
0x1800da1e8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800da1ec  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800da1f0  call    cs:__imp_LsaOpenPolicy
0x1800da1f7  nop     dword ptr [rax+rax+00h]
0x1800da1fc  test    eax, eax
0x1800da1fe  jns     short loc_1800DA23C
0x1800da200  mov     ecx, eax; int
0x1800da202  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da207  mov     ebx, eax
0x1800da209  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da210  lea     rax, WPP_GLOBAL_Control
0x1800da217  cmp     rcx, rax
0x1800da21a  jz      short loc_1800DA291
0x1800da21c  test    byte ptr [rcx+1Ch], 40h
0x1800da220  jz      short loc_1800DA291
0x1800da222  mov     edx, 0Ah
0x1800da227  mov     rcx, [rcx+10h]
0x1800da22b  lea     r8, WPP_251a3021e63d3c6493de6f296bf5551c_Traceguids
0x1800da232  mov     r9d, ebx
0x1800da235  call    WPP_SF_d
0x1800da23a  jmp     short loc_1800DA291
0x1800da23c  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800da240  lea     r8, [rbp+Buffer]; Buffer
0x1800da244  mov     edx, 0Ch; InformationClass
0x1800da249  call    cs:__imp_LsaQueryInformationPolicy
0x1800da250  nop     dword ptr [rax+rax+00h]
0x1800da255  test    eax, eax
0x1800da257  jns     short loc_1800DA282
0x1800da259  mov     ecx, eax; int
0x1800da25b  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da260  mov     ebx, eax
0x1800da262  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da269  lea     rax, WPP_GLOBAL_Control
0x1800da270  cmp     rcx, rax
0x1800da273  jz      short loc_1800DA291
0x1800da275  test    byte ptr [rcx+1Ch], 40h
0x1800da279  jz      short loc_1800DA291
0x1800da27b  mov     edx, 0Bh
0x1800da280  jmp     short loc_1800DA227
0x1800da282  mov     rax, [rbp+Buffer]
0x1800da286  xor     ebx, ebx
0x1800da288  cmp     [rax+40h], rbx
0x1800da28c  setnz   al
0x1800da28f  mov     [rdi], al
0x1800da291  mov     rcx, [rbp+Buffer]; Buffer
0x1800da295  test    rcx, rcx
0x1800da298  jz      short loc_1800DA2A6
0x1800da29a  call    cs:__imp_LsaFreeMemory
0x1800da2a1  nop     dword ptr [rax+rax+00h]
0x1800da2a6  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800da2aa  test    rcx, rcx
0x1800da2ad  jz      short loc_1800DA2BB
0x1800da2af  call    cs:__imp_LsaClose
0x1800da2b6  nop     dword ptr [rax+rax+00h]
0x1800da2bb  mov     rdi, [rsp+50h+arg_18]
0x1800da2c0  mov     eax, ebx
0x1800da2c2  mov     rbx, [rsp+50h+arg_0]
0x1800da2c7  add     rsp, 50h
0x1800da2cb  pop     rbp
0x1800da2cc  retn
```
