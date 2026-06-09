# s_NgcGetPregenUserKey

- ea: `0x18001d540`
- end: `0x18001d6b5`
- name: `s_NgcGetPregenUserKey`
- size: `373`
- prototype: `__int64(int, int, ...)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x180010784`
- `0x18001973c`
- `0x18001a9e8`
- `0x18001aa0c`
- `0x18001d540`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d573`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d573`

## string_xrefs

- `0x18001d66a`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 s_NgcGetPregenUserKey(int a1, int a2, ...)
{
  DWORD TickCount; // eax
  _DWORD *v3; // r9
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+28h] [rbp-89h]
  int v8; // [rsp+38h] [rbp-79h] BYREF
  DWORD v9; // [rsp+3Ch] [rbp-75h] BYREF
  int v10; // [rsp+40h] [rbp-71h] BYREF
  _QWORD v11[2]; // [rsp+48h] [rbp-69h] BYREF
  __int16 v12; // [rsp+58h] [rbp-59h]
  _QWORD v13[3]; // [rsp+60h] [rbp-51h] BYREF
  __int16 v14; // [rsp+78h] [rbp-39h]
  _QWORD v15[7]; // [rsp+80h] [rbp-31h] BYREF
  int v16; // [rsp+B8h] [rbp+7h] BYREF
  char v17; // [rsp+BCh] [rbp+Bh]
  char v18; // [rsp+C0h] [rbp+Fh] BYREF
  _DWORD v19[4]; // [rsp+D0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+4Fh]
  int v21; // [rsp+108h] [rbp+57h] BYREF
  int v22; // [rsp+110h] [rbp+5Fh] BYREF
  __int64 v23; // [rsp+118h] [rbp+67h] BYREF
  va_list va; // [rsp+118h] [rbp+67h]
  __int64 v25; // [rsp+120h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+120h] [rbp+6Fh]
  __int64 v27; // [rsp+128h] [rbp+77h] BYREF
  va_list va2; // [rsp+128h] [rbp+77h]
  va_list va3; // [rsp+130h] [rbp+7Fh] BYREF

  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v23 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v25 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v27 = va_arg(va3, _QWORD);
  v22 = a2;
  v21 = a1;
  v8 = 0;
  TickCount = GetTickCount();
  v16 = 0;
  v9 = TickCount;
  v17 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v16);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v10 = v8;
    if ( v17 && (v19[0] || v19[1] || v19[2] || v19[3]) )
      v3 = v19;
    else
      LODWORD(v3) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&word_18002EE0E,
      (unsigned int)&v18,
      (_DWORD)v3,
      (__int64)&v10);
  }
  v12 = 256;
  v11[0] = &v16;
  v14 = 256;
  v11[1] = &v8;
  v13[0] = &v21;
  v13[1] = &v8;
  v13[2] = &v9;
  va_copy((va_list)v15, va);
  va_copy((va_list)&v15[1], va2);
  v15[2] = &v21;
  v15[3] = &v22;
  v15[4] = &v9;
  va_copy((va_list)&v15[5], va1);
  va_copy((va_list)&v15[6], va3);
  v4 = HResultErrorContract__lambda_6e879084b73d368bf46af7ed5a0ff647_(v15);
  v8 = v4;
  v5 = v4;
  if ( v4 >= 0 )
    v5 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v4,
      v7);
  wil::details::ScopeExitFnGuard__lambda_d3abd65ea384d4da2b0a8f6dae962d1b___::operator()(v13);
  wil::details::ScopeExitFnGuard__lambda_cdd4bdbdb1b14fd9d23c70001f520b2d___::operator()(v11);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v16);
  return v5;
}

```

## disassembly

```asm
0x18001d540  mov     rax, rsp
0x18001d543  mov     [rax+20h], r9
0x18001d547  mov     [rax+18h], r8
0x18001d54b  mov     [rax+10h], edx
0x18001d54e  mov     [rax+8], ecx
0x18001d551  push    rbp
0x18001d552  push    rbx
0x18001d553  lea     rbp, [rax-4Fh]
0x18001d557  sub     rsp, 0E8h
0x18001d55e  mov     rax, cs:__security_cookie
0x18001d565  xor     rax, rsp
0x18001d568  mov     [rbp+47h+var_18], rax
0x18001d56c  mov     [rbp+47h+var_C0], 0
0x18001d573  call    cs:__imp_GetTickCount
0x18001d579  lea     rcx, [rbp+47h+var_40]
0x18001d57d  mov     [rbp+47h+var_40], 0
0x18001d584  mov     [rbp+47h+var_BC], eax
0x18001d587  mov     [rbp+47h+var_3C], 0
0x18001d58b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001d590  mov     eax, cs:dword_180037000
0x18001d596  cmp     eax, 5
0x18001d599  jbe     short loc_18001D5E8
0x18001d59b  cmp     [rbp+47h+var_3C], 0
0x18001d59f  mov     eax, [rbp+47h+var_C0]
0x18001d5a2  mov     [rbp+47h+var_B8], eax
0x18001d5a5  jz      short loc_18001D5C5
0x18001d5a7  cmp     [rbp+47h+var_28], 0
0x18001d5ab  jnz     short loc_18001D5BF
0x18001d5ad  cmp     [rbp+47h+var_24], 0
0x18001d5b1  jnz     short loc_18001D5BF
0x18001d5b3  cmp     [rbp+47h+var_20], 0
0x18001d5b7  jnz     short loc_18001D5BF
0x18001d5b9  cmp     [rbp+47h+var_1C], 0
0x18001d5bd  jz      short loc_18001D5C5
0x18001d5bf  lea     r9, [rbp+47h+var_28]
0x18001d5c3  jmp     short loc_18001D5C8
0x18001d5c5  xor     r9d, r9d
0x18001d5c8  lea     rax, [rbp+47h+var_B8]
0x18001d5cc  lea     r8, [rbp+47h+var_38]
0x18001d5d0  mov     [rsp+20h], rax; int
0x18001d5d5  lea     rdx, word_18002EE0E
0x18001d5dc  lea     rcx, dword_180037000
0x18001d5e3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d5e8  lea     rax, [rbp+47h+var_40]
0x18001d5ec  mov     [rbp+47h+var_A0], 100h
0x18001d5f2  mov     [rbp+47h+var_B0], rax
0x18001d5f6  lea     rcx, [rbp+47h+var_78]
0x18001d5fa  lea     rax, [rbp+47h+var_C0]
0x18001d5fe  mov     [rbp+47h+var_80], 100h
0x18001d604  mov     [rbp+47h+var_A8], rax
0x18001d608  lea     rax, [rbp+47h+arg_0]
0x18001d60c  mov     [rbp+47h+var_98], rax
0x18001d610  lea     rax, [rbp+47h+var_C0]
0x18001d614  mov     [rbp+47h+var_90], rax
0x18001d618  lea     rax, [rbp+47h+var_BC]
0x18001d61c  mov     [rbp+47h+var_88], rax
0x18001d620  lea     rax, [rbp+47h+arg_10]
0x18001d624  mov     [rbp+47h+var_78], rax
0x18001d628  lea     rax, [rbp+47h+arg_20]
0x18001d62c  mov     [rbp+47h+var_70], rax
0x18001d630  lea     rax, [rbp+47h+arg_0]
0x18001d634  mov     [rbp+47h+var_68], rax
0x18001d638  lea     rax, [rbp+47h+arg_8]
0x18001d63c  mov     [rbp+47h+var_60], rax
0x18001d640  lea     rax, [rbp+47h+var_BC]
0x18001d644  mov     [rbp+47h+var_58], rax
0x18001d648  lea     rax, [rbp+47h+arg_18]
0x18001d64c  mov     [rbp+47h+var_50], rax
0x18001d650  lea     rax, [rbp+47h+arg_28]
0x18001d654  mov     [rbp+47h+var_48], rax
0x18001d658  call    HResultErrorContract__lambda_6e879084b73d368bf46af7ed5a0ff647___; HResultErrorContract__lambda_6e879084b73d368bf46af7ed5a0ff647_
0x18001d65d  mov     [rbp+47h+var_C0], eax
0x18001d660  mov     ebx, eax
0x18001d662  test    eax, eax
0x18001d664  jns     short loc_18001D680
0x18001d666  mov     rcx, [rbp+4Fh]; this
0x18001d66a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d671  mov     r9d, eax; char *
0x18001d674  mov     edx, 41Ch; void *
0x18001d679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d67e  jmp     short loc_18001D682
0x18001d680  xor     ebx, ebx
0x18001d682  lea     rcx, [rbp+47h+var_98]
0x18001d686  call    wil__details__ScopeExitFnGuard__lambda_d3abd65ea384d4da2b0a8f6dae962d1b_____operator__
0x18001d68b  lea     rcx, [rbp+47h+var_B0]
0x18001d68f  call    wil__details__ScopeExitFnGuard__lambda_cdd4bdbdb1b14fd9d23c70001f520b2d_____operator__
0x18001d694  lea     rcx, [rbp+47h+var_40]
0x18001d698  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001d69d  mov     eax, ebx
0x18001d69f  mov     rcx, [rbp+47h+var_18]
0x18001d6a3  xor     rcx, rsp; StackCookie
0x18001d6a6  call    __security_check_cookie
0x18001d6ab  add     rsp, 0E8h
0x18001d6b2  pop     rbx
0x18001d6b3  pop     rbp
0x18001d6b4  retn
```
