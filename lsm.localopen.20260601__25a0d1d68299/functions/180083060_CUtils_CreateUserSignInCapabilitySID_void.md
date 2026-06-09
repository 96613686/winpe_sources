# CUtils::CreateUserSignInCapabilitySID(void * *)

- ea: `0x180083060`
- end: `0x180083225`
- name: `?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z`
- size: `453`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ab80`

## callees

- `0x1800077a0`
- `0x18004eca4`
- `0x180083060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800830e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800830e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083146`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800831bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800831ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008320d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800831bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800831ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008320d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180083136`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180083136`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083112`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083112`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x1800830d7`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x1800830d7`

## string_xrefs

- `0x18008315b`: `CopySid failed: 0x%x in %s`
- `0x180083092`: `CUtils::CreateUserSignInCapabilitySID`
- `0x180083173`: `CUtils::CreateUserSignInCapabilitySID`
- `0x180083099`: `ppUserSignInCapabilitySid`
- `0x180083169`: `Too many sids??? failed: 0x%x in %s`
- `0x1800830fc`: `CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s`

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
0x180083060  push    rbp
0x180083062  push    rbx
0x180083063  push    rsi
0x180083064  push    rdi
0x180083065  mov     rbp, rsp
0x180083068  sub     rsp, 38h
0x18008306c  mov     [rbp+hMem], 0
0x180083074  mov     rsi, rcx
0x180083077  mov     [rbp+arg_0], 0
0x18008307e  mov     [rbp+arg_10], 0
0x180083086  mov     [rbp+arg_8], 0
0x18008308d  test    rcx, rcx
0x180083090  jnz     short loc_1800830B9
0x180083092  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x180083099  lea     r8, aPpusersigninca; "ppUserSignInCapabilitySid"
0x1800830a0  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800830a7  lea     ecx, [rsi+8]; int
0x1800830aa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800830af  mov     edi, 80070057h
0x1800830b4  jmp     loc_180083184
0x1800830b9  lea     rax, [rbp+arg_8]
0x1800830bd  xor     edi, edi
0x1800830bf  lea     r9, [rbp+arg_10]
0x1800830c3  mov     [rsp+38h+var_18], rax
0x1800830c8  lea     r8, [rbp+arg_0]
0x1800830cc  lea     rdx, [rbp+hMem]
0x1800830d0  lea     rcx, aUsersigninsupp; "UserSignInSupport"
0x1800830d7  call    cs:__imp_DeriveCapabilitySidsFromName
0x1800830de  nop     dword ptr [rax+rax+00h]
0x1800830e3  test    eax, eax
0x1800830e5  jnz     short loc_180083105
0x1800830e7  call    cs:__imp_GetLastError
0x1800830ee  nop     dword ptr [rax+rax+00h]
0x1800830f3  mov     edi, eax
0x1800830f5  test    eax, eax
0x1800830f7  jns     short loc_180083105
0x1800830f9  mov     r8d, eax
0x1800830fc  lea     rdx, aCreateusersign; "CreateUserSignInCapabilitySID - DeriveC"...
0x180083103  jmp     short loc_180083173
0x180083105  cmp     [rbp+arg_8], 1
0x180083109  jnz     short loc_180083164
0x18008310b  mov     rcx, [rbp+arg_10]
0x18008310f  mov     rcx, [rcx]; pSid
0x180083112  call    cs:__imp_GetLengthSid
0x180083119  nop     dword ptr [rax+rax+00h]
0x18008311e  mov     ecx, eax; Size
0x180083120  mov     ebx, eax
0x180083122  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083127  mov     r8, [rbp+arg_10]
0x18008312b  mov     rdx, rax; pDestinationSid
0x18008312e  mov     ecx, ebx; nDestinationSidLength
0x180083130  mov     [rsi], rax
0x180083133  mov     r8, [r8]; pSourceSid
0x180083136  call    cs:__imp_CopySid
0x18008313d  nop     dword ptr [rax+rax+00h]
0x180083142  test    eax, eax
0x180083144  jnz     short loc_180083184
0x180083146  call    cs:__imp_GetLastError
0x18008314d  nop     dword ptr [rax+rax+00h]
0x180083152  mov     edi, eax
0x180083154  test    eax, eax
0x180083156  jns     short loc_180083184
0x180083158  mov     r8d, eax
0x18008315b  lea     rdx, aCopysidFailed0; "CopySid failed: 0x%x in %s"
0x180083162  jmp     short loc_180083173
0x180083164  mov     edi, 80004005h
0x180083169  lea     rdx, aTooManySidsFai; "Too many sids??? failed: 0x%x in %s"
0x180083170  mov     r8d, edi
0x180083173  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x18008317a  mov     ecx, 8; int
0x18008317f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180083184  mov     rcx, [rbp+hMem]
0x180083188  test    rcx, rcx
0x18008318b  jz      short loc_1800831D6
0x18008318d  xor     esi, esi
0x18008318f  cmp     [rbp+arg_0], esi
0x180083192  jbe     short loc_1800831BB
0x180083194  mov     rcx, [rcx+rsi*8]; hMem
0x180083198  call    cs:__imp_LocalFree
0x18008319f  nop     dword ptr [rax+rax+00h]
0x1800831a4  mov     rax, [rbp+hMem]
0x1800831a8  mov     qword ptr [rax+rsi*8], 0
0x1800831b0  inc     esi
0x1800831b2  mov     rcx, [rbp+hMem]; hMem
0x1800831b6  cmp     esi, [rbp+arg_0]
0x1800831b9  jb      short loc_180083194
0x1800831bb  call    cs:__imp_LocalFree
0x1800831c2  nop     dword ptr [rax+rax+00h]
0x1800831c7  mov     [rbp+hMem], 0
0x1800831cf  mov     [rbp+arg_0], 0
0x1800831d6  mov     rcx, [rbp+arg_10]
0x1800831da  test    rcx, rcx
0x1800831dd  jz      short loc_180083219
0x1800831df  xor     esi, esi
0x1800831e1  cmp     [rbp+arg_8], esi
0x1800831e4  jbe     short loc_18008320D
0x1800831e6  mov     rcx, [rcx+rsi*8]; hMem
0x1800831ea  call    cs:__imp_LocalFree
0x1800831f1  nop     dword ptr [rax+rax+00h]
0x1800831f6  mov     rax, [rbp+arg_10]
0x1800831fa  mov     qword ptr [rax+rsi*8], 0
0x180083202  inc     esi
0x180083204  mov     rcx, [rbp+arg_10]; hMem
0x180083208  cmp     esi, [rbp+arg_8]
0x18008320b  jb      short loc_1800831E6
0x18008320d  call    cs:__imp_LocalFree
0x180083214  nop     dword ptr [rax+rax+00h]
0x180083219  mov     eax, edi
0x18008321b  add     rsp, 38h
0x18008321f  pop     rdi
0x180083220  pop     rsi
0x180083221  pop     rbx
0x180083222  pop     rbp
0x180083223  retn
```
