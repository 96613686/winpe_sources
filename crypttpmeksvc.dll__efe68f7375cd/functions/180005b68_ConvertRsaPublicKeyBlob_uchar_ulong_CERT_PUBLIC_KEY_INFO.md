# _ConvertRsaPublicKeyBlob(uchar *,ulong,_CERT_PUBLIC_KEY_INFO * *)

- ea: `0x180005b68`
- end: `0x180005d3b`
- name: `?_ConvertRsaPublicKeyBlob@@YAJPEAEKPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(PBYTE pbData, DWORD cbData, struct _CERT_PUBLIC_KEY_INFO **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005680`

## callees

- `0x180003750`
- `0x180005b68`

## import_xrefs

- `CRYPT32!CryptExportPublicKeyInfo` at `0x180005c2e`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180005ca9`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180005c2e`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x180005ca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cb3`
- `ncrypt!NCryptImportKey` at `0x180005bf8`
- `ncrypt!NCryptImportKey` at `0x180005bf8`
- `ncrypt!NCryptOpenStorageProvider` at `0x180005ba4`
- `ncrypt!NCryptOpenStorageProvider` at `0x180005ba4`
- `ncrypt!NCryptFreeObject` at `0x180005d17`
- `ncrypt!NCryptFreeObject` at `0x180005d26`
- `ncrypt!NCryptFreeObject` at `0x180005d17`
- `ncrypt!NCryptFreeObject` at `0x180005d26`

## string_xrefs

- `0x180005bb0`: `ERROR: NCryptOpenStorageProvider. Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _ConvertRsaPublicKeyBlob(PBYTE pbData, DWORD cbData, struct _CERT_PUBLIC_KEY_INFO **a3)
{
  struct _CERT_PUBLIC_KEY_INFO *v3; // rsi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r8
  unsigned int v10; // ecx
  signed int v11; // eax
  DWORD v12; // ebx
  signed int LastError; // eax
  NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey; // [rsp+40h] [rbp-18h] BYREF
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+48h] [rbp-10h] BYREF
  DWORD pcbInfo; // [rsp+A8h] [rbp+50h] BYREF

  v3 = 0;
  phProvider[0] = 0;
  hCryptProvOrNCryptKey = 0;
  pcbInfo = 0;
  v7 = NCryptOpenStorageProvider(phProvider, L"Microsoft Software Key Storage Provider", 0x40u);
  v8 = v7;
  if ( v7 )
  {
    v9 = "ERROR: NCryptOpenStorageProvider. Hr=%x\n";
    v10 = 20255426;
LABEL_3:
    ekTraceFmt(v10, 1, v9, v7);
    goto LABEL_20;
  }
  v7 = NCryptImportKey(phProvider[0], 0, L"PUBLICBLOB", 0, &hCryptProvOrNCryptKey, pbData, cbData, 0x40u);
  v8 = v7;
  if ( v7 )
  {
    v9 = "ERROR: NCryptImportKey. Hr=%x\n";
    v10 = 21238466;
    goto LABEL_3;
  }
  pcbInfo = 0;
  if ( CryptExportPublicKeyInfo(hCryptProvOrNCryptKey, 0, 1u, 0, &pcbInfo) )
  {
    v3 = (struct _CERT_PUBLIC_KEY_INFO *)LocalAlloc(0, pcbInfo);
    if ( v3 )
    {
      v12 = pcbInfo;
      if ( CryptExportPublicKeyInfo(hCryptProvOrNCryptKey, 0, 1u, v3, &pcbInfo) )
      {
        if ( v12 == pcbInfo )
        {
          *a3 = v3;
          v3 = 0;
          v8 = 0;
        }
        else
        {
          v8 = -2147024809;
          ekTraceFmt(0x16D12C2u, 1, "ERROR: PublicKeyInfo size mismatch. Hr=%x\n", 2147942487LL);
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        ekTraceFmt(0x16612C2u, 1, "ERROR: CryptExportPublicKeyInfo. Hr=%x\n", v8);
      }
    }
    else
    {
      v8 = -2147024882;
      ekTraceFmt(0x15912C2u, 1, "ERROR: LocalAlloc. Hr=%x\n", 2147942414LL);
    }
  }
  else
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    ekTraceFmt(0x15112C2u, 1, "ERROR: CryptExportPublicKeyInfo. Hr=%x\n", v8);
  }
LABEL_20:
  LocalFree(v3);
  if ( phProvider[0] )
    NCryptFreeObject(phProvider[0]);
  if ( hCryptProvOrNCryptKey )
    NCryptFreeObject(hCryptProvOrNCryptKey);
  return v8;
}

```

## disassembly

```asm
0x180005b68  push    rbp
0x180005b6a  push    rbx
0x180005b6b  push    rsi
0x180005b6c  push    rdi
0x180005b6d  push    r14
0x180005b6f  push    r15
0x180005b71  mov     rbp, rsp
0x180005b74  sub     rsp, 58h
0x180005b78  xor     esi, esi
0x180005b7a  mov     [rbp+phProvider], 0
0x180005b82  mov     r14, r8
0x180005b85  mov     [rbp+hCryptProvOrNCryptKey], 0
0x180005b8d  mov     edi, edx
0x180005b8f  mov     [rbp+pcbInfo], esi
0x180005b92  mov     r15, rcx
0x180005b95  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x180005b9c  lea     r8d, [rsi+40h]; dwFlags
0x180005ba0  lea     rcx, [rbp+phProvider]; phProvider
0x180005ba4  call    cs:__imp_NCryptOpenStorageProvider
0x180005baa  mov     ebx, eax
0x180005bac  test    eax, eax
0x180005bae  jz      short loc_180005BCE
0x180005bb0  lea     r8, aErrorNcryptope; "ERROR: NCryptOpenStorageProvider. Hr=%x"...
0x180005bb7  mov     ecx, 13512C2h; unsigned int
0x180005bbc  mov     edx, 1; unsigned int
0x180005bc1  mov     r9d, eax
0x180005bc4  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005bc9  jmp     loc_180005D05
0x180005bce  mov     rcx, [rbp+phProvider]; hProvider
0x180005bd2  lea     rax, [rbp+hCryptProvOrNCryptKey]
0x180005bd6  mov     [rsp+58h+dwFlags], 40h ; '@'; dwFlags
0x180005bde  lea     r8, aPublicblob; "PUBLICBLOB"
0x180005be5  mov     [rsp+58h+cbData], edi; cbData
0x180005be9  xor     r9d, r9d; pParameterList
0x180005bec  mov     [rsp+58h+pbData], r15; pbData
0x180005bf1  xor     edx, edx; hImportKey
0x180005bf3  mov     [rsp+58h+phKey], rax; phKey
0x180005bf8  call    cs:__imp_NCryptImportKey
0x180005bfe  mov     ebx, eax
0x180005c00  test    eax, eax
0x180005c02  jz      short loc_180005C12
0x180005c04  lea     r8, aErrorNcryptimp; "ERROR: NCryptImportKey. Hr=%x\n"
0x180005c0b  mov     ecx, 14412C2h
0x180005c10  jmp     short loc_180005BBC
0x180005c12  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x180005c16  lea     rax, [rbp+pcbInfo]
0x180005c1a  xor     r9d, r9d; pInfo
0x180005c1d  mov     [rbp+pcbInfo], esi
0x180005c20  xor     edx, edx; dwKeySpec
0x180005c22  mov     [rsp+58h+phKey], rax; pcbInfo
0x180005c27  lea     edi, [r9+1]
0x180005c2b  mov     r8d, edi; dwCertEncodingType
0x180005c2e  call    cs:__imp_CryptExportPublicKeyInfo
0x180005c34  test    eax, eax
0x180005c36  jnz     short loc_180005C63
0x180005c38  call    cs:__imp_GetLastError
0x180005c3e  mov     ebx, eax
0x180005c40  test    eax, eax
0x180005c42  jle     short loc_180005C4D
0x180005c44  movzx   ebx, ax
0x180005c47  or      ebx, 80070000h
0x180005c4d  mov     r9d, ebx
0x180005c50  lea     r8, aErrorCryptexpo; "ERROR: CryptExportPublicKeyInfo. Hr=%x"...
0x180005c57  mov     edx, edi
0x180005c59  mov     ecx, 15112C2h
0x180005c5e  jmp     loc_180005BC4
0x180005c63  mov     edx, [rbp+pcbInfo]; uBytes
0x180005c66  xor     ecx, ecx; uFlags
0x180005c68  call    cs:__imp_LocalAlloc
0x180005c6e  mov     rsi, rax
0x180005c71  test    rax, rax
0x180005c74  jnz     short loc_180005C91
0x180005c76  mov     ebx, 8007000Eh
0x180005c7b  lea     r8, aErrorLocalallo_1; "ERROR: LocalAlloc. Hr=%x\n"
0x180005c82  mov     r9d, ebx
0x180005c85  mov     edx, edi
0x180005c87  mov     ecx, 15912C2h
0x180005c8c  jmp     loc_180005BC4
0x180005c91  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x180005c95  lea     rax, [rbp+pcbInfo]
0x180005c99  mov     ebx, [rbp+pcbInfo]
0x180005c9c  mov     r9, rsi; pInfo
0x180005c9f  mov     r8d, edi; dwCertEncodingType
0x180005ca2  mov     [rsp+58h+phKey], rax; pcbInfo
0x180005ca7  xor     edx, edx; dwKeySpec
0x180005ca9  call    cs:__imp_CryptExportPublicKeyInfo
0x180005caf  test    eax, eax
0x180005cb1  jnz     short loc_180005CDE
0x180005cb3  call    cs:__imp_GetLastError
0x180005cb9  mov     ebx, eax
0x180005cbb  test    eax, eax
0x180005cbd  jle     short loc_180005CC8
0x180005cbf  movzx   ebx, ax
0x180005cc2  or      ebx, 80070000h
0x180005cc8  mov     r9d, ebx
0x180005ccb  lea     r8, aErrorCryptexpo; "ERROR: CryptExportPublicKeyInfo. Hr=%x"...
0x180005cd2  mov     edx, edi
0x180005cd4  mov     ecx, 16612C2h
0x180005cd9  jmp     loc_180005BC4
0x180005cde  cmp     ebx, [rbp+pcbInfo]
0x180005ce1  jz      short loc_180005CFE
0x180005ce3  mov     ebx, 80070057h
0x180005ce8  lea     r8, aErrorPublickey; "ERROR: PublicKeyInfo size mismatch. Hr="...
0x180005cef  mov     r9d, ebx
0x180005cf2  mov     edx, edi
0x180005cf4  mov     ecx, 16D12C2h
0x180005cf9  jmp     loc_180005BC4
0x180005cfe  mov     [r14], rsi
0x180005d01  xor     esi, esi
0x180005d03  xor     ebx, ebx
0x180005d05  mov     rcx, rsi; hMem
0x180005d08  call    cs:__imp_LocalFree
0x180005d0e  mov     rcx, [rbp+phProvider]; hObject
0x180005d12  test    rcx, rcx
0x180005d15  jz      short loc_180005D1D
0x180005d17  call    cs:__imp_NCryptFreeObject
0x180005d1d  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hObject
0x180005d21  test    rcx, rcx
0x180005d24  jz      short loc_180005D2C
0x180005d26  call    cs:__imp_NCryptFreeObject
0x180005d2c  mov     eax, ebx
0x180005d2e  add     rsp, 58h
0x180005d32  pop     r15
0x180005d34  pop     r14
0x180005d36  pop     rdi
0x180005d37  pop     rsi
0x180005d38  pop     rbx
0x180005d39  pop     rbp
0x180005d3a  retn
```
