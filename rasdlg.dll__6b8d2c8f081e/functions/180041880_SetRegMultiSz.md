# SetRegMultiSz

- ea: `0x180041880`
- end: `0x18004199b`
- name: `SetRegMultiSz`
- size: `283`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003ff50`

## callees

- `0x18001e944`
- `0x180041880`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800418c9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800418c9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180041986`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180041986`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004197b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004197b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800418a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800418a4`

## pseudocode

```c
__int64 __fastcall SetRegMultiSz(HKEY hKey, LPCWSTR lpValueName, __int64 *a3)
{
  __int64 v3; // rbx
  int v7; // edi
  int v8; // eax
  unsigned int v9; // eax
  unsigned __int64 v10; // rsi
  wchar_t *v11; // rbx
  size_t v13; // rax
  __int64 v14; // rdi
  wchar_t *v15; // rcx
  HRESULT v16; // eax
  unsigned int v17; // edi
  size_t pcchRemaining[9]; // [rsp+30h] [rbp-48h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+90h] [rbp+18h] BYREF

  v3 = *a3;
  v7 = 2;
  while ( v3 )
  {
    v8 = lstrlenW(*(LPCWSTR *)(v3 + 16));
    v3 = *(_QWORD *)(v3 + 8);
    v7 += 2 * v8 + 2;
  }
  v9 = 4;
  if ( v7 != 2 )
    v9 = v7;
  v10 = v9;
  v11 = (wchar_t *)GlobalAlloc(0x40u, v9);
  if ( !v11 )
    return 8;
  v13 = v10 >> 1;
  pcchRemaining[0] = v10 >> 1;
  if ( (_DWORD)v10 == 4 )
  {
    *(_DWORD *)v11 = 0;
  }
  else
  {
    v14 = *a3;
    v15 = v11;
    ppszDestEnd = v11;
    while ( v14 )
    {
      v16 = StringCchCopyExW(v15, v13, *(STRSAFE_LPCWSTR *)(v14 + 16), &ppszDestEnd, pcchRemaining, 0x100u);
      if ( v16 < 0 )
      {
        v17 = (unsigned __int16)v16;
        goto LABEL_17;
      }
      v15 = ppszDestEnd + 1;
      v14 = *(_QWORD *)(v14 + 8);
      v13 = --pcchRemaining[0];
      ++ppszDestEnd;
    }
    *v15 = 0;
  }
  v17 = RegSetValueExW(hKey, lpValueName, 0, 7u, (const BYTE *)v11, v10);
LABEL_17:
  GlobalFree(v11);
  return v17;
}

```

## disassembly

```asm
0x180041880  push    rbx
0x180041882  push    rbp
0x180041883  push    rsi
0x180041884  push    rdi
0x180041885  push    r14
0x180041887  push    r15
0x180041889  sub     rsp, 48h
0x18004188d  mov     rbx, [r8]
0x180041890  mov     r14, r8
0x180041893  mov     rbp, rdx
0x180041896  mov     r15, rcx
0x180041899  mov     edi, 2
0x18004189e  jmp     short loc_1800418B4
0x1800418a0  mov     rcx, [rbx+10h]; lpString
0x1800418a4  call    cs:__imp_lstrlenW
0x1800418aa  mov     rbx, [rbx+8]
0x1800418ae  lea     edi, [rdi+rax*2]
0x1800418b1  add     edi, 2
0x1800418b4  test    rbx, rbx
0x1800418b7  jnz     short loc_1800418A0
0x1800418b9  lea     eax, [rbx+4]
0x1800418bc  cmp     edi, 2
0x1800418bf  lea     ecx, [rbx+40h]; uFlags
0x1800418c2  cmovnz  eax, edi
0x1800418c5  mov     edx, eax; dwBytes
0x1800418c7  mov     esi, eax
0x1800418c9  call    cs:__imp_GlobalAlloc
0x1800418cf  mov     rbx, rax
0x1800418d2  test    rax, rax
0x1800418d5  jnz     short loc_1800418DF
0x1800418d7  lea     eax, [rbx+8]
0x1800418da  jmp     loc_18004198E
0x1800418df  mov     rax, rsi
0x1800418e2  shr     rax, 1
0x1800418e5  mov     [rsp+78h+var_48], rax
0x1800418ea  cmp     esi, 4
0x1800418ed  jnz     short loc_1800418F5
0x1800418ef  xor     eax, eax
0x1800418f1  mov     [rbx], eax
0x1800418f3  jmp     short loc_180041963
0x1800418f5  mov     rdi, [r14]
0x1800418f8  mov     rcx, rbx; pszDest
0x1800418fb  mov     [rsp+78h+ppszDestEnd], rbx
0x180041903  test    rdi, rdi
0x180041906  jz      short loc_18004195E
0x180041908  mov     r8, [rdi+10h]; pszSrc
0x18004190c  lea     rdx, [rsp+78h+var_48]
0x180041911  mov     [rsp+78h+dwFlags], 100h; dwFlags
0x180041919  lea     r9, [rsp+78h+ppszDestEnd]; ppszDestEnd
0x180041921  mov     [rsp+78h+pcchRemaining], rdx; pcchRemaining
0x180041926  mov     rdx, rax; cchDest
0x180041929  call    StringCchCopyExW
0x18004192e  test    eax, eax
0x180041930  js      short loc_180041959
0x180041932  mov     rcx, [rsp+78h+ppszDestEnd]
0x18004193a  mov     rax, [rsp+78h+var_48]
0x18004193f  add     rcx, 2
0x180041943  mov     rdi, [rdi+8]
0x180041947  dec     rax
0x18004194a  mov     [rsp+78h+var_48], rax
0x18004194f  mov     [rsp+78h+ppszDestEnd], rcx
0x180041957  jmp     short loc_180041903
0x180041959  movzx   edi, ax
0x18004195c  jmp     short loc_180041983
0x18004195e  xor     eax, eax
0x180041960  mov     [rcx], ax
0x180041963  mov     [rsp+78h+dwFlags], esi; cbData
0x180041967  mov     r9d, 7; dwType
0x18004196d  xor     r8d, r8d; Reserved
0x180041970  mov     [rsp+78h+pcchRemaining], rbx; lpData
0x180041975  mov     rdx, rbp; lpValueName
0x180041978  mov     rcx, r15; hKey
0x18004197b  call    cs:__imp_RegSetValueExW
0x180041981  mov     edi, eax
0x180041983  mov     rcx, rbx; hMem
0x180041986  call    cs:__imp_GlobalFree
0x18004198c  mov     eax, edi
0x18004198e  add     rsp, 48h
0x180041992  pop     r15
0x180041994  pop     r14
0x180041996  pop     rdi
0x180041997  pop     rsi
0x180041998  pop     rbp
0x180041999  pop     rbx
0x18004199a  retn
```
