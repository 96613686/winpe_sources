# NgcTriggerTask

- ea: `0x18001d2e0`
- end: `0x18001d3f4`
- name: `NgcTriggerTask`
- size: `276`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017070`
- `0x18001b950`
- `0x18001c2f8`
- `0x18001c508`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x180010784`
- `0x180019760`
- `0x18001a9c4`
- `0x18001d2e0`

## string_xrefs

- `0x18001d3ab`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall NgcTriggerTask(int a1)
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
  int v15; // [rsp+A0h] [rbp+67h] BYREF

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
      (unsigned int)byte_18002EE3B,
      (unsigned int)&v12,
      (_DWORD)v1,
      (__int64)v7);
  }
  v9 = 256;
  v8[0] = &v10;
  v8[1] = &v6;
  *(_QWORD *)v7 = &v15;
  v2 = HResultErrorContract__lambda_7cb16d85f13b972392f5d718b1048d71_(v7);
  v6 = v2;
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v2,
      v5);
  wil::details::ScopeExitFnGuard__lambda_c04bb3ef629b14bb6c561799a26918d2___::operator()(v8);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v10);
  return v3;
}

```

## disassembly

```asm
0x18001d2e0  mov     [rsp-8+arg_8], rbx
0x18001d2e5  mov     [rsp-8+arg_0], ecx
0x18001d2e9  push    rbp
0x18001d2ea  lea     rbp, [rsp-57h]
0x18001d2ef  sub     rsp, 90h
0x18001d2f6  mov     rax, cs:__security_cookie
0x18001d2fd  xor     rax, rsp
0x18001d300  mov     [rbp+57h+var_10], rax
0x18001d304  lea     rcx, [rbp+57h+var_38]
0x18001d308  mov     [rbp+57h+var_60], 0
0x18001d30f  mov     [rbp+57h+var_38], 0
0x18001d316  mov     [rbp+57h+var_34], 0
0x18001d31a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001d31f  mov     eax, cs:dword_180037000
0x18001d325  cmp     eax, 5
0x18001d328  jbe     short loc_18001D377
0x18001d32a  cmp     [rbp+57h+var_34], 0
0x18001d32e  mov     eax, [rbp+57h+var_60]
0x18001d331  mov     [rbp+57h+var_58], eax
0x18001d334  jz      short loc_18001D354
0x18001d336  cmp     [rbp+57h+var_20], 0
0x18001d33a  jnz     short loc_18001D34E
0x18001d33c  cmp     [rbp+57h+var_1C], 0
0x18001d340  jnz     short loc_18001D34E
0x18001d342  cmp     [rbp+57h+var_18], 0
0x18001d346  jnz     short loc_18001D34E
0x18001d348  cmp     [rbp+57h+var_14], 0
0x18001d34c  jz      short loc_18001D354
0x18001d34e  lea     r9, [rbp+57h+var_20]
0x18001d352  jmp     short loc_18001D357
0x18001d354  xor     r9d, r9d
0x18001d357  lea     rax, [rbp+57h+var_58]
0x18001d35b  lea     r8, [rbp+57h+var_30]
0x18001d35f  mov     qword ptr [rsp+90h+var_70], rax; int
0x18001d364  lea     rdx, byte_18002EE3B
0x18001d36b  lea     rcx, dword_180037000
0x18001d372  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d377  lea     rax, [rbp+57h+var_38]
0x18001d37b  mov     [rbp+57h+var_40], 100h
0x18001d381  mov     [rbp+57h+var_50], rax
0x18001d385  lea     rcx, [rbp+57h+var_58]
0x18001d389  lea     rax, [rbp+57h+var_60]
0x18001d38d  mov     [rbp+57h+var_48], rax
0x18001d391  lea     rax, [rbp+57h+arg_0]
0x18001d395  mov     qword ptr [rbp+57h+var_58], rax
0x18001d399  call    HResultErrorContract__lambda_7cb16d85f13b972392f5d718b1048d71___; HResultErrorContract__lambda_7cb16d85f13b972392f5d718b1048d71_
0x18001d39e  mov     [rbp+57h+var_60], eax
0x18001d3a1  mov     ebx, eax
0x18001d3a3  test    eax, eax
0x18001d3a5  jns     short loc_18001D3C1
0x18001d3a7  mov     rcx, [rbp+5Fh]; this
0x18001d3ab  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d3b2  mov     r9d, eax; char *
0x18001d3b5  mov     edx, 0B5h; void *
0x18001d3ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3bf  jmp     short loc_18001D3C3
0x18001d3c1  xor     ebx, ebx
0x18001d3c3  lea     rcx, [rbp+57h+var_50]
0x18001d3c7  call    wil__details__ScopeExitFnGuard__lambda_c04bb3ef629b14bb6c561799a26918d2_____operator__
0x18001d3cc  lea     rcx, [rbp+57h+var_38]
0x18001d3d0  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001d3d5  mov     eax, ebx
0x18001d3d7  mov     rcx, [rbp+57h+var_10]
0x18001d3db  xor     rcx, rsp; StackCookie
0x18001d3de  call    __security_check_cookie
0x18001d3e3  mov     rbx, [rsp+90h+arg_8]
0x18001d3eb  add     rsp, 90h
0x18001d3f2  pop     rbp
0x18001d3f3  retn
```
