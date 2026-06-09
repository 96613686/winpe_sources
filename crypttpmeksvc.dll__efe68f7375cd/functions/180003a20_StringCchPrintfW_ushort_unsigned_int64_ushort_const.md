# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003a20`
- end: `0x180003a9c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `124`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003750`
- `0x180006f84`
- `0x18000a1c8`
- `0x18000a484`

## callees

- `0x180003a20`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003a54`
- `msvcrt!_vsnwprintf` at `0x180003a54`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // eax
  __int64 result; // rax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = a2 - 1;
    v5 = 0;
    v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v4 )
    {
      a1[v4] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v6 == v4 )
    {
      a1[v4] = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180003a20  mov     [rsp+arg_10], r8
0x180003a25  mov     qword ptr [rsp+Args], r9
0x180003a2a  push    rsi
0x180003a2b  push    rdi
0x180003a2c  sub     rsp, 38h
0x180003a30  mov     rsi, rcx
0x180003a33  test    rdx, rdx
0x180003a36  jz      short loc_180003A8B
0x180003a38  cmp     rdx, 7FFFFFFFh
0x180003a3f  ja      short loc_180003A84
0x180003a41  mov     [rsp+48h+var_18], rbx
0x180003a46  lea     r9, [rsp+48h+Args]; Args
0x180003a4b  lea     rbx, [rdx-1]
0x180003a4f  xor     edi, edi
0x180003a51  mov     rdx, rbx; BufferCount
0x180003a54  call    cs:__imp__vsnwprintf
0x180003a5a  test    eax, eax
0x180003a5c  js      short loc_180003A79
0x180003a5e  cdqe
0x180003a60  cmp     rax, rbx
0x180003a63  ja      short loc_180003A79
0x180003a65  jnz     short loc_180003A6B
0x180003a67  mov     [rsi+rbx*2], di
0x180003a6b  mov     rbx, [rsp+48h+var_18]
0x180003a70  mov     eax, edi
0x180003a72  add     rsp, 38h
0x180003a76  pop     rdi
0x180003a77  pop     rsi
0x180003a78  retn
0x180003a79  mov     [rsi+rbx*2], di
0x180003a7d  mov     edi, 8007007Ah
0x180003a82  jmp     short loc_180003A6B
0x180003a84  mov     eax, 80070057h
0x180003a89  jmp     short loc_180003A95
0x180003a8b  mov     eax, 80070057h
0x180003a90  test    rdx, rdx
0x180003a93  jz      short loc_180003A72
0x180003a95  xor     edi, edi
0x180003a97  mov     [rcx], di
0x180003a9a  jmp     short loc_180003A72
```
