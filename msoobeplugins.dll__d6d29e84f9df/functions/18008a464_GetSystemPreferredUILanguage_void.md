# GetSystemPreferredUILanguage(void)

- ea: `0x18008a464`
- end: `0x18008a509`
- name: `?GetSystemPreferredUILanguage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180089e60`
- `0x18008ad70`

## callees

- `0x18001e9a4`
- `0x1800415f0`
- `0x18008a464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a491`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18008a487`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18008a4c9`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18008a487`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18008a4c9`

## pseudocode

```c
_QWORD *__fastcall GetSystemPreferredUILanguage(_QWORD *a1)
{
  const char *v2; // r9
  char *v3; // rbx
  const char *v4; // r9
  __int64 v5; // r8
  ULONG pcchLanguagesBuffer; // [rsp+48h] [rbp+10h] BYREF
  ULONG pulNumLanguages; // [rsp+50h] [rbp+18h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+58h] [rbp+20h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) || GetLastError() == 122 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pwszLanguagesBuffer,
      0,
      pcchLanguagesBuffer,
      v2);
    v3 = (char *)pwszLanguagesBuffer;
    if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&v3[2 * v5] );
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        a1,
        v3,
        v5 + 1,
        v4);
    }
    else
    {
      *a1 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pwszLanguagesBuffer);
  }
  else
  {
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18008a464  mov     rax, rsp
0x18008a467  push    rbx
0x18008a468  push    rsi
0x18008a469  push    rdi
0x18008a46a  sub     rsp, 20h
0x18008a46e  xor     esi, esi
0x18008a470  lea     r9, [rax+10h]; pcchLanguagesBuffer
0x18008a474  mov     rdi, rcx
0x18008a477  mov     [rax+18h], esi
0x18008a47a  xor     r8d, r8d; pwszLanguagesBuffer
0x18008a47d  mov     [rax+10h], esi
0x18008a480  lea     rdx, [rax+18h]; pulNumLanguages
0x18008a484  lea     ecx, [rsi+8]; dwFlags
0x18008a487  call    cs:__imp_GetSystemPreferredUILanguages
0x18008a48d  test    eax, eax
0x18008a48f  jnz     short loc_18008A4A1
0x18008a491  call    cs:__imp_GetLastError
0x18008a497  cmp     eax, 7Ah ; 'z'
0x18008a49a  jz      short loc_18008A4A1
0x18008a49c  mov     [rdi], rsi
0x18008a49f  jmp     short loc_18008A4FE
0x18008a4a1  mov     r8d, [rsp+38h+pcchLanguagesBuffer]
0x18008a4a6  lea     rcx, [rsp+38h+pwszLanguagesBuffer]
0x18008a4ab  xor     edx, edx
0x18008a4ad  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18008a4b2  mov     rbx, [rsp+38h+pwszLanguagesBuffer]
0x18008a4b7  lea     r9, [rsp+38h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18008a4bc  mov     r8, rbx; pwszLanguagesBuffer
0x18008a4bf  lea     rdx, [rsp+38h+pulNumLanguages]; pulNumLanguages
0x18008a4c4  mov     ecx, 8; dwFlags
0x18008a4c9  call    cs:__imp_GetSystemPreferredUILanguages
0x18008a4cf  test    eax, eax
0x18008a4d1  jnz     short loc_18008A4D8
0x18008a4d3  mov     [rdi], rsi
0x18008a4d6  jmp     short loc_18008A4F4
0x18008a4d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008a4dc  inc     r8
0x18008a4df  cmp     [rbx+r8*2], si
0x18008a4e4  jnz     short loc_18008A4DC
0x18008a4e6  inc     r8
0x18008a4e9  mov     rdx, rbx
0x18008a4ec  mov     rcx, rdi
0x18008a4ef  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18008a4f4  lea     rcx, [rsp+38h+pwszLanguagesBuffer]
0x18008a4f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a4fe  mov     rax, rdi
0x18008a501  add     rsp, 20h
0x18008a505  pop     rdi
0x18008a506  pop     rsi
0x18008a507  pop     rbx
0x18008a508  retn
```
