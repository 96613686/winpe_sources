# s_NgcRenewKeyAttestation

- ea: `0x1800119b0`
- end: `0x180011adf`
- name: `s_NgcRenewKeyAttestation`
- size: `303`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d4c8`
- `0x18000da94`
- `0x1800101c8`
- `0x180010784`
- `0x1800119b0`

## string_xrefs

- `0x180011a9d`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcRenewKeyAttestation(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _DWORD *v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+28h] [rbp-39h]
  int v9; // [rsp+38h] [rbp-29h] BYREF
  int v10; // [rsp+3Ch] [rbp-25h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-21h] BYREF
  __int16 v12; // [rsp+50h] [rbp-11h]
  _QWORD v13[4]; // [rsp+58h] [rbp-9h] BYREF
  int v14; // [rsp+78h] [rbp+17h] BYREF
  char v15; // [rsp+7Ch] [rbp+1Bh]
  char v16; // [rsp+80h] [rbp+1Fh] BYREF
  _DWORD v17[4]; // [rsp+90h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  __int64 v19; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v20; // [rsp+D0h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+D8h] [rbp+77h] BYREF
  int v22; // [rsp+E0h] [rbp+7Fh] BYREF

  v22 = a4;
  v21 = a3;
  v20 = a2;
  v19 = a1;
  v9 = 0;
  v14 = 0;
  v15 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v10 = v9;
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v4 = v17;
    else
      LODWORD(v4) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)byte_18002E481,
      (unsigned int)&v16,
      (_DWORD)v4,
      (__int64)&v10);
  }
  v12 = 256;
  v11[0] = &v14;
  v11[1] = &v9;
  v13[0] = &v19;
  v13[1] = &v22;
  v13[2] = &v21;
  v13[3] = &v20;
  v5 = HResultErrorContract__lambda_285684952c41a549ce42762e6e7efc17_(v13);
  v9 = v5;
  v6 = v5;
  if ( v5 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v5,
      v8);
  wil::details::ScopeExitFnGuard__lambda_399108a49a74f8ea8f17f639d811f972___::operator()(v11);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v14);
  return v6;
}

```

## disassembly

```asm
0x1800119b0  mov     rax, rsp
0x1800119b3  mov     [rax+20h], r9d
0x1800119b7  mov     [rax+18h], r8
0x1800119bb  mov     [rax+10h], rdx
0x1800119bf  mov     [rax+8], rcx
0x1800119c3  push    rbp
0x1800119c4  push    rbx
0x1800119c5  lea     rbp, [rax-5Fh]
0x1800119c9  sub     rsp, 0A8h
0x1800119d0  mov     rax, cs:__security_cookie
0x1800119d7  xor     rax, rsp
0x1800119da  mov     [rbp+57h+var_18], rax
0x1800119de  lea     rcx, [rbp+57h+var_40]
0x1800119e2  mov     [rbp+57h+var_80], 0
0x1800119e9  mov     [rbp+57h+var_40], 0
0x1800119f0  mov     [rbp+57h+var_3C], 0
0x1800119f4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800119f9  mov     eax, cs:dword_180037000
0x1800119ff  cmp     eax, 5
0x180011a02  jbe     short loc_180011A51
0x180011a04  cmp     [rbp+57h+var_3C], 0
0x180011a08  mov     eax, [rbp+57h+var_80]
0x180011a0b  mov     [rbp+57h+var_7C], eax
0x180011a0e  jz      short loc_180011A2E
0x180011a10  cmp     [rbp+57h+var_28], 0
0x180011a14  jnz     short loc_180011A28
0x180011a16  cmp     [rbp+57h+var_24], 0
0x180011a1a  jnz     short loc_180011A28
0x180011a1c  cmp     [rbp+57h+var_20], 0
0x180011a20  jnz     short loc_180011A28
0x180011a22  cmp     [rbp+57h+var_1C], 0
0x180011a26  jz      short loc_180011A2E
0x180011a28  lea     r9, [rbp+57h+var_28]
0x180011a2c  jmp     short loc_180011A31
0x180011a2e  xor     r9d, r9d
0x180011a31  lea     rax, [rbp+57h+var_7C]
0x180011a35  lea     r8, [rbp+57h+var_38]
0x180011a39  mov     [rsp+20h], rax; int
0x180011a3e  lea     rdx, byte_18002E481
0x180011a45  lea     rcx, dword_180037000
0x180011a4c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011a51  lea     rax, [rbp+57h+var_40]
0x180011a55  mov     [rbp+57h+var_68], 100h
0x180011a5b  mov     [rbp+57h+var_78], rax
0x180011a5f  lea     rcx, [rbp+57h+var_60]
0x180011a63  lea     rax, [rbp+57h+var_80]
0x180011a67  mov     [rbp+57h+var_70], rax
0x180011a6b  lea     rax, [rbp+57h+arg_0]
0x180011a6f  mov     [rbp+57h+var_60], rax
0x180011a73  lea     rax, [rbp+57h+arg_18]
0x180011a77  mov     [rbp+57h+var_58], rax
0x180011a7b  lea     rax, [rbp+57h+arg_10]
0x180011a7f  mov     [rbp+57h+var_50], rax
0x180011a83  lea     rax, [rbp+57h+arg_8]
0x180011a87  mov     [rbp+57h+var_48], rax
0x180011a8b  call    HResultErrorContract__lambda_285684952c41a549ce42762e6e7efc17___; HResultErrorContract__lambda_285684952c41a549ce42762e6e7efc17_
0x180011a90  mov     [rbp+57h+var_80], eax
0x180011a93  mov     ebx, eax
0x180011a95  test    eax, eax
0x180011a97  jns     short loc_180011AB3
0x180011a99  mov     rcx, [rbp+5Fh]; this
0x180011a9d  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180011aa4  mov     r9d, eax; char *
0x180011aa7  mov     edx, 3F1h; void *
0x180011aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ab1  jmp     short loc_180011AB5
0x180011ab3  xor     ebx, ebx
0x180011ab5  lea     rcx, [rbp+57h+var_78]
0x180011ab9  call    wil__details__ScopeExitFnGuard__lambda_399108a49a74f8ea8f17f639d811f972_____operator__
0x180011abe  lea     rcx, [rbp+57h+var_40]
0x180011ac2  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180011ac7  mov     eax, ebx
0x180011ac9  mov     rcx, [rbp+57h+var_18]
0x180011acd  xor     rcx, rsp; StackCookie
0x180011ad0  call    __security_check_cookie
0x180011ad5  add     rsp, 0A8h
0x180011adc  pop     rbx
0x180011add  pop     rbp
0x180011ade  retn
```
