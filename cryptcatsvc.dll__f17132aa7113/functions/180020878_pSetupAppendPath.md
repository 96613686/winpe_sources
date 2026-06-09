# pSetupAppendPath

- ea: `0x180020878`
- end: `0x180020998`
- name: `pSetupAppendPath`
- size: `288`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180021124`
- `0x180021288`

## callees

- `0x180007188`
- `0x180007f30`
- `0x180008020`
- `0x1800087c8`
- `0x18001ff2c`
- `0x18001ff48`
- `0x180020878`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020977`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020977`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800208ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800208ae`

## pseudocode

```c
__int64 __fastcall pSetupAppendPath(STRSAFE_LPCWSTR pszSrc, const wchar_t *a2, __int64 *a3)
{
  const wchar_t *v5; // r15
  unsigned int v6; // ebx
  _WORD *v7; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // r12d
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  unsigned int v15; // r14d

  v5 = pszSrc;
  v6 = 0;
  if ( !pszSrc && !a2 )
  {
    v7 = HeapAlloc(hHeap, 0, 2u);
    *a3 = (__int64)v7;
    if ( v7 )
    {
      *v7 = 0;
      return 1;
    }
    return 0;
  }
  if ( !pszSrc )
  {
    pszSrc = a2;
LABEL_7:
    v9 = pSetupDuplicateString(pszSrc);
    *a3 = v9;
    LOBYTE(v6) = v9 != 0;
    return v6;
  }
  if ( !a2 )
    goto LABEL_7;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  do
    ++v10;
  while ( v5[v10] );
  v12 = v10 + v11 + 2;
  v13 = (wchar_t *)SpUtilsMallocElements(v12);
  v14 = v13;
  if ( !v13 )
  {
    *a3 = 0;
    return 0;
  }
  StringCchCopyW(v13, v12, v5);
  v15 = pSetupConcatenatePaths(v14, a2, v12);
  if ( !v15 )
  {
    HeapFree(hHeap, 0, v14);
    v14 = 0;
  }
  *a3 = (__int64)v14;
  return v15;
}

```

## disassembly

```asm
0x180020878  mov     [rsp+arg_8], rbx
0x18002087d  mov     [rsp+arg_10], r8
0x180020882  push    rsi
0x180020883  push    rdi
0x180020884  push    r12
0x180020886  push    r14
0x180020888  push    r15
0x18002088a  sub     rsp, 30h
0x18002088e  mov     rdi, r8
0x180020891  mov     r14, rdx
0x180020894  mov     r15, rcx
0x180020897  xor     ebx, ebx
0x180020899  test    rcx, rcx
0x18002089c  jnz     short loc_1800208C7
0x18002089e  test    rdx, rdx
0x1800208a1  jnz     short loc_1800208C7
0x1800208a3  lea     r8d, [rcx+2]; dwBytes
0x1800208a7  mov     rcx, cs:hHeap; hHeap
0x1800208ae  call    cs:__imp_HeapAlloc
0x1800208b4  mov     [rdi], rax
0x1800208b7  test    rax, rax
0x1800208ba  jz      short loc_180020922
0x1800208bc  mov     [rax], bx
0x1800208bf  lea     eax, [rbx+1]
0x1800208c2  jmp     loc_180020986
0x1800208c7  test    r15, r15
0x1800208ca  jnz     short loc_1800208E4
0x1800208cc  mov     rcx, r14
0x1800208cf  call    pSetupDuplicateString
0x1800208d4  mov     [rdi], rax
0x1800208d7  test    rax, rax
0x1800208da  setnz   bl
0x1800208dd  mov     eax, ebx
0x1800208df  jmp     loc_180020986
0x1800208e4  test    r14, r14
0x1800208e7  jz      short loc_1800208CF
0x1800208e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800208ed  mov     rcx, rax
0x1800208f0  inc     rcx
0x1800208f3  cmp     [rdx+rcx*2], bx
0x1800208f7  jnz     short loc_1800208F0
0x1800208f9  inc     rax
0x1800208fc  cmp     [r15+rax*2], bx
0x180020901  jnz     short loc_1800208F9
0x180020903  lea     r12d, [rcx+2]
0x180020907  add     r12d, eax
0x18002090a  mov     ecx, r12d
0x18002090d  call    SpUtilsMallocElements
0x180020912  mov     rsi, rax
0x180020915  mov     [rsp+58h+arg_0], rax
0x18002091a  test    rax, rax
0x18002091d  jnz     short loc_180020926
0x18002091f  mov     [rdi], rbx
0x180020922  xor     eax, eax
0x180020924  jmp     short loc_180020986
0x180020926  mov     edx, r12d; cchDest
0x180020929  mov     r8, r15; pszSrc
0x18002092c  mov     rcx, rsi; pszDest
0x18002092f  call    StringCchCopyW
0x180020934  mov     r8d, r12d
0x180020937  mov     rdx, r14
0x18002093a  mov     rcx, rsi
0x18002093d  call    pSetupConcatenatePaths
0x180020942  mov     r14d, eax
0x180020945  mov     [rsp+58h+var_38], eax
0x180020949  jmp     short loc_180020966
0x18002094b  mov     ecx, eax
0x18002094d  call    pSetupExceptionHandler
0x180020952  xor     r14d, r14d
0x180020955  mov     [rsp+58h+var_38], r14d
0x18002095a  xor     ebx, ebx
0x18002095c  mov     rdi, [rsp+58h+arg_10]
0x180020961  mov     rsi, [rsp+58h+arg_0]
0x180020966  test    r14d, r14d
0x180020969  jnz     short loc_180020980
0x18002096b  mov     r8, rsi; lpMem
0x18002096e  xor     edx, edx; dwFlags
0x180020970  mov     rcx, cs:hHeap; hHeap
0x180020977  call    cs:__imp_HeapFree
0x18002097d  mov     rsi, rbx
0x180020980  mov     [rdi], rsi
0x180020983  mov     eax, r14d
0x180020986  mov     rbx, [rsp+58h+arg_8]
0x18002098b  add     rsp, 30h
0x18002098f  pop     r15
0x180020991  pop     r14
0x180020993  pop     r12
0x180020995  pop     rdi
0x180020996  pop     rsi
0x180020997  retn
0x180021bd1  push    rbp
0x180021bd3  sub     rsp, 20h
0x180021bd7  mov     rbp, rdx
0x180021bda  mov     rcx, [rcx]
0x180021bdd  mov     ecx, [rcx]
0x180021bdf  call    pSetupExceptionFilter
0x180021be4  nop
0x180021be5  add     rsp, 20h
0x180021be9  pop     rbp
0x180021bea  retn
```
