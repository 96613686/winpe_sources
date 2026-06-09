# s_NgcGetKeyAttestationForContainerService

- ea: `0x180011270`
- end: `0x1800113b7`
- name: `s_NgcGetKeyAttestationForContainerService`
- size: `327`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d4ec`
- `0x18000da94`
- `0x18001039c`
- `0x180010784`
- `0x180011270`

## string_xrefs

- `0x180011375`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcGetKeyAttestationForContainerService(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        char a7)
{
  _DWORD *v7; // r9
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+28h] [rbp-71h]
  int v12; // [rsp+38h] [rbp-61h] BYREF
  int v13; // [rsp+3Ch] [rbp-5Dh] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-59h] BYREF
  __int16 v15; // [rsp+50h] [rbp-49h]
  _QWORD v16[7]; // [rsp+58h] [rbp-41h] BYREF
  int v17; // [rsp+90h] [rbp-9h] BYREF
  char v18; // [rsp+94h] [rbp-5h]
  char v19; // [rsp+98h] [rbp-1h] BYREF
  _DWORD v20[4]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+47h]
  __int64 v22; // [rsp+E8h] [rbp+4Fh] BYREF
  __int64 v23; // [rsp+F0h] [rbp+57h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+5Fh] BYREF
  __int64 v25; // [rsp+100h] [rbp+67h] BYREF

  v25 = a4;
  v24 = a3;
  v23 = a2;
  v22 = a1;
  v12 = 0;
  v17 = 0;
  v18 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v17);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v13 = v12;
    if ( v18 && (v20[0] || v20[1] || v20[2] || v20[3]) )
      v7 = v20;
    else
      LODWORD(v7) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&unk_18002E818,
      (unsigned int)&v19,
      (_DWORD)v7,
      (__int64)&v13);
  }
  v15 = 256;
  v14[0] = &v17;
  v14[1] = &v12;
  v16[0] = &v22;
  v16[1] = &v23;
  v16[2] = &a7;
  v16[3] = &v24;
  v16[4] = &v25;
  v16[5] = &a5;
  v16[6] = &a6;
  v8 = HResultErrorContract__lambda_2d285ae78f09685cc1f8f3d41017e515_(v16);
  v12 = v8;
  v9 = v8;
  if ( v8 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v8,
      v11);
  wil::details::ScopeExitFnGuard__lambda_d938933ed60a48fde63e9688af366884___::operator()(v14);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v17);
  return v9;
}

```

## disassembly

```asm
0x180011270  mov     rax, rsp
0x180011273  mov     [rax+20h], r9
0x180011277  mov     [rax+18h], r8
0x18001127b  mov     [rax+10h], rdx
0x18001127f  mov     [rax+8], rcx
0x180011283  push    rbp
0x180011284  push    rbx
0x180011285  lea     rbp, [rax-47h]
0x180011289  sub     rsp, 0C8h
0x180011290  mov     rax, cs:__security_cookie
0x180011297  xor     rax, rsp
0x18001129a  mov     [rbp+3Fh+var_20], rax
0x18001129e  lea     rcx, [rbp+3Fh+var_48]
0x1800112a2  mov     [rbp+3Fh+var_A0], 0
0x1800112a9  mov     [rbp+3Fh+var_48], 0
0x1800112b0  mov     [rbp+3Fh+var_44], 0
0x1800112b4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800112b9  mov     eax, cs:dword_180037000
0x1800112bf  cmp     eax, 5
0x1800112c2  jbe     short loc_180011311
0x1800112c4  cmp     [rbp+3Fh+var_44], 0
0x1800112c8  mov     eax, [rbp+3Fh+var_A0]
0x1800112cb  mov     [rbp+3Fh+var_9C], eax
0x1800112ce  jz      short loc_1800112EE
0x1800112d0  cmp     [rbp+3Fh+var_30], 0
0x1800112d4  jnz     short loc_1800112E8
0x1800112d6  cmp     [rbp+3Fh+var_2C], 0
0x1800112da  jnz     short loc_1800112E8
0x1800112dc  cmp     [rbp+3Fh+var_28], 0
0x1800112e0  jnz     short loc_1800112E8
0x1800112e2  cmp     [rbp+3Fh+var_24], 0
0x1800112e6  jz      short loc_1800112EE
0x1800112e8  lea     r9, [rbp+3Fh+var_30]
0x1800112ec  jmp     short loc_1800112F1
0x1800112ee  xor     r9d, r9d
0x1800112f1  lea     rax, [rbp+3Fh+var_9C]
0x1800112f5  lea     r8, [rbp+3Fh+var_40]
0x1800112f9  mov     [rsp+20h], rax; int
0x1800112fe  lea     rdx, unk_18002E818
0x180011305  lea     rcx, dword_180037000
0x18001130c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011311  lea     rax, [rbp+3Fh+var_48]
0x180011315  mov     [rbp+3Fh+var_88], 100h
0x18001131b  mov     [rbp+3Fh+var_98], rax
0x18001131f  lea     rcx, [rbp+3Fh+var_80]
0x180011323  lea     rax, [rbp+3Fh+var_A0]
0x180011327  mov     [rbp+3Fh+var_90], rax
0x18001132b  lea     rax, [rbp+3Fh+arg_0]
0x18001132f  mov     [rbp+3Fh+var_80], rax
0x180011333  lea     rax, [rbp+3Fh+arg_8]
0x180011337  mov     [rbp+3Fh+var_78], rax
0x18001133b  lea     rax, [rbp+3Fh+arg_30]
0x18001133f  mov     [rbp+3Fh+var_70], rax
0x180011343  lea     rax, [rbp+3Fh+arg_10]
0x180011347  mov     [rbp+3Fh+var_68], rax
0x18001134b  lea     rax, [rbp+3Fh+arg_18]
0x18001134f  mov     [rbp+3Fh+var_60], rax
0x180011353  lea     rax, [rbp+3Fh+arg_20]
0x180011357  mov     [rbp+3Fh+var_58], rax
0x18001135b  lea     rax, [rbp+3Fh+arg_28]
0x18001135f  mov     [rbp+3Fh+var_50], rax
0x180011363  call    HResultErrorContract__lambda_2d285ae78f09685cc1f8f3d41017e515___; HResultErrorContract__lambda_2d285ae78f09685cc1f8f3d41017e515_
0x180011368  mov     [rbp+3Fh+var_A0], eax
0x18001136b  mov     ebx, eax
0x18001136d  test    eax, eax
0x18001136f  jns     short loc_18001138B
0x180011371  mov     rcx, [rbp+47h]; this
0x180011375  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001137c  mov     r9d, eax; char *
0x18001137f  mov     edx, 3CEh; void *
0x180011384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011389  jmp     short loc_18001138D
0x18001138b  xor     ebx, ebx
0x18001138d  lea     rcx, [rbp+3Fh+var_98]
0x180011391  call    wil__details__ScopeExitFnGuard__lambda_d938933ed60a48fde63e9688af366884_____operator__
0x180011396  lea     rcx, [rbp+3Fh+var_48]
0x18001139a  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001139f  mov     eax, ebx
0x1800113a1  mov     rcx, [rbp+3Fh+var_20]
0x1800113a5  xor     rcx, rsp; StackCookie
0x1800113a8  call    __security_check_cookie
0x1800113ad  add     rsp, 0C8h
0x1800113b4  pop     rbx
0x1800113b5  pop     rbp
0x1800113b6  retn
```
