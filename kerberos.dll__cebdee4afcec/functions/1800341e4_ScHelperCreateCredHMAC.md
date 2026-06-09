# ScHelperCreateCredHMAC

- ea: `0x1800341e4`
- end: `0x180034321`
- name: `ScHelperCreateCredHMAC`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800d71e8`
- `0x1800d78e0`

## callees

- `0x1800341e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800342c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800342c4`
- `CRYPTSP!CryptCreateHash` at `0x180034238`
- `CRYPTSP!CryptCreateHash` at `0x180034238`
- `CRYPTSP!CryptHashData` at `0x180034289`
- `CRYPTSP!CryptHashData` at `0x180034289`
- `CRYPTSP!CryptSetHashParam` at `0x180034272`
- `CRYPTSP!CryptSetHashParam` at `0x180034272`
- `CRYPTSP!CryptDestroyHash` at `0x180034307`
- `CRYPTSP!CryptDestroyHash` at `0x180034307`
- `CRYPTSP!CryptGetHashParam` at `0x1800342b2`
- `CRYPTSP!CryptGetHashParam` at `0x1800342ec`
- `CRYPTSP!CryptGetHashParam` at `0x1800342b2`
- `CRYPTSP!CryptGetHashParam` at `0x1800342ec`

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
0x1800341e4  mov     [rsp-8+arg_8], rbx
0x1800341e9  mov     [rsp-8+arg_10], rdi
0x1800341ee  push    rbp
0x1800341ef  mov     rbp, rsp
0x1800341f2  sub     rsp, 60h
0x1800341f6  xor     eax, eax
0x1800341f8  mov     [rbp+hHash], 0
0x180034200  mov     [rbp+var_10], rax
0x180034204  xorps   xmm0, xmm0
0x180034207  mov     ebx, r9d
0x18003420a  mov     rdi, r8
0x18003420d  movups  xmmword ptr [rbp+pbData], xmm0
0x180034211  movups  [rbp+var_20], xmm0
0x180034215  test    rcx, rcx
0x180034218  jnz     short loc_180034224
0x18003421a  mov     edi, 0C0000321h
0x18003421f  jmp     loc_18003430D
0x180034224  lea     rax, [rbp+hHash]
0x180034228  mov     r8, rdx; hKey
0x18003422b  mov     edx, 8009h; Algid
0x180034230  mov     [rsp+60h+phHash], rax; phHash
0x180034235  xor     r9d, r9d; dwFlags
0x180034238  call    cs:__imp_CryptCreateHash
0x18003423e  test    eax, eax
0x180034240  jnz     short loc_18003424C
0x180034242  mov     edi, 0C0000321h
0x180034247  jmp     loc_1800342FE
0x18003424c  mov     rcx, [rbp+hHash]; hHash
0x180034250  lea     r8, [rbp+pbData]; pbData
0x180034254  xor     eax, eax
0x180034256  xorps   xmm0, xmm0
0x180034259  movups  xmmword ptr [rbp+pbData], xmm0
0x18003425d  xor     r9d, r9d; dwFlags
0x180034260  mov     [rbp+var_10], rax
0x180034264  movups  [rbp+var_20], xmm0
0x180034268  lea     edx, [rax+5]; dwParam
0x18003426b  mov     dword ptr [rbp+pbData], 8004h
0x180034272  call    cs:__imp_CryptSetHashParam
0x180034278  test    eax, eax
0x18003427a  jz      short loc_180034242
0x18003427c  mov     rcx, [rbp+hHash]; hHash
0x180034280  xor     r9d, r9d; dwFlags
0x180034283  mov     r8d, ebx; dwDataLen
0x180034286  mov     rdx, rdi; pbData
0x180034289  call    cs:__imp_CryptHashData
0x18003428f  test    eax, eax
0x180034291  jz      short loc_180034242
0x180034293  mov     rbx, [rbp+arg_20]
0x180034297  mov     edx, 2; dwParam
0x18003429c  mov     rdi, [rbp+pdwDataLen]
0x1800342a0  mov     rcx, [rbp+hHash]; hHash
0x1800342a4  mov     r9, rdi; pdwDataLen
0x1800342a7  mov     dword ptr [rsp+60h+phHash], 0; dwFlags
0x1800342af  mov     r8, [rbx]; pbData
0x1800342b2  call    cs:__imp_CryptGetHashParam
0x1800342b8  cmp     dword ptr [rdi], 0
0x1800342bb  jbe     short loc_180034242
0x1800342bd  mov     edx, [rdi]; uBytes
0x1800342bf  mov     ecx, 40h ; '@'; uFlags
0x1800342c4  call    cs:__imp_LocalAlloc
0x1800342ca  mov     [rbx], rax
0x1800342cd  test    rax, rax
0x1800342d0  jnz     short loc_1800342D9
0x1800342d2  mov     edi, 0C000009Ah
0x1800342d7  jmp     short loc_1800342FE
0x1800342d9  mov     rcx, [rbp+hHash]; hHash
0x1800342dd  xor     ebx, ebx
0x1800342df  mov     r9, rdi; pdwDataLen
0x1800342e2  mov     dword ptr [rsp+60h+phHash], ebx; dwFlags
0x1800342e6  mov     r8, rax; pbData
0x1800342e9  lea     edx, [rbx+2]; dwParam
0x1800342ec  call    cs:__imp_CryptGetHashParam
0x1800342f2  mov     edi, 0C0000321h
0x1800342f7  test    eax, eax
0x1800342f9  cmovz   ebx, edi
0x1800342fc  mov     edi, ebx
0x1800342fe  mov     rcx, [rbp+hHash]; hHash
0x180034302  test    rcx, rcx
0x180034305  jz      short loc_18003430D
0x180034307  call    cs:__imp_CryptDestroyHash
0x18003430d  lea     r11, [rsp+60h+var_s0]
0x180034312  mov     eax, edi
0x180034314  mov     rbx, [r11+18h]
0x180034318  mov     rdi, [r11+20h]
0x18003431c  mov     rsp, r11
0x18003431f  pop     rbp
0x180034320  retn
```
