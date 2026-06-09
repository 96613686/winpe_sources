# s_NgcDecryptWithSymmetricPopKey

- ea: `0x180010b10`
- end: `0x180010c8b`
- name: `s_NgcDecryptWithSymmetricPopKey`
- size: `379`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, char, char, char, char, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d5c4`
- `0x18000da94`
- `0x180010180`
- `0x180010784`
- `0x180010b10`

## string_xrefs

- `0x180010c48`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcDecryptWithSymmetricPopKey(
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
        char a12)
{
  _DWORD *v12; // r9
  int v13; // eax
  unsigned int v14; // ebx
  int v16; // [rsp+28h] [rbp-B9h]
  int v17[2]; // [rsp+38h] [rbp-A9h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v19; // [rsp+50h] [rbp-91h]
  _QWORD v20[12]; // [rsp+58h] [rbp-89h] BYREF
  int v21; // [rsp+B8h] [rbp-29h] BYREF
  char v22; // [rsp+BCh] [rbp-25h]
  char v23; // [rsp+C0h] [rbp-21h] BYREF
  _DWORD v24[4]; // [rsp+D0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+1Fh]
  __int64 v26; // [rsp+108h] [rbp+27h] BYREF
  int v27; // [rsp+110h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+118h] [rbp+37h] BYREF
  int v29; // [rsp+120h] [rbp+3Fh] BYREF

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v26 = a1;
  v17[0] = 0;
  v21 = 0;
  v22 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v21);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v17[1] = v17[0];
    if ( v22 && (v24[0] || v24[1] || v24[2] || v24[3]) )
      v12 = v24;
    else
      LODWORD(v12) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)byte_18002E77B,
      (unsigned int)&v23,
      (_DWORD)v12,
      (__int64)&v17[1]);
  }
  LOWORD(v19) = 256;
  v18[0] = &v21;
  v18[1] = v17;
  v20[0] = &v26;
  v20[1] = &v27;
  v20[2] = &a9;
  v20[3] = &a10;
  v20[4] = &a7;
  v20[5] = &a8;
  v20[6] = &a11;
  v20[7] = &a12;
  v20[8] = &v28;
  v20[9] = &v29;
  v20[10] = &a5;
  v20[11] = &a6;
  v13 = HResultErrorContract__lambda_618e92329ab0197f45d145d7bd2186a1_(v20);
  v17[0] = v13;
  v14 = v13;
  if ( v13 >= 0 )
    v14 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x578,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v13,
      v16);
  wil::details::ScopeExitFnGuard__lambda_27e56f603eb49d03c89da57ded626a66___::operator()(v18);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v21);
  return v14;
}

```

## disassembly

```asm
0x180010b10  mov     rax, rsp
0x180010b13  mov     [rax+20h], r9d
0x180010b17  mov     [rax+18h], r8
0x180010b1b  mov     [rax+10h], edx
0x180010b1e  mov     [rax+8], rcx
0x180010b22  push    rbp
0x180010b23  push    rbx
0x180010b24  lea     rbp, [rax-1Fh]
0x180010b28  sub     rsp, 0E8h
0x180010b2f  mov     rax, cs:__security_cookie
0x180010b36  xor     rax, rsp
0x180010b39  mov     [rbp+17h+var_18], rax
0x180010b3d  lea     rcx, [rbp+17h+var_40]
0x180010b41  mov     [rsp+0F0h+var_C0], 0
0x180010b49  mov     [rbp+17h+var_40], 0
0x180010b50  mov     [rbp+17h+var_3C], 0
0x180010b54  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180010b59  mov     eax, cs:dword_180037000
0x180010b5f  cmp     eax, 5
0x180010b62  jbe     short loc_180010BB4
0x180010b64  cmp     [rbp+17h+var_3C], 0
0x180010b68  mov     eax, [rsp+0F0h+var_C0]
0x180010b6c  mov     [rsp+0F0h+var_C0+4], eax
0x180010b70  jz      short loc_180010B90
0x180010b72  cmp     [rbp+17h+var_28], 0
0x180010b76  jnz     short loc_180010B8A
0x180010b78  cmp     [rbp+17h+var_24], 0
0x180010b7c  jnz     short loc_180010B8A
0x180010b7e  cmp     [rbp+17h+var_20], 0
0x180010b82  jnz     short loc_180010B8A
0x180010b84  cmp     [rbp+17h+var_1C], 0
0x180010b88  jz      short loc_180010B90
0x180010b8a  lea     r9, [rbp+17h+var_28]
0x180010b8e  jmp     short loc_180010B93
0x180010b90  xor     r9d, r9d
0x180010b93  lea     rax, [rsp+0F0h+var_C0+4]
0x180010b98  lea     r8, [rbp+17h+var_38]
0x180010b9c  mov     [rsp+20h], rax; int
0x180010ba1  lea     rdx, byte_18002E77B
0x180010ba8  lea     rcx, dword_180037000
0x180010baf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010bb4  lea     rax, [rbp+17h+var_40]
0x180010bb8  mov     word ptr [rsp+0F0h+var_A8], 100h
0x180010bbf  mov     [rsp+0F0h+var_B8], rax
0x180010bc4  lea     rcx, [rsp+0F0h+var_A0]
0x180010bc9  lea     rax, [rsp+0F0h+var_C0]
0x180010bce  mov     qword ptr [rsp+0F0h+var_B0], rax
0x180010bd3  lea     rax, [rbp+17h+arg_0]
0x180010bd7  mov     [rsp+0F0h+var_A0], rax
0x180010bdc  lea     rax, [rbp+17h+arg_8]
0x180010be0  mov     [rsp+58h], rax
0x180010be5  lea     rax, [rbp+17h+arg_40]
0x180010be9  mov     [rbp+17h+var_90], rax
0x180010bed  lea     rax, [rbp+17h+arg_48]
0x180010bf1  mov     [rbp+17h+var_88], rax
0x180010bf5  lea     rax, [rbp+17h+arg_30]
0x180010bf9  mov     [rbp+17h+var_80], rax
0x180010bfd  lea     rax, [rbp+17h+arg_38]
0x180010c01  mov     [rbp+17h+var_78], rax
0x180010c05  lea     rax, [rbp+17h+arg_50]
0x180010c09  mov     [rbp+17h+var_70], rax
0x180010c0d  lea     rax, [rbp+17h+arg_58]
0x180010c11  mov     [rbp+17h+var_68], rax
0x180010c15  lea     rax, [rbp+17h+arg_10]
0x180010c19  mov     [rbp+17h+var_60], rax
0x180010c1d  lea     rax, [rbp+17h+arg_18]
0x180010c21  mov     [rbp+17h+var_58], rax
0x180010c25  lea     rax, [rbp+17h+arg_20]
0x180010c29  mov     [rbp+17h+var_50], rax
0x180010c2d  lea     rax, [rbp+17h+arg_28]
0x180010c31  mov     [rbp+17h+var_48], rax
0x180010c35  call    HResultErrorContract__lambda_618e92329ab0197f45d145d7bd2186a1___; HResultErrorContract__lambda_618e92329ab0197f45d145d7bd2186a1_
0x180010c3a  mov     [rsp+0F0h+var_C0], eax
0x180010c3e  mov     ebx, eax
0x180010c40  test    eax, eax
0x180010c42  jns     short loc_180010C5E
0x180010c44  mov     rcx, [rbp+1Fh]; this
0x180010c48  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180010c4f  mov     r9d, eax; char *
0x180010c52  mov     edx, 578h; void *
0x180010c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c5c  jmp     short loc_180010C60
0x180010c5e  xor     ebx, ebx
0x180010c60  lea     rcx, [rsp+0F0h+var_B8]
0x180010c65  call    wil__details__ScopeExitFnGuard__lambda_27e56f603eb49d03c89da57ded626a66_____operator__
0x180010c6a  lea     rcx, [rbp+17h+var_40]
0x180010c6e  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180010c73  mov     eax, ebx
0x180010c75  mov     rcx, [rbp+17h+var_18]
0x180010c79  xor     rcx, rsp; StackCookie
0x180010c7c  call    __security_check_cookie
0x180010c81  add     rsp, 0E8h
0x180010c88  pop     rbx
0x180010c89  pop     rbp
0x180010c8a  retn
```
