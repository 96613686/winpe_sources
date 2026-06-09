# GetFileChecksum(ushort *,ushort const *,ushort *,ulong)

- ea: `0x14000a400`
- end: `0x14000a5fc`
- name: `?GetFileChecksum@@YAJPEAGPEBG0K@Z`
- size: `508`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006198`

## callees

- `0x140001c50`
- `0x140002920`
- `0x14000a400`
- `0x14000c500`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a49f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a49f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000a50a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000a50a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a599`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a5d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a5d2`
- `CRYPT32!CryptBinaryToStringW` at `0x14000a58b`
- `CRYPT32!CryptBinaryToStringW` at `0x14000a58b`
- `CRYPTSP!CryptDestroyHash` at `0x14000a5c3`
- `CRYPTSP!CryptDestroyHash` at `0x14000a5c3`
- `CRYPTSP!CryptGetHashParam` at `0x14000a564`
- `CRYPTSP!CryptGetHashParam` at `0x14000a564`
- `CRYPTSP!CryptHashData` at `0x14000a52c`
- `CRYPTSP!CryptHashData` at `0x14000a52c`
- `CRYPTSP!CryptCreateHash` at `0x14000a4ce`
- `CRYPTSP!CryptCreateHash` at `0x14000a4ce`

## pseudocode

```c
__int64 __fastcall GetFileChecksum(unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 FileW; // rdi
  int v5; // ebx
  DWORD v6; // r8d
  unsigned int v7; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwDataLen; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcchString; // [rsp+58h] [rbp-A8h] BYREF
  BYTE pbBinary[32]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[520]; // [rsp+80h] [rbp-80h] BYREF
  BYTE pbData[4096]; // [rsp+490h] [rbp+390h] BYREF

  pcchString = 65;
  phHash = 0;
  NumberOfBytesRead = 0;
  pdwDataLen = 32;
  if ( swprintf_s(Buffer, 0x208u, L"%s%s", a1, a2) )
  {
    FileW = (__int64)CreateFileW(Buffer, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
    if ( FileW != -1 && CryptCreateHash(hProv, 0x800Cu, 0, 0, &phHash) )
    {
      v5 = 0;
      while ( 1 )
      {
        v6 = 4096;
        if ( (unsigned int)(20971520 - v5) < 0x1000 )
          v6 = 20971520 - v5;
        if ( !ReadFile((HANDLE)FileW, pbData, v6, &NumberOfBytesRead, 0)
          || !CryptHashData(phHash, pbData, NumberOfBytesRead, 0) )
        {
          break;
        }
        if ( NumberOfBytesRead )
        {
          v5 += NumberOfBytesRead;
          if ( v5 != 20971520 )
            continue;
        }
        if ( CryptGetHashParam(phHash, 2u, pbBinary, &pdwDataLen, 0)
          && CryptBinaryToStringW(pbBinary, 0x20u, 0x4000000Cu, a3, &pcchString) )
        {
          v7 = 0;
          goto LABEL_17;
        }
        break;
      }
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    FileW = -1;
    v7 = -2147467259;
  }
LABEL_17:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v7;
}

```

## disassembly

```asm
0x14000a400  mov     [rsp-8+arg_18], rbx
0x14000a405  push    rbp
0x14000a406  push    rsi
0x14000a407  push    rdi
0x14000a408  lea     rbp, [rsp-13A0h]
0x14000a410  mov     eax, 14A0h
0x14000a415  call    _alloca_probe
0x14000a41a  sub     rsp, rax
0x14000a41d  mov     rax, cs:__security_cookie
0x14000a424  xor     rax, rsp
0x14000a427  mov     [rbp+13B0h+var_20], rax
0x14000a42e  mov     rsi, r8
0x14000a431  mov     qword ptr [rsp+14B0h+dwCreationDisposition], rdx
0x14000a436  mov     r9, rcx
0x14000a439  mov     [rsp+14B0h+pcchString], 41h ; 'A'
0x14000a441  lea     r8, aSS; "%s%s"
0x14000a448  mov     [rsp+14B0h+phHash], 0
0x14000a451  mov     edx, 208h; BufferCount
0x14000a456  mov     [rsp+14B0h+NumberOfBytesRead], 0
0x14000a45e  lea     rcx, [rbp+13B0h+Buffer]; Buffer
0x14000a462  mov     [rsp+14B0h+pdwDataLen], 20h ; ' '
0x14000a46a  call    swprintf_s
0x14000a46f  test    eax, eax
0x14000a471  jz      loc_14000A5B0
0x14000a477  mov     [rsp+14B0h+hTemplateFile], 0; hTemplateFile
0x14000a480  lea     rcx, [rbp+13B0h+Buffer]; lpFileName
0x14000a484  mov     r8d, 3; dwShareMode
0x14000a48a  mov     [rsp+14B0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x14000a492  xor     r9d, r9d; lpSecurityAttributes
0x14000a495  mov     [rsp+14B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x14000a49a  mov     edx, 80000000h; dwDesiredAccess
0x14000a49f  call    cs:__imp_CreateFileW
0x14000a4a5  mov     rdi, rax
0x14000a4a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a4ac  jz      loc_14000A599
0x14000a4b2  mov     rcx, cs:hProv; hProv
0x14000a4b9  lea     rax, [rsp+14B0h+phHash]
0x14000a4be  xor     r9d, r9d; dwFlags
0x14000a4c1  mov     qword ptr [rsp+14B0h+dwCreationDisposition], rax; phHash
0x14000a4c6  xor     r8d, r8d; hKey
0x14000a4c9  mov     edx, 800Ch; Algid
0x14000a4ce  call    cs:__imp_CryptCreateHash
0x14000a4d4  test    eax, eax
0x14000a4d6  jz      loc_14000A599
0x14000a4dc  xor     ebx, ebx
0x14000a4de  mov     r8d, 1000h
0x14000a4e4  mov     qword ptr [rsp+14B0h+dwCreationDisposition], 0; lpOverlapped
0x14000a4ed  mov     eax, 1400000h
0x14000a4f2  lea     r9, [rsp+14B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000a4f7  sub     eax, ebx
0x14000a4f9  lea     rdx, [rbp+13B0h+pbData]; lpBuffer
0x14000a500  cmp     eax, r8d
0x14000a503  mov     rcx, rdi; hFile
0x14000a506  cmovb   r8d, eax; nNumberOfBytesToRead
0x14000a50a  call    cs:__imp_ReadFile
0x14000a510  test    eax, eax
0x14000a512  jz      loc_14000A599
0x14000a518  mov     r8d, [rsp+14B0h+NumberOfBytesRead]; dwDataLen
0x14000a51d  lea     rdx, [rbp+13B0h+pbData]; pbData
0x14000a524  mov     rcx, [rsp+14B0h+phHash]; hHash
0x14000a529  xor     r9d, r9d; dwFlags
0x14000a52c  call    cs:__imp_CryptHashData
0x14000a532  test    eax, eax
0x14000a534  jz      short loc_14000A599
0x14000a536  mov     eax, [rsp+14B0h+NumberOfBytesRead]
0x14000a53a  test    eax, eax
0x14000a53c  jz      short loc_14000A548
0x14000a53e  add     ebx, eax
0x14000a540  cmp     ebx, 1400000h
0x14000a546  jnz     short loc_14000A4DE
0x14000a548  mov     rcx, [rsp+14B0h+phHash]; hHash
0x14000a54d  lea     r9, [rsp+14B0h+pdwDataLen]; pdwDataLen
0x14000a552  lea     r8, [rsp+14B0h+pbBinary]; pbData
0x14000a557  mov     [rsp+14B0h+dwCreationDisposition], 0; dwFlags
0x14000a55f  mov     edx, 2; dwParam
0x14000a564  call    cs:__imp_CryptGetHashParam
0x14000a56a  test    eax, eax
0x14000a56c  jz      short loc_14000A599
0x14000a56e  lea     rax, [rsp+14B0h+pcchString]
0x14000a573  mov     r9, rsi; pszString
0x14000a576  mov     edx, 20h ; ' '; cbBinary
0x14000a57b  mov     qword ptr [rsp+14B0h+dwCreationDisposition], rax; pcchString
0x14000a580  mov     r8d, 4000000Ch; dwFlags
0x14000a586  lea     rcx, [rsp+14B0h+pbBinary]; pbBinary
0x14000a58b  call    cs:__imp_CryptBinaryToStringW
0x14000a591  test    eax, eax
0x14000a593  jz      short loc_14000A599
0x14000a595  xor     ebx, ebx
0x14000a597  jmp     short loc_14000A5B9
0x14000a599  call    cs:__imp_GetLastError
0x14000a59f  mov     ebx, eax
0x14000a5a1  test    eax, eax
0x14000a5a3  jle     short loc_14000A5B9
0x14000a5a5  movzx   ebx, ax
0x14000a5a8  or      ebx, 80070000h
0x14000a5ae  jmp     short loc_14000A5B9
0x14000a5b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000a5b4  mov     ebx, 80004005h
0x14000a5b9  mov     rcx, [rsp+14B0h+phHash]; hHash
0x14000a5be  test    rcx, rcx
0x14000a5c1  jz      short loc_14000A5C9
0x14000a5c3  call    cs:__imp_CryptDestroyHash
0x14000a5c9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000a5cd  jz      short loc_14000A5D8
0x14000a5cf  mov     rcx, rdi; hObject
0x14000a5d2  call    cs:__imp_CloseHandle
0x14000a5d8  mov     eax, ebx
0x14000a5da  mov     rcx, [rbp+13B0h+var_20]
0x14000a5e1  xor     rcx, rsp; StackCookie
0x14000a5e4  call    __security_check_cookie
0x14000a5e9  mov     rbx, [rsp+14B0h+arg_18]
0x14000a5f1  add     rsp, 14A0h
0x14000a5f8  pop     rdi
0x14000a5f9  pop     rsi
0x14000a5fa  pop     rbp
0x14000a5fb  retn
```
