# Base64ToBytes(ushort const *,tagPROPVARIANT &)

- ea: `0x18002a990`
- end: `0x18002aa7b`
- name: `?Base64ToBytes@@YAJPEBGAEAUtagPROPVARIANT@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(LPCWSTR pszString, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002a990`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa46`
- `CRYPT32!CryptStringToBinaryW` at `0x18002a9cf`
- `CRYPT32!CryptStringToBinaryW` at `0x18002aa1f`
- `CRYPT32!CryptStringToBinaryW` at `0x18002a9cf`
- `CRYPT32!CryptStringToBinaryW` at `0x18002aa1f`

## pseudocode

```c
__int64 __fastcall Base64ToBytes(LPCWSTR pszString, struct tagPROPVARIANT *a2)
{
  BYTE *v4; // rbx
  unsigned int v5; // ecx
  signed int LastError; // eax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF
  DWORD pcbBinary; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(cb) = 0;
  if ( CryptStringToBinaryW(pszString, 0, 1u, 0, (DWORD *)&cb, 0, 0) )
  {
    v4 = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( v4 )
    {
      pcbBinary = cb;
      if ( CryptStringToBinaryW(pszString, 0, 1u, v4, &pcbBinary, 0, 0) )
      {
        v5 = 0;
        a2->lVal = pcbBinary;
        a2->vt = 65;
        a2->bstrblobVal.pData = v4;
      }
      else
      {
        CoTaskMemFree(v4);
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x18002a990  mov     rax, rsp
0x18002a993  mov     [rax+8], rbx
0x18002a997  mov     [rax+10h], rsi
0x18002a99b  push    rdi
0x18002a99c  sub     rsp, 40h
0x18002a9a0  mov     qword ptr [rax-18h], 0
0x18002a9a8  xor     r9d, r9d; pbBinary
0x18002a9ab  mov     qword ptr [rax-20h], 0
0x18002a9b3  mov     rdi, rdx
0x18002a9b6  mov     dword ptr [rax+18h], 0
0x18002a9bd  lea     rax, [rax+18h]
0x18002a9c1  xor     edx, edx; cchString
0x18002a9c3  mov     [rsp+48h+pcbBinary], rax; pcbBinary
0x18002a9c8  lea     r8d, [r9+1]; dwFlags
0x18002a9cc  mov     rsi, rcx
0x18002a9cf  call    cs:__imp_CryptStringToBinaryW
0x18002a9d5  test    eax, eax
0x18002a9d7  jz      loc_18002AA64
0x18002a9dd  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x18002a9e1  call    cs:__imp_CoTaskMemAlloc
0x18002a9e7  mov     rbx, rax
0x18002a9ea  test    rax, rax
0x18002a9ed  jz      short loc_18002AA5D
0x18002a9ef  mov     ecx, dword ptr [rsp+48h+cb]
0x18002a9f3  lea     rax, [rsp+48h+arg_18]
0x18002a9f8  xor     edx, edx; cchString
0x18002a9fa  mov     [rsp+48h+arg_18], ecx
0x18002a9fe  mov     [rsp+48h+pdwFlags], 0; pdwFlags
0x18002aa07  mov     r9, rbx; pbBinary
0x18002aa0a  mov     [rsp+48h+pdwSkip], 0; pdwSkip
0x18002aa13  mov     rcx, rsi; pszString
0x18002aa16  mov     [rsp+48h+pcbBinary], rax; pcbBinary
0x18002aa1b  lea     r8d, [rdx+1]; dwFlags
0x18002aa1f  call    cs:__imp_CryptStringToBinaryW
0x18002aa25  test    eax, eax
0x18002aa27  jz      short loc_18002AA3D
0x18002aa29  mov     eax, [rsp+48h+arg_18]
0x18002aa2d  xor     ecx, ecx
0x18002aa2f  mov     [rdi+8], eax
0x18002aa32  mov     word ptr [rdi], 41h ; 'A'
0x18002aa37  mov     [rdi+10h], rbx
0x18002aa3b  jmp     short loc_18002AA69
0x18002aa3d  mov     rcx, rbx; pv
0x18002aa40  call    cs:__imp_CoTaskMemFree
0x18002aa46  call    cs:__imp_GetLastError
0x18002aa4c  mov     ecx, eax
0x18002aa4e  test    eax, eax
0x18002aa50  jle     short loc_18002AA69
0x18002aa52  movzx   ecx, ax
0x18002aa55  or      ecx, 80070000h
0x18002aa5b  jmp     short loc_18002AA69
0x18002aa5d  mov     ecx, 8007000Eh
0x18002aa62  jmp     short loc_18002AA69
0x18002aa64  mov     ecx, 80070057h
0x18002aa69  mov     rbx, [rsp+48h+arg_0]
0x18002aa6e  mov     eax, ecx
0x18002aa70  mov     rsi, [rsp+48h+arg_8]
0x18002aa75  add     rsp, 40h
0x18002aa79  pop     rdi
0x18002aa7a  retn
```
