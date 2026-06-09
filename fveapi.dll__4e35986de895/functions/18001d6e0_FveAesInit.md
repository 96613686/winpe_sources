# FveAesInit

- ea: `0x18001d6e0`
- end: `0x18001d82a`
- name: `FveAesInit`
- size: `330`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001cff8`

## callees

- `0x18001d6e0`
- `0x18001d830`
- `0x180030060`
- `0x18011d388`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x18001d76a`
- `bcrypt!BCryptSetProperty` at `0x18001d7fd`
- `bcrypt!BCryptSetProperty` at `0x18001d76a`
- `bcrypt!BCryptSetProperty` at `0x18001d7fd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d725`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d7bb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d725`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d7bb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d819`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d819`

## string_xrefs

- `0x18001d7eb`: `CngChatConfiguration`

## pseudocode

```c
__int64 __fastcall FveAesInit(BCRYPT_ALG_HANDLE *phAlgorithm)
{
  NTSTATUS v2; // ebx
  LPCWSTR pszImplementation; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v5; // [rsp+58h] [rbp+20h] BYREF

  pszImplementation = 0;
  v5 = 0;
  FveRegistryGetAlgorithmProvider(&pszImplementation, &v5);
  v2 = BCryptOpenAlgorithmProvider(phAlgorithm, L"AES", pszImplementation, 0);
  if ( v2 < 0 )
  {
    if ( !pszImplementation )
      goto LABEL_12;
    if ( (unsigned __int8)FveDefaultToExistingProviders() )
      v2 = BCryptOpenAlgorithmProvider(phAlgorithm, L"AES", 0, 0);
  }
  if ( pszImplementation )
    FveLibFreeWithTag(pszImplementation, v5, 0);
  if ( v2 >= 0 )
  {
    v2 = BCryptSetProperty(*phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCCM", 0x20u, 0);
    if ( v2 >= 0 )
    {
      if ( qword_180174D20 )
        BCryptSetProperty(*phAlgorithm, L"CngChatConfiguration", qword_180174D20, cbInput, 0);
      return (unsigned int)v2;
    }
  }
LABEL_12:
  if ( *phAlgorithm )
    BCryptCloseAlgorithmProvider(*phAlgorithm, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001d6e0  mov     rax, rsp
0x18001d6e3  mov     [rax+8], rbx
0x18001d6e7  mov     [rax+20h], r9d
0x18001d6eb  mov     [rax+10h], rdx
0x18001d6ef  push    rdi
0x18001d6f0  sub     rsp, 30h
0x18001d6f4  mov     rdi, rcx
0x18001d6f7  mov     qword ptr [rax+10h], 0
0x18001d6ff  lea     rcx, [rax+10h]
0x18001d703  mov     dword ptr [rax+20h], 0
0x18001d70a  lea     rdx, [rax+20h]
0x18001d70e  call    FveRegistryGetAlgorithmProvider
0x18001d713  mov     r8, [rsp+38h+pszImplementation]; pszImplementation
0x18001d718  lea     rdx, aAes; "AES"
0x18001d71f  xor     r9d, r9d; dwFlags
0x18001d722  mov     rcx, rdi; phAlgorithm
0x18001d725  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001d72c  nop     dword ptr [rax+rax+00h]
0x18001d731  mov     ebx, eax
0x18001d733  test    eax, eax
0x18001d735  js      short loc_18001D79A
0x18001d737  cmp     [rsp+38h+pszImplementation], 0
0x18001d73d  jnz     loc_18001D7CE
0x18001d743  test    ebx, ebx
0x18001d745  js      loc_18001D80B
0x18001d74b  mov     rcx, [rdi]; hObject
0x18001d74e  lea     r8, pbInput; "ChainingModeCCM"
0x18001d755  mov     r9d, 20h ; ' '; cbInput
0x18001d75b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001d763  lea     rdx, aChainingmode; "ChainingMode"
0x18001d76a  call    cs:__imp_BCryptSetProperty
0x18001d771  nop     dword ptr [rax+rax+00h]
0x18001d776  mov     ebx, eax
0x18001d778  test    eax, eax
0x18001d77a  js      loc_18001D80B
0x18001d780  mov     r8, cs:qword_180174D20; pbInput
0x18001d787  test    r8, r8
0x18001d78a  jnz     short loc_18001D7E4
0x18001d78c  mov     eax, ebx
0x18001d78e  mov     rbx, [rsp+38h+arg_0]
0x18001d793  add     rsp, 30h
0x18001d797  pop     rdi
0x18001d798  retn
0x18001d79a  cmp     [rsp+38h+pszImplementation], 0
0x18001d7a0  jz      short loc_18001D80B
0x18001d7a2  call    FveDefaultToExistingProviders
0x18001d7a7  test    al, al
0x18001d7a9  jz      short loc_18001D737
0x18001d7ab  xor     r9d, r9d; dwFlags
0x18001d7ae  lea     rdx, aAes; "AES"
0x18001d7b5  xor     r8d, r8d; pszImplementation
0x18001d7b8  mov     rcx, rdi; phAlgorithm
0x18001d7bb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001d7c2  nop     dword ptr [rax+rax+00h]
0x18001d7c7  mov     ebx, eax
0x18001d7c9  jmp     loc_18001D737
0x18001d7ce  mov     edx, [rsp+38h+arg_18]
0x18001d7d2  xor     r8d, r8d
0x18001d7d5  mov     rcx, [rsp+38h+pszImplementation]
0x18001d7da  call    FveLibFreeWithTag
0x18001d7df  jmp     loc_18001D743
0x18001d7e4  mov     r9d, cs:cbInput; cbInput
0x18001d7eb  lea     rdx, aCngchatconfigu; "CngChatConfiguration"
0x18001d7f2  mov     rcx, [rdi]; hObject
0x18001d7f5  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001d7fd  call    cs:__imp_BCryptSetProperty
0x18001d804  nop     dword ptr [rax+rax+00h]
0x18001d809  jmp     short loc_18001D78C
0x18001d80b  mov     rcx, [rdi]; hAlgorithm
0x18001d80e  test    rcx, rcx
0x18001d811  jz      loc_18001D78C
0x18001d817  xor     edx, edx; dwFlags
0x18001d819  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001d820  nop     dword ptr [rax+rax+00h]
0x18001d825  jmp     loc_18001D78C
```
