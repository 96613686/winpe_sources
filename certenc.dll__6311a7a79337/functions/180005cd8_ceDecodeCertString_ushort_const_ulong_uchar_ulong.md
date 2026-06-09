# ceDecodeCertString(ushort * const,ulong,uchar * *,ulong *)

- ea: `0x180005cd8`
- end: `0x180005e3f`
- name: `?ceDecodeCertString@@YAJQEAGKPEAPEAEPEAK@Z`
- size: `359`
- prototype: `__int64 __fastcall(OLECHAR *pszString, DWORD dwFlags, unsigned __int8 **, unsigned int *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c00`
- `0x180002460`
- `0x180002be0`
- `0x1800034b0`
- `0x180003910`
- `0x180004d00`
- `0x180004f90`
- `0x180007b40`

## callees

- `0x180005b6c`
- `0x180005cd8`
- `0x1800064e0`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180005d1b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180005d4d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180005d95`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180005d1b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180005d4d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180005d95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dbd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e0e`
- `CRYPT32!CryptStringToBinaryW` at `0x180005df5`
- `CRYPT32!CryptStringToBinaryW` at `0x180005df5`

## pseudocode

```c
__int64 __fastcall ceDecodeCertString(OLECHAR *pszString, DWORD dwFlags, unsigned __int8 **a3, unsigned int *a4)
{
  DWORD v4; // eax
  DWORD v7; // ebx
  DWORD v9; // eax
  DWORD v10; // eax
  bool v11; // di
  unsigned __int64 v12; // rdx
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  int v18; // eax
  unsigned __int8 *v19; // rdi
  UINT v20; // ebx
  BOOL i; // eax
  BYTE *v22; // rax
  unsigned int *pdwSkip; // [rsp+28h] [rbp-30h]
  unsigned int *pdwFlags; // [rsp+30h] [rbp-28h]
  SIZE_T uBytes; // [rsp+68h] [rbp+10h] BYREF

  *a3 = 0;
  v4 = dwFlags & 0xDFFFFFFF;
  v7 = dwFlags;
  if ( (dwFlags & 0xDFFFFFFF) > 7 )
  {
    v13 = v4 - 8;
    if ( v13 )
    {
      v10 = v13 - 1;
      if ( v10 )
      {
LABEL_9:
        v14 = v10 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            if ( v15 - 1 >= 2 )
              return (unsigned int)-2147024809;
          }
        }
      }
    }
  }
  else if ( (dwFlags & 0xDFFFFFFF) != 7 )
  {
    if ( v4 )
    {
      v9 = v4 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( !v10 )
        {
          v11 = 0;
          LODWORD(v12) = SysStringByteLen(pszString);
          goto LABEL_16;
        }
        goto LABEL_9;
      }
    }
  }
  v17 = SysStringByteLen(pszString);
  v18 = 6;
  v12 = (unsigned __int64)(v17 + 1) >> 1;
  if ( v7 != 7 )
    v18 = v7;
  v11 = v7 == 7;
  v7 = v18;
LABEL_16:
  v16 = ceCryptStringToBinary(pszString, v12, v7, a3, a4, pdwSkip, pdwFlags);
  if ( v16 && v11 )
  {
    v19 = 0;
    v20 = SysStringByteLen(pszString);
    LODWORD(uBytes) = 0;
    for ( i = CryptStringToBinaryW(pszString, v20, 2u, 0, (DWORD *)&uBytes, 0, 0);
          i;
          i = CryptStringToBinaryW(pszString, v20, 2u, v22, (DWORD *)&uBytes, 0, 0) )
    {
      if ( v19 )
      {
        v16 = 0;
        *a4 = uBytes;
        *a3 = v19;
        return v16;
      }
      v22 = (BYTE *)LocalAlloc(0, (unsigned int)uBytes);
      v19 = v22;
      if ( !v22 )
        return (unsigned int)-2147024882;
    }
    v16 = ceHLastError();
    if ( v19 )
      LocalFree(v19);
  }
  return v16;
}

```

## disassembly

```asm
0x180005cd8  mov     [rsp+arg_0], rbx
0x180005cdd  mov     [rsp+arg_10], rsi
0x180005ce2  push    rdi
0x180005ce3  push    r14
0x180005ce5  push    r15
0x180005ce7  sub     rsp, 40h
0x180005ceb  mov     eax, edx
0x180005ced  mov     qword ptr [r8], 0
0x180005cf4  btr     eax, 1Dh
0x180005cf8  mov     r15, r9
0x180005cfb  mov     r14, r8
0x180005cfe  mov     ebx, edx
0x180005d00  mov     rsi, rcx
0x180005d03  cmp     eax, 7
0x180005d06  ja      short loc_180005D25
0x180005d08  jz      short loc_180005D4D
0x180005d0a  test    eax, eax
0x180005d0c  jz      short loc_180005D4D
0x180005d0e  sub     eax, 1
0x180005d11  jz      short loc_180005D4D
0x180005d13  sub     eax, 1
0x180005d16  jnz     short loc_180005D2F
0x180005d18  xor     dil, dil
0x180005d1b  call    cs:__imp_SysStringByteLen
0x180005d21  mov     edx, eax
0x180005d23  jmp     short loc_180005D6C
0x180005d25  sub     eax, 8
0x180005d28  jz      short loc_180005D4D
0x180005d2a  sub     eax, 1
0x180005d2d  jz      short loc_180005D4D
0x180005d2f  sub     eax, 1
0x180005d32  jz      short loc_180005D4D
0x180005d34  sub     eax, 1
0x180005d37  jz      short loc_180005D4D
0x180005d39  sub     eax, 1
0x180005d3c  jz      short loc_180005D4D
0x180005d3e  cmp     eax, 1
0x180005d41  jz      short loc_180005D4D
0x180005d43  mov     ebx, 80070057h
0x180005d48  jmp     loc_180005E14
0x180005d4d  call    cs:__imp_SysStringByteLen
0x180005d53  mov     edx, eax
0x180005d55  mov     eax, 6
0x180005d5a  inc     rdx
0x180005d5d  shr     rdx, 1; cchString
0x180005d60  cmp     ebx, 7
0x180005d63  cmovnz  eax, ebx
0x180005d66  setz    dil
0x180005d6a  mov     ebx, eax
0x180005d6c  mov     r9, r14; unsigned __int8 **
0x180005d6f  mov     [rsp+58h+pcbBinary], r15; unsigned int *
0x180005d74  mov     r8d, ebx; dwFlags
0x180005d77  mov     rcx, rsi; pszString
0x180005d7a  call    ?ceCryptStringToBinary@@YAJPEBGKKPEAPEAEPEAK22@Z; ceCryptStringToBinary(ushort const *,ulong,ulong,uchar * *,ulong *,ulong *,ulong *)
0x180005d7f  mov     ebx, eax
0x180005d81  test    eax, eax
0x180005d83  jz      loc_180005E14
0x180005d89  test    dil, dil
0x180005d8c  jz      loc_180005E14
0x180005d92  mov     rcx, rsi; bstr
0x180005d95  call    cs:__imp_SysStringByteLen
0x180005d9b  xor     edi, edi
0x180005d9d  mov     ebx, eax
0x180005d9f  mov     [rsp+58h+pdwFlags], rdi
0x180005da4  xor     r9d, r9d
0x180005da7  mov     [rsp+58h+pdwSkip], rdi
0x180005dac  mov     dword ptr [rsp+58h+uBytes], edi
0x180005db0  jmp     short loc_180005DE0
0x180005db2  test    rdi, rdi
0x180005db5  jnz     short loc_180005E31
0x180005db7  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x180005dbb  xor     ecx, ecx; uFlags
0x180005dbd  call    cs:__imp_LocalAlloc
0x180005dc3  mov     rdi, rax
0x180005dc6  test    rax, rax
0x180005dc9  jz      short loc_180005E2A
0x180005dcb  mov     [rsp+58h+pdwFlags], 0; pdwFlags
0x180005dd4  mov     r9, rax; pbBinary
0x180005dd7  mov     [rsp+58h+pdwSkip], 0; pdwSkip
0x180005de0  lea     rax, [rsp+58h+uBytes]
0x180005de5  mov     r8d, 2; dwFlags
0x180005deb  mov     edx, ebx; cchString
0x180005ded  mov     [rsp+58h+pcbBinary], rax; pcbBinary
0x180005df2  mov     rcx, rsi; pszString
0x180005df5  call    cs:__imp_CryptStringToBinaryW
0x180005dfb  test    eax, eax
0x180005dfd  jnz     short loc_180005DB2
0x180005dff  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180005e04  mov     ebx, eax
0x180005e06  test    rdi, rdi
0x180005e09  jz      short loc_180005E14
0x180005e0b  mov     rcx, rdi; hMem
0x180005e0e  call    cs:__imp_LocalFree
0x180005e14  mov     rsi, [rsp+58h+arg_10]
0x180005e19  mov     eax, ebx
0x180005e1b  mov     rbx, [rsp+58h+arg_0]
0x180005e20  add     rsp, 40h
0x180005e24  pop     r15
0x180005e26  pop     r14
0x180005e28  pop     rdi
0x180005e29  retn
0x180005e2a  mov     ebx, 8007000Eh
0x180005e2f  jmp     short loc_180005E14
0x180005e31  mov     eax, dword ptr [rsp+58h+uBytes]
0x180005e35  xor     ebx, ebx
0x180005e37  mov     [r15], eax
0x180005e3a  mov     [r14], rdi
0x180005e3d  jmp     short loc_180005E14
```
