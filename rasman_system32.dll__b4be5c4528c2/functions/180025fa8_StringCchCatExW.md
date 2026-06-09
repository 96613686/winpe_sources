# StringCchCatExW

- ea: `0x180025fa8`
- end: `0x180026051`
- name: `StringCchCatExW`
- size: `169`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180025dec`

## callees

- `0x1800155ac`
- `0x180025fa8`
- `0x1800261a4`
- `0x180026288`

## string_xrefs

- `0x180026000`: `\cmdial32.dll`

## pseudocode

```c
HRESULT __stdcall StringCchCatExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_LPCWSTR pszSrc,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  int v7; // ebx
  size_t v8; // rsi
  size_t *v10; // [rsp+20h] [rbp-18h]
  STRSAFE_LPWSTR ppszDestEnda; // [rsp+50h] [rbp+18h] BYREF
  size_t pcchNewDestLength; // [rsp+58h] [rbp+20h] BYREF

  pcchNewDestLength = 0;
  v7 = StringLengthWorkerW_0(pszDest, cchDest, &pcchNewDestLength);
  if ( v7 >= 0 )
  {
    v8 = pcchNewDestLength;
    if ( pcchNewDestLength == 261 || pcchNewDestLength == 260 )
    {
      v7 = pszDest != 0 ? -2147024774 : -2147024809;
LABEL_5:
      StringExHandleOtherFlagsW(pszDest, 0x20Au, v8, &ppszDestEnda, &pcchNewDestLength, 0x800u);
      return v7;
    }
    v7 = StringCopyWorkerW(
           &pszDest[pcchNewDestLength],
           261 - pcchNewDestLength,
           &pcchNewDestLength,
           L"\\cmdial32.dll",
           (size_t)v10);
    if ( v7 < 0 )
      goto LABEL_5;
  }
  return v7;
}

```

## disassembly

```asm
0x180025fa8  mov     rax, rsp
0x180025fab  mov     [rax+8], rbx
0x180025faf  mov     [rax+10h], rsi
0x180025fb3  mov     [rax+20h], r9
0x180025fb7  push    rdi
0x180025fb8  sub     rsp, 30h
0x180025fbc  lea     r8, [rax+20h]; pcchLength
0x180025fc0  mov     qword ptr [rax+20h], 0
0x180025fc8  mov     rdi, rcx
0x180025fcb  call    StringLengthWorkerW_0
0x180025fd0  mov     ebx, eax
0x180025fd2  test    eax, eax
0x180025fd4  js      short loc_18002603E
0x180025fd6  mov     rsi, [rsp+38h+pcchNewDestLength]
0x180025fdb  mov     edx, 105h
0x180025fe0  sub     rdx, rsi; cchDest
0x180025fe3  lea     rcx, [rdi+rsi*2]; pszDest
0x180025fe7  cmp     rdx, 1
0x180025feb  ja      short loc_180026000
0x180025fed  mov     rax, rdi
0x180025ff0  neg     rax
0x180025ff3  sbb     ebx, ebx
0x180025ff5  and     ebx, 23h
0x180025ff8  add     ebx, 80070057h
0x180025ffe  jmp     short loc_180026017
0x180026000  lea     r9, aCmdial32Dll; "\\cmdial32.dll"
0x180026007  lea     r8, [rsp+38h+pcchNewDestLength]; pcchNewDestLength
0x18002600c  call    StringCopyWorkerW
0x180026011  mov     ebx, eax
0x180026013  test    eax, eax
0x180026015  jns     short loc_18002603E
0x180026017  lea     rax, [rsp+38h+pcchNewDestLength]
0x18002601c  mov     [rsp+38h+var_10], 800h; dwFlags
0x180026024  lea     r9, [rsp+38h+ppszDestEnd]; ppszDestEnd
0x180026029  mov     [rsp+38h+var_18], rax; pcchRemaining
0x18002602e  mov     r8, rsi; cchOriginalDestLength
0x180026031  mov     edx, 20Ah; cbDest
0x180026036  mov     rcx, rdi; pszDest
0x180026039  call    StringExHandleOtherFlagsW
0x18002603e  mov     rsi, [rsp+38h+arg_8]
0x180026043  mov     eax, ebx
0x180026045  mov     rbx, [rsp+38h+arg_0]
0x18002604a  add     rsp, 30h
0x18002604e  pop     rdi
0x18002604f  retn
```
