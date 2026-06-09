# SipCryptProvider::GetAlgId(char const *,ulong *)

- ea: `0x180003ba0`
- end: `0x180003c67`
- name: `?GetAlgId@SipCryptProvider@@QEAAKPEBDPEAK@Z`
- size: `199`
- prototype: `unsigned int(SipCryptProvider *__hidden this, const char *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dd4`
- `0x180003ed8`

## callees

- `0x180003ba0`
- `0x1800054ba`

## import_xrefs

- `CRYPT32!CryptFindOIDInfo` at `0x180003bee`
- `CRYPT32!CryptFindOIDInfo` at `0x180003bee`
- `CRYPT32!CertOIDToAlgId` at `0x180003bd3`
- `CRYPT32!CertOIDToAlgId` at `0x180003bd3`

## pseudocode

```c
__int64 __fastcall SipCryptProvider::GetAlgId(SipCryptProvider *this, CHAR *a2, unsigned int *a3)
{
  __int64 result; // rax
  DWORD v6; // eax
  unsigned int v7; // ebx
  PCCRYPT_OID_INFO OIDInfo; // rax
  PCCRYPT_OID_INFO v9; // rdi

  if ( !a3 )
    return 87;
  *a3 = 0;
  if ( !a2 )
    return 87;
  v6 = CertOIDToAlgId(a2);
  v7 = v6;
  if ( !v6 )
    return 87;
  if ( v6 == -1 )
  {
    OIDInfo = CryptFindOIDInfo(1u, a2, 0);
    v9 = OIDInfo;
    if ( !OIDInfo )
      return 2148073480LL;
    if ( !wcscmp_0(*(const wchar_t **)&OIDInfo[1].cbSize, L"SHA256") )
    {
      v7 = 32780;
    }
    else if ( !wcscmp_0(*(const wchar_t **)&v9[1].cbSize, L"SHA384") )
    {
      v7 = 32781;
    }
    else if ( !wcscmp_0(*(const wchar_t **)&v9[1].cbSize, L"SHA512") )
    {
      v7 = 32782;
    }
  }
  result = 0;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x180003ba0  mov     [rsp+arg_0], rbx
0x180003ba5  mov     [rsp+arg_8], rsi
0x180003baa  push    rdi
0x180003bab  sub     rsp, 20h
0x180003baf  mov     rsi, r8
0x180003bb2  mov     rdi, rdx
0x180003bb5  test    r8, r8
0x180003bb8  jnz     short loc_180003BC4
0x180003bba  mov     eax, 57h ; 'W'
0x180003bbf  jmp     loc_180003C57
0x180003bc4  mov     dword ptr [r8], 0
0x180003bcb  test    rdi, rdi
0x180003bce  jz      short loc_180003BBA
0x180003bd0  mov     rcx, rdi; pszObjId
0x180003bd3  call    cs:__imp_CertOIDToAlgId
0x180003bd9  mov     ebx, eax
0x180003bdb  test    eax, eax
0x180003bdd  jz      short loc_180003BBA
0x180003bdf  cmp     eax, 0FFFFFFFFh
0x180003be2  jnz     short loc_180003C53
0x180003be4  xor     r8d, r8d; dwGroupId
0x180003be7  mov     rdx, rdi; pvKey
0x180003bea  lea     ecx, [r8+1]; dwKeyType
0x180003bee  call    cs:__imp_CryptFindOIDInfo
0x180003bf4  mov     rdi, rax
0x180003bf7  test    rax, rax
0x180003bfa  jnz     short loc_180003C03
0x180003bfc  mov     eax, 80090008h
0x180003c01  jmp     short loc_180003C57
0x180003c03  mov     rcx, [rax+30h]; String1
0x180003c07  lea     rdx, aSha256; "SHA256"
0x180003c0e  call    wcscmp_0
0x180003c13  test    eax, eax
0x180003c15  jnz     short loc_180003C1E
0x180003c17  mov     ebx, 800Ch
0x180003c1c  jmp     short loc_180003C53
0x180003c1e  mov     rcx, [rdi+30h]; String1
0x180003c22  lea     rdx, aSha384; "SHA384"
0x180003c29  call    wcscmp_0
0x180003c2e  test    eax, eax
0x180003c30  jnz     short loc_180003C39
0x180003c32  mov     ebx, 800Dh
0x180003c37  jmp     short loc_180003C53
0x180003c39  mov     rcx, [rdi+30h]; String1
0x180003c3d  lea     rdx, aSha512; "SHA512"
0x180003c44  call    wcscmp_0
0x180003c49  test    eax, eax
0x180003c4b  mov     ecx, 800Eh
0x180003c50  cmovz   ebx, ecx
0x180003c53  xor     eax, eax
0x180003c55  mov     [rsi], ebx
0x180003c57  mov     rbx, [rsp+28h+arg_0]
0x180003c5c  mov     rsi, [rsp+28h+arg_8]
0x180003c61  add     rsp, 20h
0x180003c65  pop     rdi
0x180003c66  retn
```
