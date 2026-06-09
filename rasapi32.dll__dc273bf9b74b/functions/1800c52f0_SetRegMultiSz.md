# SetRegMultiSz

- ea: `0x1800c52f0`
- end: `0x1800c540b`
- name: `SetRegMultiSz`
- size: `283`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800c4744`

## callees

- `0x18000e1b0`
- `0x1800c52f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c53eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c53eb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c5339`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c5339`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c53f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c53f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800c5314`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800c5314`

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
0x1800c52f0  push    rbx
0x1800c52f2  push    rbp
0x1800c52f3  push    rsi
0x1800c52f4  push    rdi
0x1800c52f5  push    r14
0x1800c52f7  push    r15
0x1800c52f9  sub     rsp, 48h
0x1800c52fd  mov     rbx, [r8]
0x1800c5300  mov     r14, r8
0x1800c5303  mov     rbp, rdx
0x1800c5306  mov     r15, rcx
0x1800c5309  mov     edi, 2
0x1800c530e  jmp     short loc_1800C5324
0x1800c5310  mov     rcx, [rbx+10h]; lpString
0x1800c5314  call    cs:__imp_lstrlenW
0x1800c531a  mov     rbx, [rbx+8]
0x1800c531e  lea     edi, [rdi+rax*2]
0x1800c5321  add     edi, 2
0x1800c5324  test    rbx, rbx
0x1800c5327  jnz     short loc_1800C5310
0x1800c5329  lea     eax, [rbx+4]
0x1800c532c  cmp     edi, 2
0x1800c532f  lea     ecx, [rbx+40h]; uFlags
0x1800c5332  cmovnz  eax, edi
0x1800c5335  mov     edx, eax; dwBytes
0x1800c5337  mov     esi, eax
0x1800c5339  call    cs:__imp_GlobalAlloc
0x1800c533f  mov     rbx, rax
0x1800c5342  test    rax, rax
0x1800c5345  jnz     short loc_1800C534F
0x1800c5347  lea     eax, [rbx+8]
0x1800c534a  jmp     loc_1800C53FE
0x1800c534f  mov     rax, rsi
0x1800c5352  shr     rax, 1
0x1800c5355  mov     [rsp+78h+var_48], rax
0x1800c535a  cmp     esi, 4
0x1800c535d  jnz     short loc_1800C5365
0x1800c535f  xor     eax, eax
0x1800c5361  mov     [rbx], eax
0x1800c5363  jmp     short loc_1800C53D3
0x1800c5365  mov     rdi, [r14]
0x1800c5368  mov     rcx, rbx; pszDest
0x1800c536b  mov     [rsp+78h+ppszDestEnd], rbx
0x1800c5373  test    rdi, rdi
0x1800c5376  jz      short loc_1800C53CE
0x1800c5378  mov     r8, [rdi+10h]; pszSrc
0x1800c537c  lea     rdx, [rsp+78h+var_48]
0x1800c5381  mov     [rsp+78h+dwFlags], 100h; dwFlags
0x1800c5389  lea     r9, [rsp+78h+ppszDestEnd]; ppszDestEnd
0x1800c5391  mov     [rsp+78h+pcchRemaining], rdx; pcchRemaining
0x1800c5396  mov     rdx, rax; cchDest
0x1800c5399  call    StringCchCopyExW
0x1800c539e  test    eax, eax
0x1800c53a0  js      short loc_1800C53C9
0x1800c53a2  mov     rcx, [rsp+78h+ppszDestEnd]
0x1800c53aa  mov     rax, [rsp+78h+var_48]
0x1800c53af  add     rcx, 2
0x1800c53b3  mov     rdi, [rdi+8]
0x1800c53b7  dec     rax
0x1800c53ba  mov     [rsp+78h+var_48], rax
0x1800c53bf  mov     [rsp+78h+ppszDestEnd], rcx
0x1800c53c7  jmp     short loc_1800C5373
0x1800c53c9  movzx   edi, ax
0x1800c53cc  jmp     short loc_1800C53F3
0x1800c53ce  xor     eax, eax
0x1800c53d0  mov     [rcx], ax
0x1800c53d3  mov     [rsp+78h+dwFlags], esi; cbData
0x1800c53d7  mov     r9d, 7; dwType
0x1800c53dd  xor     r8d, r8d; Reserved
0x1800c53e0  mov     [rsp+78h+pcchRemaining], rbx; lpData
0x1800c53e5  mov     rdx, rbp; lpValueName
0x1800c53e8  mov     rcx, r15; hKey
0x1800c53eb  call    cs:__imp_RegSetValueExW
0x1800c53f1  mov     edi, eax
0x1800c53f3  mov     rcx, rbx; hMem
0x1800c53f6  call    cs:__imp_GlobalFree
0x1800c53fc  mov     eax, edi
0x1800c53fe  add     rsp, 48h
0x1800c5402  pop     r15
0x1800c5404  pop     r14
0x1800c5406  pop     rdi
0x1800c5407  pop     rsi
0x1800c5408  pop     rbp
0x1800c5409  pop     rbx
0x1800c540a  retn
```
