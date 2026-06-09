# NgcGetPregenKey

- ea: `0x18001d070`
- end: `0x18001d19d`
- name: `NgcGetPregenKey`
- size: `301`
- prototype: `__int64(int, int, ...)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180015410`
- `0x180017f60`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x180010784`
- `0x180019718`
- `0x18001a920`
- `0x18001d070`

## string_xrefs

- `0x18001d15b`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 NgcGetPregenKey(int a1, int a2, ...)
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
      (unsigned int)qword_18002EFB0,
      (unsigned int)&v14,
      (_DWORD)v2,
      (__int64)&v8);
  }
  v10 = 256;
  v9[0] = &v12;
  v9[1] = &v7;
  va_copy((va_list)v11, va1);
  va_copy((va_list)&v11[1], va);
  v11[2] = &v17;
  v11[3] = &v18;
  v3 = HResultErrorContract__lambda_3ecba38cd93d469d640ddbce294c6b00_(v11);
  v7 = v3;
  v4 = v3;
  if ( v3 >= 0 )
    v4 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v3,
      v6);
  wil::details::ScopeExitFnGuard__lambda_3d649c0c57be6174db255f6d066f5765___::operator()(v9);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v12);
  return v4;
}

```

## disassembly

```asm
0x18001d070  mov     rax, rsp
0x18001d073  mov     [rax+20h], r9
0x18001d077  mov     [rax+18h], r8
0x18001d07b  mov     [rax+10h], edx
0x18001d07e  mov     [rax+8], ecx
0x18001d081  push    rbp
0x18001d082  push    rbx
0x18001d083  lea     rbp, [rax-5Fh]
0x18001d087  sub     rsp, 0A8h
0x18001d08e  mov     rax, cs:__security_cookie
0x18001d095  xor     rax, rsp
0x18001d098  mov     [rbp+57h+var_18], rax
0x18001d09c  lea     rcx, [rbp+57h+var_40]
0x18001d0a0  mov     [rbp+57h+var_80], 0
0x18001d0a7  mov     [rbp+57h+var_40], 0
0x18001d0ae  mov     [rbp+57h+var_3C], 0
0x18001d0b2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001d0b7  mov     eax, cs:dword_180037000
0x18001d0bd  cmp     eax, 5
0x18001d0c0  jbe     short loc_18001D10F
0x18001d0c2  cmp     [rbp+57h+var_3C], 0
0x18001d0c6  mov     eax, [rbp+57h+var_80]
0x18001d0c9  mov     [rbp+57h+var_7C], eax
0x18001d0cc  jz      short loc_18001D0EC
0x18001d0ce  cmp     [rbp+57h+var_28], 0
0x18001d0d2  jnz     short loc_18001D0E6
0x18001d0d4  cmp     [rbp+57h+var_24], 0
0x18001d0d8  jnz     short loc_18001D0E6
0x18001d0da  cmp     [rbp+57h+var_20], 0
0x18001d0de  jnz     short loc_18001D0E6
0x18001d0e0  cmp     [rbp+57h+var_1C], 0
0x18001d0e4  jz      short loc_18001D0EC
0x18001d0e6  lea     r9, [rbp+57h+var_28]
0x18001d0ea  jmp     short loc_18001D0EF
0x18001d0ec  xor     r9d, r9d
0x18001d0ef  lea     rax, [rbp+57h+var_7C]
0x18001d0f3  lea     r8, [rbp+57h+var_38]
0x18001d0f7  mov     [rsp+20h], rax; int
0x18001d0fc  lea     rdx, qword_18002EFB0
0x18001d103  lea     rcx, dword_180037000
0x18001d10a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d10f  lea     rax, [rbp+57h+var_40]
0x18001d113  mov     [rbp+57h+var_68], 100h
0x18001d119  mov     [rbp+57h+var_78], rax
0x18001d11d  lea     rcx, [rbp+57h+var_60]
0x18001d121  lea     rax, [rbp+57h+var_80]
0x18001d125  mov     [rbp+57h+var_70], rax
0x18001d129  lea     rax, [rbp+57h+arg_18]
0x18001d12d  mov     [rbp+57h+var_60], rax
0x18001d131  lea     rax, [rbp+57h+arg_10]
0x18001d135  mov     [rbp+57h+var_58], rax
0x18001d139  lea     rax, [rbp+57h+arg_0]
0x18001d13d  mov     [rbp+57h+var_50], rax
0x18001d141  lea     rax, [rbp+57h+arg_8]
0x18001d145  mov     [rbp+57h+var_48], rax
0x18001d149  call    HResultErrorContract__lambda_3ecba38cd93d469d640ddbce294c6b00___; HResultErrorContract__lambda_3ecba38cd93d469d640ddbce294c6b00_
0x18001d14e  mov     [rbp+57h+var_80], eax
0x18001d151  mov     ebx, eax
0x18001d153  test    eax, eax
0x18001d155  jns     short loc_18001D171
0x18001d157  mov     rcx, [rbp+5Fh]; this
0x18001d15b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d162  mov     r9d, eax; char *
0x18001d165  mov     edx, 2EEh; void *
0x18001d16a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d16f  jmp     short loc_18001D173
0x18001d171  xor     ebx, ebx
0x18001d173  lea     rcx, [rbp+57h+var_78]
0x18001d177  call    wil__details__ScopeExitFnGuard__lambda_3d649c0c57be6174db255f6d066f5765_____operator__
0x18001d17c  lea     rcx, [rbp+57h+var_40]
0x18001d180  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001d185  mov     eax, ebx
0x18001d187  mov     rcx, [rbp+57h+var_18]
0x18001d18b  xor     rcx, rsp; StackCookie
0x18001d18e  call    __security_check_cookie
0x18001d193  add     rsp, 0A8h
0x18001d19a  pop     rbx
0x18001d19b  pop     rbp
0x18001d19c  retn
```
