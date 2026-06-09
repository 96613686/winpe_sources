# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x180063928`
- end: `0x180063b6d`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006341c`

## callees

- `0x18002c8d0`
- `0x180063928`
- `0x180063b74`
- `0x180063bb4`
- `0x180064884`
- `0x180083aa8`
- `0x180088d45`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063a57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063a57`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180063a36`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180063a36`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063a08`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063a08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063a70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063a70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180063b62`

## string_xrefs

- `0x1800639a9`: `PackageSID`
- `0x180063ac5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180063b2a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180063b44`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 *a2,
        const WCHAR *a3,
        __int64 a4)
{
  int Field; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  LPCWSTR v10; // rcx
  BOOL v11; // ebx
  const char *v12; // r9
  PSID v13; // rbx
  DWORD LengthSid; // eax
  PSID v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  LPCWSTR v19; // rcx
  PSID pSid; // [rsp+20h] [rbp-20h] BYREF
  __int64 *p_StringSid; // [rsp+28h] [rbp-18h]
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  char v23; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  LPCWSTR StringSid; // [rsp+80h] [rbp+40h] BYREF

  StringSid = a3;
  v23 = 1;
  p_StringSid = a2 + 1;
  Sid = 0;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamilyName", (unsigned __int16 **)&Sid);
  if ( v23 )
  {
    v8 = *p_StringSid;
    *p_StringSid = (__int64)Sid;
    if ( v8 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v17 = 775;
    goto LABEL_24;
  }
  StringSid = 0;
  p_StringSid = (__int64 *)&StringSid;
  Sid = 0;
  v23 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageSID", (unsigned __int16 **)&Sid);
  if ( v23 )
  {
    v9 = *p_StringSid;
    *p_StringSid = (__int64)Sid;
    if ( v9 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
    goto LABEL_28;
  }
  v10 = StringSid;
  if ( !StringSid )
  {
    a2[11] = 0;
    goto LABEL_17;
  }
  pSid = 0;
  p_StringSid = (__int64 *)&pSid;
  Sid = 0;
  v23 = 1;
  v11 = ConvertStringSidToSidW(StringSid, &Sid);
  if ( v23 )
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      p_StringSid,
      Sid);
  if ( !v11 )
  {
    Field = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x315,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
              v12);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
LABEL_28:
    v19 = StringSid;
    StringSid = 0;
    if ( v19 )
      SRCache_Free();
    return (unsigned int)Field;
  }
  v13 = pSid;
  LengthSid = GetLengthSid(pSid);
  memcpy_0(a2 + 2, v13, LengthSid);
  v15 = pSid;
  a2[11] = (__int64)(a2 + 2);
  if ( v15 )
    LocalFree(v15);
  v10 = StringSid;
LABEL_17:
  StringSid = 0;
  if ( v10 )
    SRCache_Free();
  Sid = 0;
  p_StringSid = a2 + 12;
  v23 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Publisher", (unsigned __int16 **)&Sid);
  if ( v23 )
  {
    v16 = *p_StringSid;
    *p_StringSid = (__int64)Sid;
    if ( v16 )
      SRCache_Free();
  }
  if ( Field < 0 )
  {
    v17 = 796;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
    return (unsigned int)Field;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x180063928  mov     [rsp-28h+arg_0], rbx
0x18006392d  mov     [rsp-28h+arg_8], rsi
0x180063932  mov     [rsp-28h+StringSid], r8
0x180063937  push    rbp
0x180063938  push    rdi
0x180063939  push    r12
0x18006393b  push    r14
0x18006393d  push    r15
0x18006393f  mov     rbp, rsp
0x180063942  sub     rsp, 40h
0x180063946  lea     rax, [rdx+8]
0x18006394a  mov     [rbp+var_8], 1
0x18006394e  mov     rsi, rdx
0x180063951  mov     [rbp+var_18], rax
0x180063955  xor     r12d, r12d
0x180063958  lea     rdx, aPackagefamilyn; "PackageFamilyName"
0x18006395f  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180063963  mov     [rbp+Sid], r12
0x180063967  mov     r15, r9
0x18006396a  mov     r14, rcx
0x18006396d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180063972  mov     ebx, eax
0x180063974  cmp     [rbp+var_8], r12b
0x180063978  jz      short loc_180063991
0x18006397a  mov     r8, [rbp+var_18]
0x18006397e  mov     rdx, [rbp+Sid]
0x180063982  mov     rcx, [r8]
0x180063985  mov     [r8], rdx
0x180063988  test    rcx, rcx
0x18006398b  jnz     loc_180063B10
0x180063991  test    ebx, ebx
0x180063993  js      loc_180063AF4
0x180063999  lea     rax, [rbp+StringSid]
0x18006399d  mov     [rbp+StringSid], r12
0x1800639a1  lea     r8, [rbp+Sid]; unsigned __int16 **
0x1800639a5  mov     [rbp+var_18], rax
0x1800639a9  lea     rdx, aPackagesid; "PackageSID"
0x1800639b0  mov     [rbp+Sid], r12
0x1800639b4  mov     rcx, r14; this
0x1800639b7  mov     [rbp+var_8], 1
0x1800639bb  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800639c0  mov     ebx, eax
0x1800639c2  cmp     [rbp+var_8], r12b
0x1800639c6  jz      short loc_1800639DF
0x1800639c8  mov     r8, [rbp+var_18]
0x1800639cc  mov     rdx, [rbp+Sid]
0x1800639d0  mov     rcx, [r8]
0x1800639d3  mov     [r8], rdx
0x1800639d6  test    rcx, rcx
0x1800639d9  jnz     loc_180063B1B
0x1800639df  test    ebx, ebx
0x1800639e1  js      loc_180063B26
0x1800639e7  mov     rcx, [rbp+StringSid]; StringSid
0x1800639eb  test    rcx, rcx
0x1800639ee  jz      short loc_180063A63
0x1800639f0  lea     rax, [rbp+pSid]
0x1800639f4  mov     [rbp+pSid], r12
0x1800639f8  lea     rdx, [rbp+Sid]; Sid
0x1800639fc  mov     [rbp+var_18], rax
0x180063a00  mov     [rbp+Sid], r12
0x180063a04  mov     [rbp+var_8], 1
0x180063a08  call    cs:__imp_ConvertStringSidToSidW
0x180063a0e  mov     ebx, eax
0x180063a10  cmp     [rbp+var_8], r12b
0x180063a14  jz      short loc_180063A23
0x180063a16  mov     rdx, [rbp+Sid]
0x180063a1a  mov     rcx, [rbp+var_18]
0x180063a1e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180063a23  test    ebx, ebx
0x180063a25  jz      loc_180063B40
0x180063a2b  mov     rbx, [rbp+pSid]
0x180063a2f  lea     rdi, [rsi+10h]
0x180063a33  mov     rcx, rbx; pSid
0x180063a36  call    cs:__imp_GetLengthSid
0x180063a3c  mov     r8d, eax; Size
0x180063a3f  mov     rdx, rbx; Src
0x180063a42  mov     rcx, rdi; void *
0x180063a45  call    memcpy_0
0x180063a4a  mov     rcx, [rbp+pSid]; hMem
0x180063a4e  mov     [rsi+58h], rdi
0x180063a52  test    rcx, rcx
0x180063a55  jz      short loc_180063A5D
0x180063a57  call    cs:__imp_LocalFree
0x180063a5d  mov     rcx, [rbp+StringSid]
0x180063a61  jmp     short loc_180063A67
0x180063a63  mov     [rsi+58h], r12
0x180063a67  mov     [rbp+StringSid], r12
0x180063a6b  test    rcx, rcx
0x180063a6e  jz      short loc_180063A76
0x180063a70  call    cs:__imp_SRCache_Free
0x180063a76  lea     rax, [rsi+60h]
0x180063a7a  mov     [rbp+Sid], r12
0x180063a7e  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180063a82  mov     [rbp+var_18], rax
0x180063a86  lea     rdx, aPublisher; "Publisher"
0x180063a8d  mov     [rbp+var_8], 1
0x180063a91  mov     rcx, r14; this
0x180063a94  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180063a99  mov     ebx, eax
0x180063a9b  cmp     [rbp+var_8], r12b
0x180063a9f  jz      short loc_180063AB8
0x180063aa1  mov     r8, [rbp+var_18]
0x180063aa5  mov     rdx, [rbp+Sid]
0x180063aa9  mov     rcx, [r8]
0x180063aac  mov     [r8], rdx
0x180063aaf  test    rcx, rcx
0x180063ab2  jnz     loc_180063B62
0x180063ab8  test    ebx, ebx
0x180063aba  jns     short loc_180063AED
0x180063abc  mov     edx, 31Ch; void *
0x180063ac1  mov     rcx, [rbp+28h]; this
0x180063ac5  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063acc  mov     r9d, ebx; char *
0x180063acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063ad4  mov     eax, ebx
0x180063ad6  mov     rbx, [rsp+40h+arg_0]
0x180063adb  mov     rsi, [rsp+40h+arg_8]
0x180063ae0  add     rsp, 40h
0x180063ae4  pop     r15
0x180063ae6  pop     r14
0x180063ae8  pop     r12
0x180063aea  pop     rdi
0x180063aeb  pop     rbp
0x180063aec  retn
0x180063aed  mov     [rsi], r15
0x180063af0  xor     eax, eax
0x180063af2  jmp     short loc_180063AD6
0x180063af4  mov     edx, 307h
0x180063af9  jmp     short loc_180063AC1
0x180063afb  mov     rcx, [rbp+StringSid]
0x180063aff  mov     [rbp+StringSid], r12
0x180063b03  test    rcx, rcx
0x180063b06  jz      short loc_180063AD4
0x180063b08  call    cs:__imp_SRCache_Free
0x180063b0e  jmp     short loc_180063AD4
0x180063b10  call    cs:__imp_SRCache_Free
0x180063b16  jmp     loc_180063991
0x180063b1b  call    cs:__imp_SRCache_Free
0x180063b21  jmp     loc_1800639DF
0x180063b26  mov     rcx, [rbp+28h]; this
0x180063b2a  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063b31  mov     r9d, ebx; char *
0x180063b34  mov     edx, 30Dh; void *
0x180063b39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063b3e  jmp     short loc_180063AFB
0x180063b40  mov     rcx, [rbp+28h]; this
0x180063b44  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180063b4b  mov     edx, 315h; void *
0x180063b50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063b55  lea     rcx, [rbp+pSid]
0x180063b59  mov     ebx, eax
0x180063b5b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180063b60  jmp     short loc_180063AFB
0x180063b62  call    cs:__imp_SRCache_Free
0x180063b68  jmp     loc_180063AB8
```
