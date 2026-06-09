# NgcPregenKey

- ea: `0x18001d1b0`
- end: `0x18001d2cc`
- name: `NgcPregenKey`
- size: `284`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x180010784`
- `0x1800196d0`
- `0x18001a8fc`
- `0x18001d1b0`

## string_xrefs

- `0x18001d283`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall NgcPregenKey(int a1)
{
  _DWORD *v1; // r9
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-19h]
  int v6; // [rsp+30h] [rbp-9h] BYREF
  int v7; // [rsp+34h] [rbp-5h] BYREF
  _QWORD v8[2]; // [rsp+38h] [rbp-1h] BYREF
  __int16 v9; // [rsp+48h] [rbp+Fh]
  _QWORD v10[2]; // [rsp+50h] [rbp+17h] BYREF
  int v11; // [rsp+60h] [rbp+27h] BYREF
  char v12; // [rsp+64h] [rbp+2Bh]
  char v13; // [rsp+68h] [rbp+2Fh] BYREF
  _DWORD v14[4]; // [rsp+78h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  int v16; // [rsp+A0h] [rbp+67h] BYREF

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
      (unsigned int)&dword_18002F004,
      (unsigned int)&v13,
      (_DWORD)v1,
      (__int64)&v7);
  }
  v9 = 256;
  v8[0] = &v11;
  v8[1] = &v6;
  v10[0] = &v16;
  v10[1] = &v6;
  v2 = HResultErrorContract__lambda_250071e98a8b1632271e3444950df57f_(v10);
  v6 = v2;
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v2,
      v5);
  wil::details::ScopeExitFnGuard__lambda_38e7339d7c783d2b1c4ccfd4aafa318c___::operator()(v8);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v11);
  return v3;
}

```

## disassembly

```asm
0x18001d1b0  mov     [rsp-8+arg_8], rbx
0x18001d1b5  mov     [rsp-8+arg_0], ecx
0x18001d1b9  push    rbp
0x18001d1ba  lea     rbp, [rsp-57h]
0x18001d1bf  sub     rsp, 90h
0x18001d1c6  mov     rax, cs:__security_cookie
0x18001d1cd  xor     rax, rsp
0x18001d1d0  mov     [rbp+57h+var_8], rax
0x18001d1d4  lea     rcx, [rbp+57h+var_30]
0x18001d1d8  mov     [rbp+57h+var_60], 0
0x18001d1df  mov     [rbp+57h+var_30], 0
0x18001d1e6  mov     [rbp+57h+var_2C], 0
0x18001d1ea  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001d1ef  mov     eax, cs:dword_180037000
0x18001d1f5  cmp     eax, 5
0x18001d1f8  jbe     short loc_18001D247
0x18001d1fa  cmp     [rbp+57h+var_2C], 0
0x18001d1fe  mov     eax, [rbp+57h+var_60]
0x18001d201  mov     [rbp+57h+var_5C], eax
0x18001d204  jz      short loc_18001D224
0x18001d206  cmp     [rbp+57h+var_18], 0
0x18001d20a  jnz     short loc_18001D21E
0x18001d20c  cmp     [rbp+57h+var_14], 0
0x18001d210  jnz     short loc_18001D21E
0x18001d212  cmp     [rbp+57h+var_10], 0
0x18001d216  jnz     short loc_18001D21E
0x18001d218  cmp     [rbp+57h+var_C], 0
0x18001d21c  jz      short loc_18001D224
0x18001d21e  lea     r9, [rbp+57h+var_18]
0x18001d222  jmp     short loc_18001D227
0x18001d224  xor     r9d, r9d
0x18001d227  lea     rax, [rbp+57h+var_5C]
0x18001d22b  lea     r8, [rbp+57h+var_28]
0x18001d22f  mov     qword ptr [rsp+90h+var_70], rax; int
0x18001d234  lea     rdx, dword_18002F004
0x18001d23b  lea     rcx, dword_180037000
0x18001d242  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d247  lea     rax, [rbp+57h+var_30]
0x18001d24b  mov     [rbp+57h+var_48], 100h
0x18001d251  mov     [rbp+57h+var_58], rax
0x18001d255  lea     rcx, [rbp+57h+var_40]
0x18001d259  lea     rax, [rbp+57h+var_60]
0x18001d25d  mov     [rbp+57h+var_50], rax
0x18001d261  lea     rax, [rbp+57h+arg_0]
0x18001d265  mov     [rbp+57h+var_40], rax
0x18001d269  lea     rax, [rbp+57h+var_60]
0x18001d26d  mov     [rbp+57h+var_38], rax
0x18001d271  call    HResultErrorContract__lambda_250071e98a8b1632271e3444950df57f___; HResultErrorContract__lambda_250071e98a8b1632271e3444950df57f_
0x18001d276  mov     [rbp+57h+var_60], eax
0x18001d279  mov     ebx, eax
0x18001d27b  test    eax, eax
0x18001d27d  jns     short loc_18001D299
0x18001d27f  mov     rcx, [rbp+5Fh]; this
0x18001d283  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d28a  mov     r9d, eax; char *
0x18001d28d  mov     edx, 82Ah; void *
0x18001d292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d297  jmp     short loc_18001D29B
0x18001d299  xor     ebx, ebx
0x18001d29b  lea     rcx, [rbp+57h+var_58]
0x18001d29f  call    wil__details__ScopeExitFnGuard__lambda_38e7339d7c783d2b1c4ccfd4aafa318c_____operator__
0x18001d2a4  lea     rcx, [rbp+57h+var_30]
0x18001d2a8  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001d2ad  mov     eax, ebx
0x18001d2af  mov     rcx, [rbp+57h+var_8]
0x18001d2b3  xor     rcx, rsp; StackCookie
0x18001d2b6  call    __security_check_cookie
0x18001d2bb  mov     rbx, [rsp+90h+arg_8]
0x18001d2c3  add     rsp, 90h
0x18001d2ca  pop     rbp
0x18001d2cb  retn
```
