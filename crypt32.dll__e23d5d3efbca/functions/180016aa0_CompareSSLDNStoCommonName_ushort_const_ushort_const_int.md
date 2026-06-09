# CompareSSLDNStoCommonName(ushort const *,ushort const *,int)

- ea: `0x180016aa0`
- end: `0x180016d56`
- name: `?CompareSSLDNStoCommonName@@YAHPEBG0H@Z`
- size: `694`
- prototype: `__int64 __fastcall(PCWSTR AddressString, PCNZWCH lpString2, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800169cc`
- `0x180016aa0`
- `0x180017588`

## callees

- `0x180016aa0`
- `0x180016d5c`
- `0x180028d60`
- `0x1800781a0`
- `0x1800783f4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016b2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016c2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016b2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016c2a`
- `ntdll!wcsstr` at `0x180016b68`
- `ntdll!wcsstr` at `0x180016b7b`
- `ntdll!wcsstr` at `0x180016b68`
- `ntdll!wcsstr` at `0x180016b7b`
- `ntdll!wcschr` at `0x180016b00`
- `ntdll!wcschr` at `0x180016bbb`
- `ntdll!wcschr` at `0x180016bd2`
- `ntdll!wcschr` at `0x180016be7`
- `ntdll!wcschr` at `0x180016b00`
- `ntdll!wcschr` at `0x180016bbb`
- `ntdll!wcschr` at `0x180016bd2`
- `ntdll!wcschr` at `0x180016be7`

## pseudocode

```c
__int64 __fastcall CompareSSLDNStoCommonName(PCWSTR AddressString, PCNZWCH lpString2, int a3)
{
  const WCHAR *v4; // rbx
  const WCHAR *v5; // rdi
  WCHAR *v6; // r15
  WCHAR *v7; // r14
  const wchar_t *v8; // r12
  wchar_t *v9; // rbp
  unsigned int v10; // edi
  wchar_t *v11; // rbx
  wchar_t *v12; // rax
  wchar_t *v14; // rax
  unsigned __int64 v15; // rsi
  unsigned int v16; // r13d
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  int v21; // [rsp+80h] [rbp+8h]
  PCNZWCH v22; // [rsp+88h] [rbp+10h] BYREF
  int v23; // [rsp+90h] [rbp+18h]
  WCHAR *v24; // [rsp+98h] [rbp+20h] BYREF

  v23 = a3;
  v24 = 0;
  v4 = lpString2;
  v22 = 0;
  v5 = AddressString;
  v6 = 0;
  v7 = 0;
  if ( !AddressString || !*AddressString || !lpString2 || !*lpString2 )
    goto LABEL_36;
  if ( !wcschr(lpString2, 0x2Au) )
  {
    if ( CompareStringW(0x400u, 1u, v5, -1, v4, -1) == 2 )
      return 1;
    v8 = v5;
    v9 = (wchar_t *)v4;
    goto LABEL_9;
  }
  if ( (unsigned int)IsIpAddress(v5) )
    goto LABEL_36;
  v14 = wcschr(v4, 0x2Au);
  v15 = (unsigned __int64)v14;
  if ( v14 )
  {
    if ( wcschr(v14 + 1, 0x2Au)
      || v15 > (unsigned __int64)wcschr(v4, 0x2Eu)
      || a3 && ((const WCHAR *)v15 != v4 || *(_WORD *)(v15 + 2) != 46) )
    {
      goto LABEL_36;
    }
  }
  v8 = v5;
  v16 = 1;
  v21 = 1;
  v9 = (wchar_t *)v4;
  while ( 1 )
  {
    v17 = CompareStringW(0x400u, 1u, v5, 1, v4, 1);
    if ( v17 != 2 && *v4 != 42 )
      break;
    if ( !*v5 )
      goto LABEL_32;
    if ( !*v4 )
      goto LABEL_9;
    v18 = v21;
    if ( v17 != 2 )
      v18 = 0;
    v21 = v18;
    if ( *v4 == 42 )
    {
      v16 = 0;
      if ( *v5 == 46 )
        goto LABEL_31;
      ++v5;
    }
    else
    {
      if ( *v5 == 46 )
        ++v16;
      ++v5;
LABEL_31:
      ++v4;
    }
  }
  if ( *v5 )
    goto LABEL_9;
LABEL_32:
  if ( !*v4 && (v16 >= 2 || v21) )
    return 1;
LABEL_9:
  v10 = 0;
  if ( !v23 )
  {
    v11 = wcsstr(v9, L"xn--");
    v12 = wcsstr(v8, L"xn--");
    if ( v11 )
    {
      if ( !v12 )
      {
        v20 = I_ConvertIdnHostNameTokenToAsciiOrUnicode(1, v8, &v24);
        v6 = v24;
        if ( !v20 )
          goto LABEL_36;
        v8 = v24;
      }
    }
    else
    {
      if ( !v12 )
        return v10;
      v19 = I_ConvertIdnHostNameToAsciiOrUnicode(1u, v9, (unsigned __int16 **)&v22);
      v7 = (WCHAR *)v22;
      if ( !v19 )
      {
LABEL_36:
        v10 = 0;
        goto LABEL_37;
      }
      v9 = (wchar_t *)v22;
    }
    v10 = CompareSSLDNStoCommonName(v8, v9, 1);
LABEL_37:
    if ( v7 )
      PkiDefaultCryptFree(v7);
    if ( v6 )
      PkiDefaultCryptFree(v6);
  }
  return v10;
}

```

## disassembly

```asm
0x180016aa0  mov     rax, rsp
0x180016aa3  mov     [rax+18h], r8d
0x180016aa7  push    rbx
0x180016aa8  push    rbp
0x180016aa9  push    rsi
0x180016aaa  push    rdi
0x180016aab  push    r12
0x180016aad  push    r13
0x180016aaf  push    r14
0x180016ab1  push    r15
0x180016ab3  sub     rsp, 38h
0x180016ab7  xor     r13d, r13d
0x180016aba  mov     r12d, r8d
0x180016abd  mov     [rax+20h], r13
0x180016ac1  mov     rbx, rdx
0x180016ac4  mov     [rax+10h], r13
0x180016ac8  mov     rdi, rcx
0x180016acb  mov     r15d, r13d
0x180016ace  mov     r14d, r13d
0x180016ad1  test    rcx, rcx
0x180016ad4  jz      loc_180016CCF
0x180016ada  cmp     r13w, [rcx]
0x180016ade  jz      loc_180016CCF
0x180016ae4  test    rdx, rdx
0x180016ae7  jz      loc_180016CCF
0x180016aed  cmp     r13w, [rdx]
0x180016af1  jz      loc_180016CCF
0x180016af7  lea     esi, [r13+2Ah]
0x180016afb  mov     rcx, rbx; Str
0x180016afe  mov     edx, esi; Ch
0x180016b00  call    cs:__imp_wcschr
0x180016b06  test    rax, rax
0x180016b09  jnz     loc_180016BA6
0x180016b0f  or      r9d, 0FFFFFFFFh; cchCount1
0x180016b13  lea     esi, [rax+1]
0x180016b16  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180016b1b  mov     edx, esi; dwCmpFlags
0x180016b1d  mov     r8, rdi; lpString1
0x180016b20  mov     [rsp+78h+lpString2], rbx; lpString2
0x180016b25  mov     ecx, 400h; Locale
0x180016b2a  call    cs:__imp_CompareStringW
0x180016b30  cmp     eax, 2
0x180016b33  jz      loc_180016CAA
0x180016b39  mov     r12, rdi
0x180016b3c  mov     rbp, rbx
0x180016b3f  jmp     short loc_180016B51
0x180016b41  xor     r8d, r8d
0x180016b44  cmp     [rdi], r8w
0x180016b48  jz      loc_180016C9A
0x180016b4e  xor     r13d, r13d
0x180016b51  mov     edi, r13d
0x180016b54  cmp     [rsp+78h+arg_10], r13d
0x180016b5c  jnz     short loc_180016B93
0x180016b5e  lea     rdx, aXn; "xn--"
0x180016b65  mov     rcx, rbp; Str
0x180016b68  call    cs:__imp_wcsstr
0x180016b6e  lea     rdx, aXn; "xn--"
0x180016b75  mov     rcx, r12; Str
0x180016b78  mov     rbx, rax
0x180016b7b  call    cs:__imp_wcsstr
0x180016b81  test    rbx, rbx
0x180016b84  jnz     loc_180016D1D
0x180016b8a  test    rax, rax
0x180016b8d  jnz     loc_180016CB1
0x180016b93  mov     eax, edi
0x180016b95  add     rsp, 38h
0x180016b99  pop     r15
0x180016b9b  pop     r14
0x180016b9d  pop     r13
0x180016b9f  pop     r12
0x180016ba1  pop     rdi
0x180016ba2  pop     rsi
0x180016ba3  pop     rbp
0x180016ba4  pop     rbx
0x180016ba5  retn
0x180016ba6  mov     rcx, rdi; AddressString
0x180016ba9  call    IsIpAddress
0x180016bae  test    eax, eax
0x180016bb0  jnz     loc_180016CCF
0x180016bb6  mov     edx, esi; Ch
0x180016bb8  mov     rcx, rbx; Str
0x180016bbb  call    cs:__imp_wcschr
0x180016bc1  mov     rsi, rax
0x180016bc4  test    rax, rax
0x180016bc7  jz      short loc_180016BFF
0x180016bc9  mov     edx, 2Ah ; '*'; Ch
0x180016bce  lea     rcx, [rax+2]; Str
0x180016bd2  call    cs:__imp_wcschr
0x180016bd8  test    rax, rax
0x180016bdb  jnz     loc_180016CCF
0x180016be1  lea     edx, [rax+2Eh]; Ch
0x180016be4  mov     rcx, rbx; Str
0x180016be7  call    cs:__imp_wcschr
0x180016bed  cmp     rsi, rax
0x180016bf0  ja      loc_180016CCF
0x180016bf6  test    r12d, r12d
0x180016bf9  jnz     loc_180016D00
0x180016bff  mov     esi, 1
0x180016c04  mov     r12, rdi
0x180016c07  mov     r13d, esi
0x180016c0a  mov     [rsp+78h+arg_0], esi
0x180016c11  mov     rbp, rbx
0x180016c14  mov     [rsp+78h+cchCount2], esi; cchCount2
0x180016c18  mov     r9d, esi; cchCount1
0x180016c1b  mov     r8, rdi; lpString1
0x180016c1e  mov     [rsp+78h+lpString2], rbx; lpString2
0x180016c23  mov     edx, esi; dwCmpFlags
0x180016c25  mov     ecx, 400h; Locale
0x180016c2a  call    cs:__imp_CompareStringW
0x180016c30  mov     r9d, 2Ah ; '*'
0x180016c36  cmp     eax, 2
0x180016c39  jz      short loc_180016C45
0x180016c3b  cmp     [rbx], r9w
0x180016c3f  jnz     loc_180016B41
0x180016c45  xor     r8d, r8d
0x180016c48  cmp     [rdi], r8w
0x180016c4c  jz      short loc_180016C9A
0x180016c4e  cmp     [rbx], r8w
0x180016c52  jz      loc_180016B4E
0x180016c58  mov     ecx, [rsp+78h+arg_0]
0x180016c5f  cmp     eax, 2
0x180016c62  lea     eax, [r8+2Eh]
0x180016c66  cmovnz  ecx, r8d
0x180016c6a  mov     [rsp+78h+arg_0], ecx
0x180016c71  cmp     [rbx], r9w
0x180016c75  jnz     short loc_180016C85
0x180016c77  mov     r13d, r8d
0x180016c7a  cmp     [rdi], ax
0x180016c7d  jz      short loc_180016C91
0x180016c7f  add     rdi, 2
0x180016c83  jmp     short loc_180016C14
0x180016c85  cmp     [rdi], ax
0x180016c88  jnz     short loc_180016C8D
0x180016c8a  add     r13d, esi
0x180016c8d  add     rdi, 2
0x180016c91  add     rbx, 2
0x180016c95  jmp     loc_180016C14
0x180016c9a  cmp     [rbx], r8w
0x180016c9e  jnz     loc_180016B4E
0x180016ca4  cmp     r13d, 2
0x180016ca8  jb      short loc_180016CED
0x180016caa  mov     edi, esi
0x180016cac  jmp     loc_180016B93
0x180016cb1  lea     r8, [rsp+78h+arg_8]
0x180016cb9  mov     rdx, rbp
0x180016cbc  mov     ecx, esi
0x180016cbe  call    I_ConvertIdnHostNameToAsciiOrUnicode
0x180016cc3  mov     r14, [rsp+78h+arg_8]
0x180016ccb  test    eax, eax
0x180016ccd  jnz     short loc_180016D15
0x180016ccf  mov     edi, r13d
0x180016cd2  test    r14, r14
0x180016cd5  jnz     short loc_180016D4C
0x180016cd7  test    r15, r15
0x180016cda  jz      loc_180016B93
0x180016ce0  mov     rcx, r15; hMem
0x180016ce3  call    PkiDefaultCryptFree
0x180016ce8  jmp     loc_180016B93
0x180016ced  xor     r13d, r13d
0x180016cf0  cmp     [rsp+78h+arg_0], r13d
0x180016cf8  jz      loc_180016B51
0x180016cfe  jmp     short loc_180016CAA
0x180016d00  cmp     rsi, rbx
0x180016d03  jnz     short loc_180016CCF
0x180016d05  mov     eax, 2Eh ; '.'
0x180016d0a  cmp     [rsi+2], ax
0x180016d0e  jnz     short loc_180016CCF
0x180016d10  jmp     loc_180016BFF
0x180016d15  mov     rbp, r14
0x180016d18  jmp     loc_180115AC0
0x180016d1d  test    rax, rax
0x180016d20  jnz     loc_180115AC0
0x180016d26  lea     r8, [rsp+78h+arg_18]
0x180016d2e  mov     rdx, r12
0x180016d31  mov     ecx, esi
0x180016d33  call    I_ConvertIdnHostNameTokenToAsciiOrUnicode
0x180016d38  mov     r15, [rsp+78h+arg_18]
0x180016d40  test    eax, eax
0x180016d42  jz      short loc_180016CCF
0x180016d44  mov     r12, r15
0x180016d47  jmp     loc_180115AC0
0x180016d4c  mov     rcx, r14; hMem
0x180016d4f  call    PkiDefaultCryptFree
0x180016d54  jmp     short loc_180016CD7
0x180115ac0  mov     r8d, esi; int
0x180115ac3  mov     rdx, rbp; lpString2
0x180115ac6  mov     rcx, r12; AddressString
0x180115ac9  call    ?CompareSSLDNStoCommonName@@YAHPEBG0H@Z; CompareSSLDNStoCommonName(ushort const *,ushort const *,int)
0x180115ace  mov     edi, eax
0x180115ad0  jmp     loc_180016CD2
```
