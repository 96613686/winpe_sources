# PathCchSkipRoot

- ea: `0x140010820`
- end: `0x140010972`
- name: `PathCchSkipRoot`
- size: `338`
- prototype: `HRESULT __stdcall(PCWSTR pszPath, PCWSTR *ppszRootEnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140010768`

## callees

- `0x14000f9b4`
- `0x14000fa50`
- `0x140010820`
- `0x140010992`

## import_xrefs

- `msvcrt!wcschr` at `0x140010873`
- `msvcrt!wcschr` at `0x140010890`
- `msvcrt!wcschr` at `0x140010873`
- `msvcrt!wcschr` at `0x140010890`
- `msvcrt!iswalpha` at `0x140010931`
- `msvcrt!iswalpha` at `0x140010931`

## pseudocode

```c
HRESULT __stdcall PathCchSkipRoot(PCWSTR pszPath, PCWSTR *ppszRootEnd)
{
  PCWSTR v3; // rbx
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rsi
  wchar_t *v7; // rax
  const WCHAR *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  wint_t v11; // si
  __int64 v12; // rax

  v3 = pszPath;
  if ( pszPath && *pszPath && ppszRootEnd )
  {
    *ppszRootEnd = 0;
    if ( (unsigned int)PathIsUnc2((unsigned __int16 *)pszPath) )
    {
      v4 = wcschr(0, 0x5Cu);
      v5 = v4;
      if ( v4 )
      {
        v6 = v4 + 1;
        v7 = wcschr(v4 + 1, 0x5Cu);
        if ( v7 )
        {
          v8 = v7 + 1;
          if ( v7 == v6 )
            v8 = v7;
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( v5[v9] );
          v8 = &v5[v9];
        }
      }
      else
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(2 * v10) );
        v8 = (const WCHAR *)(2 * v10);
      }
      goto LABEL_30;
    }
    v11 = *v3;
    if ( *v3 == 92 && v3[1] != 92 )
    {
      v8 = v3 + 1;
LABEL_30:
      *ppszRootEnd = v8;
      return 0;
    }
    if ( PathIsVolumeGUIDWorker(v3) )
    {
      v12 = 49;
      if ( v3[48] != 92 )
        v12 = 48;
LABEL_29:
      v8 = &v3[v12];
      goto LABEL_30;
    }
    if ( !wcsncmp_0(v3, L"\\\\?\\", 4u) )
    {
      v3 += 4;
      v11 = *v3;
    }
    if ( iswalpha(v11) && v3[1] == 58 )
    {
      v12 = 3;
      if ( v3[2] != 92 )
        v12 = 2;
      goto LABEL_29;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x140010820  push    rbx
0x140010822  push    rbp
0x140010823  push    rsi
0x140010824  push    rdi
0x140010825  push    r14
0x140010827  push    r15
0x140010829  sub     rsp, 28h
0x14001082d  xor     ebp, ebp
0x14001082f  mov     r14, rdx
0x140010832  mov     [rsp+58h+Str], rbp
0x140010837  mov     rbx, rcx
0x14001083a  test    rcx, rcx
0x14001083d  jz      loc_14001095F
0x140010843  cmp     [rcx], bp
0x140010846  jz      loc_14001095F
0x14001084c  test    rdx, rdx
0x14001084f  jz      loc_14001095F
0x140010855  mov     [rdx], rbp
0x140010858  lea     rdx, [rsp+58h+Str]
0x14001085d  call    PathIsUnc2
0x140010862  lea     edi, [rbp+5Ch]
0x140010865  test    eax, eax
0x140010867  jz      short loc_1400108DA
0x140010869  mov     rsi, [rsp+58h+Str]
0x14001086e  mov     edx, edi; Ch
0x140010870  mov     rcx, rsi; Str
0x140010873  call    cs:__imp_wcschr
0x14001087a  nop     dword ptr [rax+rax+00h]
0x14001087f  mov     rbx, rax
0x140010882  test    rax, rax
0x140010885  jz      short loc_1400108C7
0x140010887  lea     rsi, [rax+2]
0x14001088b  mov     edx, edi; Ch
0x14001088d  mov     rcx, rsi; Str
0x140010890  call    cs:__imp_wcschr
0x140010897  nop     dword ptr [rax+rax+00h]
0x14001089c  test    rax, rax
0x14001089f  jz      short loc_1400108B1
0x1400108a1  cmp     rax, rsi
0x1400108a4  lea     rbx, [rax+2]
0x1400108a8  cmovz   rbx, rax
0x1400108ac  jmp     loc_140010958
0x1400108b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400108b5  inc     rax
0x1400108b8  cmp     [rbx+rax*2], bp
0x1400108bc  jnz     short loc_1400108B5
0x1400108be  lea     rbx, [rbx+rax*2]
0x1400108c2  jmp     loc_140010958
0x1400108c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400108cb  inc     rax
0x1400108ce  cmp     [rsi+rax*2], bp
0x1400108d2  jnz     short loc_1400108CB
0x1400108d4  lea     rbx, [rsi+rax*2]
0x1400108d8  jmp     short loc_140010958
0x1400108da  movzx   esi, word ptr [rbx]
0x1400108dd  cmp     si, di
0x1400108e0  jnz     short loc_1400108EE
0x1400108e2  cmp     [rbx+2], di
0x1400108e6  jz      short loc_1400108EE
0x1400108e8  add     rbx, 2
0x1400108ec  jmp     short loc_140010958
0x1400108ee  mov     rcx, rbx; unsigned __int16 *
0x1400108f1  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x1400108f6  test    al, al
0x1400108f8  jz      short loc_14001090B
0x1400108fa  cmp     [rbx+60h], di
0x1400108fe  mov     eax, 62h ; 'b'
0x140010903  lea     ecx, [rax-2]
0x140010906  cmovnz  eax, ecx
0x140010909  jmp     short loc_140010955
0x14001090b  mov     r15d, 4
0x140010911  lea     rdx, asc_140013A28; "\\\\?\\"
0x140010918  mov     r8d, r15d; MaxCount
0x14001091b  mov     rcx, rbx; String1
0x14001091e  call    wcsncmp_0
0x140010923  test    eax, eax
0x140010925  jnz     short loc_14001092E
0x140010927  add     rbx, 8
0x14001092b  movzx   esi, word ptr [rbx]
0x14001092e  movzx   ecx, si; C
0x140010931  call    cs:__imp_iswalpha
0x140010938  nop     dword ptr [rax+rax+00h]
0x14001093d  test    eax, eax
0x14001093f  jz      short loc_14001095F
0x140010941  cmp     word ptr [rbx+2], 3Ah ; ':'
0x140010946  jnz     short loc_14001095F
0x140010948  cmp     [rbx+4], di
0x14001094c  mov     eax, 6
0x140010951  cmovnz  rax, r15
0x140010955  add     rbx, rax
0x140010958  mov     [r14], rbx
0x14001095b  xor     eax, eax
0x14001095d  jmp     short loc_140010964
0x14001095f  mov     eax, 80070057h
0x140010964  add     rsp, 28h
0x140010968  pop     r15
0x14001096a  pop     r14
0x14001096c  pop     rdi
0x14001096d  pop     rsi
0x14001096e  pop     rbp
0x14001096f  pop     rbx
0x140010970  retn
```
