# _CleanupAllDeferredUserCacheInfo(void)

- ea: `0x18004b9ec`
- end: `0x18004bb25`
- name: `?_CleanupAllDeferredUserCacheInfo@@YAJXZ`
- size: `313`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b1e0`

## callees

- `0x18003b944`
- `0x18003b964`
- `0x18003bf28`
- `0x18003c73c`
- `0x18004755c`
- `0x18004b9ec`
- `0x18004bfe4`
- `0x18004c600`
- `0x18005c97c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ba8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ba8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba60`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004babb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004babb`

## string_xrefs

- `0x18004ba29`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004bae2`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004baad`: `Software\Microsoft\IdentityStore\DeferredCacheCleanup`

## pseudocode

```c
__int64 _CleanupAllDeferredUserCacheInfo(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  int MultiStringRegValAsVector; // eax
  unsigned int v3; // ebx
  PSID v4; // rdi
  LPCWSTR v5; // rbx
  const WCHAR *v6; // rcx
  LSTATUS v7; // eax
  LPCWSTR StringSid; // [rsp+20h] [rbp-20h] BYREF
  const WCHAR *v10; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int v12; // [rsp+50h] [rbp+10h] BYREF
  PSID Sid; // [rsp+58h] [rbp+18h] BYREF

  std::vector<std::wstring>::vector<std::wstring>(&StringSid);
  v12 = 0;
  MultiStringRegValAsVector = GetMultiStringRegValAsVector(v1, v0, &v12, &StringSid);
  v3 = MultiStringRegValAsVector;
  if ( MultiStringRegValAsVector >= 0 )
  {
    v4 = 0;
    Sid = 0;
    v5 = StringSid;
    if ( StringSid != v10 )
    {
      while ( 1 )
      {
        if ( v4 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
          LocalFree(v4);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
        }
        Sid = 0;
        if ( *((_QWORD *)v5 + 3) <= 7u )
          v6 = v5;
        else
          v6 = *(const WCHAR **)v5;
        if ( ConvertStringSidToSidW(v6, &Sid) )
          CleanupUserCacheFromPackages(Sid);
        v5 += 16;
        if ( v5 == v10 )
          break;
        v4 = Sid;
      }
    }
    v7 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityStore\\DeferredCacheCleanup");
    v3 = v7;
    if ( (v7 & 0xFFFFFFFD) != 0 )
    {
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( (v3 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x250,
          (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
          (const char *)v3,
          (int)StringSid);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      v3 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
      (const char *)(unsigned int)MultiStringRegValAsVector,
      (int)StringSid);
  }
  std::vector<std::wstring>::_Tidy(&StringSid);
  return v3;
}

```

## disassembly

```asm
0x18004b9ec  mov     [rsp-8+arg_10], rbx
0x18004b9f1  mov     [rsp-8+arg_18], rdi
0x18004b9f6  push    rbp
0x18004b9f7  mov     rbp, rsp
0x18004b9fa  sub     rsp, 40h
0x18004b9fe  lea     rcx, [rbp+StringSid]
0x18004ba02  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18004ba07  nop
0x18004ba08  mov     [rbp+arg_0], 0
0x18004ba0f  lea     r9, [rbp+StringSid]
0x18004ba13  lea     r8, [rbp+arg_0]
0x18004ba17  call    ?GetMultiStringRegValAsVector@@YAJPEBG0PEAKPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetMultiStringRegValAsVector(ushort const *,ushort const *,ulong *,std::vector<std::wstring> *)
0x18004ba1c  mov     ebx, eax
0x18004ba1e  test    eax, eax
0x18004ba20  jns     short loc_18004BA3F
0x18004ba22  mov     rcx, [rbp+8]; this
0x18004ba26  mov     r9d, eax; char *
0x18004ba29  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004ba30  mov     edx, 244h; void *
0x18004ba35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ba3a  jmp     loc_18004BB0A
0x18004ba3f  xor     edi, edi
0x18004ba41  mov     [rbp+Sid], rdi
0x18004ba45  mov     rbx, [rbp+StringSid]
0x18004ba49  cmp     rbx, [rbp+var_18]
0x18004ba4d  jz      short loc_18004BAAD
0x18004ba4f  test    rdi, rdi
0x18004ba52  jz      short loc_18004BA6F
0x18004ba54  lea     rcx, [rbp+arg_0]; this
0x18004ba58  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004ba5d  mov     rcx, rdi; hMem
0x18004ba60  call    cs:__imp_LocalFree
0x18004ba66  lea     rcx, [rbp+arg_0]; this
0x18004ba6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004ba6f  mov     [rbp+Sid], 0
0x18004ba77  cmp     qword ptr [rbx+18h], 7
0x18004ba7c  jbe     short loc_18004BA83
0x18004ba7e  mov     rcx, [rbx]
0x18004ba81  jmp     short loc_18004BA86
0x18004ba83  mov     rcx, rbx; StringSid
0x18004ba86  lea     rdx, [rbp+Sid]; Sid
0x18004ba8a  call    cs:__imp_ConvertStringSidToSidW
0x18004ba90  test    eax, eax
0x18004ba92  jz      short loc_18004BA9D
0x18004ba94  mov     rcx, [rbp+Sid]; void *
0x18004ba98  call    ?CleanupUserCacheFromPackages@@YAXPEAX@Z; CleanupUserCacheFromPackages(void *)
0x18004ba9d  add     rbx, 20h ; ' '
0x18004baa1  cmp     rbx, [rbp+var_18]
0x18004baa5  jz      short loc_18004BAAD
0x18004baa7  mov     rdi, [rbp+Sid]
0x18004baab  jmp     short loc_18004BA4F
0x18004baad  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityStore\\Def"...
0x18004bab4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004babb  call    cs:__imp_RegDeleteKeyW
0x18004bac1  mov     ebx, eax
0x18004bac3  test    eax, 0FFFFFFFDh
0x18004bac8  jz      short loc_18004BAFF
0x18004baca  test    eax, eax
0x18004bacc  jle     short loc_18004BAD7
0x18004bace  movzx   ebx, ax
0x18004bad1  or      ebx, 80070000h
0x18004bad7  test    ebx, ebx
0x18004bad9  jns     short loc_18004BAF4
0x18004badb  mov     rcx, [rbp+8]; this
0x18004badf  mov     r9d, ebx; char *
0x18004bae2  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bae9  mov     edx, 250h; void *
0x18004baee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004baf3  nop
0x18004baf4  lea     rcx, [rbp+Sid]
0x18004baf8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004bafd  jmp     short loc_18004BB0A
0x18004baff  lea     rcx, [rbp+Sid]
0x18004bb03  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004bb08  xor     ebx, ebx
0x18004bb0a  lea     rcx, [rbp+StringSid]
0x18004bb0e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004bb13  mov     eax, ebx
0x18004bb15  mov     rbx, [rsp+40h+arg_10]
0x18004bb1a  mov     rdi, [rsp+40h+arg_18]
0x18004bb1f  add     rsp, 40h
0x18004bb23  pop     rbp
0x18004bb24  retn
```
