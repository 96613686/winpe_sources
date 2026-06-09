# StringCchCopyA(x,x,x)

- ea: `0x1000ed1b`
- end: `0x1000ed48`
- name: `_StringCchCopyA@12`
- size: `45`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1000f076`

## callees

- `0x1000ed1b`
- `0x1000edf3`

## pseudocode

```c

```

## disassembly

```asm
0x1000ed1b  mov     edi, edi
0x1000ed1d  push    ebp; pszSrc
0x1000ed1e  mov     ebp, esp
0x1000ed20  test    edx, edx
0x1000ed22  jz      short loc_1000ED38
0x1000ed24  cmp     edx, 7FFFFFFFh
0x1000ed2a  ja      short loc_1000ED38
0x1000ed2c  push    ecx; pcchNewDestLength
0x1000ed2d  push    [ebp+pszDest]; cchDest
0x1000ed30  push    ecx; pszDest
0x1000ed31  call    StringCopyWorkerA
0x1000ed36  jmp     short loc_1000ED44
0x1000ed38  mov     eax, 80070057h
0x1000ed3d  test    edx, edx
0x1000ed3f  jz      short loc_1000ED44
0x1000ed41  mov     byte ptr [ecx], 0
0x1000ed44  pop     ebp
0x1000ed45  retn    4
```
