# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003978`
- end: `0x1400039a3`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002f70`
- `0x140005388`

## callees

- `0x140003910`
- `0x140003978`

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
0x140003978  sub     rsp, 38h
0x14000397c  mov     rax, [rsp+38h]
0x140003981  xor     r8d, r8d; unsigned int
0x140003984  xor     edx, edx; void *
0x140003986  mov     [rsp+38h+var_10], rax; char *
0x14000398b  xor     ecx, ecx; this
0x14000398d  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003992  test    eax, eax
0x140003994  jle     short loc_14000399E
0x140003996  movzx   eax, ax
0x140003999  or      eax, 80070000h
0x14000399e  add     rsp, 38h
0x1400039a2  retn
```
