# s_NgcGetSymmetricPopKeyTransportKey_Old

- ea: `0x180011584`
- end: `0x1800116f7`
- name: `s_NgcGetSymmetricPopKeyTransportKey_Old`
- size: `371`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800113c0`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d5a0`
- `0x18000da94`
- `0x180010330`
- `0x180010784`
- `0x180011584`

## string_xrefs

- `0x1800116b4`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcGetSymmetricPopKeyTransportKey_Old(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11)
{
  _DWORD *v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // [rsp+28h] [rbp-B1h]
  int v16[2]; // [rsp+38h] [rbp-A1h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-99h] BYREF
  __int64 v18; // [rsp+50h] [rbp-89h]
  _QWORD v19[11]; // [rsp+58h] [rbp-81h] BYREF
  int v20; // [rsp+B0h] [rbp-29h] BYREF
  char v21; // [rsp+B4h] [rbp-25h]
  char v22; // [rsp+B8h] [rbp-21h] BYREF
  _DWORD v23[4]; // [rsp+C8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+27h]
  __int64 v25; // [rsp+108h] [rbp+2Fh] BYREF
  __int64 v26; // [rsp+110h] [rbp+37h] BYREF
  int v27; // [rsp+118h] [rbp+3Fh] BYREF
  int v28; // [rsp+120h] [rbp+47h] BYREF

  v28 = a4;
  v27 = a3;
  v26 = a2;
  v25 = a1;
  v16[0] = 0;
  v20 = 0;
  v21 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v20);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v16[1] = v16[0];
    if ( v21 && (v23[0] || v23[1] || v23[2] || v23[3]) )
      v11 = v23;
    else
      LODWORD(v11) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)&unk_18002E248,
      (unsigned int)&v22,
      (_DWORD)v11,
      (__int64)&v16[1]);
  }
  LOWORD(v18) = 256;
  v17[0] = &v20;
  v17[1] = v16;
  v19[0] = &v25;
  v19[1] = &a5;
  v19[2] = &a6;
  v19[3] = &v28;
  v19[4] = &v26;
  v19[5] = &v27;
  v19[6] = &a7;
  v19[7] = &a8;
  v19[8] = &a9;
  v19[9] = &a10;
  v19[10] = &a11;
  v12 = HResultErrorContract__lambda_5f5ff5b28727227ab184bbe3192a9953_(v19);
  v16[0] = v12;
  v13 = v12;
  if ( v12 >= 0 )
    v13 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v12,
      v15);
  wil::details::ScopeExitFnGuard__lambda_cc070b856c372856e4b3c5a87d848d36___::operator()(v17);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v20);
  return v13;
}

```

## disassembly

```asm
0x180011584  mov     rax, rsp
0x180011587  mov     [rax+20h], r9d
0x18001158b  mov     [rax+18h], r8d
0x18001158f  mov     [rax+10h], rdx
0x180011593  mov     [rax+8], rcx
0x180011597  push    rbp
0x180011598  push    rbx
0x180011599  lea     rbp, [rax-27h]
0x18001159d  sub     rsp, 0E8h
0x1800115a4  mov     rax, cs:__security_cookie
0x1800115ab  xor     rax, rsp
0x1800115ae  mov     [rbp+1Fh+var_20], rax
0x1800115b2  lea     rcx, [rbp+1Fh+var_48]
0x1800115b6  mov     [rsp+0F0h+var_C0], 0
0x1800115be  mov     [rbp+1Fh+var_48], 0
0x1800115c5  mov     [rbp+1Fh+var_44], 0
0x1800115c9  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800115ce  mov     eax, cs:dword_180037000
0x1800115d4  cmp     eax, 5
0x1800115d7  jbe     short loc_180011629
0x1800115d9  cmp     [rbp+1Fh+var_44], 0
0x1800115dd  mov     eax, [rsp+0F0h+var_C0]
0x1800115e1  mov     [rsp+0F0h+var_C0+4], eax
0x1800115e5  jz      short loc_180011605
0x1800115e7  cmp     [rbp+1Fh+var_30], 0
0x1800115eb  jnz     short loc_1800115FF
0x1800115ed  cmp     [rbp+1Fh+var_2C], 0
0x1800115f1  jnz     short loc_1800115FF
0x1800115f3  cmp     [rbp+1Fh+var_28], 0
0x1800115f7  jnz     short loc_1800115FF
0x1800115f9  cmp     [rbp+1Fh+var_24], 0
0x1800115fd  jz      short loc_180011605
0x1800115ff  lea     r9, [rbp+1Fh+var_30]
0x180011603  jmp     short loc_180011608
0x180011605  xor     r9d, r9d
0x180011608  lea     rax, [rsp+0F0h+var_C0+4]
0x18001160d  lea     r8, [rbp+1Fh+var_40]
0x180011611  mov     [rsp+20h], rax; int
0x180011616  lea     rdx, unk_18002E248
0x18001161d  lea     rcx, dword_180037000
0x180011624  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011629  lea     rax, [rbp+1Fh+var_48]
0x18001162d  mov     word ptr [rsp+0F0h+var_A8], 100h
0x180011634  mov     [rsp+0F0h+var_B8], rax
0x180011639  lea     rcx, [rsp+50h]
0x18001163e  lea     rax, [rsp+0F0h+var_C0]
0x180011643  mov     qword ptr [rsp+0F0h+var_B0], rax
0x180011648  lea     rax, [rbp+1Fh+arg_0]
0x18001164c  mov     [rsp+50h], rax
0x180011651  lea     rax, [rbp+1Fh+arg_20]
0x180011655  mov     [rbp+1Fh+var_98], rax
0x180011659  lea     rax, [rbp+1Fh+arg_28]
0x18001165d  mov     [rbp+1Fh+var_90], rax
0x180011661  lea     rax, [rbp+1Fh+arg_18]
0x180011665  mov     [rbp+1Fh+var_88], rax
0x180011669  lea     rax, [rbp+1Fh+arg_8]
0x18001166d  mov     [rbp+1Fh+var_80], rax
0x180011671  lea     rax, [rbp+1Fh+arg_10]
0x180011675  mov     [rbp+1Fh+var_78], rax
0x180011679  lea     rax, [rbp+1Fh+arg_30]
0x18001167d  mov     [rbp+1Fh+var_70], rax
0x180011681  lea     rax, [rbp+1Fh+arg_38]
0x180011685  mov     [rbp+1Fh+var_68], rax
0x180011689  lea     rax, [rbp+1Fh+arg_40]
0x18001168d  mov     [rbp+1Fh+var_60], rax
0x180011691  lea     rax, [rbp+1Fh+arg_48]
0x180011695  mov     [rbp+1Fh+var_58], rax
0x180011699  lea     rax, [rbp+1Fh+arg_50]
0x18001169d  mov     [rbp+1Fh+var_50], rax
0x1800116a1  call    HResultErrorContract__lambda_5f5ff5b28727227ab184bbe3192a9953___; HResultErrorContract__lambda_5f5ff5b28727227ab184bbe3192a9953_
0x1800116a6  mov     [rsp+0F0h+var_C0], eax
0x1800116aa  mov     ebx, eax
0x1800116ac  test    eax, eax
0x1800116ae  jns     short loc_1800116CA
0x1800116b0  mov     rcx, [rbp+27h]; this
0x1800116b4  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800116bb  mov     r9d, eax; char *
0x1800116be  mov     edx, 32Bh; void *
0x1800116c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116c8  jmp     short loc_1800116CC
0x1800116ca  xor     ebx, ebx
0x1800116cc  lea     rcx, [rsp+0F0h+var_B8]
0x1800116d1  call    wil__details__ScopeExitFnGuard__lambda_cc070b856c372856e4b3c5a87d848d36_____operator__
0x1800116d6  lea     rcx, [rbp+1Fh+var_48]
0x1800116da  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x1800116df  mov     eax, ebx
0x1800116e1  mov     rcx, [rbp+1Fh+var_20]
0x1800116e5  xor     rcx, rsp; StackCookie
0x1800116e8  call    __security_check_cookie
0x1800116ed  add     rsp, 0E8h
0x1800116f4  pop     rbx
0x1800116f5  pop     rbp
0x1800116f6  retn
```
