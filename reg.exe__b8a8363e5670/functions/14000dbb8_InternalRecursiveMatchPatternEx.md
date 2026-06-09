# InternalRecursiveMatchPatternEx

- ea: `0x14000dbb8`
- end: `0x14000ddbc`
- name: `InternalRecursiveMatchPatternEx`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000dbb8`
- `0x14000e050`

## callees

- `0x14000dbb8`
- `0x14000ee5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dd98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dd98`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000dc5e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000dcc9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000dc5e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000dcc9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dbf6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dc08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dbf6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dc08`

## pseudocode

```c
__int64 __fastcall InternalRecursiveMatchPatternEx(const WCHAR *a1, const WCHAR *a2, LCID a3, DWORD a4, int a5)
{
  DWORD v5; // r13d
  unsigned int matched; // esi
  unsigned int v9; // r14d
  unsigned int v10; // edi
  unsigned int v11; // ebx
  unsigned int v12; // ebp
  bool v13; // zf
  const WCHAR *v14; // rcx
  const WCHAR *lpString2; // r13

  v5 = a4;
  if ( a1 && a2 )
  {
    matched = 1;
    v9 = lstrlenW(a1);
    v10 = 0;
    v11 = 0;
    v12 = lstrlenW(a2);
    if ( v12 )
    {
      while ( 1 )
      {
        v13 = v11 == v9;
        if ( v11 >= v9 )
          goto LABEL_23;
        v14 = &a2[v10];
        if ( *v14 == 42 )
        {
          if ( v10 + 1 < v12 )
          {
            lpString2 = v14 + 1;
            while ( 1 )
            {
              if ( CompareStringW(a3, a4, &a1[v11], 1, lpString2, 1) == 2 )
              {
                matched = InternalRecursiveMatchPatternEx((unsigned int)a1 + 2 * v11, (_DWORD)lpString2, a3, a4, a5 + 1);
                if ( matched == 1 )
                  break;
              }
              if ( ++v11 >= v9 )
                goto LABEL_18;
            }
            v11 = v9;
            v10 = v12;
            goto LABEL_19;
          }
          v11 = v9;
          v10 = v12;
        }
        else if ( *v14 == 63 )
        {
          ++v11;
          ++v10;
        }
        else
        {
          if ( CompareStringW(a3, v5, &a1[v11], 1, &a2[v10], 1) != 2 )
            return 0;
          ++v11;
          ++v10;
        }
LABEL_18:
        if ( !matched )
          return matched;
LABEL_19:
        if ( v10 >= v12 )
          break;
        v5 = a4;
      }
    }
    v13 = v11 == v9;
LABEL_23:
    if ( v13 && v10 == v12 )
    {
      return 1;
    }
    else
    {
      matched = 0;
      if ( v11 == v9 && v10 + 1 == v12 )
        return (unsigned int)StringCompareExW(&a2[v10], L"*") == 0;
    }
    return matched;
  }
  else
  {
    if ( !GetLastError() )
      SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x14000dbb8  mov     [rsp+arg_8], rbx
0x14000dbbd  mov     [rsp+dwCmpFlags], r9d
0x14000dbc2  mov     [rsp+Locale], r8d
0x14000dbc7  push    rbp
0x14000dbc8  push    rsi
0x14000dbc9  push    rdi
0x14000dbca  push    r12
0x14000dbcc  push    r13
0x14000dbce  push    r14
0x14000dbd0  push    r15
0x14000dbd2  sub     rsp, 30h
0x14000dbd6  mov     r13d, r9d
0x14000dbd9  mov     r15, rdx
0x14000dbdc  mov     r12, rcx
0x14000dbdf  test    rcx, rcx
0x14000dbe2  jz      loc_14000DD85
0x14000dbe8  test    rdx, rdx
0x14000dbeb  jz      loc_14000DD85
0x14000dbf1  mov     esi, 1
0x14000dbf6  call    cs:__imp_lstrlenW
0x14000dbfd  nop     dword ptr [rax+rax+00h]
0x14000dc02  mov     rcx, r15; lpString
0x14000dc05  mov     r14d, eax
0x14000dc08  call    cs:__imp_lstrlenW
0x14000dc0f  nop     dword ptr [rax+rax+00h]
0x14000dc14  xor     edi, edi
0x14000dc16  xor     ebx, ebx
0x14000dc18  mov     ebp, eax
0x14000dc1a  test    eax, eax
0x14000dc1c  jz      loc_14000DD46
0x14000dc22  cmp     ebx, r14d
0x14000dc25  jnb     loc_14000DD49
0x14000dc2b  mov     eax, edi
0x14000dc2d  lea     rcx, [r15+rax*2]
0x14000dc31  cmp     word ptr [rcx], 2Ah ; '*'
0x14000dc35  jz      short loc_14000DC8D
0x14000dc37  cmp     word ptr [rcx], 3Fh ; '?'
0x14000dc3b  jz      short loc_14000DC7F
0x14000dc3d  mov     eax, ebx
0x14000dc3f  mov     edx, r13d; dwCmpFlags
0x14000dc42  lea     r8, [r12+rax*2]; lpString1
0x14000dc46  mov     eax, 1
0x14000dc4b  mov     [rsp+68h+cchCount2], eax; cchCount2
0x14000dc4f  mov     r9d, eax; cchCount1
0x14000dc52  mov     [rsp+68h+lpString2], rcx; lpString2
0x14000dc57  mov     ecx, [rsp+68h+Locale]; Locale
0x14000dc5e  call    cs:__imp_CompareStringW
0x14000dc65  nop     dword ptr [rax+rax+00h]
0x14000dc6a  cmp     eax, 2
0x14000dc6d  jnz     loc_14000DD42
0x14000dc73  lea     ecx, [rax-1]
0x14000dc76  add     ebx, ecx
0x14000dc78  add     edi, ecx
0x14000dc7a  jmp     loc_14000DD2D
0x14000dc7f  mov     eax, 1
0x14000dc84  add     ebx, eax
0x14000dc86  add     edi, eax
0x14000dc88  jmp     loc_14000DD2D
0x14000dc8d  lea     eax, [rdi+1]
0x14000dc90  cmp     eax, ebp
0x14000dc92  jnb     loc_14000DD28
0x14000dc98  lea     r13, [rcx+2]
0x14000dc9c  mov     ecx, 1
0x14000dca1  mov     edx, [rsp+68h+dwCmpFlags]; dwCmpFlags
0x14000dca8  mov     r9d, ecx; cchCount1
0x14000dcab  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x14000dcaf  mov     ecx, [rsp+68h+Locale]; Locale
0x14000dcb6  mov     eax, ebx
0x14000dcb8  mov     [rsp+68h+lpString2], r13; lpString2
0x14000dcbd  lea     rax, [r12+rax*2]
0x14000dcc1  mov     r8, rax; lpString1
0x14000dcc4  mov     [rsp+68h+arg_0], rax
0x14000dcc9  call    cs:__imp_CompareStringW
0x14000dcd0  nop     dword ptr [rax+rax+00h]
0x14000dcd5  cmp     eax, 2
0x14000dcd8  jnz     short loc_14000DD16
0x14000dcda  mov     eax, [rsp+68h+arg_20]
0x14000dce1  mov     rdx, r13
0x14000dce4  mov     r9d, [rsp+68h+dwCmpFlags]
0x14000dcec  inc     eax
0x14000dcee  mov     r8d, [rsp+68h+Locale]
0x14000dcf6  mov     rcx, [rsp+68h+arg_0]
0x14000dcfb  mov     dword ptr [rsp+68h+lpString2], eax
0x14000dcff  call    InternalRecursiveMatchPatternEx
0x14000dd04  mov     ecx, 1
0x14000dd09  mov     esi, eax
0x14000dd0b  cmp     eax, ecx
0x14000dd0d  jnz     short loc_14000DD1B
0x14000dd0f  mov     ebx, r14d
0x14000dd12  mov     edi, ebp
0x14000dd14  jmp     short loc_14000DD31
0x14000dd16  mov     ecx, 1
0x14000dd1b  add     ebx, ecx
0x14000dd1d  cmp     ebx, r14d
0x14000dd20  jb      loc_14000DCA1
0x14000dd26  jmp     short loc_14000DD2D
0x14000dd28  mov     ebx, r14d
0x14000dd2b  mov     edi, ebp
0x14000dd2d  test    esi, esi
0x14000dd2f  jz      short loc_14000DD81
0x14000dd31  cmp     edi, ebp
0x14000dd33  jnb     short loc_14000DD46
0x14000dd35  mov     r13d, [rsp+68h+dwCmpFlags]
0x14000dd3d  jmp     loc_14000DC22
0x14000dd42  xor     esi, esi
0x14000dd44  jmp     short loc_14000DD81
0x14000dd46  cmp     ebx, r14d
0x14000dd49  jnz     short loc_14000DD56
0x14000dd4b  cmp     edi, ebp
0x14000dd4d  jnz     short loc_14000DD56
0x14000dd4f  mov     esi, 1
0x14000dd54  jmp     short loc_14000DD81
0x14000dd56  xor     esi, esi
0x14000dd58  cmp     ebx, r14d
0x14000dd5b  jnz     short loc_14000DD81
0x14000dd5d  lea     eax, [rdi+1]
0x14000dd60  cmp     eax, ebp
0x14000dd62  jnz     short loc_14000DD81
0x14000dd64  mov     eax, edi
0x14000dd66  lea     ebx, [rsi+1]
0x14000dd69  mov     r9d, ebx
0x14000dd6c  lea     rdx, asc_140011EB8; "*"
0x14000dd73  lea     rcx, [r15+rax*2]; lpString1
0x14000dd77  call    StringCompareExW
0x14000dd7c  test    eax, eax
0x14000dd7e  cmovz   esi, ebx
0x14000dd81  mov     eax, esi
0x14000dd83  jmp     short loc_14000DDA6
0x14000dd85  call    cs:__imp_GetLastError
0x14000dd8c  nop     dword ptr [rax+rax+00h]
0x14000dd91  test    eax, eax
0x14000dd93  jnz     short loc_14000DDA4
0x14000dd95  lea     ecx, [rax+57h]; dwErrCode
0x14000dd98  call    cs:__imp_SetLastError
0x14000dd9f  nop     dword ptr [rax+rax+00h]
0x14000dda4  xor     eax, eax
0x14000dda6  mov     rbx, [rsp+68h+arg_8]
0x14000ddab  add     rsp, 30h
0x14000ddaf  pop     r15
0x14000ddb1  pop     r14
0x14000ddb3  pop     r13
0x14000ddb5  pop     r12
0x14000ddb7  pop     rdi
0x14000ddb8  pop     rsi
0x14000ddb9  pop     rbp
0x14000ddba  retn
```
