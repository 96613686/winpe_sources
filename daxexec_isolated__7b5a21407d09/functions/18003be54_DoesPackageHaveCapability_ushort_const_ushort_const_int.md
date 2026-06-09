# DoesPackageHaveCapability(ushort const *,ushort const *,int *)

- ea: `0x18003be54`
- end: `0x18003c021`
- name: `?DoesPackageHaveCapability@@YAJPEBG0PEAH@Z`
- size: `461`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041a30`
- `0x180041a50`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x1800125f4`
- `0x180021118`
- `0x18003aa40`
- `0x18003be54`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003bf63`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003bf63`
- `ntdll!RtlInitUnicodeString` at `0x18003bf42`
- `ntdll!RtlInitUnicodeString` at `0x18003bf42`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bf9f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003bf9f`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003bedc`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003bedc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall DoesPackageHaveCapability(const unsigned __int16 *a1, const unsigned __int16 *a2, int *a3)
{
  int v5; // eax
  int v6; // eax
  __int64 v7; // rbx
  __int64 v9; // [rsp+58h] [rbp-F0h] BYREF
  unsigned __int64 v10; // [rsp+60h] [rbp-E8h]
  __int64 *v11; // [rsp+68h] [rbp-E0h]
  unsigned int v12; // [rsp+70h] [rbp-D8h] BYREF
  char v13; // [rsp+74h] [rbp-D4h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE pSid2[80]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v16[80]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v9 = 0;
  v10 = 0;
  v11 = &v9;
  v12 = 0;
  v13 = 1;
  v5 = QueryApplicationCapabilities(a1, &v9, &v12, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v5,
      0);
  if ( v13 )
    v11[1] = v12;
  DestinationString = 0;
  memset_0(pSid2, 0, 0x44u);
  memset_0(v16, 0, 0x44u);
  RtlInitUnicodeString(&DestinationString, a2);
  v6 = RtlDeriveCapabilitySidsFromName(&DestinationString, v16, pSid2);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v6,
      0);
  *a3 = 0;
  v7 = 0;
  if ( v10 )
  {
    while ( !EqualSid(*(PSID *)(v9 + 8 * v7), pSid2) )
    {
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= v10 )
        goto LABEL_10;
    }
    *a3 = 1;
  }
LABEL_10:
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(&v9);
  return 0;
}

```

## disassembly

```asm
0x18003be54  mov     [rsp+arg_18], rbx
0x18003be59  push    rdi
0x18003be5a  sub     rsp, 140h
0x18003be61  mov     rax, cs:__security_cookie
0x18003be68  xor     rax, rsp
0x18003be6b  mov     [rsp+148h+var_18], rax
0x18003be73  mov     rdi, r8
0x18003be76  mov     rbx, rdx
0x18003be79  mov     [rsp+148h+var_F0], 0
0x18003be82  mov     [rsp+148h+var_E8], 0
0x18003be8b  lea     rax, [rsp+148h+var_F0]
0x18003be90  mov     [rsp+148h+var_E0], rax
0x18003be95  mov     [rsp+148h+var_D8], 0
0x18003be9d  mov     [rsp+148h+var_D4], 1
0x18003bea2  mov     [rsp+148h+var_108], 0
0x18003beab  mov     [rsp+148h+var_110], 0
0x18003beb4  mov     [rsp+148h+var_118], 0
0x18003bebd  mov     [rsp+148h+var_120], 0
0x18003bec6  mov     qword ptr [rsp+148h+var_128], 0; int
0x18003becf  xor     r9d, r9d
0x18003bed2  lea     r8, [rsp+148h+var_D8]
0x18003bed7  lea     rdx, [rsp+148h+var_F0]
0x18003bedc  call    cs:__imp_QueryApplicationCapabilities
0x18003bee3  nop     dword ptr [rax+rax+00h]
0x18003bee8  mov     rcx, [rsp+148h]; this
0x18003bef0  test    eax, eax
0x18003bef2  js      loc_18003BFF6
0x18003bef8  cmp     [rsp+148h+var_D4], 0
0x18003befd  jz      short loc_18003BF0C
0x18003beff  mov     ecx, [rsp+148h+var_D8]
0x18003bf03  mov     rax, [rsp+148h+var_E0]
0x18003bf08  mov     [rax+8], rcx
0x18003bf0c  xorps   xmm0, xmm0
0x18003bf0f  movups  xmmword ptr [rsp+148h+DestinationString.Length], xmm0
0x18003bf14  xor     edx, edx; Val
0x18003bf16  lea     r8d, [rdx+44h]; Size
0x18003bf1a  lea     rcx, [rsp+148h+pSid2]; void *
0x18003bf22  call    memset_0
0x18003bf27  xor     edx, edx; Val
0x18003bf29  lea     r8d, [rdx+44h]; Size
0x18003bf2d  lea     rcx, [rsp+148h+var_68]; void *
0x18003bf35  call    memset_0
0x18003bf3a  mov     rdx, rbx; SourceString
0x18003bf3d  lea     rcx, [rsp+148h+DestinationString]; DestinationString
0x18003bf42  call    cs:__imp_RtlInitUnicodeString
0x18003bf49  nop     dword ptr [rax+rax+00h]
0x18003bf4e  lea     r8, [rsp+148h+pSid2]
0x18003bf56  lea     rdx, [rsp+148h+var_68]
0x18003bf5e  lea     rcx, [rsp+148h+DestinationString]
0x18003bf63  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18003bf6a  nop     dword ptr [rax+rax+00h]
0x18003bf6f  mov     rcx, [rsp+148h]; this
0x18003bf77  test    eax, eax
0x18003bf79  js      loc_18003C00B
0x18003bf7f  mov     dword ptr [rdi], 0
0x18003bf85  xor     ebx, ebx
0x18003bf87  cmp     [rsp+148h+var_E8], rbx
0x18003bf8c  jbe     short loc_18003BFC2
0x18003bf8e  lea     rdx, [rsp+148h+pSid2]; pSid2
0x18003bf96  mov     rcx, [rsp+148h+var_F0]
0x18003bf9b  mov     rcx, [rcx+rbx*8]; pSid1
0x18003bf9f  call    cs:__imp_EqualSid
0x18003bfa6  nop     dword ptr [rax+rax+00h]
0x18003bfab  test    eax, eax
0x18003bfad  jnz     short loc_18003BFBC
0x18003bfaf  inc     ebx
0x18003bfb1  mov     eax, ebx
0x18003bfb3  cmp     rax, [rsp+148h+var_E8]
0x18003bfb8  jb      short loc_18003BF8E
0x18003bfba  jmp     short loc_18003BFC2
0x18003bfbc  mov     dword ptr [rdi], 1
0x18003bfc2  lea     rcx, [rsp+148h+var_F0]
0x18003bfc7  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18003bfcc  xor     eax, eax
0x18003bfce  jmp     short loc_18003BFD4
0x18003bfd0  mov     eax, [rsp+148h+var_F8]
0x18003bfd4  mov     rcx, [rsp+148h+var_18]
0x18003bfdc  xor     rcx, rsp; StackCookie
0x18003bfdf  call    __security_check_cookie
0x18003bfe4  mov     rbx, [rsp+148h+arg_18]
0x18003bfec  add     rsp, 140h
0x18003bff3  pop     rdi
0x18003bff4  retn
0x18003bff6  mov     r9d, eax; char *
0x18003bff9  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c000  mov     edx, 2A7h; void *
0x18003c005  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c00b  mov     r9d, eax; char *
0x18003c00e  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c015  mov     edx, 2B0h; void *
0x18003c01a  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
