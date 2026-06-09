# DoesPackageHaveCapability(ushort const *,ushort const *,int *)

- ea: `0x18003a1d4`
- end: `0x18003a393`
- name: `?DoesPackageHaveCapability@@YAJPEBG0PEAH@Z`
- size: `447`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fc60`
- `0x18003fc80`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180010a84`
- `0x180020338`
- `0x18003a1d4`
- `0x18003fbb8`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003a2dc`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003a2dc`
- `ntdll!RtlInitUnicodeString` at `0x18003a2bb`
- `ntdll!RtlInitUnicodeString` at `0x18003a2bb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a317`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a317`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003a252`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003a252`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall DoesPackageHaveCapability(const unsigned __int16 *a1, const unsigned __int16 *a2, int *a3)
{
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v11; // [rsp+50h] [rbp-108h] BYREF
  unsigned __int64 v12; // [rsp+58h] [rbp-100h]
  __int64 *v13; // [rsp+68h] [rbp-F0h]
  unsigned int v14; // [rsp+70h] [rbp-E8h] BYREF
  char v15; // [rsp+74h] [rbp-E4h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-E0h] BYREF
  _BYTE pSid2[80]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v18[80]; // [rsp+E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v11 = 0;
  v12 = 0;
  v13 = &v11;
  v14 = 0;
  v15 = 1;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v11);
  v6 = QueryApplicationCapabilities(a1, &v11, &v14, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v6,
      0);
  if ( v15 )
    v13[1] = v14;
  DestinationString = 0;
  memset_0(pSid2, 0, 0x44u);
  memset_0(v18, 0, 0x44u);
  RtlInitUnicodeString(&DestinationString, a2);
  v7 = RtlDeriveCapabilitySidsFromName(&DestinationString, v18, pSid2);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v7,
      0);
  *a3 = 0;
  v8 = 0;
  if ( v12 )
  {
    v9 = 0;
    while ( !EqualSid(*(PSID *)(v11 + 8 * v9), pSid2) )
    {
      v9 = ++v8;
      if ( v8 >= v12 )
        goto LABEL_11;
    }
    *a3 = 1;
  }
LABEL_11:
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v11);
  return 0;
}

```

## disassembly

```asm
0x18003a1d4  push    rbx
0x18003a1d6  push    rsi
0x18003a1d7  push    rdi
0x18003a1d8  sub     rsp, 140h
0x18003a1df  mov     rax, cs:__security_cookie
0x18003a1e6  xor     rax, rsp
0x18003a1e9  mov     [rsp+158h+var_28], rax
0x18003a1f1  mov     rdi, r8
0x18003a1f4  mov     rsi, rdx
0x18003a1f7  mov     rbx, rcx
0x18003a1fa  and     [rsp+158h+var_108], 0
0x18003a200  and     [rsp+158h+var_100], 0
0x18003a206  lea     rax, [rsp+158h+var_108]
0x18003a20b  mov     [rsp+158h+var_F0], rax
0x18003a210  and     [rsp+158h+var_E8], 0
0x18003a215  mov     [rsp+158h+var_E4], 1
0x18003a21a  lea     rcx, [rsp+158h+var_108]
0x18003a21f  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18003a224  and     [rsp+158h+var_118], 0
0x18003a22a  and     [rsp+158h+var_120], 0
0x18003a230  and     [rsp+158h+var_128], 0
0x18003a236  and     [rsp+158h+var_130], 0
0x18003a23c  and     [rsp+158h+var_138], 0
0x18003a242  xor     r9d, r9d
0x18003a245  lea     r8, [rsp+158h+var_E8]
0x18003a24a  lea     rdx, [rsp+158h+var_108]
0x18003a24f  mov     rcx, rbx
0x18003a252  call    cs:__imp_QueryApplicationCapabilities
0x18003a259  nop     dword ptr [rax+rax+00h]
0x18003a25e  mov     rcx, [rsp+158h]; this
0x18003a266  test    eax, eax
0x18003a268  js      loc_18003A368
0x18003a26e  cmp     [rsp+158h+var_E4], 0
0x18003a273  jz      short loc_18003A282
0x18003a275  mov     ecx, [rsp+158h+var_E8]
0x18003a279  mov     rax, [rsp+158h+var_F0]
0x18003a27e  mov     [rax+8], rcx
0x18003a282  xorps   xmm0, xmm0
0x18003a285  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x18003a28a  mov     ebx, 44h ; 'D'
0x18003a28f  mov     r8d, ebx; Size
0x18003a292  xor     edx, edx; Val
0x18003a294  lea     rcx, [rsp+158h+pSid2]; void *
0x18003a29c  call    memset_0
0x18003a2a1  mov     r8d, ebx; Size
0x18003a2a4  xor     edx, edx; Val
0x18003a2a6  lea     rcx, [rsp+158h+var_78]; void *
0x18003a2ae  call    memset_0
0x18003a2b3  mov     rdx, rsi; SourceString
0x18003a2b6  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x18003a2bb  call    cs:__imp_RtlInitUnicodeString
0x18003a2c2  nop     dword ptr [rax+rax+00h]
0x18003a2c7  lea     r8, [rsp+158h+pSid2]
0x18003a2cf  lea     rdx, [rsp+158h+var_78]
0x18003a2d7  lea     rcx, [rsp+158h+DestinationString]
0x18003a2dc  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18003a2e3  nop     dword ptr [rax+rax+00h]
0x18003a2e8  mov     rcx, [rsp+158h]; this
0x18003a2f0  test    eax, eax
0x18003a2f2  js      loc_18003A37D
0x18003a2f8  and     dword ptr [rdi], 0
0x18003a2fb  xor     ebx, ebx
0x18003a2fd  cmp     [rsp+158h+var_100], rbx
0x18003a302  jbe     short loc_18003A33A
0x18003a304  xor     eax, eax
0x18003a306  lea     rdx, [rsp+158h+pSid2]; pSid2
0x18003a30e  mov     rcx, [rsp+158h+var_108]
0x18003a313  mov     rcx, [rcx+rax*8]; pSid1
0x18003a317  call    cs:__imp_EqualSid
0x18003a31e  nop     dword ptr [rax+rax+00h]
0x18003a323  test    eax, eax
0x18003a325  jnz     short loc_18003A334
0x18003a327  inc     ebx
0x18003a329  mov     eax, ebx
0x18003a32b  cmp     rax, [rsp+158h+var_100]
0x18003a330  jb      short loc_18003A306
0x18003a332  jmp     short loc_18003A33A
0x18003a334  mov     dword ptr [rdi], 1
0x18003a33a  lea     rcx, [rsp+158h+var_108]
0x18003a33f  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18003a344  xor     eax, eax
0x18003a346  jmp     short loc_18003A34C
0x18003a348  mov     eax, [rsp+158h+var_F8]
0x18003a34c  mov     rcx, [rsp+158h+var_28]
0x18003a354  xor     rcx, rsp; StackCookie
0x18003a357  call    __security_check_cookie
0x18003a35c  add     rsp, 140h
0x18003a363  pop     rdi
0x18003a364  pop     rsi
0x18003a365  pop     rbx
0x18003a366  retn
0x18003a368  mov     r9d, eax; char *
0x18003a36b  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003a372  mov     edx, 2A7h; void *
0x18003a377  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a37d  mov     r9d, eax; char *
0x18003a380  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003a387  mov     edx, 2B0h; void *
0x18003a38c  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
