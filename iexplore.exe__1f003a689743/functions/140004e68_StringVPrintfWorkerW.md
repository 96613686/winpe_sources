# StringVPrintfWorkerW

- ea: `0x140004e68`
- end: `0x140004eb6`
- name: `StringVPrintfWorkerW`
- size: `78`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000452c`
- `0x140004dac`

## callees

- `0x140004e68`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140004e84`
- `msvcrt!_vsnwprintf` at `0x140004e84`

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
  v7 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
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
0x140004e68  mov     [rsp+arg_0], rbx
0x140004e6d  push    rdi
0x140004e6e  sub     rsp, 20h
0x140004e72  lea     rbx, [rdx-1]
0x140004e76  mov     r8, r9; Format
0x140004e79  mov     r9, [rsp+28h+argList]; Args
0x140004e7e  mov     rdx, rbx; BufferCount
0x140004e81  mov     rdi, rcx
0x140004e84  call    cs:__imp__vsnwprintf
0x140004e8a  test    eax, eax
0x140004e8c  js      short loc_140004E9E
0x140004e8e  cdqe
0x140004e90  cmp     rax, rbx
0x140004e93  ja      short loc_140004E9E
0x140004e95  xor     ecx, ecx
0x140004e97  cmp     rax, rbx
0x140004e9a  jnz     short loc_140004EA9
0x140004e9c  jmp     short loc_140004EA3
0x140004e9e  mov     ecx, 8007007Ah
0x140004ea3  xor     eax, eax
0x140004ea5  mov     [rdi+rbx*2], ax
0x140004ea9  mov     rbx, [rsp+28h+arg_0]
0x140004eae  mov     eax, ecx
0x140004eb0  add     rsp, 20h
0x140004eb4  pop     rdi
0x140004eb5  retn
```
