# ImportWin31RegFile

- ea: `0x14000b91c`
- end: `0x14000bbe8`
- name: `ImportWin31RegFile`
- size: `716`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000b54c`

## callees

- `0x140001340`
- `0x140001380`
- `0x14000b2c4`
- `0x14000b91c`
- `0x14000bbf0`
- `0x14000bc3c`
- `0x14000cd24`
- `0x14000cd84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b978`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b978`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14000bb8c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14000bb8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bb9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bb9d`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x14000bae6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x14000bae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000bb60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000bb60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ba81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ba81`

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
  BYTE *v8; // rdi
  BOOL v9; // ebx
  __int64 v10; // r8
  unsigned int v11; // r14d
  WCHAR v12; // si
  BYTE *v13; // rax
  __int64 v14; // rax
  WCHAR v15; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR v17[256]; // [rsp+40h] [rbp-C0h] BYREF

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
      LODWORD(qword_140055248) = qword_140055248 - 1;
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
      v8 = (BYTE *)LocalAlloc(0x40u, 0x100u);
      v9 = v8 != 0;
      if ( (unsigned int)GetChar(&v15) )
        break;
      if ( !v8 )
        goto LABEL_32;
LABEL_29:
      *(_WORD *)&v8[2 * v7] = 0;
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
        v13 = (BYTE *)LocalReAlloc(v8, v11, 2u);
        if ( !v13 )
        {
          v9 = 0;
          break;
        }
        v9 = 1;
        v8 = v13;
      }
      v14 = v7++;
      *(_WORD *)&v8[2 * v14] = v12;
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
0x14000b91c  mov     [rsp-8+arg_8], rbx
0x14000b921  mov     [rsp-8+arg_10], rsi
0x14000b926  push    rbp
0x14000b927  push    rdi
0x14000b928  push    r12
0x14000b92a  push    r14
0x14000b92c  push    r15
0x14000b92e  lea     rbp, [rsp-150h]
0x14000b936  sub     rsp, 250h
0x14000b93d  mov     rax, cs:__security_cookie
0x14000b944  xor     rax, rsp
0x14000b947  mov     [rbp+170h+var_30], rax
0x14000b94e  or      ecx, 2
0x14000b951  lea     rax, [rsp+270h+hKey]
0x14000b956  mov     r9d, ecx; samDesired
0x14000b959  mov     [rsp+270h+phkResult], rax; phkResult
0x14000b95e  xor     r12d, r12d
0x14000b961  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000b968  xor     r8d, r8d; ulOptions
0x14000b96b  mov     [rsp+270h+hKey], r12
0x14000b970  xor     edx, edx; lpSubKey
0x14000b972  mov     [rsp+270h+var_240], r12w
0x14000b978  call    cs:__imp_RegOpenKeyExW
0x14000b97f  nop     dword ptr [rax+rax+00h]
0x14000b984  test    eax, eax
0x14000b986  jz      short loc_14000B997
0x14000b988  mov     cs:g_FileErrorStringID, 2C0h
0x14000b992  jmp     loc_14000BBA9
0x14000b997  lea     rcx, [rsp+270h+var_240]
0x14000b99c  call    GetChar
0x14000b9a1  test    eax, eax
0x14000b9a3  jz      loc_14000BB87
0x14000b9a9  mov     esi, 5Ch ; '\'
0x14000b9ae  dec     dword ptr cs:qword_140055248
0x14000b9b4  movzx   ecx, si
0x14000b9b7  mov     edi, 20h ; ' '
0x14000b9bc  call    MatchChar
0x14000b9c1  test    eax, eax
0x14000b9c3  lea     rbx, s_OldWin31RegFileRoot; ".classes"
0x14000b9ca  cmovz   rbx, cs:g_RegistryRoots
0x14000b9d2  jmp     short loc_14000B9E8
0x14000b9d4  movzx   ecx, ax
0x14000b9d7  call    MatchChar
0x14000b9dc  test    eax, eax
0x14000b9de  jz      loc_14000BB70
0x14000b9e4  add     rbx, 2
0x14000b9e8  movzx   eax, word ptr [rbx]
0x14000b9eb  test    ax, ax
0x14000b9ee  jnz     short loc_14000B9D4
0x14000b9f0  mov     ecx, esi
0x14000b9f2  call    MatchChar
0x14000b9f7  test    eax, eax
0x14000b9f9  jz      loc_14000BB70
0x14000b9ff  mov     ebx, r12d
0x14000ba02  jmp     short loc_14000BA33
0x14000ba04  movzx   ecx, [rsp+270h+var_240]
0x14000ba09  cmp     cx, di
0x14000ba0c  ja      short loc_14000BA1E
0x14000ba0e  mov     rdx, 100002400h
0x14000ba18  bt      rdx, rcx
0x14000ba1c  jb      short loc_14000BA41
0x14000ba1e  cmp     ebx, 0FFh
0x14000ba24  jnb     loc_14000BB70
0x14000ba2a  mov     eax, ebx
0x14000ba2c  inc     ebx
0x14000ba2e  mov     [rsp+rax*2+270h+var_230], cx
0x14000ba33  lea     rcx, [rsp+270h+var_240]
0x14000ba38  call    GetChar
0x14000ba3d  test    eax, eax
0x14000ba3f  jnz     short loc_14000BA04
0x14000ba41  mov     eax, ebx
0x14000ba43  lea     rcx, [rax+rax]
0x14000ba47  cmp     rcx, 200h
0x14000ba4e  jnb     loc_14000BBE2
0x14000ba54  mov     [rsp+rcx+270h+var_230], r12w
0x14000ba5a  call    SkipWhitespace
0x14000ba5f  mov     ecx, 3Dh ; '='
0x14000ba64  call    MatchChar
0x14000ba69  test    eax, eax
0x14000ba6b  jz      short loc_14000BA74
0x14000ba6d  mov     ecx, edi
0x14000ba6f  call    MatchChar
0x14000ba74  mov     edx, 100h; uBytes
0x14000ba79  mov     ecx, 40h ; '@'; uFlags
0x14000ba7e  mov     r15d, r12d
0x14000ba81  call    cs:__imp_LocalAlloc
0x14000ba88  nop     dword ptr [rax+rax+00h]
0x14000ba8d  mov     ebx, r12d
0x14000ba90  lea     rcx, [rsp+270h+var_240]
0x14000ba95  test    rax, rax
0x14000ba98  mov     rdi, rax
0x14000ba9b  setnz   bl
0x14000ba9e  call    GetChar
0x14000baa3  test    eax, eax
0x14000baa5  jz      loc_14000BBD5
0x14000baab  mov     r14d, 100h
0x14000bab1  test    ebx, ebx
0x14000bab3  jz      loc_14000BB49
0x14000bab9  movzx   esi, [rsp+270h+var_240]
0x14000babe  cmp     si, 0Ah
0x14000bac2  jz      short loc_14000BB17
0x14000bac4  cmp     si, 0Dh
0x14000bac8  jz      short loc_14000BB17
0x14000baca  lea     eax, [r14-1]
0x14000bace  cmp     r15d, eax
0x14000bad1  jb      short loc_14000BAFF
0x14000bad3  add     r14d, 100h
0x14000bada  mov     r8d, 2; uFlags
0x14000bae0  mov     edx, r14d; uBytes
0x14000bae3  mov     rcx, rdi; hMem
0x14000bae6  call    cs:__imp_LocalReAlloc
0x14000baed  nop     dword ptr [rax+rax+00h]
0x14000baf2  test    rax, rax
0x14000baf5  jz      short loc_14000BB46
0x14000baf7  mov     ebx, 1
0x14000bafc  mov     rdi, rax
0x14000baff  mov     eax, r15d
0x14000bb02  lea     rcx, [rsp+270h+var_240]
0x14000bb07  inc     r15d
0x14000bb0a  mov     [rdi+rax*2], si
0x14000bb0e  call    GetChar
0x14000bb13  test    eax, eax
0x14000bb15  jnz     short loc_14000BAB1
0x14000bb17  mov     esi, 5Ch ; '\'
0x14000bb1c  mov     ecx, r15d
0x14000bb1f  lea     rdx, [rsp+270h+var_230]
0x14000bb24  mov     r9, rdi
0x14000bb27  mov     [rdi+rcx*2], r12w
0x14000bb2c  mov     rcx, [rsp+270h+hKey]
0x14000bb31  call    MyRegSetValueW
0x14000bb36  test    eax, eax
0x14000bb38  jz      short loc_14000BB58
0x14000bb3a  mov     cs:g_FileErrorStringID, 2C1h
0x14000bb44  jmp     short loc_14000BB58
0x14000bb46  mov     ebx, r12d
0x14000bb49  mov     esi, 5Ch ; '\'
0x14000bb4e  mov     cs:g_FileErrorStringID, 6Bh ; 'k'
0x14000bb58  test    rdi, rdi
0x14000bb5b  jz      short loc_14000BB6C
0x14000bb5d  mov     rcx, rdi; hMem
0x14000bb60  call    cs:__imp_LocalFree
0x14000bb67  nop     dword ptr [rax+rax+00h]
0x14000bb6c  test    ebx, ebx
0x14000bb6e  jnz     short loc_14000BB75
0x14000bb70  call    SkipPastEndOfLine
0x14000bb75  lea     rcx, [rsp+270h+var_240]
0x14000bb7a  call    GetChar
0x14000bb7f  test    eax, eax
0x14000bb81  jnz     loc_14000B9AE
0x14000bb87  mov     rcx, [rsp+270h+hKey]; hKey
0x14000bb8c  call    cs:__imp_RegFlushKey
0x14000bb93  nop     dword ptr [rax+rax+00h]
0x14000bb98  mov     rcx, [rsp+270h+hKey]; hKey
0x14000bb9d  call    cs:__imp_RegCloseKey
0x14000bba4  nop     dword ptr [rax+rax+00h]
0x14000bba9  mov     rcx, [rbp+170h+var_30]
0x14000bbb0  xor     rcx, rsp; StackCookie
0x14000bbb3  call    __security_check_cookie
0x14000bbb8  lea     r11, [rsp+270h+var_20]
0x14000bbc0  mov     rbx, [r11+38h]
0x14000bbc4  mov     rsi, [r11+40h]
0x14000bbc8  mov     rsp, r11
0x14000bbcb  pop     r15
0x14000bbcd  pop     r14
0x14000bbcf  pop     r12
0x14000bbd1  pop     rdi
0x14000bbd2  pop     rbp
0x14000bbd3  retn
0x14000bbd5  test    ebx, ebx
0x14000bbd7  jz      loc_14000BB4E
0x14000bbdd  jmp     loc_14000BB1C
0x14000bbe2  call    __report_rangecheckfailure
```
