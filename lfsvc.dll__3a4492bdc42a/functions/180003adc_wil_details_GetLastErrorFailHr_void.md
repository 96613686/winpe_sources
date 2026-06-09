# wil::details::GetLastErrorFailHr(void)

- ea: `0x180003adc`
- end: `0x180003b13`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `55`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006308`
- `0x180006498`
- `0x180009f9c`

## callees

- `0x180003adc`
- `0x180003d84`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  const char *retaddr; // [rsp+38h] [rbp+0h]

  result = wil::details::GetLastErrorFail(0, 0, 0, 0, 0, retaddr);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003adc  sub     rsp, 38h
0x180003ae0  mov     rax, [rsp+38h]
0x180003ae5  xor     r9d, r9d; char *
0x180003ae8  mov     [rsp+38h+var_10], rax; char *
0x180003aed  xor     r8d, r8d; unsigned int
0x180003af0  xor     edx, edx; void *
0x180003af2  mov     [rsp+38h+var_18], 0; char *
0x180003afb  xor     ecx, ecx; this
0x180003afd  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003b02  test    eax, eax
0x180003b04  jle     short loc_180003B0E
0x180003b06  movzx   eax, ax
0x180003b09  or      eax, 80070000h
0x180003b0e  add     rsp, 38h
0x180003b12  retn
```
