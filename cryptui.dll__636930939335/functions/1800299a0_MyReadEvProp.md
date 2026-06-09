# _MyReadEvProp

- ea: `0x1800299a0`
- end: `0x180029bb8`
- name: `_MyReadEvProp`
- size: `536`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800299a0`
- `0x1800382b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029a11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029a9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029b19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029a11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029a9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ae1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800299db`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029a37`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800299db`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029a37`
- `CRYPT32!CryptDecodeObject` at `0x180029a8a`
- `CRYPT32!CryptDecodeObject` at `0x180029ad7`
- `CRYPT32!CryptDecodeObject` at `0x180029a8a`
- `CRYPT32!CryptDecodeObject` at `0x180029ad7`

## pseudocode

```c
__int64 __fastcall MyReadEvProp(PCCERT_CONTEXT pCertContext, _QWORD *a2, _DWORD *a3)
{
  signed int LastError; // ebx
  BYTE *v7; // rax
  BYTE *v8; // r15
  _DWORD *pvStructInfo; // r14
  _QWORD *v10; // rdi
  __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  __int64 v13; // rbp
  void *v14; // rcx
  DWORD pcbStructInfo[4]; // [rsp+40h] [rbp-38h] BYREF
  SIZE_T uBytes; // [rsp+98h] [rbp+20h] BYREF

  pcbStructInfo[0] = 0;
  LODWORD(uBytes) = 0;
  if ( !CertGetCertificateContextProperty(pCertContext, 0x53u, 0, (DWORD *)&uBytes) )
  {
    LastError = GetLastError();
    goto LABEL_30;
  }
  if ( !(_DWORD)uBytes )
    return (unsigned int)-2146762480;
  v7 = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
  v8 = v7;
  if ( !v7 )
  {
    LOWORD(LastError) = 8;
    return (unsigned __int16)LastError | 0x80070000;
  }
  if ( CertGetCertificateContextProperty(pCertContext, 0x53u, v7, (DWORD *)&uBytes) )
  {
    pcbStructInfo[0] = 0;
    if ( CryptDecodeObject(0x10001u, (LPCSTR)0x10, v8, uBytes, 0, 0, pcbStructInfo) )
    {
      pvStructInfo = LocalAlloc(0x40u, pcbStructInfo[0]);
      if ( !pvStructInfo )
      {
        LastError = 8;
        goto LABEL_29;
      }
      if ( !CryptDecodeObject(0x10001u, (LPCSTR)0x10, v8, uBytes, 0, pvStructInfo, pcbStructInfo) )
      {
        LastError = GetLastError();
LABEL_28:
        LocalFree(pvStructInfo);
        goto LABEL_29;
      }
      v10 = 0;
      v11 = 0;
      if ( *pvStructInfo && *((_QWORD *)pvStructInfo + 1) )
      {
        if ( *pvStructInfo >= 0x1FFFFFFFu || (v10 = LocalAlloc(0x40u, 8LL * (unsigned int)*pvStructInfo)) == 0 )
        {
          LastError = 8;
          goto LABEL_28;
        }
        while ( (unsigned int)v11 < *pvStructInfo )
        {
          v12 = CertUIMkWStr(*(LPCCH *)(*((_QWORD *)pvStructInfo + 1) + 24 * v11));
          v10[v11] = v12;
          if ( !v12 )
          {
            v13 = 0;
            for ( LastError = 8; (unsigned int)v13 < (unsigned int)v11; v13 = (unsigned int)(v13 + 1) )
            {
              v14 = (void *)v10[v13];
              if ( v14 )
                LocalFree(v14);
            }
            LocalFree(v10);
            goto LABEL_28;
          }
          v11 = (unsigned int)(v11 + 1);
        }
      }
      *a3 = v11;
      LastError = 0;
      *a2 = v10;
      goto LABEL_28;
    }
  }
  LastError = GetLastError();
LABEL_29:
  LocalFree(v8);
LABEL_30:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800299a0  mov     rax, rsp
0x1800299a3  mov     [rax+8], rbx
0x1800299a7  mov     [rax+10h], rbp
0x1800299ab  push    rsi
0x1800299ac  push    rdi
0x1800299ad  push    r12
0x1800299af  push    r14
0x1800299b1  push    r15
0x1800299b3  sub     rsp, 50h
0x1800299b7  mov     rbp, r8
0x1800299ba  mov     dword ptr [rax-38h], 0
0x1800299c1  xor     r8d, r8d; pvData
0x1800299c4  mov     dword ptr [rax+20h], 0
0x1800299cb  mov     r12, rdx
0x1800299ce  lea     r9, [rax+20h]; pcbData
0x1800299d2  mov     rbx, rcx
0x1800299d5  lea     esi, [r8+53h]
0x1800299d9  mov     edx, esi; dwPropId
0x1800299db  call    cs:__imp_CertGetCertificateContextProperty
0x1800299e1  test    eax, eax
0x1800299e3  jnz     short loc_1800299F2
0x1800299e5  call    cs:__imp_GetLastError
0x1800299eb  mov     ebx, eax
0x1800299ed  jmp     loc_180029B90
0x1800299f2  mov     eax, dword ptr [rsp+78h+uBytes]
0x1800299f9  test    eax, eax
0x1800299fb  jnz     short loc_180029A07
0x1800299fd  mov     ebx, 800B0110h
0x180029a02  jmp     loc_180029B9D
0x180029a07  mov     edi, 40h ; '@'
0x180029a0c  mov     rdx, rax; uBytes
0x180029a0f  mov     ecx, edi; uFlags
0x180029a11  call    cs:__imp_LocalAlloc
0x180029a17  mov     r15, rax
0x180029a1a  test    rax, rax
0x180029a1d  jnz     short loc_180029A27
0x180029a1f  lea     ebx, [rdi-38h]
0x180029a22  jmp     loc_180029B94
0x180029a27  lea     r9, [rsp+78h+uBytes]; pcbData
0x180029a2f  mov     r8, r15; pvData
0x180029a32  mov     edx, esi; dwPropId
0x180029a34  mov     rcx, rbx; pCertContext
0x180029a37  call    cs:__imp_CertGetCertificateContextProperty
0x180029a3d  test    eax, eax
0x180029a3f  jnz     short loc_180029A4E
0x180029a41  call    cs:__imp_GetLastError
0x180029a47  mov     ebx, eax
0x180029a49  jmp     loc_180029B87
0x180029a4e  mov     r9d, dword ptr [rsp+78h+uBytes]; cbEncoded
0x180029a56  lea     rax, [rsp+78h+var_38]
0x180029a5b  mov     [rsp+78h+pcbStructInfo], rax; pcbStructInfo
0x180029a60  mov     ebx, 10h
0x180029a65  mov     esi, 10001h
0x180029a6a  mov     [rsp+78h+pvStructInfo], 0; pvStructInfo
0x180029a73  mov     r8, r15; pbEncoded
0x180029a76  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180029a7e  mov     edx, ebx; lpszStructType
0x180029a80  mov     [rsp+78h+var_38], 0
0x180029a88  mov     ecx, esi; dwCertEncodingType
0x180029a8a  call    cs:__imp_CryptDecodeObject
0x180029a90  test    eax, eax
0x180029a92  jz      short loc_180029A41
0x180029a94  mov     edx, [rsp+78h+var_38]; uBytes
0x180029a98  mov     ecx, edi; uFlags
0x180029a9a  call    cs:__imp_LocalAlloc
0x180029aa0  mov     r14, rax
0x180029aa3  test    rax, rax
0x180029aa6  jnz     short loc_180029AB0
0x180029aa8  lea     ebx, [rax+8]
0x180029aab  jmp     loc_180029B87
0x180029ab0  mov     r9d, dword ptr [rsp+78h+uBytes]; cbEncoded
0x180029ab8  lea     rax, [rsp+78h+var_38]
0x180029abd  mov     [rsp+78h+pcbStructInfo], rax; pcbStructInfo
0x180029ac2  mov     r8, r15; pbEncoded
0x180029ac5  mov     [rsp+78h+pvStructInfo], r14; pvStructInfo
0x180029aca  mov     rdx, rbx; lpszStructType
0x180029acd  mov     ecx, esi; dwCertEncodingType
0x180029acf  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180029ad7  call    cs:__imp_CryptDecodeObject
0x180029add  test    eax, eax
0x180029adf  jnz     short loc_180029AEE
0x180029ae1  call    cs:__imp_GetLastError
0x180029ae7  mov     ebx, eax
0x180029ae9  jmp     loc_180029B7E
0x180029aee  xor     edi, edi
0x180029af0  xor     esi, esi
0x180029af2  cmp     [r14], esi
0x180029af5  jz      short loc_180029B75
0x180029af7  cmp     [r14+8], rsi
0x180029afb  jz      short loc_180029B75
0x180029afd  cmp     dword ptr [r14], 1FFFFFFFh
0x180029b04  jb      short loc_180029B0D
0x180029b06  mov     ebx, 8
0x180029b0b  jmp     short loc_180029B7E
0x180029b0d  mov     edx, [r14]
0x180029b10  mov     ecx, 40h ; '@'; uFlags
0x180029b15  shl     rdx, 3; uBytes
0x180029b19  call    cs:__imp_LocalAlloc
0x180029b1f  mov     rdi, rax
0x180029b22  test    rax, rax
0x180029b25  jz      short loc_180029B06
0x180029b27  cmp     esi, [r14]
0x180029b2a  jnb     short loc_180029B75
0x180029b2c  mov     rcx, [r14+8]
0x180029b30  lea     rax, [rsi+rsi*2]
0x180029b34  mov     rcx, [rcx+rax*8]; lpMultiByteStr
0x180029b38  call    ?CertUIMkWStr@@YAPEAGPEBD@Z; CertUIMkWStr(char const *)
0x180029b3d  mov     [rdi+rsi*8], rax
0x180029b41  test    rax, rax
0x180029b44  jz      short loc_180029B4A
0x180029b46  inc     esi
0x180029b48  jmp     short loc_180029B27
0x180029b4a  xor     ebp, ebp
0x180029b4c  mov     ebx, 8
0x180029b51  test    esi, esi
0x180029b53  jz      short loc_180029B6A
0x180029b55  mov     rcx, [rdi+rbp*8]; hMem
0x180029b59  test    rcx, rcx
0x180029b5c  jz      short loc_180029B64
0x180029b5e  call    cs:__imp_LocalFree
0x180029b64  inc     ebp
0x180029b66  cmp     ebp, esi
0x180029b68  jb      short loc_180029B55
0x180029b6a  mov     rcx, rdi; hMem
0x180029b6d  call    cs:__imp_LocalFree
0x180029b73  jmp     short loc_180029B7E
0x180029b75  mov     [rbp+0], esi
0x180029b78  xor     ebx, ebx
0x180029b7a  mov     [r12], rdi
0x180029b7e  mov     rcx, r14; hMem
0x180029b81  call    cs:__imp_LocalFree
0x180029b87  mov     rcx, r15; hMem
0x180029b8a  call    cs:__imp_LocalFree
0x180029b90  test    ebx, ebx
0x180029b92  jle     short loc_180029B9D
0x180029b94  movzx   ebx, bx
0x180029b97  or      ebx, 80070000h
0x180029b9d  lea     r11, [rsp+78h+var_28]
0x180029ba2  mov     eax, ebx
0x180029ba4  mov     rbx, [r11+30h]
0x180029ba8  mov     rbp, [r11+38h]
0x180029bac  mov     rsp, r11
0x180029baf  pop     r15
0x180029bb1  pop     r14
0x180029bb3  pop     r12
0x180029bb5  pop     rdi
0x180029bb6  pop     rsi
0x180029bb7  retn
```
