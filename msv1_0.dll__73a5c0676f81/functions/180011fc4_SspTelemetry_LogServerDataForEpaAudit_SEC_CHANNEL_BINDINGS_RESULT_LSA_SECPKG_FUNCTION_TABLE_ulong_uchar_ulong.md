# SspTelemetry::LogServerDataForEpaAudit(_SEC_CHANNEL_BINDINGS_RESULT *,_LSA_SECPKG_FUNCTION_TABLE *,ulong,uchar,ulong)

- ea: `0x180011fc4`
- end: `0x1800121a3`
- name: `?LogServerDataForEpaAudit@SspTelemetry@@YAXPEAU_SEC_CHANNEL_BINDINGS_RESULT@@PEAU_LSA_SECPKG_FUNCTION_TABLE@@KEK@Z`
- size: `479`
- prototype: `void __fastcall(SspTelemetry *__hidden this, struct _SEC_CHANNEL_BINDINGS_RESULT *, struct _LSA_SECPKG_FUNCTION_TABLE *, unsigned int, unsigned __int8, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180011d10`

## callees

- `0x180001208`
- `0x180011fc4`
- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x180024bd0`
- `0x18002fb50`
- `0x18005a418`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800120d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800120d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SspTelemetry::LogServerDataForEpaAudit(
        SspTelemetry *this,
        struct _LSA_SECPKG_FUNCTION_TABLE *a2,
        struct _LSA_SECPKG_FUNCTION_TABLE *a3,
        unsigned __int8 a4,
        int a5)
{
  int v5; // r13d
  const WCHAR *v8; // rbx
  __int64 SvchostServiceTag; // rax
  const WCHAR *v10; // r14
  const WCHAR *v11; // r12
  int v12; // r15d
  int v13; // r8d
  int v14; // eax
  const WCHAR *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v19; // [rsp+88h] [rbp-78h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+94h] [rbp-6Ch] BYREF
  int v22; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+9Ch] [rbp-64h] BYREF
  int v24; // [rsp+A0h] [rbp-60h] BYREF
  DWORD CurrentProcessId; // [rsp+A4h] [rbp-5Ch] BYREF
  const WCHAR *v26; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-50h] BYREF
  const WCHAR *v28; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v29; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v32; // [rsp+F0h] [rbp-10h] BYREF
  char v33; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v34; // [rsp+6F0h] [rbp+5F0h]
  _BYTE v35[8]; // [rsp+718h] [rbp+618h] BYREF

  v5 = a4;
  v18 = (int)a3;
  v8 = 0;
  v26 = 0;
  if ( a2 )
  {
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v31, a2);
    SvchostServiceTag = SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v31, &v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v26,
      SvchostServiceTag);
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v19);
    v10 = (const WCHAR *)&v32;
    v11 = (const WCHAR *)&v33;
    v12 = v34;
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v35);
    v8 = v26;
  }
  else
  {
    v10 = 0;
    v12 = 0;
    v11 = 0;
  }
  if ( (unsigned int)dword_180086270 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180086270, 0x400000000000LL) )
  {
    v27 = 0x1000000;
    v18 = a5;
    if ( this )
      v14 = *(_DWORD *)this;
    else
      v14 = 0;
    v20 = v14;
    v21 = v13;
    v22 = v5;
    v15 = &Src;
    if ( a2 )
      v15 = v11;
    v28 = v15;
    v23 = v12;
    v24 = v12;
    CurrentProcessId = GetCurrentProcessId();
    if ( a2 )
    {
      v19 = v10;
      if ( v8 )
        goto LABEL_16;
    }
    else
    {
      v19 = &Src;
    }
    v8 = &Src;
LABEL_16:
    v29 = v8;
    v30 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v16,
      byte_18007B0CD,
      v17,
      &v30,
      &v29,
      &v19,
      &CurrentProcessId,
      &v24,
      &v23,
      &v28,
      &v22,
      &v21,
      &v20,
      &v18,
      &v27);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v26);
}

```

## disassembly

```asm
0x180011fc4  push    rbp
0x180011fc6  push    rbx
0x180011fc7  push    rsi
0x180011fc8  push    rdi
0x180011fc9  push    r12
0x180011fcb  push    r13
0x180011fcd  push    r14
0x180011fcf  push    r15
0x180011fd1  lea     rbp, [rsp-638h]
0x180011fd9  sub     rsp, 738h
0x180011fe0  mov     rax, cs:__security_cookie
0x180011fe7  xor     rax, rsp
0x180011fea  mov     [rbp+670h+var_50], rax
0x180011ff1  movzx   r13d, r9b
0x180011ff5  mov     [rbp+670h+var_6F0], r8d
0x180011ff9  mov     rdi, rdx
0x180011ffc  mov     rsi, rcx
0x180011fff  xor     ebx, ebx
0x180012001  mov     [rbp+670h+var_6C8], rbx
0x180012005  test    rdx, rdx
0x180012008  jz      short loc_18001205D
0x18001200a  lea     rcx, [rbp+670h+var_6A0]; this
0x18001200e  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180012013  lea     rdx, [rbp+670h+var_6E8]
0x180012017  lea     rcx, [rbp+670h+var_6A0]
0x18001201b  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x180012020  mov     rdx, rax
0x180012023  lea     rcx, [rbp+670h+var_6C8]
0x180012027  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001202c  lea     rcx, [rbp+670h+var_6E8]
0x180012030  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180012035  lea     r14, [rbp+670h+var_680]
0x180012039  lea     r12, [rbp+670h+var_480]
0x180012040  mov     r15d, [rbp+670h+var_80]
0x180012047  lea     rcx, [rbp+670h+var_58]
0x18001204e  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180012053  mov     rbx, [rbp+670h+var_6C8]
0x180012057  mov     r8d, [rbp+670h+var_6F0]
0x18001205b  jmp     short loc_180012066
0x18001205d  xor     r14d, r14d
0x180012060  xor     r15d, r15d
0x180012063  xor     r12d, r12d
0x180012066  mov     eax, cs:dword_180086270
0x18001206c  cmp     eax, 5
0x18001206f  jbe     loc_180012177
0x180012075  mov     rdx, 400000000000h
0x18001207f  lea     rcx, dword_180086270
0x180012086  call    _tlgKeywordOn
0x18001208b  test    al, al
0x18001208d  jz      loc_180012177
0x180012093  mov     [rbp+670h+var_6C0], 1000000h
0x18001209b  mov     eax, dword ptr [rbp+670h+arg_20]
0x1800120a1  mov     [rbp+670h+var_6F0], eax
0x1800120a4  test    rsi, rsi
0x1800120a7  jz      short loc_1800120AD
0x1800120a9  mov     eax, [rsi]
0x1800120ab  jmp     short loc_1800120AF
0x1800120ad  xor     eax, eax
0x1800120af  mov     [rbp+670h+var_6E0], eax
0x1800120b2  mov     [rbp+670h+var_6DC], r8d
0x1800120b6  mov     [rbp+670h+var_6D8], r13d
0x1800120ba  lea     rsi, Src
0x1800120c1  mov     rax, rsi
0x1800120c4  test    rdi, rdi
0x1800120c7  cmovnz  rax, r12
0x1800120cb  mov     [rbp+670h+var_6B8], rax
0x1800120cf  mov     [rbp+670h+var_6D4], r15d
0x1800120d3  mov     [rbp+670h+var_6D0], r15d
0x1800120d7  call    cs:__imp_GetCurrentProcessId
0x1800120dd  mov     [rbp+670h+var_6CC], eax
0x1800120e0  test    rdi, rdi
0x1800120e3  jz      short loc_1800120F0
0x1800120e5  mov     [rbp+670h+var_6E8], r14
0x1800120e9  test    rbx, rbx
0x1800120ec  jz      short loc_1800120F4
0x1800120ee  jmp     short loc_1800120F7
0x1800120f0  mov     [rbp+670h+var_6E8], rsi
0x1800120f4  mov     rbx, rsi
0x1800120f7  mov     [rbp+670h+var_6B0], rbx
0x1800120fb  mov     [rbp+670h+var_6A8], 1
0x180012103  lea     rax, [rbp+670h+var_6C0]
0x180012107  mov     [rsp+770h+var_700], rax
0x18001210c  lea     rax, [rbp+670h+var_6F0]
0x180012110  mov     [rsp+770h+var_708], rax
0x180012115  lea     rax, [rbp+670h+var_6E0]
0x180012119  mov     [rsp+770h+var_710], rax
0x18001211e  lea     rax, [rbp+670h+var_6DC]
0x180012122  mov     [rsp+770h+var_718], rax
0x180012127  lea     rax, [rbp+670h+var_6D8]
0x18001212b  mov     [rsp+770h+var_720], rax
0x180012130  lea     rax, [rbp+670h+var_6B8]
0x180012134  mov     [rsp+770h+var_728], rax
0x180012139  lea     rax, [rbp+670h+var_6D4]
0x18001213d  mov     [rsp+770h+var_730], rax
0x180012142  lea     rax, [rbp+670h+var_6D0]
0x180012146  mov     [rsp+770h+var_738], rax
0x18001214b  lea     rax, [rbp+670h+var_6CC]
0x18001214f  mov     [rsp+770h+var_740], rax
0x180012154  lea     rax, [rbp+670h+var_6E8]
0x180012158  mov     [rsp+770h+var_748], rax
0x18001215d  lea     rax, [rbp+670h+var_6B0]
0x180012161  mov     [rsp+770h+var_750], rax
0x180012166  lea     r9, [rbp+670h+var_6A8]
0x18001216a  lea     rdx, byte_18007B0CD
0x180012171  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U2@U3@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@44344442@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180012176  nop
0x180012177  lea     rcx, [rbp+670h+var_6C8]
0x18001217b  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180012180  mov     rcx, [rbp+670h+var_50]
0x180012187  xor     rcx, rsp; StackCookie
0x18001218a  call    __security_check_cookie
0x18001218f  add     rsp, 738h
0x180012196  pop     r15
0x180012198  pop     r14
0x18001219a  pop     r13
0x18001219c  pop     r12
0x18001219e  pop     rdi
0x18001219f  pop     rsi
0x1800121a0  pop     rbx
0x1800121a1  pop     rbp
0x1800121a2  retn
```
