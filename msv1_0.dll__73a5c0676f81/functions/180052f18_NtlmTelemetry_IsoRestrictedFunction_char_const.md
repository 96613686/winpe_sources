# NtlmTelemetry::IsoRestrictedFunction(char const *)

- ea: `0x180052f18`
- end: `0x1800530a4`
- name: `?IsoRestrictedFunction@NtlmTelemetry@@YAXPEBD@Z`
- size: `396`
- prototype: `void __fastcall(NtlmTelemetry *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180024c00`
- `0x1800462b0`
- `0x180046700`

## callees

- `0x180001d10`
- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x180024bd0`
- `0x18002fb50`
- `0x180052f18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052fb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052fc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052fb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052fc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NtlmTelemetry::IsoRestrictedFunction(NtlmTelemetry *this, const char *a2)
{
  __int64 v3; // r8
  const WCHAR *v4; // rcx
  int v5; // [rsp+70h] [rbp-90h] BYREF
  DWORD CurrentProcessId; // [rsp+74h] [rbp-8Ch] BYREF
  int v7; // [rsp+78h] [rbp-88h] BYREF
  DWORD v8; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v9; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v10; // [rsp+88h] [rbp-78h] BYREF
  __int64 v11; // [rsp+90h] [rbp-70h] BYREF
  char *v12; // [rsp+98h] [rbp-68h] BYREF
  char *v13; // [rsp+A0h] [rbp-60h] BYREF
  NtlmTelemetry *v14; // [rsp+A8h] [rbp-58h] BYREF
  const WCHAR *v15; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v16; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v17[32]; // [rsp+C0h] [rbp-40h] BYREF
  char v18; // [rsp+E0h] [rbp-20h] BYREF
  char v19; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v20; // [rsp+6E0h] [rbp+5E0h]
  _BYTE v21[8]; // [rsp+708h] [rbp+608h] BYREF

  SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v17, LsaFunctions);
  SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v17, &v10);
  if ( (unsigned int)dword_1800861D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800861D8, 0x400000000000LL) )
  {
    v11 = 0x1000000;
    v5 = v17[16];
    v12 = &v18;
    v13 = &v19;
    CurrentProcessId = GetCurrentProcessId();
    v7 = v20;
    v8 = GetCurrentProcessId();
    v14 = this;
    v4 = &Src;
    if ( v10 )
      v4 = v10;
    v15 = v4;
    v9 = ((unsigned int)dword_180087A84 >> 5) & 1;
    v16 = 1;
    ((void (__fastcall *)(const WCHAR *, char *, __int64, __int64 *, unsigned int *, const WCHAR **, NtlmTelemetry **, DWORD *, int *, DWORD *, char **, char **, int *, __int64 *))_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>)(
      v4,
      byte_18007A60B,
      v3,
      &v16,
      &v9,
      &v15,
      &v14,
      &v8,
      &v7,
      &CurrentProcessId,
      &v13,
      &v12,
      &v5,
      &v11);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v21);
}

```

## disassembly

```asm
0x180052f18  mov     [rsp-8+arg_0], rbx
0x180052f1d  push    rbp
0x180052f1e  lea     rbp, [rsp-620h]
0x180052f26  sub     rsp, 720h
0x180052f2d  mov     rax, cs:__security_cookie
0x180052f34  xor     rax, rsp
0x180052f37  mov     [rbp+620h+var_10], rax
0x180052f3e  mov     rbx, rcx
0x180052f41  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x180052f48  lea     rcx, [rbp+620h+var_660]; this
0x180052f4c  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180052f51  nop
0x180052f52  lea     rdx, [rbp+620h+var_698]
0x180052f56  lea     rcx, [rbp+620h+var_660]
0x180052f5a  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x180052f5f  nop
0x180052f60  mov     eax, cs:dword_1800861D8
0x180052f66  cmp     eax, 5
0x180052f69  jbe     loc_18005306E
0x180052f6f  mov     rdx, 400000000000h
0x180052f79  lea     rcx, dword_1800861D8
0x180052f80  call    _tlgKeywordOn
0x180052f85  test    al, al
0x180052f87  jz      loc_18005306E
0x180052f8d  mov     [rbp+620h+var_690], 1000000h
0x180052f95  movzx   eax, [rbp+620h+var_650]
0x180052f99  mov     [rsp+720h+var_6B0], eax
0x180052f9d  lea     rax, [rbp+620h+var_640]
0x180052fa1  mov     [rbp+620h+var_688], rax
0x180052fa5  lea     rax, [rbp+620h+var_440]
0x180052fac  mov     [rbp+620h+var_680], rax
0x180052fb0  call    cs:__imp_GetCurrentProcessId
0x180052fb6  mov     [rsp+720h+var_6AC], eax
0x180052fba  mov     eax, [rbp+620h+var_40]
0x180052fc0  mov     [rsp+720h+var_6A8], eax
0x180052fc4  call    cs:__imp_GetCurrentProcessId
0x180052fca  mov     [rsp+720h+var_6A4], eax
0x180052fce  mov     [rbp+620h+var_678], rbx
0x180052fd2  lea     rcx, Src
0x180052fd9  mov     rax, [rbp+620h+var_698]
0x180052fdd  test    rax, rax
0x180052fe0  cmovnz  rcx, rax
0x180052fe4  mov     [rbp+620h+var_670], rcx
0x180052fe8  mov     eax, cs:dword_180087A84
0x180052fee  shr     eax, 5
0x180052ff1  and     eax, 1
0x180052ff4  mov     [rbp+620h+var_6A0], eax
0x180052ff7  mov     [rbp+620h+var_668], 1
0x180052fff  lea     rax, [rbp+620h+var_690]
0x180053003  mov     [rsp+720h+var_6B8], rax
0x180053008  lea     rax, [rsp+720h+var_6B0]
0x18005300d  mov     [rsp+720h+var_6C0], rax
0x180053012  lea     rax, [rbp+620h+var_688]
0x180053016  mov     [rsp+720h+var_6C8], rax
0x18005301b  lea     rax, [rbp+620h+var_680]
0x18005301f  mov     [rsp+720h+var_6D0], rax
0x180053024  lea     rax, [rsp+720h+var_6AC]
0x180053029  mov     [rsp+720h+var_6D8], rax
0x18005302e  lea     rax, [rsp+720h+var_6A8]
0x180053033  mov     [rsp+720h+var_6E0], rax
0x180053038  lea     rax, [rsp+720h+var_6A4]
0x18005303d  mov     [rsp+720h+var_6E8], rax
0x180053042  lea     rax, [rbp+620h+var_678]
0x180053046  mov     [rsp+720h+var_6F0], rax
0x18005304b  lea     rax, [rbp+620h+var_670]
0x18005304f  mov     [rsp+720h+var_6F8], rax
0x180053054  lea     rax, [rbp+620h+var_6A0]
0x180053058  mov     [rsp+720h+var_700], rax
0x18005305d  lea     r9, [rbp+620h+var_668]
0x180053061  lea     rdx, byte_18007A60B
0x180053068  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U2@U2@U2@U3@U3@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@3334432@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005306d  nop
0x18005306e  lea     rcx, [rbp+620h+var_698]
0x180053072  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180053077  nop
0x180053078  lea     rcx, [rbp+620h+var_18]
0x18005307f  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180053084  mov     rcx, [rbp+620h+var_10]
0x18005308b  xor     rcx, rsp; StackCookie
0x18005308e  call    __security_check_cookie
0x180053093  mov     rbx, [rsp+720h+arg_0]
0x18005309b  add     rsp, 720h
0x1800530a2  pop     rbp
0x1800530a3  retn
```
