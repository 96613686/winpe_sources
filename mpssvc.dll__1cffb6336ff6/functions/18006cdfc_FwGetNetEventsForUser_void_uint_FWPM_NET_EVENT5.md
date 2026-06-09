# FwGetNetEventsForUser(void *,uint *,FWPM_NET_EVENT5_ * * *)

- ea: `0x18006cdfc`
- end: `0x18006d082`
- name: `?FwGetNetEventsForUser@@YAJPEAXPEAIPEAPEAPEAUFWPM_NET_EVENT5_@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(void *, unsigned int *, struct FWPM_NET_EVENT5_ ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800b0554`

## callees

- `0x18000af3c`
- `0x18006cdfc`
- `0x18006f520`
- `0x1800873a0`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x18006cea5`
- `fwpuclnt!FwpmEngineOpen0` at `0x18006cf84`
- `fwpuclnt!FwpmEngineOpen0` at `0x18006cea5`
- `fwpuclnt!FwpmEngineOpen0` at `0x18006cf84`
- `fwpuclnt!FwpmEngineClose0` at `0x18006d056`
- `fwpuclnt!FwpmEngineClose0` at `0x18006d056`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18006cef8`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18006cef8`
- `fwpuclnt!FwpmNetEventEnum5` at `0x18006cfd5`
- `fwpuclnt!FwpmNetEventEnum5` at `0x18006cfd5`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x18006d02c`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x18006d02c`

## pseudocode

```c
__int64 __fastcall FwGetNetEventsForUser(void *a1, unsigned int *a2, struct FWPM_NET_EVENT5_ ***a3)
{
  char v5; // si
  signed int v6; // eax
  signed int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  int v12; // eax
  HANDLE v13; // rcx
  HANDLE engineHandle; // [rsp+30h] [rbp-79h] BYREF
  HANDLE enumHandle; // [rsp+38h] [rbp-71h] BYREF
  FWPM_SESSION0 session; // [rsp+40h] [rbp-69h] BYREF
  GUID v18; // [rsp+90h] [rbp-19h] BYREF
  int v19; // [rsp+A0h] [rbp-9h]
  _BYTE v20[20]; // [rsp+A4h] [rbp-5h]
  FWPM_NET_EVENT_ENUM_TEMPLATE0 enumTemplate; // [rsp+B8h] [rbp+Fh] BYREF

  memset(&enumTemplate, 0, 24);
  engineHandle = 0;
  v5 = 0;
  enumHandle = 0;
  enumTemplate.numFilterConditions = 1;
  v19 = 0;
  *(_OWORD *)v20 = 0;
  *(_DWORD *)&v20[4] = 13;
  v18 = FWPM_CONDITION_ALE_USER_ID;
  *(_QWORD *)&v20[12] = a1;
  enumTemplate.filterCondition = (FWPM_FILTER_CONDITION0 *)&v18;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"NetEvents for User";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 1;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v11 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 20;
        goto LABEL_27;
      }
      goto LABEL_28;
    }
  }
  else
  {
    v6 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 21;
LABEL_27:
        WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_6b0d10e62d0e39a840640e53a67581ff_Traceguids, (unsigned int)v7);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
    v5 = 1;
  }
  v10 = FwpmNetEventCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( v7 >= 0 )
  {
    v12 = FwpmNetEventEnum5(engineHandle, enumHandle, 0xFFFFFFFFLL, a3, a2);
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 23;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 22;
      goto LABEL_27;
    }
  }
LABEL_28:
  if ( enumHandle )
    FwpmNetEventDestroyEnumHandle0(engineHandle, enumHandle);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    v13 = engineHandle;
    if ( engineHandle )
      goto LABEL_35;
  }
  else if ( v5 )
  {
    v13 = engineHandle;
LABEL_35:
    FwpmEngineClose0(v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006cdfc  mov     [rsp-8+arg_18], rbx
0x18006ce01  push    rbp
0x18006ce02  push    rsi
0x18006ce03  push    r12
0x18006ce05  push    r14
0x18006ce07  push    r15
0x18006ce09  lea     rbp, [rsp-37h]
0x18006ce0e  sub     rsp, 0E0h
0x18006ce15  mov     rax, cs:__security_cookie
0x18006ce1c  xor     rax, rsp
0x18006ce1f  mov     [rbp+57h+var_28], rax
0x18006ce23  xor     r12d, r12d
0x18006ce26  lea     rax, [rbp+57h+var_70]
0x18006ce2a  xorps   xmm0, xmm0
0x18006ce2d  mov     [rbp+57h+enumTemplate.startTime.dwLowDateTime], r12d
0x18006ce31  movups  xmmword ptr [rbp+57h+enumTemplate.startTime.dwHighDateTime], xmm0
0x18006ce35  mov     r15, r8
0x18006ce38  mov     r14, rdx
0x18006ce3b  movups  xmmword ptr [rbp+57h+enumTemplate.numFilterConditions], xmm0
0x18006ce3f  mov     [rbp+57h+var_D0], r12
0x18006ce43  mov     sil, r12b
0x18006ce46  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_ALE_USER_ID.Data1
0x18006ce4d  mov     [rbp+57h+enumHandle], r12
0x18006ce51  xorps   xmm1, xmm1
0x18006ce54  mov     [rbp+57h+enumTemplate.numFilterConditions], 1
0x18006ce5b  movups  [rbp+57h+var_70+4], xmm1
0x18006ce5f  mov     [rbp+57h+var_60], r12d
0x18006ce63  movups  xmmword ptr [rbp+57h+var_5C], xmm1
0x18006ce67  mov     dword ptr [rbp+57h+var_5C+4], 0Dh
0x18006ce6e  movdqu  [rbp+57h+var_70], xmm0
0x18006ce73  mov     qword ptr [rbp+57h+var_5C+0Ch], rcx
0x18006ce77  mov     [rbp+57h+enumTemplate.filterCondition], rax
0x18006ce7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x18006ce82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x18006ce87  xor     r8d, r8d; authIdentity
0x18006ce8a  lea     edx, [r12+0Ah]; authnService
0x18006ce8f  xor     ecx, ecx; serverName
0x18006ce91  test    al, al
0x18006ce93  jnz     loc_18006CF40
0x18006ce99  lea     rax, [rbp+57h+var_D0]
0x18006ce9d  xor     r9d, r9d; session
0x18006cea0  mov     [rsp+100h+engineHandle], rax; engineHandle
0x18006cea5  call    cs:__imp_FwpmEngineOpen0
0x18006ceab  mov     ebx, eax
0x18006cead  test    eax, eax
0x18006ceaf  jle     short loc_18006CEBA
0x18006ceb1  movzx   ebx, ax
0x18006ceb4  or      ebx, 80070000h
0x18006ceba  test    ebx, ebx
0x18006cebc  jns     short loc_18006CEE9
0x18006cebe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cec5  lea     rax, WPP_GLOBAL_Control
0x18006cecc  cmp     rcx, rax
0x18006cecf  jz      loc_18006D01F
0x18006ced5  test    byte ptr [rcx+1Ch], 1
0x18006ced9  jz      loc_18006D01F
0x18006cedf  mov     edx, 15h
0x18006cee4  jmp     loc_18006D00C
0x18006cee9  mov     sil, 1
0x18006ceec  mov     rcx, [rbp+57h+var_D0]; engineHandle
0x18006cef0  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x18006cef4  lea     rdx, [rbp+57h+enumTemplate]; enumTemplate
0x18006cef8  call    cs:__imp_FwpmNetEventCreateEnumHandle0
0x18006cefe  mov     ebx, eax
0x18006cf00  test    eax, eax
0x18006cf02  jle     short loc_18006CF0D
0x18006cf04  movzx   ebx, ax
0x18006cf07  or      ebx, 80070000h
0x18006cf0d  test    ebx, ebx
0x18006cf0f  jns     loc_18006CFC1
0x18006cf15  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf1c  lea     rax, WPP_GLOBAL_Control
0x18006cf23  cmp     rcx, rax
0x18006cf26  jz      loc_18006D01F
0x18006cf2c  test    byte ptr [rcx+1Ch], 1
0x18006cf30  jz      loc_18006D01F
0x18006cf36  mov     edx, 16h
0x18006cf3b  jmp     loc_18006D00C
0x18006cf40  lea     rax, aNeteventsForUs; "NetEvents for User"
0x18006cf47  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r12
0x18006cf4b  mov     [rbp+57h+session.displayData.name], rax
0x18006cf4f  lea     r9, [rbp+57h+session]; session
0x18006cf53  xor     eax, eax
0x18006cf55  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r12
0x18006cf59  mov     dword ptr [rbp+57h+session+2Ch], eax
0x18006cf5c  xorps   xmm0, xmm0
0x18006cf5f  lea     rax, [rbp+57h+var_D0]
0x18006cf63  mov     [rbp+57h+session.displayData.description], r12
0x18006cf67  mov     [rsp+100h+engineHandle], rax; engineHandle
0x18006cf6c  mov     [rbp+57h+session.flags], 1
0x18006cf73  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x18006cf7b  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x18006cf80  mov     qword ptr [rbp+57h+session.kernelMode], r12
0x18006cf84  call    cs:__imp_FwpmEngineOpen0
0x18006cf8a  mov     ebx, eax
0x18006cf8c  test    eax, eax
0x18006cf8e  jle     short loc_18006CF99
0x18006cf90  movzx   ebx, ax
0x18006cf93  or      ebx, 80070000h
0x18006cf99  test    ebx, ebx
0x18006cf9b  jns     loc_18006CEEC
0x18006cfa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cfa8  lea     rax, WPP_GLOBAL_Control
0x18006cfaf  cmp     rcx, rax
0x18006cfb2  jz      short loc_18006D01F
0x18006cfb4  test    byte ptr [rcx+1Ch], 1
0x18006cfb8  jz      short loc_18006D01F
0x18006cfba  mov     edx, 14h
0x18006cfbf  jmp     short loc_18006D00C
0x18006cfc1  mov     rdx, [rbp+57h+enumHandle]
0x18006cfc5  mov     r9, r15
0x18006cfc8  mov     rcx, [rbp+57h+var_D0]
0x18006cfcc  or      r8d, 0FFFFFFFFh
0x18006cfd0  mov     [rsp+100h+engineHandle], r14
0x18006cfd5  call    cs:__imp_FwpmNetEventEnum5
0x18006cfdb  mov     ebx, eax
0x18006cfdd  test    eax, eax
0x18006cfdf  jle     short loc_18006CFEA
0x18006cfe1  movzx   ebx, ax
0x18006cfe4  or      ebx, 80070000h
0x18006cfea  test    ebx, ebx
0x18006cfec  jns     short loc_18006D01F
0x18006cfee  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cff5  lea     rax, WPP_GLOBAL_Control
0x18006cffc  cmp     rcx, rax
0x18006cfff  jz      short loc_18006D01F
0x18006d001  test    byte ptr [rcx+1Ch], 1
0x18006d005  jz      short loc_18006D01F
0x18006d007  mov     edx, 17h
0x18006d00c  mov     rcx, [rcx+10h]
0x18006d010  lea     r8, WPP_6b0d10e62d0e39a840640e53a67581ff_Traceguids
0x18006d017  mov     r9d, ebx
0x18006d01a  call    WPP_SF_d
0x18006d01f  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x18006d023  test    rdx, rdx
0x18006d026  jz      short loc_18006D032
0x18006d028  mov     rcx, [rbp+57h+var_D0]; engineHandle
0x18006d02c  call    cs:__imp_FwpmNetEventDestroyEnumHandle0
0x18006d032  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x18006d039  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x18006d03e  test    al, al
0x18006d040  jz      short loc_18006D04D
0x18006d042  mov     rcx, [rbp+57h+var_D0]
0x18006d046  test    rcx, rcx
0x18006d049  jz      short loc_18006D05C
0x18006d04b  jmp     short loc_18006D056
0x18006d04d  test    sil, sil
0x18006d050  jz      short loc_18006D05C
0x18006d052  mov     rcx, [rbp+57h+var_D0]; engineHandle
0x18006d056  call    cs:__imp_FwpmEngineClose0
0x18006d05c  mov     eax, ebx
0x18006d05e  mov     rcx, [rbp+57h+var_28]
0x18006d062  xor     rcx, rsp; StackCookie
0x18006d065  call    __security_check_cookie
0x18006d06a  mov     rbx, [rsp+100h+arg_18]
0x18006d072  add     rsp, 0E0h
0x18006d079  pop     r15
0x18006d07b  pop     r14
0x18006d07d  pop     r12
0x18006d07f  pop     rsi
0x18006d080  pop     rbp
0x18006d081  retn
```
