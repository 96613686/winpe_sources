# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005a80`
- end: `0x180005ac4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `68`
- prototype: `__int64(unsigned __int16 *, size_t, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a38`
- `0x180004fa8`
- `0x180006744`
- `0x180007b7c`

## callees

- `0x180005a80`
- `0x180005bb0`
- `0x180005c04`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3, ...)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  v6 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v6 < 0 )
  {
    if ( v3 )
      *v4 = 0;
  }
  else
  {
    return (unsigned int)StringVPrintfWorkerW(v4, v3, v5, (STRSAFE_LPCWSTR)v5, va);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005a80  mov     [rsp+arg_10], r8
0x180005a85  mov     qword ptr [rsp+arg_18], r9
0x180005a8a  sub     rsp, 48h
0x180005a8e  call    StringValidateDestW
0x180005a93  mov     r9d, eax
0x180005a96  xor     eax, eax
0x180005a98  test    r9d, r9d
0x180005a9b  js      short loc_180005AB4
0x180005a9d  lea     rax, [rsp+48h+arg_18]
0x180005aa2  mov     r9, r8; pszFormat
0x180005aa5  mov     [rsp+48h+argList], rax; argList
0x180005aaa  call    StringVPrintfWorkerW
0x180005aaf  mov     r9d, eax
0x180005ab2  jmp     short loc_180005ABC
0x180005ab4  test    rdx, rdx
0x180005ab7  jz      short loc_180005ABC
0x180005ab9  mov     [rcx], ax
0x180005abc  mov     eax, r9d
0x180005abf  add     rsp, 48h
0x180005ac3  retn
```
