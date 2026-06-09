# OLE1StmToString

- ea: `0x1800a8384`
- end: `0x1800a84ee`
- name: `OLE1StmToString`
- size: `362`
- prototype: `__int64 __fastcall(_OLESTREAM *pos, wchar_t **ppsz)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a7c08`
- `0x1800a8770`

## callees

- `0x18000a574`
- `0x1800327c0`
- `0x1800a8384`
- `0x1800a84f4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a84bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a84bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a83ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a83ec`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a8483`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a8483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a8459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a8459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a849b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a849b`

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
  unsigned int cbSize; // [rsp+58h] [rbp+10h] BYREF

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
          goto $errRtn_166;
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
          goto $errRtn_166;
        }
      }
      v4 = -2147221056;
$errRtn_166:
      HeapFree(g_hHeap, 0, v7);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a8384  mov     rax, rsp
0x1800a8387  mov     [rax+8], rbx
0x1800a838b  mov     [rax+18h], rbp
0x1800a838f  mov     [rax+20h], rsi
0x1800a8393  push    rdi
0x1800a8394  push    r14
0x1800a8396  push    r15
0x1800a8398  sub     rsp, 30h
0x1800a839c  and     dword ptr [rax+10h], 0
0x1800a83a0  mov     rsi, ppsz
0x1800a83a3  mov     rbp, pos
0x1800a83a6  test    ppsz, ppsz
0x1800a83a9  jz      short loc_1800A83AF
0x1800a83ab  and     qword ptr [ppsz], 0
0x1800a83af  lea     ppsz, [rsp+48h+cbSize]; pul
0x1800a83b4  call    OLE1StreamToUL
0x1800a83b9  mov     ebx, eax
0x1800a83bb  test    eax, eax
0x1800a83bd  js      loc_1800A84D2
0x1800a83c3  mov     edi, [rsp+48h+cbSize]
0x1800a83c7  test    edi, edi
0x1800a83c9  jz      loc_1800A84D2
0x1800a83cf  mov     r14d, edi
0x1800a83d2  call    GetSafeAllocSize
0x1800a83d7  cmp     rdi, rax
0x1800a83da  jnb     loc_1800A84CD
0x1800a83e0  mov     pos, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a83e7  mov     r8d, edi; dwBytes
0x1800a83ea  xor     edx, edx; dwFlags
0x1800a83ec  call    cs:__imp_HeapAlloc
0x1800a83f3  nop     dword ptr [rax+rax+00h]
0x1800a83f8  mov     r15, rax
0x1800a83fb  test    rax, rax
0x1800a83fe  jz      loc_1800A84CD
0x1800a8404  mov     pos, [rbp+0]
0x1800a8408  mov     r8d, edi
0x1800a840b  mov     ppsz, r15
0x1800a840e  mov     rax, [pos]
0x1800a8411  mov     pos, rbp
0x1800a8414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8419  cmp     eax, edi
0x1800a841b  jnb     short loc_1800A8427
0x1800a841d  mov     ebx, 800401C0h
0x1800a8422  jmp     $errRtn_166
0x1800a8427  test    rsi, rsi
0x1800a842a  jz      $errRtn_166
0x1800a8430  xor     r8d, r8d; pcbLength
0x1800a8433  mov     ppsz, r14; cbMax
0x1800a8436  mov     pos, r15; psz
0x1800a8439  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800a843e  test    eax, eax
0x1800a8440  js      short loc_1800A841D
0x1800a8442  lea     eax, [rdi+rdi]
0x1800a8445  cmp     edi, eax
0x1800a8447  ja      short loc_1800A841D
0x1800a8449  add     r14, r14
0x1800a844c  call    GetSafeAllocSize
0x1800a8451  cmp     r14, rax
0x1800a8454  jnb     short loc_1800A84AE
0x1800a8456  mov     pos, r14; cb
0x1800a8459  call    cs:__imp_CoTaskMemAlloc
0x1800a8460  nop     dword ptr [rax+rax+00h]
0x1800a8465  mov     rbp, rax
0x1800a8468  test    rax, rax
0x1800a846b  jz      short loc_1800A84AE
0x1800a846d  mov     [rsp+48h+cchWideChar], edi; cchWideChar
0x1800a8471  mov     r9d, edi; cbMultiByte
0x1800a8474  mov     r8, r15; lpMultiByteStr
0x1800a8477  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x1800a847c  mov     edx, 1; dwFlags
0x1800a8481  xor     ecx, ecx; CodePage
0x1800a8483  call    cs:__imp_MultiByteToWideChar
0x1800a848a  nop     dword ptr [rax+rax+00h]
0x1800a848f  test    eax, eax
0x1800a8491  jnz     short loc_1800A84A9
0x1800a8493  mov     pos, rbp; pv
0x1800a8496  mov     ebx, 80070459h
0x1800a849b  call    cs:__imp_CoTaskMemFree
0x1800a84a2  nop     dword ptr [rax+rax+00h]
0x1800a84a7  jmp     short $errRtn_166
0x1800a84a9  mov     [rsi], rbp
0x1800a84ac  jmp     short $errRtn_166
0x1800a84ae  mov     ebx, 8007000Eh
0x1800a84b3  mov     pos, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a84ba  mov     r8, r15; lpMem
0x1800a84bd  xor     edx, edx; dwFlags
0x1800a84bf  call    cs:__imp_HeapFree
0x1800a84c6  nop     dword ptr [rax+rax+00h]
0x1800a84cb  jmp     short loc_1800A84D2
0x1800a84cd  mov     ebx, 8007000Eh
0x1800a84d2  mov     rbp, [rsp+48h+arg_10]
0x1800a84d7  mov     eax, ebx
0x1800a84d9  mov     rbx, [rsp+48h+arg_0]
0x1800a84de  mov     rsi, [rsp+48h+arg_18]
0x1800a84e3  add     rsp, 30h
0x1800a84e7  pop     r15
0x1800a84e9  pop     r14
0x1800a84eb  pop     rdi
0x1800a84ec  retn
```
