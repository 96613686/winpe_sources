# s_NgcCreateTokenBindingAik

- ea: `0x1800107d0`
- end: `0x18001093d`
- name: `s_NgcCreateTokenBindingAik`
- size: `365`
- prototype: `__int64(int, ...)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d5e8`
- `0x18000da94`
- `0x1800103c0`
- `0x180010784`
- `0x1800107d0`

## string_xrefs

- `0x1800108fb`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 s_NgcCreateTokenBindingAik(int a1, ...)
{
  _DWORD *v1; // r9
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+28h] [rbp-69h]
  int v6; // [rsp+38h] [rbp-59h] BYREF
  int v7; // [rsp+3Ch] [rbp-55h] BYREF
  _QWORD *v8; // [rsp+40h] [rbp-51h] BYREF
  _DWORD *v9; // [rsp+48h] [rbp-49h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-41h] BYREF
  __int16 v11; // [rsp+60h] [rbp-31h]
  _QWORD v12[6]; // [rsp+68h] [rbp-29h] BYREF
  int v13; // [rsp+98h] [rbp+7h] BYREF
  char v14; // [rsp+9Ch] [rbp+Bh]
  char v15; // [rsp+A0h] [rbp+Fh] BYREF
  _DWORD v16[4]; // [rsp+B0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+4Fh]
  int v18; // [rsp+E8h] [rbp+57h] BYREF
  __int64 v19; // [rsp+F0h] [rbp+5Fh] BYREF
  va_list va; // [rsp+F0h] [rbp+5Fh]
  __int64 v21; // [rsp+F8h] [rbp+67h] BYREF
  va_list va1; // [rsp+F8h] [rbp+67h]
  __int64 v23; // [rsp+100h] [rbp+6Fh] BYREF
  va_list va2; // [rsp+100h] [rbp+6Fh]
  _QWORD *v25; // [rsp+108h] [rbp+77h]
  _DWORD *v26; // [rsp+110h] [rbp+7Fh]
  va_list va3; // [rsp+118h] [rbp+87h] BYREF

  va_start(va3, a1);
  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v19 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v21 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v23 = va_arg(va3, _QWORD);
  v25 = va_arg(va3, _QWORD *);
  v26 = va_arg(va3, _DWORD *);
  v18 = a1;
  v8 = v25;
  v9 = v26;
  v6 = 0;
  v13 = 0;
  v14 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v7 = v6;
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v1 = v16;
    else
      LODWORD(v1) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&word_18002E7E6,
      (unsigned int)&v15,
      (_DWORD)v1,
      (__int64)&v7);
  }
  v11 = 256;
  v10[0] = &v13;
  v10[1] = &v6;
  if ( v8 )
    *v8 = 0;
  if ( v9 )
    *v9 = 0;
  va_copy((va_list)v12, va);
  va_copy((va_list)&v12[1], va1);
  v12[2] = &v8;
  v12[3] = &v9;
  v12[4] = &v18;
  va_copy((va_list)&v12[5], va2);
  v2 = HResultErrorContract__lambda_672f079b9a7fc35cc254628069702815_(v12);
  v6 = v2;
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x681,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v2,
      v5);
  wil::details::ScopeExitFnGuard__lambda_e6389373bb1ac1678589a2465f164e89___::operator()(v10);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v13);
  return v3;
}

```

## disassembly

```asm
0x1800107d0  mov     rax, rsp
0x1800107d3  mov     [rax+20h], r9
0x1800107d7  mov     [rax+18h], r8
0x1800107db  mov     [rax+10h], rdx
0x1800107df  mov     [rax+8], ecx
0x1800107e2  push    rbp
0x1800107e3  push    rbx
0x1800107e4  lea     rbp, [rax-4Fh]
0x1800107e8  sub     rsp, 0C8h
0x1800107ef  mov     rax, cs:__security_cookie
0x1800107f6  xor     rax, rsp
0x1800107f9  mov     [rbp+47h+var_18], rax
0x1800107fd  mov     rax, [rbp+47h+arg_20]
0x180010801  lea     rcx, [rbp+47h+var_40]
0x180010805  mov     [rbp+47h+var_98], rax
0x180010809  mov     rax, [rbp+47h+arg_28]
0x18001080d  mov     [rbp+47h+var_90], rax
0x180010811  mov     [rbp+47h+var_A0], 0
0x180010818  mov     [rbp+47h+var_40], 0
0x18001081f  mov     [rbp+47h+var_3C], 0
0x180010823  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180010828  mov     eax, cs:dword_180037000
0x18001082e  cmp     eax, 5
0x180010831  jbe     short loc_180010880
0x180010833  cmp     [rbp+47h+var_3C], 0
0x180010837  mov     eax, [rbp+47h+var_A0]
0x18001083a  mov     [rbp+47h+var_9C], eax
0x18001083d  jz      short loc_18001085D
0x18001083f  cmp     [rbp+47h+var_28], 0
0x180010843  jnz     short loc_180010857
0x180010845  cmp     [rbp+47h+var_24], 0
0x180010849  jnz     short loc_180010857
0x18001084b  cmp     [rbp+47h+var_20], 0
0x18001084f  jnz     short loc_180010857
0x180010851  cmp     [rbp+47h+var_1C], 0
0x180010855  jz      short loc_18001085D
0x180010857  lea     r9, [rbp+47h+var_28]
0x18001085b  jmp     short loc_180010860
0x18001085d  xor     r9d, r9d
0x180010860  lea     rax, [rbp+47h+var_9C]
0x180010864  lea     r8, [rbp+47h+var_38]
0x180010868  mov     [rsp+20h], rax; int
0x18001086d  lea     rdx, word_18002E7E6
0x180010874  lea     rcx, dword_180037000
0x18001087b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010880  lea     rax, [rbp+47h+var_40]
0x180010884  mov     [rbp+47h+var_78], 100h
0x18001088a  mov     [rbp+47h+var_88], rax
0x18001088e  lea     rax, [rbp+47h+var_A0]
0x180010892  mov     [rbp+47h+var_80], rax
0x180010896  mov     rax, [rbp+47h+var_98]
0x18001089a  test    rax, rax
0x18001089d  jz      short loc_1800108A6
0x18001089f  mov     qword ptr [rax], 0
0x1800108a6  mov     rax, [rbp+47h+var_90]
0x1800108aa  test    rax, rax
0x1800108ad  jz      short loc_1800108B5
0x1800108af  mov     dword ptr [rax], 0
0x1800108b5  lea     rax, [rbp+47h+arg_8]
0x1800108b9  mov     [rbp+47h+var_70], rax
0x1800108bd  lea     rcx, [rbp+47h+var_70]
0x1800108c1  lea     rax, [rbp+47h+arg_10]
0x1800108c5  mov     [rbp+47h+var_68], rax
0x1800108c9  lea     rax, [rbp+47h+var_98]
0x1800108cd  mov     [rbp+47h+var_60], rax
0x1800108d1  lea     rax, [rbp+47h+var_90]
0x1800108d5  mov     [rbp+47h+var_58], rax
0x1800108d9  lea     rax, [rbp+47h+arg_0]
0x1800108dd  mov     [rbp+47h+var_50], rax
0x1800108e1  lea     rax, [rbp+47h+arg_18]
0x1800108e5  mov     [rbp+47h+var_48], rax
0x1800108e9  call    HResultErrorContract__lambda_672f079b9a7fc35cc254628069702815___; HResultErrorContract__lambda_672f079b9a7fc35cc254628069702815_
0x1800108ee  mov     [rbp+47h+var_A0], eax
0x1800108f1  mov     ebx, eax
0x1800108f3  test    eax, eax
0x1800108f5  jns     short loc_180010911
0x1800108f7  mov     rcx, [rbp+4Fh]; this
0x1800108fb  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180010902  mov     r9d, eax; char *
0x180010905  mov     edx, 681h; void *
0x18001090a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001090f  jmp     short loc_180010913
0x180010911  xor     ebx, ebx
0x180010913  lea     rcx, [rbp+47h+var_88]
0x180010917  call    wil__details__ScopeExitFnGuard__lambda_e6389373bb1ac1678589a2465f164e89_____operator__
0x18001091c  lea     rcx, [rbp+47h+var_40]
0x180010920  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180010925  mov     eax, ebx
0x180010927  mov     rcx, [rbp+47h+var_18]
0x18001092b  xor     rcx, rsp; StackCookie
0x18001092e  call    __security_check_cookie
0x180010933  add     rsp, 0C8h
0x18001093a  pop     rbx
0x18001093b  pop     rbp
0x18001093c  retn
```
