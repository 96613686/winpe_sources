# FwDeletePhase1SAsInternal

- ea: `0x1800b5c7c`
- end: `0x1800b5f9c`
- name: `FwDeletePhase1SAsInternal`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18009fd80`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x18008b9f8`
- `0x1800b35e0`
- `0x1800b4bc4`
- `0x1800b5c7c`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x1800b5d1e`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b5d6d`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b5d1e`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b5d6d`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b5f66`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b5f66`
- `fwpuclnt!IkeextSaDeleteById0` at `0x1800b5e9a`
- `fwpuclnt!IkeextSaDeleteById0` at `0x1800b5e9a`
- `fwpuclnt!IkeextSaEnum2` at `0x1800b5e07`
- `fwpuclnt!IkeextSaEnum2` at `0x1800b5e07`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b5f38`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b5f38`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800b5db1`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800b5db1`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800b5f51`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800b5f51`

## string_xrefs

- `0x1800b5cdd`: `Firewall Delete Phase1 SAs`

## pseudocode

```c
__int64 __fastcall FwDeletePhase1SAsInternal(struct _tag_FW_ENDPOINTS *a1, void *a2)
{
  DWORD v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rsi
  unsigned int v10; // r14d
  __int64 v11; // r12
  DWORD v12; // eax
  void *p; // [rsp+38h] [rbp-51h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-49h] BYREF
  HANDLE enumHandle; // [rsp+48h] [rbp-41h] BYREF
  FWPM_SESSION0 session; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v19; // [rsp+A0h] [rbp+17h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  p = 0;
  v19 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Firewall Delete Phase1 SAs";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 0;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v3 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_35;
      v6 = 60;
LABEL_6:
      v7 = *(_QWORD *)(v5 + 16);
      v8 = v3;
      goto LABEL_34;
    }
  }
  else
  {
    v3 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_35;
      v6 = 61;
      goto LABEL_6;
    }
  }
  v3 = IkeextSaCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_35;
    v6 = 62;
    goto LABEL_6;
  }
  v3 = IkeextSaEnum2(engineHandle, enumHandle, 0xFFFFFFFFLL, &p, &v19);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_35;
    v6 = 63;
    goto LABEL_6;
  }
  if ( !v19 )
    goto LABEL_35;
  if ( p )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = 0;
    v10 = 0;
    while ( 1 )
    {
      v11 = *((_QWORD *)p + v10);
      if ( (unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)(v11 + 24)) )
      {
        v12 = IkeextSaDeleteById0(engineHandle, *(_QWORD *)v11);
        if ( v12 )
        {
          v4 = v12;
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_29;
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            64,
            WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids,
            **((unsigned int **)p + v10));
        }
        else
        {
          FwAuditDeletePhase1SAs(a2, *((struct IKEEXT_SA_DETAILS2_ **)p + v10));
        }
        v9 = WPP_GLOBAL_Control;
      }
LABEL_29:
      if ( ++v10 >= v19 )
      {
        if ( v4 && (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
        {
          v7 = *(_QWORD *)(v9 + 16);
          v6 = 65;
          v8 = v4;
LABEL_34:
          WPP_SF_d(v7, v6, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids, v8);
        }
LABEL_35:
        if ( p )
          FwpmFreeMemory0(&p);
        break;
      }
    }
  }
  if ( enumHandle )
    IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v4;
}

```

## disassembly

```asm
0x1800b5c7c  mov     [rsp-8+arg_10], rbx
0x1800b5c81  push    rbp
0x1800b5c82  push    rsi
0x1800b5c83  push    rdi
0x1800b5c84  push    r12
0x1800b5c86  push    r13
0x1800b5c88  push    r14
0x1800b5c8a  push    r15
0x1800b5c8c  lea     rbp, [rsp-27h]
0x1800b5c91  sub     rsp, 0B0h
0x1800b5c98  mov     rax, cs:__security_cookie
0x1800b5c9f  xor     rax, rsp
0x1800b5ca2  mov     [rbp+57h+var_38], rax
0x1800b5ca6  xor     r15d, r15d
0x1800b5ca9  mov     [rbp+57h+var_B0], rcx
0x1800b5cad  mov     [rbp+57h+var_A0], r15
0x1800b5cb1  mov     r13, rdx
0x1800b5cb4  mov     [rbp+57h+enumHandle], r15
0x1800b5cb8  mov     [rbp+57h+p], r15
0x1800b5cbc  mov     [rbp+57h+var_40], r15d
0x1800b5cc0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800b5cc7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800b5ccc  xor     r8d, r8d; authIdentity
0x1800b5ccf  lea     edx, [r15+0Ah]; authnService
0x1800b5cd3  xor     ecx, ecx; serverName
0x1800b5cd5  test    al, al
0x1800b5cd7  jz      loc_1800B5D61
0x1800b5cdd  lea     rax, aFirewallDelete_0; "Firewall Delete Phase1 SAs"
0x1800b5ce4  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800b5ce8  mov     [rbp+57h+session.displayData.name], rax
0x1800b5cec  lea     r9, [rbp+57h+session]; session
0x1800b5cf0  xor     eax, eax
0x1800b5cf2  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800b5cf6  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800b5cf9  xorps   xmm0, xmm0
0x1800b5cfc  lea     rax, [rbp+57h+var_A0]
0x1800b5d00  mov     [rbp+57h+session.displayData.description], r15
0x1800b5d04  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800b5d09  mov     [rbp+57h+session.flags], r15d
0x1800b5d0d  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800b5d15  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800b5d1a  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800b5d1e  call    cs:__imp_FwpmEngineOpen0
0x1800b5d25  nop     dword ptr [rax+rax+00h]
0x1800b5d2a  mov     ebx, eax
0x1800b5d2c  test    eax, eax
0x1800b5d2e  jz      short loc_1800B5DA7
0x1800b5d30  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5d37  lea     rdi, WPP_GLOBAL_Control
0x1800b5d3e  cmp     rcx, rdi
0x1800b5d41  jz      loc_1800B5F2E
0x1800b5d47  test    byte ptr [rcx+1Ch], 1
0x1800b5d4b  jz      loc_1800B5F2E
0x1800b5d51  lea     edx, [r15+3Ch]
0x1800b5d55  mov     rcx, [rcx+10h]
0x1800b5d59  mov     r9d, eax
0x1800b5d5c  jmp     loc_1800B5F22
0x1800b5d61  lea     rax, [rbp+57h+var_A0]
0x1800b5d65  xor     r9d, r9d; session
0x1800b5d68  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800b5d6d  call    cs:__imp_FwpmEngineOpen0
0x1800b5d74  nop     dword ptr [rax+rax+00h]
0x1800b5d79  mov     ebx, eax
0x1800b5d7b  test    eax, eax
0x1800b5d7d  jz      short loc_1800B5DA7
0x1800b5d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5d86  lea     rdi, WPP_GLOBAL_Control
0x1800b5d8d  cmp     rcx, rdi
0x1800b5d90  jz      loc_1800B5F2E
0x1800b5d96  test    byte ptr [rcx+1Ch], 1
0x1800b5d9a  jz      loc_1800B5F2E
0x1800b5da0  mov     edx, 3Dh ; '='
0x1800b5da5  jmp     short loc_1800B5D55
0x1800b5da7  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b5dab  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800b5daf  xor     edx, edx; enumTemplate
0x1800b5db1  call    cs:__imp_IkeextSaCreateEnumHandle0
0x1800b5db8  nop     dword ptr [rax+rax+00h]
0x1800b5dbd  mov     ebx, eax
0x1800b5dbf  test    eax, eax
0x1800b5dc1  jz      short loc_1800B5DEE
0x1800b5dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5dca  lea     rdi, WPP_GLOBAL_Control
0x1800b5dd1  cmp     rcx, rdi
0x1800b5dd4  jz      loc_1800B5F2E
0x1800b5dda  test    byte ptr [rcx+1Ch], 1
0x1800b5dde  jz      loc_1800B5F2E
0x1800b5de4  mov     edx, 3Eh ; '>'
0x1800b5de9  jmp     loc_1800B5D55
0x1800b5dee  mov     rdx, [rbp+57h+enumHandle]
0x1800b5df2  lea     rax, [rbp+57h+var_40]
0x1800b5df6  mov     rcx, [rbp+57h+var_A0]
0x1800b5dfa  lea     r9, [rbp+57h+p]
0x1800b5dfe  or      r8d, 0FFFFFFFFh
0x1800b5e02  mov     [rsp+0E0h+engineHandle], rax
0x1800b5e07  call    cs:__imp_IkeextSaEnum2
0x1800b5e0e  nop     dword ptr [rax+rax+00h]
0x1800b5e13  mov     ebx, eax
0x1800b5e15  test    eax, eax
0x1800b5e17  jz      short loc_1800B5E44
0x1800b5e19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5e20  lea     rdi, WPP_GLOBAL_Control
0x1800b5e27  cmp     rcx, rdi
0x1800b5e2a  jz      loc_1800B5F2E
0x1800b5e30  test    byte ptr [rcx+1Ch], 1
0x1800b5e34  jz      loc_1800B5F2E
0x1800b5e3a  mov     edx, 3Fh ; '?'
0x1800b5e3f  jmp     loc_1800B5D55
0x1800b5e44  mov     eax, [rbp+57h+var_40]
0x1800b5e47  test    eax, eax
0x1800b5e49  jz      loc_1800B5F2E
0x1800b5e4f  cmp     [rbp+57h+p], r15
0x1800b5e53  jz      loc_1800B5F44
0x1800b5e59  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b5e60  mov     ebx, r15d
0x1800b5e63  lea     rdi, WPP_GLOBAL_Control
0x1800b5e6a  mov     r14d, r15d
0x1800b5e6d  test    eax, eax
0x1800b5e6f  jz      loc_1800B5F07
0x1800b5e75  mov     rax, [rbp+57h+p]
0x1800b5e79  mov     rcx, [rbp+57h+var_B0]; struct _tag_FW_ENDPOINTS *
0x1800b5e7d  mov     r15d, r14d
0x1800b5e80  mov     r12, [rax+r15*8]
0x1800b5e84  lea     rdx, [r12+18h]; struct IKEEXT_TRAFFIC0_ *
0x1800b5e89  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b5e8e  test    eax, eax
0x1800b5e90  jz      short loc_1800B5EF7
0x1800b5e92  mov     rdx, [r12]; id
0x1800b5e96  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b5e9a  call    cs:__imp_IkeextSaDeleteById0
0x1800b5ea1  nop     dword ptr [rax+rax+00h]
0x1800b5ea6  test    eax, eax
0x1800b5ea8  jz      short loc_1800B5EE0
0x1800b5eaa  mov     ebx, eax
0x1800b5eac  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b5eb3  cmp     rsi, rdi
0x1800b5eb6  jz      short loc_1800B5EF7
0x1800b5eb8  test    byte ptr [rsi+1Ch], 1
0x1800b5ebc  jz      short loc_1800B5EF7
0x1800b5ebe  mov     rax, [rbp+57h+p]
0x1800b5ec2  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b5ec9  mov     rcx, [rsi+10h]
0x1800b5ecd  mov     edx, 40h ; '@'
0x1800b5ed2  mov     r9, [rax+r15*8]
0x1800b5ed6  mov     r9d, [r9]
0x1800b5ed9  call    WPP_SF_d
0x1800b5ede  jmp     short loc_1800B5EF0
0x1800b5ee0  mov     rdx, [rbp+57h+p]
0x1800b5ee4  mov     rcx, r13; void *
0x1800b5ee7  mov     rdx, [rdx+r15*8]; struct IKEEXT_SA_DETAILS2_ *
0x1800b5eeb  call    ?FwAuditDeletePhase1SAs@@YAKPEAXPEAUIKEEXT_SA_DETAILS2_@@@Z; FwAuditDeletePhase1SAs(void *,IKEEXT_SA_DETAILS2_ *)
0x1800b5ef0  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b5ef7  inc     r14d
0x1800b5efa  cmp     r14d, [rbp+57h+var_40]
0x1800b5efe  jb      loc_1800B5E75
0x1800b5f04  xor     r15d, r15d
0x1800b5f07  test    ebx, ebx
0x1800b5f09  jz      short loc_1800B5F2E
0x1800b5f0b  cmp     rsi, rdi
0x1800b5f0e  jz      short loc_1800B5F2E
0x1800b5f10  test    byte ptr [rsi+1Ch], 1
0x1800b5f14  jz      short loc_1800B5F2E
0x1800b5f16  mov     rcx, [rsi+10h]
0x1800b5f1a  mov     edx, 41h ; 'A'
0x1800b5f1f  mov     r9d, ebx
0x1800b5f22  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b5f29  call    WPP_SF_d
0x1800b5f2e  cmp     [rbp+57h+p], r15
0x1800b5f32  jz      short loc_1800B5F44
0x1800b5f34  lea     rcx, [rbp+57h+p]; p
0x1800b5f38  call    cs:__imp_FwpmFreeMemory0
0x1800b5f3f  nop     dword ptr [rax+rax+00h]
0x1800b5f44  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b5f48  test    rdx, rdx
0x1800b5f4b  jz      short loc_1800B5F5D
0x1800b5f4d  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b5f51  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x1800b5f58  nop     dword ptr [rax+rax+00h]
0x1800b5f5d  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b5f61  test    rcx, rcx
0x1800b5f64  jz      short loc_1800B5F72
0x1800b5f66  call    cs:__imp_FwpmEngineClose0
0x1800b5f6d  nop     dword ptr [rax+rax+00h]
0x1800b5f72  mov     eax, ebx
0x1800b5f74  mov     rcx, [rbp+57h+var_38]
0x1800b5f78  xor     rcx, rsp; StackCookie
0x1800b5f7b  call    __security_check_cookie
0x1800b5f80  mov     rbx, [rsp+0E0h+arg_10]
0x1800b5f88  add     rsp, 0B0h
0x1800b5f8f  pop     r15
0x1800b5f91  pop     r14
0x1800b5f93  pop     r13
0x1800b5f95  pop     r12
0x1800b5f97  pop     rdi
0x1800b5f98  pop     rsi
0x1800b5f99  pop     rbp
0x1800b5f9a  retn
```
