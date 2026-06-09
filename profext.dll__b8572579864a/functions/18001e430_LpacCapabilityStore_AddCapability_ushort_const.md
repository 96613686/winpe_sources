# LpacCapabilityStore::AddCapability(ushort const *)

- ea: `0x18001e430`
- end: `0x18001e519`
- name: `?AddCapability@LpacCapabilityStore@@QEAAJPEBG@Z`
- size: `233`
- prototype: `__int64 __fastcall(LpacCapabilityStore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e520`

## callees

- `0x18000f864`
- `0x18001e308`
- `0x18001e430`
- `0x18001e80c`
- `0x18001e88c`

## import_xrefs

- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18001e46d`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18001e46d`

## string_xrefs

- `0x18001e481`: `onecore\ds\security\gina\profile\profext\lpaccapabilitystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LpacCapabilityStore::AddCapability(LpacCapabilityStore *this, const unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 v5; // rax
  __int64 *v6; // rbx
  __int64 *v7; // rsi
  __int64 v8; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h]
  _QWORD v12[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int v14; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+98h] [rbp+38h] BYREF

  v9 = 0;
  v15 = 0;
  v8 = 0;
  v14 = 0;
  if ( !(unsigned int)DeriveCapabilitySidsFromName(a2, &v8, &v14, &v9, &v15) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1F,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpaccapabilitystore.cpp",
             v3);
  v12[0] = v8;
  v12[1] = v14;
  v10 = v9;
  v11 = v15;
  std::vector<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>::push_back(
    this,
    &v10);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v10);
  v5 = *((_QWORD *)this + 1);
  v6 = *(__int64 **)(v5 - 16);
  v7 = &v6[*(_QWORD *)(v5 - 8)];
  while ( v6 != v7 )
  {
    v10 = *v6;
    v11 = 4;
    std::vector<_SID_AND_ATTRIBUTES>::push_back((char *)this + 24, &v10);
    ++v6;
  }
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(v12);
  return 0;
}

```

## disassembly

```asm
0x18001e430  mov     [rsp-18h+arg_0], rbx
0x18001e435  push    rbp
0x18001e436  push    rsi
0x18001e437  push    rdi
0x18001e438  mov     rbp, rsp
0x18001e43b  sub     rsp, 60h
0x18001e43f  mov     rax, rdx
0x18001e442  mov     rdi, rcx
0x18001e445  xor     ebx, ebx
0x18001e447  mov     [rbp+var_28], rbx
0x18001e44b  mov     [rbp+arg_18], ebx
0x18001e44e  mov     [rbp+var_30], rbx
0x18001e452  mov     [rbp+arg_10], ebx
0x18001e455  lea     rcx, [rbp+arg_18]
0x18001e459  mov     [rsp+60h+var_40], rcx
0x18001e45e  lea     r9, [rbp+var_28]
0x18001e462  lea     r8, [rbp+arg_10]
0x18001e466  lea     rdx, [rbp+var_30]
0x18001e46a  mov     rcx, rax
0x18001e46d  call    cs:__imp_DeriveCapabilitySidsFromName
0x18001e474  nop     dword ptr [rax+rax+00h]
0x18001e479  test    eax, eax
0x18001e47b  jnz     short loc_18001E492
0x18001e47d  mov     rcx, [rbp+18h]; this
0x18001e481  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e488  lea     edx, [rbx+1Fh]; void *
0x18001e48b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e490  jmp     short loc_18001E508
0x18001e492  mov     rax, [rbp+var_30]
0x18001e496  mov     [rbp+var_10], rax
0x18001e49a  mov     eax, [rbp+arg_10]
0x18001e49d  mov     [rbp+var_8], rax
0x18001e4a1  mov     rax, [rbp+var_28]
0x18001e4a5  mov     [rbp+var_20], rax
0x18001e4a9  mov     eax, [rbp+arg_18]
0x18001e4ac  mov     [rbp+var_18], rax
0x18001e4b0  lea     rdx, [rbp+var_20]
0x18001e4b4  mov     rcx, rdi
0x18001e4b7  call    ?push_back@?$vector@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@Z; std::vector<wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>>::push_back(wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64> &&)
0x18001e4bc  nop
0x18001e4bd  lea     rcx, [rbp+var_20]
0x18001e4c1  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18001e4c6  mov     rax, [rdi+8]
0x18001e4ca  mov     rbx, [rax-10h]
0x18001e4ce  mov     rax, [rax-8]
0x18001e4d2  lea     rsi, [rbx+rax*8]
0x18001e4d6  jmp     short loc_18001E4F8
0x18001e4d8  mov     rax, [rbx]
0x18001e4db  mov     [rbp+var_20], rax
0x18001e4df  mov     [rbp+var_18], 4
0x18001e4e7  lea     rdx, [rbp+var_20]
0x18001e4eb  lea     rcx, [rdi+18h]
0x18001e4ef  call    ?push_back@?$vector@U_SID_AND_ATTRIBUTES@@V?$allocator@U_SID_AND_ATTRIBUTES@@@std@@@std@@QEAAX$$QEAU_SID_AND_ATTRIBUTES@@@Z; std::vector<_SID_AND_ATTRIBUTES>::push_back(_SID_AND_ATTRIBUTES &&)
0x18001e4f4  add     rbx, 8
0x18001e4f8  cmp     rbx, rsi
0x18001e4fb  jnz     short loc_18001E4D8
0x18001e4fd  lea     rcx, [rbp+var_10]
0x18001e501  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18001e506  xor     eax, eax
0x18001e508  mov     rbx, [rsp+60h+arg_0]
0x18001e510  add     rsp, 60h
0x18001e514  pop     rdi
0x18001e515  pop     rsi
0x18001e516  pop     rbp
0x18001e517  retn
```
