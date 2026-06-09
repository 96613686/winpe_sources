# CryptExportKeyHelper(unsigned __int64,unsigned __int64,ulong,uchar * *,ulong *)

- ea: `0x180044f64`
- end: `0x180045045`
- name: `?CryptExportKeyHelper@@YAJ_K0KPEAPEAEPEAK@Z`
- size: `225`
- prototype: `__int64 __usercall@<rax>(HCRYPTKEY hKey@<rcx>, HCRYPTKEY hExpKey@<rdx>, unsigned int@<r8d>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800445fc`

## callees

- `0x18000ac48`
- `0x180044f64`

## import_xrefs

- `CRYPTSP!CryptExportKey` at `0x180044fb5`
- `CRYPTSP!CryptExportKey` at `0x180045005`
- `CRYPTSP!CryptExportKey` at `0x180044fb5`
- `CRYPTSP!CryptExportKey` at `0x180045005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045030`

## pseudocode

```c
__int64 __fastcall CryptExportKeyHelper(
        HCRYPTKEY hKey,
        HCRYPTKEY hExpKey,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int *v5; // r14
  int Error; // ebx
  void *pbData; // rdi
  unsigned int v11; // ecx
  SIZE_T cb; // [rsp+80h] [rbp+18h] BYREF

  v5 = a5;
  *a4 = 0;
  LODWORD(cb) = 0;
  *v5 = 0;
  if ( CryptExportKey(hKey, hExpKey, 1u, 0, 0, (DWORD *)&cb) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pbData = CoTaskMemAlloc((unsigned int)cb);
    if ( !pbData )
      return (unsigned int)-2147024882;
    if ( CryptExportKey(hKey, hExpKey, 1u, 0, (BYTE *)pbData, (DWORD *)&cb) )
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
    v11 = cb;
    *a4 = (unsigned __int8 *)pbData;
    pbData = 0;
    *v5 = v11;
    goto LABEL_9;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180044f64  mov     r11, rsp
0x180044f67  mov     [r11+18h], r8d
0x180044f6b  push    rbx
0x180044f6c  push    rbp
0x180044f6d  push    rsi
0x180044f6e  push    rdi
0x180044f6f  push    r14
0x180044f71  push    r15
0x180044f73  sub     rsp, 38h
0x180044f77  mov     r14, [rsp+68h+arg_20]
0x180044f7f  lea     rax, [r11+18h]
0x180044f83  mov     rsi, r9
0x180044f86  mov     qword ptr [r9], 0
0x180044f8d  xor     r9d, r9d; dwFlags
0x180044f90  mov     [r11-40h], rax
0x180044f94  mov     rbp, rdx
0x180044f97  mov     dword ptr [r11+18h], 0
0x180044f9f  mov     r15, rcx
0x180044fa2  mov     dword ptr [r14], 0
0x180044fa9  mov     qword ptr [r11-48h], 0
0x180044fb1  lea     r8d, [r9+1]; dwBlobType
0x180044fb5  call    cs:__imp_CryptExportKey
0x180044fbb  test    eax, eax
0x180044fbd  jnz     short loc_180044FCA
0x180044fbf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180044fc4  mov     ebx, eax
0x180044fc6  test    eax, eax
0x180044fc8  js      short loc_180045036
0x180044fca  mov     ecx, dword ptr [rsp+68h+cb]; cb
0x180044fd1  call    cs:__imp_CoTaskMemAlloc
0x180044fd7  mov     rdi, rax
0x180044fda  test    rax, rax
0x180044fdd  jnz     short loc_180044FE6
0x180044fdf  mov     ebx, 8007000Eh
0x180044fe4  jmp     short loc_180045036
0x180044fe6  xor     r9d, r9d; dwFlags
0x180044fe9  lea     rax, [rsp+68h+cb]
0x180044ff1  mov     [rsp+68h+pdwDataLen], rax; pdwDataLen
0x180044ff6  mov     rdx, rbp; hExpKey
0x180044ff9  mov     rcx, r15; hKey
0x180044ffc  mov     [rsp+68h+pbData], rdi; pbData
0x180045001  lea     r8d, [r9+1]; dwBlobType
0x180045005  call    cs:__imp_CryptExportKey
0x18004500b  test    eax, eax
0x18004500d  jz      short loc_180045013
0x18004500f  xor     ebx, ebx
0x180045011  jmp     short loc_18004501E
0x180045013  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045018  mov     ebx, eax
0x18004501a  test    eax, eax
0x18004501c  js      short loc_18004502D
0x18004501e  mov     ecx, dword ptr [rsp+68h+cb]
0x180045025  mov     [rsi], rdi
0x180045028  xor     edi, edi
0x18004502a  mov     [r14], ecx
0x18004502d  mov     rcx, rdi; pv
0x180045030  call    cs:__imp_CoTaskMemFree
0x180045036  mov     eax, ebx
0x180045038  add     rsp, 38h
0x18004503c  pop     r15
0x18004503e  pop     r14
0x180045040  pop     rdi
0x180045041  pop     rsi
0x180045042  pop     rbp
0x180045043  pop     rbx
0x180045044  retn
```
