# _wcserror

- ea: `0x180030e40`
- end: `0x180030eef`
- name: `_wcserror`
- size: `175`
- prototype: `wchar_t *__cdecl(int ErrorNumber)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003bf0`
- `0x18001d50c`
- `0x18002f05c`
- `0x180030e40`
- `0x18003e074`

## string_xrefs

- `0x180030ed8`: `Visual C++ CRT: Not enough memory to complete call to strerror.`

## pseudocode

```c
wchar_t *__cdecl wcserror(int ErrorNumber)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  wchar_t *v4; // rbx
  __int64 v5; // rax

  v2 = getptd_noexit();
  v3 = v2;
  if ( !v2 )
    return L"Visual C++ CRT: Not enough memory to complete call to strerror.";
  v4 = *(wchar_t **)(v2 + 64);
  if ( !v4 )
  {
    v5 = calloc_crt(134, 2);
    *(_QWORD *)(v3 + 64) = v5;
    v4 = (wchar_t *)v5;
    if ( !v5 )
      return L"Visual C++ CRT: Not enough memory to complete call to strerror.";
  }
  if ( ErrorNumber < 0 || ErrorNumber >= sys_nerr )
    ErrorNumber = sys_nerr;
  if ( mbstowcs_s(0, v4, 0x86u, sys_errlist[ErrorNumber], 0x85u) )
    invoke_watson(0, 0, 0, 0, 0);
  return v4;
}

```

## disassembly

```asm
0x180030e40  mov     [rsp+arg_0], rbx
0x180030e45  mov     [rsp+arg_8], rsi
0x180030e4a  push    rdi
0x180030e4b  sub     rsp, 30h
0x180030e4f  mov     edi, ecx
0x180030e51  call    _getptd_noexit
0x180030e56  mov     rsi, rax
0x180030e59  test    rax, rax
0x180030e5c  jz      short loc_180030ED8
0x180030e5e  mov     rbx, [rax+40h]
0x180030e62  test    rbx, rbx
0x180030e65  jnz     short loc_180030E80
0x180030e67  lea     edx, [rbx+2]
0x180030e6a  mov     ecx, 86h
0x180030e6f  call    _calloc_crt
0x180030e74  mov     [rsi+40h], rax
0x180030e78  mov     rbx, rax
0x180030e7b  test    rax, rax
0x180030e7e  jz      short loc_180030ED8
0x180030e80  mov     eax, cs:_sys_nerr
0x180030e86  test    edi, edi
0x180030e88  js      short loc_180030E8E
0x180030e8a  cmp     edi, eax
0x180030e8c  jl      short loc_180030E90
0x180030e8e  mov     edi, eax
0x180030e90  lea     rax, _sys_errlist
0x180030e97  movsxd  r9, edi
0x180030e9a  mov     r8d, 86h; SizeInWords
0x180030ea0  mov     [rsp+38h+MaxCount], 85h; MaxCount
0x180030ea9  mov     rdx, rbx; DstBuf
0x180030eac  xor     ecx, ecx; PtNumOfCharConverted
0x180030eae  mov     r9, [rax+r9*8]; SrcBuf
0x180030eb2  call    mbstowcs_s
0x180030eb7  test    eax, eax
0x180030eb9  jz      short loc_180030ED3
0x180030ebb  xor     r9d, r9d; LineNo
0x180030ebe  mov     [rsp+38h+MaxCount], 0; Reserved
0x180030ec7  xor     r8d, r8d; FileName
0x180030eca  xor     edx, edx; FunctionName
0x180030ecc  xor     ecx, ecx; Expression
0x180030ece  call    _invoke_watson
0x180030ed3  mov     rax, rbx
0x180030ed6  jmp     short loc_180030EDF
0x180030ed8  lea     rax, aVisualCCrtNotE
0x180030edf  mov     rbx, [rsp+38h+arg_0]
0x180030ee4  mov     rsi, [rsp+38h+arg_8]
0x180030ee9  add     rsp, 30h
0x180030eed  pop     rdi
0x180030eee  retn
```
