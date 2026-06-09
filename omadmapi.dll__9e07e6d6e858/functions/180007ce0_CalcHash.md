# CalcHash

- ea: `0x180007ce0`
- end: `0x180007f91`
- name: `CalcHash`
- size: `689`
- prototype: `__int64 __fastcall(BYTE *pbData, ALG_ID Algid)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800183b0`

## callees

- `0x18000756c`
- `0x180007ce0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007edf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e94`
- `CRYPTSP!CryptCreateHash` at `0x180007d54`
- `CRYPTSP!CryptCreateHash` at `0x180007d54`
- `CRYPTSP!CryptHashData` at `0x180007dd8`
- `CRYPTSP!CryptHashData` at `0x180007dd8`
- `CRYPTSP!CryptGetHashParam` at `0x180007e1c`
- `CRYPTSP!CryptGetHashParam` at `0x180007e84`
- `CRYPTSP!CryptGetHashParam` at `0x180007e1c`
- `CRYPTSP!CryptGetHashParam` at `0x180007e84`
- `CRYPTSP!CryptDestroyHash` at `0x180007f53`
- `CRYPTSP!CryptDestroyHash` at `0x180007f53`
- `CRYPTSP!CryptReleaseContext` at `0x180007f6a`
- `CRYPTSP!CryptReleaseContext` at `0x180007f6a`
- `DMCmnUtils!BinaryToHexString` at `0x180007ec5`
- `DMCmnUtils!BinaryToHexString` at `0x180007f0c`
- `DMCmnUtils!BinaryToHexString` at `0x180007ec5`
- `DMCmnUtils!BinaryToHexString` at `0x180007f0c`

## pseudocode

```c
__int64 __fastcall CalcHash(BYTE *pbData, ALG_ID Algid, _QWORD *a3)
{
  void *v6; // rdi
  BYTE *v7; // rsi
  signed int v8; // ebx
  signed int LastError; // eax
  __int64 v10; // rdx
  BYTE *v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  BYTE *v14; // rax
  signed int v15; // eax
  HLOCAL v16; // rax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-10h] BYREF
  HCRYPTPROV hProv; // [rsp+38h] [rbp-8h] BYREF
  DWORD pdwDataLen; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+58h] BYREF

  hProv = 0;
  hHash = 0;
  pdwDataLen = 0;
  v6 = 0;
  v21 = 0;
  v7 = 0;
  if ( pbData && a3 )
  {
    v8 = AcquireCryptoContext(&hProv);
    if ( v8 >= 0 )
    {
      if ( CryptCreateHash(hProv, Algid, 0, 0, &hHash) )
        goto LABEL_8;
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
      {
LABEL_8:
        v10 = 0x7FFFFFFF;
        v11 = pbData;
        do
        {
          if ( !*(_WORD *)v11 )
            break;
          v11 += 2;
          --v10;
        }
        while ( v10 );
        v8 = v10 == 0 ? 0x80070057 : 0;
        if ( v10 )
        {
          if ( CryptHashData(hHash, pbData, v10 != 0 ? -2 - 2 * v10 : 0, 0) )
            goto LABEL_19;
          v12 = GetLastError();
          v8 = v12;
          if ( v12 > 0 )
            v8 = (unsigned __int16)v12 | 0x80070000;
          if ( v8 >= 0 )
          {
LABEL_19:
            if ( CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
              goto LABEL_20;
            v13 = GetLastError();
            v8 = v13;
            if ( v13 > 0 )
              v8 = (unsigned __int16)v13 | 0x80070000;
            if ( v8 >= 0 )
            {
LABEL_20:
              v14 = (BYTE *)LocalAlloc(0, pdwDataLen);
              v7 = v14;
              if ( !v14 )
              {
LABEL_21:
                v8 = -2147024882;
                goto LABEL_31;
              }
              if ( CryptGetHashParam(hHash, 2u, v14, &pdwDataLen, 0) )
                goto LABEL_38;
              v15 = GetLastError();
              v8 = v15;
              if ( v15 > 0 )
                v8 = (unsigned __int16)v15 | 0x80070000;
              if ( v8 >= 0 )
              {
LABEL_38:
                v8 = BinaryToHexString(v7, pdwDataLen, 0, &v21);
                if ( v8 >= 0 )
                {
                  v16 = LocalAlloc(0, 2LL * v21);
                  v6 = v16;
                  if ( !v16 )
                    goto LABEL_21;
                  v8 = BinaryToHexString(v7, pdwDataLen, v16, &v21);
                  if ( v8 >= 0 )
                  {
                    *a3 = v6;
                    v6 = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_31:
  LocalFree(v7);
  LocalFree(v6);
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007ce0  mov     [rsp-38h+arg_8], rbx
0x180007ce5  push    rbp
0x180007ce6  push    rsi
0x180007ce7  push    rdi
0x180007ce8  push    r12
0x180007cea  push    r13
0x180007cec  push    r14
0x180007cee  push    r15
0x180007cf0  mov     rbp, rsp
0x180007cf3  sub     rsp, 40h
0x180007cf7  xor     r13d, r13d
0x180007cfa  mov     r12, r8
0x180007cfd  mov     [rbp+hProv], r13
0x180007d01  mov     r15d, edx
0x180007d04  mov     [rbp+hHash], r13
0x180007d08  mov     r14, rcx
0x180007d0b  mov     [rbp+pdwDataLen], r13d
0x180007d0f  mov     edi, r13d
0x180007d12  mov     [rbp+arg_18], r13d
0x180007d16  mov     esi, r13d
0x180007d19  test    rcx, rcx
0x180007d1c  jz      loc_180007F27
0x180007d22  test    r8, r8
0x180007d25  jz      loc_180007F27
0x180007d2b  lea     rcx, [rbp+hProv]; phProv
0x180007d2f  call    ?AcquireCryptoContext@@YAJPEA_K@Z; AcquireCryptoContext(unsigned __int64 *)
0x180007d34  mov     ebx, eax
0x180007d36  test    eax, eax
0x180007d38  js      loc_180007F2C
0x180007d3e  mov     rcx, [rbp+hProv]; hProv
0x180007d42  lea     rax, [rbp+hHash]
0x180007d46  xor     r9d, r9d; dwFlags
0x180007d49  mov     [rsp+40h+phHash], rax; phHash
0x180007d4e  xor     r8d, r8d; hKey
0x180007d51  mov     edx, r15d; Algid
0x180007d54  call    cs:__imp_CryptCreateHash
0x180007d5b  nop     dword ptr [rax+rax+00h]
0x180007d60  mov     r15d, 80070000h
0x180007d66  test    eax, eax
0x180007d68  jnz     short loc_180007D8A
0x180007d6a  call    cs:__imp_GetLastError
0x180007d71  nop     dword ptr [rax+rax+00h]
0x180007d76  mov     ebx, eax
0x180007d78  test    eax, eax
0x180007d7a  jle     short loc_180007D82
0x180007d7c  movzx   ebx, ax
0x180007d7f  or      ebx, r15d
0x180007d82  test    ebx, ebx
0x180007d84  js      loc_180007F2C
0x180007d8a  mov     edx, 7FFFFFFFh
0x180007d8f  mov     rax, r14
0x180007d92  cmp     [rax], r13w
0x180007d96  jz      short loc_180007DA2
0x180007d98  add     rax, 2
0x180007d9c  sub     rdx, 1
0x180007da0  jnz     short loc_180007D92
0x180007da2  mov     rax, rdx
0x180007da5  neg     rax
0x180007da8  sbb     ebx, ebx
0x180007daa  not     ebx
0x180007dac  and     ebx, 80070057h
0x180007db2  test    rdx, rdx
0x180007db5  jz      loc_180007F2C
0x180007dbb  lea     eax, [rdx+rdx]
0x180007dbe  mov     ecx, 0FFFFFFFEh
0x180007dc3  sub     ecx, eax
0x180007dc5  neg     rdx
0x180007dc8  mov     rdx, r14; pbData
0x180007dcb  sbb     r8d, r8d
0x180007dce  xor     r9d, r9d; dwFlags
0x180007dd1  and     r8d, ecx; dwDataLen
0x180007dd4  mov     rcx, [rbp+hHash]; hHash
0x180007dd8  call    cs:__imp_CryptHashData
0x180007ddf  nop     dword ptr [rax+rax+00h]
0x180007de4  test    eax, eax
0x180007de6  jnz     short loc_180007E08
0x180007de8  call    cs:__imp_GetLastError
0x180007def  nop     dword ptr [rax+rax+00h]
0x180007df4  mov     ebx, eax
0x180007df6  test    eax, eax
0x180007df8  jle     short loc_180007E00
0x180007dfa  movzx   ebx, ax
0x180007dfd  or      ebx, r15d
0x180007e00  test    ebx, ebx
0x180007e02  js      loc_180007F2C
0x180007e08  mov     rcx, [rbp+hHash]; hHash
0x180007e0c  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180007e10  xor     r8d, r8d; pbData
0x180007e13  mov     dword ptr [rsp+40h+phHash], r13d; dwFlags
0x180007e18  lea     edx, [r8+2]; dwParam
0x180007e1c  call    cs:__imp_CryptGetHashParam
0x180007e23  nop     dword ptr [rax+rax+00h]
0x180007e28  test    eax, eax
0x180007e2a  jnz     short loc_180007E4C
0x180007e2c  call    cs:__imp_GetLastError
0x180007e33  nop     dword ptr [rax+rax+00h]
0x180007e38  mov     ebx, eax
0x180007e3a  test    eax, eax
0x180007e3c  jle     short loc_180007E44
0x180007e3e  movzx   ebx, ax
0x180007e41  or      ebx, r15d
0x180007e44  test    ebx, ebx
0x180007e46  js      loc_180007F2C
0x180007e4c  mov     edx, [rbp+pdwDataLen]; uBytes
0x180007e4f  xor     ecx, ecx; uFlags
0x180007e51  call    cs:__imp_LocalAlloc
0x180007e58  nop     dword ptr [rax+rax+00h]
0x180007e5d  mov     rsi, rax
0x180007e60  test    rax, rax
0x180007e63  jnz     short loc_180007E6F
0x180007e65  mov     ebx, 8007000Eh
0x180007e6a  jmp     loc_180007F2C
0x180007e6f  mov     rcx, [rbp+hHash]; hHash
0x180007e73  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180007e77  mov     r8, rsi; pbData
0x180007e7a  mov     dword ptr [rsp+40h+phHash], r13d; dwFlags
0x180007e7f  mov     edx, 2; dwParam
0x180007e84  call    cs:__imp_CryptGetHashParam
0x180007e8b  nop     dword ptr [rax+rax+00h]
0x180007e90  test    eax, eax
0x180007e92  jnz     short loc_180007EB0
0x180007e94  call    cs:__imp_GetLastError
0x180007e9b  nop     dword ptr [rax+rax+00h]
0x180007ea0  mov     ebx, eax
0x180007ea2  test    eax, eax
0x180007ea4  jle     short loc_180007EAC
0x180007ea6  movzx   ebx, ax
0x180007ea9  or      ebx, r15d
0x180007eac  test    ebx, ebx
0x180007eae  js      short loc_180007F2C
0x180007eb0  mov     edx, [rbp+pdwDataLen]
0x180007eb3  lea     r9, [rbp+arg_18]
0x180007eb7  xor     r8d, r8d
0x180007eba  mov     dword ptr [rsp+40h+phHash], 1
0x180007ec2  mov     rcx, rsi
0x180007ec5  call    cs:__imp_BinaryToHexString
0x180007ecc  nop     dword ptr [rax+rax+00h]
0x180007ed1  mov     ebx, eax
0x180007ed3  test    eax, eax
0x180007ed5  js      short loc_180007F2C
0x180007ed7  mov     edx, [rbp+arg_18]
0x180007eda  xor     ecx, ecx; uFlags
0x180007edc  add     rdx, rdx; uBytes
0x180007edf  call    cs:__imp_LocalAlloc
0x180007ee6  nop     dword ptr [rax+rax+00h]
0x180007eeb  mov     rdi, rax
0x180007eee  test    rax, rax
0x180007ef1  jz      loc_180007E65
0x180007ef7  mov     edx, [rbp+pdwDataLen]
0x180007efa  lea     r9, [rbp+arg_18]
0x180007efe  mov     r8, rax
0x180007f01  mov     dword ptr [rsp+40h+phHash], 1
0x180007f09  mov     rcx, rsi
0x180007f0c  call    cs:__imp_BinaryToHexString
0x180007f13  nop     dword ptr [rax+rax+00h]
0x180007f18  mov     ebx, eax
0x180007f1a  test    eax, eax
0x180007f1c  js      short loc_180007F2C
0x180007f1e  mov     [r12], rdi
0x180007f22  mov     rdi, r13
0x180007f25  jmp     short loc_180007F2C
0x180007f27  mov     ebx, 80070057h
0x180007f2c  mov     rcx, rsi; hMem
0x180007f2f  call    cs:__imp_LocalFree
0x180007f36  nop     dword ptr [rax+rax+00h]
0x180007f3b  mov     rcx, rdi; hMem
0x180007f3e  call    cs:__imp_LocalFree
0x180007f45  nop     dword ptr [rax+rax+00h]
0x180007f4a  mov     rcx, [rbp+hHash]; hHash
0x180007f4e  test    rcx, rcx
0x180007f51  jz      short loc_180007F5F
0x180007f53  call    cs:__imp_CryptDestroyHash
0x180007f5a  nop     dword ptr [rax+rax+00h]
0x180007f5f  mov     rcx, [rbp+hProv]; hProv
0x180007f63  test    rcx, rcx
0x180007f66  jz      short loc_180007F76
0x180007f68  xor     edx, edx; dwFlags
0x180007f6a  call    cs:__imp_CryptReleaseContext
0x180007f71  nop     dword ptr [rax+rax+00h]
0x180007f76  mov     eax, ebx
0x180007f78  mov     rbx, [rsp+40h+arg_8]
0x180007f80  add     rsp, 40h
0x180007f84  pop     r15
0x180007f86  pop     r14
0x180007f88  pop     r13
0x180007f8a  pop     r12
0x180007f8c  pop     rdi
0x180007f8d  pop     rsi
0x180007f8e  pop     rbp
0x180007f8f  retn
```
