# DeleteAppContainerProfileWorker(ushort const *,APP_CONTAINER_PROFILE_TYPE)

- ea: `0x180015da0`
- end: `0x180015fd8`
- name: `?DeleteAppContainerProfileWorker@@YAJPEBGW4APP_CONTAINER_PROFILE_TYPE@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800041ec`
- `0x180004594`
- `0x180008b78`
- `0x180009440`
- `0x18000a540`
- `0x18000a7a4`
- `0x18000b984`
- `0x18000c1f8`
- `0x18000c250`
- `0x18000c588`
- `0x18000ca58`
- `0x18000e4d0`
- `0x18000ee08`
- `0x180015da0`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180015f47`
- `ntdll!EtwEventActivityIdControl` at `0x180015f47`

## string_xrefs

- `0x180015dd8`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015f04`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall DeleteAppContainerProfileWorker(const unsigned __int16 *a1, int a2)
{
  struct wil::CallContextInfo *v5; // r8
  bool v6; // r9
  _DWORD *v7; // r9
  int v8; // edi
  int v9; // r9d
  int v10; // [rsp+20h] [rbp-59h]
  int v11; // [rsp+40h] [rbp-39h] BYREF
  const unsigned __int16 *v12; // [rsp+48h] [rbp-31h] BYREF
  __int64 (__fastcall **v13)(); // [rsp+50h] [rbp-29h] BYREF
  _BYTE v14[48]; // [rsp+58h] [rbp-21h] BYREF
  int *v15; // [rsp+88h] [rbp+Fh]
  int v16; // [rsp+90h] [rbp+17h] BYREF
  char v17; // [rsp+94h] [rbp+1Bh]
  struct _GUID v18; // [rsp+98h] [rbp+1Fh] BYREF
  _DWORD v19[4]; // [rsp+A8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a1 )
  {
    v16 = 0;
    v17 = 0;
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v16);
    if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      v11 = a2;
      v12 = a1;
      if ( v17 && (v19[0] || v19[1] || v19[2] || v19[3]) )
        v7 = v19;
      else
        LODWORD(v7) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180031038,
        (unsigned int)word_18002B30A,
        (unsigned int)&v18,
        (_DWORD)v7,
        (__int64)&v12,
        (__int64)&v11);
    }
    v13 = &off_180025B38;
    wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
      (wil::details::ThreadFailureCallbackHolder *)v14,
      (struct wil::details::IFailureCallback *)&v13,
      v5,
      v6);
    v15 = &v16;
    AppContainerRegistrationHelper::LogSuccess(&AppModelAppContainerDeletionStart, a1, 0);
    v8 = DeleteAppContainerProfileWorkerNoLogging((const char *)a1, a2);
    if ( v8 < 0 )
    {
      LOBYTE(v10) = v8 != -2147024864;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0xBA5,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v8,
        v10,
        (bool)"Name %ls type %d",
        (const char *)a1,
        a2);
      AppContainerRegistrationHelper::LogAppContainerDeletionFailure(a1, v8, &v18);
    }
    else
    {
      AppContainerRegistrationHelper::LogSuccess(&AppModelAppContainerDeletionSuccess, a1, &v18);
    }
    AppContainerRegistrationHelper::LogFailureWithContext(&AppModelAppContainerDeletionStop, a1, v8, 0);
    if ( v17 )
      EtwEventActivityIdControl(4, v19);
    v16 = 2;
    if ( (unsigned int)dword_180031038 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
      {
        v11 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180031038,
          (unsigned int)byte_18002B3B3,
          (unsigned int)&v18,
          v9,
          (__int64)&v11);
      }
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v14);
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v16);
    return (unsigned int)v8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180015da0  mov     [rsp-8+arg_10], rbx
0x180015da5  push    rbp
0x180015da6  push    rsi
0x180015da7  push    rdi
0x180015da8  lea     rbp, [rsp-47h]
0x180015dad  sub     rsp, 0C0h
0x180015db4  mov     rax, cs:__security_cookie
0x180015dbb  xor     rax, rsp
0x180015dbe  mov     [rbp+57h+var_18], rax
0x180015dc2  mov     esi, edx
0x180015dc4  mov     rbx, rcx
0x180015dc7  test    rcx, rcx
0x180015dca  jnz     short loc_180015DF0
0x180015dcc  mov     rcx, [rbp+5Fh]; this
0x180015dd0  mov     ebx, 80070057h
0x180015dd5  mov     r9d, ebx; char *
0x180015dd8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015ddf  mov     edx, 0B8Ah; void *
0x180015de4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015de9  mov     eax, ebx
0x180015deb  jmp     loc_180015FB8
0x180015df0  mov     [rbp+57h+var_40], 0
0x180015df7  mov     [rbp+57h+var_3C], 0
0x180015dfb  lea     rcx, [rbp+57h+var_40]
0x180015dff  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180015e04  mov     eax, cs:dword_180031038
0x180015e0a  cmp     eax, 5
0x180015e0d  jbe     short loc_180015E80
0x180015e0f  mov     rdx, 400000000000h
0x180015e19  lea     rcx, dword_180031038
0x180015e20  call    _tlgKeywordOn
0x180015e25  test    al, al
0x180015e27  jz      short loc_180015E80
0x180015e29  mov     [rbp+57h+var_90], esi
0x180015e2c  mov     [rbp+57h+var_88], rbx
0x180015e30  cmp     [rbp+57h+var_3C], 0
0x180015e34  jz      short loc_180015E54
0x180015e36  cmp     [rbp+57h+var_28], 0
0x180015e3a  jnz     short loc_180015E4E
0x180015e3c  cmp     [rbp+57h+var_24], 0
0x180015e40  jnz     short loc_180015E4E
0x180015e42  cmp     [rbp+57h+var_20], 0
0x180015e46  jnz     short loc_180015E4E
0x180015e48  cmp     [rbp+57h+var_1C], 0
0x180015e4c  jz      short loc_180015E54
0x180015e4e  lea     r9, [rbp+57h+var_28]
0x180015e52  jmp     short loc_180015E57
0x180015e54  xor     r9d, r9d
0x180015e57  lea     rax, [rbp+57h+var_90]
0x180015e5b  mov     qword ptr [rsp+0D0h+var_A8], rax
0x180015e60  lea     rax, [rbp+57h+var_88]
0x180015e64  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180015e69  lea     r8, [rbp+57h+var_38]
0x180015e6d  lea     rdx, word_18002B30A
0x180015e74  lea     rcx, dword_180031038
0x180015e7b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180015e80  lea     rax, off_180025B38
0x180015e87  mov     [rbp+57h+var_80], rax
0x180015e8b  lea     rdx, [rbp+57h+var_80]; struct wil::details::IFailureCallback *
0x180015e8f  lea     rcx, [rbp+57h+var_78]; this
0x180015e93  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180015e98  lea     rax, [rbp+57h+var_40]
0x180015e9c  mov     [rbp+57h+var_48], rax
0x180015ea0  xor     r8d, r8d; struct _GUID *
0x180015ea3  mov     rdx, rbx; unsigned __int16 *
0x180015ea6  lea     rcx, AppModelAppContainerDeletionStart; struct _EVENT_DESCRIPTOR *
0x180015ead  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x180015eb2  lea     r8, [rbp+57h+var_38]
0x180015eb6  mov     edx, esi
0x180015eb8  mov     rcx, rbx
0x180015ebb  call    ?DeleteAppContainerProfileWorkerNoLogging@@YAJPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; DeleteAppContainerProfileWorkerNoLogging(ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180015ec0  mov     edi, eax
0x180015ec2  test    eax, eax
0x180015ec4  js      short loc_180015EDB
0x180015ec6  lea     r8, [rbp+57h+var_38]; struct _GUID *
0x180015eca  mov     rdx, rbx; unsigned __int16 *
0x180015ecd  lea     rcx, AppModelAppContainerDeletionSuccess; struct _EVENT_DESCRIPTOR *
0x180015ed4  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x180015ed9  jmp     short loc_180015F23
0x180015edb  cmp     edi, 80070020h
0x180015ee1  setnz   al
0x180015ee4  mov     rcx, [rbp+5Fh]; this
0x180015ee8  mov     [rsp+0D0h+var_98], esi
0x180015eec  mov     [rsp+0D0h+var_A0], rbx; char *
0x180015ef1  lea     rdx, aNameLsTypeD; "Name %ls type %d"
0x180015ef8  mov     qword ptr [rsp+0D0h+var_A8], rdx; bool
0x180015efd  mov     byte ptr [rsp+0D0h+var_B0], al; int
0x180015f01  mov     r9d, edi; char *
0x180015f04  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015f0b  mov     edx, 0BA5h; void *
0x180015f10  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015f15  lea     r8, [rbp+57h+var_38]; struct _GUID *
0x180015f19  mov     edx, edi; int
0x180015f1b  mov     rcx, rbx; unsigned __int16 *
0x180015f1e  call    ?LogAppContainerDeletionFailure@AppContainerRegistrationHelper@@SAXPEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogAppContainerDeletionFailure(ushort const *,long,_GUID const *)
0x180015f23  xor     r9d, r9d; struct _GUID *
0x180015f26  mov     r8d, edi; int
0x180015f29  mov     rdx, rbx; unsigned __int16 *
0x180015f2c  lea     rcx, AppModelAppContainerDeletionStop; struct _EVENT_DESCRIPTOR *
0x180015f33  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x180015f38  cmp     [rbp+57h+var_3C], 0
0x180015f3c  jz      short loc_180015F53
0x180015f3e  lea     rdx, [rbp+57h+var_28]
0x180015f42  mov     ecx, 4
0x180015f47  call    cs:__imp_EtwEventActivityIdControl
0x180015f4e  nop     dword ptr [rax+rax+00h]
0x180015f53  mov     [rbp+57h+var_40], 2
0x180015f5a  mov     eax, cs:dword_180031038
0x180015f60  cmp     eax, 5
0x180015f63  jbe     short loc_180015FA3
0x180015f65  mov     rdx, 400000000000h
0x180015f6f  lea     rcx, dword_180031038
0x180015f76  call    _tlgKeywordOn
0x180015f7b  test    al, al
0x180015f7d  jz      short loc_180015FA3
0x180015f7f  mov     [rbp+57h+var_90], edi
0x180015f82  lea     rax, [rbp+57h+var_90]
0x180015f86  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180015f8b  lea     r8, [rbp+57h+var_38]
0x180015f8f  lea     rdx, byte_18002B3B3
0x180015f96  lea     rcx, dword_180031038
0x180015f9d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180015fa2  nop
0x180015fa3  lea     rcx, [rbp+57h+var_78]; this
0x180015fa7  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180015fac  nop
0x180015fad  lea     rcx, [rbp+57h+var_40]
0x180015fb1  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180015fb6  mov     eax, edi
0x180015fb8  mov     rcx, [rbp+57h+var_18]
0x180015fbc  xor     rcx, rsp; StackCookie
0x180015fbf  call    __security_check_cookie
0x180015fc4  mov     rbx, [rsp+0D0h+arg_10]
0x180015fcc  add     rsp, 0C0h
0x180015fd3  pop     rdi
0x180015fd4  pop     rsi
0x180015fd5  pop     rbp
0x180015fd6  retn
```
