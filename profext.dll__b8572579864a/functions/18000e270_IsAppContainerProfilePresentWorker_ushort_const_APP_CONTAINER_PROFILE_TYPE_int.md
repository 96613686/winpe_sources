# IsAppContainerProfilePresentWorker(ushort const *,APP_CONTAINER_PROFILE_TYPE,int *)

- ea: `0x18000e270`
- end: `0x18000e427`
- name: `?IsAppContainerProfilePresentWorker@@YAJPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEAH@Z`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004594`
- `0x180009440`
- `0x18000a7a4`
- `0x18000b984`
- `0x18000c1f8`
- `0x18000e270`
- `0x18000ee08`
- `0x180013de4`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000e3a2`
- `ntdll!EtwEventActivityIdControl` at `0x18000e3a2`

## string_xrefs

- `0x18000e2ab`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsAppContainerProfilePresentWorker(__int64 *a1, int a2, __int64 a3)
{
  __int64 v3; // rdx
  _DWORD *v5; // r9
  int v6; // ebx
  __int64 v7; // r9
  int v8; // [rsp+28h] [rbp-19h]
  int v9; // [rsp+38h] [rbp-9h] BYREF
  __int64 *v10; // [rsp+40h] [rbp-1h] BYREF
  _QWORD v11[4]; // [rsp+48h] [rbp+7h] BYREF
  int v12; // [rsp+68h] [rbp+27h] BYREF
  char v13; // [rsp+6Ch] [rbp+2Bh]
  _BYTE v14[16]; // [rsp+70h] [rbp+2Fh] BYREF
  _DWORD v15[4]; // [rsp+80h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+5Fh]
  __int64 *v17; // [rsp+A8h] [rbp+67h] BYREF
  int v18; // [rsp+B0h] [rbp+6Fh] BYREF
  __int64 v19; // [rsp+B8h] [rbp+77h] BYREF

  v19 = a3;
  v18 = a2;
  v17 = a1;
  if ( !a1 )
  {
    v3 = 3156;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v8);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v3 = 3157;
    goto LABEL_3;
  }
  v12 = 0;
  v13 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
  {
    v9 = v18;
    v10 = v17;
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v5 = v15;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180031038,
      (unsigned __int8 *)byte_18002B33B,
      (__int64)v14,
      (__int64)v5,
      &v10,
      (__int64)&v9);
  }
  v11[0] = &v17;
  v11[1] = &v18;
  v11[2] = &v19;
  v11[3] = &v12;
  v6 = lambda_9fdda04c22a03e74515a873f658de96c_::operator()((__int64)v11);
  if ( v13 )
    EtwEventActivityIdControl(4, v15);
  v12 = 2;
  if ( (unsigned int)dword_180031038 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      v9 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180031038,
        (unsigned __int8 *)byte_18002B10B,
        (__int64)v14,
        v7,
        (__int64)&v9);
    }
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v12);
  return 0;
}

```

## disassembly

```asm
0x18000e270  mov     rax, rsp
0x18000e273  mov     [rax+20h], rbx
0x18000e277  mov     [rax+18h], r8
0x18000e27b  mov     [rax+10h], edx
0x18000e27e  mov     [rax+8], rcx
0x18000e282  push    rbp
0x18000e283  lea     rbp, [rax-5Fh]
0x18000e287  sub     rsp, 90h
0x18000e28e  mov     rax, cs:__security_cookie
0x18000e295  xor     rax, rsp
0x18000e298  mov     [rbp+57h+var_8], rax
0x18000e29c  test    rcx, rcx
0x18000e29f  jnz     short loc_18000E2C5
0x18000e2a1  mov     edx, 0C54h; void *
0x18000e2a6  mov     ebx, 80070057h
0x18000e2ab  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000e2b2  mov     r9d, ebx; char *
0x18000e2b5  mov     rcx, [rbp+5Fh]; this
0x18000e2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2be  mov     eax, ebx
0x18000e2c0  jmp     loc_18000E409
0x18000e2c5  test    r8, r8
0x18000e2c8  jnz     short loc_18000E2D1
0x18000e2ca  mov     edx, 0C55h
0x18000e2cf  jmp     short loc_18000E2A6
0x18000e2d1  mov     [rbp+57h+var_30], 0
0x18000e2d8  mov     [rbp+57h+var_2C], 0
0x18000e2dc  lea     rcx, [rbp+57h+var_30]
0x18000e2e0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18000e2e5  mov     eax, cs:dword_180031038
0x18000e2eb  cmp     eax, 5
0x18000e2ee  jbe     short loc_18000E368
0x18000e2f0  mov     rdx, 400000000000h
0x18000e2fa  lea     rcx, dword_180031038
0x18000e301  call    _tlgKeywordOn
0x18000e306  test    al, al
0x18000e308  jz      short loc_18000E368
0x18000e30a  mov     eax, [rbp+57h+arg_8]
0x18000e30d  mov     [rbp+57h+var_60], eax
0x18000e310  mov     rax, [rbp+57h+arg_0]
0x18000e314  mov     [rbp+57h+var_58], rax
0x18000e318  cmp     [rbp+57h+var_2C], 0
0x18000e31c  jz      short loc_18000E33C
0x18000e31e  cmp     [rbp+57h+var_18], 0
0x18000e322  jnz     short loc_18000E336
0x18000e324  cmp     [rbp+57h+var_14], 0
0x18000e328  jnz     short loc_18000E336
0x18000e32a  cmp     [rbp+57h+var_10], 0
0x18000e32e  jnz     short loc_18000E336
0x18000e330  cmp     [rbp+57h+var_C], 0
0x18000e334  jz      short loc_18000E33C
0x18000e336  lea     r9, [rbp+57h+var_18]
0x18000e33a  jmp     short loc_18000E33F
0x18000e33c  xor     r9d, r9d
0x18000e33f  lea     rax, [rbp+57h+var_60]
0x18000e343  mov     qword ptr [rsp+90h+var_70+8], rax
0x18000e348  lea     rax, [rbp+57h+var_58]
0x18000e34c  mov     qword ptr [rsp+90h+var_70], rax
0x18000e351  lea     r8, [rbp+57h+var_28]
0x18000e355  lea     rdx, byte_18002B33B
0x18000e35c  lea     rcx, dword_180031038
0x18000e363  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e368  lea     rax, [rbp+57h+arg_0]
0x18000e36c  mov     [rbp+57h+var_50], rax
0x18000e370  lea     rax, [rbp+57h+arg_8]
0x18000e374  mov     [rbp+57h+var_48], rax
0x18000e378  lea     rax, [rbp+57h+arg_10]
0x18000e37c  mov     [rbp+57h+var_40], rax
0x18000e380  lea     rax, [rbp+57h+var_30]
0x18000e384  mov     [rbp+57h+var_38], rax
0x18000e388  lea     rcx, [rbp+57h+var_50]
0x18000e38c  call    _lambda_9fdda04c22a03e74515a873f658de96c___operator__
0x18000e391  mov     ebx, eax
0x18000e393  cmp     [rbp+57h+var_2C], 0
0x18000e397  jz      short loc_18000E3AE
0x18000e399  lea     rdx, [rbp+57h+var_18]
0x18000e39d  mov     ecx, 4
0x18000e3a2  call    cs:__imp_EtwEventActivityIdControl
0x18000e3a9  nop     dword ptr [rax+rax+00h]
0x18000e3ae  mov     [rbp+57h+var_30], 2
0x18000e3b5  mov     ecx, cs:dword_180031038
0x18000e3bb  cmp     ecx, 5
0x18000e3be  jbe     short loc_18000E3FE
0x18000e3c0  mov     rdx, 400000000000h
0x18000e3ca  lea     rcx, dword_180031038
0x18000e3d1  call    _tlgKeywordOn
0x18000e3d6  test    al, al
0x18000e3d8  jz      short loc_18000E3FE
0x18000e3da  mov     [rbp+57h+var_60], ebx
0x18000e3dd  lea     rax, [rbp+57h+var_60]
0x18000e3e1  mov     qword ptr [rsp+90h+var_70], rax
0x18000e3e6  lea     r8, [rbp+57h+var_28]
0x18000e3ea  lea     rdx, byte_18002B10B
0x18000e3f1  lea     rcx, dword_180031038
0x18000e3f8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000e3fd  nop
0x18000e3fe  lea     rcx, [rbp+57h+var_30]
0x18000e402  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18000e407  xor     eax, eax
0x18000e409  mov     rcx, [rbp+57h+var_8]
0x18000e40d  xor     rcx, rsp; StackCookie
0x18000e410  call    __security_check_cookie
0x18000e415  mov     rbx, [rsp+90h+arg_18]
0x18000e41d  add     rsp, 90h
0x18000e424  pop     rbp
0x18000e425  retn
```
