# FwGetNetEventsForUser(void *,uint *,FWPM_NET_EVENT5_ * * *)

- ea: `0x180070078`
- end: `0x180070323`
- name: `?FwGetNetEventsForUser@@YAJPEAXPEAIPEAPEAPEAUFWPM_NET_EVENT5_@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(void *, unsigned int *, struct FWPM_NET_EVENT5_ ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800b6dc8`

## callees

- `0x18000a710`
- `0x180070078`
- `0x1800729c0`
- `0x18008b9f8`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x180070121`
- `fwpuclnt!FwpmEngineOpen0` at `0x18007020c`
- `fwpuclnt!FwpmEngineOpen0` at `0x180070121`
- `fwpuclnt!FwpmEngineOpen0` at `0x18007020c`
- `fwpuclnt!FwpmEngineClose0` at `0x1800702f0`
- `fwpuclnt!FwpmEngineClose0` at `0x1800702f0`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18007017a`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18007017a`
- `fwpuclnt!FwpmNetEventEnum5` at `0x180070263`
- `fwpuclnt!FwpmNetEventEnum5` at `0x180070263`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x1800702c0`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x1800702c0`

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
0x180070078  mov     [rsp-8+arg_18], rbx
0x18007007d  push    rbp
0x18007007e  push    rsi
0x18007007f  push    r12
0x180070081  push    r14
0x180070083  push    r15
0x180070085  lea     rbp, [rsp-37h]
0x18007008a  sub     rsp, 0E0h
0x180070091  mov     rax, cs:__security_cookie
0x180070098  xor     rax, rsp
0x18007009b  mov     [rbp+57h+var_28], rax
0x18007009f  xor     r12d, r12d
0x1800700a2  lea     rax, [rbp+57h+var_70]
0x1800700a6  xorps   xmm0, xmm0
0x1800700a9  mov     [rbp+57h+enumTemplate.startTime.dwLowDateTime], r12d
0x1800700ad  movups  xmmword ptr [rbp+57h+enumTemplate.startTime.dwHighDateTime], xmm0
0x1800700b1  mov     r15, r8
0x1800700b4  mov     r14, rdx
0x1800700b7  movups  xmmword ptr [rbp+57h+enumTemplate.numFilterConditions], xmm0
0x1800700bb  mov     [rbp+57h+var_D0], r12
0x1800700bf  mov     sil, r12b
0x1800700c2  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_ALE_USER_ID.Data1
0x1800700c9  mov     [rbp+57h+enumHandle], r12
0x1800700cd  xorps   xmm1, xmm1
0x1800700d0  mov     [rbp+57h+enumTemplate.numFilterConditions], 1
0x1800700d7  movups  [rbp+57h+var_70+4], xmm1
0x1800700db  mov     [rbp+57h+var_60], r12d
0x1800700df  movups  xmmword ptr [rbp+57h+var_5C], xmm1
0x1800700e3  mov     dword ptr [rbp+57h+var_5C+4], 0Dh
0x1800700ea  movdqu  [rbp+57h+var_70], xmm0
0x1800700ef  mov     qword ptr [rbp+57h+var_5C+0Ch], rcx
0x1800700f3  mov     [rbp+57h+enumTemplate.filterCondition], rax
0x1800700f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800700fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x180070103  xor     r8d, r8d; authIdentity
0x180070106  lea     edx, [r12+0Ah]; authnService
0x18007010b  xor     ecx, ecx; serverName
0x18007010d  test    al, al
0x18007010f  jnz     loc_1800701C8
0x180070115  lea     rax, [rbp+57h+var_D0]
0x180070119  xor     r9d, r9d; session
0x18007011c  mov     [rsp+100h+engineHandle], rax; engineHandle
0x180070121  call    cs:__imp_FwpmEngineOpen0
0x180070128  nop     dword ptr [rax+rax+00h]
0x18007012d  mov     ebx, eax
0x18007012f  test    eax, eax
0x180070131  jle     short loc_18007013C
0x180070133  movzx   ebx, ax
0x180070136  or      ebx, 80070000h
0x18007013c  test    ebx, ebx
0x18007013e  jns     short loc_18007016B
0x180070140  mov     rcx, cs:WPP_GLOBAL_Control
0x180070147  lea     rax, WPP_GLOBAL_Control
0x18007014e  cmp     rcx, rax
0x180070151  jz      loc_1800702B3
0x180070157  test    byte ptr [rcx+1Ch], 1
0x18007015b  jz      loc_1800702B3
0x180070161  mov     edx, 15h
0x180070166  jmp     loc_1800702A0
0x18007016b  mov     sil, 1
0x18007016e  mov     rcx, [rbp+57h+var_D0]; engineHandle
0x180070172  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x180070176  lea     rdx, [rbp+57h+enumTemplate]; enumTemplate
0x18007017a  call    cs:__imp_FwpmNetEventCreateEnumHandle0
0x180070181  nop     dword ptr [rax+rax+00h]
0x180070186  mov     ebx, eax
0x180070188  test    eax, eax
0x18007018a  jle     short loc_180070195
0x18007018c  movzx   ebx, ax
0x18007018f  or      ebx, 80070000h
0x180070195  test    ebx, ebx
0x180070197  jns     loc_18007024F
0x18007019d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800701a4  lea     rax, WPP_GLOBAL_Control
0x1800701ab  cmp     rcx, rax
0x1800701ae  jz      loc_1800702B3
0x1800701b4  test    byte ptr [rcx+1Ch], 1
0x1800701b8  jz      loc_1800702B3
0x1800701be  mov     edx, 16h
0x1800701c3  jmp     loc_1800702A0
0x1800701c8  lea     rax, aNeteventsForUs; "NetEvents for User"
0x1800701cf  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r12
0x1800701d3  mov     [rbp+57h+session.displayData.name], rax
0x1800701d7  lea     r9, [rbp+57h+session]; session
0x1800701db  xor     eax, eax
0x1800701dd  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r12
0x1800701e1  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800701e4  xorps   xmm0, xmm0
0x1800701e7  lea     rax, [rbp+57h+var_D0]
0x1800701eb  mov     [rbp+57h+session.displayData.description], r12
0x1800701ef  mov     [rsp+100h+engineHandle], rax; engineHandle
0x1800701f4  mov     [rbp+57h+session.flags], 1
0x1800701fb  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x180070203  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x180070208  mov     qword ptr [rbp+57h+session.kernelMode], r12
0x18007020c  call    cs:__imp_FwpmEngineOpen0
0x180070213  nop     dword ptr [rax+rax+00h]
0x180070218  mov     ebx, eax
0x18007021a  test    eax, eax
0x18007021c  jle     short loc_180070227
0x18007021e  movzx   ebx, ax
0x180070221  or      ebx, 80070000h
0x180070227  test    ebx, ebx
0x180070229  jns     loc_18007016E
0x18007022f  mov     rcx, cs:WPP_GLOBAL_Control
0x180070236  lea     rax, WPP_GLOBAL_Control
0x18007023d  cmp     rcx, rax
0x180070240  jz      short loc_1800702B3
0x180070242  test    byte ptr [rcx+1Ch], 1
0x180070246  jz      short loc_1800702B3
0x180070248  mov     edx, 14h
0x18007024d  jmp     short loc_1800702A0
0x18007024f  mov     rdx, [rbp+57h+enumHandle]
0x180070253  mov     r9, r15
0x180070256  mov     rcx, [rbp+57h+var_D0]
0x18007025a  or      r8d, 0FFFFFFFFh
0x18007025e  mov     [rsp+100h+engineHandle], r14
0x180070263  call    cs:__imp_FwpmNetEventEnum5
0x18007026a  nop     dword ptr [rax+rax+00h]
0x18007026f  mov     ebx, eax
0x180070271  test    eax, eax
0x180070273  jle     short loc_18007027E
0x180070275  movzx   ebx, ax
0x180070278  or      ebx, 80070000h
0x18007027e  test    ebx, ebx
0x180070280  jns     short loc_1800702B3
0x180070282  mov     rcx, cs:WPP_GLOBAL_Control
0x180070289  lea     rax, WPP_GLOBAL_Control
0x180070290  cmp     rcx, rax
0x180070293  jz      short loc_1800702B3
0x180070295  test    byte ptr [rcx+1Ch], 1
0x180070299  jz      short loc_1800702B3
0x18007029b  mov     edx, 17h
0x1800702a0  mov     rcx, [rcx+10h]
0x1800702a4  lea     r8, WPP_6b0d10e62d0e39a840640e53a67581ff_Traceguids
0x1800702ab  mov     r9d, ebx
0x1800702ae  call    WPP_SF_d
0x1800702b3  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800702b7  test    rdx, rdx
0x1800702ba  jz      short loc_1800702CC
0x1800702bc  mov     rcx, [rbp+57h+var_D0]; engineHandle
0x1800702c0  call    cs:__imp_FwpmNetEventDestroyEnumHandle0
0x1800702c7  nop     dword ptr [rax+rax+00h]
0x1800702cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800702d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800702d8  test    al, al
0x1800702da  jz      short loc_1800702E7
0x1800702dc  mov     rcx, [rbp+57h+var_D0]
0x1800702e0  test    rcx, rcx
0x1800702e3  jz      short loc_1800702FC
0x1800702e5  jmp     short loc_1800702F0
0x1800702e7  test    sil, sil
0x1800702ea  jz      short loc_1800702FC
0x1800702ec  mov     rcx, [rbp+57h+var_D0]; engineHandle
0x1800702f0  call    cs:__imp_FwpmEngineClose0
0x1800702f7  nop     dword ptr [rax+rax+00h]
0x1800702fc  mov     eax, ebx
0x1800702fe  mov     rcx, [rbp+57h+var_28]
0x180070302  xor     rcx, rsp; StackCookie
0x180070305  call    __security_check_cookie
0x18007030a  mov     rbx, [rsp+100h+arg_18]
0x180070312  add     rsp, 0E0h
0x180070319  pop     r15
0x18007031b  pop     r14
0x18007031d  pop     r12
0x18007031f  pop     rsi
0x180070320  pop     rbp
0x180070321  retn
```
