# ScHelperCreateCredHMAC

- ea: `0x18007d358`
- end: `0x18007d495`
- name: `ScHelperCreateCredHMAC`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007db08`
- `0x18007de50`

## callees

- `0x18007d358`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007d438`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007d438`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x18007d3e6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x18007d3e6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007d47b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007d47b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d3fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d3fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007d3ac`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007d3ac`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d460`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d460`

## pseudocode

```c
__int64 __fastcall ScHelperCreateCredHMAC(
        HCRYPTPROV a1,
        HCRYPTKEY a2,
        const BYTE *a3,
        DWORD a4,
        BYTE **a5,
        DWORD *pdwDataLen)
{
  unsigned int v8; // edi
  BYTE **v9; // rbx
  DWORD *v10; // rdi
  BYTE *v11; // rax
  int v12; // ebx
  BYTE pbData[16]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+40h] [rbp-20h]
  __int64 v16; // [rsp+50h] [rbp-10h]
  HCRYPTHASH hHash; // [rsp+70h] [rbp+10h] BYREF

  hHash = 0;
  v16 = 0;
  *(_OWORD *)pbData = 0;
  v15 = 0;
  if ( a1 )
  {
    if ( CryptCreateHash(a1, 0x8009u, a2, 0, &hHash)
      && (*(_OWORD *)pbData = 0, v16 = 0, v15 = 0, *(_DWORD *)pbData = 32772, CryptSetHashParam(hHash, 5u, pbData, 0))
      && CryptHashData(hHash, a3, a4, 0)
      && (v9 = a5, v10 = pdwDataLen, CryptGetHashParam(hHash, 2u, *a5, pdwDataLen, 0), *v10) )
    {
      v11 = (BYTE *)LocalAlloc(0x40u, *v10);
      *v9 = v11;
      if ( v11 )
      {
        v12 = 0;
        if ( !CryptGetHashParam(hHash, 2u, v11, v10, 0) )
          v12 = -1073741023;
        v8 = v12;
      }
      else
      {
        v8 = -1073741670;
      }
    }
    else
    {
      v8 = -1073741023;
    }
    if ( hHash )
      CryptDestroyHash(hHash);
  }
  else
  {
    return (unsigned int)-1073741023;
  }
  return v8;
}

```

## disassembly

```asm
0x18007d358  mov     [rsp-8+arg_8], rbx
0x18007d35d  mov     [rsp-8+arg_10], rdi
0x18007d362  push    rbp
0x18007d363  mov     rbp, rsp
0x18007d366  sub     rsp, 60h
0x18007d36a  xor     eax, eax
0x18007d36c  mov     [rbp+hHash], 0
0x18007d374  mov     [rbp+var_10], rax
0x18007d378  xorps   xmm0, xmm0
0x18007d37b  mov     ebx, r9d
0x18007d37e  mov     rdi, r8
0x18007d381  movups  xmmword ptr [rbp+pbData], xmm0
0x18007d385  movups  [rbp+var_20], xmm0
0x18007d389  test    rcx, rcx
0x18007d38c  jnz     short loc_18007D398
0x18007d38e  mov     edi, 0C0000321h
0x18007d393  jmp     loc_18007D481
0x18007d398  lea     rax, [rbp+hHash]
0x18007d39c  mov     r8, rdx; hKey
0x18007d39f  mov     edx, 8009h; Algid
0x18007d3a4  mov     [rsp+60h+phHash], rax; phHash
0x18007d3a9  xor     r9d, r9d; dwFlags
0x18007d3ac  call    cs:__imp_CryptCreateHash
0x18007d3b2  test    eax, eax
0x18007d3b4  jnz     short loc_18007D3C0
0x18007d3b6  mov     edi, 0C0000321h
0x18007d3bb  jmp     loc_18007D472
0x18007d3c0  mov     rcx, [rbp+hHash]; hHash
0x18007d3c4  lea     r8, [rbp+pbData]; pbData
0x18007d3c8  xor     eax, eax
0x18007d3ca  xorps   xmm0, xmm0
0x18007d3cd  movups  xmmword ptr [rbp+pbData], xmm0
0x18007d3d1  xor     r9d, r9d; dwFlags
0x18007d3d4  mov     [rbp+var_10], rax
0x18007d3d8  movups  [rbp+var_20], xmm0
0x18007d3dc  lea     edx, [rax+5]; dwParam
0x18007d3df  mov     dword ptr [rbp+pbData], 8004h
0x18007d3e6  call    cs:__imp_CryptSetHashParam
0x18007d3ec  test    eax, eax
0x18007d3ee  jz      short loc_18007D3B6
0x18007d3f0  mov     rcx, [rbp+hHash]; hHash
0x18007d3f4  xor     r9d, r9d; dwFlags
0x18007d3f7  mov     r8d, ebx; dwDataLen
0x18007d3fa  mov     rdx, rdi; pbData
0x18007d3fd  call    cs:__imp_CryptHashData
0x18007d403  test    eax, eax
0x18007d405  jz      short loc_18007D3B6
0x18007d407  mov     rbx, [rbp+arg_20]
0x18007d40b  mov     edx, 2; dwParam
0x18007d410  mov     rdi, [rbp+pdwDataLen]
0x18007d414  mov     rcx, [rbp+hHash]; hHash
0x18007d418  mov     r9, rdi; pdwDataLen
0x18007d41b  mov     dword ptr [rsp+60h+phHash], 0; dwFlags
0x18007d423  mov     r8, [rbx]; pbData
0x18007d426  call    cs:__imp_CryptGetHashParam
0x18007d42c  cmp     dword ptr [rdi], 0
0x18007d42f  jbe     short loc_18007D3B6
0x18007d431  mov     edx, [rdi]; uBytes
0x18007d433  mov     ecx, 40h ; '@'; uFlags
0x18007d438  call    cs:__imp_LocalAlloc
0x18007d43e  mov     [rbx], rax
0x18007d441  test    rax, rax
0x18007d444  jnz     short loc_18007D44D
0x18007d446  mov     edi, 0C000009Ah
0x18007d44b  jmp     short loc_18007D472
0x18007d44d  mov     rcx, [rbp+hHash]; hHash
0x18007d451  xor     ebx, ebx
0x18007d453  mov     r9, rdi; pdwDataLen
0x18007d456  mov     dword ptr [rsp+60h+phHash], ebx; dwFlags
0x18007d45a  mov     r8, rax; pbData
0x18007d45d  lea     edx, [rbx+2]; dwParam
0x18007d460  call    cs:__imp_CryptGetHashParam
0x18007d466  mov     edi, 0C0000321h
0x18007d46b  test    eax, eax
0x18007d46d  cmovz   ebx, edi
0x18007d470  mov     edi, ebx
0x18007d472  mov     rcx, [rbp+hHash]; hHash
0x18007d476  test    rcx, rcx
0x18007d479  jz      short loc_18007D481
0x18007d47b  call    cs:__imp_CryptDestroyHash
0x18007d481  lea     r11, [rsp+60h+var_s0]
0x18007d486  mov     eax, edi
0x18007d488  mov     rbx, [r11+18h]
0x18007d48c  mov     rdi, [r11+20h]
0x18007d490  mov     rsp, r11
0x18007d493  pop     rbp
0x18007d494  retn
```
