# GetTextualSidW

- ea: `0x180026a08`
- end: `0x180026c50`
- name: `GetTextualSidW`
- size: `584`
- prototype: `__int64 __fastcall(PSID pSid, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002529c`

## callees

- `0x1800093ec`
- `0x18000af80`
- `0x18000b250`
- `0x180026a08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180026a8c`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180026a8c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026a25`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026a25`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180026beb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180026beb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180026a9e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180026a9e`

## string_xrefs

- `0x180026a60`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180026afb`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall GetTextualSidW(PSID pSid, STRSAFE_LPWSTR pszDest, size_t cchDest, unsigned int *a4)
{
  size_t v5; // rbp
  int v8; // edx
  unsigned int v9; // ebx
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rdi
  DWORD v11; // r12d
  unsigned int v12; // ecx
  HRESULT v13; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rbx
  DWORD i; // edi
  PDWORD SidSubAuthority; // rax

  v5 = (unsigned int)cchDest;
  if ( IsValidSid(pSid) )
  {
    SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
    v11 = *GetSidSubAuthorityCount(pSid);
    v12 = 24 * v11 + 56;
    if ( !pszDest )
    {
      *a4 = v12;
      return 0;
    }
    if ( (unsigned int)v5 < v12 )
    {
      *a4 = v12;
      return 122;
    }
    v13 = StringCchPrintfW(pszDest, v5, L"S-%lu-", 1);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 2219;
LABEL_11:
      DebugTraceError((unsigned int)v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v14);
      return v9;
    }
    v15 = -1;
    do
      ++v15;
    while ( pszDest[v15] );
    if ( *(_WORD *)SidIdentifierAuthority->Value )
    {
      v13 = StringCchPrintfW(
              &pszDest[(unsigned int)v15],
              (unsigned int)(v5 - v15),
              L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
              SidIdentifierAuthority->Value[0],
              SidIdentifierAuthority->Value[1],
              SidIdentifierAuthority->Value[2],
              SidIdentifierAuthority->Value[3],
              SidIdentifierAuthority->Value[4],
              SidIdentifierAuthority->Value[5]);
      v9 = v13;
      if ( v13 < 0 )
      {
        v14 = 2241;
        goto LABEL_11;
      }
    }
    else
    {
      v13 = StringCchPrintfW(
              &pszDest[(unsigned int)v15],
              (unsigned int)(v5 - v15),
              L"%lu",
              SidIdentifierAuthority->Value[5]
            + (SidIdentifierAuthority->Value[4] << 8)
            + (SidIdentifierAuthority->Value[3] << 16)
            + (SidIdentifierAuthority->Value[2] << 24));
      v9 = v13;
      if ( v13 < 0 )
      {
        v14 = 2257;
        goto LABEL_11;
      }
    }
    v16 = -1;
    do
      ++v16;
    while ( pszDest[v16] );
    for ( i = 0; i < v11; ++i )
    {
      SidSubAuthority = GetSidSubAuthority(pSid, i);
      v13 = StringCchPrintfW(&pszDest[(unsigned int)v16], (unsigned int)(v5 - v16), L"-%lu", *SidSubAuthority);
      v9 = v13;
      if ( v13 < 0 )
      {
        v14 = 2275;
        goto LABEL_11;
      }
      v16 = -1;
      do
        ++v16;
      while ( pszDest[v16] );
    }
    *a4 = v16 + 1;
    return 0;
  }
  v9 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
      (unsigned int)"Status",
      87,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
      130);
  return v9;
}

```

## disassembly

```asm
0x180026a08  push    rbx
0x180026a0a  push    rbp
0x180026a0b  push    rsi
0x180026a0c  push    rdi
0x180026a0d  push    r12
0x180026a0f  push    r13
0x180026a11  push    r14
0x180026a13  push    r15
0x180026a15  sub     rsp, 58h
0x180026a19  mov     r14, r9
0x180026a1c  mov     ebp, r8d
0x180026a1f  mov     rsi, rdx
0x180026a22  mov     r15, rcx
0x180026a25  call    cs:__imp_IsValidSid
0x180026a2c  nop     dword ptr [rax+rax+00h]
0x180026a31  xor     r13d, r13d
0x180026a34  test    eax, eax
0x180026a36  jnz     short loc_180026A89
0x180026a38  lea     ebx, [rax+57h]
0x180026a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a42  lea     rax, WPP_GLOBAL_Control
0x180026a49  cmp     rcx, rax
0x180026a4c  jz      loc_180026C3C
0x180026a52  test    byte ptr [rcx+1Ch], 1
0x180026a56  jz      loc_180026C3C
0x180026a5c  mov     rcx, [rcx+10h]
0x180026a60  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180026a67  mov     [rsp+98h+var_68], 882h
0x180026a6f  lea     r9, aStatus; "Status"
0x180026a76  mov     [rsp+98h+var_70], r8
0x180026a7b  mov     [rsp+98h+var_78], ebx
0x180026a7f  call    WPP_SF_sDsd
0x180026a84  jmp     loc_180026C3C
0x180026a89  mov     rcx, r15; pSid
0x180026a8c  call    cs:__imp_GetSidIdentifierAuthority
0x180026a93  nop     dword ptr [rax+rax+00h]
0x180026a98  mov     rcx, r15; pSid
0x180026a9b  mov     rdi, rax
0x180026a9e  call    cs:__imp_GetSidSubAuthorityCount
0x180026aa5  nop     dword ptr [rax+rax+00h]
0x180026aaa  movzx   r12d, byte ptr [rax]
0x180026aae  lea     ecx, [r12+r12*2]
0x180026ab2  lea     ecx, ds:38h[rcx*8]
0x180026ab9  test    rsi, rsi
0x180026abc  jnz     short loc_180026AC6
0x180026abe  mov     [r14], ecx
0x180026ac1  jmp     loc_180026C39
0x180026ac6  cmp     ebp, ecx
0x180026ac8  jnb     short loc_180026AD7
0x180026aca  mov     [r14], ecx
0x180026acd  mov     ebx, 7Ah ; 'z'
0x180026ad2  jmp     loc_180026C3C
0x180026ad7  mov     rdx, rbp; cchDest
0x180026ada  lea     r8, aSLu; "S-%lu-"
0x180026ae1  mov     r9d, 1
0x180026ae7  mov     rcx, rsi; pszDest
0x180026aea  call    StringCchPrintfW
0x180026aef  mov     ebx, eax
0x180026af1  test    eax, eax
0x180026af3  jns     short loc_180026B15
0x180026af5  mov     r9d, 8ABh
0x180026afb  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180026b02  mov     ecx, eax
0x180026b04  lea     rdx, aStatus; "Status"
0x180026b0b  call    DebugTraceError
0x180026b10  jmp     loc_180026C3C
0x180026b15  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026b19  inc     rcx
0x180026b1c  cmp     [rsi+rcx*2], r13w
0x180026b21  jnz     short loc_180026B19
0x180026b23  movzx   eax, byte ptr [rdi]
0x180026b26  test    al, al
0x180026b28  jnz     short loc_180026B78
0x180026b2a  cmp     [rdi+1], r13b
0x180026b2e  jnz     short loc_180026B78
0x180026b30  movzx   eax, byte ptr [rdi+3]
0x180026b34  lea     r8, aLu_0; "%lu"
0x180026b3b  movzx   r9d, byte ptr [rdi+2]
0x180026b40  mov     edx, ebp
0x180026b42  shl     eax, 10h
0x180026b45  sub     edx, ecx; cchDest
0x180026b47  shl     r9d, 18h
0x180026b4b  add     r9d, eax
0x180026b4e  movzx   eax, byte ptr [rdi+4]
0x180026b52  shl     eax, 8
0x180026b55  add     r9d, eax
0x180026b58  movzx   eax, byte ptr [rdi+5]
0x180026b5c  add     r9d, eax
0x180026b5f  mov     eax, ecx
0x180026b61  lea     rcx, [rsi+rax*2]; pszDest
0x180026b65  call    StringCchPrintfW
0x180026b6a  mov     ebx, eax
0x180026b6c  test    eax, eax
0x180026b6e  jns     short loc_180026BD0
0x180026b70  mov     r9d, 8D1h
0x180026b76  jmp     short loc_180026AFB
0x180026b78  movzx   r8d, byte ptr [rdi+5]
0x180026b7d  mov     r9d, eax
0x180026b80  movzx   r10d, byte ptr [rdi+4]
0x180026b85  mov     edx, ebp
0x180026b87  movzx   r11d, byte ptr [rdi+3]
0x180026b8c  sub     edx, ecx; cchDest
0x180026b8e  movzx   ebx, byte ptr [rdi+2]
0x180026b92  movzx   edi, byte ptr [rdi+1]
0x180026b96  mov     [rsp+98h+var_58], r8d
0x180026b9b  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x180026ba2  mov     [rsp+98h+var_60], r10d
0x180026ba7  mov     [rsp+98h+var_68], r11d
0x180026bac  mov     eax, ecx
0x180026bae  mov     dword ptr [rsp+98h+var_70], ebx
0x180026bb2  mov     [rsp+98h+var_78], edi
0x180026bb6  lea     rcx, [rsi+rax*2]; pszDest
0x180026bba  call    StringCchPrintfW
0x180026bbf  mov     ebx, eax
0x180026bc1  test    eax, eax
0x180026bc3  jns     short loc_180026BD0
0x180026bc5  mov     r9d, 8C1h
0x180026bcb  jmp     loc_180026AFB
0x180026bd0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026bd4  inc     rbx
0x180026bd7  cmp     [rsi+rbx*2], r13w
0x180026bdc  jnz     short loc_180026BD4
0x180026bde  mov     edi, r13d
0x180026be1  cmp     edi, r12d
0x180026be4  jnb     short loc_180026C33
0x180026be6  mov     edx, edi; nSubAuthority
0x180026be8  mov     rcx, r15; pSid
0x180026beb  call    cs:__imp_GetSidSubAuthority
0x180026bf2  nop     dword ptr [rax+rax+00h]
0x180026bf7  mov     edx, ebp
0x180026bf9  mov     ecx, ebx
0x180026bfb  sub     edx, ebx; cchDest
0x180026bfd  lea     r8, aLu; "-%lu"
0x180026c04  mov     r9d, [rax]
0x180026c07  lea     rcx, [rsi+rcx*2]; pszDest
0x180026c0b  call    StringCchPrintfW
0x180026c10  mov     ebx, eax
0x180026c12  test    eax, eax
0x180026c14  js      short loc_180026C28
0x180026c16  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026c1a  inc     rbx
0x180026c1d  cmp     [rsi+rbx*2], r13w
0x180026c22  jnz     short loc_180026C1A
0x180026c24  inc     edi
0x180026c26  jmp     short loc_180026BE1
0x180026c28  mov     r9d, 8E3h
0x180026c2e  jmp     loc_180026AFB
0x180026c33  lea     eax, [rbx+1]
0x180026c36  mov     [r14], eax
0x180026c39  mov     ebx, r13d
0x180026c3c  mov     eax, ebx
0x180026c3e  add     rsp, 58h
0x180026c42  pop     r15
0x180026c44  pop     r14
0x180026c46  pop     r13
0x180026c48  pop     r12
0x180026c4a  pop     rdi
0x180026c4b  pop     rsi
0x180026c4c  pop     rbp
0x180026c4d  pop     rbx
0x180026c4e  retn
```
