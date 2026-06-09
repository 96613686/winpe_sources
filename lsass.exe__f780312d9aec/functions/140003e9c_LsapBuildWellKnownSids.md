# LsapBuildWellKnownSids

- ea: `0x140003e9c`
- end: `0x140004150`
- name: `LsapBuildWellKnownSids`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x140002b9c`

## callees

- `0x1400016c0`
- `0x140001a80`
- `0x1400020c0`
- `0x140003e9c`

## import_xrefs

- `ntdll!RtlLengthRequiredSid` at `0x140003ef3`
- `ntdll!RtlLengthRequiredSid` at `0x140003f41`
- `ntdll!RtlLengthRequiredSid` at `0x140003ff9`
- `ntdll!RtlLengthRequiredSid` at `0x140004036`
- `ntdll!RtlLengthRequiredSid` at `0x140004084`
- `ntdll!RtlLengthRequiredSid` at `0x1400040ce`
- `ntdll!RtlLengthRequiredSid` at `0x1400040ea`
- `ntdll!RtlLengthRequiredSid` at `0x140003ef3`
- `ntdll!RtlLengthRequiredSid` at `0x140003f41`
- `ntdll!RtlLengthRequiredSid` at `0x140003ff9`
- `ntdll!RtlLengthRequiredSid` at `0x140004036`
- `ntdll!RtlLengthRequiredSid` at `0x140004084`
- `ntdll!RtlLengthRequiredSid` at `0x1400040ce`
- `ntdll!RtlLengthRequiredSid` at `0x1400040ea`
- `ntdll!RtlSubAuthoritySid` at `0x140003f33`
- `ntdll!RtlSubAuthoritySid` at `0x140003fea`
- `ntdll!RtlSubAuthoritySid` at `0x140004027`
- `ntdll!RtlSubAuthoritySid` at `0x140004064`
- `ntdll!RtlSubAuthoritySid` at `0x140004075`
- `ntdll!RtlSubAuthoritySid` at `0x1400040b2`
- `ntdll!RtlSubAuthoritySid` at `0x1400040c3`
- `ntdll!RtlSubAuthoritySid` at `0x140003f33`
- `ntdll!RtlSubAuthoritySid` at `0x140003fea`
- `ntdll!RtlSubAuthoritySid` at `0x140004027`
- `ntdll!RtlSubAuthoritySid` at `0x140004064`
- `ntdll!RtlSubAuthoritySid` at `0x140004075`
- `ntdll!RtlSubAuthoritySid` at `0x1400040b2`
- `ntdll!RtlSubAuthoritySid` at `0x1400040c3`
- `ntdll!RtlInitializeSid` at `0x140003f28`
- `ntdll!RtlInitializeSid` at `0x140003fdf`
- `ntdll!RtlInitializeSid` at `0x14000401c`
- `ntdll!RtlInitializeSid` at `0x140004059`
- `ntdll!RtlInitializeSid` at `0x1400040a7`
- `ntdll!RtlInitializeSid` at `0x140003f28`
- `ntdll!RtlInitializeSid` at `0x140003fdf`
- `ntdll!RtlInitializeSid` at `0x14000401c`
- `ntdll!RtlInitializeSid` at `0x140004059`
- `ntdll!RtlInitializeSid` at `0x1400040a7`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x14000410d`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x14000410d`

## string_xrefs

- `0x140003ec8`: `lpacIdentityServices`

## pseudocode

```c
__int64 LsapBuildWellKnownSids()
{
  void *v0; // rsi
  ULONG v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  void *LsaHeap; // rax
  void *v5; // r13
  int v6; // ebx
  void *v7; // r14
  void *v8; // r12
  void *v9; // r15
  __int64 v10; // rdi
  ULONG v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  void *v14; // rax
  void *v15; // rbx
  ULONG v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  void *v20; // rax
  ULONG v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  void *v24; // rax
  ULONG v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  void *v28; // rax
  ULONG v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  ULONG v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rax
  void *v36; // [rsp+20h] [rbp-48h]
  _QWORD v37[2]; // [rsp+28h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+38h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v39; // [rsp+40h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v40; // [rsp+48h] [rbp-20h] BYREF

  v0 = 0;
  v37[0] = 2752552;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v37[1] = L"lpacIdentityServices";
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v39.Value = 0;
  *(_WORD *)&v39.Value[4] = 256;
  *(_DWORD *)v40.Value = 0;
  *(_WORD *)&v40.Value[4] = 3840;
  v1 = RtlLengthRequiredSid(1u);
  LsaHeap = (void *)LsapAllocateLsaHeap(v1, v2, v3);
  v5 = LsaHeap;
  if ( !LsaHeap )
    return (unsigned int)-1073741670;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  RtlInitializeSid(LsaHeap, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v5, 0) = 18;
  v11 = RtlLengthRequiredSid(1u);
  v14 = (void *)LsapAllocateLsaHeap(v11, v12, v13);
  v36 = v14;
  v15 = v14;
  if ( !v14 )
    goto LABEL_4;
  RtlInitializeSid(v14, &v39, 1u);
  *RtlSubAuthoritySid(v15, 0) = 0;
  v17 = RtlLengthRequiredSid(1u);
  v20 = (void *)LsapAllocateLsaHeap(v17, v18, v19);
  v0 = v20;
  if ( !v20 )
    goto LABEL_4;
  RtlInitializeSid(v20, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v0, 0) = 7;
  v21 = RtlLengthRequiredSid(2u);
  v24 = (void *)LsapAllocateLsaHeap(v21, v22, v23);
  v7 = v24;
  if ( !v24 )
    goto LABEL_4;
  RtlInitializeSid(v24, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v7, 0) = 32;
  *RtlSubAuthoritySid(v7, 1u) = 544;
  v25 = RtlLengthRequiredSid(2u);
  v28 = (void *)LsapAllocateLsaHeap(v25, v26, v27);
  v8 = v28;
  if ( !v28 )
    goto LABEL_4;
  RtlInitializeSid(v28, &v40, 2u);
  *RtlSubAuthoritySid(v8, 0) = 2;
  *RtlSubAuthoritySid(v8, 1u) = 1;
  v29 = RtlLengthRequiredSid(0xAu);
  v9 = (void *)LsapAllocateLsaHeap(v29, v30, v31);
  if ( !v9 )
    goto LABEL_4;
  v32 = RtlLengthRequiredSid(9u);
  v35 = LsapAllocateLsaHeap(v32, v33, v34);
  v10 = v35;
  if ( v35 )
  {
    v6 = RtlDeriveCapabilitySidsFromName(v37, v35, v9);
    if ( v6 >= 0 )
    {
      gLsapWorldSid = v36;
      gLsapLocalSystemSid = v5;
      gLsapAliasAdminsSid = v7;
      gLsapAnonymousSid = v0;
      gLsapAnyPackageSid = v8;
      gLsapIdentityServicesLpacSid = v9;
LABEL_16:
      LsapFreeLsaHeap(v10);
      return (unsigned int)v6;
    }
  }
  else
  {
LABEL_4:
    v6 = -1073741670;
  }
  LsapFreeLsaHeap(v5);
  if ( v36 )
    LsapFreeLsaHeap(v36);
  if ( v0 )
    LsapFreeLsaHeap(v0);
  if ( v7 )
    LsapFreeLsaHeap(v7);
  if ( v8 )
    LsapFreeLsaHeap(v8);
  if ( v9 )
    LsapFreeLsaHeap(v9);
  if ( v10 )
    goto LABEL_16;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003e9c  push    rbp
0x140003e9e  push    rbx
0x140003e9f  push    rsi
0x140003ea0  push    rdi
0x140003ea1  push    r12
0x140003ea3  push    r13
0x140003ea5  push    r14
0x140003ea7  push    r15
0x140003ea9  mov     rbp, rsp
0x140003eac  sub     rsp, 68h
0x140003eb0  mov     rax, cs:__security_cookie
0x140003eb7  xor     rax, rsp
0x140003eba  mov     [rbp+var_18], rax
0x140003ebe  xor     esi, esi
0x140003ec0  mov     [rbp+var_40], 2A0028h
0x140003ec8  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x140003ecf  mov     dword ptr [rbp+IdentifierAuthority.Value], esi
0x140003ed2  mov     [rbp+var_38], rax
0x140003ed6  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140003edc  lea     ebx, [rsi+1]
0x140003edf  mov     dword ptr [rbp+var_28.Value], esi
0x140003ee2  mov     ecx, ebx; SubAuthorityCount
0x140003ee4  mov     word ptr [rbp+var_28.Value+4], 100h
0x140003eea  mov     dword ptr [rbp+var_20.Value], esi
0x140003eed  mov     word ptr [rbp+var_20.Value+4], 0F00h
0x140003ef3  call    cs:__imp_RtlLengthRequiredSid
0x140003ef9  mov     ecx, eax
0x140003efb  call    LsapAllocateLsaHeap
0x140003f00  mov     r13, rax
0x140003f03  test    rax, rax
0x140003f06  jnz     short loc_140003F12
0x140003f08  mov     ebx, 0C000009Ah
0x140003f0d  jmp     loc_140003FB6
0x140003f12  mov     r8b, bl; SubAuthorityCount
0x140003f15  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140003f19  mov     rcx, r13; Sid
0x140003f1c  mov     r14, rsi
0x140003f1f  mov     r12, rsi
0x140003f22  mov     r15, rsi
0x140003f25  mov     rdi, rsi
0x140003f28  call    cs:__imp_RtlInitializeSid
0x140003f2e  xor     edx, edx; SubAuthority
0x140003f30  mov     rcx, r13; Sid
0x140003f33  call    cs:__imp_RtlSubAuthoritySid
0x140003f39  mov     ecx, ebx; SubAuthorityCount
0x140003f3b  mov     dword ptr [rax], 12h
0x140003f41  call    cs:__imp_RtlLengthRequiredSid
0x140003f47  mov     ecx, eax
0x140003f49  call    LsapAllocateLsaHeap
0x140003f4e  mov     [rbp+var_48], rax
0x140003f52  mov     rbx, rax
0x140003f55  test    rax, rax
0x140003f58  jnz     short loc_140003FD5
0x140003f5a  mov     ebx, 0C000009Ah
0x140003f5f  mov     rcx, r13
0x140003f62  call    LsapFreeLsaHeap
0x140003f67  mov     rcx, [rbp+var_48]
0x140003f6b  test    rcx, rcx
0x140003f6e  jz      short loc_140003F75
0x140003f70  call    LsapFreeLsaHeap
0x140003f75  test    rsi, rsi
0x140003f78  jz      short loc_140003F82
0x140003f7a  mov     rcx, rsi
0x140003f7d  call    LsapFreeLsaHeap
0x140003f82  test    r14, r14
0x140003f85  jz      short loc_140003F8F
0x140003f87  mov     rcx, r14
0x140003f8a  call    LsapFreeLsaHeap
0x140003f8f  test    r12, r12
0x140003f92  jz      short loc_140003F9C
0x140003f94  mov     rcx, r12
0x140003f97  call    LsapFreeLsaHeap
0x140003f9c  test    r15, r15
0x140003f9f  jz      short loc_140003FA9
0x140003fa1  mov     rcx, r15
0x140003fa4  call    LsapFreeLsaHeap
0x140003fa9  test    rdi, rdi
0x140003fac  jz      short loc_140003FB6
0x140003fae  mov     rcx, rdi
0x140003fb1  call    LsapFreeLsaHeap
0x140003fb6  mov     eax, ebx
0x140003fb8  mov     rcx, [rbp+var_18]
0x140003fbc  xor     rcx, rsp; StackCookie
0x140003fbf  call    __security_check_cookie
0x140003fc4  add     rsp, 68h
0x140003fc8  pop     r15
0x140003fca  pop     r14
0x140003fcc  pop     r13
0x140003fce  pop     r12
0x140003fd0  pop     rdi
0x140003fd1  pop     rsi
0x140003fd2  pop     rbx
0x140003fd3  pop     rbp
0x140003fd4  retn
0x140003fd5  mov     r8b, 1; SubAuthorityCount
0x140003fd8  lea     rdx, [rbp+var_28]; IdentifierAuthority
0x140003fdc  mov     rcx, rbx; Sid
0x140003fdf  call    cs:__imp_RtlInitializeSid
0x140003fe5  xor     edx, edx; SubAuthority
0x140003fe7  mov     rcx, rbx; Sid
0x140003fea  call    cs:__imp_RtlSubAuthoritySid
0x140003ff0  mov     ebx, 1
0x140003ff5  mov     ecx, ebx; SubAuthorityCount
0x140003ff7  mov     [rax], esi
0x140003ff9  call    cs:__imp_RtlLengthRequiredSid
0x140003fff  mov     ecx, eax
0x140004001  call    LsapAllocateLsaHeap
0x140004006  mov     rsi, rax
0x140004009  test    rax, rax
0x14000400c  jz      loc_140003F5A
0x140004012  mov     r8b, bl; SubAuthorityCount
0x140004015  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140004019  mov     rcx, rax; Sid
0x14000401c  call    cs:__imp_RtlInitializeSid
0x140004022  xor     edx, edx; SubAuthority
0x140004024  mov     rcx, rsi; Sid
0x140004027  call    cs:__imp_RtlSubAuthoritySid
0x14000402d  lea     ecx, [rbx+1]; SubAuthorityCount
0x140004030  mov     dword ptr [rax], 7
0x140004036  call    cs:__imp_RtlLengthRequiredSid
0x14000403c  mov     ecx, eax
0x14000403e  call    LsapAllocateLsaHeap
0x140004043  mov     r14, rax
0x140004046  test    rax, rax
0x140004049  jz      loc_140003F5A
0x14000404f  mov     r8b, 2; SubAuthorityCount
0x140004052  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140004056  mov     rcx, rax; Sid
0x140004059  call    cs:__imp_RtlInitializeSid
0x14000405f  xor     edx, edx; SubAuthority
0x140004061  mov     rcx, r14; Sid
0x140004064  call    cs:__imp_RtlSubAuthoritySid
0x14000406a  mov     edx, ebx; SubAuthority
0x14000406c  mov     rcx, r14; Sid
0x14000406f  mov     dword ptr [rax], 20h ; ' '
0x140004075  call    cs:__imp_RtlSubAuthoritySid
0x14000407b  lea     ecx, [rbx+1]; SubAuthorityCount
0x14000407e  mov     dword ptr [rax], 220h
0x140004084  call    cs:__imp_RtlLengthRequiredSid
0x14000408a  mov     ecx, eax
0x14000408c  call    LsapAllocateLsaHeap
0x140004091  mov     r12, rax
0x140004094  test    rax, rax
0x140004097  jz      loc_140003F5A
0x14000409d  mov     r8b, 2; SubAuthorityCount
0x1400040a0  lea     rdx, [rbp+var_20]; IdentifierAuthority
0x1400040a4  mov     rcx, rax; Sid
0x1400040a7  call    cs:__imp_RtlInitializeSid
0x1400040ad  xor     edx, edx; SubAuthority
0x1400040af  mov     rcx, r12; Sid
0x1400040b2  call    cs:__imp_RtlSubAuthoritySid
0x1400040b8  mov     edx, ebx; SubAuthority
0x1400040ba  mov     rcx, r12; Sid
0x1400040bd  mov     dword ptr [rax], 2
0x1400040c3  call    cs:__imp_RtlSubAuthoritySid
0x1400040c9  lea     ecx, [rbx+9]; SubAuthorityCount
0x1400040cc  mov     [rax], ebx
0x1400040ce  call    cs:__imp_RtlLengthRequiredSid
0x1400040d4  mov     ecx, eax
0x1400040d6  call    LsapAllocateLsaHeap
0x1400040db  mov     r15, rax
0x1400040de  test    rax, rax
0x1400040e1  jz      loc_140003F5A
0x1400040e7  lea     ecx, [rbx+8]; SubAuthorityCount
0x1400040ea  call    cs:__imp_RtlLengthRequiredSid
0x1400040f0  mov     ecx, eax
0x1400040f2  call    LsapAllocateLsaHeap
0x1400040f7  mov     rdi, rax
0x1400040fa  test    rax, rax
0x1400040fd  jz      loc_140003F5A
0x140004103  mov     r8, r15
0x140004106  lea     rcx, [rbp+var_40]
0x14000410a  mov     rdx, rax
0x14000410d  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x140004113  mov     ebx, eax
0x140004115  test    eax, eax
0x140004117  js      loc_140003F5F
0x14000411d  mov     rcx, [rbp+var_48]
0x140004121  mov     cs:gLsapWorldSid, rcx
0x140004128  mov     cs:gLsapLocalSystemSid, r13
0x14000412f  mov     cs:gLsapAliasAdminsSid, r14
0x140004136  mov     cs:gLsapAnonymousSid, rsi
0x14000413d  mov     cs:gLsapAnyPackageSid, r12
0x140004144  mov     cs:gLsapIdentityServicesLpacSid, r15
0x14000414b  jmp     loc_140003FAE
```
