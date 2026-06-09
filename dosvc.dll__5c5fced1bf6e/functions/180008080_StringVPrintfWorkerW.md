# StringVPrintfWorkerW

- ea: `0x180008080`
- end: `0x1800080cd`
- name: `StringVPrintfWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007f7c`
- `0x180007fe0`
- `0x180008a6c`

## callees

- `0x180005b5c`
- `0x180008080`

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
0x180008080  mov     [rsp+arg_0], rbx
0x180008085  push    rdi
0x180008086  sub     rsp, 20h
0x18000808a  lea     rbx, [rdx-1]
0x18000808e  mov     r8, r9; Format
0x180008091  mov     r9, [rsp+28h+argList]; Args
0x180008096  mov     rdx, rbx; BufferCount
0x180008099  mov     rdi, rcx
0x18000809c  call    _vsnwprintf
0x1800080a1  test    eax, eax
0x1800080a3  js      short loc_1800080B5
0x1800080a5  cdqe
0x1800080a7  cmp     rax, rbx
0x1800080aa  ja      short loc_1800080B5
0x1800080ac  xor     ecx, ecx
0x1800080ae  cmp     rax, rbx
0x1800080b1  jnz     short loc_1800080C0
0x1800080b3  jmp     short loc_1800080BA
0x1800080b5  mov     ecx, 8007007Ah
0x1800080ba  xor     eax, eax
0x1800080bc  mov     [rdi+rbx*2], ax
0x1800080c0  mov     rbx, [rsp+28h+arg_0]
0x1800080c5  mov     eax, ecx
0x1800080c7  add     rsp, 20h
0x1800080cb  pop     rdi
0x1800080cc  retn
```
