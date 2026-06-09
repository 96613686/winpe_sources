# ParseValue

- ea: `0x18009d154`
- end: `0x18009d3b0`
- name: `ParseValue`
- size: `604`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18009cafc`

## callees

- `0x18009cc24`
- `0x18009cc70`
- `0x18009ceb0`
- `0x18009cf18`
- `0x18009d014`
- `0x18009d154`
- `0x18009d9b4`
- `0x18009da18`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18009d373`
- `ADVAPI32!RegSetValueExW` at `0x18009d373`
- `ADVAPI32!RegDeleteValueW` at `0x18009d297`
- `ADVAPI32!RegDeleteValueW` at `0x18009d297`
- `KERNEL32!LocalAlloc` at `0x18009d1a5`
- `KERNEL32!LocalAlloc` at `0x18009d1a5`
- `KERNEL32!LocalFree` at `0x18009d382`
- `KERNEL32!LocalFree` at `0x18009d382`

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
0x18009d154  mov     [rsp-38h+arg_0], rbx
0x18009d159  push    rbp
0x18009d15a  push    rsi
0x18009d15b  push    rdi
0x18009d15c  push    r12
0x18009d15e  push    r13
0x18009d160  push    r14
0x18009d162  push    r15
0x18009d164  mov     rbp, rsp
0x18009d167  sub     rsp, 40h
0x18009d16b  mov     eax, 1
0x18009d170  xor     r13d, r13d
0x18009d173  mov     ebx, eax
0x18009d175  mov     [rbp+arg_10], eax
0x18009d178  mov     edi, r13d
0x18009d17b  mov     esi, eax
0x18009d17d  mov     r15, rdx
0x18009d180  mov     r12, rcx
0x18009d183  call    SkipWhitespace
0x18009d188  lea     ecx, [rsi+3Ch]
0x18009d18b  call    MatchChar
0x18009d190  test    eax, eax
0x18009d192  jz      loc_18009D392
0x18009d198  call    SkipWhitespace
0x18009d19d  mov     edx, 100h; uBytes
0x18009d1a2  lea     ecx, [rsi+3Fh]; uFlags
0x18009d1a5  call    cs:__imp_LocalAlloc
0x18009d1ac  nop     dword ptr [rax+rax+00h]
0x18009d1b1  mov     r14, rax
0x18009d1b4  test    rax, rax
0x18009d1b7  jnz     short loc_18009D1C8
0x18009d1b9  mov     cs:g_FileErrorStringID, 8
0x18009d1c3  jmp     loc_18009D397
0x18009d1c8  mov     ecx, 22h ; '"'
0x18009d1cd  call    MatchChar
0x18009d1d2  test    eax, eax
0x18009d1d4  jz      short loc_18009D203
0x18009d1d6  lea     rcx, [rbp+var_10]
0x18009d1da  mov     [rbp+var_8], 100h
0x18009d1e2  mov     [rbp+var_10], r14
0x18009d1e6  call    ParseString
0x18009d1eb  test    eax, eax
0x18009d1ed  jz      short loc_18009D1FC
0x18009d1ef  call    ParseEndOfLine
0x18009d1f4  test    eax, eax
0x18009d1f6  jnz     loc_18009D353
0x18009d1fc  mov     edi, esi
0x18009d1fe  jmp     loc_18009D350
0x18009d203  mov     ecx, 64h ; 'd'
0x18009d208  call    MatchChar
0x18009d20d  test    eax, eax
0x18009d20f  jz      short loc_18009D273
0x18009d211  lea     rsi, s_DwordPrefix+2; "word:"
0x18009d218  mov     ecx, 77h ; 'w'
0x18009d21d  call    MatchChar
0x18009d222  lea     rsi, [rsi+2]
0x18009d226  test    eax, eax
0x18009d228  jnz     short loc_18009D22D
0x18009d22a  lea     edi, [rax+1]
0x18009d22d  movzx   ecx, word ptr [rsi]
0x18009d230  neg     eax
0x18009d232  sbb     eax, eax
0x18009d234  and     eax, ebx
0x18009d236  mov     ebx, eax
0x18009d238  test    cx, cx
0x18009d23b  jnz     short loc_18009D21D
0x18009d23d  test    eax, eax
0x18009d23f  jz      loc_18009D37F
0x18009d245  call    SkipWhitespace
0x18009d24a  mov     rcx, r14
0x18009d24d  call    ParseHexDword
0x18009d252  test    eax, eax
0x18009d254  jz      short loc_18009D25F
0x18009d256  call    ParseEndOfLine
0x18009d25b  test    eax, eax
0x18009d25d  jnz     short loc_18009D267
0x18009d25f  mov     ebx, r13d
0x18009d262  mov     edi, 1
0x18009d267  mov     esi, 4
0x18009d26c  mov     eax, esi
0x18009d26e  jmp     loc_18009D35A
0x18009d273  mov     ecx, 2Dh ; '-'
0x18009d278  call    MatchChar
0x18009d27d  test    eax, eax
0x18009d27f  jz      short loc_18009D2A8
0x18009d281  call    ParseEndOfLine
0x18009d286  test    eax, eax
0x18009d288  jnz     short loc_18009D291
0x18009d28a  mov     edi, ebx
0x18009d28c  jmp     loc_18009D37F
0x18009d291  mov     rdx, r15; lpValueName
0x18009d294  mov     rcx, r12; hKey
0x18009d297  call    cs:__imp_RegDeleteValueW
0x18009d29e  nop     dword ptr [rax+rax+00h]
0x18009d2a3  jmp     loc_18009D37F
0x18009d2a8  lea     rsi, s_HexPrefix; "hex"
0x18009d2af  mov     ecx, 68h ; 'h'
0x18009d2b4  call    MatchChar
0x18009d2b9  lea     rsi, [rsi+2]
0x18009d2bd  test    eax, eax
0x18009d2bf  jnz     short loc_18009D2C4
0x18009d2c1  lea     edi, [rax+1]
0x18009d2c4  movzx   ecx, word ptr [rsi]
0x18009d2c7  neg     eax
0x18009d2c9  sbb     eax, eax
0x18009d2cb  and     eax, ebx
0x18009d2cd  mov     ebx, eax
0x18009d2cf  test    cx, cx
0x18009d2d2  jnz     short loc_18009D2B4
0x18009d2d4  test    eax, eax
0x18009d2d6  jz      loc_18009D37F
0x18009d2dc  mov     ecx, 28h ; '('
0x18009d2e1  call    MatchChar
0x18009d2e6  test    eax, eax
0x18009d2e8  jz      short loc_18009D316
0x18009d2ea  lea     rcx, [rbp+arg_10]
0x18009d2ee  call    ParseHexDword
0x18009d2f3  test    eax, eax
0x18009d2f5  jz      short loc_18009D305
0x18009d2f7  mov     ecx, 29h ; ')'
0x18009d2fc  call    MatchChar
0x18009d301  test    eax, eax
0x18009d303  jnz     short loc_18009D30D
0x18009d305  mov     ebx, r13d
0x18009d308  mov     edi, 1
0x18009d30d  test    ebx, ebx
0x18009d30f  jz      short loc_18009D37F
0x18009d311  mov     esi, [rbp+arg_10]
0x18009d314  jmp     short loc_18009D31B
0x18009d316  mov     esi, 3
0x18009d31b  mov     ecx, 3Ah ; ':'
0x18009d320  mov     [rbp+var_8], 100h
0x18009d328  mov     [rbp+var_10], r14
0x18009d32c  call    MatchChar
0x18009d331  test    eax, eax
0x18009d333  jz      short loc_18009D34B
0x18009d335  lea     rcx, [rbp+var_10]
0x18009d339  call    ParseHexSequence
0x18009d33e  test    eax, eax
0x18009d340  jz      short loc_18009D34B
0x18009d342  call    ParseEndOfLine
0x18009d347  test    eax, eax
0x18009d349  jnz     short loc_18009D353
0x18009d34b  mov     edi, 1
0x18009d350  mov     ebx, r13d
0x18009d353  mov     eax, dword ptr [rbp+var_8]
0x18009d356  mov     r14, [rbp+var_10]
0x18009d35a  test    ebx, ebx
0x18009d35c  jz      short loc_18009D37F
0x18009d35e  mov     [rsp+40h+cbData], eax; cbData
0x18009d362  mov     r9d, esi; dwType
0x18009d365  xor     r8d, r8d; Reserved
0x18009d368  mov     [rsp+40h+lpData], r14; lpData
0x18009d36d  mov     rdx, r15; lpValueName
0x18009d370  mov     rcx, r12; hKey
0x18009d373  call    cs:__imp_RegSetValueExW
0x18009d37a  nop     dword ptr [rax+rax+00h]
0x18009d37f  mov     rcx, r14; hMem
0x18009d382  call    cs:__imp_LocalFree
0x18009d389  nop     dword ptr [rax+rax+00h]
0x18009d38e  test    edi, edi
0x18009d390  jz      short loc_18009D397
0x18009d392  call    SkipPastEndOfLine
0x18009d397  mov     rbx, [rsp+40h+arg_0]
0x18009d39f  add     rsp, 40h
0x18009d3a3  pop     r15
0x18009d3a5  pop     r14
0x18009d3a7  pop     r13
0x18009d3a9  pop     r12
0x18009d3ab  pop     rdi
0x18009d3ac  pop     rsi
0x18009d3ad  pop     rbp
0x18009d3ae  retn
```
