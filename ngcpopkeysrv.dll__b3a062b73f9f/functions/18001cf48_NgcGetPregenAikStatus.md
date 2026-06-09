# NgcGetPregenAikStatus

- ea: `0x18001cf48`
- end: `0x18001d05d`
- name: `NgcGetPregenAikStatus`
- size: `277`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001608c`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x180010784`
- `0x180019784`
- `0x18001a944`
- `0x18001cf48`

## string_xrefs

- `0x18001d014`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall NgcGetPregenAikStatus(__int64 a1)
{
  _DWORD *v1; // r9
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-19h]
  int v6; // [rsp+30h] [rbp-9h] BYREF
  int v7[2]; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v8[2]; // [rsp+40h] [rbp+7h] BYREF
  __int16 v9; // [rsp+50h] [rbp+17h]
  int v10; // [rsp+58h] [rbp+1Fh] BYREF
  char v11; // [rsp+5Ch] [rbp+23h]
  char v12; // [rsp+60h] [rbp+27h] BYREF
  _DWORD v13[4]; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  __int64 v15; // [rsp+A0h] [rbp+67h] BYREF

  v15 = a1;
  v6 = 0;
  v10 = 0;
  v11 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v10);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v7[0] = v6;
    if ( v11 && (v13[0] || v13[1] || v13[2] || v13[3]) )
      v1 = v13;
    else
      LODWORD(v1) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)byte_18002EE61,
      (unsigned int)&v12,
      (_DWORD)v1,
      (__int64)v7);
  }
  v9 = 256;
  v8[0] = &v10;
  v8[1] = &v6;
  *(_QWORD *)v7 = &v15;
  v2 = HResultErrorContract__lambda_ae1d8ede72b8928ed4ee48978e64dbf4_(v7);
  v6 = v2;
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x327,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v2,
      v5);
  wil::details::ScopeExitFnGuard__lambda_5e64815bdff8998acb53aaf912b286c7___::operator()(v8);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v10);
  return v3;
}

```

## disassembly

```asm
0x18001cf48  mov     [rsp-8+arg_8], rbx
0x18001cf4d  mov     [rsp-8+arg_0], rcx
0x18001cf52  push    rbp
0x18001cf53  lea     rbp, [rsp-57h]
0x18001cf58  sub     rsp, 90h
0x18001cf5f  mov     rax, cs:__security_cookie
0x18001cf66  xor     rax, rsp
0x18001cf69  mov     [rbp+57h+var_10], rax
0x18001cf6d  lea     rcx, [rbp+57h+var_38]
0x18001cf71  mov     [rbp+57h+var_60], 0
0x18001cf78  mov     [rbp+57h+var_38], 0
0x18001cf7f  mov     [rbp+57h+var_34], 0
0x18001cf83  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001cf88  mov     eax, cs:dword_180037000
0x18001cf8e  cmp     eax, 5
0x18001cf91  jbe     short loc_18001CFE0
0x18001cf93  cmp     [rbp+57h+var_34], 0
0x18001cf97  mov     eax, [rbp+57h+var_60]
0x18001cf9a  mov     [rbp+57h+var_58], eax
0x18001cf9d  jz      short loc_18001CFBD
0x18001cf9f  cmp     [rbp+57h+var_20], 0
0x18001cfa3  jnz     short loc_18001CFB7
0x18001cfa5  cmp     [rbp+57h+var_1C], 0
0x18001cfa9  jnz     short loc_18001CFB7
0x18001cfab  cmp     [rbp+57h+var_18], 0
0x18001cfaf  jnz     short loc_18001CFB7
0x18001cfb1  cmp     [rbp+57h+var_14], 0
0x18001cfb5  jz      short loc_18001CFBD
0x18001cfb7  lea     r9, [rbp+57h+var_20]
0x18001cfbb  jmp     short loc_18001CFC0
0x18001cfbd  xor     r9d, r9d
0x18001cfc0  lea     rax, [rbp+57h+var_58]
0x18001cfc4  lea     r8, [rbp+57h+var_30]
0x18001cfc8  mov     qword ptr [rsp+90h+var_70], rax; int
0x18001cfcd  lea     rdx, byte_18002EE61
0x18001cfd4  lea     rcx, dword_180037000
0x18001cfdb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001cfe0  lea     rax, [rbp+57h+var_38]
0x18001cfe4  mov     [rbp+57h+var_40], 100h
0x18001cfea  mov     [rbp+57h+var_50], rax
0x18001cfee  lea     rcx, [rbp+57h+var_58]
0x18001cff2  lea     rax, [rbp+57h+var_60]
0x18001cff6  mov     [rbp+57h+var_48], rax
0x18001cffa  lea     rax, [rbp+57h+arg_0]
0x18001cffe  mov     qword ptr [rbp+57h+var_58], rax
0x18001d002  call    HResultErrorContract__lambda_ae1d8ede72b8928ed4ee48978e64dbf4___; HResultErrorContract__lambda_ae1d8ede72b8928ed4ee48978e64dbf4_
0x18001d007  mov     [rbp+57h+var_60], eax
0x18001d00a  mov     ebx, eax
0x18001d00c  test    eax, eax
0x18001d00e  jns     short loc_18001D02A
0x18001d010  mov     rcx, [rbp+5Fh]; this
0x18001d014  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d01b  mov     r9d, eax; char *
0x18001d01e  mov     edx, 327h; void *
0x18001d023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d028  jmp     short loc_18001D02C
0x18001d02a  xor     ebx, ebx
0x18001d02c  lea     rcx, [rbp+57h+var_50]
0x18001d030  call    wil__details__ScopeExitFnGuard__lambda_5e64815bdff8998acb53aaf912b286c7_____operator__
0x18001d035  lea     rcx, [rbp+57h+var_38]
0x18001d039  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001d03e  mov     eax, ebx
0x18001d040  mov     rcx, [rbp+57h+var_10]
0x18001d044  xor     rcx, rsp; StackCookie
0x18001d047  call    __security_check_cookie
0x18001d04c  mov     rbx, [rsp+90h+arg_8]
0x18001d054  add     rsp, 90h
0x18001d05b  pop     rbp
0x18001d05c  retn
```
