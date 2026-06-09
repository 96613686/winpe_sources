# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002d90`
- end: `0x180002e22`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `146`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025c8`
- `0x180002770`
- `0x1800066b8`

## callees

- `0x180002d90`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002dc4`
- `msvcrt!_vsnwprintf` at `0x180002dc4`

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
    if ( v6 < 0 )
      goto LABEL_9;
    if ( v6 != v4 )
    {
      if ( v6 <= v4 )
        return v5;
LABEL_9:
      a1[v4] = 0;
      return (unsigned int)-2147024774;
    }
    a1[v4] = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp+arg_10], r8
0x180002d95  mov     qword ptr [rsp+Args], r9
0x180002d9a  push    rsi
0x180002d9b  push    rdi
0x180002d9c  sub     rsp, 38h
0x180002da0  mov     rsi, rcx
0x180002da3  test    rdx, rdx
0x180002da6  jz      short loc_180002E11
0x180002da8  cmp     rdx, 7FFFFFFFh
0x180002daf  ja      short loc_180002DFF
0x180002db1  mov     [rsp+48h+var_18], rbx
0x180002db6  lea     r9, [rsp+48h+Args]; Args
0x180002dbb  lea     rbx, [rdx-1]
0x180002dbf  xor     edi, edi
0x180002dc1  mov     rdx, rbx; BufferCount
0x180002dc4  call    cs:__imp__vsnwprintf
0x180002dcb  nop     dword ptr [rax+rax+00h]
0x180002dd0  test    eax, eax
0x180002dd2  js      short loc_180002E06
0x180002dd4  cdqe
0x180002dd6  cmp     rax, rbx
0x180002dd9  jz      short loc_180002DEC
0x180002ddb  ja      short loc_180002E06
0x180002ddd  mov     rbx, [rsp+48h+var_18]
0x180002de2  mov     eax, edi
0x180002de4  add     rsp, 38h
0x180002de8  pop     rdi
0x180002de9  pop     rsi
0x180002dea  retn
0x180002dec  mov     [rsi+rbx*2], di
0x180002df0  mov     eax, edi
0x180002df2  mov     rbx, [rsp+48h+var_18]
0x180002df7  add     rsp, 38h
0x180002dfb  pop     rdi
0x180002dfc  pop     rsi
0x180002dfd  retn
0x180002dff  mov     eax, 80070057h
0x180002e04  jmp     short loc_180002E1B
0x180002e06  mov     [rsi+rbx*2], di
0x180002e0a  mov     edi, 8007007Ah
0x180002e0f  jmp     short loc_180002DDD
0x180002e11  mov     eax, 80070057h
0x180002e16  test    rdx, rdx
0x180002e19  jz      short loc_180002DE4
0x180002e1b  xor     edi, edi
0x180002e1d  mov     [rcx], di
0x180002e20  jmp     short loc_180002DE4
```
