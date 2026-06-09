# StringExHandleOtherFlagsW

- ea: `0x1800042c4`
- end: `0x180004361`
- name: `StringExHandleOtherFlagsW`
- size: `157`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, size_t cchOriginalDestLength, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f78`
- `0x180004100`

## callees

- `0x1800042c4`
- `0x180005486`

## pseudocode

```c
HRESULT __stdcall StringExHandleOtherFlagsW(
        STRSAFE_LPWSTR pszDest,
        size_t cbDest,
        size_t cchOriginalDestLength,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  size_t v6; // rdi
  wchar_t *v10; // rcx

  v6 = cbDest >> 1;
  if ( cbDest >> 1 && (dwFlags & 0x1000) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pszDest = 0;
    *pcchRemaining = v6;
  }
  if ( (dwFlags & 0x400) == 0 )
  {
LABEL_7:
    if ( !v6 )
      return 0;
    goto LABEL_8;
  }
  memset_0(pszDest, (unsigned __int8)dwFlags, cbDest);
  if ( !(_BYTE)dwFlags )
  {
    *ppszDestEnd = pszDest;
    *pcchRemaining = v6;
    goto LABEL_7;
  }
  if ( !v6 )
    return 0;
  *pcchRemaining = 1;
  v10 = &pszDest[v6 - 1];
  *ppszDestEnd = v10;
  *v10 = 0;
LABEL_8:
  if ( (dwFlags & 0x800) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pszDest = 0;
    *pcchRemaining = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800042c4  push    rbx
0x1800042c6  push    rsi
0x1800042c7  push    rdi
0x1800042c8  push    r14
0x1800042ca  push    r15
0x1800042cc  sub     rsp, 20h
0x1800042d0  mov     r15, [rsp+48h+pcchRemaining]
0x1800042d5  mov     rdi, rdx
0x1800042d8  shr     rdi, 1
0x1800042db  mov     r14, r9
0x1800042de  mov     rsi, rcx
0x1800042e1  jz      short loc_1800042F8
0x1800042e3  test    [rsp+48h+dwFlags], 1000h
0x1800042eb  jz      short loc_1800042F8
0x1800042ed  xor     eax, eax
0x1800042ef  mov     [r9], rcx
0x1800042f2  mov     [rcx], ax
0x1800042f5  mov     [r15], rdi
0x1800042f8  test    [rsp+48h+dwFlags], 400h
0x180004300  jz      short loc_18000431B
0x180004302  movzx   ebx, byte ptr [rsp+48h+dwFlags]
0x180004307  mov     r8, rdx; Size
0x18000430a  mov     edx, ebx; Val
0x18000430c  call    memset_0
0x180004311  test    ebx, ebx
0x180004313  jnz     short loc_180004343
0x180004315  mov     [r14], rsi
0x180004318  mov     [r15], rdi
0x18000431b  test    rdi, rdi
0x18000431e  jz      short loc_180004335
0x180004320  test    [rsp+48h+dwFlags], 800h
0x180004328  jz      short loc_180004335
0x18000432a  xor     eax, eax
0x18000432c  mov     [r14], rsi
0x18000432f  mov     [rsi], ax
0x180004332  mov     [r15], rdi
0x180004335  xor     eax, eax
0x180004337  add     rsp, 20h
0x18000433b  pop     r15
0x18000433d  pop     r14
0x18000433f  pop     rdi
0x180004340  pop     rsi
0x180004341  pop     rbx
0x180004342  retn
0x180004343  test    rdi, rdi
0x180004346  jz      short loc_180004335
0x180004348  lea     rcx, [rsi-2]
0x18000434c  mov     qword ptr [r15], 1
0x180004353  lea     rcx, [rcx+rdi*2]
0x180004357  xor     eax, eax
0x180004359  mov     [r14], rcx
0x18000435c  mov     [rcx], ax
0x18000435f  jmp     short loc_180004320
```
