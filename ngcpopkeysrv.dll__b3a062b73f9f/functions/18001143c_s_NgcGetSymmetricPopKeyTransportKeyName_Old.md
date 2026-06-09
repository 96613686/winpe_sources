# s_NgcGetSymmetricPopKeyTransportKeyName_Old

- ea: `0x18001143c`
- end: `0x18001157b`
- name: `s_NgcGetSymmetricPopKeyTransportKeyName_Old`
- size: `319`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, char, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011430`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d534`
- `0x18000da94`
- `0x18001030c`
- `0x180010784`
- `0x18001143c`

## string_xrefs

- `0x180011539`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcGetSymmetricPopKeyTransportKeyName_Old(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        char a6)
{
  _DWORD *v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+28h] [rbp-59h]
  int v11; // [rsp+38h] [rbp-49h] BYREF
  int v12; // [rsp+3Ch] [rbp-45h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-41h] BYREF
  __int16 v14; // [rsp+50h] [rbp-31h]
  _QWORD v15[6]; // [rsp+58h] [rbp-29h] BYREF
  int v16; // [rsp+88h] [rbp+7h] BYREF
  char v17; // [rsp+8Ch] [rbp+Bh]
  char v18; // [rsp+90h] [rbp+Fh] BYREF
  _DWORD v19[4]; // [rsp+A0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+4Fh]
  __int64 v21; // [rsp+D8h] [rbp+57h] BYREF
  __int64 v22; // [rsp+E0h] [rbp+5Fh] BYREF
  int v23; // [rsp+E8h] [rbp+67h] BYREF
  int v24; // [rsp+F0h] [rbp+6Fh] BYREF

  v24 = a4;
  v23 = a3;
  v22 = a2;
  v21 = a1;
  v11 = 0;
  v16 = 0;
  v17 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v16);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v12 = v11;
    if ( v17 && (v19[0] || v19[1] || v19[2] || v19[3]) )
      v6 = v19;
    else
      LODWORD(v6) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)byte_18002E581,
      (unsigned int)&v18,
      (_DWORD)v6,
      (__int64)&v12);
  }
  v14 = 256;
  v13[0] = &v16;
  v13[1] = &v11;
  v15[0] = &v21;
  v15[1] = &a5;
  v15[2] = &v24;
  v15[3] = &v22;
  v15[4] = &v23;
  v15[5] = &a6;
  v7 = HResultErrorContract__lambda_53e01c79c4e0fb57815606df94148ba1_(v15);
  v11 = v7;
  v8 = v7;
  if ( v7 >= 0 )
    v8 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v7,
      v10);
  wil::details::ScopeExitFnGuard__lambda_c39ebbb1a56c0186e332a377bc2bbefe___::operator()(v13);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v16);
  return v8;
}

```

## disassembly

```asm
0x18001143c  mov     rax, rsp
0x18001143f  mov     [rax+20h], r9d
0x180011443  mov     [rax+18h], r8d
0x180011447  mov     [rax+10h], rdx
0x18001144b  mov     [rax+8], rcx
0x18001144f  push    rbp
0x180011450  push    rbx
0x180011451  lea     rbp, [rax-4Fh]
0x180011455  sub     rsp, 0B8h
0x18001145c  mov     rax, cs:__security_cookie
0x180011463  xor     rax, rsp
0x180011466  mov     [rbp+47h+var_18], rax
0x18001146a  lea     rcx, [rbp+47h+var_40]
0x18001146e  mov     [rbp+47h+var_90], 0
0x180011475  mov     [rbp+47h+var_40], 0
0x18001147c  mov     [rbp+47h+var_3C], 0
0x180011480  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180011485  mov     eax, cs:dword_180037000
0x18001148b  cmp     eax, 5
0x18001148e  jbe     short loc_1800114DD
0x180011490  cmp     [rbp+47h+var_3C], 0
0x180011494  mov     eax, [rbp+47h+var_90]
0x180011497  mov     [rbp+47h+var_8C], eax
0x18001149a  jz      short loc_1800114BA
0x18001149c  cmp     [rbp+47h+var_28], 0
0x1800114a0  jnz     short loc_1800114B4
0x1800114a2  cmp     [rbp+47h+var_24], 0
0x1800114a6  jnz     short loc_1800114B4
0x1800114a8  cmp     [rbp+47h+var_20], 0
0x1800114ac  jnz     short loc_1800114B4
0x1800114ae  cmp     [rbp+47h+var_1C], 0
0x1800114b2  jz      short loc_1800114BA
0x1800114b4  lea     r9, [rbp+47h+var_28]
0x1800114b8  jmp     short loc_1800114BD
0x1800114ba  xor     r9d, r9d
0x1800114bd  lea     rax, [rbp+47h+var_8C]
0x1800114c1  lea     r8, [rbp+47h+var_38]
0x1800114c5  mov     [rsp+20h], rax; int
0x1800114ca  lea     rdx, byte_18002E581
0x1800114d1  lea     rcx, dword_180037000
0x1800114d8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800114dd  lea     rax, [rbp+47h+var_40]
0x1800114e1  mov     [rbp+47h+var_78], 100h
0x1800114e7  mov     [rbp+47h+var_88], rax
0x1800114eb  lea     rcx, [rbp+47h+var_70]
0x1800114ef  lea     rax, [rbp+47h+var_90]
0x1800114f3  mov     [rbp+47h+var_80], rax
0x1800114f7  lea     rax, [rbp+47h+arg_0]
0x1800114fb  mov     [rbp+47h+var_70], rax
0x1800114ff  lea     rax, [rbp+47h+arg_20]
0x180011503  mov     [rbp+47h+var_68], rax
0x180011507  lea     rax, [rbp+47h+arg_18]
0x18001150b  mov     [rbp+47h+var_60], rax
0x18001150f  lea     rax, [rbp+47h+arg_8]
0x180011513  mov     [rbp+47h+var_58], rax
0x180011517  lea     rax, [rbp+47h+arg_10]
0x18001151b  mov     [rbp+47h+var_50], rax
0x18001151f  lea     rax, [rbp+47h+arg_28]
0x180011523  mov     [rbp+47h+var_48], rax
0x180011527  call    HResultErrorContract__lambda_53e01c79c4e0fb57815606df94148ba1___; HResultErrorContract__lambda_53e01c79c4e0fb57815606df94148ba1_
0x18001152c  mov     [rbp+47h+var_90], eax
0x18001152f  mov     ebx, eax
0x180011531  test    eax, eax
0x180011533  jns     short loc_18001154F
0x180011535  mov     rcx, [rbp+4Fh]; this
0x180011539  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180011540  mov     r9d, eax; char *
0x180011543  mov     edx, 19Fh; void *
0x180011548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001154d  jmp     short loc_180011551
0x18001154f  xor     ebx, ebx
0x180011551  lea     rcx, [rbp+47h+var_88]
0x180011555  call    wil__details__ScopeExitFnGuard__lambda_c39ebbb1a56c0186e332a377bc2bbefe_____operator__
0x18001155a  lea     rcx, [rbp+47h+var_40]
0x18001155e  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180011563  mov     eax, ebx
0x180011565  mov     rcx, [rbp+47h+var_18]
0x180011569  xor     rcx, rsp; StackCookie
0x18001156c  call    __security_check_cookie
0x180011571  add     rsp, 0B8h
0x180011578  pop     rbx
0x180011579  pop     rbp
0x18001157a  retn
```
