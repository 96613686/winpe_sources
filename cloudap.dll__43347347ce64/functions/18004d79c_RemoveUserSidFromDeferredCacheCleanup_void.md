# RemoveUserSidFromDeferredCacheCleanup(void *)

- ea: `0x18004d79c`
- end: `0x18004d964`
- name: `?RemoveUserSidFromDeferredCacheCleanup@@YAJPEAX@Z`
- size: `456`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f210`

## callees

- `0x18003a5cc`
- `0x18003bf28`
- `0x18003c73c`
- `0x180042410`
- `0x180046efc`
- `0x180047204`
- `0x180047350`
- `0x1800473c0`
- `0x18004755c`
- `0x18004765c`
- `0x18004af14`
- `0x18004bfe4`
- `0x18004c034`
- `0x18004d79c`
- `0x18005c97c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d7ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d7ca`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004d8f0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004d8f0`

## string_xrefs

- `0x18004d7d8`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d818`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d901`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x18004d8e2`: `Software\Microsoft\IdentityStore\DeferredCacheCleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoveUserSidFromDeferredCacheCleanup(void *a1)
{
  const char *v1; // r9
  unsigned int LastError; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  int MultiStringRegValAsVector; // eax
  __int64 v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rsi
  _QWORD *v10; // rbx
  _QWORD *v11; // r8
  _QWORD *v12; // rcx
  unsigned int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-50h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v17; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp-38h]
  _QWORD v19[4]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    v15 = 0;
    std::vector<std::wstring>::vector<std::wstring>(&v17);
    MultiStringRegValAsVector = GetMultiStringRegValAsVector(v4, v3, &v15, &v17);
    LastError = MultiStringRegValAsVector;
    if ( MultiStringRegValAsVector < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B4,
        (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp",
        (const char *)(unsigned int)MultiStringRegValAsVector,
        v15);
LABEL_5:
      std::vector<std::wstring>::_Tidy(&v17);
      goto LABEL_24;
    }
    v6 = -1;
    do
      ++v6;
    while ( StringSid[v6] );
    std::wstring::wstring(v19, StringSid, &StringSid[v6]);
    v7 = v18;
    v8 = std::_Find_unchecked<std::wstring *,std::wstring>(v17, v18, v19);
    v9 = v8;
    if ( (_QWORD *)v8 != v7 )
    {
      v10 = (_QWORD *)(v8 + 32);
      if ( (_QWORD *)(v8 + 32) == v7 )
      {
LABEL_19:
        std::_Destroy_range<std::allocator<std::wstring>>(v9, v7);
        v7 = (_QWORD *)v9;
        v18 = (_QWORD *)v9;
LABEL_20:
        if ( v17 != v7
          || (v13 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityStore\\DeferredCacheCleanup")) == 0 )
        {
          std::wstring::_Tidy_deallocate(v19);
          std::vector<std::wstring>::_Tidy(&v17);
          LastError = 0;
          goto LABEL_24;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x6BA,
                      (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp",
                      (const char *)v13,
                      v15);
        std::wstring::_Tidy_deallocate(v19);
        goto LABEL_5;
      }
      do
      {
        v11 = v19;
        if ( v19[3] > 7u )
          v11 = (_QWORD *)v19[0];
        if ( v10[3] <= 7u )
          v12 = v10;
        else
          v12 = (_QWORD *)*v10;
        if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v12, v10[2], v11, v19[2], v15) )
        {
          std::wstring::operator=(v9, v10);
          v9 += 32;
        }
        v10 += 4;
      }
      while ( v10 != v7 );
    }
    if ( (_QWORD *)v9 == v7 )
      goto LABEL_20;
    goto LABEL_19;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x6AD,
                (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp",
                v1);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return LastError;
}

```

## disassembly

```asm
0x18004d79c  mov     [rsp-18h+arg_8], rbx
0x18004d7a1  mov     [rsp-18h+arg_10], rsi
0x18004d7a6  push    rbp
0x18004d7a7  push    rdi
0x18004d7a8  push    r14
0x18004d7aa  mov     rbp, rsp
0x18004d7ad  sub     rsp, 70h
0x18004d7b1  mov     rax, cs:__security_cookie
0x18004d7b8  xor     rax, rsp
0x18004d7bb  mov     [rbp+var_8], rax
0x18004d7bf  xor     r14d, r14d
0x18004d7c2  mov     [rbp+StringSid], r14
0x18004d7c6  lea     rdx, [rbp+StringSid]; StringSid
0x18004d7ca  call    cs:__imp_ConvertSidToStringSidW
0x18004d7d0  test    eax, eax
0x18004d7d2  jnz     short loc_18004D7F0
0x18004d7d4  mov     rcx, [rbp+18h]; this
0x18004d7d8  lea     r8, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d7df  mov     edx, 6ADh; void *
0x18004d7e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004d7e9  mov     ebx, eax
0x18004d7eb  jmp     loc_18004D938
0x18004d7f0  mov     [rbp+var_50], r14d
0x18004d7f4  lea     rcx, [rbp+var_40]
0x18004d7f8  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18004d7fd  nop
0x18004d7fe  lea     r9, [rbp+var_40]
0x18004d802  lea     r8, [rbp+var_50]
0x18004d806  call    ?GetMultiStringRegValAsVector@@YAJPEBG0PEAKPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetMultiStringRegValAsVector(ushort const *,ushort const *,ulong *,std::vector<std::wstring> *)
0x18004d80b  mov     ebx, eax
0x18004d80d  test    eax, eax
0x18004d80f  jns     short loc_18004D838
0x18004d811  mov     rcx, [rbp+18h]; this
0x18004d815  mov     r9d, eax; char *
0x18004d818  lea     r8, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d81f  mov     edx, 6B4h; void *
0x18004d824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d829  nop
0x18004d82a  lea     rcx, [rbp+var_40]
0x18004d82e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004d833  jmp     loc_18004D938
0x18004d838  mov     rdx, [rbp+StringSid]
0x18004d83c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d840  inc     rax
0x18004d843  cmp     [rdx+rax*2], r14w
0x18004d848  jnz     short loc_18004D840
0x18004d84a  lea     r8, [rdx+rax*2]
0x18004d84e  lea     rcx, [rbp+var_28]
0x18004d852  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18004d857  mov     rdi, [rbp+var_38]
0x18004d85b  lea     r8, [rbp+var_28]
0x18004d85f  mov     rdx, rdi
0x18004d862  mov     rcx, [rbp+var_40]
0x18004d866  call    ??$_Find_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@QEAV10@AEBV10@@Z; std::_Find_unchecked<std::wstring *,std::wstring>(std::wstring *,std::wstring * const,std::wstring const &)
0x18004d86b  mov     rbx, rax
0x18004d86e  mov     rsi, rax
0x18004d871  cmp     rax, rdi
0x18004d874  jz      short loc_18004D8C5
0x18004d876  add     rbx, 20h ; ' '
0x18004d87a  cmp     rbx, rdi
0x18004d87d  jz      short loc_18004D8CA
0x18004d87f  lea     r8, [rbp+var_28]
0x18004d883  cmp     [rbp+var_10], 7
0x18004d888  cmova   r8, [rbp+var_28]
0x18004d88d  cmp     qword ptr [rbx+18h], 7
0x18004d892  jbe     short loc_18004D899
0x18004d894  mov     rcx, [rbx]
0x18004d897  jmp     short loc_18004D89C
0x18004d899  mov     rcx, rbx
0x18004d89c  mov     r9, [rbp+var_18]
0x18004d8a0  mov     rdx, [rbx+10h]
0x18004d8a4  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d8a9  test    al, al
0x18004d8ab  jnz     short loc_18004D8BC
0x18004d8ad  mov     rdx, rbx
0x18004d8b0  mov     rcx, rsi
0x18004d8b3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004d8b8  add     rsi, 20h ; ' '
0x18004d8bc  add     rbx, 20h ; ' '
0x18004d8c0  cmp     rbx, rdi
0x18004d8c3  jnz     short loc_18004D87F
0x18004d8c5  cmp     rsi, rdi
0x18004d8c8  jz      short loc_18004D8DC
0x18004d8ca  mov     rdx, rdi
0x18004d8cd  mov     rcx, rsi
0x18004d8d0  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18004d8d5  mov     rdi, rsi
0x18004d8d8  mov     [rbp+var_38], rsi
0x18004d8dc  cmp     [rbp+var_40], rdi
0x18004d8e0  jnz     short loc_18004D922
0x18004d8e2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityStore\\Def"...
0x18004d8e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d8f0  call    cs:__imp_RegDeleteKeyW
0x18004d8f6  test    eax, eax
0x18004d8f8  jz      short loc_18004D922
0x18004d8fa  mov     rcx, [rbp+18h]; this
0x18004d8fe  mov     r9d, eax; char *
0x18004d901  lea     r8, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x18004d908  mov     edx, 6BAh; void *
0x18004d90d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004d912  mov     ebx, eax
0x18004d914  lea     rcx, [rbp+var_28]
0x18004d918  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d91d  jmp     loc_18004D82A
0x18004d922  lea     rcx, [rbp+var_28]
0x18004d926  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d92b  nop
0x18004d92c  lea     rcx, [rbp+var_40]
0x18004d930  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004d935  mov     ebx, r14d
0x18004d938  lea     rcx, [rbp+StringSid]
0x18004d93c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d941  mov     eax, ebx
0x18004d943  mov     rcx, [rbp+var_8]
0x18004d947  xor     rcx, rsp; StackCookie
0x18004d94a  call    __security_check_cookie
0x18004d94f  lea     r11, [rsp+70h+var_s0]
0x18004d954  mov     rbx, [r11+28h]
0x18004d958  mov     rsi, [r11+30h]
0x18004d95c  mov     rsp, r11
0x18004d95f  pop     r14
0x18004d961  pop     rdi
0x18004d962  pop     rbp
0x18004d963  retn
```
