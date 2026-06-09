# CNgcTasksHandler::Worker(void)

- ea: `0x1800149c0`
- end: `0x180014ad8`
- name: `?Worker@CNgcTasksHandler@@EEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CNgcTasksHandler *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e70`
- `0x180006330`
- `0x18000cc34`
- `0x18000ec2c`
- `0x18000fbc4`
- `0x18000fe50`
- `0x180010178`
- `0x180011464`
- `0x1800149c0`
- `0x180015060`

## string_xrefs

- `0x180014a86`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
__int64 __fastcall CNgcTasksHandler::Worker(CNgcTasksHandler *this)
{
  struct _GUID *v2; // r9
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-29h]
  int v7; // [rsp+30h] [rbp-19h] BYREF
  int v8[2]; // [rsp+38h] [rbp-11h] BYREF
  int *v9; // [rsp+40h] [rbp-9h]
  _BYTE v10[24]; // [rsp+50h] [rbp+7h] BYREF
  int v11; // [rsp+68h] [rbp+1Fh] BYREF
  char v12; // [rsp+6Ch] [rbp+23h]
  char v13; // [rsp+70h] [rbp+27h] BYREF
  struct _GUID v14; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v7 = 0;
  v11 = 0;
  v12 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180031038 > 5 )
  {
    v8[0] = v7;
    if ( !v12 || _tlgGuidIsZero(&v14) )
      LODWORD(v2) = 0;
    else
      v2 = &v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180031038,
      (unsigned int)byte_180029689,
      (unsigned int)&v13,
      (_DWORD)v2,
      (__int64)v8);
  }
  *(_QWORD *)v8 = &v11;
  v9 = &v7;
  wil::ScopeExitIgnore__lambda_80dc3ccc7eefa5fa3bfb0c6b9944ad5d___(v10, v8);
  *(_QWORD *)v8 = this;
  v3 = HResultErrorContract__lambda_cc831c91b53458fb9833aae4c24a5007_(v8);
  v4 = v3;
  v7 = v3;
  if ( v3 >= 0 )
  {
    wil::details::ScopeExitFnGuard__lambda_80dc3ccc7eefa5fa3bfb0c6b9944ad5d___::operator()(v10);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x678,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v3,
      v6);
    wil::details::ScopeExitFnGuard__lambda_80dc3ccc7eefa5fa3bfb0c6b9944ad5d___::operator()(v10);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v11);
  return v4;
}

```

## disassembly

```asm
0x1800149c0  mov     [rsp-8+arg_0], rbx
0x1800149c5  push    rbp
0x1800149c6  lea     rbp, [rsp-57h]
0x1800149cb  sub     rsp, 0A0h
0x1800149d2  mov     rax, cs:__security_cookie
0x1800149d9  xor     rax, rsp
0x1800149dc  mov     [rbp+57h+var_10], rax
0x1800149e0  mov     rbx, rcx
0x1800149e3  mov     [rbp+57h+var_70], 0
0x1800149ea  mov     [rbp+57h+var_38], 0
0x1800149f1  mov     [rbp+57h+var_34], 0
0x1800149f5  lea     rcx, [rbp+57h+var_38]
0x1800149f9  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800149fe  mov     eax, cs:dword_180031038
0x180014a04  cmp     eax, 5
0x180014a07  jbe     short loc_180014A4B
0x180014a09  mov     eax, [rbp+57h+var_70]
0x180014a0c  mov     [rbp+57h+var_68], eax
0x180014a0f  cmp     [rbp+57h+var_34], 0
0x180014a13  jz      short loc_180014A28
0x180014a15  lea     rcx, [rbp+57h+var_20]; struct _GUID *
0x180014a19  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180014a1e  test    al, al
0x180014a20  jnz     short loc_180014A28
0x180014a22  lea     r9, [rbp+57h+var_20]
0x180014a26  jmp     short loc_180014A2B
0x180014a28  xor     r9d, r9d
0x180014a2b  lea     rax, [rbp+57h+var_68]
0x180014a2f  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180014a34  lea     r8, [rbp+57h+var_30]
0x180014a38  lea     rdx, byte_180029689
0x180014a3f  lea     rcx, dword_180031038
0x180014a46  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180014a4b  lea     rax, [rbp+57h+var_38]
0x180014a4f  mov     qword ptr [rbp+57h+var_68], rax
0x180014a53  lea     rax, [rbp+57h+var_70]
0x180014a57  mov     [rbp+57h+var_60], rax
0x180014a5b  lea     rdx, [rbp+57h+var_68]
0x180014a5f  lea     rcx, [rbp+57h+var_50]
0x180014a63  call    wil__ScopeExitIgnore__lambda_80dc3ccc7eefa5fa3bfb0c6b9944ad5d___
0x180014a68  nop
0x180014a69  mov     qword ptr [rbp+57h+var_68], rbx
0x180014a6d  lea     rcx, [rbp+57h+var_68]
0x180014a71  call    HResultErrorContract__lambda_cc831c91b53458fb9833aae4c24a5007___; HResultErrorContract__lambda_cc831c91b53458fb9833aae4c24a5007_
0x180014a76  mov     ebx, eax
0x180014a78  mov     [rbp+57h+var_70], eax
0x180014a7b  test    eax, eax
0x180014a7d  jns     short loc_180014AA4
0x180014a7f  mov     rcx, [rbp+5Fh]; this
0x180014a83  mov     r9d, eax; char *
0x180014a86  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014a8d  mov     edx, 678h; void *
0x180014a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a97  nop
0x180014a98  lea     rcx, [rbp+57h+var_50]
0x180014a9c  call    wil__details__ScopeExitFnGuard__lambda_80dc3ccc7eefa5fa3bfb0c6b9944ad5d_____operator__
0x180014aa1  nop
0x180014aa2  jmp     short loc_180014AB0
0x180014aa4  lea     rcx, [rbp+57h+var_50]
0x180014aa8  call    wil__details__ScopeExitFnGuard__lambda_80dc3ccc7eefa5fa3bfb0c6b9944ad5d_____operator__
0x180014aad  nop
0x180014aae  xor     ebx, ebx
0x180014ab0  lea     rcx, [rbp+57h+var_38]
0x180014ab4  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180014ab9  mov     eax, ebx
0x180014abb  mov     rcx, [rbp+57h+var_10]
0x180014abf  xor     rcx, rsp; StackCookie
0x180014ac2  call    __security_check_cookie
0x180014ac7  mov     rbx, [rsp+0A0h+arg_0]
0x180014acf  add     rsp, 0A0h
0x180014ad6  pop     rbp
0x180014ad7  retn
```
