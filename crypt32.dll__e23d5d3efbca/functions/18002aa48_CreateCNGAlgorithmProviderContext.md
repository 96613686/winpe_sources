# CreateCNGAlgorithmProviderContext

- ea: `0x18002aa48`
- end: `0x18002ab8f`
- name: `CreateCNGAlgorithmProviderContext`
- size: `327`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a410`
- `0x18002a8bc`
- `0x180048990`

## callees

- `0x18002aa48`
- `0x18002bbd4`
- `0x180046e10`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab28`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180116db0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180116db0`
- `bcrypt!BCryptSetProperty` at `0x180116d7f`
- `bcrypt!BCryptSetProperty` at `0x180116de1`
- `bcrypt!BCryptSetProperty` at `0x180116d7f`
- `bcrypt!BCryptSetProperty` at `0x180116de1`
- `bcrypt!BCryptGetProperty` at `0x18002ab1c`
- `bcrypt!BCryptGetProperty` at `0x18002ab6c`
- `bcrypt!BCryptGetProperty` at `0x18002ab1c`
- `bcrypt!BCryptGetProperty` at `0x18002ab6c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002aade`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002aade`

## pseudocode

```c
__int64 __fastcall CreateCNGAlgorithmProviderContext(int a1, _WORD *a2, int a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  size_t v7; // rbp
  __int64 v8; // rax
  __int64 v9; // rbx
  BCRYPT_HANDLE *v11; // r14
  NTSTATUS Property; // eax
  BCRYPT_HANDLE v13; // rcx
  BCRYPT_HANDLE v14; // rcx
  ULONG pcbResult; // [rsp+68h] [rbp+10h] BYREF
  int pbInput; // [rsp+70h] [rbp+18h] BYREF

  pbInput = a3;
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  v6 = (unsigned int)(2 * v5 + 2);
  v7 = (unsigned int)v6;
  v8 = PkiZeroAlloc(v6 + 48);
  v9 = v8;
  if ( v8 )
  {
    *(_DWORD *)(v8 + 12) = a1;
    *(_QWORD *)(v8 + 16) = v8 + 48;
    *(_DWORD *)(v8 + 8) = 1;
    memcpy_0((void *)(v8 + 48), a2, v7);
    v11 = (BCRYPT_HANDLE *)(v9 + 32);
    *(_DWORD *)(v9 + 24) = pbInput;
    Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(v9 + 32), a2, 0, 0);
    if ( !Property )
    {
      if ( ((a1 - 1) & 0xFFFFFFFD) == 0 )
        return v9;
      v13 = *v11;
      pcbResult = 0;
      Property = BCryptGetProperty(v13, L"ObjectLength", (PUCHAR)(v9 + 40), 4u, &pcbResult, 0);
      if ( !Property )
      {
        if ( a1 == 2 )
        {
          v14 = *v11;
          pcbResult = 0;
          Property = BCryptGetProperty(v14, L"HashDigestLength", (PUCHAR)(v9 + 44), 4u, &pcbResult, 0);
          if ( !Property )
          {
            if ( *(_DWORD *)(v9 + 44) )
              return v9;
            Property = -2147418113;
          }
        }
        else
        {
          if ( a1 != 5 )
            return v9;
          Property = BCryptSetProperty(*v11, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
          if ( !Property )
          {
            if ( CompareStringW(0x409u, 1u, a2, -1, L"RC2", -1) != 2 )
              return v9;
            if ( !pbInput )
              return v9;
            Property = BCryptSetProperty(*v11, L"EffectiveKeyLength", (PUCHAR)&pbInput, 4u, 0);
            if ( !Property )
              return v9;
          }
        }
      }
    }
    SetLastError(Property);
    I_CryptReleaseCNGAlgorithmProvider((HLOCAL)v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002aa48  mov     [rsp+arg_0], rbx
0x18002aa4d  mov     [rsp+pbInput], r8d
0x18002aa52  push    rbp
0x18002aa53  push    rsi
0x18002aa54  push    rdi
0x18002aa55  push    r14
0x18002aa57  push    r15
0x18002aa59  sub     rsp, 30h
0x18002aa5d  xor     r15d, r15d
0x18002aa60  mov     rsi, rdx
0x18002aa63  mov     edi, ecx
0x18002aa65  test    rdx, rdx
0x18002aa68  jz      loc_18002AB87
0x18002aa6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aa72  inc     rax
0x18002aa75  cmp     [rdx+rax*2], r15w
0x18002aa7a  jnz     short loc_18002AA72
0x18002aa7c  lea     eax, ds:2[rax*2]
0x18002aa83  lea     rcx, [rax+30h]; uBytes
0x18002aa87  mov     ebp, eax
0x18002aa89  call    PkiZeroAlloc
0x18002aa8e  mov     rbx, rax
0x18002aa91  test    rax, rax
0x18002aa94  jnz     short loc_18002AAAA
0x18002aa96  mov     rax, rbx
0x18002aa99  mov     rbx, [rsp+58h+arg_0]
0x18002aa9e  add     rsp, 30h
0x18002aaa2  pop     r15
0x18002aaa4  pop     r14
0x18002aaa6  pop     rdi
0x18002aaa7  pop     rsi
0x18002aaa8  pop     rbp
0x18002aaa9  retn
0x18002aaaa  lea     rcx, [rax+30h]; void *
0x18002aaae  mov     [rax+0Ch], edi
0x18002aab1  mov     r8, rbp; Size
0x18002aab4  mov     [rax+10h], rcx
0x18002aab8  mov     rdx, rsi; Src
0x18002aabb  mov     dword ptr [rax+8], 1
0x18002aac2  call    memcpy_0
0x18002aac7  mov     ecx, [rsp+58h+pbInput]
0x18002aacb  lea     r14, [rbx+20h]
0x18002aacf  mov     [rbx+18h], ecx
0x18002aad2  xor     r9d, r9d; dwFlags
0x18002aad5  mov     rcx, r14; phAlgorithm
0x18002aad8  xor     r8d, r8d; pszImplementation
0x18002aadb  mov     rdx, rsi; pszAlgId
0x18002aade  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002aae4  test    eax, eax
0x18002aae6  jnz     short loc_18002AB26
0x18002aae8  lea     eax, [rdi-1]
0x18002aaeb  test    eax, 0FFFFFFFDh
0x18002aaf0  jz      short loc_18002AA96
0x18002aaf2  mov     rcx, [r14]; hObject
0x18002aaf5  lea     rax, [rsp+58h+arg_8]
0x18002aafa  mov     ebp, 4
0x18002aaff  mov     [rsp+58h+dwFlags], r15d; dwFlags
0x18002ab04  mov     r9d, ebp; cbOutput
0x18002ab07  mov     [rsp+58h+arg_8], r15d
0x18002ab0c  lea     r8, [rbx+28h]; pbOutput
0x18002ab10  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18002ab15  lea     rdx, aObjectlength; "ObjectLength"
0x18002ab1c  call    cs:__imp_BCryptGetProperty
0x18002ab22  test    eax, eax
0x18002ab24  jz      short loc_18002AB3E
0x18002ab26  mov     ecx, eax; dwErrCode
0x18002ab28  call    cs:__imp_SetLastError
0x18002ab2e  mov     rcx, rbx; hMem
0x18002ab31  call    I_CryptReleaseCNGAlgorithmProvider
0x18002ab36  mov     rbx, r15
0x18002ab39  jmp     loc_18002AA96
0x18002ab3e  cmp     edi, 2
0x18002ab41  jnz     loc_180116D5C
0x18002ab47  mov     rcx, [r14]; hObject
0x18002ab4a  lea     rax, [rsp+58h+arg_8]
0x18002ab4f  mov     [rsp+58h+dwFlags], r15d; dwFlags
0x18002ab54  lea     r8, [rbx+2Ch]; pbOutput
0x18002ab58  mov     r9d, ebp; cbOutput
0x18002ab5b  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18002ab60  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18002ab67  mov     [rsp+58h+arg_8], r15d
0x18002ab6c  call    cs:__imp_BCryptGetProperty
0x18002ab72  test    eax, eax
0x18002ab74  jnz     short loc_18002AB26
0x18002ab76  cmp     [rbx+2Ch], r15d
0x18002ab7a  jnz     loc_18002AA96
0x18002ab80  mov     eax, 8000FFFFh
0x18002ab85  jmp     short loc_18002AB26
0x18002ab87  mov     eax, r15d
0x18002ab8a  jmp     loc_18002AA7C
0x180116d5c  cmp     edi, 5
0x180116d5f  jnz     loc_18002AA96
0x180116d65  mov     rcx, [r14]; hObject
0x180116d68  lea     r9d, [rdi+1Bh]; cbInput
0x180116d6c  lea     r8, pbInput; "ChainingModeCBC"
0x180116d73  mov     dword ptr [rsp+58h+pcbResult], r15d; dwFlags
0x180116d78  lea     rdx, aChainingmode; "ChainingMode"
0x180116d7f  call    cs:__imp_BCryptSetProperty
0x180116d85  test    eax, eax
0x180116d87  jnz     loc_18002AB26
0x180116d8d  lea     rax, aRc2; "RC2"
0x180116d94  mov     [rsp+58h+dwFlags], 0FFFFFFFFh; cchCount2
0x180116d9c  or      r9d, 0FFFFFFFFh; cchCount1
0x180116da0  mov     [rsp+58h+pcbResult], rax; lpString2
0x180116da5  mov     r8, rsi; lpString1
0x180116da8  lea     edx, [rdi-4]; dwCmpFlags
0x180116dab  mov     ecx, 409h; Locale
0x180116db0  call    cs:__imp_CompareStringW
0x180116db6  cmp     eax, 2
0x180116db9  jnz     loc_18002AA96
0x180116dbf  cmp     [rsp+58h+pbInput], r15d
0x180116dc4  jz      loc_18002AA96
0x180116dca  mov     rcx, [r14]; hObject
0x180116dcd  lea     r8, [rsp+58h+pbInput]; pbInput
0x180116dd2  mov     r9d, ebp; cbInput
0x180116dd5  mov     dword ptr [rsp+58h+pcbResult], r15d; dwFlags
0x180116dda  lea     rdx, aEffectivekeyle; "EffectiveKeyLength"
0x180116de1  call    cs:__imp_BCryptSetProperty
0x180116de7  test    eax, eax
0x180116de9  jz      loc_18002AA96
0x180116def  jmp     loc_18002AB26
```
