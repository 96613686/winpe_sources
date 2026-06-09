# s_NgcDeleteTokenBindingAik

- ea: `0x180010de0`
- end: `0x180010f0e`
- name: `s_NgcDeleteTokenBindingAik`
- size: `302`
- prototype: `__int64(int, ...)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d60c`
- `0x18000da94`
- `0x180010234`
- `0x180010784`
- `0x180010de0`

## string_xrefs

- `0x180010ecc`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 s_NgcDeleteTokenBindingAik(int a1, ...)
{
  _DWORD *v1; // r9
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+28h] [rbp-39h]
  int v6; // [rsp+38h] [rbp-29h] BYREF
  int v7; // [rsp+3Ch] [rbp-25h] BYREF
  _QWORD v8[2]; // [rsp+40h] [rbp-21h] BYREF
  __int16 v9; // [rsp+50h] [rbp-11h]
  _QWORD v10[4]; // [rsp+58h] [rbp-9h] BYREF
  int v11; // [rsp+78h] [rbp+17h] BYREF
  char v12; // [rsp+7Ch] [rbp+1Bh]
  char v13; // [rsp+80h] [rbp+1Fh] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  int v16; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v17; // [rsp+D0h] [rbp+6Fh] BYREF
  va_list va; // [rsp+D0h] [rbp+6Fh]
  __int64 v19; // [rsp+D8h] [rbp+77h] BYREF
  va_list va1; // [rsp+D8h] [rbp+77h]
  va_list va2; // [rsp+E0h] [rbp+7Fh] BYREF

  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v17 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v19 = va_arg(va2, _QWORD);
  v16 = a1;
  v6 = 0;
  v11 = 0;
  v12 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v7 = v6;
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v1 = v14;
    else
      LODWORD(v1) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)byte_18002E8C5,
      (unsigned int)&v13,
      (_DWORD)v1,
      (__int64)&v7);
  }
  v9 = 256;
  v8[0] = &v11;
  v8[1] = &v6;
  va_copy((va_list)v10, va);
  va_copy((va_list)&v10[1], va1);
  v10[2] = &v16;
  va_copy((va_list)&v10[3], va2);
  v2 = HResultErrorContract__lambda_67f6ce2ec630c05f8afe91b269454bfa_(v10);
  v6 = v2;
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v2,
      v5);
  wil::details::ScopeExitFnGuard__lambda_60b5dabd42f897317e40b2371b7de3e4___::operator()(v8);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v11);
  return v3;
}

```

## disassembly

```asm
0x180010de0  mov     rax, rsp
0x180010de3  mov     [rax+20h], r9
0x180010de7  mov     [rax+18h], r8
0x180010deb  mov     [rax+10h], rdx
0x180010def  mov     [rax+8], ecx
0x180010df2  push    rbp
0x180010df3  push    rbx
0x180010df4  lea     rbp, [rax-5Fh]
0x180010df8  sub     rsp, 0A8h
0x180010dff  mov     rax, cs:__security_cookie
0x180010e06  xor     rax, rsp
0x180010e09  mov     [rbp+57h+var_18], rax
0x180010e0d  lea     rcx, [rbp+57h+var_40]
0x180010e11  mov     [rbp+57h+var_80], 0
0x180010e18  mov     [rbp+57h+var_40], 0
0x180010e1f  mov     [rbp+57h+var_3C], 0
0x180010e23  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180010e28  mov     eax, cs:dword_180037000
0x180010e2e  cmp     eax, 5
0x180010e31  jbe     short loc_180010E80
0x180010e33  cmp     [rbp+57h+var_3C], 0
0x180010e37  mov     eax, [rbp+57h+var_80]
0x180010e3a  mov     [rbp+57h+var_7C], eax
0x180010e3d  jz      short loc_180010E5D
0x180010e3f  cmp     [rbp+57h+var_28], 0
0x180010e43  jnz     short loc_180010E57
0x180010e45  cmp     [rbp+57h+var_24], 0
0x180010e49  jnz     short loc_180010E57
0x180010e4b  cmp     [rbp+57h+var_20], 0
0x180010e4f  jnz     short loc_180010E57
0x180010e51  cmp     [rbp+57h+var_1C], 0
0x180010e55  jz      short loc_180010E5D
0x180010e57  lea     r9, [rbp+57h+var_28]
0x180010e5b  jmp     short loc_180010E60
0x180010e5d  xor     r9d, r9d
0x180010e60  lea     rax, [rbp+57h+var_7C]
0x180010e64  lea     r8, [rbp+57h+var_38]
0x180010e68  mov     [rsp+20h], rax; int
0x180010e6d  lea     rdx, byte_18002E8C5
0x180010e74  lea     rcx, dword_180037000
0x180010e7b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010e80  lea     rax, [rbp+57h+var_40]
0x180010e84  mov     [rbp+57h+var_68], 100h
0x180010e8a  mov     [rbp+57h+var_78], rax
0x180010e8e  lea     rcx, [rbp+57h+var_60]
0x180010e92  lea     rax, [rbp+57h+var_80]
0x180010e96  mov     [rbp+57h+var_70], rax
0x180010e9a  lea     rax, [rbp+57h+arg_8]
0x180010e9e  mov     [rbp+57h+var_60], rax
0x180010ea2  lea     rax, [rbp+57h+arg_10]
0x180010ea6  mov     [rbp+57h+var_58], rax
0x180010eaa  lea     rax, [rbp+57h+arg_0]
0x180010eae  mov     [rbp+57h+var_50], rax
0x180010eb2  lea     rax, [rbp+57h+arg_18]
0x180010eb6  mov     [rbp+57h+var_48], rax
0x180010eba  call    HResultErrorContract__lambda_67f6ce2ec630c05f8afe91b269454bfa___; HResultErrorContract__lambda_67f6ce2ec630c05f8afe91b269454bfa_
0x180010ebf  mov     [rbp+57h+var_80], eax
0x180010ec2  mov     ebx, eax
0x180010ec4  test    eax, eax
0x180010ec6  jns     short loc_180010EE2
0x180010ec8  mov     rcx, [rbp+5Fh]; this
0x180010ecc  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180010ed3  mov     r9d, eax; char *
0x180010ed6  mov     edx, 6A0h; void *
0x180010edb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ee0  jmp     short loc_180010EE4
0x180010ee2  xor     ebx, ebx
0x180010ee4  lea     rcx, [rbp+57h+var_78]
0x180010ee8  call    wil__details__ScopeExitFnGuard__lambda_60b5dabd42f897317e40b2371b7de3e4_____operator__
0x180010eed  lea     rcx, [rbp+57h+var_40]
0x180010ef1  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180010ef6  mov     eax, ebx
0x180010ef8  mov     rcx, [rbp+57h+var_18]
0x180010efc  xor     rcx, rsp; StackCookie
0x180010eff  call    __security_check_cookie
0x180010f04  add     rsp, 0A8h
0x180010f0b  pop     rbx
0x180010f0c  pop     rbp
0x180010f0d  retn
```
