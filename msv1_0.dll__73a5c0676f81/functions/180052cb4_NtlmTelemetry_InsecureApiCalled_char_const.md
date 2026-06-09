# NtlmTelemetry::InsecureApiCalled(char const *)

- ea: `0x180052cb4`
- end: `0x180052ded`
- name: `?InsecureApiCalled@NtlmTelemetry@@YAXPEBD@Z`
- size: `313`
- prototype: `void __fastcall(NtlmTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024c00`

## callees

- `0x1800018cc`
- `0x18001eaec`
- `0x18001f878`
- `0x180024bd0`
- `0x18002fb50`
- `0x180052cb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052d4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052d4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NtlmTelemetry::InsecureApiCalled(NtlmTelemetry *this, const char *a2)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // [rsp+60h] [rbp-A0h] BYREF
  DWORD CurrentProcessId; // [rsp+64h] [rbp-9Ch] BYREF
  int v6; // [rsp+68h] [rbp-98h] BYREF
  DWORD v7; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v8; // [rsp+70h] [rbp-90h] BYREF
  char *v9; // [rsp+78h] [rbp-88h] BYREF
  char *v10; // [rsp+80h] [rbp-80h] BYREF
  const char *v11; // [rsp+88h] [rbp-78h] BYREF
  __int64 v12; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v13[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v14; // [rsp+C0h] [rbp-40h] BYREF
  char v15; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v16; // [rsp+6C0h] [rbp+5C0h]
  _BYTE v17[8]; // [rsp+6E8h] [rbp+5E8h] BYREF

  SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v13, LsaFunctions);
  if ( (unsigned int)dword_1800861D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800861D8, 0x200000000000LL) )
  {
    v8 = 0x1000000;
    v4 = v13[16];
    v9 = &v14;
    v10 = &v15;
    CurrentProcessId = GetCurrentProcessId();
    v6 = v16;
    v7 = GetCurrentProcessId();
    v11 = "MspLm20GetChallengeResponse";
    v12 = 1;
    ((void (__fastcall *)(__int64, int *, __int64, __int64 *, const char **, DWORD *, int *, DWORD *, char **, char **, int *, __int64 *))_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>)(
      v2,
      &dword_18007A77C,
      v3,
      &v12,
      &v11,
      &v7,
      &v6,
      &CurrentProcessId,
      &v10,
      &v9,
      &v4,
      &v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v17);
}

```

## disassembly

```asm
0x180052cb4  push    rbp
0x180052cb6  lea     rbp, [rsp-600h]
0x180052cbe  sub     rsp, 700h
0x180052cc5  mov     rax, cs:__security_cookie
0x180052ccc  xor     rax, rsp
0x180052ccf  mov     [rbp+600h+var_10], rax
0x180052cd6  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x180052cdd  lea     rcx, [rbp+600h+var_660]; this
0x180052ce1  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180052ce6  nop
0x180052ce7  mov     eax, cs:dword_1800861D8
0x180052ced  cmp     eax, 5
0x180052cf0  jbe     loc_180052DC9
0x180052cf6  mov     rdx, 200000000000h
0x180052d00  lea     rcx, dword_1800861D8
0x180052d07  call    _tlgKeywordOn
0x180052d0c  test    al, al
0x180052d0e  jz      loc_180052DC9
0x180052d14  mov     [rsp+700h+var_690], 1000000h
0x180052d1d  movzx   eax, [rbp+600h+var_650]
0x180052d21  mov     [rsp+700h+var_6A0], eax
0x180052d25  lea     rax, [rbp+600h+var_640]
0x180052d29  mov     [rsp+700h+var_688], rax
0x180052d2e  lea     rax, [rbp+600h+var_440]
0x180052d35  mov     [rbp+600h+var_680], rax
0x180052d39  call    cs:__imp_GetCurrentProcessId
0x180052d3f  mov     [rsp+700h+var_69C], eax
0x180052d43  mov     eax, [rbp+600h+var_40]
0x180052d49  mov     [rsp+700h+var_698], eax
0x180052d4d  call    cs:__imp_GetCurrentProcessId
0x180052d53  mov     [rsp+700h+var_694], eax
0x180052d57  lea     rax, aMsplm20getchal; "MspLm20GetChallengeResponse"
0x180052d5e  mov     [rbp+600h+var_678], rax
0x180052d62  mov     [rbp+600h+var_670], 1
0x180052d6a  lea     rax, [rsp+700h+var_690]
0x180052d6f  mov     [rsp+700h+var_6A8], rax
0x180052d74  lea     rax, [rsp+700h+var_6A0]
0x180052d79  mov     [rsp+700h+var_6B0], rax
0x180052d7e  lea     rax, [rsp+700h+var_688]
0x180052d83  mov     [rsp+700h+var_6B8], rax
0x180052d88  lea     rax, [rbp+600h+var_680]
0x180052d8c  mov     [rsp+700h+var_6C0], rax
0x180052d91  lea     rax, [rsp+700h+var_69C]
0x180052d96  mov     [rsp+700h+var_6C8], rax
0x180052d9b  lea     rax, [rsp+700h+var_698]
0x180052da0  mov     [rsp+700h+var_6D0], rax
0x180052da5  lea     rax, [rsp+700h+var_694]
0x180052daa  mov     [rsp+700h+var_6D8], rax
0x180052daf  lea     rax, [rbp+600h+var_678]
0x180052db3  mov     [rsp+700h+var_6E0], rax
0x180052db8  lea     r9, [rbp+600h+var_670]
0x180052dbc  lea     rdx, dword_18007A77C
0x180052dc3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapSz@G@@U4@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@542@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180052dc8  nop
0x180052dc9  lea     rcx, [rbp+600h+var_18]
0x180052dd0  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180052dd5  mov     rcx, [rbp+600h+var_10]
0x180052ddc  xor     rcx, rsp; StackCookie
0x180052ddf  call    __security_check_cookie
0x180052de4  add     rsp, 700h
0x180052deb  pop     rbp
0x180052dec  retn
```
