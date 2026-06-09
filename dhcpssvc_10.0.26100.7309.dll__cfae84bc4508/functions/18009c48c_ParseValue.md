# ParseValue

- ea: `0x18009c48c`
- end: `0x18009c6e8`
- name: `ParseValue`
- size: `604`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18009be2c`

## callees

- `0x18009bf54`
- `0x18009bfa0`
- `0x18009c1e0`
- `0x18009c248`
- `0x18009c344`
- `0x18009c48c`
- `0x18009ccec`
- `0x18009cd50`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18009c6ab`
- `ADVAPI32!RegSetValueExW` at `0x18009c6ab`
- `ADVAPI32!RegDeleteValueW` at `0x18009c5cf`
- `ADVAPI32!RegDeleteValueW` at `0x18009c5cf`
- `KERNEL32!LocalAlloc` at `0x18009c4dd`
- `KERNEL32!LocalAlloc` at `0x18009c4dd`
- `KERNEL32!LocalFree` at `0x18009c6ba`
- `KERNEL32!LocalFree` at `0x18009c6ba`

## pseudocode

```c
BYTE *__fastcall ParseValue(HKEY hKey, LPCWSTR lpValueName)
{
  int v2; // ebx
  int v3; // edi
  DWORD v4; // esi
  BYTE *result; // rax
  BYTE *lpData; // r14
  wchar_t *v9; // rsi
  __int64 v10; // rcx
  int matched; // eax
  int v12; // eax
  DWORD cbData; // eax
  const wchar_t *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  BYTE *v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+38h] [rbp-8h]
  int v20; // [rsp+90h] [rbp+50h] BYREF

  v2 = 1;
  v20 = 1;
  v3 = 0;
  v4 = 1;
  SkipWhitespace();
  if ( (unsigned int)MatchChar(61) )
  {
    SkipWhitespace();
    result = (BYTE *)LocalAlloc(0x40u, 0x100u);
    lpData = result;
    if ( !result )
    {
      g_FileErrorStringID = 8;
      return result;
    }
    if ( (unsigned int)MatchChar(34) )
    {
      v19 = 256;
      v18 = lpData;
      if ( (unsigned int)ParseString(&v18) && (unsigned int)ParseEndOfLine() )
        goto LABEL_39;
      v3 = 1;
LABEL_38:
      v2 = 0;
LABEL_39:
      cbData = v19;
      lpData = v18;
LABEL_40:
      if ( v2 )
        RegSetValueExW(hKey, lpValueName, 0, v4, lpData, cbData);
      goto LABEL_42;
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
          v3 = 1;
        v10 = *v9;
        v12 = matched != 0 ? v2 : 0;
        v2 = v12;
      }
      while ( (_WORD)v10 );
      if ( v12 )
      {
        SkipWhitespace();
        if ( !(unsigned int)ParseHexDword(lpData) || !(unsigned int)ParseEndOfLine() )
        {
          v2 = 0;
          v3 = 1;
        }
        v4 = 4;
        cbData = 4;
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
          v3 = 1;
        goto LABEL_42;
      }
      v14 = L"hex";
      v15 = 104;
      do
      {
        v16 = MatchChar(v15);
        ++v14;
        if ( !v16 )
          v3 = 1;
        v15 = *v14;
        v17 = v16 != 0 ? v2 : 0;
        v2 = v17;
      }
      while ( (_WORD)v15 );
      if ( v17 )
      {
        if ( (unsigned int)MatchChar(40) )
        {
          if ( !(unsigned int)ParseHexDword(&v20) || !(unsigned int)MatchChar(41) )
          {
            v2 = 0;
            v3 = 1;
          }
          if ( !v2 )
            goto LABEL_42;
          v4 = v20;
        }
        else
        {
          v4 = 3;
        }
        v19 = 256;
        v18 = lpData;
        if ( (unsigned int)MatchChar(58) && (unsigned int)ParseHexSequence(&v18) && (unsigned int)ParseEndOfLine() )
          goto LABEL_39;
        v3 = 1;
        goto LABEL_38;
      }
    }
LABEL_42:
    result = (BYTE *)LocalFree(lpData);
    if ( !v3 )
      return result;
  }
  return (BYTE *)SkipPastEndOfLine();
}

```

## disassembly

```asm
0x18009c48c  mov     [rsp-38h+arg_0], rbx
0x18009c491  push    rbp
0x18009c492  push    rsi
0x18009c493  push    rdi
0x18009c494  push    r12
0x18009c496  push    r13
0x18009c498  push    r14
0x18009c49a  push    r15
0x18009c49c  mov     rbp, rsp
0x18009c49f  sub     rsp, 40h
0x18009c4a3  mov     eax, 1
0x18009c4a8  xor     r13d, r13d
0x18009c4ab  mov     ebx, eax
0x18009c4ad  mov     [rbp+arg_10], eax
0x18009c4b0  mov     edi, r13d
0x18009c4b3  mov     esi, eax
0x18009c4b5  mov     r15, rdx
0x18009c4b8  mov     r12, rcx
0x18009c4bb  call    SkipWhitespace
0x18009c4c0  lea     ecx, [rsi+3Ch]
0x18009c4c3  call    MatchChar
0x18009c4c8  test    eax, eax
0x18009c4ca  jz      loc_18009C6CA
0x18009c4d0  call    SkipWhitespace
0x18009c4d5  mov     edx, 100h; uBytes
0x18009c4da  lea     ecx, [rsi+3Fh]; uFlags
0x18009c4dd  call    cs:__imp_LocalAlloc
0x18009c4e4  nop     dword ptr [rax+rax+00h]
0x18009c4e9  mov     r14, rax
0x18009c4ec  test    rax, rax
0x18009c4ef  jnz     short loc_18009C500
0x18009c4f1  mov     cs:g_FileErrorStringID, 8
0x18009c4fb  jmp     loc_18009C6CF
0x18009c500  mov     ecx, 22h ; '"'
0x18009c505  call    MatchChar
0x18009c50a  test    eax, eax
0x18009c50c  jz      short loc_18009C53B
0x18009c50e  lea     rcx, [rbp+var_10]
0x18009c512  mov     [rbp+var_8], 100h
0x18009c51a  mov     [rbp+var_10], r14
0x18009c51e  call    ParseString
0x18009c523  test    eax, eax
0x18009c525  jz      short loc_18009C534
0x18009c527  call    ParseEndOfLine
0x18009c52c  test    eax, eax
0x18009c52e  jnz     loc_18009C68B
0x18009c534  mov     edi, esi
0x18009c536  jmp     loc_18009C688
0x18009c53b  mov     ecx, 64h ; 'd'
0x18009c540  call    MatchChar
0x18009c545  test    eax, eax
0x18009c547  jz      short loc_18009C5AB
0x18009c549  lea     rsi, s_DwordPrefix+2; "word:"
0x18009c550  mov     ecx, 77h ; 'w'
0x18009c555  call    MatchChar
0x18009c55a  lea     rsi, [rsi+2]
0x18009c55e  test    eax, eax
0x18009c560  jnz     short loc_18009C565
0x18009c562  lea     edi, [rax+1]
0x18009c565  movzx   ecx, word ptr [rsi]
0x18009c568  neg     eax
0x18009c56a  sbb     eax, eax
0x18009c56c  and     eax, ebx
0x18009c56e  mov     ebx, eax
0x18009c570  test    cx, cx
0x18009c573  jnz     short loc_18009C555
0x18009c575  test    eax, eax
0x18009c577  jz      loc_18009C6B7
0x18009c57d  call    SkipWhitespace
0x18009c582  mov     rcx, r14
0x18009c585  call    ParseHexDword
0x18009c58a  test    eax, eax
0x18009c58c  jz      short loc_18009C597
0x18009c58e  call    ParseEndOfLine
0x18009c593  test    eax, eax
0x18009c595  jnz     short loc_18009C59F
0x18009c597  mov     ebx, r13d
0x18009c59a  mov     edi, 1
0x18009c59f  mov     esi, 4
0x18009c5a4  mov     eax, esi
0x18009c5a6  jmp     loc_18009C692
0x18009c5ab  mov     ecx, 2Dh ; '-'
0x18009c5b0  call    MatchChar
0x18009c5b5  test    eax, eax
0x18009c5b7  jz      short loc_18009C5E0
0x18009c5b9  call    ParseEndOfLine
0x18009c5be  test    eax, eax
0x18009c5c0  jnz     short loc_18009C5C9
0x18009c5c2  mov     edi, ebx
0x18009c5c4  jmp     loc_18009C6B7
0x18009c5c9  mov     rdx, r15; lpValueName
0x18009c5cc  mov     rcx, r12; hKey
0x18009c5cf  call    cs:__imp_RegDeleteValueW
0x18009c5d6  nop     dword ptr [rax+rax+00h]
0x18009c5db  jmp     loc_18009C6B7
0x18009c5e0  lea     rsi, s_HexPrefix; "hex"
0x18009c5e7  mov     ecx, 68h ; 'h'
0x18009c5ec  call    MatchChar
0x18009c5f1  lea     rsi, [rsi+2]
0x18009c5f5  test    eax, eax
0x18009c5f7  jnz     short loc_18009C5FC
0x18009c5f9  lea     edi, [rax+1]
0x18009c5fc  movzx   ecx, word ptr [rsi]
0x18009c5ff  neg     eax
0x18009c601  sbb     eax, eax
0x18009c603  and     eax, ebx
0x18009c605  mov     ebx, eax
0x18009c607  test    cx, cx
0x18009c60a  jnz     short loc_18009C5EC
0x18009c60c  test    eax, eax
0x18009c60e  jz      loc_18009C6B7
0x18009c614  mov     ecx, 28h ; '('
0x18009c619  call    MatchChar
0x18009c61e  test    eax, eax
0x18009c620  jz      short loc_18009C64E
0x18009c622  lea     rcx, [rbp+arg_10]
0x18009c626  call    ParseHexDword
0x18009c62b  test    eax, eax
0x18009c62d  jz      short loc_18009C63D
0x18009c62f  mov     ecx, 29h ; ')'
0x18009c634  call    MatchChar
0x18009c639  test    eax, eax
0x18009c63b  jnz     short loc_18009C645
0x18009c63d  mov     ebx, r13d
0x18009c640  mov     edi, 1
0x18009c645  test    ebx, ebx
0x18009c647  jz      short loc_18009C6B7
0x18009c649  mov     esi, [rbp+arg_10]
0x18009c64c  jmp     short loc_18009C653
0x18009c64e  mov     esi, 3
0x18009c653  mov     ecx, 3Ah ; ':'
0x18009c658  mov     [rbp+var_8], 100h
0x18009c660  mov     [rbp+var_10], r14
0x18009c664  call    MatchChar
0x18009c669  test    eax, eax
0x18009c66b  jz      short loc_18009C683
0x18009c66d  lea     rcx, [rbp+var_10]
0x18009c671  call    ParseHexSequence
0x18009c676  test    eax, eax
0x18009c678  jz      short loc_18009C683
0x18009c67a  call    ParseEndOfLine
0x18009c67f  test    eax, eax
0x18009c681  jnz     short loc_18009C68B
0x18009c683  mov     edi, 1
0x18009c688  mov     ebx, r13d
0x18009c68b  mov     eax, dword ptr [rbp+var_8]
0x18009c68e  mov     r14, [rbp+var_10]
0x18009c692  test    ebx, ebx
0x18009c694  jz      short loc_18009C6B7
0x18009c696  mov     [rsp+40h+cbData], eax; cbData
0x18009c69a  mov     r9d, esi; dwType
0x18009c69d  xor     r8d, r8d; Reserved
0x18009c6a0  mov     [rsp+40h+lpData], r14; lpData
0x18009c6a5  mov     rdx, r15; lpValueName
0x18009c6a8  mov     rcx, r12; hKey
0x18009c6ab  call    cs:__imp_RegSetValueExW
0x18009c6b2  nop     dword ptr [rax+rax+00h]
0x18009c6b7  mov     rcx, r14; hMem
0x18009c6ba  call    cs:__imp_LocalFree
0x18009c6c1  nop     dword ptr [rax+rax+00h]
0x18009c6c6  test    edi, edi
0x18009c6c8  jz      short loc_18009C6CF
0x18009c6ca  call    SkipPastEndOfLine
0x18009c6cf  mov     rbx, [rsp+40h+arg_0]
0x18009c6d7  add     rsp, 40h
0x18009c6db  pop     r15
0x18009c6dd  pop     r14
0x18009c6df  pop     r13
0x18009c6e1  pop     r12
0x18009c6e3  pop     rdi
0x18009c6e4  pop     rsi
0x18009c6e5  pop     rbp
0x18009c6e6  retn
```
