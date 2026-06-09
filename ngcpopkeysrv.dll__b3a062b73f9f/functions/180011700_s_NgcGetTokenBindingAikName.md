# s_NgcGetTokenBindingAikName

- ea: `0x180011700`
- end: `0x18001184e`
- name: `s_NgcGetTokenBindingAikName`
- size: `334`
- prototype: `__int64(int, ...)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d6fc`
- `0x18000da94`
- `0x180010378`
- `0x180010784`
- `0x180011700`

## string_xrefs

- `0x18001180c`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 s_NgcGetTokenBindingAikName(int a1, ...)
{
  _DWORD *v1; // r9
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+28h] [rbp-51h]
  int v6; // [rsp+38h] [rbp-41h] BYREF
  int v7; // [rsp+3Ch] [rbp-3Dh] BYREF
  _QWORD *v8; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-31h] BYREF
  __int16 v10; // [rsp+58h] [rbp-21h]
  _QWORD v11[5]; // [rsp+60h] [rbp-19h] BYREF
  int v12; // [rsp+88h] [rbp+Fh] BYREF
  char v13; // [rsp+8Ch] [rbp+13h]
  char v14; // [rsp+90h] [rbp+17h] BYREF
  _DWORD v15[4]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]
  int v17; // [rsp+D8h] [rbp+5Fh] BYREF
  __int64 v18; // [rsp+E0h] [rbp+67h] BYREF
  va_list va; // [rsp+E0h] [rbp+67h]
  __int64 v20; // [rsp+E8h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+E8h] [rbp+6Fh]
  __int64 v22; // [rsp+F0h] [rbp+77h] BYREF
  va_list va2; // [rsp+F0h] [rbp+77h]
  _QWORD *v24; // [rsp+F8h] [rbp+7Fh]
  va_list va3; // [rsp+100h] [rbp+87h] BYREF

  va_start(va3, a1);
  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v22 = va_arg(va3, _QWORD);
  v24 = va_arg(va3, _QWORD *);
  v17 = a1;
  v8 = v24;
  v6 = 0;
  v12 = 0;
  v13 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    v7 = v6;
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v1 = v15;
    else
      LODWORD(v1) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180037000,
      (unsigned int)word_18002E522,
      (unsigned int)&v14,
      (_DWORD)v1,
      (__int64)&v7);
  }
  v10 = 256;
  v9[0] = &v12;
  v9[1] = &v6;
  if ( v8 )
    *v8 = 0;
  va_copy((va_list)v11, va);
  va_copy((va_list)&v11[1], va1);
  v11[2] = &v8;
  v11[3] = &v17;
  va_copy((va_list)&v11[4], va2);
  v2 = HResultErrorContract__lambda_ce36f9f612b7224e191828a46f0d8aa0_(v11);
  v6 = v2;
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6CA,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)v2,
      v5);
  wil::details::ScopeExitFnGuard__lambda_ce8d92a9ad03dcc9739bf75aeb56bf55___::operator()(v9);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v12);
  return v3;
}

```

## disassembly

```asm
0x180011700  mov     rax, rsp
0x180011703  mov     [rax+20h], r9
0x180011707  mov     [rax+18h], r8
0x18001170b  mov     [rax+10h], rdx
0x18001170f  mov     [rax+8], ecx
0x180011712  push    rbp
0x180011713  push    rbx
0x180011714  lea     rbp, [rax-57h]
0x180011718  sub     rsp, 0B8h
0x18001171f  mov     rax, cs:__security_cookie
0x180011726  xor     rax, rsp
0x180011729  mov     [rbp+4Fh+var_18], rax
0x18001172d  mov     rax, [rbp+4Fh+arg_20]
0x180011731  lea     rcx, [rbp+4Fh+var_40]
0x180011735  mov     [rbp+4Fh+var_88], rax
0x180011739  mov     [rbp+4Fh+var_90], 0
0x180011740  mov     [rbp+4Fh+var_40], 0
0x180011747  mov     [rbp+4Fh+var_3C], 0
0x18001174b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180011750  mov     eax, cs:dword_180037000
0x180011756  cmp     eax, 5
0x180011759  jbe     short loc_1800117A8
0x18001175b  cmp     [rbp+4Fh+var_3C], 0
0x18001175f  mov     eax, [rbp+4Fh+var_90]
0x180011762  mov     [rbp+4Fh+var_8C], eax
0x180011765  jz      short loc_180011785
0x180011767  cmp     [rbp+4Fh+var_28], 0
0x18001176b  jnz     short loc_18001177F
0x18001176d  cmp     [rbp+4Fh+var_24], 0
0x180011771  jnz     short loc_18001177F
0x180011773  cmp     [rbp+4Fh+var_20], 0
0x180011777  jnz     short loc_18001177F
0x180011779  cmp     [rbp+4Fh+var_1C], 0
0x18001177d  jz      short loc_180011785
0x18001177f  lea     r9, [rbp+4Fh+var_28]
0x180011783  jmp     short loc_180011788
0x180011785  xor     r9d, r9d
0x180011788  lea     rax, [rbp+4Fh+var_8C]
0x18001178c  lea     r8, [rbp+4Fh+var_38]
0x180011790  mov     [rsp+20h], rax; int
0x180011795  lea     rdx, word_18002E522
0x18001179c  lea     rcx, dword_180037000
0x1800117a3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800117a8  lea     rax, [rbp+4Fh+var_40]
0x1800117ac  mov     [rbp+4Fh+var_70], 100h
0x1800117b2  mov     [rbp+4Fh+var_80], rax
0x1800117b6  lea     rax, [rbp+4Fh+var_90]
0x1800117ba  mov     [rbp+4Fh+var_78], rax
0x1800117be  mov     rax, [rbp+4Fh+var_88]
0x1800117c2  test    rax, rax
0x1800117c5  jz      short loc_1800117CE
0x1800117c7  mov     qword ptr [rax], 0
0x1800117ce  lea     rax, [rbp+4Fh+arg_8]
0x1800117d2  mov     [rbp+4Fh+var_68], rax
0x1800117d6  lea     rcx, [rbp+4Fh+var_68]
0x1800117da  lea     rax, [rbp+4Fh+arg_10]
0x1800117de  mov     [rbp+4Fh+var_60], rax
0x1800117e2  lea     rax, [rbp+4Fh+var_88]
0x1800117e6  mov     [rbp+4Fh+var_58], rax
0x1800117ea  lea     rax, [rbp+4Fh+arg_0]
0x1800117ee  mov     [rbp+4Fh+var_50], rax
0x1800117f2  lea     rax, [rbp+4Fh+arg_18]
0x1800117f6  mov     [rbp+4Fh+var_48], rax
0x1800117fa  call    HResultErrorContract__lambda_ce36f9f612b7224e191828a46f0d8aa0___; HResultErrorContract__lambda_ce36f9f612b7224e191828a46f0d8aa0_
0x1800117ff  mov     [rbp+4Fh+var_90], eax
0x180011802  mov     ebx, eax
0x180011804  test    eax, eax
0x180011806  jns     short loc_180011822
0x180011808  mov     rcx, [rbp+57h]; this
0x18001180c  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180011813  mov     r9d, eax; char *
0x180011816  mov     edx, 6CAh; void *
0x18001181b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011820  jmp     short loc_180011824
0x180011822  xor     ebx, ebx
0x180011824  lea     rcx, [rbp+4Fh+var_80]
0x180011828  call    wil__details__ScopeExitFnGuard__lambda_ce8d92a9ad03dcc9739bf75aeb56bf55_____operator__
0x18001182d  lea     rcx, [rbp+4Fh+var_40]
0x180011831  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180011836  mov     eax, ebx
0x180011838  mov     rcx, [rbp+4Fh+var_18]
0x18001183c  xor     rcx, rsp; StackCookie
0x18001183f  call    __security_check_cookie
0x180011844  add     rsp, 0B8h
0x18001184b  pop     rbx
0x18001184c  pop     rbp
0x18001184d  retn
```
