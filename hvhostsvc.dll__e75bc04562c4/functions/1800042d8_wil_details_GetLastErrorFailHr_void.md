# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800042d8`
- end: `0x180004303`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a38`
- `0x180006088`
- `0x180008c58`

## callees

- `0x180004270`
- `0x1800042d8`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this, __int64 a2, __int64 a3, const char *a4)
{
  signed int result; // eax
  const char *v5; // [rsp+20h] [rbp-18h]
  const char *retaddr; // [rsp+38h] [rbp+0h]

  result = wil::details::GetLastErrorFail(0, 0, 0, a4, v5, retaddr);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800042d8  sub     rsp, 38h
0x1800042dc  mov     rax, [rsp+38h]
0x1800042e1  xor     r8d, r8d; unsigned int
0x1800042e4  xor     edx, edx; void *
0x1800042e6  mov     [rsp+38h+var_10], rax; char *
0x1800042eb  xor     ecx, ecx; this
0x1800042ed  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800042f2  test    eax, eax
0x1800042f4  jle     short loc_1800042FE
0x1800042f6  movzx   eax, ax
0x1800042f9  or      eax, 80070000h
0x1800042fe  add     rsp, 38h
0x180004302  retn
```
