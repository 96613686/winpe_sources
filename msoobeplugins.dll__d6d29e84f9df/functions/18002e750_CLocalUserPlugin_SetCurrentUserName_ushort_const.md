# CLocalUserPlugin::SetCurrentUserName(ushort const *)

- ea: `0x18002e750`
- end: `0x18002e884`
- name: `?SetCurrentUserName@CLocalUserPlugin@@UEAAJPEBG@Z`
- size: `308`
- prototype: `__int64 __fastcall(CLocalUserPlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008544`
- `0x18000b358`
- `0x18001e9a4`
- `0x1800230b0`
- `0x180023574`
- `0x18002e750`
- `0x180031800`
- `0x1800bf2ac`

## import_xrefs

- `SHLWAPI!StrTrimW` at `0x18002e7cd`
- `SHLWAPI!StrTrimW` at `0x18002e7cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e84c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e84c`

## string_xrefs

- `0x18002e7ea`: `COMPUTERNAME`
- `0x18002e7a9`: `shell\oobe\machine\plugins\localuser\localuserplugin.cpp`
- `0x18002e801`: `shell\oobe\machine\plugins\localuser\localuserplugin.cpp`
- `0x18002e82b`: `shell\oobe\machine\plugins\localuser\localuserplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLocalUserPlugin::SetCurrentUserName(LPVOID *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  size_t v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *v9; // rsi
  int GlobalSettingString; // eax
  int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-10h]
  int v14; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPCWCH lpString1; // [rsp+60h] [rbp+30h] BYREF
  PWSTR psz; // [rsp+68h] [rbp+38h] BYREF

  psz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &psz,
    0);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = _AllocStringWorker<CTCoAllocPolicy>(v5, v4, a2, v6, v13, (void **)&psz);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = psz;
    StrTrimW(psz, pszTrimChars);
    lpString1 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpString1,
      0);
    GlobalSettingString = CBasePlugin::_GetGlobalSettingString(
                            (CBasePlugin *)(this - 3),
                            L"COMPUTERNAME",
                            (unsigned __int16 **)&lpString1);
    if ( GlobalSettingString < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localuserplugin.cpp",
        (const char *)(unsigned int)GlobalSettingString,
        v14);
    v11 = ValidateUserName(v9, (WCHAR *)lpString1);
    v8 = v11;
    if ( v11 >= 0 )
    {
      CoTaskMemFree(this[3]);
      psz = 0;
      this[3] = (LPVOID)v9;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString1);
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localuserplugin.cpp",
        (const char *)(unsigned int)v11,
        v14);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString1);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localuserplugin.cpp",
      (const char *)(unsigned int)v7,
      v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psz);
  return v8;
}

```

## disassembly

```asm
0x18002e750  mov     [rsp-18h+arg_0], rbx
0x18002e755  mov     [rsp-18h+arg_8], rsi
0x18002e75a  push    rbp
0x18002e75b  push    rdi
0x18002e75c  push    r14
0x18002e75e  mov     rbp, rsp
0x18002e761  sub     rsp, 30h
0x18002e765  mov     rbx, rdx
0x18002e768  mov     rdi, rcx
0x18002e76b  xor     r14d, r14d
0x18002e76e  mov     [rbp+psz], r14
0x18002e772  xor     edx, edx
0x18002e774  lea     rcx, [rbp+psz]
0x18002e778  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e77d  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002e781  inc     r9
0x18002e784  cmp     [rbx+r9*2], r14w
0x18002e789  jnz     short loc_18002E781
0x18002e78b  lea     rax, [rbp+psz]
0x18002e78f  mov     [rsp+30h+var_8], rax
0x18002e794  mov     r8, rbx
0x18002e797  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002e79c  mov     ebx, eax
0x18002e79e  test    eax, eax
0x18002e7a0  jns     short loc_18002E7BF
0x18002e7a2  mov     rcx, [rbp+18h]; this
0x18002e7a6  mov     r9d, eax; char *
0x18002e7a9  lea     r8, aShellOobeMachi_15; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002e7b0  mov     edx, 8Ah; void *
0x18002e7b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e7ba  jmp     loc_18002E866
0x18002e7bf  lea     rdx, pszTrimChars; " \t"
0x18002e7c6  mov     rsi, [rbp+psz]
0x18002e7ca  mov     rcx, rsi; psz
0x18002e7cd  call    cs:__imp_StrTrimW
0x18002e7d3  mov     [rbp+lpString1], r14
0x18002e7d7  xor     edx, edx
0x18002e7d9  lea     rcx, [rbp+lpString1]
0x18002e7dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e7e2  lea     rcx, [rdi-18h]; this
0x18002e7e6  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x18002e7ea  lea     rdx, aComputername_0; "COMPUTERNAME"
0x18002e7f1  call    ?_GetGlobalSettingString@CBasePlugin@@IEAAJPEBGPEAPEAG@Z; CBasePlugin::_GetGlobalSettingString(ushort const *,ushort * *)
0x18002e7f6  mov     rcx, [rbp+18h]; this
0x18002e7fa  test    eax, eax
0x18002e7fc  jns     short loc_18002E812
0x18002e7fe  mov     r9d, eax; char *
0x18002e801  lea     r8, aShellOobeMachi_15; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002e808  mov     edx, 8Dh; void *
0x18002e80d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e812  mov     rdx, [rbp+lpString1]; lpString1
0x18002e816  mov     rcx, rsi; lpString2
0x18002e819  call    ?ValidateUserName@@YAJPEBG0@Z; ValidateUserName(ushort const *,ushort const *)
0x18002e81e  mov     ebx, eax
0x18002e820  test    eax, eax
0x18002e822  jns     short loc_18002E848
0x18002e824  mov     rcx, [rbp+18h]; this
0x18002e828  mov     r9d, eax; char *
0x18002e82b  lea     r8, aShellOobeMachi_15; "shell\\oobe\\machine\\plugins\\localuse"...
0x18002e832  mov     edx, 8Eh; void *
0x18002e837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e83c  nop
0x18002e83d  lea     rcx, [rbp+lpString1]
0x18002e841  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002e846  jmp     short loc_18002E866
0x18002e848  mov     rcx, [rdi+18h]; pv
0x18002e84c  call    cs:__imp_CoTaskMemFree
0x18002e852  mov     [rbp+psz], r14
0x18002e856  mov     [rdi+18h], rsi
0x18002e85a  lea     rcx, [rbp+lpString1]
0x18002e85e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002e863  mov     ebx, r14d
0x18002e866  lea     rcx, [rbp+psz]
0x18002e86a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002e86f  mov     eax, ebx
0x18002e871  mov     rbx, [rsp+30h+arg_0]
0x18002e876  mov     rsi, [rsp+30h+arg_8]
0x18002e87b  add     rsp, 30h
0x18002e87f  pop     r14
0x18002e881  pop     rdi
0x18002e882  pop     rbp
0x18002e883  retn
```
