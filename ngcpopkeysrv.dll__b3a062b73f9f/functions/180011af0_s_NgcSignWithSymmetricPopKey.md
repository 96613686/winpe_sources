# s_NgcSignWithSymmetricPopKey

- ea: `0x180011af0`
- end: `0x180011c56`
- name: `s_NgcSignWithSymmetricPopKey`
- size: `358`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, char, char, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d6d8`
- `0x18000da94`
- `0x18001015c`
- `0x180010784`
- `0x180011af0`

## string_xrefs

- `0x180011c13`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcSignWithSymmetricPopKey(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10)
{
  _DWORD *v10; // r9
  int v11; // eax
  unsigned int v12; // ebx
  int v14; // [rsp+28h] [rbp-99h]
  int v15[2]; // [rsp+38h] [rbp-89h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-81h] BYREF
  __int16 v17; // [rsp+50h] [rbp-71h]
  _QWORD v18[10]; // [rsp+58h] [rbp-69h] BYREF
  int v19; // [rsp+A8h] [rbp-19h] BYREF
  char v20; // [rsp+ACh] [rbp-15h]
  char v21; // [rsp+B0h] [rbp-11h] BYREF
  _DWORD v22[4]; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+2Fh]
  __int64 v24; // [rsp+F8h] [rbp+37h] BYREF
  int v25; // [rsp+100h] [rbp+3Fh] BYREF
  __int64 v26; // [rsp+108h] [rbp+47h] BYREF
  int v27; // [rsp+110h] [rbp+4Fh] BYREF

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v24 = a1;
  v15[0] = 0;
  v19 = 0;
  v20 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v15[1] = v15[0];
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v10 = v22;
    else
      LODWORD(v10) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&unk_18002E2C0,
      (unsigned int)&v21,
      (_DWORD)v10,
      (__int64)&v15[1]);
  }
  v17 = 256;
  v16[0] = &v19;
  v16[1] = v15;
  v18[0] = &v24;
  v18[1] = &v25;
  v18[2] = &a7;
  v18[3] = &a8;
  v18[4] = &a9;
  v18[5] = &a10;
  v18[6] = &v26;
  v18[7] = &v27;
  v18[8] = &a5;
  v18[9] = &a6;
  v11 = HResultErrorContract__lambda_b8402da669a83f52afb58bad96f51f53_(v18);
  v15[0] = v11;
  v12 = v11;
  if ( v11 >= 0 )
    v12 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x451,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v11,
      v14);
  wil::details::ScopeExitFnGuard__lambda_18cef5f5cdd3ff5d0a2b66fffe78944c___::operator()(v16);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v19);
  return v12;
}

```

## disassembly

```asm
0x180011af0  mov     rax, rsp
0x180011af3  mov     [rax+20h], r9d
0x180011af7  mov     [rax+18h], r8
0x180011afb  mov     [rax+10h], edx
0x180011afe  mov     [rax+8], rcx
0x180011b02  push    rbp
0x180011b03  push    rbx
0x180011b04  lea     rbp, [rax-2Fh]
0x180011b08  sub     rsp, 0D8h
0x180011b0f  mov     rax, cs:__security_cookie
0x180011b16  xor     rax, rsp
0x180011b19  mov     [rbp+27h+var_18], rax
0x180011b1d  lea     rcx, [rbp+27h+var_40]
0x180011b21  mov     [rsp+0E0h+var_B0], 0
0x180011b29  mov     [rbp+27h+var_40], 0
0x180011b30  mov     [rbp+27h+var_3C], 0
0x180011b34  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180011b39  mov     eax, cs:dword_180037000
0x180011b3f  cmp     eax, 5
0x180011b42  jbe     short loc_180011B94
0x180011b44  cmp     [rbp+27h+var_3C], 0
0x180011b48  mov     eax, [rsp+0E0h+var_B0]
0x180011b4c  mov     [rsp+0E0h+var_B0+4], eax
0x180011b50  jz      short loc_180011B70
0x180011b52  cmp     [rbp+27h+var_28], 0
0x180011b56  jnz     short loc_180011B6A
0x180011b58  cmp     [rbp+27h+var_24], 0
0x180011b5c  jnz     short loc_180011B6A
0x180011b5e  cmp     [rbp+27h+var_20], 0
0x180011b62  jnz     short loc_180011B6A
0x180011b64  cmp     [rbp+27h+var_1C], 0
0x180011b68  jz      short loc_180011B70
0x180011b6a  lea     r9, [rbp+27h+var_28]
0x180011b6e  jmp     short loc_180011B73
0x180011b70  xor     r9d, r9d
0x180011b73  lea     rax, [rsp+0E0h+var_B0+4]
0x180011b78  lea     r8, [rbp+27h+var_38]
0x180011b7c  mov     [rsp+20h], rax; int
0x180011b81  lea     rdx, unk_18002E2C0
0x180011b88  lea     rcx, dword_180037000
0x180011b8f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011b94  lea     rax, [rbp+27h+var_40]
0x180011b98  mov     [rbp+27h+var_98], 100h
0x180011b9e  mov     [rsp+38h], rax
0x180011ba3  lea     rcx, [rbp+27h+var_90]
0x180011ba7  lea     rax, [rsp+0E0h+var_B0]
0x180011bac  mov     [rbp+27h+var_A0], rax
0x180011bb0  lea     rax, [rbp+27h+arg_0]
0x180011bb4  mov     [rbp+27h+var_90], rax
0x180011bb8  lea     rax, [rbp+27h+arg_8]
0x180011bbc  mov     [rbp+27h+var_88], rax
0x180011bc0  lea     rax, [rbp+27h+arg_30]
0x180011bc4  mov     [rbp+27h+var_80], rax
0x180011bc8  lea     rax, [rbp+27h+arg_38]
0x180011bcc  mov     [rbp+27h+var_78], rax
0x180011bd0  lea     rax, [rbp+27h+arg_40]
0x180011bd4  mov     [rbp+27h+var_70], rax
0x180011bd8  lea     rax, [rbp+27h+arg_48]
0x180011bdc  mov     [rbp+27h+var_68], rax
0x180011be0  lea     rax, [rbp+27h+arg_10]
0x180011be4  mov     [rbp+27h+var_60], rax
0x180011be8  lea     rax, [rbp+27h+arg_18]
0x180011bec  mov     [rbp+27h+var_58], rax
0x180011bf0  lea     rax, [rbp+27h+arg_20]
0x180011bf4  mov     [rbp+27h+var_50], rax
0x180011bf8  lea     rax, [rbp+27h+arg_28]
0x180011bfc  mov     [rbp+27h+var_48], rax
0x180011c00  call    HResultErrorContract__lambda_b8402da669a83f52afb58bad96f51f53___; HResultErrorContract__lambda_b8402da669a83f52afb58bad96f51f53_
0x180011c05  mov     [rsp+0E0h+var_B0], eax
0x180011c09  mov     ebx, eax
0x180011c0b  test    eax, eax
0x180011c0d  jns     short loc_180011C29
0x180011c0f  mov     rcx, [rbp+2Fh]; this
0x180011c13  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180011c1a  mov     r9d, eax; char *
0x180011c1d  mov     edx, 451h; void *
0x180011c22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c27  jmp     short loc_180011C2B
0x180011c29  xor     ebx, ebx
0x180011c2b  lea     rcx, [rsp+38h]
0x180011c30  call    wil__details__ScopeExitFnGuard__lambda_18cef5f5cdd3ff5d0a2b66fffe78944c_____operator__
0x180011c35  lea     rcx, [rbp+27h+var_40]
0x180011c39  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180011c3e  mov     eax, ebx
0x180011c40  mov     rcx, [rbp+27h+var_18]
0x180011c44  xor     rcx, rsp; StackCookie
0x180011c47  call    __security_check_cookie
0x180011c4c  add     rsp, 0D8h
0x180011c53  pop     rbx
0x180011c54  pop     rbp
0x180011c55  retn
```
