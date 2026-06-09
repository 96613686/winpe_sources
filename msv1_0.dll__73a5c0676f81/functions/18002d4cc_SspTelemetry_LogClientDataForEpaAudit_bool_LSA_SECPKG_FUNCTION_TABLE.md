# SspTelemetry::LogClientDataForEpaAudit(bool,_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x18002d4cc`
- end: `0x18002d674`
- name: `?LogClientDataForEpaAudit@SspTelemetry@@YAX_NPEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `424`
- prototype: `void __fastcall(SspTelemetry *__hidden this, bool, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18002e0a4`

## callees

- `0x180001f94`
- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x180024bd0`
- `0x18002d4cc`
- `0x18002fb50`
- `0x18005a418`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d5c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d5c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SspTelemetry::LogClientDataForEpaAudit(
        SspTelemetry *this,
        struct _LSA_SECPKG_FUNCTION_TABLE *a2,
        struct _LSA_SECPKG_FUNCTION_TABLE *a3)
{
  int v4; // r12d
  const WCHAR *v5; // rbx
  __int64 SvchostServiceTag; // rax
  const WCHAR *v7; // r15
  const WCHAR *v8; // rsi
  int v9; // r14d
  __int64 v10; // rcx
  __int64 v11; // r8
  const WCHAR *v12; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+68h] [rbp-98h] BYREF
  int v14; // [rsp+6Ch] [rbp-94h] BYREF
  int v15; // [rsp+70h] [rbp-90h] BYREF
  DWORD CurrentProcessId; // [rsp+74h] [rbp-8Ch] BYREF
  const WCHAR *v17; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v19; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v20; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v23; // [rsp+C0h] [rbp-40h] BYREF
  char v24; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v25; // [rsp+6C0h] [rbp+5C0h]
  _BYTE v26[8]; // [rsp+6E8h] [rbp+5E8h] BYREF

  v4 = (unsigned __int8)this;
  v5 = 0;
  v17 = 0;
  if ( a2 )
  {
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v22, a2);
    SvchostServiceTag = SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v22, &v12);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v17,
      SvchostServiceTag);
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v12);
    v7 = (const WCHAR *)&v23;
    v8 = (const WCHAR *)&v24;
    v9 = v25;
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v26);
    v5 = v17;
  }
  else
  {
    v7 = 0;
    v9 = 0;
    v8 = 0;
  }
  if ( (unsigned int)dword_180086270 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180086270, 0x400000000000LL) )
  {
    v18 = 0x1000000;
    v13 = v4;
    if ( a2 )
    {
      v12 = v7;
    }
    else
    {
      v12 = &Src;
      v8 = &Src;
    }
    v19 = v8;
    v14 = v9;
    v15 = v9;
    CurrentProcessId = GetCurrentProcessId();
    if ( !a2 || !v5 )
      v5 = &Src;
    v20 = v5;
    v21 = 1;
    ((void (__fastcall *)(__int64, __int16 *, __int64, __int64 *, const WCHAR **, DWORD *, int *, int *, const WCHAR **, const WCHAR **, int *, __int64 *))_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>)(
      v10,
      word_18007B01A,
      v11,
      &v21,
      &v20,
      &CurrentProcessId,
      &v15,
      &v14,
      &v19,
      &v12,
      &v13,
      &v18);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v17);
}

```

## disassembly

```asm
0x18002d4cc  push    rbp
0x18002d4ce  push    rbx
0x18002d4cf  push    rsi
0x18002d4d0  push    rdi
0x18002d4d1  push    r12
0x18002d4d3  push    r14
0x18002d4d5  push    r15
0x18002d4d7  lea     rbp, [rsp-600h]
0x18002d4df  sub     rsp, 700h
0x18002d4e6  mov     rax, cs:__security_cookie
0x18002d4ed  xor     rax, rsp
0x18002d4f0  mov     [rbp+630h+var_40], rax
0x18002d4f7  mov     rdi, rdx
0x18002d4fa  movzx   r12d, cl
0x18002d4fe  xor     ebx, ebx
0x18002d500  mov     [rsp+730h+var_6B8], rbx
0x18002d505  test    rdx, rdx
0x18002d508  jz      short loc_18002D55D
0x18002d50a  lea     rcx, [rbp+630h+var_690]; this
0x18002d50e  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x18002d513  lea     rdx, [rsp+730h+var_6D0]
0x18002d518  lea     rcx, [rbp+630h+var_690]
0x18002d51c  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x18002d521  mov     rdx, rax
0x18002d524  lea     rcx, [rsp+730h+var_6B8]
0x18002d529  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002d52e  lea     rcx, [rsp+730h+var_6D0]
0x18002d533  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x18002d538  lea     r15, [rbp+630h+var_670]
0x18002d53c  lea     rsi, [rbp+630h+var_470]
0x18002d543  mov     r14d, [rbp+630h+var_70]
0x18002d54a  lea     rcx, [rbp+630h+var_48]
0x18002d551  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x18002d556  mov     rbx, [rsp+730h+var_6B8]
0x18002d55b  jmp     short loc_18002D565
0x18002d55d  xor     r15d, r15d
0x18002d560  xor     r14d, r14d
0x18002d563  xor     esi, esi
0x18002d565  mov     eax, cs:dword_180086270
0x18002d56b  cmp     eax, 5
0x18002d56e  jbe     loc_18002D649
0x18002d574  mov     rdx, 400000000000h
0x18002d57e  lea     rcx, dword_180086270
0x18002d585  call    _tlgKeywordOn
0x18002d58a  test    al, al
0x18002d58c  jz      loc_18002D649
0x18002d592  mov     [rbp+630h+var_6B0], 1000000h
0x18002d59a  mov     [rsp+730h+var_6C8], r12d
0x18002d59f  lea     r12, Src
0x18002d5a6  test    rdi, rdi
0x18002d5a9  jz      short loc_18002D5B2
0x18002d5ab  mov     [rsp+730h+var_6D0], r15
0x18002d5b0  jmp     short loc_18002D5BA
0x18002d5b2  mov     [rsp+730h+var_6D0], r12
0x18002d5b7  mov     rsi, r12
0x18002d5ba  mov     [rbp+630h+var_6A8], rsi
0x18002d5be  mov     [rsp+730h+var_6C4], r14d
0x18002d5c3  mov     [rsp+730h+var_6C0], r14d
0x18002d5c8  call    cs:__imp_GetCurrentProcessId
0x18002d5ce  mov     [rsp+730h+var_6BC], eax
0x18002d5d2  test    rdi, rdi
0x18002d5d5  jz      short loc_18002D5DC
0x18002d5d7  test    rbx, rbx
0x18002d5da  jnz     short loc_18002D5DF
0x18002d5dc  mov     rbx, r12
0x18002d5df  mov     [rbp+630h+var_6A0], rbx
0x18002d5e3  mov     [rbp+630h+var_698], 1
0x18002d5eb  lea     rax, [rbp+630h+var_6B0]
0x18002d5ef  mov     [rsp+730h+var_6D8], rax
0x18002d5f4  lea     rax, [rsp+730h+var_6C8]
0x18002d5f9  mov     [rsp+730h+var_6E0], rax
0x18002d5fe  lea     rax, [rsp+730h+var_6D0]
0x18002d603  mov     [rsp+730h+var_6E8], rax
0x18002d608  lea     rax, [rbp+630h+var_6A8]
0x18002d60c  mov     [rsp+730h+var_6F0], rax
0x18002d611  lea     rax, [rsp+730h+var_6C4]
0x18002d616  mov     [rsp+730h+var_6F8], rax
0x18002d61b  lea     rax, [rsp+730h+var_6C0]
0x18002d620  mov     [rsp+730h+var_700], rax
0x18002d625  lea     rax, [rsp+730h+var_6BC]
0x18002d62a  mov     [rsp+730h+var_708], rax
0x18002d62f  lea     rax, [rbp+630h+var_6A0]
0x18002d633  mov     [rsp+730h+var_710], rax
0x18002d638  lea     r9, [rbp+630h+var_698]
0x18002d63c  lea     rdx, word_18007B01A
0x18002d643  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@443342@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18002d648  nop
0x18002d649  lea     rcx, [rsp+730h+var_6B8]
0x18002d64e  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x18002d653  mov     rcx, [rbp+630h+var_40]
0x18002d65a  xor     rcx, rsp; StackCookie
0x18002d65d  call    __security_check_cookie
0x18002d662  add     rsp, 700h
0x18002d669  pop     r15
0x18002d66b  pop     r14
0x18002d66d  pop     r12
0x18002d66f  pop     rdi
0x18002d670  pop     rsi
0x18002d671  pop     rbx
0x18002d672  pop     rbp
0x18002d673  retn
```
