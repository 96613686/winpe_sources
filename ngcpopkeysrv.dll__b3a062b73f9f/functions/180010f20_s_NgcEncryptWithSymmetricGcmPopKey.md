# s_NgcEncryptWithSymmetricGcmPopKey

- ea: `0x180010f20`
- end: `0x1800110cb`
- name: `s_NgcEncryptWithSymmetricGcmPopKey`
- size: `427`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, char, char, char, char, char, char, char, char, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d6b4`
- `0x18000da94`
- `0x1800102c4`
- `0x180010784`
- `0x180010f20`

## string_xrefs

- `0x180011088`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcEncryptWithSymmetricGcmPopKey(
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
      (unsigned int)&unk_18002E4E8,
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
  v17 = HResultErrorContract__lambda_849025bf0edbd919a5c758284b8d3a61_(v24);
  v21[0] = v17;
  v18 = v17;
  if ( v17 >= 0 )
    v18 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D8,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v17,
      v20);
  wil::details::ScopeExitFnGuard__lambda_99b01af25cbbfacd0ecfb0b671e260fe___::operator()(v22);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v25);
  return v18;
}

```

## disassembly

```asm
0x180010f20  mov     rax, rsp
0x180010f23  mov     [rax+20h], r9d
0x180010f27  mov     [rax+18h], r8
0x180010f2b  mov     [rax+10h], edx
0x180010f2e  mov     [rax+8], rcx
0x180010f32  push    rbp
0x180010f33  push    rbx
0x180010f34  lea     rbp, [rax-18h]
0x180010f38  sub     rsp, 108h
0x180010f3f  mov     rax, cs:__security_cookie
0x180010f46  xor     rax, rsp
0x180010f49  mov     [rbp+10h+var_18], rax
0x180010f4d  lea     rcx, [rbp+10h+var_40]
0x180010f51  mov     [rsp+110h+var_E0], 0
0x180010f59  mov     [rbp+10h+var_40], 0
0x180010f60  mov     [rbp+10h+var_3C], 0
0x180010f64  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180010f69  mov     eax, cs:dword_180037000
0x180010f6f  cmp     eax, 5
0x180010f72  jbe     short loc_180010FC4
0x180010f74  cmp     [rbp+10h+var_3C], 0
0x180010f78  mov     eax, [rsp+110h+var_E0]
0x180010f7c  mov     [rsp+110h+var_E0+4], eax
0x180010f80  jz      short loc_180010FA0
0x180010f82  cmp     [rbp+10h+var_28], 0
0x180010f86  jnz     short loc_180010F9A
0x180010f88  cmp     [rbp+10h+var_24], 0
0x180010f8c  jnz     short loc_180010F9A
0x180010f8e  cmp     [rbp+10h+var_20], 0
0x180010f92  jnz     short loc_180010F9A
0x180010f94  cmp     [rbp+10h+var_1C], 0
0x180010f98  jz      short loc_180010FA0
0x180010f9a  lea     r9, [rbp+10h+var_28]
0x180010f9e  jmp     short loc_180010FA3
0x180010fa0  xor     r9d, r9d
0x180010fa3  lea     rax, [rsp+110h+var_E0+4]
0x180010fa8  lea     r8, [rbp+10h+var_38]
0x180010fac  mov     [rsp+20h], rax; int
0x180010fb1  lea     rdx, unk_18002E4E8
0x180010fb8  lea     rcx, dword_180037000
0x180010fbf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180010fc4  lea     rax, [rbp+10h+var_40]
0x180010fc8  mov     word ptr [rsp+110h+var_C8], 100h
0x180010fcf  mov     [rsp+110h+var_D8], rax
0x180010fd4  lea     rcx, [rsp+110h+var_C0]
0x180010fd9  lea     rax, [rsp+110h+var_E0]
0x180010fde  mov     qword ptr [rsp+110h+var_D0], rax
0x180010fe3  lea     rax, [rbp+10h+arg_0]
0x180010fe7  mov     [rsp+110h+var_C0], rax
0x180010fec  lea     rax, [rbp+10h+arg_8]
0x180010ff0  mov     [rsp+110h+var_B8], rax
0x180010ff5  lea     rax, [rbp+10h+arg_60]
0x180010ffc  mov     [rsp+110h+var_B0], rax
0x180011001  lea     rax, [rbp+10h+arg_68]
0x180011008  mov     [rsp+110h+var_A8], rax
0x18001100d  lea     rax, [rbp+10h+arg_30]
0x180011011  mov     [rsp+110h+var_A0], rax
0x180011016  lea     rax, [rbp+10h+arg_38]
0x18001101a  mov     [rsp+78h], rax
0x18001101f  lea     rax, [rbp+10h+arg_40]
0x180011023  mov     [rbp+10h+var_90], rax
0x180011027  lea     rax, [rbp+10h+arg_48]
0x18001102b  mov     [rbp+10h+var_88], rax
0x18001102f  lea     rax, [rbp+10h+arg_50]
0x180011033  mov     [rbp+10h+var_80], rax
0x180011037  lea     rax, [rbp+10h+arg_58]
0x18001103b  mov     [rbp+10h+var_78], rax
0x18001103f  lea     rax, [rbp+10h+arg_70]
0x180011046  mov     [rbp+10h+var_70], rax
0x18001104a  lea     rax, [rbp+10h+arg_78]
0x180011051  mov     [rbp+10h+var_68], rax
0x180011055  lea     rax, [rbp+10h+arg_10]
0x180011059  mov     [rbp+10h+var_60], rax
0x18001105d  lea     rax, [rbp+10h+arg_18]
0x180011061  mov     [rbp+10h+var_58], rax
0x180011065  lea     rax, [rbp+10h+arg_20]
0x180011069  mov     [rbp+10h+var_50], rax
0x18001106d  lea     rax, [rbp+10h+arg_28]
0x180011071  mov     [rbp+10h+var_48], rax
0x180011075  call    HResultErrorContract__lambda_849025bf0edbd919a5c758284b8d3a61___; HResultErrorContract__lambda_849025bf0edbd919a5c758284b8d3a61_
0x18001107a  mov     [rsp+110h+var_E0], eax
0x18001107e  mov     ebx, eax
0x180011080  test    eax, eax
0x180011082  jns     short loc_18001109E
0x180011084  mov     rcx, [rbp+18h]; this
0x180011088  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001108f  mov     r9d, eax; char *
0x180011092  mov     edx, 5D8h; void *
0x180011097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001109c  jmp     short loc_1800110A0
0x18001109e  xor     ebx, ebx
0x1800110a0  lea     rcx, [rsp+110h+var_D8]
0x1800110a5  call    wil__details__ScopeExitFnGuard__lambda_99b01af25cbbfacd0ecfb0b671e260fe_____operator__
0x1800110aa  lea     rcx, [rbp+10h+var_40]
0x1800110ae  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x1800110b3  mov     eax, ebx
0x1800110b5  mov     rcx, [rbp+10h+var_18]
0x1800110b9  xor     rcx, rsp; StackCookie
0x1800110bc  call    __security_check_cookie
0x1800110c1  add     rsp, 108h
0x1800110c8  pop     rbx
0x1800110c9  pop     rbp
0x1800110ca  retn
```
