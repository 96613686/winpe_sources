# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180001e80`
- end: `0x180001ebf`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `63`
- prototype: `int(unsigned __int16 *, size_t, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ce0`
- `0x180004e48`
- `0x1800095e8`

## callees

- `0x180001e80`
- `0x180007f20`
- `0x180007f74`

## pseudocode

```c
int StringCchPrintfW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3, ...)
{
  int result; // eax
  size_t v4; // rdx
  wchar_t *v5; // rcx
  size_t *v6; // r8
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  result = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( result >= 0 )
    return StringVPrintfWorkerW(v5, v4, v6, (STRSAFE_LPCWSTR)v6, va);
  if ( v4 )
    *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x180001e80  mov     [rsp+arg_10], r8
0x180001e85  mov     qword ptr [rsp+arg_18], r9
0x180001e8a  sub     rsp, 48h
0x180001e8e  call    StringValidateDestW
0x180001e93  test    eax, eax
0x180001e95  js      short loc_180001EAE
0x180001e97  lea     rax, [rsp+48h+arg_18]
0x180001e9c  mov     r9, r8; pszFormat
0x180001e9f  mov     [rsp+48h+argList], rax; argList
0x180001ea4  call    StringVPrintfWorkerW
0x180001ea9  add     rsp, 48h
0x180001ead  retn
0x180001eae  test    rdx, rdx
0x180001eb1  jz      short loc_180001EBA
0x180001eb3  xor     r9d, r9d
0x180001eb6  mov     [rcx], r9w
0x180001eba  add     rsp, 48h
0x180001ebe  retn
```
