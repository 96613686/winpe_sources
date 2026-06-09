# CUserName::InitializeUserName(void *)

- ea: `0x180008f40`
- end: `0x1800090e5`
- name: `?InitializeUserName@CUserName@@AEAAJPEAX@Z`
- size: `421`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800092e0`
- `0x1800093b0`
- `0x18001e8e0`
- `0x18002e960`
- `0x1800334a0`
- `0x180040070`

## callees

- `0x180006980`
- `0x1800077a0`
- `0x180008f40`
- `0x18004ec5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009075`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008f77`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008fda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008f77`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008fda`

## string_xrefs

- `0x18000902e`: `GetTokenInformatino failed: 0x%x`
- `0x18000905d`: `Can get the TOKEN_USER length`
- `0x18000908a`: `Can get the TOKEN_USER length: 0x%x`

## pseudocode

```c
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
0x180008f40  mov     [rsp+arg_0], rbx
0x180008f45  mov     [rsp+arg_8], rsi
0x180008f4a  push    rdi
0x180008f4b  sub     rsp, 30h
0x180008f4f  mov     rdi, rdx
0x180008f52  lea     rax, [rsp+38h+TokenInformationLength]
0x180008f57  mov     rbx, rcx
0x180008f5a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180008f5f  xor     esi, esi
0x180008f61  mov     rcx, rdi; TokenHandle
0x180008f64  xor     r9d, r9d; TokenInformationLength
0x180008f67  mov     [rsp+38h+TokenInformationLength], esi
0x180008f6b  xor     r8d, r8d; TokenInformation
0x180008f6e  mov     [rsp+38h+arg_18], esi
0x180008f72  mov     edx, 1; TokenInformationClass
0x180008f77  call    cs:__imp_GetTokenInformation
0x180008f7e  nop     dword ptr [rax+rax+00h]
0x180008f83  test    eax, eax
0x180008f85  jnz     loc_18000905D
0x180008f8b  call    cs:__imp_GetLastError
0x180008f92  nop     dword ptr [rax+rax+00h]
0x180008f97  cmp     eax, 7Ah ; 'z'
0x180008f9a  jnz     loc_180009075
0x180008fa0  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180008fa4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008fab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008fb0  mov     [rbx+648h], rax
0x180008fb7  test    rax, rax
0x180008fba  jz      loc_1800090B9
0x180008fc0  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180008fc5  lea     rcx, [rsp+38h+arg_18]
0x180008fca  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180008fcf  mov     r8, rax; TokenInformation
0x180008fd2  mov     rcx, rdi; TokenHandle
0x180008fd5  mov     edx, 1; TokenInformationClass
0x180008fda  call    cs:__imp_GetTokenInformation
0x180008fe1  nop     dword ptr [rax+rax+00h]
0x180008fe6  test    eax, eax
0x180008fe8  jz      short loc_180009019
0x180008fea  mov     rdx, rdi; void *
0x180008fed  mov     rcx, rbx; this
0x180008ff0  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x180008ff5  mov     edi, eax
0x180008ff7  test    eax, eax
0x180008ff9  js      loc_1800090C3
0x180008fff  or      dword ptr [rbx+640h], 2
0x180009006  mov     eax, esi
0x180009008  mov     rbx, [rsp+38h+arg_0]
0x18000900d  mov     rsi, [rsp+38h+arg_8]
0x180009012  add     rsp, 30h
0x180009016  pop     rdi
0x180009017  retn
0x180009019  call    cs:__imp_GetLastError
0x180009020  nop     dword ptr [rax+rax+00h]
0x180009025  mov     ebx, eax
0x180009027  test    eax, eax
0x180009029  jg      short loc_180009052
0x18000902b  mov     r8d, ebx
0x18000902e  lea     rdx, aGettokeninform_1; "GetTokenInformatino failed: 0x%x"
0x180009035  mov     ecx, 8; int
0x18000903a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000903f  mov     eax, ebx
0x180009041  mov     rbx, [rsp+38h+arg_0]
0x180009046  mov     rsi, [rsp+38h+arg_8]
0x18000904b  add     rsp, 30h
0x18000904f  pop     rdi
0x180009050  retn
0x180009052  movzx   ebx, ax
0x180009055  or      ebx, 80070000h
0x18000905b  jmp     short loc_18000902B
0x18000905d  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180009064  mov     ecx, 8; int
0x180009069  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000906e  mov     eax, 80070057h
0x180009073  jmp     short loc_180009008
0x180009075  call    cs:__imp_GetLastError
0x18000907c  nop     dword ptr [rax+rax+00h]
0x180009081  mov     ebx, eax
0x180009083  test    eax, eax
0x180009085  jg      short loc_1800090AE
0x180009087  mov     r8d, ebx
0x18000908a  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x180009091  mov     ecx, 8; int
0x180009096  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000909b  mov     rsi, [rsp+38h+arg_8]
0x1800090a0  mov     eax, ebx
0x1800090a2  mov     rbx, [rsp+38h+arg_0]
0x1800090a7  add     rsp, 30h
0x1800090ab  pop     rdi
0x1800090ac  retn
0x1800090ae  movzx   ebx, ax
0x1800090b1  or      ebx, 80070000h
0x1800090b7  jmp     short loc_180009087
0x1800090b9  mov     eax, 8007000Eh
0x1800090be  jmp     loc_180009008
0x1800090c3  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x1800090ca  mov     r8d, edi
0x1800090cd  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x1800090d4  mov     ecx, 8; int
0x1800090d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800090de  mov     eax, edi
0x1800090e0  jmp     loc_180009008
```
