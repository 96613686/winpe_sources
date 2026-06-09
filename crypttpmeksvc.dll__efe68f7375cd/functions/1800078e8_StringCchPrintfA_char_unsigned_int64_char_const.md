# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x1800078e8`
- end: `0x18000793a`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `82`
- prototype: `HRESULT(char *, size_t, size_t *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003750`
- `0x180007b38`
- `0x180007bcc`

## callees

- `0x180005240`
- `0x1800078e8`

## pseudocode

```c
HRESULT StringCchPrintfA(char *a1, size_t a2, size_t *a3, ...)
{
  HRESULT result; // eax
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( !a2 )
    return -2147024809;
  if ( a2 <= 0x7FFFFFFF )
    return StringVPrintfWorkerA(a1, a2, a3, (STRSAFE_LPCSTR)a3, va);
  result = -2147024809;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800078e8  mov     [rsp+arg_10], r8
0x1800078ed  mov     qword ptr [rsp+arg_18], r9
0x1800078f2  sub     rsp, 48h
0x1800078f6  test    rdx, rdx
0x1800078f9  jz      short loc_180007928
0x1800078fb  cmp     rdx, 7FFFFFFFh
0x180007902  jbe     short loc_18000790B
0x180007904  mov     eax, 80070057h
0x180007909  jmp     short loc_180007932
0x18000790b  lea     rax, [rsp+48h+arg_18]
0x180007910  mov     [rsp+48h+var_18], 0
0x180007919  mov     r9, r8; pszFormat
0x18000791c  mov     [rsp+48h+argList], rax; argList
0x180007921  call    StringVPrintfWorkerA
0x180007926  jmp     short loc_180007935
0x180007928  mov     eax, 80070057h
0x18000792d  test    rdx, rdx
0x180007930  jz      short loc_180007935
0x180007932  mov     byte ptr [rcx], 0
0x180007935  add     rsp, 48h
0x180007939  retn
```
