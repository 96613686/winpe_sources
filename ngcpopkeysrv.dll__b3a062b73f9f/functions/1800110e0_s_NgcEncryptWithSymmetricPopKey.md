# s_NgcEncryptWithSymmetricPopKey

- ea: `0x1800110e0`
- end: `0x18001125b`
- name: `s_NgcEncryptWithSymmetricPopKey`
- size: `379`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, char, char, char, char, char, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d4a4`
- `0x18000da94`
- `0x180010210`
- `0x180010784`
- `0x1800110e0`

## string_xrefs

- `0x180011218`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall s_NgcEncryptWithSymmetricPopKey(
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
      (unsigned int)byte_18002E4B1,
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
  v13 = HResultErrorContract__lambda_0777c056401d5fa7da1ccdfb87aa96b5_(v20);
  v17[0] = v13;
  v14 = v13;
  if ( v13 >= 0 )
    v14 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x512,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v13,
      v16);
  wil::details::ScopeExitFnGuard__lambda_5772e0020432863d00a6a4310522989e___::operator()(v18);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v21);
  return v14;
}

```

## disassembly

```asm
0x1800110e0  mov     rax, rsp
0x1800110e3  mov     [rax+20h], r9d
0x1800110e7  mov     [rax+18h], r8
0x1800110eb  mov     [rax+10h], edx
0x1800110ee  mov     [rax+8], rcx
0x1800110f2  push    rbp
0x1800110f3  push    rbx
0x1800110f4  lea     rbp, [rax-1Fh]
0x1800110f8  sub     rsp, 0E8h
0x1800110ff  mov     rax, cs:__security_cookie
0x180011106  xor     rax, rsp
0x180011109  mov     [rbp+17h+var_18], rax
0x18001110d  lea     rcx, [rbp+17h+var_40]
0x180011111  mov     [rsp+0F0h+var_C0], 0
0x180011119  mov     [rbp+17h+var_40], 0
0x180011120  mov     [rbp+17h+var_3C], 0
0x180011124  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180011129  mov     eax, cs:dword_180037000
0x18001112f  cmp     eax, 5
0x180011132  jbe     short loc_180011184
0x180011134  cmp     [rbp+17h+var_3C], 0
0x180011138  mov     eax, [rsp+0F0h+var_C0]
0x18001113c  mov     [rsp+0F0h+var_C0+4], eax
0x180011140  jz      short loc_180011160
0x180011142  cmp     [rbp+17h+var_28], 0
0x180011146  jnz     short loc_18001115A
0x180011148  cmp     [rbp+17h+var_24], 0
0x18001114c  jnz     short loc_18001115A
0x18001114e  cmp     [rbp+17h+var_20], 0
0x180011152  jnz     short loc_18001115A
0x180011154  cmp     [rbp+17h+var_1C], 0
0x180011158  jz      short loc_180011160
0x18001115a  lea     r9, [rbp+17h+var_28]
0x18001115e  jmp     short loc_180011163
0x180011160  xor     r9d, r9d
0x180011163  lea     rax, [rsp+0F0h+var_C0+4]
0x180011168  lea     r8, [rbp+17h+var_38]
0x18001116c  mov     [rsp+20h], rax; int
0x180011171  lea     rdx, byte_18002E4B1
0x180011178  lea     rcx, dword_180037000
0x18001117f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011184  lea     rax, [rbp+17h+var_40]
0x180011188  mov     word ptr [rsp+0F0h+var_A8], 100h
0x18001118f  mov     [rsp+0F0h+var_B8], rax
0x180011194  lea     rcx, [rsp+0F0h+var_A0]
0x180011199  lea     rax, [rsp+0F0h+var_C0]
0x18001119e  mov     qword ptr [rsp+0F0h+var_B0], rax
0x1800111a3  lea     rax, [rbp+17h+arg_0]
0x1800111a7  mov     [rsp+0F0h+var_A0], rax
0x1800111ac  lea     rax, [rbp+17h+arg_8]
0x1800111b0  mov     [rsp+58h], rax
0x1800111b5  lea     rax, [rbp+17h+arg_40]
0x1800111b9  mov     [rbp+17h+var_90], rax
0x1800111bd  lea     rax, [rbp+17h+arg_48]
0x1800111c1  mov     [rbp+17h+var_88], rax
0x1800111c5  lea     rax, [rbp+17h+arg_30]
0x1800111c9  mov     [rbp+17h+var_80], rax
0x1800111cd  lea     rax, [rbp+17h+arg_38]
0x1800111d1  mov     [rbp+17h+var_78], rax
0x1800111d5  lea     rax, [rbp+17h+arg_50]
0x1800111d9  mov     [rbp+17h+var_70], rax
0x1800111dd  lea     rax, [rbp+17h+arg_58]
0x1800111e1  mov     [rbp+17h+var_68], rax
0x1800111e5  lea     rax, [rbp+17h+arg_10]
0x1800111e9  mov     [rbp+17h+var_60], rax
0x1800111ed  lea     rax, [rbp+17h+arg_18]
0x1800111f1  mov     [rbp+17h+var_58], rax
0x1800111f5  lea     rax, [rbp+17h+arg_20]
0x1800111f9  mov     [rbp+17h+var_50], rax
0x1800111fd  lea     rax, [rbp+17h+arg_28]
0x180011201  mov     [rbp+17h+var_48], rax
0x180011205  call    HResultErrorContract__lambda_0777c056401d5fa7da1ccdfb87aa96b5___; HResultErrorContract__lambda_0777c056401d5fa7da1ccdfb87aa96b5_
0x18001120a  mov     [rsp+0F0h+var_C0], eax
0x18001120e  mov     ebx, eax
0x180011210  test    eax, eax
0x180011212  jns     short loc_18001122E
0x180011214  mov     rcx, [rbp+1Fh]; this
0x180011218  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001121f  mov     r9d, eax; char *
0x180011222  mov     edx, 512h; void *
0x180011227  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001122c  jmp     short loc_180011230
0x18001122e  xor     ebx, ebx
0x180011230  lea     rcx, [rsp+0F0h+var_B8]
0x180011235  call    wil__details__ScopeExitFnGuard__lambda_5772e0020432863d00a6a4310522989e_____operator__
0x18001123a  lea     rcx, [rbp+17h+var_40]
0x18001123e  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180011243  mov     eax, ebx
0x180011245  mov     rcx, [rbp+17h+var_18]
0x180011249  xor     rcx, rsp; StackCookie
0x18001124c  call    __security_check_cookie
0x180011251  add     rsp, 0E8h
0x180011258  pop     rbx
0x180011259  pop     rbp
0x18001125a  retn
```
