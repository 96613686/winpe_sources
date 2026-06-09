# CreateAppContainerProfileWorker(ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,APP_CONTAINER_PROFILE_TYPE,void * *)

- ea: `0x18000d610`
- end: `0x18000d978`
- name: `?CreateAppContainerProfileWorker@@YAJPEBG00PEAU_SID_AND_ATTRIBUTES@@KW4APP_CONTAINER_PROFILE_TYPE@@PEAPEAX@Z`
- size: `872`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002030`
- `0x180002a80`
- `0x1800040c0`
- `0x180004594`
- `0x180008cec`
- `0x180009440`
- `0x18000a540`
- `0x18000b984`
- `0x18000c1f8`
- `0x18000c250`
- `0x18000d610`
- `0x18000e430`
- `0x18000ee08`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000d8e8`
- `ntdll!EtwEventActivityIdControl` at `0x18000d8e8`

## string_xrefs

- `0x18000d65f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000d844`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000d888`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateAppContainerProfileWorker(
        unsigned __int16 *a1,
        char *a2,
        char *a3,
        __int64 a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  __int64 v11; // rdx
  int AppContainerProfileWorkerNoLogging; // ebx
  _DWORD *v13; // r9
  unsigned __int16 *v14; // rdx
  const struct _EVENT_DESCRIPTOR *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r9
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  char *v23; // [rsp+58h] [rbp-A8h] BYREF
  char *v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  char v27; // [rsp+74h] [rbp-8Ch]
  struct _GUID v28; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v29[6]; // [rsp+88h] [rbp-78h] BYREF
  char v30[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[1036]; // [rsp+A4h] [rbp-5Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  if ( !a1 )
  {
    v11 = 2549;
LABEL_3:
    AppContainerProfileWorkerNoLogging = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)AppContainerProfileWorkerNoLogging;
  }
  if ( !a2 )
  {
    v11 = 2550;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v11 = 2551;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v11 = 2552;
    goto LABEL_3;
  }
  if ( a4 )
  {
    if ( !a5 )
    {
      v11 = 2554;
      goto LABEL_3;
    }
  }
  else if ( a5 )
  {
    v11 = 2553;
    goto LABEL_3;
  }
  v26 = 0;
  v27 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v26);
  if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
  {
    v22 = a5;
    v21 = a6;
    v23 = a3;
    v24 = a2;
    v25 = a1;
    if ( v27 && (v29[0] || v29[1] || v29[2] || v29[3]) )
      v13 = v29;
    else
      LODWORD(v13) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180031038,
      (unsigned int)&unk_18002B200,
      (unsigned int)&v28,
      (_DWORD)v13,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)&v22);
  }
  AppContainerRegistrationHelper::LogSuccess(&AppModelAppContainerCreationStart, a1, 0);
  *(_DWORD *)v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  AppContainerProfileWorkerNoLogging = CreateAppContainerProfileWorkerNoLogging(
                                         a1,
                                         a2,
                                         a3,
                                         a4,
                                         a5,
                                         a6,
                                         520,
                                         (__int64)&v28,
                                         (unsigned __int16 *)v30,
                                         a7);
  if ( AppContainerProfileWorkerNoLogging < 0 )
  {
    v16 = StringCchCatW((unsigned __int16 *)v30, 0x208u, L" ");
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xA19,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v16,
      (__int64)"Context %ls",
      v30);
    v17 = StringCchCatW((unsigned __int16 *)v30, 0x208u, a1);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xA1B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v17,
      (__int64)"Context %ls name %ls",
      v30,
      a1);
    if ( AppContainerProfileWorkerNoLogging != -2147024713 )
    {
      AppContainerRegistrationHelper::LogAppContainerCreationFailure(
        (const unsigned __int16 *)v30,
        AppContainerProfileWorkerNoLogging,
        &v28);
      goto LABEL_31;
    }
    v14 = (unsigned __int16 *)v30;
    v15 = &AppModelAppContainerAlreadyExists;
  }
  else
  {
    v14 = a1;
    v15 = (const struct _EVENT_DESCRIPTOR *)"'";
  }
  AppContainerRegistrationHelper::LogSuccess(v15, v14, &v28);
LABEL_31:
  AppContainerRegistrationHelper::LogFailureWithContext(
    &AppModelAppContainerCreationStop,
    a1,
    AppContainerProfileWorkerNoLogging,
    0);
  if ( v27 )
    EtwEventActivityIdControl(4, v29);
  v26 = 2;
  if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
  {
    v21 = AppContainerProfileWorkerNoLogging;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180031038,
      (unsigned __int8 *)&dword_18002AEBC,
      (__int64)&v28,
      v18,
      (__int64)&v21);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v26);
  return (unsigned int)AppContainerProfileWorkerNoLogging;
}

```

## disassembly

```asm
0x18000d610  push    rbp
0x18000d612  push    rbx
0x18000d613  push    rsi
0x18000d614  push    rdi
0x18000d615  push    r12
0x18000d617  push    r13
0x18000d619  push    r14
0x18000d61b  push    r15
0x18000d61d  lea     rbp, [rsp-3C8h]
0x18000d625  sub     rsp, 4C8h
0x18000d62c  mov     rax, cs:__security_cookie
0x18000d633  xor     rax, rsp
0x18000d636  mov     [rbp+400h+var_50], rax
0x18000d63d  mov     r12, r9
0x18000d640  mov     r14, r8
0x18000d643  mov     rsi, rdx
0x18000d646  mov     rdi, rcx
0x18000d649  mov     r13, [rbp+400h+arg_30]
0x18000d650  test    rcx, rcx
0x18000d653  jnz     short loc_18000D67A
0x18000d655  mov     edx, 9F5h; void *
0x18000d65a  mov     ebx, 80070057h
0x18000d65f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d666  mov     r9d, ebx; char *
0x18000d669  mov     rcx, [rbp+408h]; this
0x18000d670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d675  jmp     loc_18000D952
0x18000d67a  test    rsi, rsi
0x18000d67d  jnz     short loc_18000D686
0x18000d67f  mov     edx, 9F6h
0x18000d684  jmp     short loc_18000D65A
0x18000d686  test    r14, r14
0x18000d689  jnz     short loc_18000D692
0x18000d68b  mov     edx, 9F7h
0x18000d690  jmp     short loc_18000D65A
0x18000d692  test    r13, r13
0x18000d695  jnz     short loc_18000D69E
0x18000d697  mov     edx, 9F8h
0x18000d69c  jmp     short loc_18000D65A
0x18000d69e  mov     ebx, [rbp+400h+arg_20]
0x18000d6a4  test    r12, r12
0x18000d6a7  jnz     short loc_18000D6B4
0x18000d6a9  test    ebx, ebx
0x18000d6ab  jz      short loc_18000D6BF
0x18000d6ad  mov     edx, 9F9h
0x18000d6b2  jmp     short loc_18000D65A
0x18000d6b4  test    ebx, ebx
0x18000d6b6  jnz     short loc_18000D6BF
0x18000d6b8  mov     edx, 9FAh
0x18000d6bd  jmp     short loc_18000D65A
0x18000d6bf  mov     [rsp+500h+var_490], 0
0x18000d6c7  mov     [rsp+500h+var_48C], 0
0x18000d6cc  lea     rcx, [rsp+500h+var_490]
0x18000d6d1  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18000d6d6  mov     eax, cs:dword_180031038
0x18000d6dc  mov     r15d, [rbp+400h+arg_28]
0x18000d6e3  cmp     eax, 5
0x18000d6e6  jbe     loc_18000D791
0x18000d6ec  mov     rdx, 400000000000h
0x18000d6f6  lea     rcx, dword_180031038
0x18000d6fd  call    _tlgKeywordOn
0x18000d702  xor     ecx, ecx
0x18000d704  test    al, al
0x18000d706  jz      loc_18000D791
0x18000d70c  mov     [rsp+500h+var_4AC], ebx
0x18000d710  mov     [rsp+500h+var_4B0], r15d
0x18000d715  mov     [rsp+500h+var_4A8], r14
0x18000d71a  mov     [rsp+500h+var_4A0], rsi
0x18000d71f  mov     [rsp+500h+var_498], rdi
0x18000d724  cmp     [rsp+500h+var_48C], cl
0x18000d728  jz      short loc_18000D744
0x18000d72a  cmp     [rbp+400h+var_478], ecx
0x18000d72d  jnz     short loc_18000D73E
0x18000d72f  cmp     [rbp+400h+var_474], ecx
0x18000d732  jnz     short loc_18000D73E
0x18000d734  cmp     [rbp+400h+var_470], ecx
0x18000d737  jnz     short loc_18000D73E
0x18000d739  cmp     [rbp+400h+var_46C], ecx
0x18000d73c  jz      short loc_18000D744
0x18000d73e  lea     r9, [rbp+400h+var_478]
0x18000d742  jmp     short loc_18000D747
0x18000d744  mov     r9, rcx
0x18000d747  lea     rax, [rsp+500h+var_4AC]
0x18000d74c  mov     [rsp+500h+var_4C0], rax
0x18000d751  lea     rax, [rsp+500h+var_4B0]
0x18000d756  mov     [rsp+500h+var_4C8], rax
0x18000d75b  lea     rax, [rsp+500h+var_4A8]
0x18000d760  mov     [rsp+500h+var_4D0], rax
0x18000d765  lea     rax, [rsp+500h+var_4A0]
0x18000d76a  mov     [rsp+500h+var_4D8], rax
0x18000d76f  lea     rax, [rsp+500h+var_498]
0x18000d774  mov     [rsp+500h+var_4E0], rax
0x18000d779  lea     r8, [rsp+500h+var_488]
0x18000d77e  lea     rdx, unk_18002B200
0x18000d785  lea     rcx, dword_180031038
0x18000d78c  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d791  xor     r8d, r8d; struct _GUID *
0x18000d794  mov     rdx, rdi; unsigned __int16 *
0x18000d797  lea     rcx, AppModelAppContainerCreationStart; struct _EVENT_DESCRIPTOR *
0x18000d79e  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000d7a3  mov     dword ptr [rbp+400h+var_460], 0
0x18000d7aa  xor     edx, edx; Val
0x18000d7ac  mov     r8d, 40Ch; Size
0x18000d7b2  lea     rcx, [rbp+400h+var_45C]; void *
0x18000d7b6  call    memset_0
0x18000d7bb  mov     [rsp+500h+var_4B8], r13
0x18000d7c0  lea     rax, [rbp+400h+var_460]
0x18000d7c4  mov     [rsp+500h+var_4C0], rax
0x18000d7c9  lea     rax, [rsp+500h+var_488]
0x18000d7ce  mov     [rsp+500h+var_4C8], rax
0x18000d7d3  mov     r13d, 208h
0x18000d7d9  mov     [rsp+500h+var_4D0], r13
0x18000d7de  mov     dword ptr [rsp+500h+var_4D8], r15d
0x18000d7e3  mov     dword ptr [rsp+500h+var_4E0], ebx
0x18000d7e7  mov     r9, r12
0x18000d7ea  mov     r8, r14
0x18000d7ed  mov     rdx, rsi
0x18000d7f0  mov     rcx, rdi
0x18000d7f3  call    ?CreateAppContainerProfileWorkerNoLogging@@YAJPEBG00PEAU_SID_AND_ATTRIBUTES@@KW4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAGPEAPEAX@Z; CreateAppContainerProfileWorkerNoLogging(ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *,void * *)
0x18000d7f8  mov     ebx, eax
0x18000d7fa  test    eax, eax
0x18000d7fc  js      short loc_18000D812
0x18000d7fe  lea     r8, [rsp+500h+var_488]
0x18000d803  mov     rdx, rdi
0x18000d806  lea     rcx, AppModelAppContainerCreationSuccess; "'"
0x18000d80d  jmp     loc_18000D8B1
0x18000d812  lea     r8, asc_180028A9C; " "
0x18000d819  mov     rdx, r13; unsigned __int64
0x18000d81c  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18000d820  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d825  mov     rcx, [rbp+408h]; this
0x18000d82c  lea     r8, [rbp+400h+var_460]
0x18000d830  mov     [rsp+500h+var_4D8], r8; char *
0x18000d835  lea     r8, aContextLs; "Context %ls"
0x18000d83c  mov     [rsp+500h+var_4E0], r8; __int64
0x18000d841  mov     r9d, eax; char *
0x18000d844  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d84b  mov     edx, 0A19h; void *
0x18000d850  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000d855  mov     r8, rdi; unsigned __int16 *
0x18000d858  mov     rdx, r13; unsigned __int64
0x18000d85b  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18000d85f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d864  mov     rcx, [rbp+408h]; this
0x18000d86b  mov     [rsp+500h+var_4D0], rdi
0x18000d870  lea     rdx, [rbp+400h+var_460]
0x18000d874  mov     [rsp+500h+var_4D8], rdx; char *
0x18000d879  lea     rdx, aContextLsNameL; "Context %ls name %ls"
0x18000d880  mov     [rsp+500h+var_4E0], rdx; __int64
0x18000d885  mov     r9d, eax; char *
0x18000d888  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d88f  mov     edx, 0A1Bh; void *
0x18000d894  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000d899  lea     r8, [rsp+500h+var_488]; struct _GUID *
0x18000d89e  cmp     ebx, 800700B7h
0x18000d8a4  jnz     short loc_18000D8B8
0x18000d8a6  lea     rdx, [rbp+400h+var_460]; unsigned __int16 *
0x18000d8aa  lea     rcx, AppModelAppContainerAlreadyExists; struct _EVENT_DESCRIPTOR *
0x18000d8b1  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000d8b6  jmp     short loc_18000D8C3
0x18000d8b8  mov     edx, ebx; int
0x18000d8ba  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18000d8be  call    ?LogAppContainerCreationFailure@AppContainerRegistrationHelper@@SAXPEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogAppContainerCreationFailure(ushort const *,long,_GUID const *)
0x18000d8c3  xor     r9d, r9d; struct _GUID *
0x18000d8c6  mov     r8d, ebx; int
0x18000d8c9  mov     rdx, rdi; unsigned __int16 *
0x18000d8cc  lea     rcx, AppModelAppContainerCreationStop; struct _EVENT_DESCRIPTOR *
0x18000d8d3  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000d8d8  cmp     [rsp+500h+var_48C], 0
0x18000d8dd  jz      short loc_18000D8F4
0x18000d8df  lea     rdx, [rbp+400h+var_478]
0x18000d8e3  mov     ecx, 4
0x18000d8e8  call    cs:__imp_EtwEventActivityIdControl
0x18000d8ef  nop     dword ptr [rax+rax+00h]
0x18000d8f4  mov     [rsp+500h+var_490], 2
0x18000d8fc  mov     eax, cs:dword_180031038
0x18000d902  cmp     eax, 5
0x18000d905  jbe     short loc_18000D948
0x18000d907  mov     rdx, 400000000000h
0x18000d911  lea     rcx, dword_180031038
0x18000d918  call    _tlgKeywordOn
0x18000d91d  test    al, al
0x18000d91f  jz      short loc_18000D948
0x18000d921  mov     [rsp+500h+var_4B0], ebx
0x18000d925  lea     rax, [rsp+500h+var_4B0]
0x18000d92a  mov     [rsp+500h+var_4E0], rax
0x18000d92f  lea     r8, [rsp+500h+var_488]
0x18000d934  lea     rdx, dword_18002AEBC
0x18000d93b  lea     rcx, dword_180031038
0x18000d942  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000d947  nop
0x18000d948  lea     rcx, [rsp+500h+var_490]
0x18000d94d  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18000d952  mov     eax, ebx
0x18000d954  mov     rcx, [rbp+400h+var_50]
0x18000d95b  xor     rcx, rsp; StackCookie
0x18000d95e  call    __security_check_cookie
0x18000d963  add     rsp, 4C8h
0x18000d96a  pop     r15
0x18000d96c  pop     r14
0x18000d96e  pop     r13
0x18000d970  pop     r12
0x18000d972  pop     rdi
0x18000d973  pop     rsi
0x18000d974  pop     rbx
0x18000d975  pop     rbp
0x18000d976  retn
```
