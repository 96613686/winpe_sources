# permissive_name

- ea: `0x14000389c`
- end: `0x140003acb`
- name: `permissive_name`
- size: `559`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b20`

## callees

- `0x14000389c`
- `0x1400076c5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003948`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003a9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003ab2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003948`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003a9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003ab2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400038c6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140003920`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140003a37`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400038c6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140003920`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140003a37`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000390b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000393d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000390b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000393d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400038eb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400038eb`

## pseudocode

```c
WCHAR *__fastcall permissive_name(LPCCH lpMultiByteStr)
{
  __int64 cchWideChar; // rbx
  WCHAR *lpWideCharStr; // rax
  WCHAR *v4; // rdi
  unsigned int v5; // eax
  DWORD FullPathNameW; // eax
  DWORD v7; // esi
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  DWORD v10; // esi
  WCHAR *v11; // r14
  int v12; // ebp
  WCHAR v13; // cx
  WCHAR *result; // rax
  WCHAR v15; // cx
  _WORD *v16; // rax
  _WORD *v17; // rax
  __int16 v18; // cx
  _WORD *v19; // r8
  unsigned int v20; // esi
  wchar_t *v21; // rax
  wchar_t *v22; // rdi
  WCHAR *v23; // rcx
  __int64 v24; // r12
  wchar_t *v25; // rdi
  unsigned int v26; // r15d

  cchWideChar = -1;
  do
    ++cchWideChar;
  while ( lpMultiByteStr[cchWideChar] );
  lpWideCharStr = (WCHAR *)malloc(2LL * (unsigned int)(cchWideChar + 1));
  v4 = lpWideCharStr;
  if ( !lpWideCharStr )
    return 0;
  v5 = MultiByteToWideChar(0, 0, lpMultiByteStr, cchWideChar, lpWideCharStr, cchWideChar);
  if ( !v5
    || (v4[v5] = 0, FullPathNameW = GetFullPathNameW(v4, 0, 0, 0), (v7 = FullPathNameW) == 0)
    || (v8 = (WCHAR *)malloc(2LL * FullPathNameW), (v9 = v8) == 0) )
  {
    v23 = v4;
    goto LABEL_40;
  }
  v10 = GetFullPathNameW(v4, v7, v8, 0);
  free(v4);
  if ( *v9 != 92 || v9[1] != 92 )
    goto LABEL_20;
  if ( v9[2] != 63 )
  {
    if ( v9[2] == 46 && v9[3] == 92 )
    {
      v13 = v9[4];
      if ( ((unsigned __int16)(v13 - 97) <= 0x19u || (unsigned __int16)(v13 - 65) <= 0x19u)
        && v9[5] == 58
        && v9[6] == 92 )
      {
        v9[2] = 63;
      }
      return v9;
    }
LABEL_20:
    v11 = v9;
    v12 = 0;
    if ( *v9 != 92 )
      goto LABEL_34;
    goto LABEL_21;
  }
  if ( v9[3] == 92 )
    return v9;
  v11 = v9;
  v12 = 0;
LABEL_21:
  if ( v9[1] == 92 )
  {
    v15 = v9[2];
    if ( v15 != 92 )
    {
      v16 = v9 + 2;
      do
      {
        if ( !v15 )
          break;
        v15 = *++v16;
      }
      while ( *v16 != 92 );
      if ( *v16 == 92 )
      {
        v17 = v16 + 1;
        v18 = *v17;
        if ( *v17 != 92 )
        {
          v19 = v17;
          do
          {
            if ( !v18 )
              break;
            v18 = *++v17;
          }
          while ( *v17 != 92 );
          if ( *v17 == 92 && v17 != v19 )
          {
            v9 += 2;
            v10 -= 2;
            v12 = 1;
          }
        }
      }
    }
  }
LABEL_34:
  v20 = v10 + 4 * v12 + 5;
  v21 = (wchar_t *)malloc(2LL * v20);
  v22 = v21;
  if ( !v21 )
  {
    v23 = v11;
LABEL_40:
    free(v23);
    return 0;
  }
  v24 = (__int64)v21;
  wcsncpy_0(v21, L"\\\\?\\", 4u);
  v25 = v22 + 4;
  v26 = v20 - 4;
  if ( v12 )
  {
    wcsncpy_0(v25, L"UNC\\", 4u);
    v25 += 4;
    v26 = v20 - 8;
  }
  wcsncpy_0(v25, v9, v26);
  free(v11);
  result = (WCHAR *)v24;
  *(_WORD *)(v24 + 2LL * (v20 - 1)) = 0;
  return result;
}

```

## disassembly

```asm
0x14000389c  push    rbx
0x14000389e  push    rbp
0x14000389f  push    rsi
0x1400038a0  push    rdi
0x1400038a1  push    r12
0x1400038a3  push    r13
0x1400038a5  push    r14
0x1400038a7  push    r15
0x1400038a9  sub     rsp, 38h
0x1400038ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400038b1  mov     rsi, rcx
0x1400038b4  xor     r13d, r13d
0x1400038b7  inc     rbx
0x1400038ba  cmp     [rcx+rbx], r13b
0x1400038be  jnz     short loc_1400038B7
0x1400038c0  lea     ecx, [rbx+1]
0x1400038c3  add     rcx, rcx; Size
0x1400038c6  call    cs:__imp_malloc
0x1400038cc  mov     rdi, rax
0x1400038cf  test    rax, rax
0x1400038d2  jz      loc_140003AB8
0x1400038d8  mov     [rsp+78h+cchWideChar], ebx; cchWideChar
0x1400038dc  mov     r9d, ebx; cbMultiByte
0x1400038df  mov     r8, rsi; lpMultiByteStr
0x1400038e2  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x1400038e7  xor     edx, edx; dwFlags
0x1400038e9  xor     ecx, ecx; CodePage
0x1400038eb  call    cs:__imp_MultiByteToWideChar
0x1400038f1  test    eax, eax
0x1400038f3  jz      loc_140003AAF
0x1400038f9  mov     ecx, eax
0x1400038fb  xor     r9d, r9d; lpFilePart
0x1400038fe  xor     r8d, r8d; lpBuffer
0x140003901  xor     edx, edx; nBufferLength
0x140003903  mov     [rdi+rcx*2], r13w
0x140003908  mov     rcx, rdi; lpFileName
0x14000390b  call    cs:__imp_GetFullPathNameW
0x140003911  mov     esi, eax
0x140003913  test    eax, eax
0x140003915  jz      loc_140003AAF
0x14000391b  mov     ecx, esi
0x14000391d  add     rcx, rcx; Size
0x140003920  call    cs:__imp_malloc
0x140003926  mov     rbx, rax
0x140003929  test    rax, rax
0x14000392c  jz      loc_140003AAF
0x140003932  xor     r9d, r9d; lpFilePart
0x140003935  mov     r8, rax; lpBuffer
0x140003938  mov     edx, esi; nBufferLength
0x14000393a  mov     rcx, rdi; lpFileName
0x14000393d  call    cs:__imp_GetFullPathNameW
0x140003943  mov     rcx, rdi; Block
0x140003946  mov     esi, eax
0x140003948  call    cs:__imp_free
0x14000394e  mov     r9w, 5Ch ; '\'
0x140003953  cmp     [rbx], r9w
0x140003957  jnz     short loc_1400039B9
0x140003959  cmp     [rbx+2], r9w
0x14000395e  jnz     short loc_1400039B9
0x140003960  mov     edx, 3Fh ; '?'
0x140003965  cmp     [rbx+4], dx
0x140003969  jnz     short loc_14000397A
0x14000396b  cmp     [rbx+6], r9w
0x140003970  jz      short loc_1400039B1
0x140003972  mov     r14, rbx
0x140003975  mov     ebp, r13d
0x140003978  jmp     short loc_1400039C5
0x14000397a  cmp     word ptr [rbx+4], 2Eh ; '.'
0x14000397f  jnz     short loc_1400039B9
0x140003981  cmp     [rbx+6], r9w
0x140003986  jnz     short loc_1400039B9
0x140003988  movzx   ecx, word ptr [rbx+8]
0x14000398c  lea     eax, [rcx-61h]
0x14000398f  cmp     ax, 19h
0x140003993  jbe     short loc_14000399F
0x140003995  sub     cx, 41h ; 'A'
0x140003999  cmp     cx, 19h
0x14000399d  ja      short loc_1400039B1
0x14000399f  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x1400039a4  jnz     short loc_1400039B1
0x1400039a6  cmp     [rbx+0Ch], r9w
0x1400039ab  jnz     short loc_1400039B1
0x1400039ad  mov     [rbx+4], dx
0x1400039b1  mov     rax, rbx
0x1400039b4  jmp     loc_140003ABA
0x1400039b9  mov     r14, rbx
0x1400039bc  mov     ebp, r13d
0x1400039bf  cmp     [rbx], r9w
0x1400039c3  jnz     short loc_140003A2C
0x1400039c5  cmp     [rbx+2], r9w
0x1400039ca  jnz     short loc_140003A2C
0x1400039cc  lea     rdx, [rbx+4]
0x1400039d0  movzx   ecx, word ptr [rdx]
0x1400039d3  cmp     cx, r9w
0x1400039d7  jz      short loc_140003A2C
0x1400039d9  mov     rax, rdx
0x1400039dc  test    cx, cx
0x1400039df  jz      short loc_1400039EE
0x1400039e1  add     rax, 2
0x1400039e5  movzx   ecx, word ptr [rax]
0x1400039e8  cmp     cx, r9w
0x1400039ec  jnz     short loc_1400039DC
0x1400039ee  cmp     [rax], r9w
0x1400039f2  jnz     short loc_140003A2C
0x1400039f4  add     rax, 2
0x1400039f8  movzx   ecx, word ptr [rax]
0x1400039fb  cmp     cx, r9w
0x1400039ff  jz      short loc_140003A2C
0x140003a01  mov     r8, rax
0x140003a04  test    cx, cx
0x140003a07  jz      short loc_140003A16
0x140003a09  add     rax, 2
0x140003a0d  movzx   ecx, word ptr [rax]
0x140003a10  cmp     cx, r9w
0x140003a14  jnz     short loc_140003A04
0x140003a16  cmp     [rax], r9w
0x140003a1a  jnz     short loc_140003A2C
0x140003a1c  cmp     rax, r8
0x140003a1f  jz      short loc_140003A2C
0x140003a21  mov     rbx, rdx
0x140003a24  add     esi, 0FFFFFFFEh
0x140003a27  mov     ebp, 1
0x140003a2c  lea     esi, [rsi+rbp*4]
0x140003a2f  add     esi, 5
0x140003a32  mov     ecx, esi
0x140003a34  add     rcx, rcx; Size
0x140003a37  call    cs:__imp_malloc
0x140003a3d  mov     rdi, rax
0x140003a40  test    rax, rax
0x140003a43  jnz     short loc_140003A4A
0x140003a45  mov     rcx, r14
0x140003a48  jmp     short loc_140003AB2
0x140003a4a  mov     r8d, 4; Count
0x140003a50  lea     rdx, Source; "\\\\?\\"
0x140003a57  mov     rcx, rdi; Destination
0x140003a5a  mov     r12, rdi
0x140003a5d  call    wcsncpy_0
0x140003a62  add     rdi, 8
0x140003a66  lea     r15d, [rsi-4]
0x140003a6a  test    ebp, ebp
0x140003a6c  jz      short loc_140003A8B
0x140003a6e  mov     r8d, 4; Count
0x140003a74  lea     rdx, aUnc; "UNC\\"
0x140003a7b  mov     rcx, rdi; Destination
0x140003a7e  call    wcsncpy_0
0x140003a83  add     rdi, 8
0x140003a87  add     r15d, 0FFFFFFFCh
0x140003a8b  mov     r8d, r15d; Count
0x140003a8e  mov     rdx, rbx; Source
0x140003a91  mov     rcx, rdi; Destination
0x140003a94  call    wcsncpy_0
0x140003a99  mov     rcx, r14; Block
0x140003a9c  call    cs:__imp_free
0x140003aa2  lea     ecx, [rsi-1]
0x140003aa5  mov     rax, r12
0x140003aa8  mov     [r12+rcx*2], r13w
0x140003aad  jmp     short loc_140003ABA
0x140003aaf  mov     rcx, rdi; Block
0x140003ab2  call    cs:__imp_free
0x140003ab8  xor     eax, eax
0x140003aba  add     rsp, 38h
0x140003abe  pop     r15
0x140003ac0  pop     r14
0x140003ac2  pop     r13
0x140003ac4  pop     r12
0x140003ac6  pop     rdi
0x140003ac7  pop     rsi
0x140003ac8  pop     rbp
0x140003ac9  pop     rbx
0x140003aca  retn
```
