# _lambda_165f69de33380801137d42b0e005749c_::operator()(Windows::Internal::CNoResult &)

- ea: `0x18008ff8c`
- end: `0x1800901a7`
- name: `??R_lambda_165f69de33380801137d42b0e005749c_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180092990`

## callees

- `0x180008524`
- `0x180008544`
- `0x18001ad08`
- `0x18001e9a4`
- `0x1800415f0`
- `0x18005cf54`
- `0x18007fb9c`
- `0x18008ff8c`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18008ffbb`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18008fffc`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18008ffbb`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18008fffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180090036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180090036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090095`
- `Input!__imp_InstallLayoutOrTip` at `0x1800900a6`
- `Input!__imp_InstallLayoutOrTip` at `0x1800900cc`
- `Input!__imp_InstallLayoutOrTip` at `0x1800900eb`
- `Input!__imp_InstallLayoutOrTip` at `0x1800900a6`
- `Input!__imp_InstallLayoutOrTip` at `0x1800900cc`
- `Input!__imp_InstallLayoutOrTip` at `0x1800900eb`
- `Input!__imp_SetDefaultLayoutOrTip` at `0x1800900f6`
- `Input!__imp_SetDefaultLayoutOrTip` at `0x1800900f6`

## string_xrefs

- `0x18009000a`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x18009004a`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`
- `0x180090138`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _lambda_165f69de33380801137d42b0e005749c_::operator()(__int64 a1, void *a2)
{
  int LocaleInfo; // eax
  const char *v4; // r9
  UINT32 v5; // edi
  const WCHAR *v6; // rbx
  unsigned int LastError; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  const char *v10; // r9
  HRESULT v11; // eax
  PCWSTR StringRawBuffer; // r15
  PCWSTR v13; // rsi
  PCWSTR v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rcx
  void *v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  int v21; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  void *v23; // [rsp+78h] [rbp+48h] BYREF
  HSTRING string; // [rsp+80h] [rbp+50h] BYREF
  LPWSTR lpLCData; // [rsp+88h] [rbp+58h] BYREF

  v23 = a2;
  string = 0;
  LocaleInfo = GetLocaleInfoEx(0, 0x5Eu, 0, 0);
  v5 = LocaleInfo;
  if ( LocaleInfo <= 0 )
    goto LABEL_11;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpLCData,
    0,
    LocaleInfo,
    v4);
  v6 = lpLCData;
  if ( !lpLCData )
  {
    LastError = -2147024882;
    v8 = 2147942414LL;
    v9 = 431;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
      (const char *)v8,
      v21);
    goto LABEL_9;
  }
  if ( GetLocaleInfoEx(0, 0x5Eu, lpLCData, v5) )
  {
    WindowsDeleteString(string);
    string = 0;
    v11 = WindowsCreateString(v6, v5, &string);
    LastError = v11;
    if ( v11 < 0 )
    {
      v8 = (unsigned int)v11;
      v9 = 433;
      goto LABEL_8;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpLCData);
LABEL_11:
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 8), 0);
    v13 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 24), 0);
    v14 = WindowsGetStringRawBuffer(string, 0);
    InstallLayoutOrTip(StringRawBuffer, 64);
    v15 = -1;
    if ( v13 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v13[v16] );
      if ( v16 )
        InstallLayoutOrTip(v13, 0);
    }
    if ( v14 )
    {
      do
        ++v15;
      while ( v14[v15] );
      if ( v15 )
        InstallLayoutOrTip(v14, 0);
    }
    SetDefaultLayoutOrTip(StringRawBuffer, 0);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
      &v23,
      a1);
    v17 = v23;
    if ( !v23 )
    {
      v23 = 0;
      v18 = CloudExperienceHostCreateElevatedObject(
              &GUID_b742e827_ede6_400f_8312_cd522198be86,
              &GUID_7f21035b_4610_43a3_9f5c_285e70d9f52d,
              &v23);
      LastError = v18;
      if ( v18 < 0 )
      {
        v19 = 457;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
          (const char *)(unsigned int)v18,
          v21);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v23);
        goto LABEL_28;
      }
      v17 = v23;
    }
    v18 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, HSTRING))(*(_QWORD *)v17 + 48LL))(
            v17,
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(a1 + 24),
            string);
    LastError = v18;
    if ( v18 >= 0 )
    {
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v23);
      LastError = 0;
      goto LABEL_28;
    }
    v19 = 459;
    goto LABEL_23;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1B0,
                (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
                v10);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpLCData);
LABEL_28:
  WindowsDeleteString(string);
  return LastError;
}

```

## disassembly

```asm
0x18008ff8c  mov     [rsp-38h+arg_8], rdx
0x18008ff91  push    rbp
0x18008ff92  push    rbx
0x18008ff93  push    rsi
0x18008ff94  push    rdi
0x18008ff95  push    r12
0x18008ff97  push    r14
0x18008ff99  push    r15
0x18008ff9b  mov     rbp, rsp
0x18008ff9e  sub     rsp, 30h
0x18008ffa2  mov     r14, rcx
0x18008ffa5  xor     r12d, r12d
0x18008ffa8  mov     [rbp+string], r12
0x18008ffac  xor     r9d, r9d; cchData
0x18008ffaf  xor     r8d, r8d; lpLCData
0x18008ffb2  lea     esi, [r12+5Eh]
0x18008ffb7  mov     edx, esi; LCType
0x18008ffb9  xor     ecx, ecx; lpLocaleName
0x18008ffbb  call    cs:__imp_GetLocaleInfoEx
0x18008ffc1  movsxd  rdi, eax
0x18008ffc4  test    eax, eax
0x18008ffc6  jle     loc_180090071
0x18008ffcc  mov     r8, rdi
0x18008ffcf  xor     edx, edx
0x18008ffd1  lea     rcx, [rbp+lpLCData]
0x18008ffd5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18008ffda  mov     rbx, [rbp+lpLCData]
0x18008ffde  test    rbx, rbx
0x18008ffe1  jnz     short loc_18008FFF2
0x18008ffe3  mov     ebx, 8007000Eh
0x18008ffe8  mov     r9d, ebx
0x18008ffeb  mov     edx, 1AFh
0x18008fff0  jmp     short loc_18009004A
0x18008fff2  mov     r9d, edi; cchData
0x18008fff5  mov     r8, rbx; lpLCData
0x18008fff8  mov     edx, esi; LCType
0x18008fffa  xor     ecx, ecx; lpLocaleName
0x18008fffc  call    cs:__imp_GetLocaleInfoEx
0x180090002  test    eax, eax
0x180090004  jnz     short loc_18009001F
0x180090006  mov     rcx, [rbp+38h]; this
0x18009000a  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180090011  mov     edx, 1B0h; void *
0x180090016  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009001b  mov     ebx, eax
0x18009001d  jmp     short loc_18009005A
0x18009001f  mov     rcx, [rbp+string]; string
0x180090023  call    cs:__imp_WindowsDeleteString
0x180090029  mov     [rbp+string], r12
0x18009002d  lea     r8, [rbp+string]; string
0x180090031  mov     edx, edi; length
0x180090033  mov     rcx, rbx; sourceString
0x180090036  call    cs:__imp_WindowsCreateString
0x18009003c  mov     ebx, eax
0x18009003e  test    eax, eax
0x180090040  jns     short loc_180090068
0x180090042  mov     r9d, eax; char *
0x180090045  mov     edx, 1B1h; void *
0x18009004a  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180090051  mov     rcx, [rbp+38h]; this
0x180090055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009005a  lea     rcx, [rbp+lpLCData]
0x18009005e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180090063  jmp     loc_18009018C
0x180090068  lea     rcx, [rbp+lpLCData]
0x18009006c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180090071  xor     edx, edx; length
0x180090073  mov     rcx, [r14+8]; string
0x180090077  call    cs:__imp_WindowsGetStringRawBuffer
0x18009007d  mov     r15, rax
0x180090080  xor     edx, edx; length
0x180090082  mov     rcx, [r14+18h]; string
0x180090086  call    cs:__imp_WindowsGetStringRawBuffer
0x18009008c  mov     rsi, rax
0x18009008f  xor     edx, edx; length
0x180090091  mov     rcx, [rbp+string]; string
0x180090095  call    cs:__imp_WindowsGetStringRawBuffer
0x18009009b  mov     rdi, rax
0x18009009e  mov     edx, 40h ; '@'
0x1800900a3  mov     rcx, r15
0x1800900a6  call    cs:__imp_InstallLayoutOrTip
0x1800900ac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800900b0  test    rsi, rsi
0x1800900b3  jz      short loc_1800900D2
0x1800900b5  mov     rcx, rbx
0x1800900b8  inc     rcx
0x1800900bb  cmp     [rsi+rcx*2], r12w
0x1800900c0  jnz     short loc_1800900B8
0x1800900c2  test    rcx, rcx
0x1800900c5  jz      short loc_1800900D2
0x1800900c7  xor     edx, edx
0x1800900c9  mov     rcx, rsi
0x1800900cc  call    cs:__imp_InstallLayoutOrTip
0x1800900d2  test    rdi, rdi
0x1800900d5  jz      short loc_1800900F1
0x1800900d7  inc     rbx
0x1800900da  cmp     [rdi+rbx*2], r12w
0x1800900df  jnz     short loc_1800900D7
0x1800900e1  test    rbx, rbx
0x1800900e4  jz      short loc_1800900F1
0x1800900e6  xor     edx, edx
0x1800900e8  mov     rcx, rdi
0x1800900eb  call    cs:__imp_InstallLayoutOrTip
0x1800900f1  xor     edx, edx
0x1800900f3  mov     rcx, r15
0x1800900f6  call    cs:__imp_SetDefaultLayoutOrTip
0x1800900fc  mov     rdx, r14
0x1800900ff  lea     rcx, [rbp+arg_8]
0x180090103  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x180090108  nop
0x180090109  mov     rcx, [rbp+arg_8]
0x18009010d  test    rcx, rcx
0x180090110  jnz     short loc_18009015B
0x180090112  mov     [rbp+arg_8], r12
0x180090116  lea     r8, [rbp+arg_8]; void **
0x18009011a  lea     rdx, _GUID_7f21035b_4610_43a3_9f5c_285e70d9f52d; struct _GUID *
0x180090121  lea     rcx, _GUID_b742e827_ede6_400f_8312_cd522198be86; struct _GUID *
0x180090128  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18009012d  mov     ebx, eax
0x18009012f  test    eax, eax
0x180090131  jns     short loc_180090157
0x180090133  mov     edx, 1C9h; void *
0x180090138  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009013f  mov     r9d, eax; char *
0x180090142  mov     rcx, [rbp+38h]; this
0x180090146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009014b  nop
0x18009014c  lea     rcx, [rbp+arg_8]
0x180090150  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180090155  jmp     short loc_18009018C
0x180090157  mov     rcx, [rbp+arg_8]
0x18009015b  mov     rax, [rcx]
0x18009015e  mov     r9, [rbp+string]
0x180090162  mov     r8, [r14+18h]
0x180090166  mov     rdx, [r14+8]
0x18009016a  mov     rax, [rax+30h]
0x18009016e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090173  mov     ebx, eax
0x180090175  test    eax, eax
0x180090177  jns     short loc_180090180
0x180090179  mov     edx, 1CBh
0x18009017e  jmp     short loc_180090138
0x180090180  lea     rcx, [rbp+arg_8]
0x180090184  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180090189  mov     ebx, r12d
0x18009018c  mov     rcx, [rbp+string]; string
0x180090190  call    cs:__imp_WindowsDeleteString
0x180090196  mov     eax, ebx
0x180090198  add     rsp, 30h
0x18009019c  pop     r15
0x18009019e  pop     r14
0x1800901a0  pop     r12
0x1800901a2  pop     rdi
0x1800901a3  pop     rsi
0x1800901a4  pop     rbx
0x1800901a5  pop     rbp
0x1800901a6  retn
```
