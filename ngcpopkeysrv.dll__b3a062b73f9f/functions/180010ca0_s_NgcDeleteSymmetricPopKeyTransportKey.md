# s_NgcDeleteSymmetricPopKeyTransportKey

- ea: `0x180010ca0`
- end: `0x180010dcd`
- name: `s_NgcDeleteSymmetricPopKeyTransportKey`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d558`
- `0x18000da94`
- `0x180010354`
- `0x180010784`
- `0x180010ca0`

## string_xrefs

- `0x180010d84`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcDeleteSymmetricPopKeyTransportKey(__int64 a1, __int64 a2, int a3)
{
  _DWORD *v3; // r9
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+28h] [rbp-29h]
  int v8; // [rsp+38h] [rbp-19h] BYREF
  int v9; // [rsp+3Ch] [rbp-15h] BYREF
  _QWORD v10[2]; // [rsp+40h] [rbp-11h] BYREF
  __int16 v11; // [rsp+50h] [rbp-1h]
  _QWORD v12[3]; // [rsp+58h] [rbp+7h] BYREF
  int v13; // [rsp+70h] [rbp+1Fh] BYREF
  char v14; // [rsp+74h] [rbp+23h]
  char v15; // [rsp+78h] [rbp+27h] BYREF
  _DWORD v16[4]; // [rsp+88h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]
  __int64 v18; // [rsp+B8h] [rbp+67h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+6Fh] BYREF
  int v20; // [rsp+C8h] [rbp+77h] BYREF

  v20 = a3;
  v19 = a2;
  v18 = a1;
  v8 = 0;
  v13 = 0;
  v14 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v9 = v8;
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v3 = v16;
    else
      LODWORD(v3) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&byte_18002E3AF,
      (unsigned int)&v15,
      (_DWORD)v3,
      (__int64)&v9);
  }
  v11 = 256;
  v10[0] = &v13;
  v10[1] = &v8;
  v12[0] = &v18;
  v12[1] = &v20;
  v12[2] = &v19;
  v4 = HResultErrorContract__lambda_56f8b042f69a69797ce862124663e406_(v12);
  v8 = v4;
  v5 = v4;
  if ( v4 >= 0 )
    v5 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x396,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v4,
      v7);
  wil::details::ScopeExitFnGuard__lambda_cd0b8cc3e79890bc5f57c7e6c0941029___::operator()(v10);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180010ca0  mov     rax, rsp
0x180010ca3  mov     [rax+20h], rbx
0x180010ca7  mov     [rax+18h], r8d
0x180010cab  mov     [rax+10h], rdx
0x180010caf  mov     [rax+8], rcx
0x180010cb3  push    rbp
0x180010cb4  lea     rbp, [rax-5Fh]
0x180010cb8  sub     rsp, 0A0h
0x180010cbf  mov     rax, cs:__security_cookie
0x180010cc6  xor     rax, rsp
0x180010cc9  mov     [rbp+57h+var_10], rax
0x180010ccd  lea     rcx, [rbp+57h+var_38]
0x180010cd1  mov     [rbp+57h+var_70], 0
0x180010cd8  mov     [rbp+57h+var_38], 0
0x180010cdf  mov     [rbp+57h+var_34], 0
0x180010ce3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180010ce8  mov     eax, cs:dword_180037000
0x180010cee  cmp     eax, 5
0x180010cf1  jbe     short loc_180010D40
0x180010cf3  cmp     [rbp+57h+var_34], 0
0x180010cf7  mov     eax, [rbp+57h+var_70]
0x180010cfa  mov     [rbp+57h+var_6C], eax
0x180010cfd  jz      short loc_180010D1D
0x180010cff  cmp     [rbp+57h+var_20], 0
0x180010d03  jnz     short loc_180010D17
0x180010d05  cmp     [rbp+57h+var_1C], 0
0x180010d09  jnz     short loc_180010D17
0x180010d0b  cmp     [rbp+57h+var_18], 0
0x180010d0f  jnz     short loc_180010D17
0x180010d11  cmp     [rbp+57h+var_14], 0
0x180010d15  jz      short loc_180010D1D
0x180010d17  lea     r9, [rbp+57h+var_20]
0x180010d1b  jmp     short loc_180010D20
0x180010d1d  xor     r9d, r9d
0x180010d20  lea     rax, [rbp+57h+var_6C]
0x180010d24  lea     r8, [rbp+57h+var_30]
0x180010d28  mov     [rsp+20h], rax; int
0x180010d2d  lea     rdx, byte_18002E3AF
0x180010d34  lea     rcx, dword_180037000
0x180010d3b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010d40  lea     rax, [rbp+57h+var_38]
0x180010d44  mov     [rbp+57h+var_58], 100h
0x180010d4a  mov     [rbp+57h+var_68], rax
0x180010d4e  lea     rcx, [rbp+57h+var_50]
0x180010d52  lea     rax, [rbp+57h+var_70]
0x180010d56  mov     [rbp+57h+var_60], rax
0x180010d5a  lea     rax, [rbp+57h+arg_0]
0x180010d5e  mov     [rbp+57h+var_50], rax
0x180010d62  lea     rax, [rbp+57h+arg_10]
0x180010d66  mov     [rbp+57h+var_48], rax
0x180010d6a  lea     rax, [rbp+57h+arg_8]
0x180010d6e  mov     [rbp+57h+var_40], rax
0x180010d72  call    HResultErrorContract__lambda_56f8b042f69a69797ce862124663e406___; HResultErrorContract__lambda_56f8b042f69a69797ce862124663e406_
0x180010d77  mov     [rbp+57h+var_70], eax
0x180010d7a  mov     ebx, eax
0x180010d7c  test    eax, eax
0x180010d7e  jns     short loc_180010D9A
0x180010d80  mov     rcx, [rbp+5Fh]; this
0x180010d84  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180010d8b  mov     r9d, eax; char *
0x180010d8e  mov     edx, 396h; void *
0x180010d93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d98  jmp     short loc_180010D9C
0x180010d9a  xor     ebx, ebx
0x180010d9c  lea     rcx, [rbp+57h+var_68]
0x180010da0  call    wil__details__ScopeExitFnGuard__lambda_cd0b8cc3e79890bc5f57c7e6c0941029_____operator__
0x180010da5  lea     rcx, [rbp+57h+var_38]
0x180010da9  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180010dae  mov     eax, ebx
0x180010db0  mov     rcx, [rbp+57h+var_10]
0x180010db4  xor     rcx, rsp; StackCookie
0x180010db7  call    __security_check_cookie
0x180010dbc  mov     rbx, [rsp+0A0h+arg_18]
0x180010dc4  add     rsp, 0A0h
0x180010dcb  pop     rbp
0x180010dcc  retn
```
