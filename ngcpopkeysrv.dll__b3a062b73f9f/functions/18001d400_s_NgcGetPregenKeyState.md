# s_NgcGetPregenKeyState

- ea: `0x18001d400`
- end: `0x18001d52d`
- name: `s_NgcGetPregenKeyState`
- size: `301`
- prototype: `__int64(int, int, ...)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x180010784`
- `0x1800196f4`
- `0x18001aac4`
- `0x18001d400`

## string_xrefs

- `0x18001d4eb`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 s_NgcGetPregenKeyState(int a1, int a2, ...)
{
  _DWORD *v2; // r9
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+28h] [rbp-39h]
  int v7; // [rsp+38h] [rbp-29h] BYREF
  int v8; // [rsp+3Ch] [rbp-25h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-21h] BYREF
  __int16 v10; // [rsp+50h] [rbp-11h]
  _QWORD v11[4]; // [rsp+58h] [rbp-9h] BYREF
  int v12; // [rsp+78h] [rbp+17h] BYREF
  char v13; // [rsp+7Ch] [rbp+1Bh]
  char v14; // [rsp+80h] [rbp+1Fh] BYREF
  _DWORD v15[4]; // [rsp+90h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  int v17; // [rsp+C8h] [rbp+67h] BYREF
  int v18; // [rsp+D0h] [rbp+6Fh] BYREF
  __int64 v19; // [rsp+D8h] [rbp+77h] BYREF
  va_list va; // [rsp+D8h] [rbp+77h]
  va_list va1; // [rsp+E0h] [rbp+7Fh] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v19 = va_arg(va1, _QWORD);
  v18 = a2;
  v17 = a1;
  v7 = 0;
  v12 = 0;
  v13 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v8 = v7;
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v2 = v15;
    else
      LODWORD(v2) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)byte_18002EF5B,
      (unsigned int)&v14,
      (_DWORD)v2,
      (__int64)&v8);
  }
  v10 = 256;
  v9[0] = &v12;
  v9[1] = &v7;
  va_copy((va_list)v11, va1);
  v11[1] = &v18;
  va_copy((va_list)&v11[2], va);
  v11[3] = &v17;
  v3 = HResultErrorContract__lambda_3cab1146f4d7b9a6ecad3714dfa4f1a4_(v11);
  v7 = v3;
  v4 = v3;
  if ( v3 >= 0 )
    v4 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F2,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v3,
      v6);
  wil::details::ScopeExitFnGuard__lambda_e44539bd0c4424472e3af783c1457ebc___::operator()(v9);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v12);
  return v4;
}

```

## disassembly

```asm
0x18001d400  mov     rax, rsp
0x18001d403  mov     [rax+20h], r9
0x18001d407  mov     [rax+18h], r8
0x18001d40b  mov     [rax+10h], edx
0x18001d40e  mov     [rax+8], ecx
0x18001d411  push    rbp
0x18001d412  push    rbx
0x18001d413  lea     rbp, [rax-5Fh]
0x18001d417  sub     rsp, 0A8h
0x18001d41e  mov     rax, cs:__security_cookie
0x18001d425  xor     rax, rsp
0x18001d428  mov     [rbp+57h+var_18], rax
0x18001d42c  lea     rcx, [rbp+57h+var_40]
0x18001d430  mov     [rbp+57h+var_80], 0
0x18001d437  mov     [rbp+57h+var_40], 0
0x18001d43e  mov     [rbp+57h+var_3C], 0
0x18001d442  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001d447  mov     eax, cs:dword_180037000
0x18001d44d  cmp     eax, 5
0x18001d450  jbe     short loc_18001D49F
0x18001d452  cmp     [rbp+57h+var_3C], 0
0x18001d456  mov     eax, [rbp+57h+var_80]
0x18001d459  mov     [rbp+57h+var_7C], eax
0x18001d45c  jz      short loc_18001D47C
0x18001d45e  cmp     [rbp+57h+var_28], 0
0x18001d462  jnz     short loc_18001D476
0x18001d464  cmp     [rbp+57h+var_24], 0
0x18001d468  jnz     short loc_18001D476
0x18001d46a  cmp     [rbp+57h+var_20], 0
0x18001d46e  jnz     short loc_18001D476
0x18001d470  cmp     [rbp+57h+var_1C], 0
0x18001d474  jz      short loc_18001D47C
0x18001d476  lea     r9, [rbp+57h+var_28]
0x18001d47a  jmp     short loc_18001D47F
0x18001d47c  xor     r9d, r9d
0x18001d47f  lea     rax, [rbp+57h+var_7C]
0x18001d483  lea     r8, [rbp+57h+var_38]
0x18001d487  mov     [rsp+20h], rax; int
0x18001d48c  lea     rdx, byte_18002EF5B
0x18001d493  lea     rcx, dword_180037000
0x18001d49a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d49f  lea     rax, [rbp+57h+var_40]
0x18001d4a3  mov     [rbp+57h+var_68], 100h
0x18001d4a9  mov     [rbp+57h+var_78], rax
0x18001d4ad  lea     rcx, [rbp+57h+var_60]
0x18001d4b1  lea     rax, [rbp+57h+var_80]
0x18001d4b5  mov     [rbp+57h+var_70], rax
0x18001d4b9  lea     rax, [rbp+57h+arg_18]
0x18001d4bd  mov     [rbp+57h+var_60], rax
0x18001d4c1  lea     rax, [rbp+57h+arg_8]
0x18001d4c5  mov     [rbp+57h+var_58], rax
0x18001d4c9  lea     rax, [rbp+57h+arg_10]
0x18001d4cd  mov     [rbp+57h+var_50], rax
0x18001d4d1  lea     rax, [rbp+57h+arg_0]
0x18001d4d5  mov     [rbp+57h+var_48], rax
0x18001d4d9  call    HResultErrorContract__lambda_3cab1146f4d7b9a6ecad3714dfa4f1a4___; HResultErrorContract__lambda_3cab1146f4d7b9a6ecad3714dfa4f1a4_
0x18001d4de  mov     [rbp+57h+var_80], eax
0x18001d4e1  mov     ebx, eax
0x18001d4e3  test    eax, eax
0x18001d4e5  jns     short loc_18001D501
0x18001d4e7  mov     rcx, [rbp+5Fh]; this
0x18001d4eb  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d4f2  mov     r9d, eax; char *
0x18001d4f5  mov     edx, 4F2h; void *
0x18001d4fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d4ff  jmp     short loc_18001D503
0x18001d501  xor     ebx, ebx
0x18001d503  lea     rcx, [rbp+57h+var_78]
0x18001d507  call    wil__details__ScopeExitFnGuard__lambda_e44539bd0c4424472e3af783c1457ebc_____operator__
0x18001d50c  lea     rcx, [rbp+57h+var_40]
0x18001d510  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001d515  mov     eax, ebx
0x18001d517  mov     rcx, [rbp+57h+var_18]
0x18001d51b  xor     rcx, rsp; StackCookie
0x18001d51e  call    __security_check_cookie
0x18001d523  add     rsp, 0A8h
0x18001d52a  pop     rbx
0x18001d52b  pop     rbp
0x18001d52c  retn
```
