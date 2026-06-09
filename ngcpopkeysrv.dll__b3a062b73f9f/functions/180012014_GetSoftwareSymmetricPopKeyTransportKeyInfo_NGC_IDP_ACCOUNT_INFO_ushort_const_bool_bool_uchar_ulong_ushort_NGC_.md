# GetSoftwareSymmetricPopKeyTransportKeyInfo(_NGC_IDP_ACCOUNT_INFO *,ushort const *,bool,bool,uchar * *,ulong *,ushort * *,_NGC_KEY_STATUS *)

- ea: `0x180012014`
- end: `0x1800122c2`
- name: `?GetSoftwareSymmetricPopKeyTransportKeyInfo@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_N2PEAPEAEPEAKPEAPEAGPEAW4_NGC_KEY_STATUS@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, __int64, bool, unsigned __int8 **, unsigned int *, unsigned __int16 **, enum _NGC_KEY_STATUS *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6b0`
- `0x18000edb4`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d8f0`
- `0x18000da94`
- `0x18000db34`
- `0x18000db5c`
- `0x18001070c`
- `0x180010730`
- `0x180010784`
- `0x180011f28`
- `0x180011f4c`
- `0x180011f94`
- `0x180012014`
- `0x1800122c8`

## string_xrefs

- `0x180012144`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`

## pseudocode

```c
__int64 __fastcall GetSoftwareSymmetricPopKeyTransportKeyInfo(
        struct _NGC_IDP_ACCOUNT_INFO *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        bool a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int16 **a7,
        enum _NGC_KEY_STATUS *a8)
{
  _DWORD *v11; // r9
  int SymmetricPopKeyTransportKeyInfo; // eax
  unsigned int v13; // ebx
  unsigned __int8 *v14; // rdi
  unsigned __int16 *v15; // rbx
  _DWORD *v16; // r9
  int v18; // [rsp+20h] [rbp-B9h]
  unsigned __int16 *v19; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-91h] BYREF
  unsigned __int8 *v21; // [rsp+50h] [rbp-89h] BYREF
  int *v22; // [rsp+58h] [rbp-81h] BYREF
  __int16 v23; // [rsp+60h] [rbp-79h]
  struct NgcKeyTransportKey *v24; // [rsp+68h] [rbp-71h] BYREF
  int *v25; // [rsp+70h] [rbp-69h] BYREF
  __int16 v26; // [rsp+78h] [rbp-61h]
  int v27; // [rsp+80h] [rbp-59h] BYREF
  char v28; // [rsp+84h] [rbp-55h]
  _BYTE v29[16]; // [rsp+88h] [rbp-51h] BYREF
  _DWORD v30[4]; // [rsp+98h] [rbp-41h] BYREF
  int v31; // [rsp+A8h] [rbp-31h] BYREF
  char v32; // [rsp+ACh] [rbp-2Dh]
  _BYTE v33[16]; // [rsp+B0h] [rbp-29h] BYREF
  _DWORD v34[4]; // [rsp+C0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  *(_DWORD *)a8 = 0;
  std::make_unique<SoftwareKeyTransKey,,0>(&v24);
  v20 = 0;
  v19 = 0;
  v22 = 0;
  v31 = 0;
  v32 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v31);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    if ( v32 && (v34[0] || v34[1] || v34[2] || v34[3]) )
      v11 = v34;
    else
      v11 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      word_18002EAAA,
      v33,
      v11);
  }
  v25 = &v31;
  v26 = 256;
  SymmetricPopKeyTransportKeyInfo = GetSymmetricPopKeyTransportKeyInfo(
                                      v24,
                                      a1,
                                      a2,
                                      0,
                                      a4,
                                      (unsigned __int8 **)((unsigned __int64)&v19 & -(__int64)(a5 != 0)),
                                      (unsigned int *)((unsigned __int64)&v20 & -(__int64)(a6 != 0)),
                                      (unsigned __int16 **)((unsigned __int64)&v22 & -(__int64)(a7 != 0)));
  v13 = SymmetricPopKeyTransportKeyInfo;
  if ( SymmetricPopKeyTransportKeyInfo >= 0 )
  {
    v14 = 0;
    v21 = 0;
    if ( a5 && v19 )
    {
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v21,
        v19);
      v14 = v21;
    }
    v15 = 0;
    v19 = 0;
    if ( a7 && v22 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v19,
        v22);
      v15 = v19;
    }
    *(_DWORD *)a8 = 1;
    if ( CanUseTpmTransportKey(1) )
    {
      v27 = 0;
      v28 = 0;
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v27);
      if ( (unsigned int)dword_180037000 > 5 )
      {
        if ( v28 && (v30[0] || v30[1] || v30[2] || v30[3]) )
          v16 = v30;
        else
          v16 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_180037000,
          &dword_18002EAE4,
          v29,
          v16);
      }
      v22 = &v27;
      v23 = 256;
      *(_DWORD *)a8 = 2;
      wil::details::ScopeExitFnGuard__lambda_1b1c54ac725e724da6d63bdb52eebacb___::operator()(&v22);
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v27);
    }
    if ( a5 )
    {
      v21 = 0;
      *a5 = v14;
      *a6 = v20;
    }
    if ( a7 )
    {
      v19 = 0;
      *a7 = v15;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v21, 0);
    v13 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
      (const char *)(unsigned int)SymmetricPopKeyTransportKeyInfo,
      v18);
  }
  wil::details::ScopeExitFnGuard__lambda_3083a8dcc595a8ff66cebb748806fd0e___::operator()(&v25);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v31);
  std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(&v24);
  return v13;
}

```

## disassembly

```asm
0x180012014  mov     [rsp-8+arg_10], rbx
0x180012019  push    rbp
0x18001201a  push    rsi
0x18001201b  push    rdi
0x18001201c  push    r12
0x18001201e  push    r13
0x180012020  push    r14
0x180012022  push    r15
0x180012024  lea     rbp, [rsp-7]
0x180012029  sub     rsp, 0E0h
0x180012030  mov     rax, cs:__security_cookie
0x180012037  xor     rax, rsp
0x18001203a  mov     [rbp+37h+var_40], rax
0x18001203e  mov     r12b, r9b
0x180012041  mov     rdi, rdx
0x180012044  mov     rbx, rcx
0x180012047  mov     r14, [rbp+37h+arg_20]
0x18001204b  mov     r13, [rbp+37h+arg_28]
0x18001204f  mov     rsi, [rbp+37h+arg_30]
0x180012053  mov     r15, [rbp+37h+arg_38]
0x180012057  mov     dword ptr [r15], 0
0x18001205e  lea     rcx, [rbp+37h+var_A8]
0x180012062  call    ??$make_unique@VSoftwareKeyTransKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VSoftwareKeyTransKey@@U?$default_delete@VSoftwareKeyTransKey@@@std@@@0@XZ; std::make_unique<SoftwareKeyTransKey,,0>(void)
0x180012067  nop
0x180012068  xor     eax, eax
0x18001206a  mov     [rsp+110h+var_C8], eax
0x18001206e  mov     [rsp+110h+var_D0], rax
0x180012073  mov     [rsp+110h+var_B8], rax
0x180012078  mov     [rbp+37h+var_68], eax
0x18001207b  mov     [rbp+37h+var_64], al
0x18001207e  lea     rcx, [rbp+37h+var_68]
0x180012082  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180012087  mov     eax, cs:dword_180037000
0x18001208d  cmp     eax, 5
0x180012090  jbe     short loc_1800120CD
0x180012092  xor     eax, eax
0x180012094  cmp     [rbp+37h+var_64], al
0x180012097  jz      short loc_1800120B3
0x180012099  cmp     [rbp+37h+var_50], eax
0x18001209c  jnz     short loc_1800120AD
0x18001209e  cmp     [rbp+37h+var_4C], eax
0x1800120a1  jnz     short loc_1800120AD
0x1800120a3  cmp     [rbp+37h+var_48], eax
0x1800120a6  jnz     short loc_1800120AD
0x1800120a8  cmp     [rbp+37h+var_44], eax
0x1800120ab  jz      short loc_1800120B3
0x1800120ad  lea     r9, [rbp+37h+var_50]
0x1800120b1  jmp     short loc_1800120B6
0x1800120b3  mov     r9, rax
0x1800120b6  lea     r8, [rbp+37h+var_60]
0x1800120ba  lea     rdx, word_18002EAAA
0x1800120c1  lea     rcx, dword_180037000
0x1800120c8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800120cd  lea     rax, [rbp+37h+var_68]
0x1800120d1  mov     [rbp+37h+var_A0], rax
0x1800120d5  mov     [rbp+37h+var_98], 100h
0x1800120db  mov     rax, rsi
0x1800120de  neg     rax
0x1800120e1  sbb     r10, r10
0x1800120e4  lea     rax, [rsp+110h+var_B8]
0x1800120e9  and     r10, rax
0x1800120ec  mov     rax, r13
0x1800120ef  neg     rax
0x1800120f2  sbb     r9, r9
0x1800120f5  lea     rax, [rsp+110h+var_C8]
0x1800120fa  and     r9, rax
0x1800120fd  mov     rax, r14
0x180012100  neg     rax
0x180012103  sbb     rcx, rcx
0x180012106  lea     rax, [rsp+110h+var_D0]
0x18001210b  and     rcx, rax
0x18001210e  mov     [rsp+110h+var_D8], r10; unsigned __int16 **
0x180012113  mov     [rsp+110h+var_E0], r9; unsigned int *
0x180012118  mov     [rsp+110h+var_E8], rcx; unsigned __int8 **
0x18001211d  mov     [rsp+110h+var_F0], r12b; int
0x180012122  xor     r9d, r9d; unsigned int
0x180012125  mov     r8, rdi; unsigned __int16 *
0x180012128  mov     rdx, rbx; struct _NGC_IDP_ACCOUNT_INFO *
0x18001212b  mov     rcx, [rbp+37h+var_A8]; this
0x18001212f  call    ?GetSymmetricPopKeyTransportKeyInfo@@YAJPEAVNgcKeyTransportKey@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGK_NPEAPEAEPEAKPEAPEAG@Z; GetSymmetricPopKeyTransportKeyInfo(NgcKeyTransportKey *,_NGC_IDP_ACCOUNT_INFO *,ushort const *,ulong,bool,uchar * *,ulong *,ushort * *)
0x180012134  mov     ebx, eax
0x180012136  xor     r12d, r12d
0x180012139  test    eax, eax
0x18001213b  jns     short loc_18001215A
0x18001213d  mov     rcx, [rbp+3Fh]; this
0x180012141  mov     r9d, eax; char *
0x180012144  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001214b  mov     edx, 0DDh; void *
0x180012150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012155  jmp     loc_18001227C
0x18001215a  mov     rdi, r12
0x18001215d  mov     [rsp+110h+var_C0], r12
0x180012162  test    r14, r14
0x180012165  jz      short loc_180012180
0x180012167  mov     rdx, [rsp+110h+var_D0]
0x18001216c  test    rdx, rdx
0x18001216f  jz      short loc_180012180
0x180012171  lea     rcx, [rsp+110h+var_C0]
0x180012176  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001217b  mov     rdi, [rsp+110h+var_C0]
0x180012180  mov     rbx, r12
0x180012183  mov     [rsp+110h+var_D0], rbx
0x180012188  test    rsi, rsi
0x18001218b  jz      short loc_1800121A6
0x18001218d  mov     rdx, [rsp+110h+var_B8]
0x180012192  test    rdx, rdx
0x180012195  jz      short loc_1800121A6
0x180012197  lea     rcx, [rsp+110h+var_D0]
0x18001219c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800121a1  mov     rbx, [rsp+110h+var_D0]
0x1800121a6  mov     dword ptr [r15], 1
0x1800121ad  mov     cl, 1; bool
0x1800121af  call    ?CanUseTpmTransportKey@@YA_N_N@Z; CanUseTpmTransportKey(bool)
0x1800121b4  test    al, al
0x1800121b6  jz      loc_180012240
0x1800121bc  mov     [rbp+37h+var_90], r12d
0x1800121c0  mov     [rbp+37h+var_8C], r12b
0x1800121c4  lea     rcx, [rbp+37h+var_90]
0x1800121c8  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800121cd  mov     eax, cs:dword_180037000
0x1800121d3  cmp     eax, 5
0x1800121d6  jbe     short loc_180012216
0x1800121d8  cmp     [rbp+37h+var_8C], r12b
0x1800121dc  jz      short loc_1800121FC
0x1800121de  cmp     [rbp+37h+var_78], r12d
0x1800121e2  jnz     short loc_1800121F6
0x1800121e4  cmp     [rbp+37h+var_74], r12d
0x1800121e8  jnz     short loc_1800121F6
0x1800121ea  cmp     [rbp+37h+var_70], r12d
0x1800121ee  jnz     short loc_1800121F6
0x1800121f0  cmp     [rbp+37h+var_6C], r12d
0x1800121f4  jz      short loc_1800121FC
0x1800121f6  lea     r9, [rbp+37h+var_78]
0x1800121fa  jmp     short loc_1800121FF
0x1800121fc  mov     r9, r12
0x1800121ff  lea     r8, [rbp+37h+var_88]
0x180012203  lea     rdx, dword_18002EAE4
0x18001220a  lea     rcx, dword_180037000
0x180012211  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180012216  lea     rax, [rbp+37h+var_90]
0x18001221a  mov     [rsp+110h+var_B8], rax
0x18001221f  mov     [rbp+37h+var_B0], 100h
0x180012225  mov     dword ptr [r15], 2
0x18001222c  lea     rcx, [rsp+110h+var_B8]
0x180012231  call    wil__details__ScopeExitFnGuard__lambda_1b1c54ac725e724da6d63bdb52eebacb_____operator__
0x180012236  nop
0x180012237  lea     rcx, [rbp+37h+var_90]
0x18001223b  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180012240  test    r14, r14
0x180012243  jz      short loc_180012255
0x180012245  mov     [rsp+110h+var_C0], r12
0x18001224a  mov     [r14], rdi
0x18001224d  mov     eax, [rsp+110h+var_C8]
0x180012251  mov     [r13+0], eax
0x180012255  test    rsi, rsi
0x180012258  jz      short loc_180012262
0x18001225a  mov     [rsp+110h+var_D0], r12
0x18001225f  mov     [rsi], rbx
0x180012262  lea     rcx, [rsp+110h+var_D0]
0x180012267  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001226c  nop
0x18001226d  xor     edx, edx
0x18001226f  lea     rcx, [rsp+110h+var_C0]
0x180012274  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012279  mov     ebx, r12d
0x18001227c  lea     rcx, [rbp+37h+var_A0]
0x180012280  call    wil__details__ScopeExitFnGuard__lambda_3083a8dcc595a8ff66cebb748806fd0e_____operator__
0x180012285  nop
0x180012286  lea     rcx, [rbp+37h+var_68]
0x18001228a  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18001228f  nop
0x180012290  lea     rcx, [rbp+37h+var_A8]
0x180012294  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x180012299  mov     eax, ebx
0x18001229b  mov     rcx, [rbp+37h+var_40]
0x18001229f  xor     rcx, rsp; StackCookie
0x1800122a2  call    __security_check_cookie
0x1800122a7  mov     rbx, [rsp+110h+arg_10]
0x1800122af  add     rsp, 0E0h
0x1800122b6  pop     r15
0x1800122b8  pop     r14
0x1800122ba  pop     r13
0x1800122bc  pop     r12
0x1800122be  pop     rdi
0x1800122bf  pop     rsi
0x1800122c0  pop     rbp
0x1800122c1  retn
```
