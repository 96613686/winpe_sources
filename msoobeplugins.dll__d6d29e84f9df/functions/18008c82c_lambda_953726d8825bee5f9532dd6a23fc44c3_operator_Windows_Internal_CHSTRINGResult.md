# _lambda_953726d8825bee5f9532dd6a23fc44c3_::operator()(Windows::Internal::CHSTRINGResult &)

- ea: `0x18008c82c`
- end: `0x18008cb93`
- name: `??R_lambda_953726d8825bee5f9532dd6a23fc44c3_@@QEBAJAEAVCHSTRINGResult@Internal@Windows@@@Z`
- size: `871`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008e370`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x18001adf0`
- `0x18001e9a4`
- `0x180023574`
- `0x180040898`
- `0x1800415f0`
- `0x180041930`
- `0x180042068`
- `0x18005a8e8`
- `0x18008b17c`
- `0x18008b208`
- `0x18008b294`
- `0x18008c82c`
- `0x18008e3e4`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18008c9d1`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18008c9d1`

## string_xrefs

- `0x18008c87a`: `shell\oobe\machine\plugins\adapters\winrt\oobeeula.cpp`
- `0x18008c8af`: `shell\oobe\machine\plugins\adapters\winrt\oobeeula.cpp`
- `0x18008c942`: `shell\oobe\machine\plugins\adapters\winrt\oobeeula.cpp`
- `0x18008c9e4`: `shell\oobe\machine\plugins\adapters\winrt\oobeeula.cpp`
- `0x18008ca57`: `shell\oobe\machine\plugins\adapters\winrt\oobeeula.cpp`
- `0x18008cb09`: `shell\oobe\machine\plugins\adapters\winrt\oobeeula.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_953726d8825bee5f9532dd6a23fc44c3_::operator()(__int64 a1, __int64 a2)
{
  int EulaPlugin; // eax
  unsigned int v5; // ebx
  int v6; // ecx
  struct IOOBEEulaPlugin *v7; // rdi
  __int64 (__fastcall *v8)(struct IOOBEEulaPlugin *, char **); // rbx
  int v9; // eax
  HSTRING *v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  HSTRING *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // rdi
  PWSTR v18; // rbx
  HRESULT v19; // eax
  HRESULT v20; // edi
  __int64 v21; // rdx
  __int64 v22; // rcx
  struct IOOBEEulaPlugin *v23; // rdi
  __int64 (__fastcall *v24)(struct IOOBEEulaPlugin *, HSTRING *); // rbx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(UINT); // r9
  int v30; // eax
  char v31; // r8
  PWSTR pszPath; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v34; // [rsp+28h] [rbp-58h] BYREF
  char *v35; // [rsp+30h] [rbp-50h] BYREF
  HSTRING Reserved1; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v37; // [rsp+40h] [rbp-40h] BYREF
  struct IOOBEEulaPlugin *v38; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING v40; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v38 = 0;
  EulaPlugin = GetEulaPlugin(*(_DWORD *)(a1 + 16) == 1, &v38);
  v5 = EulaPlugin;
  if ( EulaPlugin >= 0 )
  {
    pszPath = 0;
    v6 = *(_DWORD *)(a1 + 16);
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        v5 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeeula.cpp",
          (const char *)0x8000FFFFLL,
          (int)pszPath);
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
        goto LABEL_34;
      }
      CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[121],unsigned short const (&)[13]>();
      v35 = 0;
      v7 = v38;
      v8 = *(__int64 (__fastcall **)(struct IOOBEEulaPlugin *, char **))(*(_QWORD *)v38 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v35,
        0);
      v9 = v8(v7, &v35);
      v5 = v9;
      if ( v9 == -2147023728 )
      {
        v40 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, (PCWSTR)&Class, 1u, 0);
        v34 = v40;
        Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a2 + 16), &v34);
        v10 = (HSTRING *)&v35;
LABEL_33:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v10);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
        v5 = 0;
        goto LABEL_34;
      }
      if ( v9 < 0 )
      {
        v11 = (unsigned int)v9;
        v12 = 114;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeeula.cpp",
          (const char *)v11,
          (int)pszPath);
        v13 = (HSTRING *)&v35;
        goto LABEL_23;
      }
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v35[2 * v15] );
      v16 = *(const char **)(*(_QWORD *)(a1 + 8) + 104LL);
      do
        ++v14;
      while ( *(_WORD *)&v16[2 * v14] );
      v17 = v15 + v14;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v34,
        v35,
        v15 + v14 + 2,
        v16);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &pszPath,
        &v34);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
      v18 = pszPath;
      if ( !pszPath )
      {
        v5 = -2147024882;
        v11 = 2147942414LL;
        v12 = 121;
        goto LABEL_10;
      }
      v19 = PathCchRenameExtension(pszPath, v17 + 2, *(PCWSTR *)(*(_QWORD *)(a1 + 8) + 104LL));
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeeula.cpp",
          (const char *)(unsigned int)v19,
          (int)pszPath);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
        v5 = v20;
        goto LABEL_34;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
LABEL_28:
      Reserved1 = (HSTRING)v18;
      CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[121],unsigned short const (&)[5],unsigned short *>(
        v22,
        v21,
        &Reserved1);
      v27 = *(_DWORD *)(a1 + 16) != 0 ? 65001 : 1252;
      v37 = 0;
      v28 = *(_QWORD *)(a1 + 8);
      v29 = GetHtmlFileWideCharContent;
      if ( *(_QWORD *)(v28 + 112) )
        v29 = *(__int64 (__fastcall **)(UINT))(v28 + 112);
      v30 = ((__int64 (__fastcall *)(__int64, PWSTR, HSTRING *))v29)(v27, v18, &v37);
      v5 = v30;
      if ( v30 >= 0 )
      {
        Reserved1 = v37;
        Reserved1 = (HSTRING)Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                               &hstringHeader,
                               (const WCHAR **)&Reserved1,
                               v31)[1].Reserved.Reserved1;
        Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a2 + 16), &Reserved1);
        v10 = &v37;
        goto LABEL_33;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeeula.cpp",
        (const char *)(unsigned int)v30,
        (int)pszPath);
      v13 = &v37;
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v13);
      goto LABEL_24;
    }
    CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[121],unsigned short const (&)[19]>();
    v34 = 0;
    v23 = v38;
    v24 = *(__int64 (__fastcall **)(struct IOOBEEulaPlugin *, HSTRING *))(*(_QWORD *)v38 + 24LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    v25 = v24(v23, &v34);
    v5 = v25;
    if ( v25 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszPath,
        0);
      v25 = RtfToHtmlConverter::ConvertRtfFileToTempHtml((const unsigned __int16 *)v34, &pszPath);
      v5 = v25;
      if ( v25 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
        v18 = pszPath;
        goto LABEL_28;
      }
      v26 = 94;
    }
    else
    {
      v26 = 93;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeeula.cpp",
      (const char *)(unsigned int)v25,
      (int)pszPath);
    v13 = &v34;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x53,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobeeula.cpp",
    (const char *)(unsigned int)EulaPlugin,
    (int)pszPath);
LABEL_34:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v38);
  return v5;
}

```

## disassembly

```asm
0x18008c82c  mov     [rsp-28h+arg_10], rbx
0x18008c831  push    rbp
0x18008c832  push    rsi
0x18008c833  push    rdi
0x18008c834  push    r14
0x18008c836  push    r15
0x18008c838  mov     rbp, rsp
0x18008c83b  sub     rsp, 80h
0x18008c842  mov     rax, cs:__security_cookie
0x18008c849  xor     rax, rsp
0x18008c84c  mov     [rbp+var_10], rax
0x18008c850  mov     r14, rdx
0x18008c853  mov     rsi, rcx
0x18008c856  xor     r15d, r15d
0x18008c859  mov     [rbp+var_38], r15
0x18008c85d  cmp     dword ptr [rcx+10h], 1
0x18008c861  setz    cl; bool
0x18008c864  lea     rdx, [rbp+var_38]; struct IOOBEEulaPlugin **
0x18008c868  call    ?GetEulaPlugin@@YAJ_NPEAPEAUIOOBEEulaPlugin@@@Z; GetEulaPlugin(bool,IOOBEEulaPlugin * *)
0x18008c86d  mov     ebx, eax
0x18008c86f  test    eax, eax
0x18008c871  jns     short loc_18008C88F
0x18008c873  mov     rcx, [rbp+28h]; this
0x18008c877  mov     r9d, eax; char *
0x18008c87a  lea     r8, aShellOobeMachi_19; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008c881  lea     edx, [r15+53h]; void *
0x18008c885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c88a  jmp     loc_18008CB65
0x18008c88f  mov     [rbp+pszPath], r15
0x18008c893  mov     ecx, [rsi+10h]
0x18008c896  test    ecx, ecx
0x18008c898  jz      loc_18008CA1E
0x18008c89e  cmp     ecx, 1
0x18008c8a1  jz      short loc_18008C8C5
0x18008c8a3  mov     rcx, [rbp+28h]; this
0x18008c8a7  mov     ebx, 8000FFFFh
0x18008c8ac  mov     r9d, ebx; char *
0x18008c8af  lea     r8, aShellOobeMachi_19; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008c8b6  mov     edx, 7Fh; void *
0x18008c8bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c8c0  jmp     loc_18008CA75
0x18008c8c5  call    ??$CoreEvent1@AEAY0HJ@$$CBDAEAY0N@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0HJ@$$CBDAEAY0N@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[121],ushort const (&)[13]>(char const (&)[121],ushort const (&)[13])
0x18008c8ca  mov     [rbp+var_50], r15
0x18008c8ce  mov     rdi, [rbp+var_38]
0x18008c8d2  mov     rax, [rdi]
0x18008c8d5  mov     rbx, [rax+20h]
0x18008c8d9  xor     edx, edx
0x18008c8db  lea     rcx, [rbp+var_50]
0x18008c8df  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008c8e4  lea     rdx, [rbp+var_50]
0x18008c8e8  mov     rcx, rdi
0x18008c8eb  mov     rax, rbx
0x18008c8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8f3  mov     ebx, eax
0x18008c8f5  cmp     eax, 80070490h
0x18008c8fa  jnz     short loc_18008C936
0x18008c8fc  mov     [rbp+var_18], r15
0x18008c900  xor     r9d, r9d; unsigned int
0x18008c903  lea     r8d, [r9+1]; unsigned int
0x18008c907  lea     rdx, Class; sourceString
0x18008c90e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18008c912  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008c917  mov     rax, [rbp+var_18]
0x18008c91b  mov     [rbp+var_58], rax
0x18008c91f  lea     rcx, [r14+10h]; newString
0x18008c923  lea     rdx, [rbp+var_58]; HSTRING *
0x18008c927  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18008c92c  nop
0x18008c92d  lea     rcx, [rbp+var_50]
0x18008c931  jmp     loc_18008CB53
0x18008c936  test    eax, eax
0x18008c938  jns     short loc_18008C95C
0x18008c93a  mov     r9d, eax; char *
0x18008c93d  mov     edx, 72h ; 'r'; void *
0x18008c942  lea     r8, aShellOobeMachi_19; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008c949  mov     rcx, [rbp+28h]; this
0x18008c94d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c952  nop
0x18008c953  lea     rcx, [rbp+var_50]
0x18008c957  jmp     loc_18008CA6F
0x18008c95c  mov     rdx, [rbp+var_50]
0x18008c960  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008c964  mov     r8, rcx
0x18008c967  inc     r8
0x18008c96a  cmp     [rdx+r8*2], r15w
0x18008c96f  jnz     short loc_18008C967
0x18008c971  mov     rax, [rsi+8]
0x18008c975  mov     r9, [rax+68h]
0x18008c979  inc     rcx
0x18008c97c  cmp     [r9+rcx*2], r15w
0x18008c981  jnz     short loc_18008C979
0x18008c983  lea     rdi, [r8+rcx]
0x18008c987  lea     r8, [rdi+2]
0x18008c98b  lea     rcx, [rbp+var_58]
0x18008c98f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18008c994  lea     rdx, [rbp+var_58]
0x18008c998  lea     rcx, [rbp+pszPath]
0x18008c99c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18008c9a1  lea     rcx, [rbp+var_58]
0x18008c9a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008c9aa  mov     rbx, [rbp+pszPath]
0x18008c9ae  test    rbx, rbx
0x18008c9b1  jnz     short loc_18008C9C2
0x18008c9b3  mov     ebx, 8007000Eh
0x18008c9b8  mov     r9d, ebx
0x18008c9bb  mov     edx, 79h ; 'y'
0x18008c9c0  jmp     short loc_18008C942
0x18008c9c2  mov     r8, [rsi+8]
0x18008c9c6  mov     r8, [r8+68h]; pszExt
0x18008c9ca  lea     rdx, [rdi+2]; cchPath
0x18008c9ce  mov     rcx, rbx; pszPath
0x18008c9d1  call    cs:__imp_PathCchRenameExtension
0x18008c9d7  mov     edi, eax
0x18008c9d9  test    eax, eax
0x18008c9db  jns     short loc_18008CA10
0x18008c9dd  mov     rcx, [rbp+28h]; this
0x18008c9e1  mov     r9d, eax; char *
0x18008c9e4  lea     r8, aShellOobeMachi_19; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008c9eb  mov     edx, 7Ah ; 'z'; void *
0x18008c9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c9f5  nop
0x18008c9f6  lea     rcx, [rbp+var_50]
0x18008c9fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008c9ff  nop
0x18008ca00  lea     rcx, [rbp+pszPath]
0x18008ca04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008ca09  mov     ebx, edi
0x18008ca0b  jmp     loc_18008CB65
0x18008ca10  lea     rcx, [rbp+var_50]
0x18008ca14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008ca19  jmp     loc_18008CAB5
0x18008ca1e  call    ??$CoreEvent1@AEAY0HJ@$$CBDAEAY0BD@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0HJ@$$CBDAEAY0BD@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[121],ushort const (&)[19]>(char const (&)[121],ushort const (&)[19])
0x18008ca23  mov     [rbp+var_58], r15
0x18008ca27  mov     rdi, [rbp+var_38]
0x18008ca2b  mov     rax, [rdi]
0x18008ca2e  mov     rbx, [rax+18h]
0x18008ca32  xor     edx, edx
0x18008ca34  lea     rcx, [rbp+var_58]
0x18008ca38  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008ca3d  lea     rdx, [rbp+var_58]
0x18008ca41  mov     rcx, rdi
0x18008ca44  mov     rax, rbx
0x18008ca47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ca4c  mov     ebx, eax
0x18008ca4e  test    eax, eax
0x18008ca50  jns     short loc_18008CA83
0x18008ca52  mov     edx, 5Dh ; ']'; void *
0x18008ca57  lea     r8, aShellOobeMachi_19; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008ca5e  mov     r9d, eax; char *
0x18008ca61  mov     rcx, [rbp+28h]; this
0x18008ca65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ca6a  nop
0x18008ca6b  lea     rcx, [rbp+var_58]
0x18008ca6f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008ca74  nop
0x18008ca75  lea     rcx, [rbp+pszPath]
0x18008ca79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008ca7e  jmp     loc_18008CB65
0x18008ca83  xor     edx, edx
0x18008ca85  lea     rcx, [rbp+pszPath]
0x18008ca89  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008ca8e  lea     rdx, [rbp+pszPath]; unsigned __int16 **
0x18008ca92  mov     rcx, [rbp+var_58]; unsigned __int16 *
0x18008ca96  call    ?ConvertRtfFileToTempHtml@RtfToHtmlConverter@@SAJPEBGPEAPEAG@Z; RtfToHtmlConverter::ConvertRtfFileToTempHtml(ushort const *,ushort * *)
0x18008ca9b  mov     ebx, eax
0x18008ca9d  test    eax, eax
0x18008ca9f  jns     short loc_18008CAA8
0x18008caa1  mov     edx, 5Eh ; '^'
0x18008caa6  jmp     short loc_18008CA57
0x18008caa8  lea     rcx, [rbp+var_58]
0x18008caac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008cab1  mov     rbx, [rbp+pszPath]
0x18008cab5  mov     [rbp+var_48], rbx
0x18008cab9  lea     r8, [rbp+var_48]
0x18008cabd  call    ??$CoreEvent2@AEAY0HJ@$$CBDAEAY04$$CBGPEAG@CloudExperienceHostCoreTelemetry@@SAXAEAY0HJ@$$CBDAEAY04$$CBG$$QEAPEAG@Z; CloudExperienceHostCoreTelemetry::CoreEvent2<char const (&)[121],ushort const (&)[5],ushort *>(char const (&)[121],ushort const (&)[5],ushort * &&)
0x18008cac2  mov     eax, [rsi+10h]
0x18008cac5  neg     eax
0x18008cac7  sbb     ecx, ecx
0x18008cac9  and     ecx, 0F905h
0x18008cacf  add     ecx, 4E4h
0x18008cad5  mov     [rbp+var_40], r15
0x18008cad9  mov     rax, [rsi+8]
0x18008cadd  lea     r9, ?GetHtmlFileWideCharContent@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetHtmlFileWideCharContent(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18008cae4  cmp     [rax+70h], r15
0x18008cae8  cmovnz  r9, [rax+70h]
0x18008caed  lea     r8, [rbp+var_40]
0x18008caf1  mov     rdx, rbx
0x18008caf4  mov     rax, r9
0x18008caf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cafc  mov     ebx, eax
0x18008cafe  test    eax, eax
0x18008cb00  jns     short loc_18008CB24
0x18008cb02  mov     rcx, [rbp+28h]; this
0x18008cb06  mov     r9d, eax; char *
0x18008cb09  lea     r8, aShellOobeMachi_19; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008cb10  mov     edx, 8Ah; void *
0x18008cb15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cb1a  nop
0x18008cb1b  lea     rcx, [rbp+var_40]
0x18008cb1f  jmp     loc_18008CA6F
0x18008cb24  mov     rax, [rbp+var_40]
0x18008cb28  mov     [rbp+var_48], rax
0x18008cb2c  lea     rdx, [rbp+var_48]
0x18008cb30  lea     rcx, [rbp+hstringHeader]
0x18008cb34  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008cb39  mov     rcx, [rax+18h]
0x18008cb3d  mov     [rbp+var_48], rcx
0x18008cb41  lea     rcx, [r14+10h]; newString
0x18008cb45  lea     rdx, [rbp+var_48]; HSTRING *
0x18008cb49  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18008cb4e  nop
0x18008cb4f  lea     rcx, [rbp+var_40]
0x18008cb53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008cb58  nop
0x18008cb59  lea     rcx, [rbp+pszPath]
0x18008cb5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008cb62  mov     ebx, r15d
0x18008cb65  lea     rcx, [rbp+var_38]
0x18008cb69  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18008cb6e  mov     eax, ebx
0x18008cb70  mov     rcx, [rbp+var_10]
0x18008cb74  xor     rcx, rsp; StackCookie
0x18008cb77  call    __security_check_cookie
0x18008cb7c  mov     rbx, [rsp+80h+arg_10]
0x18008cb84  add     rsp, 80h
0x18008cb8b  pop     r15
0x18008cb8d  pop     r14
0x18008cb8f  pop     rdi
0x18008cb90  pop     rsi
0x18008cb91  pop     rbp
0x18008cb92  retn
```
