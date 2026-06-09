# CUtils::CreateUserSignInCapabilitySID(void * *)

- ea: `0x18007e5e4`
- end: `0x18007e772`
- name: `?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019dc8`

## callees

- `0x1800074c0`
- `0x18004b8b4`
- `0x18007e5e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e6b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e6fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e71b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e744`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e6fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e71b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e744`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e761`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007e6a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007e6a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007e68a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007e68a`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18007e65b`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18007e65b`

## string_xrefs

- `0x18007e6c1`: `CopySid failed: 0x%x in %s`
- `0x18007e61d`: `ppUserSignInCapabilitySid`
- `0x18007e616`: `CUtils::CreateUserSignInCapabilitySID`
- `0x18007e6d9`: `CUtils::CreateUserSignInCapabilitySID`
- `0x18007e674`: `CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s`
- `0x18007e6cf`: `Too many sids??? failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateUserSignInCapabilitySID(void **a1)
{
  unsigned int v2; // edi
  signed int v3; // eax
  size_t LengthSid; // rbx
  void *v5; // rax
  PSID *v6; // r8
  signed int LastError; // eax
  HLOCAL *v8; // rcx
  __int64 i; // rsi
  HLOCAL *v10; // rcx
  __int64 j; // rsi
  unsigned int v13; // [rsp+60h] [rbp+28h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+30h] BYREF
  HLOCAL v15; // [rsp+70h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+40h] BYREF

  hMem = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( a1 )
  {
    v2 = 0;
    if ( (unsigned int)DeriveCapabilitySidsFromName(L"UserSignInSupport", &hMem, &v13, &v15, &v14)
      || (v3 = GetLastError(), v2 = v3, v3 >= 0) )
    {
      if ( v14 == 1 )
      {
        LengthSid = GetLengthSid(*(PSID *)v15);
        v5 = operator new(LengthSid);
        v6 = (PSID *)v15;
        *a1 = v5;
        if ( !CopySid(LengthSid, v5, *v6) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError < 0 )
            _DbgPrintMessage(
              8,
              "CopySid failed: 0x%x in %s",
              (unsigned int)LastError,
              "CUtils::CreateUserSignInCapabilitySID");
        }
      }
      else
      {
        v2 = -2147467259;
        _DbgPrintMessage(
          8,
          "Too many sids??? failed: 0x%x in %s",
          2147500037LL,
          "CUtils::CreateUserSignInCapabilitySID");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s",
        (unsigned int)v3,
        "CUtils::CreateUserSignInCapabilitySID");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "Missing paramter %s in %s",
      "ppUserSignInCapabilitySid",
      "CUtils::CreateUserSignInCapabilitySID");
    v2 = -2147024809;
  }
  v8 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( i = 0; (unsigned int)i < v13; v8 = (HLOCAL *)hMem )
    {
      LocalFree(v8[i]);
      *((_QWORD *)hMem + i) = 0;
      i = (unsigned int)(i + 1);
    }
    LocalFree(v8);
    hMem = 0;
    v13 = 0;
  }
  v10 = (HLOCAL *)v15;
  if ( v15 )
  {
    for ( j = 0; (unsigned int)j < v14; v10 = (HLOCAL *)v15 )
    {
      LocalFree(v10[j]);
      *((_QWORD *)v15 + j) = 0;
      j = (unsigned int)(j + 1);
    }
    LocalFree(v10);
  }
  return v2;
}

```

## disassembly

```asm
0x18007e5e4  push    rbp
0x18007e5e6  push    rbx
0x18007e5e7  push    rsi
0x18007e5e8  push    rdi
0x18007e5e9  mov     rbp, rsp
0x18007e5ec  sub     rsp, 38h
0x18007e5f0  mov     [rbp+hMem], 0
0x18007e5f8  mov     rsi, rcx
0x18007e5fb  mov     [rbp+arg_0], 0
0x18007e602  mov     [rbp+arg_10], 0
0x18007e60a  mov     [rbp+arg_8], 0
0x18007e611  test    rcx, rcx
0x18007e614  jnz     short loc_18007E63D
0x18007e616  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x18007e61d  lea     r8, aPpusersigninca; "ppUserSignInCapabilitySid"
0x18007e624  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18007e62b  lea     ecx, [rsi+8]; int
0x18007e62e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007e633  mov     edi, 80070057h
0x18007e638  jmp     loc_18007E6EA
0x18007e63d  lea     rax, [rbp+arg_8]
0x18007e641  xor     edi, edi
0x18007e643  lea     r9, [rbp+arg_10]
0x18007e647  mov     [rsp+38h+var_18], rax
0x18007e64c  lea     r8, [rbp+arg_0]
0x18007e650  lea     rdx, [rbp+hMem]
0x18007e654  lea     rcx, aUsersigninsupp; "UserSignInSupport"
0x18007e65b  call    cs:__imp_DeriveCapabilitySidsFromName
0x18007e661  test    eax, eax
0x18007e663  jnz     short loc_18007E67D
0x18007e665  call    cs:__imp_GetLastError
0x18007e66b  mov     edi, eax
0x18007e66d  test    eax, eax
0x18007e66f  jns     short loc_18007E67D
0x18007e671  mov     r8d, eax
0x18007e674  lea     rdx, aCreateusersign; "CreateUserSignInCapabilitySID - DeriveC"...
0x18007e67b  jmp     short loc_18007E6D9
0x18007e67d  cmp     [rbp+arg_8], 1
0x18007e681  jnz     short loc_18007E6CA
0x18007e683  mov     rcx, [rbp+arg_10]
0x18007e687  mov     rcx, [rcx]; pSid
0x18007e68a  call    cs:__imp_GetLengthSid
0x18007e690  mov     ecx, eax; Size
0x18007e692  mov     ebx, eax
0x18007e694  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e699  mov     r8, [rbp+arg_10]
0x18007e69d  mov     rdx, rax; pDestinationSid
0x18007e6a0  mov     ecx, ebx; nDestinationSidLength
0x18007e6a2  mov     [rsi], rax
0x18007e6a5  mov     r8, [r8]; pSourceSid
0x18007e6a8  call    cs:__imp_CopySid
0x18007e6ae  test    eax, eax
0x18007e6b0  jnz     short loc_18007E6EA
0x18007e6b2  call    cs:__imp_GetLastError
0x18007e6b8  mov     edi, eax
0x18007e6ba  test    eax, eax
0x18007e6bc  jns     short loc_18007E6EA
0x18007e6be  mov     r8d, eax
0x18007e6c1  lea     rdx, aCopysidFailed0; "CopySid failed: 0x%x in %s"
0x18007e6c8  jmp     short loc_18007E6D9
0x18007e6ca  mov     edi, 80004005h
0x18007e6cf  lea     rdx, aTooManySidsFai; "Too many sids??? failed: 0x%x in %s"
0x18007e6d6  mov     r8d, edi
0x18007e6d9  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x18007e6e0  mov     ecx, 8; int
0x18007e6e5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007e6ea  mov     rcx, [rbp+hMem]
0x18007e6ee  test    rcx, rcx
0x18007e6f1  jz      short loc_18007E730
0x18007e6f3  xor     esi, esi
0x18007e6f5  cmp     [rbp+arg_0], esi
0x18007e6f8  jbe     short loc_18007E71B
0x18007e6fa  mov     rcx, [rcx+rsi*8]; hMem
0x18007e6fe  call    cs:__imp_LocalFree
0x18007e704  mov     rax, [rbp+hMem]
0x18007e708  mov     qword ptr [rax+rsi*8], 0
0x18007e710  inc     esi
0x18007e712  mov     rcx, [rbp+hMem]; hMem
0x18007e716  cmp     esi, [rbp+arg_0]
0x18007e719  jb      short loc_18007E6FA
0x18007e71b  call    cs:__imp_LocalFree
0x18007e721  mov     [rbp+hMem], 0
0x18007e729  mov     [rbp+arg_0], 0
0x18007e730  mov     rcx, [rbp+arg_10]
0x18007e734  test    rcx, rcx
0x18007e737  jz      short loc_18007E767
0x18007e739  xor     esi, esi
0x18007e73b  cmp     [rbp+arg_8], esi
0x18007e73e  jbe     short loc_18007E761
0x18007e740  mov     rcx, [rcx+rsi*8]; hMem
0x18007e744  call    cs:__imp_LocalFree
0x18007e74a  mov     rax, [rbp+arg_10]
0x18007e74e  mov     qword ptr [rax+rsi*8], 0
0x18007e756  inc     esi
0x18007e758  mov     rcx, [rbp+arg_10]; hMem
0x18007e75c  cmp     esi, [rbp+arg_8]
0x18007e75f  jb      short loc_18007E740
0x18007e761  call    cs:__imp_LocalFree
0x18007e767  mov     eax, edi
0x18007e769  add     rsp, 38h
0x18007e76d  pop     rdi
0x18007e76e  pop     rsi
0x18007e76f  pop     rbx
0x18007e770  pop     rbp
0x18007e771  retn
```
