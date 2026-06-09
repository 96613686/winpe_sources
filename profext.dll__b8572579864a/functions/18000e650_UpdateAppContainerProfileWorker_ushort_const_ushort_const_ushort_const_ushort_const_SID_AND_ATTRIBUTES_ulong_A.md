# UpdateAppContainerProfileWorker(ushort const *,ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,APP_CONTAINER_PROFILE_TYPE)

- ea: `0x18000e650`
- end: `0x18000ea15`
- name: `?UpdateAppContainerProfileWorker@@YAJPEBG000PEAU_SID_AND_ATTRIBUTES@@KW4APP_CONTAINER_PROFILE_TYPE@@@Z`
- size: `965`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002030`
- `0x1800020d0`
- `0x1800040c0`
- `0x180004594`
- `0x180008b78`
- `0x180008ebc`
- `0x180009440`
- `0x18000a540`
- `0x18000b984`
- `0x18000c1f8`
- `0x18000c250`
- `0x18000c588`
- `0x18000e570`
- `0x18000e650`
- `0x18000ee08`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000e97e`
- `ntdll!EtwEventActivityIdControl` at `0x18000e97e`

## string_xrefs

- `0x18000e69f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000e892`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000e8f7`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000e93a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdateAppContainerProfileWorker(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4,
        __int64 a5,
        int a6,
        int a7)
{
  __int64 v11; // rdx
  struct wil::CallContextInfo *v13; // r8
  bool v14; // r9
  _DWORD *v15; // r9
  unsigned int updated; // eax
  int v17; // edi
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // r9
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 *v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v27; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall **v29)(); // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[48]; // [rsp+98h] [rbp-68h] BYREF
  int *v31; // [rsp+C8h] [rbp-38h]
  int v32; // [rsp+D0h] [rbp-30h] BYREF
  char v33; // [rsp+D4h] [rbp-2Ch]
  struct _GUID v34; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v35[6]; // [rsp+E8h] [rbp-18h] BYREF
  char v36[4]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v37[524]; // [rsp+104h] [rbp+4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  if ( !a1 )
  {
    v11 = 2762;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    v11 = 2763;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v11 = 2764;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v11 = 2765;
    goto LABEL_3;
  }
  if ( a5 )
  {
    if ( !a6 )
    {
      v11 = 2767;
      goto LABEL_3;
    }
  }
  else if ( a6 )
  {
    v11 = 2766;
    goto LABEL_3;
  }
  v32 = 0;
  v33 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v32);
  if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
  {
    v24 = a6;
    v23 = a7;
    v25 = a4;
    v26 = a3;
    v27 = a2;
    v28 = a1;
    if ( v33 && (v35[0] || v35[1] || v35[2] || v35[3]) )
      v15 = v35;
    else
      v15 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180031038,
      (unsigned __int8 *)byte_18002B3DB,
      (__int64)&v34,
      (__int64)v15,
      &v28,
      &v27,
      &v26,
      &v25,
      (__int64)&v23,
      (__int64)&v24);
  }
  v29 = off_180025B30;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v30,
    (struct wil::details::IFailureCallback *)&v29,
    v13,
    v14);
  v31 = &v32;
  AppContainerRegistrationHelper::LogSuccess(&AppModelAppContainerUpdateStart, (unsigned __int16 *)a1, 0);
  *(_DWORD *)v36 = 0;
  memset_0(v37, 0, 0x204u);
  updated = UpdateAppContainerProfileNoLogging(
              (const unsigned __int16 *)a1,
              (__int64)a2,
              (__int64)a3,
              (const unsigned __int16 *)a4,
              a5,
              a6,
              a7,
              260,
              (__int64)&v34,
              (unsigned __int16 *)v36);
  LODWORD(v22) = a6;
  v17 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0xAF3,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)updated,
          (__int64)"Name %ls, %ls, %ls, %ls, %d, %d",
          (const char *)a1,
          a2,
          a3,
          a4,
          v22,
          a7);
  if ( v17 < 0 )
  {
    v18 = StringCchCatW((unsigned __int16 *)v36, 0x104u, L" ");
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xAFA,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v18,
      (__int64)"Context %ls",
      v36);
    v19 = StringCchCatW((unsigned __int16 *)v36, 0x104u, (const unsigned __int16 *)a1);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xAFC,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v19,
      (__int64)"Context %ls name %ls",
      v36,
      a1);
    AppContainerRegistrationHelper::LogAppContainerUpdateFailure((const unsigned __int16 *)v36, v17, &v34);
  }
  else
  {
    AppContainerRegistrationHelper::LogSuccess(&AppModelAppContainerUpdateSuccess, (unsigned __int16 *)a1, &v34);
  }
  AppContainerRegistrationHelper::LogFailureWithContext(&AppModelAppContainerUpdateStop, (unsigned __int16 *)a1, v17, 0);
  if ( v33 )
    EtwEventActivityIdControl(4, v35);
  v32 = 2;
  if ( (unsigned int)dword_180031038 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      v23 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180031038,
        (unsigned __int8 *)byte_18002B0E3,
        (__int64)&v34,
        v20,
        (__int64)&v23);
    }
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v30);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v32);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000e650  push    rbp
0x18000e652  push    rbx
0x18000e653  push    rsi
0x18000e654  push    rdi
0x18000e655  push    r12
0x18000e657  push    r13
0x18000e659  push    r14
0x18000e65b  push    r15
0x18000e65d  lea     rbp, [rsp-228h]
0x18000e665  sub     rsp, 328h
0x18000e66c  mov     rax, cs:__security_cookie
0x18000e673  xor     rax, rsp
0x18000e676  mov     [rbp+260h+var_50], rax
0x18000e67d  mov     r15, r9
0x18000e680  mov     r14, r8
0x18000e683  mov     rsi, rdx
0x18000e686  mov     rbx, rcx
0x18000e689  mov     r13, [rbp+260h+arg_20]
0x18000e690  test    rcx, rcx
0x18000e693  jnz     short loc_18000E6BC
0x18000e695  mov     edx, 0ACAh; void *
0x18000e69a  mov     ebx, 80070057h
0x18000e69f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000e6a6  mov     r9d, ebx; char *
0x18000e6a9  mov     rcx, [rbp+268h]; this
0x18000e6b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6b5  mov     eax, ebx
0x18000e6b7  jmp     loc_18000E9F1
0x18000e6bc  test    r15, r15
0x18000e6bf  jnz     short loc_18000E6C8
0x18000e6c1  mov     edx, 0ACBh
0x18000e6c6  jmp     short loc_18000E69A
0x18000e6c8  test    r14, r14
0x18000e6cb  jnz     short loc_18000E6D4
0x18000e6cd  mov     edx, 0ACCh
0x18000e6d2  jmp     short loc_18000E69A
0x18000e6d4  test    rsi, rsi
0x18000e6d7  jnz     short loc_18000E6E0
0x18000e6d9  mov     edx, 0ACDh
0x18000e6de  jmp     short loc_18000E69A
0x18000e6e0  mov     edi, [rbp+260h+arg_28]
0x18000e6e6  test    r13, r13
0x18000e6e9  jnz     short loc_18000E6F6
0x18000e6eb  test    edi, edi
0x18000e6ed  jz      short loc_18000E701
0x18000e6ef  mov     edx, 0ACEh
0x18000e6f4  jmp     short loc_18000E69A
0x18000e6f6  test    edi, edi
0x18000e6f8  jnz     short loc_18000E701
0x18000e6fa  mov     edx, 0ACFh
0x18000e6ff  jmp     short loc_18000E69A
0x18000e701  mov     [rbp+260h+var_290], 0
0x18000e708  mov     [rbp+260h+var_28C], 0
0x18000e70c  lea     rcx, [rbp+260h+var_290]
0x18000e710  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18000e715  mov     eax, cs:dword_180031038
0x18000e71b  mov     r12d, [rbp+260h+arg_30]
0x18000e722  cmp     eax, 5
0x18000e725  jbe     loc_18000E7DB
0x18000e72b  mov     rdx, 400000000000h
0x18000e735  lea     rcx, dword_180031038
0x18000e73c  call    _tlgKeywordOn
0x18000e741  xor     ecx, ecx
0x18000e743  test    al, al
0x18000e745  jz      loc_18000E7DB
0x18000e74b  mov     [rsp+360h+var_2FC], edi
0x18000e74f  mov     [rsp+360h+var_300], r12d
0x18000e754  mov     [rsp+360h+var_2F8], r15
0x18000e759  mov     [rsp+360h+var_2F0], r14
0x18000e75e  mov     [rsp+360h+var_2E8], rsi
0x18000e763  mov     [rbp+260h+var_2E0], rbx
0x18000e767  cmp     [rbp+260h+var_28C], cl
0x18000e76a  jz      short loc_18000E786
0x18000e76c  cmp     [rbp+260h+var_278], ecx
0x18000e76f  jnz     short loc_18000E780
0x18000e771  cmp     [rbp+260h+var_274], ecx
0x18000e774  jnz     short loc_18000E780
0x18000e776  cmp     [rbp+260h+var_270], ecx
0x18000e779  jnz     short loc_18000E780
0x18000e77b  cmp     [rbp+260h+var_26C], ecx
0x18000e77e  jz      short loc_18000E786
0x18000e780  lea     r9, [rbp+260h+var_278]
0x18000e784  jmp     short loc_18000E789
0x18000e786  mov     r9, rcx
0x18000e789  lea     rax, [rsp+360h+var_2FC]
0x18000e78e  mov     [rsp+360h+var_318], rax
0x18000e793  lea     rax, [rsp+360h+var_300]
0x18000e798  mov     [rsp+360h+var_320], rax
0x18000e79d  lea     rax, [rsp+360h+var_2F8]
0x18000e7a2  mov     [rsp+360h+var_328], rax
0x18000e7a7  lea     rax, [rsp+360h+var_2F0]
0x18000e7ac  mov     [rsp+360h+var_330], rax
0x18000e7b1  lea     rax, [rsp+360h+var_2E8]
0x18000e7b6  mov     [rsp+360h+var_338], rax
0x18000e7bb  lea     rax, [rbp+260h+var_2E0]
0x18000e7bf  mov     [rsp+360h+var_340], rax
0x18000e7c4  lea     r8, [rbp+260h+var_288]
0x18000e7c8  lea     rdx, byte_18002B3DB
0x18000e7cf  lea     rcx, dword_180031038
0x18000e7d6  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e7db  lea     rax, off_180025B30
0x18000e7e2  mov     [rbp+260h+var_2D0], rax
0x18000e7e6  lea     rdx, [rbp+260h+var_2D0]; struct wil::details::IFailureCallback *
0x18000e7ea  lea     rcx, [rbp+260h+var_2C8]; this
0x18000e7ee  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18000e7f3  lea     rax, [rbp+260h+var_290]
0x18000e7f7  mov     [rbp+260h+var_298], rax
0x18000e7fb  xor     r8d, r8d; struct _GUID *
0x18000e7fe  mov     rdx, rbx; unsigned __int16 *
0x18000e801  lea     rcx, AppModelAppContainerUpdateStart; struct _EVENT_DESCRIPTOR *
0x18000e808  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000e80d  mov     dword ptr [rbp+260h+var_260], 0
0x18000e814  xor     edx, edx; Val
0x18000e816  mov     r8d, 204h; Size
0x18000e81c  lea     rcx, [rbp+260h+var_25C]; void *
0x18000e820  call    memset_0
0x18000e825  lea     rax, [rbp+260h+var_260]
0x18000e829  mov     [rsp+360h+var_318], rax
0x18000e82e  lea     rax, [rbp+260h+var_288]
0x18000e832  mov     [rsp+360h+var_320], rax
0x18000e837  mov     [rsp+360h+var_328], 104h
0x18000e840  mov     dword ptr [rsp+360h+var_330], r12d
0x18000e845  mov     dword ptr [rsp+360h+var_338], edi
0x18000e849  mov     [rsp+360h+var_340], r13
0x18000e84e  mov     r9, r15
0x18000e851  mov     r8, r14
0x18000e854  mov     rdx, rsi
0x18000e857  mov     rcx, rbx
0x18000e85a  call    ?UpdateAppContainerProfileNoLogging@@YAJPEBG000PEAU_SID_AND_ATTRIBUTES@@KW4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAG@Z; UpdateAppContainerProfileNoLogging(ushort const *,ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *)
0x18000e85f  mov     rcx, [rbp+268h]; this
0x18000e866  mov     [rsp+360h+var_310], r12d
0x18000e86b  mov     dword ptr [rsp+360h+var_318], edi
0x18000e86f  mov     [rsp+360h+var_320], r15
0x18000e874  mov     [rsp+360h+var_328], r14
0x18000e879  mov     [rsp+360h+var_330], rsi
0x18000e87e  mov     [rsp+360h+var_338], rbx; char *
0x18000e883  lea     rdx, aNameLsLsLsLsDD; "Name %ls, %ls, %ls, %ls, %d, %d"
0x18000e88a  mov     [rsp+360h+var_340], rdx; __int64
0x18000e88f  mov     r9d, eax; char *
0x18000e892  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000e899  mov     edx, 0AF3h; void *
0x18000e89e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e8a3  mov     edi, eax
0x18000e8a5  test    eax, eax
0x18000e8a7  js      short loc_18000E8C1
0x18000e8a9  lea     r8, [rbp+260h+var_288]; struct _GUID *
0x18000e8ad  mov     rdx, rbx; unsigned __int16 *
0x18000e8b0  lea     rcx, AppModelAppContainerUpdateSuccess; struct _EVENT_DESCRIPTOR *
0x18000e8b7  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000e8bc  jmp     loc_18000E95A
0x18000e8c1  lea     r8, asc_180028A9C; " "
0x18000e8c8  mov     esi, 104h
0x18000e8cd  mov     edx, esi; unsigned __int64
0x18000e8cf  lea     rcx, [rbp+260h+var_260]; unsigned __int16 *
0x18000e8d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e8d8  mov     rcx, [rbp+268h]; this
0x18000e8df  lea     r8, [rbp+260h+var_260]
0x18000e8e3  mov     [rsp+360h+var_338], r8; char *
0x18000e8e8  lea     r8, aContextLs; "Context %ls"
0x18000e8ef  mov     [rsp+360h+var_340], r8; __int64
0x18000e8f4  mov     r9d, eax; char *
0x18000e8f7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000e8fe  mov     edx, 0AFAh; void *
0x18000e903  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e908  mov     r8, rbx; unsigned __int16 *
0x18000e90b  mov     edx, esi; unsigned __int64
0x18000e90d  lea     rcx, [rbp+260h+var_260]; unsigned __int16 *
0x18000e911  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e916  mov     rcx, [rbp+268h]; this
0x18000e91d  mov     [rsp+360h+var_330], rbx
0x18000e922  lea     rdx, [rbp+260h+var_260]
0x18000e926  mov     [rsp+360h+var_338], rdx; char *
0x18000e92b  lea     rdx, aContextLsNameL; "Context %ls name %ls"
0x18000e932  mov     [rsp+360h+var_340], rdx; __int64
0x18000e937  mov     r9d, eax; char *
0x18000e93a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000e941  mov     edx, 0AFCh; void *
0x18000e946  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e94b  lea     r8, [rbp+260h+var_288]; struct _GUID *
0x18000e94f  mov     edx, edi; int
0x18000e951  lea     rcx, [rbp+260h+var_260]; unsigned __int16 *
0x18000e955  call    ?LogAppContainerUpdateFailure@AppContainerRegistrationHelper@@SAXPEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogAppContainerUpdateFailure(ushort const *,long,_GUID const *)
0x18000e95a  xor     r9d, r9d; struct _GUID *
0x18000e95d  mov     r8d, edi; int
0x18000e960  mov     rdx, rbx; unsigned __int16 *
0x18000e963  lea     rcx, AppModelAppContainerUpdateStop; struct _EVENT_DESCRIPTOR *
0x18000e96a  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000e96f  cmp     [rbp+260h+var_28C], 0
0x18000e973  jz      short loc_18000E98A
0x18000e975  lea     rdx, [rbp+260h+var_278]
0x18000e979  mov     ecx, 4
0x18000e97e  call    cs:__imp_EtwEventActivityIdControl
0x18000e985  nop     dword ptr [rax+rax+00h]
0x18000e98a  mov     [rbp+260h+var_290], 2
0x18000e991  mov     eax, cs:dword_180031038
0x18000e997  cmp     eax, 5
0x18000e99a  jbe     short loc_18000E9DC
0x18000e99c  mov     rdx, 400000000000h
0x18000e9a6  lea     rcx, dword_180031038
0x18000e9ad  call    _tlgKeywordOn
0x18000e9b2  test    al, al
0x18000e9b4  jz      short loc_18000E9DC
0x18000e9b6  mov     [rsp+360h+var_300], edi
0x18000e9ba  lea     rax, [rsp+360h+var_300]
0x18000e9bf  mov     [rsp+360h+var_340], rax
0x18000e9c4  lea     r8, [rbp+260h+var_288]
0x18000e9c8  lea     rdx, byte_18002B0E3
0x18000e9cf  lea     rcx, dword_180031038
0x18000e9d6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000e9db  nop
0x18000e9dc  lea     rcx, [rbp+260h+var_2C8]; this
0x18000e9e0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000e9e5  nop
0x18000e9e6  lea     rcx, [rbp+260h+var_290]
0x18000e9ea  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18000e9ef  mov     eax, edi
0x18000e9f1  mov     rcx, [rbp+260h+var_50]
0x18000e9f8  xor     rcx, rsp; StackCookie
0x18000e9fb  call    __security_check_cookie
0x18000ea00  add     rsp, 328h
0x18000ea07  pop     r15
0x18000ea09  pop     r14
0x18000ea0b  pop     r13
0x18000ea0d  pop     r12
0x18000ea0f  pop     rdi
0x18000ea10  pop     rsi
0x18000ea11  pop     rbx
0x18000ea12  pop     rbp
0x18000ea13  retn
```
