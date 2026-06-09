# ParseValue

- ea: `0x14000ba40`
- end: `0x14000bd3b`
- name: `ParseValue`
- size: `763`
- prototype: `BYTE *__fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000ad40`

## callees

- `0x140001340`
- `0x14000b480`
- `0x14000b5a8`
- `0x14000b810`
- `0x14000b86c`
- `0x14000b93c`
- `0x14000ba40`
- `0x14000c500`
- `0x14000c560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000bced`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000bced`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000bb99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000bb99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x14000bccf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x14000bccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000bd04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000bd04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ba9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ba9c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000bcb1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000bcb1`

## pseudocode

```c
BYTE *__fastcall ParseValue(HKEY hKey, LPCWSTR lpValueName)
{
  BYTE *result; // rax
  BYTE *v5; // rsi
  DWORD v6; // edi
  int v7; // r14d
  int v8; // ebx
  wchar_t *v9; // rdi
  __int64 v10; // rcx
  int matched; // eax
  int v12; // eax
  DWORD v13; // r15d
  const wchar_t *v14; // rdi
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  LSTATUS v18; // eax
  DWORD v19; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  CHAR MultiByteStr[256]; // [rsp+60h] [rbp-A0h] BYREF

  v19 = 0;
  SkipWhitespace();
  if ( (unsigned int)MatchChar(61) )
  {
    SkipWhitespace();
    result = (BYTE *)LocalAlloc(0x40u, 0x100u);
    v5 = result;
    if ( !result )
    {
      g_FileErrorStringID = 705;
      return result;
    }
    v6 = 1;
    v7 = 0;
    v8 = 1;
    if ( (unsigned int)MatchChar(34) )
    {
      v21 = 256;
      v20 = v5;
      if ( (unsigned int)ParseString(&v20) && (unsigned int)ParseEndOfLine() )
        goto LABEL_39;
      v7 = 1;
LABEL_38:
      v8 = 0;
LABEL_39:
      v13 = v21;
      v5 = v20;
LABEL_40:
      if ( v8 )
      {
        if ( (unsigned int)g_ImportFileVersion < 0x500 && (v6 == 2 || v6 == 7) )
        {
          MultiByteStr[0] = 0;
          WideCharToMultiByte(3u, 0, lpValueName, -1, MultiByteStr, 256, 0, 0);
          v18 = RegSetValueExA(hKey, MultiByteStr, 0, v6, v5, v13);
        }
        else
        {
          v18 = RegSetValueExW(hKey, lpValueName, 0, v6, v5, v13);
        }
        if ( v18 )
          g_FileErrorStringID = 705;
      }
      goto LABEL_48;
    }
    if ( (unsigned int)MatchChar(100) )
    {
      v9 = L"word:";
      v10 = 119;
      do
      {
        matched = MatchChar(v10);
        ++v9;
        if ( !matched )
          v7 = 1;
        v10 = *v9;
        v12 = matched != 0 ? v8 : 0;
        v8 = v12;
      }
      while ( (_WORD)v10 );
      if ( v12 )
      {
        SkipWhitespace();
        if ( !(unsigned int)ParseHexDword(v5) || !(unsigned int)ParseEndOfLine() )
        {
          v8 = 0;
          v7 = 1;
        }
        v13 = 4;
        v6 = 4;
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
          v7 = 1;
        goto LABEL_48;
      }
      v14 = L"hex";
      v15 = 104;
      do
      {
        v16 = MatchChar(v15);
        ++v14;
        if ( !v16 )
          v7 = 1;
        v15 = *v14;
        v17 = v16 != 0 ? v8 : 0;
        v8 = v17;
      }
      while ( (_WORD)v15 );
      if ( v17 )
      {
        if ( (unsigned int)MatchChar(40) )
        {
          if ( !(unsigned int)ParseHexDword(&v19) || !(unsigned int)MatchChar(41) )
          {
            v8 = 0;
            v7 = 1;
          }
          if ( !v8 )
            goto LABEL_48;
          v6 = v19;
        }
        else
        {
          v6 = 3;
        }
        v21 = 256;
        v20 = v5;
        if ( (unsigned int)MatchChar(58) && (unsigned int)ParseHexSequence(&v20) && (unsigned int)ParseEndOfLine() )
          goto LABEL_39;
        v7 = 1;
        goto LABEL_38;
      }
    }
LABEL_48:
    result = (BYTE *)LocalFree(v5);
    if ( !v7 )
      return result;
  }
  return (BYTE *)SkipPastEndOfLine();
}

```

## disassembly

```asm
0x14000ba40  mov     [rsp-8+arg_10], rbx
0x14000ba45  push    rbp
0x14000ba46  push    rsi
0x14000ba47  push    rdi
0x14000ba48  push    r12
0x14000ba4a  push    r13
0x14000ba4c  push    r14
0x14000ba4e  push    r15
0x14000ba50  lea     rbp, [rsp-70h]
0x14000ba55  sub     rsp, 170h
0x14000ba5c  mov     rax, cs:__security_cookie
0x14000ba63  xor     rax, rsp
0x14000ba66  mov     [rbp+0A0h+var_40], rax
0x14000ba6a  xor     r15d, r15d
0x14000ba6d  mov     r13, rdx
0x14000ba70  mov     [rsp+1A0h+var_160], r15d
0x14000ba75  mov     r12, rcx
0x14000ba78  call    SkipWhitespace
0x14000ba7d  lea     ecx, [r15+3Dh]
0x14000ba81  call    MatchChar
0x14000ba86  test    eax, eax
0x14000ba88  jz      loc_14000BD0F
0x14000ba8e  call    SkipWhitespace
0x14000ba93  mov     edx, 100h; uBytes
0x14000ba98  lea     ecx, [r15+40h]; uFlags
0x14000ba9c  call    cs:__imp_LocalAlloc
0x14000baa2  mov     rsi, rax
0x14000baa5  test    rax, rax
0x14000baa8  jnz     short loc_14000BAB9
0x14000baaa  mov     cs:g_FileErrorStringID, 2C1h
0x14000bab4  jmp     loc_14000BD14
0x14000bab9  mov     edi, 1
0x14000babe  mov     r14d, r15d
0x14000bac1  mov     ebx, edi
0x14000bac3  lea     ecx, [rdi+21h]
0x14000bac6  call    MatchChar
0x14000bacb  test    eax, eax
0x14000bacd  jz      short loc_14000BB00
0x14000bacf  lea     rcx, [rsp+1A0h+var_158]
0x14000bad4  mov     [rsp+1A0h+var_150], 100h
0x14000badd  mov     [rsp+1A0h+var_158], rsi
0x14000bae2  call    ParseString
0x14000bae7  test    eax, eax
0x14000bae9  jz      short loc_14000BAF8
0x14000baeb  call    ParseEndOfLine
0x14000baf0  test    eax, eax
0x14000baf2  jnz     loc_14000BC5B
0x14000baf8  mov     r14d, edi
0x14000bafb  jmp     loc_14000BC58
0x14000bb00  mov     ecx, 64h ; 'd'
0x14000bb05  call    MatchChar
0x14000bb0a  test    eax, eax
0x14000bb0c  jz      short loc_14000BB74
0x14000bb0e  lea     rdi, s_DwordPrefix+2; "word:"
0x14000bb15  mov     ecx, 77h ; 'w'
0x14000bb1a  call    MatchChar
0x14000bb1f  lea     rdi, [rdi+2]
0x14000bb23  test    eax, eax
0x14000bb25  jnz     short loc_14000BB2B
0x14000bb27  lea     r14d, [rax+1]
0x14000bb2b  movzx   ecx, word ptr [rdi]
0x14000bb2e  neg     eax
0x14000bb30  sbb     eax, eax
0x14000bb32  and     eax, ebx
0x14000bb34  mov     ebx, eax
0x14000bb36  test    cx, cx
0x14000bb39  jnz     short loc_14000BB1A
0x14000bb3b  test    eax, eax
0x14000bb3d  jz      loc_14000BD01
0x14000bb43  call    SkipWhitespace
0x14000bb48  mov     rcx, rsi
0x14000bb4b  call    ParseHexDword
0x14000bb50  test    eax, eax
0x14000bb52  jz      short loc_14000BB5D
0x14000bb54  call    ParseEndOfLine
0x14000bb59  test    eax, eax
0x14000bb5b  jnz     short loc_14000BB66
0x14000bb5d  mov     ebx, r15d
0x14000bb60  mov     r14d, 1
0x14000bb66  mov     r15d, 4
0x14000bb6c  mov     edi, r15d
0x14000bb6f  jmp     loc_14000BC65
0x14000bb74  mov     ecx, 2Dh ; '-'
0x14000bb79  call    MatchChar
0x14000bb7e  test    eax, eax
0x14000bb80  jz      short loc_14000BBA4
0x14000bb82  call    ParseEndOfLine
0x14000bb87  test    eax, eax
0x14000bb89  jnz     short loc_14000BB93
0x14000bb8b  mov     r14d, edi
0x14000bb8e  jmp     loc_14000BD01
0x14000bb93  mov     rdx, r13; lpValueName
0x14000bb96  mov     rcx, r12; hKey
0x14000bb99  call    cs:__imp_RegDeleteValueW
0x14000bb9f  jmp     loc_14000BD01
0x14000bba4  lea     rdi, s_HexPrefix; "hex"
0x14000bbab  mov     ecx, 68h ; 'h'
0x14000bbb0  call    MatchChar
0x14000bbb5  lea     rdi, [rdi+2]
0x14000bbb9  test    eax, eax
0x14000bbbb  jnz     short loc_14000BBC1
0x14000bbbd  lea     r14d, [rax+1]
0x14000bbc1  movzx   ecx, word ptr [rdi]
0x14000bbc4  neg     eax
0x14000bbc6  sbb     eax, eax
0x14000bbc8  and     eax, ebx
0x14000bbca  mov     ebx, eax
0x14000bbcc  test    cx, cx
0x14000bbcf  jnz     short loc_14000BBB0
0x14000bbd1  test    eax, eax
0x14000bbd3  jz      loc_14000BD01
0x14000bbd9  mov     ecx, 28h ; '('
0x14000bbde  call    MatchChar
0x14000bbe3  test    eax, eax
0x14000bbe5  jz      short loc_14000BC1A
0x14000bbe7  lea     rcx, [rsp+1A0h+var_160]
0x14000bbec  call    ParseHexDword
0x14000bbf1  test    eax, eax
0x14000bbf3  jz      short loc_14000BC03
0x14000bbf5  mov     ecx, 29h ; ')'
0x14000bbfa  call    MatchChar
0x14000bbff  test    eax, eax
0x14000bc01  jnz     short loc_14000BC0C
0x14000bc03  mov     ebx, r15d
0x14000bc06  mov     r14d, 1
0x14000bc0c  test    ebx, ebx
0x14000bc0e  jz      loc_14000BD01
0x14000bc14  mov     edi, [rsp+1A0h+var_160]
0x14000bc18  jmp     short loc_14000BC1F
0x14000bc1a  mov     edi, 3
0x14000bc1f  mov     ecx, 3Ah ; ':'
0x14000bc24  mov     [rsp+1A0h+var_150], 100h
0x14000bc2d  mov     [rsp+1A0h+var_158], rsi
0x14000bc32  call    MatchChar
0x14000bc37  test    eax, eax
0x14000bc39  jz      short loc_14000BC52
0x14000bc3b  lea     rcx, [rsp+1A0h+var_158]
0x14000bc40  call    ParseHexSequence
0x14000bc45  test    eax, eax
0x14000bc47  jz      short loc_14000BC52
0x14000bc49  call    ParseEndOfLine
0x14000bc4e  test    eax, eax
0x14000bc50  jnz     short loc_14000BC5B
0x14000bc52  mov     r14d, 1
0x14000bc58  mov     ebx, r15d
0x14000bc5b  mov     r15d, dword ptr [rsp+1A0h+var_150]
0x14000bc60  mov     rsi, [rsp+1A0h+var_158]
0x14000bc65  xor     eax, eax
0x14000bc67  test    ebx, ebx
0x14000bc69  jz      loc_14000BD01
0x14000bc6f  cmp     cs:g_ImportFileVersion, 500h
0x14000bc79  jnb     short loc_14000BCD7
0x14000bc7b  cmp     edi, 2
0x14000bc7e  jz      short loc_14000BC85
0x14000bc80  cmp     edi, 7
0x14000bc83  jnz     short loc_14000BCD7
0x14000bc85  mov     [rsp+1A0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x14000bc8a  xor     edx, edx; dwFlags
0x14000bc8c  mov     [rsp+1A0h+lpDefaultChar], rax; lpDefaultChar
0x14000bc91  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000bc95  mov     [rsp+1A0h+MultiByteStr], al
0x14000bc99  mov     r8, r13; lpWideCharStr
0x14000bc9c  lea     rax, [rsp+1A0h+MultiByteStr]
0x14000bca1  mov     [rsp+1A0h+cbMultiByte], 100h; cbMultiByte
0x14000bca9  lea     ecx, [rdx+3]; CodePage
0x14000bcac  mov     [rsp+1A0h+lpMultiByteStr], rax; lpMultiByteStr
0x14000bcb1  call    cs:__imp_WideCharToMultiByte
0x14000bcb7  mov     r9d, edi; dwType
0x14000bcba  mov     [rsp+1A0h+cbMultiByte], r15d; cbData
0x14000bcbf  xor     r8d, r8d; Reserved
0x14000bcc2  mov     [rsp+1A0h+lpMultiByteStr], rsi; lpData
0x14000bcc7  lea     rdx, [rsp+1A0h+MultiByteStr]; lpValueName
0x14000bccc  mov     rcx, r12; hKey
0x14000bccf  call    cs:__imp_RegSetValueExA
0x14000bcd5  jmp     short loc_14000BCF3
0x14000bcd7  mov     [rsp+1A0h+cbMultiByte], r15d; cbData
0x14000bcdc  mov     r9d, edi; dwType
0x14000bcdf  xor     r8d, r8d; Reserved
0x14000bce2  mov     [rsp+1A0h+lpMultiByteStr], rsi; lpData
0x14000bce7  mov     rdx, r13; lpValueName
0x14000bcea  mov     rcx, r12; hKey
0x14000bced  call    cs:__imp_RegSetValueExW
0x14000bcf3  test    eax, eax
0x14000bcf5  jz      short loc_14000BD01
0x14000bcf7  mov     cs:g_FileErrorStringID, 2C1h
0x14000bd01  mov     rcx, rsi; hMem
0x14000bd04  call    cs:__imp_LocalFree
0x14000bd0a  test    r14d, r14d
0x14000bd0d  jz      short loc_14000BD14
0x14000bd0f  call    SkipPastEndOfLine
0x14000bd14  mov     rcx, [rbp+0A0h+var_40]
0x14000bd18  xor     rcx, rsp; StackCookie
0x14000bd1b  call    __security_check_cookie
0x14000bd20  mov     rbx, [rsp+1A0h+arg_10]
0x14000bd28  add     rsp, 170h
0x14000bd2f  pop     r15
0x14000bd31  pop     r14
0x14000bd33  pop     r13
0x14000bd35  pop     r12
0x14000bd37  pop     rdi
0x14000bd38  pop     rsi
0x14000bd39  pop     rbp
0x14000bd3a  retn
```
