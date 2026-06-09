# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004cd0`
- end: `0x180004cfc`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `44`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800066b8`
- `0x180008698`

## callees

- `0x180004cd0`
- `0x180004f4c`

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
0x180004cd0  sub     rsp, 38h
0x180004cd4  mov     rax, [rsp+38h]
0x180004cd9  xor     r8d, r8d; unsigned int
0x180004cdc  xor     edx, edx; void *
0x180004cde  mov     [rsp+38h+var_10], rax; char *
0x180004ce3  xor     ecx, ecx; this
0x180004ce5  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180004cea  test    eax, eax
0x180004cec  jle     short loc_180004CF6
0x180004cee  movzx   eax, ax
0x180004cf1  or      eax, 80070000h
0x180004cf6  add     rsp, 38h
0x180004cfa  retn
```
