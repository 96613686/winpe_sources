# s_NgcImportSymmetricPopKey

- ea: `0x180011860`
- end: `0x1800119a7`
- name: `s_NgcImportSymmetricPopKey`
- size: `327`
- prototype: `__int64(__int64, __int64, int, ...)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d510`
- `0x18000da94`
- `0x1800101ec`
- `0x180010784`
- `0x180011860`

## string_xrefs

- `0x180011965`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 s_NgcImportSymmetricPopKey(__int64 a1, __int64 a2, int a3, ...)
{
  _DWORD *v3; // r9
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+28h] [rbp-71h]
  int v8; // [rsp+38h] [rbp-61h] BYREF
  int v9; // [rsp+3Ch] [rbp-5Dh] BYREF
  _QWORD v10[2]; // [rsp+40h] [rbp-59h] BYREF
  __int16 v11; // [rsp+50h] [rbp-49h]
  _QWORD v12[7]; // [rsp+58h] [rbp-41h] BYREF
  int v13; // [rsp+90h] [rbp-9h] BYREF
  char v14; // [rsp+94h] [rbp-5h]
  char v15; // [rsp+98h] [rbp-1h] BYREF
  _DWORD v16[4]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+47h]
  __int64 v18; // [rsp+E8h] [rbp+4Fh] BYREF
  __int64 v19; // [rsp+F0h] [rbp+57h] BYREF
  int v20; // [rsp+F8h] [rbp+5Fh] BYREF
  __int64 v21; // [rsp+100h] [rbp+67h] BYREF
  va_list va; // [rsp+100h] [rbp+67h]
  __int64 v23; // [rsp+108h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+108h] [rbp+6Fh]
  __int64 v25; // [rsp+110h] [rbp+77h] BYREF
  va_list va2; // [rsp+110h] [rbp+77h]
  va_list va3; // [rsp+118h] [rbp+7Fh] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v23 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v25 = va_arg(va3, _QWORD);
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
      (unsigned int)byte_18002E3ED,
      (unsigned int)&v15,
      (_DWORD)v3,
      (__int64)&v9);
  }
  v11 = 256;
  v10[0] = &v13;
  v10[1] = &v8;
  v12[0] = &v18;
  va_copy((va_list)&v12[1], va);
  va_copy((va_list)&v12[2], va1);
  va_copy((va_list)&v12[3], va2);
  va_copy((va_list)&v12[4], va3);
  v12[5] = &v20;
  v12[6] = &v19;
  v4 = HResultErrorContract__lambda_4e843492e665f4071ad8a2b3fb0129a4_(v12);
  v8 = v4;
  v5 = v4;
  if ( v4 >= 0 )
    v5 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v4,
      v7);
  wil::details::ScopeExitFnGuard__lambda_412152ff6d0910be13a9698d4d21258e___::operator()(v10);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180011860  mov     rax, rsp
0x180011863  mov     [rax+20h], r9
0x180011867  mov     [rax+18h], r8d
0x18001186b  mov     [rax+10h], rdx
0x18001186f  mov     [rax+8], rcx
0x180011873  push    rbp
0x180011874  push    rbx
0x180011875  lea     rbp, [rax-47h]
0x180011879  sub     rsp, 0C8h
0x180011880  mov     rax, cs:__security_cookie
0x180011887  xor     rax, rsp
0x18001188a  mov     [rbp+3Fh+var_20], rax
0x18001188e  lea     rcx, [rbp+3Fh+var_48]
0x180011892  mov     [rbp+3Fh+var_A0], 0
0x180011899  mov     [rbp+3Fh+var_48], 0
0x1800118a0  mov     [rbp+3Fh+var_44], 0
0x1800118a4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800118a9  mov     eax, cs:dword_180037000
0x1800118af  cmp     eax, 5
0x1800118b2  jbe     short loc_180011901
0x1800118b4  cmp     [rbp+3Fh+var_44], 0
0x1800118b8  mov     eax, [rbp+3Fh+var_A0]
0x1800118bb  mov     [rbp+3Fh+var_9C], eax
0x1800118be  jz      short loc_1800118DE
0x1800118c0  cmp     [rbp+3Fh+var_30], 0
0x1800118c4  jnz     short loc_1800118D8
0x1800118c6  cmp     [rbp+3Fh+var_2C], 0
0x1800118ca  jnz     short loc_1800118D8
0x1800118cc  cmp     [rbp+3Fh+var_28], 0
0x1800118d0  jnz     short loc_1800118D8
0x1800118d2  cmp     [rbp+3Fh+var_24], 0
0x1800118d6  jz      short loc_1800118DE
0x1800118d8  lea     r9, [rbp+3Fh+var_30]
0x1800118dc  jmp     short loc_1800118E1
0x1800118de  xor     r9d, r9d
0x1800118e1  lea     rax, [rbp+3Fh+var_9C]
0x1800118e5  lea     r8, [rbp+3Fh+var_40]
0x1800118e9  mov     [rsp+20h], rax; int
0x1800118ee  lea     rdx, byte_18002E3ED
0x1800118f5  lea     rcx, dword_180037000
0x1800118fc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011901  lea     rax, [rbp+3Fh+var_48]
0x180011905  mov     [rbp+3Fh+var_88], 100h
0x18001190b  mov     [rbp+3Fh+var_98], rax
0x18001190f  lea     rcx, [rbp+3Fh+var_80]
0x180011913  lea     rax, [rbp+3Fh+var_A0]
0x180011917  mov     [rbp+3Fh+var_90], rax
0x18001191b  lea     rax, [rbp+3Fh+arg_0]
0x18001191f  mov     [rbp+3Fh+var_80], rax
0x180011923  lea     rax, [rbp+3Fh+arg_18]
0x180011927  mov     [rbp+3Fh+var_78], rax
0x18001192b  lea     rax, [rbp+3Fh+arg_20]
0x18001192f  mov     [rbp+3Fh+var_70], rax
0x180011933  lea     rax, [rbp+3Fh+arg_28]
0x180011937  mov     [rbp+3Fh+var_68], rax
0x18001193b  lea     rax, [rbp+3Fh+arg_30]
0x18001193f  mov     [rbp+3Fh+var_60], rax
0x180011943  lea     rax, [rbp+3Fh+arg_10]
0x180011947  mov     [rbp+3Fh+var_58], rax
0x18001194b  lea     rax, [rbp+3Fh+arg_8]
0x18001194f  mov     [rbp+3Fh+var_50], rax
0x180011953  call    HResultErrorContract__lambda_4e843492e665f4071ad8a2b3fb0129a4___; HResultErrorContract__lambda_4e843492e665f4071ad8a2b3fb0129a4_
0x180011958  mov     [rbp+3Fh+var_A0], eax
0x18001195b  mov     ebx, eax
0x18001195d  test    eax, eax
0x18001195f  jns     short loc_18001197B
0x180011961  mov     rcx, [rbp+47h]; this
0x180011965  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001196c  mov     r9d, eax; char *
0x18001196f  mov     edx, 94h; void *
0x180011974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011979  jmp     short loc_18001197D
0x18001197b  xor     ebx, ebx
0x18001197d  lea     rcx, [rbp+3Fh+var_98]
0x180011981  call    wil__details__ScopeExitFnGuard__lambda_412152ff6d0910be13a9698d4d21258e_____operator__
0x180011986  lea     rcx, [rbp+3Fh+var_48]
0x18001198a  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001198f  mov     eax, ebx
0x180011991  mov     rcx, [rbp+3Fh+var_20]
0x180011995  xor     rcx, rsp; StackCookie
0x180011998  call    __security_check_cookie
0x18001199d  add     rsp, 0C8h
0x1800119a4  pop     rbx
0x1800119a5  pop     rbp
0x1800119a6  retn
```
