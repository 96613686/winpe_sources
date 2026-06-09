# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180005ea4`
- end: `0x180005f02`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `94`
- prototype: `int(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d7c`
- `0x1800052d8`
- `0x180007e0c`
- `0x180008f50`
- `0x18000ac68`
- `0x18000ca48`
- `0x1800114d4`
- `0x180011f44`

## callees

- `0x180005ea4`
- `0x180005f60`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, size_t a2, wchar_t *a3, ...)
{
  unsigned int v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringVPrintfWorkerW(a1, a2, (size_t *)a3, a3, va);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180005ea4  mov     [rsp+arg_10], r8
0x180005ea9  mov     qword ptr [rsp+arg_18], r9
0x180005eae  sub     rsp, 48h
0x180005eb2  mov     rax, rdx
0x180005eb5  test    rdx, rdx
0x180005eb8  jz      short loc_180005EEB
0x180005eba  cmp     rax, 7FFFFFFFh
0x180005ec0  jbe     short loc_180005EC9
0x180005ec2  mov     edx, 80070057h
0x180005ec7  jmp     short loc_180005EF5
0x180005ec9  lea     rdx, [rsp+48h+arg_18]
0x180005ece  mov     [rsp+48h+var_18], 0
0x180005ed7  mov     [rsp+48h+argList], rdx; argList
0x180005edc  mov     r9, r8; pszFormat
0x180005edf  mov     rdx, rax; cchDest
0x180005ee2  call    StringVPrintfWorkerW
0x180005ee7  mov     edx, eax
0x180005ee9  jmp     short loc_180005EFA
0x180005eeb  mov     edx, 80070057h
0x180005ef0  test    rax, rax
0x180005ef3  jz      short loc_180005EFA
0x180005ef5  xor     eax, eax
0x180005ef7  mov     [rcx], ax
0x180005efa  mov     eax, edx
0x180005efc  add     rsp, 48h
0x180005f00  retn
```
