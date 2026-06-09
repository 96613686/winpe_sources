# PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18005e764`
- end: `0x18005e918`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005fe20`

## callees

- `0x180047324`
- `0x18004cc04`
- `0x18005c718`
- `0x18005e764`
- `0x18005ffd4`
- `0x180060014`
- `0x180060068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e7a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e83e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e7a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005e83e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e8fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e8fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e816`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e816`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005e877`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005e877`

## string_xrefs

- `0x18005e7cd`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`
- `0x18005e7ff`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`
- `0x18005e858`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`
- `0x18005e891`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`
- `0x18005e7b7`: `GetTokenInformation succeeded with an empty buffer!`
- `0x18005e7ef`: `GetTokenInformation (size) failed!`
- `0x18005e849`: `GetTokenInformation (token) failed!`
- `0x18005e882`: `ConvertSidToStringSid failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned __int64 *v4; // rdi
  BOOL TokenInformation; // eax
  char v6; // al
  DWORD LastError; // eax
  PSID *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r8
  LPWSTR v12; // r9
  unsigned __int64 v13; // rdx
  __int64 v14; // rdi
  const char *v15; // r9
  __int64 result; // rax
  char *v17; // [rsp+28h] [rbp-30h]
  char *v18; // [rsp+28h] [rbp-30h]
  char *v19; // [rsp+28h] [rbp-30h]
  const char *v20; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+18h] BYREF
  PSID *v24; // [rsp+78h] [rbp+20h]

  v2 = a2;
  v4 = a2 + 2;
  a2[2] = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_WORD *)a2 = 0;
  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v6 = TokenInformation;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
      (const char *)0x8000FFFFLL,
      v6,
      (bool)"GetTokenInformation succeeded with an empty buffer!",
      v20);
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
      (const char *)(LastError != 122),
      (bool)"GetTokenInformation (size) failed!",
      v17);
    v8 = (PSID *)LocalAlloc(0, TokenInformationLength);
    v24 = v8;
    v9 = GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
      (const char *)v9,
      (int)"GetTokenInformation (token) failed!",
      v18);
    StringSid = 0;
    v10 = ConvertSidToStringSidW(*v8, &StringSid);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
      (const char *)v10,
      (int)"ConvertSidToStringSid failed!",
      v19);
    v12 = StringSid;
    v13 = -1;
    do
      ++v13;
    while ( StringSid[v13] );
    if ( v13 > v2[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v2,
        v13,
        v11,
        StringSid);
    }
    else
    {
      if ( v2[3] > 7u )
        v2 = (_QWORD *)*v2;
      *v4 = v13;
      v14 = 2 * v13;
      memmove_0(v2, v12, 2 * v13);
      *(_WORD *)((char *)v2 + v14) = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    if ( v8 )
      LocalFree(v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB7,
                           (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18005e764  push    rbx
0x18005e766  push    rsi
0x18005e767  push    rdi
0x18005e768  push    r14
0x18005e76a  push    r15; char *
0x18005e76c  sub     rsp, 30h
0x18005e770  mov     rsi, rdx
0x18005e773  mov     r14, rcx
0x18005e776  lea     rdi, [rdx+10h]
0x18005e77a  xor     r15d, r15d
0x18005e77d  mov     [rdi], r15
0x18005e780  cmp     qword ptr [rdx+18h], 7
0x18005e785  jbe     short loc_18005E78A
0x18005e787  mov     rdx, [rdx]
0x18005e78a  mov     [rdx], r15w
0x18005e78e  mov     [rsp+58h+TokenInformationLength], r15d
0x18005e793  lea     rax, [rsp+58h+TokenInformationLength]
0x18005e798  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005e79d  xor     r9d, r9d; TokenInformationLength
0x18005e7a0  xor     r8d, r8d; TokenInformation
0x18005e7a3  lea     edx, [r9+1]; TokenInformationClass
0x18005e7a7  call    cs:__imp_GetTokenInformation
0x18005e7ad  test    eax, eax
0x18005e7af  setnz   al
0x18005e7b2  mov     rcx, [rsp+58h]; this
0x18005e7b7  lea     rdx, aGettokeninform_0; "GetTokenInformation succeeded with an e"...
0x18005e7be  mov     [rsp+58h+var_30], rdx; char *
0x18005e7c3  mov     byte ptr [rsp+58h+ReturnLength], al; char
0x18005e7c7  mov     r9d, 8000FFFFh; char *
0x18005e7cd  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\T"...
0x18005e7d4  mov     edx, 0AAh; void *
0x18005e7d9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005e7de  call    cs:__imp_GetLastError
0x18005e7e4  cmp     eax, 7Ah ; 'z'
0x18005e7e7  setnz   al
0x18005e7ea  mov     rcx, [rsp+58h]; this
0x18005e7ef  lea     rdx, aGettokeninform_2; "GetTokenInformation (size) failed!"
0x18005e7f6  mov     [rsp+58h+ReturnLength], rdx; bool
0x18005e7fb  movzx   r9d, al; char *
0x18005e7ff  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\T"...
0x18005e806  mov     edx, 0ACh; void *
0x18005e80b  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005e810  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18005e814  xor     ecx, ecx; uFlags
0x18005e816  call    cs:__imp_LocalAlloc
0x18005e81c  mov     rbx, rax
0x18005e81f  mov     [rsp+58h+arg_18], rax
0x18005e824  lea     rax, [rsp+58h+TokenInformationLength]
0x18005e829  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005e82e  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18005e833  mov     r8, rbx; TokenInformation
0x18005e836  mov     edx, 1; TokenInformationClass
0x18005e83b  mov     rcx, r14; TokenHandle
0x18005e83e  call    cs:__imp_GetTokenInformation
0x18005e844  mov     rcx, [rsp+58h]; this
0x18005e849  lea     rdx, aGettokeninform_3; "GetTokenInformation (token) failed!"
0x18005e850  mov     [rsp+58h+ReturnLength], rdx; int
0x18005e855  mov     r9d, eax; char *
0x18005e858  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\T"...
0x18005e85f  mov     edx, 0AFh; void *
0x18005e864  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18005e869  nop
0x18005e86a  mov     [rsp+58h+StringSid], r15
0x18005e86f  lea     rdx, [rsp+58h+StringSid]; StringSid
0x18005e874  mov     rcx, [rbx]; Sid
0x18005e877  call    cs:__imp_ConvertSidToStringSidW
0x18005e87d  mov     rcx, [rsp+58h]; this
0x18005e882  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSid failed!"
0x18005e889  mov     [rsp+58h+ReturnLength], rdx; int
0x18005e88e  mov     r9d, eax; char *
0x18005e891  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\T"...
0x18005e898  mov     edx, 0B2h; void *
0x18005e89d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18005e8a2  mov     r9, [rsp+58h+StringSid]
0x18005e8a7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005e8ab  inc     rdx
0x18005e8ae  cmp     [r9+rdx*2], r15w
0x18005e8b3  jnz     short loc_18005E8AB
0x18005e8b5  cmp     rdx, [rsi+18h]
0x18005e8b9  ja      short loc_18005E8E1
0x18005e8bb  cmp     qword ptr [rsi+18h], 7
0x18005e8c0  jbe     short loc_18005E8C5
0x18005e8c2  mov     rsi, [rsi]
0x18005e8c5  mov     [rdi], rdx
0x18005e8c8  lea     rdi, [rdx+rdx]
0x18005e8cc  mov     r8, rdi; Size
0x18005e8cf  mov     rdx, r9; Src
0x18005e8d2  mov     rcx, rsi; void *
0x18005e8d5  call    memmove_0
0x18005e8da  mov     [rdi+rsi], r15w
0x18005e8df  jmp     short loc_18005E8EA
0x18005e8e1  mov     rcx, rsi
0x18005e8e4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18005e8e9  nop
0x18005e8ea  lea     rcx, [rsp+58h+StringSid]
0x18005e8ef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005e8f4  nop
0x18005e8f5  test    rbx, rbx
0x18005e8f8  jz      short loc_18005E903
0x18005e8fa  mov     rcx, rbx; hMem
0x18005e8fd  call    cs:__imp_LocalFree
0x18005e903  xor     eax, eax
0x18005e905  jmp     short loc_18005E90B
0x18005e907  mov     eax, [rsp+58h+TokenInformationLength]
0x18005e90b  add     rsp, 30h
0x18005e90f  pop     r15
0x18005e911  pop     r14
0x18005e913  pop     rdi
0x18005e914  pop     rsi
0x18005e915  pop     rbx
0x18005e916  retn
```
