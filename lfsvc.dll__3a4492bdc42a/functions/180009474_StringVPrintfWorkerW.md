# StringVPrintfWorkerW

- ea: `0x180009474`
- end: `0x1800094c1`
- name: `StringVPrintfWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051d8`
- `0x18000935c`
- `0x1800093d4`

## callees

- `0x180004d60`
- `0x180009474`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  size_t v5; // rbx
  int v7; // eax
  HRESULT v8; // ecx

  v5 = cchDest - 1;
  v7 = vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
  if ( v7 < 0 || v7 > v5 )
  {
    v8 = -2147024774;
LABEL_6:
    pszDest[v5] = 0;
    return v8;
  }
  v8 = 0;
  if ( v7 == v5 )
    goto LABEL_6;
  return v8;
}

```

## disassembly

```asm
0x180009474  mov     [rsp+arg_0], rbx
0x180009479  push    rdi
0x18000947a  sub     rsp, 20h
0x18000947e  lea     rbx, [rdx-1]
0x180009482  mov     r8, r9; Format
0x180009485  mov     r9, [rsp+28h+argList]; Args
0x18000948a  mov     rdx, rbx; BufferCount
0x18000948d  mov     rdi, rcx
0x180009490  call    _vsnwprintf
0x180009495  test    eax, eax
0x180009497  js      short loc_1800094A9
0x180009499  cdqe
0x18000949b  cmp     rax, rbx
0x18000949e  ja      short loc_1800094A9
0x1800094a0  xor     ecx, ecx
0x1800094a2  cmp     rax, rbx
0x1800094a5  jnz     short loc_1800094B4
0x1800094a7  jmp     short loc_1800094AE
0x1800094a9  mov     ecx, 8007007Ah
0x1800094ae  xor     eax, eax
0x1800094b0  mov     [rdi+rbx*2], ax
0x1800094b4  mov     rbx, [rsp+28h+arg_0]
0x1800094b9  mov     eax, ecx
0x1800094bb  add     rsp, 20h
0x1800094bf  pop     rdi
0x1800094c0  retn
```
