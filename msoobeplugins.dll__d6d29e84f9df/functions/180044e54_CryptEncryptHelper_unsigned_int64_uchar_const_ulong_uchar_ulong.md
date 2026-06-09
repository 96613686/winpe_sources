# CryptEncryptHelper(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180044e54`
- end: `0x180044f5c`
- name: `?CryptEncryptHelper@@YAJ_KPEBEKPEAPEAEPEAK@Z`
- size: `264`
- prototype: `__int64 __usercall@<rax>(HCRYPTKEY hKey@<rcx>, const unsigned __int8 *Src@<rdx>, unsigned int@<r8d>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800445fc`

## callees

- `0x180005d8d`
- `0x18000ac48`
- `0x180044e54`

## import_xrefs

- `CRYPTSP!CryptEncrypt` at `0x180044eab`
- `CRYPTSP!CryptEncrypt` at `0x180044f1c`
- `CRYPTSP!CryptEncrypt` at `0x180044eab`
- `CRYPTSP!CryptEncrypt` at `0x180044f1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f47`

## pseudocode

```c
__int64 __fastcall CryptEncryptHelper(
        HCRYPTKEY hKey,
        const unsigned __int8 *Src,
        DWORD a3,
        unsigned __int8 **a4,
        unsigned int *cb)
{
  unsigned int *v5; // r14
  int Error; // ebx
  void *v10; // rax
  void *pbData; // rdi
  unsigned int v12; // ecx
  DWORD pdwDataLen; // [rsp+90h] [rbp+18h] BYREF

  pdwDataLen = a3;
  v5 = cb;
  *a4 = 0;
  LODWORD(cb) = a3;
  *v5 = 0;
  if ( CryptEncrypt(hKey, 0, 1, 0, 0, (DWORD *)&cb, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v10 = CoTaskMemAlloc((unsigned int)cb);
    pbData = v10;
    if ( !v10 )
      return (unsigned int)-2147024882;
    memcpy_0(v10, Src, (unsigned int)cb);
    if ( CryptEncrypt(hKey, 0, 1, 0, (BYTE *)pbData, &pdwDataLen, (DWORD)cb) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_9:
        CoTaskMemFree(pbData);
        return (unsigned int)Error;
      }
    }
    v12 = (unsigned int)cb;
    *a4 = (unsigned __int8 *)pbData;
    pbData = 0;
    *v5 = v12;
    goto LABEL_9;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180044e54  mov     r11, rsp
0x180044e57  mov     [r11+18h], r8d
0x180044e5b  push    rbx
0x180044e5c  push    rbp
0x180044e5d  push    rsi
0x180044e5e  push    rdi
0x180044e5f  push    r14
0x180044e61  push    r15
0x180044e63  sub     rsp, 48h
0x180044e67  mov     r14, [rsp+78h+cb]
0x180044e6f  lea     rax, [r11+28h]
0x180044e73  mov     rsi, r9
0x180044e76  mov     qword ptr [r9], 0
0x180044e7d  xor     r9d, r9d; dwFlags
0x180044e80  mov     [r11+28h], r8d
0x180044e84  mov     r15, rdx
0x180044e87  mov     [rsp+78h+dwBufLen], 0; dwBufLen
0x180044e8f  mov     [r11-50h], rax
0x180044e93  xor     edx, edx; hHash
0x180044e95  mov     rbp, rcx
0x180044e98  mov     dword ptr [r14], 0
0x180044e9f  lea     r8d, [r9+1]; Final
0x180044ea3  mov     qword ptr [r11-58h], 0
0x180044eab  call    cs:__imp_CryptEncrypt
0x180044eb1  test    eax, eax
0x180044eb3  jnz     short loc_180044EC4
0x180044eb5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180044eba  mov     ebx, eax
0x180044ebc  test    eax, eax
0x180044ebe  js      loc_180044F4D
0x180044ec4  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x180044ecb  call    cs:__imp_CoTaskMemAlloc
0x180044ed1  mov     rdi, rax
0x180044ed4  test    rax, rax
0x180044ed7  jnz     short loc_180044EE0
0x180044ed9  mov     ebx, 8007000Eh
0x180044ede  jmp     short loc_180044F4D
0x180044ee0  mov     r8d, dword ptr [rsp+78h+cb]; Size
0x180044ee8  mov     rdx, r15; Src
0x180044eeb  mov     rcx, rdi; void *
0x180044eee  call    memcpy_0
0x180044ef3  mov     eax, dword ptr [rsp+78h+cb]
0x180044efa  xor     r9d, r9d; dwFlags
0x180044efd  mov     [rsp+78h+dwBufLen], eax; dwBufLen
0x180044f01  xor     edx, edx; hHash
0x180044f03  lea     rax, [rsp+78h+arg_10]
0x180044f0b  mov     rcx, rbp; hKey
0x180044f0e  mov     [rsp+78h+pdwDataLen], rax; pdwDataLen
0x180044f13  lea     r8d, [r9+1]; Final
0x180044f17  mov     [rsp+78h+pbData], rdi; pbData
0x180044f1c  call    cs:__imp_CryptEncrypt
0x180044f22  test    eax, eax
0x180044f24  jz      short loc_180044F2A
0x180044f26  xor     ebx, ebx
0x180044f28  jmp     short loc_180044F35
0x180044f2a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180044f2f  mov     ebx, eax
0x180044f31  test    eax, eax
0x180044f33  js      short loc_180044F44
0x180044f35  mov     ecx, dword ptr [rsp+78h+cb]
0x180044f3c  mov     [rsi], rdi
0x180044f3f  xor     edi, edi
0x180044f41  mov     [r14], ecx
0x180044f44  mov     rcx, rdi; pv
0x180044f47  call    cs:__imp_CoTaskMemFree
0x180044f4d  mov     eax, ebx
0x180044f4f  add     rsp, 48h
0x180044f53  pop     r15
0x180044f55  pop     r14
0x180044f57  pop     rdi
0x180044f58  pop     rsi
0x180044f59  pop     rbp
0x180044f5a  pop     rbx
0x180044f5b  retn
```
