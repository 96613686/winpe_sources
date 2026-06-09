# GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x18005e5f8`
- end: `0x18005e72e`
- name: `?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d084`
- `0x18005f3cc`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x1800097f4`
- `0x1800190d8`
- `0x18005e5f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e639`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e62b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e699`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e62b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e699`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e64e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e64e`

## string_xrefs

- `0x18005e666`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18005e6a8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18005e6e8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18005e703`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall GetTokenInformationHelper(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS a2, void **a3)
{
  DWORD LastError; // eax
  void *v6; // rbx
  int v7; // ebx
  const char *v8; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v13; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(uBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8000FFFFLL,
      ReturnLength);
    return v7;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x19,
               (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
               (const char *)LastError,
               ReturnLength);
    return 0;
  }
  v13 = LocalAlloc(0, (unsigned int)uBytes);
  v6 = v13;
  if ( v13 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, v13, uBytes, (PDWORD)&uBytes) )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             v8);
      goto LABEL_7;
    }
    v13 = 0;
    *a3 = v6;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
    return 0;
  }
  v7 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11,
    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
    (const char *)0x8007000ELL,
    ReturnLength);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return v7;
}

```

## disassembly

```asm
0x18005e5f8  mov     rax, rsp
0x18005e5fb  mov     [rax+8], rbx
0x18005e5ff  mov     [rax+18h], rsi
0x18005e603  mov     [rax+10h], edx
0x18005e606  push    rdi
0x18005e607  sub     rsp, 30h
0x18005e60b  xor     r9d, r9d; TokenInformationLength
0x18005e60e  mov     dword ptr [rax+10h], 0
0x18005e615  mov     rdi, r8
0x18005e618  lea     rax, [rax+10h]
0x18005e61c  xor     r8d, r8d; TokenInformation
0x18005e61f  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18005e624  mov     rsi, rcx
0x18005e627  lea     edx, [r9+1]; TokenInformationClass
0x18005e62b  call    cs:__imp_GetTokenInformation
0x18005e631  test    eax, eax
0x18005e633  jnz     loc_18005E6FE
0x18005e639  call    cs:__imp_GetLastError
0x18005e63f  cmp     eax, 7Ah ; 'z'
0x18005e642  jnz     loc_18005E6DF
0x18005e648  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x18005e64c  xor     ecx, ecx; uFlags
0x18005e64e  call    cs:__imp_LocalAlloc
0x18005e654  mov     [rsp+38h+arg_18], rax
0x18005e659  mov     rbx, rax
0x18005e65c  test    rax, rax
0x18005e65f  jnz     short loc_18005E67F
0x18005e661  mov     rcx, [rsp+38h]; this
0x18005e666  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005e66d  mov     ebx, 8007000Eh
0x18005e672  lea     edx, [rax+11h]; void *
0x18005e675  mov     r9d, ebx; char *
0x18005e678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e67d  jmp     short loc_18005E6B9
0x18005e67f  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x18005e684  lea     rax, [rsp+38h+uBytes]
0x18005e689  mov     r8, rbx; TokenInformation
0x18005e68c  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18005e691  mov     edx, 1; TokenInformationClass
0x18005e696  mov     rcx, rsi; TokenHandle
0x18005e699  call    cs:__imp_GetTokenInformation
0x18005e69f  test    eax, eax
0x18005e6a1  jnz     short loc_18005E6C5
0x18005e6a3  mov     rcx, [rsp+38h]; this
0x18005e6a8  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005e6af  lea     edx, [rax+13h]; void *
0x18005e6b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e6b7  mov     ebx, eax
0x18005e6b9  lea     rcx, [rsp+38h+arg_18]
0x18005e6be  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005e6c3  jmp     short loc_18005E71C
0x18005e6c5  lea     rcx, [rsp+38h+arg_18]
0x18005e6ca  mov     [rsp+38h+arg_18], 0
0x18005e6d3  mov     [rdi], rbx
0x18005e6d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005e6db  xor     eax, eax
0x18005e6dd  jmp     short loc_18005E71E
0x18005e6df  test    eax, eax
0x18005e6e1  jz      short loc_18005E6DB
0x18005e6e3  mov     rcx, [rsp+38h]; this
0x18005e6e8  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005e6ef  mov     r9d, eax; char *
0x18005e6f2  mov     edx, 19h; void *
0x18005e6f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005e6fc  jmp     short loc_18005E71E
0x18005e6fe  mov     rcx, [rsp+38h]; this
0x18005e703  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005e70a  mov     ebx, 8000FFFFh
0x18005e70f  mov     edx, 1Eh; void *
0x18005e714  mov     r9d, ebx; char *
0x18005e717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e71c  mov     eax, ebx
0x18005e71e  mov     rbx, [rsp+38h+arg_0]
0x18005e723  mov     rsi, [rsp+38h+arg_10]
0x18005e728  add     rsp, 30h
0x18005e72c  pop     rdi
0x18005e72d  retn
```
