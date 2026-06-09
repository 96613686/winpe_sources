# TextLogWriteEntry

- ea: `0x180005bcc`
- end: `0x180005e56`
- name: `TextLogWriteEntry`
- size: `650`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005e5c`
- `0x180006590`

## callees

- `0x1800044e0`
- `0x18000512c`
- `0x180005bcc`
- `0x180008128`
- `0x180008248`
- `0x18000828c`
- `0x18000a1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c9c`
- `KERNEL32!GetLocalTime` at `0x180005d06`
- `KERNEL32!GetLocalTime` at `0x180005d06`

## pseudocode

```c
__int64 __fastcall TextLogWriteEntry(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v6; // r12d
  __int64 v7; // rax
  __int64 v8; // rbx
  DWORD LastError; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  const char *v13; // rdx
  int v14; // r15d
  BOOL v15; // esi
  BOOL v16; // r14d
  int v17; // r12d
  HRESULT v18; // eax
  DWORD v19; // edi
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-39h] BYREF
  char v24[24]; // [rsp+60h] [rbp-29h] BYREF
  char pszDest[24]; // [rsp+78h] [rbp-11h] BYREF

  v6 = a2;
  v7 = pStrBufCreate(0);
  v8 = v7;
  if ( !v7 )
  {
    StrBufDestroyA(0);
    LastError = GetLastError();
LABEL_41:
    v19 = LastError;
    goto LABEL_42;
  }
  v10 = *(_QWORD *)(v7 + 8);
  v11 = -1;
  do
    ++v11;
  while ( *(_BYTE *)(v10 + v11) );
  *(_DWORD *)(v8 + 4) = v11;
  v12 = a5 & 0xF;
  if ( v12 == 1 )
  {
    v13 = "!!!  ";
  }
  else if ( v12 == 2 )
  {
    v13 = "!    ";
  }
  else if ( (a5 & 0x10) != 0 )
  {
    v13 = ">>>  ";
  }
  else if ( (a5 & 0x20) != 0 )
  {
    v13 = "<<<  ";
  }
  else
  {
    v13 = "   . ";
    if ( (a5 & 0x40) == 0 )
      v13 = "     ";
  }
  if ( !(unsigned int)StrBufCatA(v8, v13) )
  {
LABEL_16:
    LastError = GetLastError();
    goto LABEL_41;
  }
  v14 = 0;
  if ( (a5 & 0x30) != 0 )
  {
    v15 = (a5 & 0x10000) != 0;
    v16 = v15;
    if ( (a5 & 0x10000) == 0 )
    {
LABEL_35:
      if ( (unsigned int)StrBufCatA(v8, a3)
        && (!v15 || (!v16 || (unsigned int)StrBufCatA(v8, v24)) && (unsigned int)StrBufCatA(v8, pszDest)) )
      {
        LastError = TextLogInsertString(a1, v6, *(_QWORD *)(v8 + 8));
        goto LABEL_41;
      }
      goto LABEL_16;
    }
    v17 = 1;
  }
  else
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 12LL) & 0x8000000) != 0 )
    {
      v14 = 1;
    }
    else
    {
      if ( (a5 & 0x10000) == 0 )
        goto LABEL_33;
      v15 = 1;
    }
  }
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v18 = StringCchPrintfA(
          pszDest,
          0x14u,
          " %02d:%02d:%02d.%03d",
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
  if ( v18 >= 0 )
  {
    if ( !v16
      || (v18 = StringCchPrintfA(v24, 0x14u, " %04d/%02d/%02d", SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay),
          v18 >= 0) )
    {
      if ( v14 && (v16 && !(unsigned int)StrBufCatA(v8, v24) || !(unsigned int)StrBufCatA(v8, pszDest)) )
        goto LABEL_16;
      if ( v17 )
      {
LABEL_34:
        v6 = a2;
        goto LABEL_35;
      }
LABEL_33:
      if ( !(unsigned int)StrBufCatA(v8, " ") )
        goto LABEL_16;
      goto LABEL_34;
    }
  }
  v19 = (unsigned __int16)v18;
LABEL_42:
  StrBufDestroyA((LPVOID)v8);
  return v19;
}

```

## disassembly

```asm
0x180005bcc  mov     [rsp-8+arg_18], rbx
0x180005bd1  push    rbp
0x180005bd2  push    rsi
0x180005bd3  push    rdi
0x180005bd4  push    r12
0x180005bd6  push    r13
0x180005bd8  push    r14
0x180005bda  push    r15
0x180005bdc  lea     rbp, [rsp-17h]
0x180005be1  sub     rsp, 0A0h
0x180005be8  mov     rax, cs:__security_cookie
0x180005bef  xor     rax, rsp
0x180005bf2  mov     [rbp+47h+var_40], rax
0x180005bf6  mov     r13, rcx
0x180005bf9  mov     [rbp+47h+var_88], r8
0x180005bfd  xor     ecx, ecx
0x180005bff  mov     [rbp+47h+var_90], edx
0x180005c02  mov     r12d, edx
0x180005c05  call    pStrBufCreate
0x180005c0a  mov     rbx, rax
0x180005c0d  test    rax, rax
0x180005c10  jnz     short loc_180005C24
0x180005c12  xor     ecx, ecx; lpMem
0x180005c14  call    StrBufDestroyA
0x180005c19  call    cs:__imp_GetLastError
0x180005c1f  jmp     loc_180005E23
0x180005c24  mov     rcx, [rax+8]
0x180005c28  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005c2c  inc     rax
0x180005c2f  cmp     byte ptr [rcx+rax], 0
0x180005c33  jnz     short loc_180005C2C
0x180005c35  mov     edi, [rbp+47h+arg_20]
0x180005c38  mov     [rbx+4], eax
0x180005c3b  mov     eax, edi
0x180005c3d  and     eax, 0Fh
0x180005c40  cmp     eax, 1
0x180005c43  jnz     short loc_180005C4E
0x180005c45  lea     rdx, asc_18000D860; "!!!  "
0x180005c4c  jmp     short loc_180005C90
0x180005c4e  cmp     eax, 2
0x180005c51  jnz     short loc_180005C5C
0x180005c53  lea     rdx, asc_18000D868; "!    "
0x180005c5a  jmp     short loc_180005C90
0x180005c5c  test    dil, 10h
0x180005c60  jz      short loc_180005C6B
0x180005c62  lea     rdx, asc_18000D870; ">>>  "
0x180005c69  jmp     short loc_180005C90
0x180005c6b  test    dil, 20h
0x180005c6f  jz      short loc_180005C7A
0x180005c71  lea     rdx, asc_18000D878; "<<<  "
0x180005c78  jmp     short loc_180005C90
0x180005c7a  test    dil, 40h
0x180005c7e  lea     rdx, asc_18000D880; "   . "
0x180005c85  lea     rax, asc_18000D888; "     "
0x180005c8c  cmovz   rdx, rax
0x180005c90  mov     rcx, rbx
0x180005c93  call    StrBufCatA
0x180005c98  test    eax, eax
0x180005c9a  jnz     short loc_180005CA7
0x180005c9c  call    cs:__imp_GetLastError
0x180005ca2  jmp     loc_180005E23
0x180005ca7  xor     r15d, r15d
0x180005caa  test    dil, 30h
0x180005cae  jz      short loc_180005CD1
0x180005cb0  test    [rbp+47h+arg_20], 10000h
0x180005cb7  mov     esi, r15d
0x180005cba  setnz   sil
0x180005cbe  mov     r14d, esi
0x180005cc1  bt      edi, 10h
0x180005cc5  jnb     loc_180005DCF
0x180005ccb  lea     r12d, [r15+1]
0x180005ccf  jmp     short loc_180005CFB
0x180005cd1  mov     rax, [r13+20h]
0x180005cd5  xor     esi, esi
0x180005cd7  xor     r14d, r14d
0x180005cda  xor     r12d, r12d
0x180005cdd  test    dword ptr [rax+0Ch], 8000000h
0x180005ce4  jz      short loc_180005CEC
0x180005ce6  lea     r15d, [rsi+1]
0x180005cea  jmp     short loc_180005CFB
0x180005cec  bt      edi, 10h
0x180005cf0  jnb     loc_180005DB4
0x180005cf6  mov     esi, 1
0x180005cfb  xorps   xmm0, xmm0
0x180005cfe  lea     rcx, [rbp+47h+SystemTime]; lpSystemTime
0x180005d02  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x180005d06  call    cs:__imp_GetLocalTime
0x180005d0c  movzx   ecx, [rbp+47h+SystemTime.wSecond]
0x180005d10  lea     r8, a02d02d02d03d; " %02d:%02d:%02d.%03d"
0x180005d17  movzx   edx, [rbp+47h+SystemTime.wMinute]
0x180005d1b  mov     edi, 14h
0x180005d20  movzx   eax, [rbp+47h+SystemTime.wMilliseconds]
0x180005d24  movzx   r9d, [rbp+47h+SystemTime.wHour]
0x180005d29  mov     [rsp+0D0h+var_A0], eax
0x180005d2d  mov     [rsp+0D0h+var_A8], ecx
0x180005d31  lea     rcx, [rbp+47h+pszDest]; pszDest
0x180005d35  mov     [rsp+0D0h+var_B0], edx
0x180005d39  mov     edx, edi; cchDest
0x180005d3b  call    StringCchPrintfA
0x180005d40  test    eax, eax
0x180005d42  jns     short loc_180005D4C
0x180005d44  movzx   edi, ax
0x180005d47  jmp     loc_180005E25
0x180005d4c  test    r14d, r14d
0x180005d4f  jz      short loc_180005D7D
0x180005d51  movzx   ecx, [rbp+47h+SystemTime.wMonth]
0x180005d55  lea     r8, a04d02d02d; " %04d/%02d/%02d"
0x180005d5c  movzx   eax, [rbp+47h+SystemTime.wDay]
0x180005d60  mov     rdx, rdi; cchDest
0x180005d63  movzx   r9d, [rbp+47h+SystemTime.wYear]
0x180005d68  mov     [rsp+0D0h+var_A8], eax
0x180005d6c  mov     [rsp+0D0h+var_B0], ecx
0x180005d70  lea     rcx, [rbp+47h+var_70]; pszDest
0x180005d74  call    StringCchPrintfA
0x180005d79  test    eax, eax
0x180005d7b  js      short loc_180005D44
0x180005d7d  test    r15d, r15d
0x180005d80  jz      short loc_180005DAF
0x180005d82  test    r14d, r14d
0x180005d85  jz      short loc_180005D9B
0x180005d87  lea     rdx, [rbp+47h+var_70]
0x180005d8b  mov     rcx, rbx
0x180005d8e  call    StrBufCatA
0x180005d93  test    eax, eax
0x180005d95  jz      loc_180005C9C
0x180005d9b  lea     rdx, [rbp+47h+pszDest]
0x180005d9f  mov     rcx, rbx
0x180005da2  call    StrBufCatA
0x180005da7  test    eax, eax
0x180005da9  jz      loc_180005C9C
0x180005daf  test    r12d, r12d
0x180005db2  jnz     short loc_180005DCB
0x180005db4  lea     rdx, asc_18000D8B8; " "
0x180005dbb  mov     rcx, rbx
0x180005dbe  call    StrBufCatA
0x180005dc3  test    eax, eax
0x180005dc5  jz      loc_180005C9C
0x180005dcb  mov     r12d, [rbp+47h+var_90]
0x180005dcf  mov     rdx, [rbp+47h+var_88]
0x180005dd3  mov     rcx, rbx
0x180005dd6  call    StrBufCatA
0x180005ddb  test    eax, eax
0x180005ddd  jz      loc_180005C9C
0x180005de3  test    esi, esi
0x180005de5  jz      short loc_180005E14
0x180005de7  test    r14d, r14d
0x180005dea  jz      short loc_180005E00
0x180005dec  lea     rdx, [rbp+47h+var_70]
0x180005df0  mov     rcx, rbx
0x180005df3  call    StrBufCatA
0x180005df8  test    eax, eax
0x180005dfa  jz      loc_180005C9C
0x180005e00  lea     rdx, [rbp+47h+pszDest]
0x180005e04  mov     rcx, rbx
0x180005e07  call    StrBufCatA
0x180005e0c  test    eax, eax
0x180005e0e  jz      loc_180005C9C
0x180005e14  mov     r8, [rbx+8]
0x180005e18  mov     edx, r12d
0x180005e1b  mov     rcx, r13
0x180005e1e  call    TextLogInsertString
0x180005e23  mov     edi, eax
0x180005e25  mov     rcx, rbx; lpMem
0x180005e28  call    StrBufDestroyA
0x180005e2d  mov     eax, edi
0x180005e2f  mov     rcx, [rbp+47h+var_40]
0x180005e33  xor     rcx, rsp; StackCookie
0x180005e36  call    __security_check_cookie
0x180005e3b  mov     rbx, [rsp+0D0h+arg_18]
0x180005e43  add     rsp, 0A0h
0x180005e4a  pop     r15
0x180005e4c  pop     r14
0x180005e4e  pop     r13
0x180005e50  pop     r12
0x180005e52  pop     rdi
0x180005e53  pop     rsi
0x180005e54  pop     rbp
0x180005e55  retn
```
