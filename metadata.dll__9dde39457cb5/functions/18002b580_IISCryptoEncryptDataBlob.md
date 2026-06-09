# IISCryptoEncryptDataBlob

- ea: `0x18002b580`
- end: `0x18002b78d`
- name: `IISCryptoEncryptDataBlob`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002a128`

## callees

- `0x18002937c`
- `0x180029aa4`
- `0x180029bc8`
- `0x180029c24`
- `0x180029c90`
- `0x180029e24`
- `0x18002b580`
- `0x18003098e`

## import_xrefs

- `ADVAPI32!CryptEncrypt` at `0x18002b65a`
- `ADVAPI32!CryptEncrypt` at `0x18002b71c`
- `ADVAPI32!CryptEncrypt` at `0x18002b65a`
- `ADVAPI32!CryptEncrypt` at `0x18002b71c`
- `ADVAPI32!CryptSignHashA` at `0x18002b764`
- `ADVAPI32!CryptSignHashA` at `0x18002b764`
- `ole32!CoTaskMemFree` at `0x18002b68a`
- `ole32!CoTaskMemFree` at `0x18002b68a`
- `KERNEL32!LeaveCriticalSection` at `0x18002b66e`
- `KERNEL32!LeaveCriticalSection` at `0x18002b6ae`
- `KERNEL32!LeaveCriticalSection` at `0x18002b72d`
- `KERNEL32!LeaveCriticalSection` at `0x18002b66e`
- `KERNEL32!LeaveCriticalSection` at `0x18002b6ae`
- `KERNEL32!LeaveCriticalSection` at `0x18002b72d`
- `KERNEL32!EnterCriticalSection` at `0x18002b632`
- `KERNEL32!EnterCriticalSection` at `0x18002b6f2`
- `KERNEL32!EnterCriticalSection` at `0x18002b632`
- `KERNEL32!EnterCriticalSection` at `0x18002b6f2`

## pseudocode

```c
__int64 __fastcall IISCryptoEncryptDataBlob(
        BYTE **a1,
        const void *a2,
        DWORD a3,
        int a4,
        HCRYPTPROV hProv,
        HCRYPTKEY hKey)
{
  __int64 result; // rax
  BYTE *v10; // rdi
  int HashLength; // ebx
  struct _IC_BLOB *Blob; // rax
  BYTE *pbData; // rbx
  DWORD pdwDataLen; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwSigLen; // [rsp+44h] [rbp-Ch] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwBufLen; // [rsp+90h] [rbp+40h] BYREF

  dwBufLen = a3;
  pdwDataLen = 0;
  pdwSigLen = 0;
  if ( dword_180048964 )
  {
    v10 = 0;
    hHash = 0;
    HashLength = IISCryptoCreateHash(&hHash, hProv);
    if ( HashLength >= 0 )
    {
      if ( !hHash )
        return (unsigned int)HashLength;
      HashLength = IcpGetHashLength(&pdwSigLen, hProv);
      if ( HashLength >= 0 )
      {
        dwBufLen += 4;
        pdwDataLen = dwBufLen;
        EnterCriticalSection(&IcpGlobals);
        if ( CryptEncrypt(hKey, 0, 1, 0, 0, &pdwDataLen, dwBufLen) )
        {
          LeaveCriticalSection(&IcpGlobals);
          Blob = IcpCreateBlob(1648649033, pdwDataLen, pdwSigLen);
          v10 = (BYTE *)Blob;
          if ( !Blob )
          {
            HashLength = -2147024888;
            goto LABEL_11;
          }
          pbData = (BYTE *)Blob + 16;
          *((_DWORD *)Blob + 4) = a4;
          memcpy_0((char *)Blob + 20, a2, dwBufLen - 4LL);
          EnterCriticalSection(&IcpGlobals);
          if ( CryptEncrypt(hKey, hHash, 1, 0, pbData, &dwBufLen, pdwDataLen) )
          {
            LeaveCriticalSection(&IcpGlobals);
            if ( CryptSignHashA(hHash, 2u, 0, 0, &v10[((*((_DWORD *)v10 + 2) + 7) & 0xFFFFFFF8) + 16], &pdwSigLen) )
            {
              IISCryptoDestroyHash(hHash);
              result = 0;
              *a1 = v10;
              return result;
            }
            HashLength = IcpGetLastError();
            goto LABEL_11;
          }
        }
        HashLength = IcpGetLastError();
        LeaveCriticalSection(&IcpGlobals);
      }
    }
LABEL_11:
    if ( hHash )
      IISCryptoDestroyHash(hHash);
    if ( v10 )
      CoTaskMemFree(v10);
    return (unsigned int)HashLength;
  }
  if ( hProv == 1984918096 && hKey == 1800627539 )
    return IISCryptoCreateCleartextBlob(a1, a2, a3);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18002b580  mov     [rsp-28h+arg_0], rbx
0x18002b585  mov     [rsp-28h+arg_8], rsi
0x18002b58a  mov     [rsp-28h+arg_10], r8d
0x18002b58f  push    rbp
0x18002b590  push    rdi
0x18002b591  push    r13
0x18002b593  push    r14
0x18002b595  push    r15
0x18002b597  mov     rbp, rsp
0x18002b59a  sub     rsp, 50h
0x18002b59e  cmp     cs:dword_180048964, 0
0x18002b5a5  mov     r15d, r9d
0x18002b5a8  mov     r14, rdx
0x18002b5ab  mov     [rbp+var_10], 0
0x18002b5b2  mov     rsi, rcx
0x18002b5b5  mov     [rbp+pdwSigLen], 0
0x18002b5bc  jnz     short loc_18002B5E6
0x18002b5be  cmp     [rbp+hProv], 764F7250h
0x18002b5c6  jnz     short loc_18002B5DC
0x18002b5c8  cmp     [rbp+hKey], 6B536553h
0x18002b5d0  jnz     short loc_18002B5DC
0x18002b5d2  call    IISCryptoCreateCleartextBlob
0x18002b5d7  jmp     loc_18002B692
0x18002b5dc  mov     eax, 80070057h
0x18002b5e1  jmp     loc_18002B692
0x18002b5e6  mov     rdx, [rbp+hProv]; hProv
0x18002b5ea  lea     rcx, [rbp+hHash]; phHash
0x18002b5ee  xor     edi, edi
0x18002b5f0  mov     [rbp+hHash], rdi
0x18002b5f4  call    IISCryptoCreateHash
0x18002b5f9  mov     ebx, eax
0x18002b5fb  test    eax, eax
0x18002b5fd  js      short loc_18002B674
0x18002b5ff  cmp     [rbp+hHash], rdi
0x18002b603  jz      loc_18002B690
0x18002b609  mov     rdx, [rbp+hProv]; unsigned __int64
0x18002b60d  lea     rcx, [rbp+pdwSigLen]; unsigned int *
0x18002b611  call    ?IcpGetHashLength@@YAJPEAK_K@Z; IcpGetHashLength(ulong *,unsigned __int64)
0x18002b616  mov     ebx, eax
0x18002b618  test    eax, eax
0x18002b61a  js      short loc_18002B674
0x18002b61c  mov     eax, [rbp+arg_10]
0x18002b61f  lea     r13, ?IcpGlobals@@3U_IC_GLOBALS@@A; _IC_GLOBALS IcpGlobals
0x18002b626  add     eax, 4
0x18002b629  mov     rcx, r13; lpCriticalSection
0x18002b62c  mov     [rbp+arg_10], eax
0x18002b62f  mov     [rbp+var_10], eax
0x18002b632  call    cs:__imp_EnterCriticalSection
0x18002b638  mov     eax, [rbp+arg_10]
0x18002b63b  lea     r8d, [rdi+1]; Final
0x18002b63f  mov     rcx, [rbp+hKey]; hKey
0x18002b643  xor     r9d, r9d; dwFlags
0x18002b646  mov     [rsp+50h+dwBufLen], eax; dwBufLen
0x18002b64a  xor     edx, edx; hHash
0x18002b64c  lea     rax, [rbp+var_10]
0x18002b650  mov     [rsp+50h+pdwDataLen], rax; pdwDataLen
0x18002b655  mov     [rsp+50h+pbData], rdi; pbData
0x18002b65a  call    cs:__imp_CryptEncrypt
0x18002b660  test    eax, eax
0x18002b662  jnz     short loc_18002B6AB
0x18002b664  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002b669  mov     rcx, r13; lpCriticalSection
0x18002b66c  mov     ebx, eax
0x18002b66e  call    cs:__imp_LeaveCriticalSection
0x18002b674  mov     rcx, [rbp+hHash]
0x18002b678  test    rcx, rcx
0x18002b67b  jz      short loc_18002B682
0x18002b67d  call    IISCryptoDestroyHash
0x18002b682  test    rdi, rdi
0x18002b685  jz      short loc_18002B690
0x18002b687  mov     rcx, rdi; pv
0x18002b68a  call    cs:__imp_CoTaskMemFree
0x18002b690  mov     eax, ebx
0x18002b692  lea     r11, [rsp+50h+var_s0]
0x18002b697  mov     rbx, [r11+30h]
0x18002b69b  mov     rsi, [r11+38h]
0x18002b69f  mov     rsp, r11
0x18002b6a2  pop     r15
0x18002b6a4  pop     r14
0x18002b6a6  pop     r13
0x18002b6a8  pop     rdi
0x18002b6a9  pop     rbp
0x18002b6aa  retn
0x18002b6ab  mov     rcx, r13; lpCriticalSection
0x18002b6ae  call    cs:__imp_LeaveCriticalSection
0x18002b6b4  mov     r8d, [rbp+pdwSigLen]; unsigned int
0x18002b6b8  mov     ecx, 62446349h; unsigned int
0x18002b6bd  mov     edx, [rbp+var_10]; unsigned int
0x18002b6c0  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x18002b6c5  mov     rdi, rax
0x18002b6c8  test    rax, rax
0x18002b6cb  jnz     short loc_18002B6D4
0x18002b6cd  mov     ebx, 80070008h
0x18002b6d2  jmp     short loc_18002B674
0x18002b6d4  lea     rbx, [rax+10h]
0x18002b6d8  mov     rdx, r14; Src
0x18002b6db  mov     [rbx], r15d
0x18002b6de  lea     rcx, [rbx+4]; void *
0x18002b6e2  mov     r8d, [rbp+arg_10]
0x18002b6e6  sub     r8, 4; Size
0x18002b6ea  call    memcpy_0
0x18002b6ef  mov     rcx, r13; lpCriticalSection
0x18002b6f2  call    cs:__imp_EnterCriticalSection
0x18002b6f8  mov     eax, [rbp+var_10]
0x18002b6fb  xor     r9d, r9d; dwFlags
0x18002b6fe  mov     rdx, [rbp+hHash]; hHash
0x18002b702  mov     rcx, [rbp+hKey]; hKey
0x18002b706  mov     [rsp+50h+dwBufLen], eax; dwBufLen
0x18002b70a  lea     rax, [rbp+arg_10]
0x18002b70e  mov     [rsp+50h+pdwDataLen], rax; pdwDataLen
0x18002b713  lea     r8d, [r9+1]; Final
0x18002b717  mov     [rsp+50h+pbData], rbx; pbData
0x18002b71c  call    cs:__imp_CryptEncrypt
0x18002b722  test    eax, eax
0x18002b724  jz      loc_18002B664
0x18002b72a  mov     rcx, r13; lpCriticalSection
0x18002b72d  call    cs:__imp_LeaveCriticalSection
0x18002b733  mov     eax, [rdi+8]
0x18002b736  mov     ecx, 0FFFFFFF8h
0x18002b73b  add     eax, 7
0x18002b73e  xor     r9d, r9d; dwFlags
0x18002b741  and     rax, rcx
0x18002b744  xor     r8d, r8d; szDescription
0x18002b747  add     rax, 10h
0x18002b74b  lea     rcx, [rbp+pdwSigLen]
0x18002b74f  mov     [rsp+50h+pdwDataLen], rcx; pdwSigLen
0x18002b754  add     rax, rdi
0x18002b757  mov     rcx, [rbp+hHash]; hHash
0x18002b75b  lea     edx, [r9+2]; dwKeySpec
0x18002b75f  mov     [rsp+50h+pbData], rax; pbSignature
0x18002b764  call    cs:__imp_CryptSignHashA
0x18002b76a  test    eax, eax
0x18002b76c  jnz     short loc_18002B77A
0x18002b76e  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002b773  mov     ebx, eax
0x18002b775  jmp     loc_18002B674
0x18002b77a  mov     rcx, [rbp+hHash]
0x18002b77e  call    IISCryptoDestroyHash
0x18002b783  xor     eax, eax
0x18002b785  mov     [rsi], rdi
0x18002b788  jmp     loc_18002B692
```
