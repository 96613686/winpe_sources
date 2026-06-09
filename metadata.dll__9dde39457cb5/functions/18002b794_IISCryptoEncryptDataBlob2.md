# IISCryptoEncryptDataBlob2

- ea: `0x18002b794`
- end: `0x18002b950`
- name: `IISCryptoEncryptDataBlob2`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002a058`

## callees

- `0x18002937c`
- `0x180029aa4`
- `0x180029bc8`
- `0x180029c24`
- `0x180029c90`
- `0x180029e24`
- `0x18002b794`
- `0x18003098e`

## import_xrefs

- `ADVAPI32!CryptEncrypt` at `0x18002b864`
- `ADVAPI32!CryptEncrypt` at `0x18002b926`
- `ADVAPI32!CryptEncrypt` at `0x18002b864`
- `ADVAPI32!CryptEncrypt` at `0x18002b926`
- `ole32!CoTaskMemFree` at `0x18002b894`
- `ole32!CoTaskMemFree` at `0x18002b894`
- `KERNEL32!LeaveCriticalSection` at `0x18002b878`
- `KERNEL32!LeaveCriticalSection` at `0x18002b8b8`
- `KERNEL32!LeaveCriticalSection` at `0x18002b937`
- `KERNEL32!LeaveCriticalSection` at `0x18002b878`
- `KERNEL32!LeaveCriticalSection` at `0x18002b8b8`
- `KERNEL32!LeaveCriticalSection` at `0x18002b937`
- `KERNEL32!EnterCriticalSection` at `0x18002b83c`
- `KERNEL32!EnterCriticalSection` at `0x18002b8fc`
- `KERNEL32!EnterCriticalSection` at `0x18002b83c`
- `KERNEL32!EnterCriticalSection` at `0x18002b8fc`

## pseudocode

```c
__int64 __fastcall IISCryptoEncryptDataBlob2(
        struct _IC_BLOB **a1,
        const void *a2,
        DWORD a3,
        int a4,
        HCRYPTPROV hProv,
        HCRYPTKEY hKey)
{
  __int64 result; // rax
  struct _IC_BLOB *v10; // rdi
  int HashLength; // ebx
  struct _IC_BLOB *Blob; // rax
  BYTE *pbData; // rbx
  DWORD pdwDataLen; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-Ch] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwBufLen; // [rsp+90h] [rbp+40h] BYREF

  dwBufLen = a3;
  pdwDataLen = 0;
  v15 = 0;
  if ( !dword_180048964 )
  {
    if ( hProv == 1984918096 && hKey == 1800627539 )
      return IISCryptoCreateCleartextBlob(a1, a2, a3);
    else
      return 2147942487LL;
  }
  v10 = 0;
  hHash = 0;
  HashLength = IISCryptoCreateHash(&hHash, hProv);
  if ( HashLength >= 0 )
  {
    HashLength = IcpGetHashLength(&v15, hProv);
    if ( HashLength >= 0 )
    {
      dwBufLen += 4;
      pdwDataLen = dwBufLen;
      EnterCriticalSection(&IcpGlobals);
      if ( CryptEncrypt(hKey, 0, 1, 0, 0, &pdwDataLen, dwBufLen) )
      {
        LeaveCriticalSection(&IcpGlobals);
        Blob = IcpCreateBlob(1648649033, pdwDataLen, v15);
        v10 = Blob;
        if ( !Blob )
        {
          HashLength = -2147024888;
          goto LABEL_10;
        }
        pbData = (BYTE *)Blob + 16;
        *((_DWORD *)Blob + 4) = a4;
        memcpy_0((char *)Blob + 20, a2, dwBufLen - 4LL);
        EnterCriticalSection(&IcpGlobals);
        if ( CryptEncrypt(hKey, hHash, 1, 0, pbData, &dwBufLen, pdwDataLen) )
        {
          LeaveCriticalSection(&IcpGlobals);
          IISCryptoDestroyHash(hHash);
          result = 0;
          *a1 = v10;
          return result;
        }
      }
      HashLength = IcpGetLastError();
      LeaveCriticalSection(&IcpGlobals);
    }
  }
LABEL_10:
  if ( hHash )
    IISCryptoDestroyHash(hHash);
  if ( v10 )
    CoTaskMemFree(v10);
  return (unsigned int)HashLength;
}

```

## disassembly

```asm
0x18002b794  mov     [rsp-28h+arg_0], rbx
0x18002b799  mov     [rsp-28h+arg_8], rsi
0x18002b79e  mov     [rsp-28h+arg_10], r8d
0x18002b7a3  push    rbp
0x18002b7a4  push    rdi
0x18002b7a5  push    r13
0x18002b7a7  push    r14
0x18002b7a9  push    r15
0x18002b7ab  mov     rbp, rsp
0x18002b7ae  sub     rsp, 50h
0x18002b7b2  cmp     cs:dword_180048964, 0
0x18002b7b9  mov     r15d, r9d
0x18002b7bc  mov     r14, rdx
0x18002b7bf  mov     [rbp+var_10], 0
0x18002b7c6  mov     rsi, rcx
0x18002b7c9  mov     [rbp+var_C], 0
0x18002b7d0  jnz     short loc_18002B7FA
0x18002b7d2  cmp     [rbp+hProv], 764F7250h
0x18002b7da  jnz     short loc_18002B7F0
0x18002b7dc  cmp     [rbp+hKey], 6B536553h
0x18002b7e4  jnz     short loc_18002B7F0
0x18002b7e6  call    IISCryptoCreateCleartextBlob
0x18002b7eb  jmp     loc_18002B89C
0x18002b7f0  mov     eax, 80070057h
0x18002b7f5  jmp     loc_18002B89C
0x18002b7fa  mov     rdx, [rbp+hProv]; hProv
0x18002b7fe  lea     rcx, [rbp+hHash]; phHash
0x18002b802  xor     edi, edi
0x18002b804  mov     [rbp+hHash], rdi
0x18002b808  call    IISCryptoCreateHash
0x18002b80d  mov     ebx, eax
0x18002b80f  test    eax, eax
0x18002b811  js      short loc_18002B87E
0x18002b813  mov     rdx, [rbp+hProv]; unsigned __int64
0x18002b817  lea     rcx, [rbp+var_C]; unsigned int *
0x18002b81b  call    ?IcpGetHashLength@@YAJPEAK_K@Z; IcpGetHashLength(ulong *,unsigned __int64)
0x18002b820  mov     ebx, eax
0x18002b822  test    eax, eax
0x18002b824  js      short loc_18002B87E
0x18002b826  mov     eax, [rbp+arg_10]
0x18002b829  lea     r13, ?IcpGlobals@@3U_IC_GLOBALS@@A; _IC_GLOBALS IcpGlobals
0x18002b830  add     eax, 4
0x18002b833  mov     rcx, r13; lpCriticalSection
0x18002b836  mov     [rbp+arg_10], eax
0x18002b839  mov     [rbp+var_10], eax
0x18002b83c  call    cs:__imp_EnterCriticalSection
0x18002b842  mov     eax, [rbp+arg_10]
0x18002b845  lea     r8d, [rdi+1]; Final
0x18002b849  mov     rcx, [rbp+hKey]; hKey
0x18002b84d  xor     r9d, r9d; dwFlags
0x18002b850  mov     [rsp+50h+dwBufLen], eax; dwBufLen
0x18002b854  xor     edx, edx; hHash
0x18002b856  lea     rax, [rbp+var_10]
0x18002b85a  mov     [rsp+50h+pdwDataLen], rax; pdwDataLen
0x18002b85f  mov     [rsp+50h+pbData], rdi; pbData
0x18002b864  call    cs:__imp_CryptEncrypt
0x18002b86a  test    eax, eax
0x18002b86c  jnz     short loc_18002B8B5
0x18002b86e  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002b873  mov     rcx, r13; lpCriticalSection
0x18002b876  mov     ebx, eax
0x18002b878  call    cs:__imp_LeaveCriticalSection
0x18002b87e  mov     rcx, [rbp+hHash]
0x18002b882  test    rcx, rcx
0x18002b885  jz      short loc_18002B88C
0x18002b887  call    IISCryptoDestroyHash
0x18002b88c  test    rdi, rdi
0x18002b88f  jz      short loc_18002B89A
0x18002b891  mov     rcx, rdi; pv
0x18002b894  call    cs:__imp_CoTaskMemFree
0x18002b89a  mov     eax, ebx
0x18002b89c  lea     r11, [rsp+50h+var_s0]
0x18002b8a1  mov     rbx, [r11+30h]
0x18002b8a5  mov     rsi, [r11+38h]
0x18002b8a9  mov     rsp, r11
0x18002b8ac  pop     r15
0x18002b8ae  pop     r14
0x18002b8b0  pop     r13
0x18002b8b2  pop     rdi
0x18002b8b3  pop     rbp
0x18002b8b4  retn
0x18002b8b5  mov     rcx, r13; lpCriticalSection
0x18002b8b8  call    cs:__imp_LeaveCriticalSection
0x18002b8be  mov     r8d, [rbp+var_C]; unsigned int
0x18002b8c2  mov     ecx, 62446349h; unsigned int
0x18002b8c7  mov     edx, [rbp+var_10]; unsigned int
0x18002b8ca  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x18002b8cf  mov     rdi, rax
0x18002b8d2  test    rax, rax
0x18002b8d5  jnz     short loc_18002B8DE
0x18002b8d7  mov     ebx, 80070008h
0x18002b8dc  jmp     short loc_18002B87E
0x18002b8de  lea     rbx, [rax+10h]
0x18002b8e2  mov     rdx, r14; Src
0x18002b8e5  mov     [rbx], r15d
0x18002b8e8  lea     rcx, [rbx+4]; void *
0x18002b8ec  mov     r8d, [rbp+arg_10]
0x18002b8f0  sub     r8, 4; Size
0x18002b8f4  call    memcpy_0
0x18002b8f9  mov     rcx, r13; lpCriticalSection
0x18002b8fc  call    cs:__imp_EnterCriticalSection
0x18002b902  mov     eax, [rbp+var_10]
0x18002b905  xor     r9d, r9d; dwFlags
0x18002b908  mov     rdx, [rbp+hHash]; hHash
0x18002b90c  mov     rcx, [rbp+hKey]; hKey
0x18002b910  mov     [rsp+50h+dwBufLen], eax; dwBufLen
0x18002b914  lea     rax, [rbp+arg_10]
0x18002b918  mov     [rsp+50h+pdwDataLen], rax; pdwDataLen
0x18002b91d  lea     r8d, [r9+1]; Final
0x18002b921  mov     [rsp+50h+pbData], rbx; pbData
0x18002b926  call    cs:__imp_CryptEncrypt
0x18002b92c  test    eax, eax
0x18002b92e  jz      loc_18002B86E
0x18002b934  mov     rcx, r13; lpCriticalSection
0x18002b937  call    cs:__imp_LeaveCriticalSection
0x18002b93d  mov     rcx, [rbp+hHash]
0x18002b941  call    IISCryptoDestroyHash
0x18002b946  xor     eax, eax
0x18002b948  mov     [rsi], rdi
0x18002b94b  jmp     loc_18002B89C
```
