# OLE1StmToString

- ea: `0x1800a20d0`
- end: `0x1800a2204`
- name: `OLE1StmToString`
- size: `308`
- prototype: `__int64 __fastcall(_OLESTREAM *pos, wchar_t **ppsz)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1a88`
- `0x1800a2464`

## callees

- `0x18000b2d4`
- `0x18002f2c4`
- `0x1800a20d0`
- `0x1800a220c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a21e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a21e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2134`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2134`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a21b8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a21b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a2194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a2194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a21ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a21ca`

## pseudocode

```c
__int64 __fastcall OLE1StmToString(_OLESTREAM *pos, wchar_t **ppsz)
{
  int v4; // ebx
  unsigned __int64 cchWideChar; // rdi
  char *v6; // rax
  char *v7; // r15
  SIZE_T v8; // r14
  WCHAR *lpWideCharStr; // rax
  wchar_t *v10; // rbp
  unsigned int cbSize; // [rsp+78h] [rbp+10h] BYREF

  cbSize = 0;
  if ( ppsz )
    *ppsz = 0;
  v4 = OLE1StreamToUL(pos, &cbSize);
  if ( v4 >= 0 )
  {
    cchWideChar = cbSize;
    if ( cbSize )
    {
      if ( cchWideChar >= GetSafeAllocSize() )
        return (unsigned int)-2147024882;
      v6 = (char *)HeapAlloc(g_hHeap, 0, (unsigned int)cchWideChar);
      if ( (v7 = v6) == 0 )
        return (unsigned int)-2147024882;
      if ( ((__int64 (__fastcall *)(_OLESTREAM *, char *, _QWORD))pos->lpstbl->Get)(pos, v6, (unsigned int)cchWideChar) >= (unsigned int)cchWideChar )
      {
        if ( !ppsz )
          goto $errRtn_167;
        if ( StringCbLengthA(v7, (unsigned int)cchWideChar, 0) >= 0 && (unsigned int)cchWideChar <= 2 * (int)cchWideChar )
        {
          v8 = 2LL * (unsigned int)cchWideChar;
          if ( v8 < GetSafeAllocSize() && (lpWideCharStr = (WCHAR *)CoTaskMemAlloc(v8), (v10 = lpWideCharStr) != 0) )
          {
            if ( MultiByteToWideChar(0, 1u, v7, cchWideChar, lpWideCharStr, cchWideChar) )
            {
              *ppsz = v10;
            }
            else
            {
              v4 = -2147023783;
              CoTaskMemFree(v10);
            }
          }
          else
          {
            v4 = -2147024882;
          }
          goto $errRtn_167;
        }
      }
      v4 = -2147221056;
$errRtn_167:
      HeapFree(g_hHeap, 0, v7);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a20d0  push    rbx
0x1800a20d2  push    rbp
0x1800a20d3  push    rsi
0x1800a20d4  push    rdi
0x1800a20d5  push    r14
0x1800a20d7  push    r15
0x1800a20d9  sub     rsp, 38h
0x1800a20dd  mov     [rsp+68h+cbSize], 0
0x1800a20e5  mov     rsi, ppsz
0x1800a20e8  mov     rbp, pos
0x1800a20eb  test    ppsz, ppsz
0x1800a20ee  jz      short loc_1800A20F7
0x1800a20f0  mov     qword ptr [ppsz], 0
0x1800a20f7  lea     ppsz, [rsp+68h+cbSize]; pul
0x1800a20fc  call    OLE1StreamToUL
0x1800a2101  mov     ebx, eax
0x1800a2103  test    eax, eax
0x1800a2105  js      loc_1800A21F5
0x1800a210b  mov     edi, [rsp+68h+cbSize]
0x1800a210f  test    edi, edi
0x1800a2111  jz      loc_1800A21F5
0x1800a2117  mov     r14d, edi
0x1800a211a  call    GetSafeAllocSize
0x1800a211f  cmp     rdi, rax
0x1800a2122  jnb     loc_1800A21F0
0x1800a2128  mov     pos, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a212f  mov     r8d, edi; dwBytes
0x1800a2132  xor     edx, edx; dwFlags
0x1800a2134  call    cs:__imp_HeapAlloc
0x1800a213a  mov     r15, rax
0x1800a213d  test    rax, rax
0x1800a2140  jz      loc_1800A21F0
0x1800a2146  mov     pos, [rbp+0]
0x1800a214a  mov     r8d, edi
0x1800a214d  mov     ppsz, r15
0x1800a2150  mov     rax, [pos]
0x1800a2153  mov     pos, rbp
0x1800a2156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a215b  cmp     eax, edi
0x1800a215d  jnb     short loc_1800A2166
0x1800a215f  mov     ebx, 800401C0h
0x1800a2164  jmp     short $errRtn_167
0x1800a2166  test    rsi, rsi
0x1800a2169  jz      short $errRtn_167
0x1800a216b  xor     r8d, r8d; pcbLength
0x1800a216e  mov     ppsz, r14; cbMax
0x1800a2171  mov     pos, r15; psz
0x1800a2174  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800a2179  test    eax, eax
0x1800a217b  js      short loc_1800A215F
0x1800a217d  lea     eax, [rdi+rdi]
0x1800a2180  cmp     edi, eax
0x1800a2182  ja      short loc_1800A215F
0x1800a2184  add     r14, r14
0x1800a2187  call    GetSafeAllocSize
0x1800a218c  cmp     r14, rax
0x1800a218f  jnb     short loc_1800A21D7
0x1800a2191  mov     pos, r14; cb
0x1800a2194  call    cs:__imp_CoTaskMemAlloc
0x1800a219a  mov     rbp, rax
0x1800a219d  test    rax, rax
0x1800a21a0  jz      short loc_1800A21D7
0x1800a21a2  mov     [rsp+68h+cchWideChar], edi; cchWideChar
0x1800a21a6  mov     r9d, edi; cbMultiByte
0x1800a21a9  mov     r8, r15; lpMultiByteStr
0x1800a21ac  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1800a21b1  mov     edx, 1; dwFlags
0x1800a21b6  xor     ecx, ecx; CodePage
0x1800a21b8  call    cs:__imp_MultiByteToWideChar
0x1800a21be  test    eax, eax
0x1800a21c0  jnz     short loc_1800A21D2
0x1800a21c2  mov     pos, rbp; pv
0x1800a21c5  mov     ebx, 80070459h
0x1800a21ca  call    cs:__imp_CoTaskMemFree
0x1800a21d0  jmp     short $errRtn_167
0x1800a21d2  mov     [rsi], rbp
0x1800a21d5  jmp     short $errRtn_167
0x1800a21d7  mov     ebx, 8007000Eh
0x1800a21dc  mov     pos, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a21e3  mov     r8, r15; lpMem
0x1800a21e6  xor     edx, edx; dwFlags
0x1800a21e8  call    cs:__imp_HeapFree
0x1800a21ee  jmp     short loc_1800A21F5
0x1800a21f0  mov     ebx, 8007000Eh
0x1800a21f5  mov     eax, ebx
0x1800a21f7  add     rsp, 38h
0x1800a21fb  pop     r15
0x1800a21fd  pop     r14
0x1800a21ff  pop     rdi
0x1800a2200  pop     rsi
0x1800a2201  pop     rbp
0x1800a2202  pop     rbx
0x1800a2203  retn
```
