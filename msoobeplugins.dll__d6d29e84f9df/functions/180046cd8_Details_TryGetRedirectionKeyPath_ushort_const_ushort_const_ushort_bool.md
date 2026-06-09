# Details::TryGetRedirectionKeyPath(ushort const *,ushort const *,ushort * *,bool *)

- ea: `0x180046cd8`
- end: `0x180046de2`
- name: `?TryGetRedirectionKeyPath@Details@@YAJPEBG0PEAPEAGPEA_N@Z`
- size: `266`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800464fc`

## callees

- `0x180008544`
- `0x18001e9a4`
- `0x180046cd8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046dab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046dab`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180046d18`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180046d71`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180046d18`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180046d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046d29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046d29`

## pseudocode

```c
__int64 __fastcall Details::TryGetRedirectionKeyPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        LPCWCH *a3,
        bool *a4)
{
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  unsigned int v10; // ebx
  bool v11; // bl
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  LODWORD(cb) = 0;
  *a3 = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, 0, 0) == 234 )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    v15 = v8;
    v9 = v8;
    if ( !v8 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
        (const char *)0x8007000ELL,
        (int)&cb);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
      return v10;
    }
    if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, v8, (unsigned int)cb) )
    {
      *a4 = 0;
      v10 = 0;
      goto LABEL_11;
    }
    v15 = 0;
    *a3 = v9;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  }
  if ( !*a3 || (v11 = 1, CompareStringOrdinal(a2, -1, *a3, -1, 1) == 2) )
    v11 = 0;
  *a4 = v11;
  return 0;
}

```

## disassembly

```asm
0x180046cd8  mov     rax, rsp
0x180046cdb  mov     [rax+8], rbx
0x180046cdf  mov     [rax+10h], rbp
0x180046ce3  push    rsi
0x180046ce4  push    rdi
0x180046ce5  push    r14
0x180046ce7  sub     rsp, 30h
0x180046ceb  mov     byte ptr [r9], 0
0x180046cef  mov     rdi, r9
0x180046cf2  mov     dword ptr [rax+18h], 0
0x180046cf9  lea     rax, [rax+18h]
0x180046cfd  mov     qword ptr [r8], 0
0x180046d04  mov     rsi, r8
0x180046d07  xor     r8d, r8d
0x180046d0a  mov     qword ptr [rsp+48h+bIgnoreCase], rax; int
0x180046d0f  xor     r9d, r9d
0x180046d12  mov     rbp, rdx
0x180046d15  mov     r14, rcx
0x180046d18  call    cs:__imp_GetPersistedRegistryLocationW
0x180046d1e  cmp     eax, 0EAh
0x180046d23  jnz     short loc_180046D91
0x180046d25  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180046d29  call    cs:__imp_CoTaskMemAlloc
0x180046d2f  mov     [rsp+48h+arg_18], rax
0x180046d34  mov     rbx, rax
0x180046d37  test    rax, rax
0x180046d3a  jnz     short loc_180046D5A
0x180046d3c  mov     rcx, [rsp+48h]; this
0x180046d41  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180046d48  mov     ebx, 8007000Eh
0x180046d4d  lea     edx, [rax+2Dh]; void *
0x180046d50  mov     r9d, ebx; char *
0x180046d53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046d58  jmp     short loc_180046DD4
0x180046d5a  mov     r9d, dword ptr [rsp+48h+cb]
0x180046d5f  mov     r8, rbx
0x180046d62  mov     rdx, rbp
0x180046d65  mov     qword ptr [rsp+48h+bIgnoreCase], 0
0x180046d6e  mov     rcx, r14
0x180046d71  call    cs:__imp_GetPersistedRegistryLocationW
0x180046d77  test    eax, eax
0x180046d79  jnz     short loc_180046DCF
0x180046d7b  lea     rcx, [rsp+48h+arg_18]
0x180046d80  mov     [rsp+48h+arg_18], 0
0x180046d89  mov     [rsi], rbx
0x180046d8c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180046d91  mov     r8, [rsi]; lpString2
0x180046d94  test    r8, r8
0x180046d97  jz      short loc_180046DB6
0x180046d99  or      edx, 0FFFFFFFFh; cchCount1
0x180046d9c  mov     ebx, 1
0x180046da1  mov     r9d, edx; cchCount2
0x180046da4  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x180046da8  mov     rcx, rbp; lpString1
0x180046dab  call    cs:__imp_CompareStringOrdinal
0x180046db1  cmp     eax, 2
0x180046db4  jnz     short loc_180046DB8
0x180046db6  xor     bl, bl
0x180046db8  mov     [rdi], bl
0x180046dba  xor     eax, eax
0x180046dbc  mov     rbx, [rsp+48h+arg_0]
0x180046dc1  mov     rbp, [rsp+48h+arg_8]
0x180046dc6  add     rsp, 30h
0x180046dca  pop     r14
0x180046dcc  pop     rdi
0x180046dcd  pop     rsi
0x180046dce  retn
0x180046dcf  mov     byte ptr [rdi], 0
0x180046dd2  xor     ebx, ebx
0x180046dd4  lea     rcx, [rsp+48h+arg_18]
0x180046dd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180046dde  mov     eax, ebx
0x180046de0  jmp     short loc_180046DBC
```
