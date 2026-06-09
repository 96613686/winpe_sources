# ImportWin31RegFile

- ea: `0x14000b1d4`
- end: `0x14000b477`
- name: `ImportWin31RegFile`
- size: `675`
- prototype: `LSTATUS __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000ae58`

## callees

- `0x140001340`
- `0x140001380`
- `0x14000ac00`
- `0x14000b1d4`
- `0x14000b480`
- `0x14000b4cc`
- `0x14000c500`
- `0x14000c560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b230`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b230`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14000b42c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14000b42c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b437`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x14000b392`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x14000b392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b406`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b333`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b333`

## pseudocode

```c
LSTATUS __fastcall ImportWin31RegFile(int a1)
{
  LSTATUS result; // eax
  const wchar_t *v2; // rbx
  __int64 v3; // rcx
  unsigned int i; // ebx
  __int64 v5; // rdx
  __int64 v6; // rax
  unsigned int v7; // r15d
  _WORD *v8; // rdi
  BOOL v9; // ebx
  __int64 v10; // r8
  unsigned int v11; // r14d
  unsigned __int16 v12; // si
  _WORD *v13; // rax
  __int64 v14; // rax
  unsigned __int16 v15; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v17[256]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  v15 = 0;
  result = RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, a1 | 2, &hKey);
  if ( result )
  {
    g_FileErrorStringID = 704;
    return result;
  }
  if ( (unsigned int)GetChar(&v15) )
  {
    while ( 1 )
    {
      LODWORD(qword_140054248) = qword_140054248 - 1;
      v2 = L".classes";
      if ( !(unsigned int)MatchChar(92) )
        v2 = g_RegistryRoots;
      while ( *v2 )
      {
        if ( !(unsigned int)MatchChar(*v2) )
          goto LABEL_36;
        ++v2;
      }
      if ( !(unsigned int)MatchChar(92) )
      {
LABEL_36:
        SkipPastEndOfLine(v3);
        goto LABEL_37;
      }
      for ( i = 0; (unsigned int)GetChar(&v15); ++i )
      {
        v3 = v15;
        if ( v15 <= 0x20u )
        {
          v5 = 0x100002400LL;
          if ( _bittest64(&v5, v15) )
            break;
        }
        if ( i >= 0xFF )
          goto LABEL_36;
        v6 = i;
        v17[v6] = v15;
      }
      if ( 2 * (unsigned __int64)i >= 0x200 )
        _report_rangecheckfailure();
      v17[i] = 0;
      SkipWhitespace();
      if ( (unsigned int)MatchChar(61) )
        MatchChar(32);
      v7 = 0;
      v8 = LocalAlloc(0x40u, 0x100u);
      v9 = v8 != 0;
      if ( (unsigned int)GetChar(&v15) )
        break;
      if ( !v8 )
        goto LABEL_32;
LABEL_29:
      v8[v7] = 0;
      if ( (unsigned int)MyRegSetValueW(hKey, v17, v10, v8) )
        g_FileErrorStringID = 705;
LABEL_33:
      if ( v8 )
        LocalFree(v8);
      if ( !v9 )
        goto LABEL_36;
LABEL_37:
      if ( !(unsigned int)GetChar(&v15) )
        goto LABEL_38;
    }
    v11 = 256;
    while ( v9 )
    {
      v12 = v15;
      if ( v15 == 10 || v15 == 13 )
        goto LABEL_29;
      if ( v7 >= v11 - 1 )
      {
        v11 += 256;
        v13 = LocalReAlloc(v8, v11, 2u);
        if ( !v13 )
        {
          v9 = 0;
          break;
        }
        v9 = 1;
        v8 = v13;
      }
      v14 = v7++;
      v8[v14] = v12;
      if ( !(unsigned int)GetChar(&v15) )
        goto LABEL_29;
    }
LABEL_32:
    g_FileErrorStringID = 107;
    goto LABEL_33;
  }
LABEL_38:
  RegFlushKey(hKey);
  return RegCloseKey(hKey);
}

```

## disassembly

```asm
0x14000b1d4  mov     [rsp-8+arg_8], rbx
0x14000b1d9  mov     [rsp-8+arg_10], rsi
0x14000b1de  push    rbp
0x14000b1df  push    rdi
0x14000b1e0  push    r12
0x14000b1e2  push    r14
0x14000b1e4  push    r15
0x14000b1e6  lea     rbp, [rsp-150h]
0x14000b1ee  sub     rsp, 250h
0x14000b1f5  mov     rax, cs:__security_cookie
0x14000b1fc  xor     rax, rsp
0x14000b1ff  mov     [rbp+170h+var_30], rax
0x14000b206  or      ecx, 2
0x14000b209  lea     rax, [rsp+270h+hKey]
0x14000b20e  mov     r9d, ecx; samDesired
0x14000b211  mov     [rsp+270h+phkResult], rax; phkResult
0x14000b216  xor     r12d, r12d
0x14000b219  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000b220  xor     r8d, r8d; ulOptions
0x14000b223  mov     [rsp+270h+hKey], r12
0x14000b228  xor     edx, edx; lpSubKey
0x14000b22a  mov     [rsp+270h+var_240], r12w
0x14000b230  call    cs:__imp_RegOpenKeyExW
0x14000b236  test    eax, eax
0x14000b238  jz      short loc_14000B249
0x14000b23a  mov     cs:g_FileErrorStringID, 2C0h
0x14000b244  jmp     loc_14000B43D
0x14000b249  lea     rcx, [rsp+270h+var_240]
0x14000b24e  call    GetChar
0x14000b253  test    eax, eax
0x14000b255  jz      loc_14000B427
0x14000b25b  mov     esi, 5Ch ; '\'
0x14000b260  dec     dword ptr cs:qword_140054248
0x14000b266  movzx   ecx, si
0x14000b269  mov     edi, 20h ; ' '
0x14000b26e  call    MatchChar
0x14000b273  test    eax, eax
0x14000b275  lea     rbx, s_OldWin31RegFileRoot; ".classes"
0x14000b27c  cmovz   rbx, cs:g_RegistryRoots
0x14000b284  jmp     short loc_14000B29A
0x14000b286  movzx   ecx, ax
0x14000b289  call    MatchChar
0x14000b28e  test    eax, eax
0x14000b290  jz      loc_14000B410
0x14000b296  add     rbx, 2
0x14000b29a  movzx   eax, word ptr [rbx]
0x14000b29d  test    ax, ax
0x14000b2a0  jnz     short loc_14000B286
0x14000b2a2  mov     ecx, esi
0x14000b2a4  call    MatchChar
0x14000b2a9  test    eax, eax
0x14000b2ab  jz      loc_14000B410
0x14000b2b1  mov     ebx, r12d
0x14000b2b4  jmp     short loc_14000B2E5
0x14000b2b6  movzx   ecx, [rsp+270h+var_240]
0x14000b2bb  cmp     cx, di
0x14000b2be  ja      short loc_14000B2D0
0x14000b2c0  mov     rdx, 100002400h
0x14000b2ca  bt      rdx, rcx
0x14000b2ce  jb      short loc_14000B2F3
0x14000b2d0  cmp     ebx, 0FFh
0x14000b2d6  jnb     loc_14000B410
0x14000b2dc  mov     eax, ebx
0x14000b2de  inc     ebx
0x14000b2e0  mov     [rsp+rax*2+270h+var_230], cx
0x14000b2e5  lea     rcx, [rsp+270h+var_240]
0x14000b2ea  call    GetChar
0x14000b2ef  test    eax, eax
0x14000b2f1  jnz     short loc_14000B2B6
0x14000b2f3  mov     eax, ebx
0x14000b2f5  lea     rcx, [rax+rax]
0x14000b2f9  cmp     rcx, 200h
0x14000b300  jnb     loc_14000B471
0x14000b306  mov     [rsp+rcx+270h+var_230], r12w
0x14000b30c  call    SkipWhitespace
0x14000b311  mov     ecx, 3Dh ; '='
0x14000b316  call    MatchChar
0x14000b31b  test    eax, eax
0x14000b31d  jz      short loc_14000B326
0x14000b31f  mov     ecx, edi
0x14000b321  call    MatchChar
0x14000b326  mov     edx, 100h; uBytes
0x14000b32b  mov     ecx, 40h ; '@'; uFlags
0x14000b330  mov     r15d, r12d
0x14000b333  call    cs:__imp_LocalAlloc
0x14000b339  mov     ebx, r12d
0x14000b33c  lea     rcx, [rsp+270h+var_240]
0x14000b341  test    rax, rax
0x14000b344  mov     rdi, rax
0x14000b347  setnz   bl
0x14000b34a  call    GetChar
0x14000b34f  test    eax, eax
0x14000b351  jz      loc_14000B468
0x14000b357  mov     r14d, 100h
0x14000b35d  test    ebx, ebx
0x14000b35f  jz      loc_14000B3EF
0x14000b365  movzx   esi, [rsp+270h+var_240]
0x14000b36a  cmp     si, 0Ah
0x14000b36e  jz      short loc_14000B3BD
0x14000b370  cmp     si, 0Dh
0x14000b374  jz      short loc_14000B3BD
0x14000b376  lea     eax, [r14-1]
0x14000b37a  cmp     r15d, eax
0x14000b37d  jb      short loc_14000B3A5
0x14000b37f  add     r14d, 100h
0x14000b386  mov     r8d, 2; uFlags
0x14000b38c  mov     edx, r14d; uBytes
0x14000b38f  mov     rcx, rdi; hMem
0x14000b392  call    cs:__imp_LocalReAlloc
0x14000b398  test    rax, rax
0x14000b39b  jz      short loc_14000B3EC
0x14000b39d  mov     ebx, 1
0x14000b3a2  mov     rdi, rax
0x14000b3a5  mov     eax, r15d
0x14000b3a8  lea     rcx, [rsp+270h+var_240]
0x14000b3ad  inc     r15d
0x14000b3b0  mov     [rdi+rax*2], si
0x14000b3b4  call    GetChar
0x14000b3b9  test    eax, eax
0x14000b3bb  jnz     short loc_14000B35D
0x14000b3bd  mov     esi, 5Ch ; '\'
0x14000b3c2  mov     ecx, r15d
0x14000b3c5  lea     rdx, [rsp+270h+var_230]
0x14000b3ca  mov     r9, rdi
0x14000b3cd  mov     [rdi+rcx*2], r12w
0x14000b3d2  mov     rcx, [rsp+270h+hKey]
0x14000b3d7  call    MyRegSetValueW
0x14000b3dc  test    eax, eax
0x14000b3de  jz      short loc_14000B3FE
0x14000b3e0  mov     cs:g_FileErrorStringID, 2C1h
0x14000b3ea  jmp     short loc_14000B3FE
0x14000b3ec  mov     ebx, r12d
0x14000b3ef  mov     esi, 5Ch ; '\'
0x14000b3f4  mov     cs:g_FileErrorStringID, 6Bh ; 'k'
0x14000b3fe  test    rdi, rdi
0x14000b401  jz      short loc_14000B40C
0x14000b403  mov     rcx, rdi; hMem
0x14000b406  call    cs:__imp_LocalFree
0x14000b40c  test    ebx, ebx
0x14000b40e  jnz     short loc_14000B415
0x14000b410  call    SkipPastEndOfLine
0x14000b415  lea     rcx, [rsp+270h+var_240]
0x14000b41a  call    GetChar
0x14000b41f  test    eax, eax
0x14000b421  jnz     loc_14000B260
0x14000b427  mov     rcx, [rsp+270h+hKey]; hKey
0x14000b42c  call    cs:__imp_RegFlushKey
0x14000b432  mov     rcx, [rsp+270h+hKey]; hKey
0x14000b437  call    cs:__imp_RegCloseKey
0x14000b43d  mov     rcx, [rbp+170h+var_30]
0x14000b444  xor     rcx, rsp; StackCookie
0x14000b447  call    __security_check_cookie
0x14000b44c  lea     r11, [rsp+270h+var_20]
0x14000b454  mov     rbx, [r11+38h]
0x14000b458  mov     rsi, [r11+40h]
0x14000b45c  mov     rsp, r11
0x14000b45f  pop     r15
0x14000b461  pop     r14
0x14000b463  pop     r12
0x14000b465  pop     rdi
0x14000b466  pop     rbp
0x14000b467  retn
0x14000b468  test    ebx, ebx
0x14000b46a  jz      short loc_14000B3F4
0x14000b46c  jmp     loc_14000B3C2
0x14000b471  call    __report_rangecheckfailure
```
