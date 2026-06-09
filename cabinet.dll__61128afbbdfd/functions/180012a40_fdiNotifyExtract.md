# fdiNotifyExtract

- ea: `0x180012a40`
- end: `0x180012c95`
- name: `fdiNotifyExtract`
- size: `597`
- prototype: `INT_PTR __cdecl(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180004700`
- `0x180012a40`
- `0x180012c9c`
- `0x180012cec`
- `0x180014788`
- `0x180014850`
- `0x180014904`
- `0x180014dc0`
- `0x180015880`
- `0x1800159c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180012c3b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180012c3b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180012af4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180012af4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180012b08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180012b72`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180012bad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180012b08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180012b72`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180012bad`

## pseudocode

```c
INT_PTR __fastcall fdiNotifyExtract(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  char *pv; // rdi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  DWORD v8; // edx
  char *v9; // rsi
  __int64 v10; // rbx
  const char *v11; // r14
  const char *v12; // r15
  char *psz1; // rbp
  __int64 v14; // rsi
  __int64 i; // rdi
  size_t *v16; // r8
  unsigned int v17; // r10d
  char *v18; // rcx
  _BYTE *v19; // rax
  _BYTE *v20; // rbx
  size_t v21; // [rsp+20h] [rbp-168h]
  size_t pcchLength[2]; // [rsp+30h] [rbp-158h] BYREF
  char pszDest[260]; // [rsp+40h] [rbp-148h] BYREF
  char v24; // [rsp+144h] [rbp-44h] BYREF

  pv = (char *)pfdin->pv;
  if ( fdint == fdintCABINET_INFO )
    return 0;
  v4 = fdint - 1;
  if ( !v4 )
    return 0;
  v5 = v4 - 1;
  if ( !v5 )
  {
    v11 = pv + 32;
    v12 = pv + 292;
    if ( !(unsigned int)catDirAndFile(pv + 292) || !(unsigned int)AddFile((__int64)pv, pfdin->psz1, pfdin->cb) )
      return -1;
    psz1 = pfdin->psz1;
    v14 = *((_QWORD *)pv + 2);
    while ( lstrcmpiA(psz1, *(LPCSTR *)v14) )
    {
      v14 = *(_QWORD *)(v14 + 8);
      if ( !v14 )
        goto LABEL_24;
    }
    if ( !*(_DWORD *)(v14 + 16) )
      return 0;
LABEL_24:
    if ( (pv[28] & 2) != 0 )
    {
LABEL_29:
      if ( StrChar(pfdin->psz1) )
      {
        pcchLength[0] = 0;
        if ( StringCopyWorkerA(pszDest, 0x104u, v16, v12, v21) < 0
          || !v11
          || StringLengthWorkerA(v11, v17, pcchLength) < 0 )
        {
          return -1;
        }
        v18 = &pszDest[pcchLength[0] + 1];
        while ( v18 < &v24 )
        {
          if ( !*v18 )
            break;
          v19 = (_BYTE *)StrChar(v18);
          v20 = v19;
          if ( !v19 )
            break;
          *v19 = 0;
          CreateDirectoryA(pszDest, 0);
          v18 = v20 + 1;
          *v20 = 92;
        }
      }
      return openfunc(v12, 33538, 0);
    }
    for ( i = *((_QWORD *)pv + 102); i; i = *(_QWORD *)(i + 8) )
    {
      if ( !lstrcmpiA(*(LPCSTR *)i, psz1) )
        goto LABEL_29;
    }
    return 0;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 == 1 )
      return -1;
    return 0;
  }
  if ( !(unsigned int)catDirAndFile(pv + 292) )
    return -1;
  AdjustFileTime((HANDLE)pfdin->hf);
  closefunc(pfdin->hf);
  if ( pfdin->attribs )
    v8 = pfdin->attribs & 0xFFD8;
  else
    v8 = 128;
  SetFileAttributesA(pv + 292, v8);
  v9 = pfdin->psz1;
  v10 = *((_QWORD *)pv + 2);
  while ( lstrcmpiA(v9, *(LPCSTR *)v10) )
  {
    v10 = *(_QWORD *)(v10 + 8);
    if ( !v10 )
      return 1;
  }
  *(_DWORD *)(v10 + 16) = 0;
  return 1;
}

```

## disassembly

```asm
0x180012a40  mov     [rsp+arg_0], rbx
0x180012a45  mov     [rsp+arg_10], rbp
0x180012a4a  push    rsi
0x180012a4b  push    rdi
0x180012a4c  push    r12
0x180012a4e  push    r14
0x180012a50  push    r15
0x180012a52  sub     rsp, 160h
0x180012a59  mov     rax, cs:__security_cookie
0x180012a60  xor     rax, rsp
0x180012a63  mov     [rsp+188h+var_38], rax
0x180012a6b  mov     rdi, [rdx+20h]
0x180012a6f  xor     r12d, r12d
0x180012a72  mov     rbx, rdx
0x180012a75  test    ecx, ecx
0x180012a77  jz      loc_180012C67
0x180012a7d  sub     ecx, 1
0x180012a80  jz      loc_180012C67
0x180012a86  sub     ecx, 1
0x180012a89  jz      loc_180012B2B
0x180012a8f  sub     ecx, 1
0x180012a92  jz      short loc_180012AA6
0x180012a94  cmp     ecx, 1
0x180012a97  jnz     loc_180012C67
0x180012a9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012aa1  jmp     loc_180012C69
0x180012aa6  mov     r9, [rdx+8]
0x180012aaa  lea     rsi, [rdi+124h]
0x180012ab1  mov     rcx, rsi; pszDest
0x180012ab4  lea     r8, [rdi+20h]
0x180012ab8  call    catDirAndFile
0x180012abd  test    eax, eax
0x180012abf  jz      short loc_180012A9D
0x180012ac1  movzx   r8d, word ptr [rbx+32h]
0x180012ac6  movzx   edx, word ptr [rbx+30h]
0x180012aca  mov     rcx, [rbx+28h]; hFile
0x180012ace  call    AdjustFileTime
0x180012ad3  mov     rcx, [rbx+28h]
0x180012ad7  call    closefunc
0x180012adc  cmp     [rbx+34h], r12w
0x180012ae1  jnz     short loc_180012AEA
0x180012ae3  mov     edx, 80h
0x180012ae8  jmp     short loc_180012AF1
0x180012aea  movzx   edx, word ptr [rbx+34h]
0x180012aee  and     edx, 0FFFFFFD8h; dwFileAttributes
0x180012af1  mov     rcx, rsi; lpFileName
0x180012af4  call    cs:__imp_SetFileAttributesA
0x180012afa  mov     rsi, [rbx+8]
0x180012afe  mov     rbx, [rdi+10h]
0x180012b02  mov     rdx, [rbx]; lpString2
0x180012b05  mov     rcx, rsi; lpString1
0x180012b08  call    cs:__imp_lstrcmpiA
0x180012b0e  test    eax, eax
0x180012b10  jz      short loc_180012B1D
0x180012b12  mov     rbx, [rbx+8]
0x180012b16  test    rbx, rbx
0x180012b19  jnz     short loc_180012B02
0x180012b1b  jmp     short loc_180012B21
0x180012b1d  mov     [rbx+10h], r12d
0x180012b21  mov     eax, 1
0x180012b26  jmp     loc_180012C69
0x180012b2b  mov     r9, [rdx+8]
0x180012b2f  lea     r14, [rdi+20h]
0x180012b33  lea     r15, [rdi+124h]
0x180012b3a  mov     r8, r14
0x180012b3d  mov     rcx, r15; pszDest
0x180012b40  call    catDirAndFile
0x180012b45  test    eax, eax
0x180012b47  jz      loc_180012A9D
0x180012b4d  mov     r8d, [rbx]
0x180012b50  mov     rcx, rdi
0x180012b53  mov     rdx, [rbx+8]
0x180012b57  call    AddFile
0x180012b5c  test    eax, eax
0x180012b5e  jz      loc_180012A9D
0x180012b64  mov     rbp, [rbx+8]
0x180012b68  mov     rsi, [rdi+10h]
0x180012b6c  mov     rdx, [rsi]; lpString2
0x180012b6f  mov     rcx, rbp; lpString1
0x180012b72  call    cs:__imp_lstrcmpiA
0x180012b78  test    eax, eax
0x180012b7a  jz      short loc_180012B87
0x180012b7c  mov     rsi, [rsi+8]
0x180012b80  test    rsi, rsi
0x180012b83  jnz     short loc_180012B6C
0x180012b85  jmp     short loc_180012B91
0x180012b87  cmp     [rsi+10h], r12d
0x180012b8b  jz      loc_180012C67
0x180012b91  test    byte ptr [rdi+1Ch], 2
0x180012b95  jnz     short loc_180012BBD
0x180012b97  mov     rdi, [rdi+330h]
0x180012b9e  test    rdi, rdi
0x180012ba1  jz      loc_180012C67
0x180012ba7  mov     rcx, [rdi]; lpString1
0x180012baa  mov     rdx, rbp; lpString2
0x180012bad  call    cs:__imp_lstrcmpiA
0x180012bb3  test    eax, eax
0x180012bb5  jz      short loc_180012BBD
0x180012bb7  mov     rdi, [rdi+8]
0x180012bbb  jmp     short loc_180012B9E
0x180012bbd  mov     rcx, [rbx+8]
0x180012bc1  call    StrChar
0x180012bc6  test    rax, rax
0x180012bc9  jz      loc_180012C55
0x180012bcf  mov     r10d, 104h
0x180012bd5  mov     [rsp+188h+pcchLength], r12
0x180012bda  mov     edx, r10d; cchDest
0x180012bdd  lea     rcx, [rsp+188h+pszDest]; pszDest
0x180012be2  mov     r9, r15; pszSrc
0x180012be5  call    StringCopyWorkerA
0x180012bea  test    eax, eax
0x180012bec  js      loc_180012A9D
0x180012bf2  test    r14, r14
0x180012bf5  jz      loc_180012A9D
0x180012bfb  lea     r8, [rsp+188h+pcchLength]; pcchLength
0x180012c00  mov     edx, r10d; cchMax
0x180012c03  mov     rcx, r14; psz
0x180012c06  call    StringLengthWorkerA
0x180012c0b  test    eax, eax
0x180012c0d  js      loc_180012A9D
0x180012c13  lea     rcx, [rsp+188h+var_147]
0x180012c18  add     rcx, [rsp+188h+pcchLength]
0x180012c1d  jmp     short loc_180012C48
0x180012c1f  cmp     [rcx], r12b
0x180012c22  jz      short loc_180012C55
0x180012c24  call    StrChar
0x180012c29  mov     rbx, rax
0x180012c2c  test    rax, rax
0x180012c2f  jz      short loc_180012C55
0x180012c31  xor     edx, edx; lpSecurityAttributes
0x180012c33  mov     [rax], r12b
0x180012c36  lea     rcx, [rsp+188h+pszDest]; lpPathName
0x180012c3b  call    cs:__imp_CreateDirectoryA
0x180012c41  lea     rcx, [rbx+1]
0x180012c45  mov     byte ptr [rbx], 5Ch ; '\'
0x180012c48  lea     rax, [rsp+188h+var_44]
0x180012c50  cmp     rcx, rax
0x180012c53  jb      short loc_180012C1F
0x180012c55  xor     r8d, r8d
0x180012c58  mov     edx, 8302h
0x180012c5d  mov     rcx, r15
0x180012c60  call    openfunc
0x180012c65  jmp     short loc_180012C69
0x180012c67  xor     eax, eax
0x180012c69  mov     rcx, [rsp+188h+var_38]
0x180012c71  xor     rcx, rsp; StackCookie
0x180012c74  call    __security_check_cookie
0x180012c79  lea     r11, [rsp+188h+var_28]
0x180012c81  mov     rbx, [r11+30h]
0x180012c85  mov     rbp, [r11+40h]
0x180012c89  mov     rsp, r11
0x180012c8c  pop     r15
0x180012c8e  pop     r14
0x180012c90  pop     r12
0x180012c92  pop     rdi
0x180012c93  pop     rsi
0x180012c94  retn
```
