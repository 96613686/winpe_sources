# InternalRecursiveMatchPatternEx

- ea: `0x14000d204`
- end: `0x14000d3df`
- name: `InternalRecursiveMatchPatternEx`
- size: `475`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d204`
- `0x14000d5c4`

## callees

- `0x14000d204`
- `0x14000e228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d3b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d3b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d3c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d3c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000d29e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000d303`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000d29e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000d303`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d242`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d24e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d242`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d24e`

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
0x14000d204  mov     [rsp+arg_8], rbx
0x14000d209  mov     [rsp+dwCmpFlags], r9d
0x14000d20e  mov     [rsp+Locale], r8d
0x14000d213  push    rbp
0x14000d214  push    rsi
0x14000d215  push    rdi
0x14000d216  push    r12
0x14000d218  push    r13
0x14000d21a  push    r14
0x14000d21c  push    r15
0x14000d21e  sub     rsp, 30h
0x14000d222  mov     r13d, r9d
0x14000d225  mov     r15, rdx
0x14000d228  mov     r12, rcx
0x14000d22b  test    rcx, rcx
0x14000d22e  jz      loc_14000D3B5
0x14000d234  test    rdx, rdx
0x14000d237  jz      loc_14000D3B5
0x14000d23d  mov     esi, 1
0x14000d242  call    cs:__imp_lstrlenW
0x14000d248  mov     rcx, r15; lpString
0x14000d24b  mov     r14d, eax
0x14000d24e  call    cs:__imp_lstrlenW
0x14000d254  xor     edi, edi
0x14000d256  xor     ebx, ebx
0x14000d258  mov     ebp, eax
0x14000d25a  test    eax, eax
0x14000d25c  jz      loc_14000D376
0x14000d262  cmp     ebx, r14d
0x14000d265  jnb     loc_14000D379
0x14000d26b  mov     eax, edi
0x14000d26d  lea     rcx, [r15+rax*2]
0x14000d271  cmp     word ptr [rcx], 2Ah ; '*'
0x14000d275  jz      short loc_14000D2C7
0x14000d277  cmp     word ptr [rcx], 3Fh ; '?'
0x14000d27b  jz      short loc_14000D2B9
0x14000d27d  mov     eax, ebx
0x14000d27f  mov     edx, r13d; dwCmpFlags
0x14000d282  lea     r8, [r12+rax*2]; lpString1
0x14000d286  mov     eax, 1
0x14000d28b  mov     [rsp+68h+cchCount2], eax; cchCount2
0x14000d28f  mov     r9d, eax; cchCount1
0x14000d292  mov     [rsp+68h+lpString2], rcx; lpString2
0x14000d297  mov     ecx, [rsp+68h+Locale]; Locale
0x14000d29e  call    cs:__imp_CompareStringW
0x14000d2a4  cmp     eax, 2
0x14000d2a7  jnz     loc_14000D372
0x14000d2ad  lea     ecx, [rax-1]
0x14000d2b0  add     ebx, ecx
0x14000d2b2  add     edi, ecx
0x14000d2b4  jmp     loc_14000D35D
0x14000d2b9  mov     eax, 1
0x14000d2be  add     ebx, eax
0x14000d2c0  add     edi, eax
0x14000d2c2  jmp     loc_14000D35D
0x14000d2c7  lea     eax, [rdi+1]
0x14000d2ca  cmp     eax, ebp
0x14000d2cc  jnb     loc_14000D358
0x14000d2d2  lea     r13, [rcx+2]
0x14000d2d6  mov     ecx, 1
0x14000d2db  mov     edx, [rsp+68h+dwCmpFlags]; dwCmpFlags
0x14000d2e2  mov     r9d, ecx; cchCount1
0x14000d2e5  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x14000d2e9  mov     ecx, [rsp+68h+Locale]; Locale
0x14000d2f0  mov     eax, ebx
0x14000d2f2  mov     [rsp+68h+lpString2], r13; lpString2
0x14000d2f7  lea     rax, [r12+rax*2]
0x14000d2fb  mov     r8, rax; lpString1
0x14000d2fe  mov     [rsp+68h+arg_0], rax
0x14000d303  call    cs:__imp_CompareStringW
0x14000d309  cmp     eax, 2
0x14000d30c  jnz     short loc_14000D34A
0x14000d30e  mov     eax, [rsp+68h+arg_20]
0x14000d315  mov     rdx, r13
0x14000d318  mov     r9d, [rsp+68h+dwCmpFlags]
0x14000d320  inc     eax
0x14000d322  mov     r8d, [rsp+68h+Locale]
0x14000d32a  mov     rcx, [rsp+68h+arg_0]
0x14000d32f  mov     dword ptr [rsp+68h+lpString2], eax
0x14000d333  call    InternalRecursiveMatchPatternEx
0x14000d338  mov     ecx, 1
0x14000d33d  mov     esi, eax
0x14000d33f  cmp     eax, ecx
0x14000d341  jnz     short loc_14000D34F
0x14000d343  mov     ebx, r14d
0x14000d346  mov     edi, ebp
0x14000d348  jmp     short loc_14000D361
0x14000d34a  mov     ecx, 1
0x14000d34f  add     ebx, ecx
0x14000d351  cmp     ebx, r14d
0x14000d354  jb      short loc_14000D2DB
0x14000d356  jmp     short loc_14000D35D
0x14000d358  mov     ebx, r14d
0x14000d35b  mov     edi, ebp
0x14000d35d  test    esi, esi
0x14000d35f  jz      short loc_14000D3B1
0x14000d361  cmp     edi, ebp
0x14000d363  jnb     short loc_14000D376
0x14000d365  mov     r13d, [rsp+68h+dwCmpFlags]
0x14000d36d  jmp     loc_14000D262
0x14000d372  xor     esi, esi
0x14000d374  jmp     short loc_14000D3B1
0x14000d376  cmp     ebx, r14d
0x14000d379  jnz     short loc_14000D386
0x14000d37b  cmp     edi, ebp
0x14000d37d  jnz     short loc_14000D386
0x14000d37f  mov     esi, 1
0x14000d384  jmp     short loc_14000D3B1
0x14000d386  xor     esi, esi
0x14000d388  cmp     ebx, r14d
0x14000d38b  jnz     short loc_14000D3B1
0x14000d38d  lea     eax, [rdi+1]
0x14000d390  cmp     eax, ebp
0x14000d392  jnz     short loc_14000D3B1
0x14000d394  mov     eax, edi
0x14000d396  lea     ebx, [rsi+1]
0x14000d399  mov     r9d, ebx
0x14000d39c  lea     rdx, asc_140010EB8; "*"
0x14000d3a3  lea     rcx, [r15+rax*2]; lpString1
0x14000d3a7  call    StringCompareExW
0x14000d3ac  test    eax, eax
0x14000d3ae  cmovz   esi, ebx
0x14000d3b1  mov     eax, esi
0x14000d3b3  jmp     short loc_14000D3CA
0x14000d3b5  call    cs:__imp_GetLastError
0x14000d3bb  test    eax, eax
0x14000d3bd  jnz     short loc_14000D3C8
0x14000d3bf  lea     ecx, [rax+57h]; dwErrCode
0x14000d3c2  call    cs:__imp_SetLastError
0x14000d3c8  xor     eax, eax
0x14000d3ca  mov     rbx, [rsp+68h+arg_8]
0x14000d3cf  add     rsp, 30h
0x14000d3d3  pop     r15
0x14000d3d5  pop     r14
0x14000d3d7  pop     r13
0x14000d3d9  pop     r12
0x14000d3db  pop     rdi
0x14000d3dc  pop     rsi
0x14000d3dd  pop     rbp
0x14000d3de  retn
```
