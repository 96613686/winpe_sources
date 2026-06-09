# s_NgcDecryptWithSymmetricGcmPopKey

- ea: `0x180010950`
- end: `0x180010afb`
- name: `s_NgcDecryptWithSymmetricGcmPopKey`
- size: `427`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, char, char, char, char, char, char, char, char, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d57c`
- `0x18000da94`
- `0x180010258`
- `0x180010784`
- `0x180010950`

## string_xrefs

- `0x180010ab8`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcDecryptWithSymmetricGcmPopKey(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16)
{
  _DWORD *v16; // r9
  int v17; // eax
  unsigned int v18; // ebx
  int v20; // [rsp+28h] [rbp-E0h]
  int v21[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B8h]
  _QWORD v24[16]; // [rsp+58h] [rbp-B0h] BYREF
  int v25; // [rsp+D8h] [rbp-30h] BYREF
  char v26; // [rsp+DCh] [rbp-2Ch]
  char v27; // [rsp+E0h] [rbp-28h] BYREF
  _DWORD v28[4]; // [rsp+F0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+18h]
  __int64 v30; // [rsp+128h] [rbp+20h] BYREF
  int v31; // [rsp+130h] [rbp+28h] BYREF
  __int64 v32; // [rsp+138h] [rbp+30h] BYREF
  int v33; // [rsp+140h] [rbp+38h] BYREF

  v33 = a4;
  v32 = a3;
  v31 = a2;
  v30 = a1;
  v21[0] = 0;
  v25 = 0;
  v26 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v25);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v21[1] = v21[0];
    if ( v26 && (v28[0] || v28[1] || v28[2] || v28[3]) )
      v16 = v28;
    else
      LODWORD(v16) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&dword_18002E2F4,
      (unsigned int)&v27,
      (_DWORD)v16,
      (__int64)&v21[1]);
  }
  LOWORD(v23) = 256;
  v22[0] = &v25;
  v22[1] = v21;
  v24[0] = &v30;
  v24[1] = &v31;
  v24[2] = &a13;
  v24[3] = &a14;
  v24[4] = &a7;
  v24[5] = &a8;
  v24[6] = &a9;
  v24[7] = &a10;
  v24[8] = &a11;
  v24[9] = &a12;
  v24[10] = &a15;
  v24[11] = &a16;
  v24[12] = &v32;
  v24[13] = &v33;
  v24[14] = &a5;
  v24[15] = &a6;
  v17 = HResultErrorContract__lambda_5bda11768702f181e9bfaba8a3cb63eb_(v24);
  v21[0] = v17;
  v18 = v17;
  if ( v17 >= 0 )
    v18 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x638,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v17,
      v20);
  wil::details::ScopeExitFnGuard__lambda_690d2eb6c624ada1b87a2c53b52400c8___::operator()(v22);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v25);
  return v18;
}

```

## disassembly

```asm
0x180010950  mov     rax, rsp
0x180010953  mov     [rax+20h], r9d
0x180010957  mov     [rax+18h], r8
0x18001095b  mov     [rax+10h], edx
0x18001095e  mov     [rax+8], rcx
0x180010962  push    rbp
0x180010963  push    rbx
0x180010964  lea     rbp, [rax-18h]
0x180010968  sub     rsp, 108h
0x18001096f  mov     rax, cs:__security_cookie
0x180010976  xor     rax, rsp
0x180010979  mov     [rbp+10h+var_18], rax
0x18001097d  lea     rcx, [rbp+10h+var_40]
0x180010981  mov     [rsp+110h+var_E0], 0
0x180010989  mov     [rbp+10h+var_40], 0
0x180010990  mov     [rbp+10h+var_3C], 0
0x180010994  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180010999  mov     eax, cs:dword_180037000
0x18001099f  cmp     eax, 5
0x1800109a2  jbe     short loc_1800109F4
0x1800109a4  cmp     [rbp+10h+var_3C], 0
0x1800109a8  mov     eax, [rsp+110h+var_E0]
0x1800109ac  mov     [rsp+110h+var_E0+4], eax
0x1800109b0  jz      short loc_1800109D0
0x1800109b2  cmp     [rbp+10h+var_28], 0
0x1800109b6  jnz     short loc_1800109CA
0x1800109b8  cmp     [rbp+10h+var_24], 0
0x1800109bc  jnz     short loc_1800109CA
0x1800109be  cmp     [rbp+10h+var_20], 0
0x1800109c2  jnz     short loc_1800109CA
0x1800109c4  cmp     [rbp+10h+var_1C], 0
0x1800109c8  jz      short loc_1800109D0
0x1800109ca  lea     r9, [rbp+10h+var_28]
0x1800109ce  jmp     short loc_1800109D3
0x1800109d0  xor     r9d, r9d
0x1800109d3  lea     rax, [rsp+110h+var_E0+4]
0x1800109d8  lea     r8, [rbp+10h+var_38]
0x1800109dc  mov     [rsp+20h], rax; int
0x1800109e1  lea     rdx, dword_18002E2F4
0x1800109e8  lea     rcx, dword_180037000
0x1800109ef  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800109f4  lea     rax, [rbp+10h+var_40]
0x1800109f8  mov     word ptr [rsp+110h+var_C8], 100h
0x1800109ff  mov     [rsp+110h+var_D8], rax
0x180010a04  lea     rcx, [rsp+110h+var_C0]
0x180010a09  lea     rax, [rsp+110h+var_E0]
0x180010a0e  mov     qword ptr [rsp+110h+var_D0], rax
0x180010a13  lea     rax, [rbp+10h+arg_0]
0x180010a17  mov     [rsp+110h+var_C0], rax
0x180010a1c  lea     rax, [rbp+10h+arg_8]
0x180010a20  mov     [rsp+110h+var_B8], rax
0x180010a25  lea     rax, [rbp+10h+arg_60]
0x180010a2c  mov     [rsp+110h+var_B0], rax
0x180010a31  lea     rax, [rbp+10h+arg_68]
0x180010a38  mov     [rsp+110h+var_A8], rax
0x180010a3d  lea     rax, [rbp+10h+arg_30]
0x180010a41  mov     [rsp+110h+var_A0], rax
0x180010a46  lea     rax, [rbp+10h+arg_38]
0x180010a4a  mov     [rsp+78h], rax
0x180010a4f  lea     rax, [rbp+10h+arg_40]
0x180010a53  mov     [rbp+10h+var_90], rax
0x180010a57  lea     rax, [rbp+10h+arg_48]
0x180010a5b  mov     [rbp+10h+var_88], rax
0x180010a5f  lea     rax, [rbp+10h+arg_50]
0x180010a63  mov     [rbp+10h+var_80], rax
0x180010a67  lea     rax, [rbp+10h+arg_58]
0x180010a6b  mov     [rbp+10h+var_78], rax
0x180010a6f  lea     rax, [rbp+10h+arg_70]
0x180010a76  mov     [rbp+10h+var_70], rax
0x180010a7a  lea     rax, [rbp+10h+arg_78]
0x180010a81  mov     [rbp+10h+var_68], rax
0x180010a85  lea     rax, [rbp+10h+arg_10]
0x180010a89  mov     [rbp+10h+var_60], rax
0x180010a8d  lea     rax, [rbp+10h+arg_18]
0x180010a91  mov     [rbp+10h+var_58], rax
0x180010a95  lea     rax, [rbp+10h+arg_20]
0x180010a99  mov     [rbp+10h+var_50], rax
0x180010a9d  lea     rax, [rbp+10h+arg_28]
0x180010aa1  mov     [rbp+10h+var_48], rax
0x180010aa5  call    HResultErrorContract__lambda_5bda11768702f181e9bfaba8a3cb63eb___; HResultErrorContract__lambda_5bda11768702f181e9bfaba8a3cb63eb_
0x180010aaa  mov     [rsp+110h+var_E0], eax
0x180010aae  mov     ebx, eax
0x180010ab0  test    eax, eax
0x180010ab2  jns     short loc_180010ACE
0x180010ab4  mov     rcx, [rbp+18h]; this
0x180010ab8  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180010abf  mov     r9d, eax; char *
0x180010ac2  mov     edx, 638h; void *
0x180010ac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010acc  jmp     short loc_180010AD0
0x180010ace  xor     ebx, ebx
0x180010ad0  lea     rcx, [rsp+110h+var_D8]
0x180010ad5  call    wil__details__ScopeExitFnGuard__lambda_690d2eb6c624ada1b87a2c53b52400c8_____operator__
0x180010ada  lea     rcx, [rbp+10h+var_40]
0x180010ade  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180010ae3  mov     eax, ebx
0x180010ae5  mov     rcx, [rbp+10h+var_18]
0x180010ae9  xor     rcx, rsp; StackCookie
0x180010aec  call    __security_check_cookie
0x180010af1  add     rsp, 108h
0x180010af8  pop     rbx
0x180010af9  pop     rbp
0x180010afa  retn
```
