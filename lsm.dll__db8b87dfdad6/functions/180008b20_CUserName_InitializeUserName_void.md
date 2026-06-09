# CUserName::InitializeUserName(void *)

- ea: `0x180008b20`
- end: `0x180008ca4`
- name: `?InitializeUserName@CUserName@@AEAAJPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a1e0`
- `0x18000a2f0`
- `0x18001d4b0`
- `0x18002ca10`
- `0x180031400`
- `0x18003d93c`

## callees

- `0x1800067f0`
- `0x1800074c0`
- `0x180008b20`
- `0x18004b86c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008bae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008bae`

## string_xrefs

- `0x180008bf5`: `GetTokenInformatino failed: 0x%x`
- `0x180008c23`: `Can get the TOKEN_USER length`
- `0x180008c4a`: `Can get the TOKEN_USER length: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserName::InitializeUserName(CUserName *this, void *a2)
{
  void *v4; // rax
  int v5; // eax
  unsigned int v6; // edi
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  unsigned int v11; // ebx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
  {
    _DbgPrintMessage(8, "Can get the TOKEN_USER length");
    return 2147942487LL;
  }
  else if ( GetLastError() == 122 )
  {
    v4 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 201) = v4;
    if ( v4 )
    {
      if ( GetTokenInformation(a2, TokenUser, v4, TokenInformationLength, &ReturnLength) )
      {
        v5 = CUserName::ResolveUserName((PSID **)this, a2);
        v6 = v5;
        if ( v5 < 0 )
        {
          _DbgPrintMessage(8, "ResolveUserName failed: 0x%x in %s", v5, "CUserName::InitializeUserName");
          return v6;
        }
        else
        {
          *((_DWORD *)this + 400) |= 2u;
          return 0;
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "GetTokenInformatino failed: 0x%x", v9);
        return v9;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    _DbgPrintMessage(8, "Can get the TOKEN_USER length: 0x%x", v11);
    return v11;
  }
}

```

## disassembly

```asm
0x180008b20  mov     [rsp+arg_0], rbx
0x180008b25  mov     [rsp+arg_8], rsi
0x180008b2a  push    rdi
0x180008b2b  sub     rsp, 30h
0x180008b2f  mov     rdi, rdx
0x180008b32  lea     rax, [rsp+38h+TokenInformationLength]
0x180008b37  mov     rbx, rcx
0x180008b3a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180008b3f  xor     esi, esi
0x180008b41  mov     rcx, rdi; TokenHandle
0x180008b44  xor     r9d, r9d; TokenInformationLength
0x180008b47  mov     [rsp+38h+TokenInformationLength], esi
0x180008b4b  xor     r8d, r8d; TokenInformation
0x180008b4e  mov     [rsp+38h+arg_18], esi
0x180008b52  mov     edx, 1; TokenInformationClass
0x180008b57  call    cs:__imp_GetTokenInformation
0x180008b5d  test    eax, eax
0x180008b5f  jnz     loc_180008C23
0x180008b65  call    cs:__imp_GetLastError
0x180008b6b  cmp     eax, 7Ah ; 'z'
0x180008b6e  jnz     loc_180008C3B
0x180008b74  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180008b78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008b7f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008b84  mov     [rbx+648h], rax
0x180008b8b  test    rax, rax
0x180008b8e  jz      loc_180008C78
0x180008b94  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180008b99  lea     rcx, [rsp+38h+arg_18]
0x180008b9e  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180008ba3  mov     r8, rax; TokenInformation
0x180008ba6  mov     rcx, rdi; TokenHandle
0x180008ba9  mov     edx, 1; TokenInformationClass
0x180008bae  call    cs:__imp_GetTokenInformation
0x180008bb4  test    eax, eax
0x180008bb6  jz      short loc_180008BE6
0x180008bb8  mov     rdx, rdi; void *
0x180008bbb  mov     rcx, rbx; this
0x180008bbe  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x180008bc3  mov     edi, eax
0x180008bc5  test    eax, eax
0x180008bc7  js      loc_180008C82
0x180008bcd  or      dword ptr [rbx+640h], 2
0x180008bd4  mov     eax, esi
0x180008bd6  mov     rbx, [rsp+38h+arg_0]
0x180008bdb  mov     rsi, [rsp+38h+arg_8]
0x180008be0  add     rsp, 30h
0x180008be4  pop     rdi
0x180008be5  retn
0x180008be6  call    cs:__imp_GetLastError
0x180008bec  mov     ebx, eax
0x180008bee  test    eax, eax
0x180008bf0  jg      short loc_180008C18
0x180008bf2  mov     r8d, ebx
0x180008bf5  lea     rdx, aGettokeninform_1; "GetTokenInformatino failed: 0x%x"
0x180008bfc  mov     ecx, 8; int
0x180008c01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c06  mov     eax, ebx
0x180008c08  mov     rbx, [rsp+38h+arg_0]
0x180008c0d  mov     rsi, [rsp+38h+arg_8]
0x180008c12  add     rsp, 30h
0x180008c16  pop     rdi
0x180008c17  retn
0x180008c18  movzx   ebx, ax
0x180008c1b  or      ebx, 80070000h
0x180008c21  jmp     short loc_180008BF2
0x180008c23  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180008c2a  mov     ecx, 8; int
0x180008c2f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c34  mov     eax, 80070057h
0x180008c39  jmp     short loc_180008BD6
0x180008c3b  call    cs:__imp_GetLastError
0x180008c41  mov     ebx, eax
0x180008c43  test    eax, eax
0x180008c45  jg      short loc_180008C6D
0x180008c47  mov     r8d, ebx
0x180008c4a  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x180008c51  mov     ecx, 8; int
0x180008c56  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c5b  mov     rsi, [rsp+38h+arg_8]
0x180008c60  mov     eax, ebx
0x180008c62  mov     rbx, [rsp+38h+arg_0]
0x180008c67  add     rsp, 30h
0x180008c6b  pop     rdi
0x180008c6c  retn
0x180008c6d  movzx   ebx, ax
0x180008c70  or      ebx, 80070000h
0x180008c76  jmp     short loc_180008C47
0x180008c78  mov     eax, 8007000Eh
0x180008c7d  jmp     loc_180008BD6
0x180008c82  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x180008c89  mov     r8d, edi
0x180008c8c  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x180008c93  mov     ecx, 8; int
0x180008c98  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008c9d  mov     eax, edi
0x180008c9f  jmp     loc_180008BD6
```
