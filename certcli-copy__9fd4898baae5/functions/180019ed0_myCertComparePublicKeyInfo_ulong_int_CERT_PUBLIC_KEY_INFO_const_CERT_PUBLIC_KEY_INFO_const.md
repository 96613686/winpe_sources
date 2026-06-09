# myCertComparePublicKeyInfo(ulong,int,_CERT_PUBLIC_KEY_INFO const *,_CERT_PUBLIC_KEY_INFO const *)

- ea: `0x180019ed0`
- end: `0x180019ff7`
- name: `?myCertComparePublicKeyInfo@@YAHKHPEBU_CERT_PUBLIC_KEY_INFO@@0@Z`
- size: `295`
- prototype: `int(unsigned int, int, const struct _CERT_PUBLIC_KEY_INFO *, const struct _CERT_PUBLIC_KEY_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b028`

## callees

- `0x180019ed0`
- `0x18001a708`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019fdf`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180019f05`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180019fcb`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180019f05`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180019fcb`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180019f87`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180019f87`

## pseudocode

```c
__int64 __fastcall myCertComparePublicKeyInfo(
        __int64 a1,
        int a2,
        struct _CERT_PUBLIC_KEY_INFO *a3,
        struct _CERT_PUBLIC_KEY_INFO *a4)
{
  unsigned int v7; // ebx
  DWORD cbData; // eax
  DWORD v9; // edx
  __int128 v10; // xmm3
  __int128 v11; // xmm2
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  int v14; // eax
  HLOCAL v15; // rdi
  DWORD v16; // edx
  HLOCAL hMem; // [rsp+20h] [rbp-49h] BYREF
  struct _CERT_PUBLIC_KEY_INFO pPublicKey2; // [rsp+28h] [rbp-41h] BYREF
  struct _CERT_PUBLIC_KEY_INFO pPublicKey1; // [rsp+58h] [rbp-11h] BYREF

  hMem = 0;
  if ( CertComparePublicKeyInfo(1u, a3, a4) )
  {
    return 1;
  }
  else
  {
    v7 = 0;
    if ( a2 )
    {
      cbData = a4->PublicKey.cbData;
      if ( a3->PublicKey.cbData == cbData || a3->PublicKey.cbData == cbData + 1 )
      {
        v9 = a3->PublicKey.cbData;
        v10 = *(_OWORD *)&a3->PublicKey.pbData;
        v11 = *(_OWORD *)&a3->Algorithm.Parameters.pbData;
        v12 = *(_OWORD *)&a4->Algorithm.Parameters.pbData;
        *(_OWORD *)&pPublicKey1.Algorithm.pszObjId = *(_OWORD *)&a3->Algorithm.pszObjId;
        *(_OWORD *)&pPublicKey2.Algorithm.pszObjId = *(_OWORD *)&a4->Algorithm.pszObjId;
        v13 = *(_OWORD *)&a4->PublicKey.pbData;
        *(_OWORD *)&pPublicKey1.Algorithm.Parameters.pbData = v11;
        *(_OWORD *)&pPublicKey2.PublicKey.pbData = v13;
        *(_OWORD *)&pPublicKey1.PublicKey.pbData = v10;
        *(_OWORD *)&pPublicKey2.Algorithm.Parameters.pbData = v12;
        v14 = mySqueezePublicKey(
                (const unsigned __int8 *)v10,
                v9,
                (unsigned __int8 **)&hMem,
                &pPublicKey1.PublicKey.cbData);
        v15 = hMem;
        if ( v14 )
        {
          CSPrintErrorLineFile(0x95B01A3u, v14);
        }
        else
        {
          v16 = pPublicKey2.PublicKey.cbData;
          pPublicKey1.PublicKey.pbData = (BYTE *)hMem;
          if ( pPublicKey2.PublicKey.cbData > 2
            && pPublicKey2.PublicKey.cbData == pPublicKey1.PublicKey.cbData + 1
            && pPublicKey2.PublicKey.pbData[pPublicKey2.PublicKey.cbData - 1] == 1 )
          {
            if ( pPublicKey2.PublicKey.pbData[pPublicKey2.PublicKey.cbData - 2] == 1 )
              v16 = pPublicKey2.PublicKey.cbData - 1;
            pPublicKey2.PublicKey.cbData = v16;
          }
          if ( CertComparePublicKeyInfo(1u, &pPublicKey1, &pPublicKey2) )
            v7 = 1;
        }
        if ( v15 )
          LocalFree(v15);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180019ed0  push    rbp
0x180019ed2  push    rbx
0x180019ed3  push    rsi
0x180019ed4  push    rdi
0x180019ed5  push    r14
0x180019ed7  push    r15
0x180019ed9  lea     rbp, [rsp-2Fh]
0x180019ede  sub     rsp, 98h
0x180019ee5  mov     rsi, r8
0x180019ee8  mov     [rbp+57h+hMem], 0
0x180019ef0  mov     r14d, edx
0x180019ef3  mov     r15d, 1
0x180019ef9  mov     rdx, rsi; pPublicKey1
0x180019efc  mov     ecx, r15d; dwCertEncodingType
0x180019eff  mov     r8, r9; pPublicKey2
0x180019f02  mov     rdi, r9
0x180019f05  call    cs:__imp_CertComparePublicKeyInfo
0x180019f0b  test    eax, eax
0x180019f0d  jz      short loc_180019F17
0x180019f0f  mov     ebx, r15d
0x180019f12  jmp     loc_180019FE5
0x180019f17  xor     ebx, ebx
0x180019f19  test    r14d, r14d
0x180019f1c  jz      loc_180019FE5
0x180019f22  mov     eax, [rdi+18h]
0x180019f25  cmp     [rsi+18h], eax
0x180019f28  jz      short loc_180019F35
0x180019f2a  inc     eax
0x180019f2c  cmp     [rsi+18h], eax
0x180019f2f  jnz     loc_180019FE5
0x180019f35  movups  xmm0, xmmword ptr [rsi]
0x180019f38  mov     edx, [rsi+18h]; unsigned int
0x180019f3b  lea     r9, [rbp+57h+pPublicKey1.PublicKey]; unsigned int *
0x180019f3f  movups  xmm3, xmmword ptr [rsi+20h]
0x180019f43  lea     r8, [rbp+57h+hMem]; unsigned __int8 **
0x180019f47  movups  xmm2, xmmword ptr [rsi+10h]
0x180019f4b  movups  xmm1, xmmword ptr [rdi+10h]
0x180019f4f  movups  xmmword ptr [rbp+57h+pPublicKey1.Algorithm.pszObjId], xmm0
0x180019f53  movups  xmm0, xmmword ptr [rdi]
0x180019f56  movq    rcx, xmm3; unsigned __int8 *
0x180019f5b  movups  xmmword ptr [rbp+57h+pPublicKey2.Algorithm.pszObjId], xmm0
0x180019f5f  movups  xmm0, xmmword ptr [rdi+20h]
0x180019f63  movups  xmmword ptr [rbp-1], xmm2
0x180019f67  movups  xmmword ptr [rbp+57h+pPublicKey2.PublicKey.pbData], xmm0
0x180019f6b  movups  xmmword ptr [rbp+57h+pPublicKey1.PublicKey.pbData], xmm3
0x180019f6f  movups  xmmword ptr [rbp+57h+pPublicKey2.Algorithm.Parameters.pbData], xmm1
0x180019f73  call    ?mySqueezePublicKey@@YAJPEBEKPEAPEAEPEAK@Z; mySqueezePublicKey(uchar const *,ulong,uchar * *,ulong *)
0x180019f78  mov     rdi, [rbp+57h+hMem]
0x180019f7c  test    eax, eax
0x180019f7e  jz      short loc_180019F8F
0x180019f80  mov     edx, eax
0x180019f82  mov     ecx, 95B01A3h
0x180019f87  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180019f8d  jmp     short loc_180019FD7
0x180019f8f  mov     edx, [rbp+57h+pPublicKey2.PublicKey.cbData]
0x180019f92  mov     [rbp+57h+pPublicKey1.PublicKey.pbData], rdi
0x180019f96  cmp     edx, 2
0x180019f99  jbe     short loc_180019FC0
0x180019f9b  mov     eax, [rbp+57h+pPublicKey1.PublicKey.cbData]
0x180019f9e  inc     eax
0x180019fa0  cmp     edx, eax
0x180019fa2  jnz     short loc_180019FC0
0x180019fa4  mov     r8, [rbp+57h+pPublicKey2.PublicKey.pbData]
0x180019fa8  lea     r9d, [rdx-1]
0x180019fac  cmp     [r9+r8], r15b
0x180019fb0  jnz     short loc_180019FC0
0x180019fb2  lea     eax, [rdx-2]
0x180019fb5  cmp     [rax+r8], r15b
0x180019fb9  cmovz   edx, r9d
0x180019fbd  mov     [rbp+57h+pPublicKey2.PublicKey.cbData], edx
0x180019fc0  lea     r8, [rbp+57h+pPublicKey2]; pPublicKey2
0x180019fc4  mov     ecx, r15d; dwCertEncodingType
0x180019fc7  lea     rdx, [rbp+57h+pPublicKey1]; pPublicKey1
0x180019fcb  call    cs:__imp_CertComparePublicKeyInfo
0x180019fd1  test    eax, eax
0x180019fd3  cmovnz  ebx, r15d
0x180019fd7  test    rdi, rdi
0x180019fda  jz      short loc_180019FE5
0x180019fdc  mov     rcx, rdi; hMem
0x180019fdf  call    cs:__imp_LocalFree
0x180019fe5  mov     eax, ebx
0x180019fe7  add     rsp, 98h
0x180019fee  pop     r15
0x180019ff0  pop     r14
0x180019ff2  pop     rdi
0x180019ff3  pop     rsi
0x180019ff4  pop     rbx
0x180019ff5  pop     rbp
0x180019ff6  retn
```
