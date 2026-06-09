# ParseValue

- ea: `0x14000c1d8`
- end: `0x14000c4f8`
- name: `ParseValue`
- size: `800`
- prototype: `BYTE *__fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000b418`

## callees

- `0x140001340`
- `0x14000bbf0`
- `0x14000bd2c`
- `0x14000bf98`
- `0x14000bff4`
- `0x14000c0cc`
- `0x14000c1d8`
- `0x14000cd24`
- `0x14000cd84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000c49d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000c49d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000c337`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000c337`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x14000c479`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x14000c479`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c4ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c4ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c234`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c234`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000c455`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000c455`

## pseudocode

```c
BYTE *__fastcall ParseValue(HKEY hKey, LPCWSTR lpValueName)
{
  __int64 v4; // rcx
  BYTE *result; // rax
  BYTE *v6; // rsi
  DWORD v7; // edi
  int v8; // r14d
  int v9; // ebx
  wchar_t *v10; // rdi
  __int64 v11; // rcx
  int matched; // eax
  int v13; // eax
  DWORD v14; // r15d
  const wchar_t *v15; // rdi
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  LSTATUS v19; // eax
  DWORD v20; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  CHAR MultiByteStr[256]; // [rsp+60h] [rbp-A0h] BYREF

  v20 = 0;
  SkipWhitespace();
  if ( (unsigned int)MatchChar(61) )
  {
    SkipWhitespace();
    result = (BYTE *)LocalAlloc(0x40u, 0x100u);
    v6 = result;
    if ( !result )
    {
      g_FileErrorStringID = 705;
      return result;
    }
    v7 = 1;
    v8 = 0;
    v9 = 1;
    if ( (unsigned int)MatchChar(34) )
    {
      v22 = 256;
      v21 = v6;
      if ( (unsigned int)ParseString((__int64)&v21) && (unsigned int)ParseEndOfLine() )
        goto LABEL_39;
      v8 = 1;
LABEL_38:
      v9 = 0;
LABEL_39:
      v14 = v22;
      v6 = v21;
LABEL_40:
      if ( v9 )
      {
        if ( (unsigned int)g_ImportFileVersion < 0x500 && (v7 == 2 || v7 == 7) )
        {
          MultiByteStr[0] = 0;
          WideCharToMultiByte(3u, 0, lpValueName, -1, MultiByteStr, 256, 0, 0);
          v19 = RegSetValueExA(hKey, MultiByteStr, 0, v7, v6, v14);
        }
        else
        {
          v19 = RegSetValueExW(hKey, lpValueName, 0, v7, v6, v14);
        }
        if ( v19 )
          g_FileErrorStringID = 705;
      }
      goto LABEL_48;
    }
    if ( (unsigned int)MatchChar(100) )
    {
      v10 = L"word:";
      v11 = 119;
      do
      {
        matched = MatchChar(v11);
        ++v10;
        if ( !matched )
          v8 = 1;
        v11 = *v10;
        v13 = matched != 0 ? v9 : 0;
        v9 = v13;
      }
      while ( (_WORD)v11 );
      if ( v13 )
      {
        SkipWhitespace();
        if ( !(unsigned int)ParseHexDword(v6) || !(unsigned int)ParseEndOfLine() )
        {
          v9 = 0;
          v8 = 1;
        }
        v14 = 4;
        v7 = 4;
        goto LABEL_40;
      }
    }
    else
    {
      if ( (unsigned int)MatchChar(45) )
      {
        if ( (unsigned int)ParseEndOfLine() )
          RegDeleteValueW(hKey, lpValueName);
        else
          v8 = 1;
        goto LABEL_48;
      }
      v15 = L"hex";
      v16 = 104;
      do
      {
        v17 = MatchChar(v16);
        ++v15;
        if ( !v17 )
          v8 = 1;
        v16 = *v15;
        v18 = v17 != 0 ? v9 : 0;
        v9 = v18;
      }
      while ( (_WORD)v16 );
      if ( v18 )
      {
        if ( (unsigned int)MatchChar(40) )
        {
          if ( !(unsigned int)ParseHexDword(&v20) || !(unsigned int)MatchChar(41) )
          {
            v9 = 0;
            v8 = 1;
          }
          if ( !v9 )
            goto LABEL_48;
          v7 = v20;
        }
        else
        {
          v7 = 3;
        }
        v22 = 256;
        v21 = v6;
        if ( (unsigned int)MatchChar(58) && (unsigned int)ParseHexSequence(&v21) && (unsigned int)ParseEndOfLine() )
          goto LABEL_39;
        v8 = 1;
        goto LABEL_38;
      }
    }
LABEL_48:
    result = (BYTE *)LocalFree(v6);
    if ( !v8 )
      return result;
  }
  return (BYTE *)SkipPastEndOfLine(v4);
}

```

## disassembly

```asm
0x14000c1d8  mov     [rsp-8+arg_10], rbx
0x14000c1dd  push    rbp
0x14000c1de  push    rsi
0x14000c1df  push    rdi
0x14000c1e0  push    r12
0x14000c1e2  push    r13
0x14000c1e4  push    r14
0x14000c1e6  push    r15
0x14000c1e8  lea     rbp, [rsp-70h]
0x14000c1ed  sub     rsp, 170h
0x14000c1f4  mov     rax, cs:__security_cookie
0x14000c1fb  xor     rax, rsp
0x14000c1fe  mov     [rbp+0A0h+var_40], rax
0x14000c202  xor     r15d, r15d
0x14000c205  mov     r13, rdx
0x14000c208  mov     [rsp+1A0h+var_160], r15d
0x14000c20d  mov     r12, rcx
0x14000c210  call    SkipWhitespace
0x14000c215  lea     ecx, [r15+3Dh]
0x14000c219  call    MatchChar
0x14000c21e  test    eax, eax
0x14000c220  jz      loc_14000C4CB
0x14000c226  call    SkipWhitespace
0x14000c22b  mov     edx, 100h; uBytes
0x14000c230  lea     ecx, [r15+40h]; uFlags
0x14000c234  call    cs:__imp_LocalAlloc
0x14000c23b  nop     dword ptr [rax+rax+00h]
0x14000c240  mov     rsi, rax
0x14000c243  test    rax, rax
0x14000c246  jnz     short loc_14000C257
0x14000c248  mov     cs:g_FileErrorStringID, 2C1h
0x14000c252  jmp     loc_14000C4D0
0x14000c257  mov     edi, 1
0x14000c25c  mov     r14d, r15d
0x14000c25f  mov     ebx, edi
0x14000c261  lea     ecx, [rdi+21h]
0x14000c264  call    MatchChar
0x14000c269  test    eax, eax
0x14000c26b  jz      short loc_14000C29E
0x14000c26d  lea     rcx, [rsp+1A0h+var_158]
0x14000c272  mov     [rsp+1A0h+var_150], 100h
0x14000c27b  mov     [rsp+1A0h+var_158], rsi
0x14000c280  call    ParseString
0x14000c285  test    eax, eax
0x14000c287  jz      short loc_14000C296
0x14000c289  call    ParseEndOfLine
0x14000c28e  test    eax, eax
0x14000c290  jnz     loc_14000C3FF
0x14000c296  mov     r14d, edi
0x14000c299  jmp     loc_14000C3FC
0x14000c29e  mov     ecx, 64h ; 'd'
0x14000c2a3  call    MatchChar
0x14000c2a8  test    eax, eax
0x14000c2aa  jz      short loc_14000C312
0x14000c2ac  lea     rdi, s_DwordPrefix+2; "word:"
0x14000c2b3  mov     ecx, 77h ; 'w'
0x14000c2b8  call    MatchChar
0x14000c2bd  lea     rdi, [rdi+2]
0x14000c2c1  test    eax, eax
0x14000c2c3  jnz     short loc_14000C2C9
0x14000c2c5  lea     r14d, [rax+1]
0x14000c2c9  movzx   ecx, word ptr [rdi]
0x14000c2cc  neg     eax
0x14000c2ce  sbb     eax, eax
0x14000c2d0  and     eax, ebx
0x14000c2d2  mov     ebx, eax
0x14000c2d4  test    cx, cx
0x14000c2d7  jnz     short loc_14000C2B8
0x14000c2d9  test    eax, eax
0x14000c2db  jz      loc_14000C4B7
0x14000c2e1  call    SkipWhitespace
0x14000c2e6  mov     rcx, rsi
0x14000c2e9  call    ParseHexDword
0x14000c2ee  test    eax, eax
0x14000c2f0  jz      short loc_14000C2FB
0x14000c2f2  call    ParseEndOfLine
0x14000c2f7  test    eax, eax
0x14000c2f9  jnz     short loc_14000C304
0x14000c2fb  mov     ebx, r15d
0x14000c2fe  mov     r14d, 1
0x14000c304  mov     r15d, 4
0x14000c30a  mov     edi, r15d
0x14000c30d  jmp     loc_14000C409
0x14000c312  mov     ecx, 2Dh ; '-'
0x14000c317  call    MatchChar
0x14000c31c  test    eax, eax
0x14000c31e  jz      short loc_14000C348
0x14000c320  call    ParseEndOfLine
0x14000c325  test    eax, eax
0x14000c327  jnz     short loc_14000C331
0x14000c329  mov     r14d, edi
0x14000c32c  jmp     loc_14000C4B7
0x14000c331  mov     rdx, r13; lpValueName
0x14000c334  mov     rcx, r12; hKey
0x14000c337  call    cs:__imp_RegDeleteValueW
0x14000c33e  nop     dword ptr [rax+rax+00h]
0x14000c343  jmp     loc_14000C4B7
0x14000c348  lea     rdi, s_HexPrefix; "hex"
0x14000c34f  mov     ecx, 68h ; 'h'
0x14000c354  call    MatchChar
0x14000c359  lea     rdi, [rdi+2]
0x14000c35d  test    eax, eax
0x14000c35f  jnz     short loc_14000C365
0x14000c361  lea     r14d, [rax+1]
0x14000c365  movzx   ecx, word ptr [rdi]
0x14000c368  neg     eax
0x14000c36a  sbb     eax, eax
0x14000c36c  and     eax, ebx
0x14000c36e  mov     ebx, eax
0x14000c370  test    cx, cx
0x14000c373  jnz     short loc_14000C354
0x14000c375  test    eax, eax
0x14000c377  jz      loc_14000C4B7
0x14000c37d  mov     ecx, 28h ; '('
0x14000c382  call    MatchChar
0x14000c387  test    eax, eax
0x14000c389  jz      short loc_14000C3BE
0x14000c38b  lea     rcx, [rsp+1A0h+var_160]
0x14000c390  call    ParseHexDword
0x14000c395  test    eax, eax
0x14000c397  jz      short loc_14000C3A7
0x14000c399  mov     ecx, 29h ; ')'
0x14000c39e  call    MatchChar
0x14000c3a3  test    eax, eax
0x14000c3a5  jnz     short loc_14000C3B0
0x14000c3a7  mov     ebx, r15d
0x14000c3aa  mov     r14d, 1
0x14000c3b0  test    ebx, ebx
0x14000c3b2  jz      loc_14000C4B7
0x14000c3b8  mov     edi, [rsp+1A0h+var_160]
0x14000c3bc  jmp     short loc_14000C3C3
0x14000c3be  mov     edi, 3
0x14000c3c3  mov     ecx, 3Ah ; ':'
0x14000c3c8  mov     [rsp+1A0h+var_150], 100h
0x14000c3d1  mov     [rsp+1A0h+var_158], rsi
0x14000c3d6  call    MatchChar
0x14000c3db  test    eax, eax
0x14000c3dd  jz      short loc_14000C3F6
0x14000c3df  lea     rcx, [rsp+1A0h+var_158]
0x14000c3e4  call    ParseHexSequence
0x14000c3e9  test    eax, eax
0x14000c3eb  jz      short loc_14000C3F6
0x14000c3ed  call    ParseEndOfLine
0x14000c3f2  test    eax, eax
0x14000c3f4  jnz     short loc_14000C3FF
0x14000c3f6  mov     r14d, 1
0x14000c3fc  mov     ebx, r15d
0x14000c3ff  mov     r15d, dword ptr [rsp+1A0h+var_150]
0x14000c404  mov     rsi, [rsp+1A0h+var_158]
0x14000c409  xor     eax, eax
0x14000c40b  test    ebx, ebx
0x14000c40d  jz      loc_14000C4B7
0x14000c413  cmp     cs:g_ImportFileVersion, 500h
0x14000c41d  jnb     short loc_14000C487
0x14000c41f  cmp     edi, 2
0x14000c422  jz      short loc_14000C429
0x14000c424  cmp     edi, 7
0x14000c427  jnz     short loc_14000C487
0x14000c429  mov     [rsp+1A0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x14000c42e  xor     edx, edx; dwFlags
0x14000c430  mov     [rsp+1A0h+lpDefaultChar], rax; lpDefaultChar
0x14000c435  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000c439  mov     [rsp+1A0h+MultiByteStr], al
0x14000c43d  mov     r8, r13; lpWideCharStr
0x14000c440  lea     rax, [rsp+1A0h+MultiByteStr]
0x14000c445  mov     [rsp+1A0h+cbMultiByte], 100h; cbMultiByte
0x14000c44d  lea     ecx, [rdx+3]; CodePage
0x14000c450  mov     [rsp+1A0h+lpMultiByteStr], rax; lpMultiByteStr
0x14000c455  call    cs:__imp_WideCharToMultiByte
0x14000c45c  nop     dword ptr [rax+rax+00h]
0x14000c461  mov     r9d, edi; dwType
0x14000c464  mov     [rsp+1A0h+cbMultiByte], r15d; cbData
0x14000c469  xor     r8d, r8d; Reserved
0x14000c46c  mov     [rsp+1A0h+lpMultiByteStr], rsi; lpData
0x14000c471  lea     rdx, [rsp+1A0h+MultiByteStr]; lpValueName
0x14000c476  mov     rcx, r12; hKey
0x14000c479  call    cs:__imp_RegSetValueExA
0x14000c480  nop     dword ptr [rax+rax+00h]
0x14000c485  jmp     short loc_14000C4A9
0x14000c487  mov     [rsp+1A0h+cbMultiByte], r15d; cbData
0x14000c48c  mov     r9d, edi; dwType
0x14000c48f  xor     r8d, r8d; Reserved
0x14000c492  mov     [rsp+1A0h+lpMultiByteStr], rsi; lpData
0x14000c497  mov     rdx, r13; lpValueName
0x14000c49a  mov     rcx, r12; hKey
0x14000c49d  call    cs:__imp_RegSetValueExW
0x14000c4a4  nop     dword ptr [rax+rax+00h]
0x14000c4a9  test    eax, eax
0x14000c4ab  jz      short loc_14000C4B7
0x14000c4ad  mov     cs:g_FileErrorStringID, 2C1h
0x14000c4b7  mov     rcx, rsi; hMem
0x14000c4ba  call    cs:__imp_LocalFree
0x14000c4c1  nop     dword ptr [rax+rax+00h]
0x14000c4c6  test    r14d, r14d
0x14000c4c9  jz      short loc_14000C4D0
0x14000c4cb  call    SkipPastEndOfLine
0x14000c4d0  mov     rcx, [rbp+0A0h+var_40]
0x14000c4d4  xor     rcx, rsp; StackCookie
0x14000c4d7  call    __security_check_cookie
0x14000c4dc  mov     rbx, [rsp+1A0h+arg_10]
0x14000c4e4  add     rsp, 170h
0x14000c4eb  pop     r15
0x14000c4ed  pop     r14
0x14000c4ef  pop     r13
0x14000c4f1  pop     r12
0x14000c4f3  pop     rdi
0x14000c4f4  pop     rsi
0x14000c4f5  pop     rbp
0x14000c4f6  retn
```
