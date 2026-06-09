# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800024a4`
- end: `0x1800024cf`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ce0`
- `0x180004e48`
- `0x180008c04`

## callees

- `0x1800024a4`
- `0x180002720`

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
0x1800024a4  sub     rsp, 38h
0x1800024a8  mov     rax, [rsp+38h]
0x1800024ad  xor     r8d, r8d; unsigned int
0x1800024b0  xor     edx, edx; void *
0x1800024b2  mov     [rsp+38h+var_10], rax; char *
0x1800024b7  xor     ecx, ecx; this
0x1800024b9  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800024be  test    eax, eax
0x1800024c0  jle     short loc_1800024CA
0x1800024c2  movzx   eax, ax
0x1800024c5  or      eax, 80070000h
0x1800024ca  add     rsp, 38h
0x1800024ce  retn
```
