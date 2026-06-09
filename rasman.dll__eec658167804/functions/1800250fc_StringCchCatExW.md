# StringCchCatExW

- ea: `0x1800250fc`
- end: `0x1800251a4`
- name: `StringCchCatExW`
- size: `168`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024f6c`

## callees

- `0x180014c0c`
- `0x1800250fc`
- `0x1800252f4`
- `0x1800253d4`

## string_xrefs

- `0x180025154`: `\cmdial32.dll`

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
0x1800250fc  mov     rax, rsp
0x1800250ff  mov     [rax+8], rbx
0x180025103  mov     [rax+10h], rsi
0x180025107  mov     [rax+20h], r9
0x18002510b  push    rdi
0x18002510c  sub     rsp, 30h
0x180025110  lea     r8, [rax+20h]; pcchLength
0x180025114  mov     qword ptr [rax+20h], 0
0x18002511c  mov     rdi, rcx
0x18002511f  call    StringLengthWorkerW_0
0x180025124  mov     ebx, eax
0x180025126  test    eax, eax
0x180025128  js      short loc_180025192
0x18002512a  mov     rsi, [rsp+38h+pcchNewDestLength]
0x18002512f  mov     edx, 105h
0x180025134  sub     rdx, rsi; cchDest
0x180025137  lea     rcx, [rdi+rsi*2]; pszDest
0x18002513b  cmp     rdx, 1
0x18002513f  ja      short loc_180025154
0x180025141  mov     rax, rdi
0x180025144  neg     rax
0x180025147  sbb     ebx, ebx
0x180025149  and     ebx, 23h
0x18002514c  add     ebx, 80070057h
0x180025152  jmp     short loc_18002516B
0x180025154  lea     r9, aCmdial32Dll; "\\cmdial32.dll"
0x18002515b  lea     r8, [rsp+38h+pcchNewDestLength]; pcchNewDestLength
0x180025160  call    StringCopyWorkerW
0x180025165  mov     ebx, eax
0x180025167  test    eax, eax
0x180025169  jns     short loc_180025192
0x18002516b  lea     rax, [rsp+38h+pcchNewDestLength]
0x180025170  mov     [rsp+38h+var_10], 800h; dwFlags
0x180025178  lea     r9, [rsp+38h+ppszDestEnd]; ppszDestEnd
0x18002517d  mov     [rsp+38h+var_18], rax; pcchRemaining
0x180025182  mov     r8, rsi; cchOriginalDestLength
0x180025185  mov     edx, 20Ah; cbDest
0x18002518a  mov     rcx, rdi; pszDest
0x18002518d  call    StringExHandleOtherFlagsW
0x180025192  mov     rsi, [rsp+38h+arg_8]
0x180025197  mov     eax, ebx
0x180025199  mov     rbx, [rsp+38h+arg_0]
0x18002519e  add     rsp, 30h
0x1800251a2  pop     rdi
0x1800251a3  retn
```
