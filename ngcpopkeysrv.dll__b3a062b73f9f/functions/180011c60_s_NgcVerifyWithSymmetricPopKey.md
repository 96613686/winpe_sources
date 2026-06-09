# s_NgcVerifyWithSymmetricPopKey

- ea: `0x180011c60`
- end: `0x180011dc6`
- name: `s_NgcVerifyWithSymmetricPopKey`
- size: `358`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, char, char, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d690`
- `0x18000da94`
- `0x180010138`
- `0x180010784`
- `0x180011c60`

## string_xrefs

- `0x180011d83`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcVerifyWithSymmetricPopKey(
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
      (unsigned int)&byte_18002E8F7,
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
  v11 = HResultErrorContract__lambda_7d609b263a7796c8d915a89496086331_(v18);
  v15[0] = v11;
  v12 = v11;
  if ( v11 >= 0 )
    v12 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v11,
      v14);
  wil::details::ScopeExitFnGuard__lambda_07a718059fc19a1ff6330649c5c28b49___::operator()(v16);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v19);
  return v12;
}

```

## disassembly

```asm
0x180011c60  mov     rax, rsp
0x180011c63  mov     [rax+20h], r9d
0x180011c67  mov     [rax+18h], r8
0x180011c6b  mov     [rax+10h], edx
0x180011c6e  mov     [rax+8], rcx
0x180011c72  push    rbp
0x180011c73  push    rbx
0x180011c74  lea     rbp, [rax-2Fh]
0x180011c78  sub     rsp, 0D8h
0x180011c7f  mov     rax, cs:__security_cookie
0x180011c86  xor     rax, rsp
0x180011c89  mov     [rbp+27h+var_18], rax
0x180011c8d  lea     rcx, [rbp+27h+var_40]
0x180011c91  mov     [rsp+0E0h+var_B0], 0
0x180011c99  mov     [rbp+27h+var_40], 0
0x180011ca0  mov     [rbp+27h+var_3C], 0
0x180011ca4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180011ca9  mov     eax, cs:dword_180037000
0x180011caf  cmp     eax, 5
0x180011cb2  jbe     short loc_180011D04
0x180011cb4  cmp     [rbp+27h+var_3C], 0
0x180011cb8  mov     eax, [rsp+0E0h+var_B0]
0x180011cbc  mov     [rsp+0E0h+var_B0+4], eax
0x180011cc0  jz      short loc_180011CE0
0x180011cc2  cmp     [rbp+27h+var_28], 0
0x180011cc6  jnz     short loc_180011CDA
0x180011cc8  cmp     [rbp+27h+var_24], 0
0x180011ccc  jnz     short loc_180011CDA
0x180011cce  cmp     [rbp+27h+var_20], 0
0x180011cd2  jnz     short loc_180011CDA
0x180011cd4  cmp     [rbp+27h+var_1C], 0
0x180011cd8  jz      short loc_180011CE0
0x180011cda  lea     r9, [rbp+27h+var_28]
0x180011cde  jmp     short loc_180011CE3
0x180011ce0  xor     r9d, r9d
0x180011ce3  lea     rax, [rsp+0E0h+var_B0+4]
0x180011ce8  lea     r8, [rbp+27h+var_38]
0x180011cec  mov     [rsp+20h], rax; int
0x180011cf1  lea     rdx, byte_18002E8F7
0x180011cf8  lea     rcx, dword_180037000
0x180011cff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011d04  lea     rax, [rbp+27h+var_40]
0x180011d08  mov     [rbp+27h+var_98], 100h
0x180011d0e  mov     [rsp+38h], rax
0x180011d13  lea     rcx, [rbp+27h+var_90]
0x180011d17  lea     rax, [rsp+0E0h+var_B0]
0x180011d1c  mov     [rbp+27h+var_A0], rax
0x180011d20  lea     rax, [rbp+27h+arg_0]
0x180011d24  mov     [rbp+27h+var_90], rax
0x180011d28  lea     rax, [rbp+27h+arg_8]
0x180011d2c  mov     [rbp+27h+var_88], rax
0x180011d30  lea     rax, [rbp+27h+arg_30]
0x180011d34  mov     [rbp+27h+var_80], rax
0x180011d38  lea     rax, [rbp+27h+arg_38]
0x180011d3c  mov     [rbp+27h+var_78], rax
0x180011d40  lea     rax, [rbp+27h+arg_40]
0x180011d44  mov     [rbp+27h+var_70], rax
0x180011d48  lea     rax, [rbp+27h+arg_48]
0x180011d4c  mov     [rbp+27h+var_68], rax
0x180011d50  lea     rax, [rbp+27h+arg_10]
0x180011d54  mov     [rbp+27h+var_60], rax
0x180011d58  lea     rax, [rbp+27h+arg_18]
0x180011d5c  mov     [rbp+27h+var_58], rax
0x180011d60  lea     rax, [rbp+27h+arg_20]
0x180011d64  mov     [rbp+27h+var_50], rax
0x180011d68  lea     rax, [rbp+27h+arg_28]
0x180011d6c  mov     [rbp+27h+var_48], rax
0x180011d70  call    HResultErrorContract__lambda_7d609b263a7796c8d915a89496086331___; HResultErrorContract__lambda_7d609b263a7796c8d915a89496086331_
0x180011d75  mov     [rsp+0E0h+var_B0], eax
0x180011d79  mov     ebx, eax
0x180011d7b  test    eax, eax
0x180011d7d  jns     short loc_180011D99
0x180011d7f  mov     rcx, [rbp+2Fh]; this
0x180011d83  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180011d8a  mov     r9d, eax; char *
0x180011d8d  mov     edx, 4ACh; void *
0x180011d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d97  jmp     short loc_180011D9B
0x180011d99  xor     ebx, ebx
0x180011d9b  lea     rcx, [rsp+38h]
0x180011da0  call    wil__details__ScopeExitFnGuard__lambda_07a718059fc19a1ff6330649c5c28b49_____operator__
0x180011da5  lea     rcx, [rbp+27h+var_40]
0x180011da9  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180011dae  mov     eax, ebx
0x180011db0  mov     rcx, [rbp+27h+var_18]
0x180011db4  xor     rcx, rsp; StackCookie
0x180011db7  call    __security_check_cookie
0x180011dbc  add     rsp, 0D8h
0x180011dc3  pop     rbx
0x180011dc4  pop     rbp
0x180011dc5  retn
```
