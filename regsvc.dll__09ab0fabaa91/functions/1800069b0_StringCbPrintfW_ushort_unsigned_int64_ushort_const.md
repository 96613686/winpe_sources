# StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800069b0`
- end: `0x180006a3d`
- name: `?StringCbPrintfW@@YAJPEAG_KPEBGZZ`
- size: `141`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b40`
- `0x180005f20`
- `0x180010430`
- `0x180016260`

## callees

- `0x1800069b0`
- `0x180008334`

## pseudocode

```c
__int64 StringCbPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  unsigned __int64 v6; // rdi
  unsigned int v7; // ebx
  int v8; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  v3 = a2 >> 1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
    return result;
  }
  v6 = v3 - 1;
  v7 = 0;
  v8 = vsnwprintf(a1, v3 - 1, a3, Args);
  if ( v8 < 0 || v8 > v6 )
  {
    a1[v6] = 0;
    return (unsigned int)-2147024774;
  }
  else if ( v8 == v6 )
  {
    a1[v6] = 0;
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800069b0  mov     [rsp+arg_10], r8
0x1800069b5  mov     qword ptr [rsp+Args], r9
0x1800069ba  push    rbx
0x1800069bb  push    rsi
0x1800069bc  sub     rsp, 38h
0x1800069c0  shr     rdx, 1
0x1800069c3  mov     rsi, rcx
0x1800069c6  jz      short loc_180006A27
0x1800069c8  cmp     rdx, 7FFFFFFFh
0x1800069cf  jbe     short loc_1800069D8
0x1800069d1  mov     eax, 80070057h
0x1800069d6  jmp     short loc_180006A31
0x1800069d8  mov     [rsp+48h+var_18], rdi
0x1800069dd  lea     r9, [rsp+48h+Args]; Args
0x1800069e2  lea     rdi, [rdx-1]
0x1800069e6  xor     ebx, ebx
0x1800069e8  mov     rdx, rdi; BufferCount
0x1800069eb  call    _vsnwprintf
0x1800069f0  test    eax, eax
0x1800069f2  js      short loc_180006A10
0x1800069f4  movsxd  rcx, eax
0x1800069f7  cmp     rcx, rdi
0x1800069fa  ja      short loc_180006A10
0x1800069fc  jnz     short loc_180006A19
0x1800069fe  mov     [rsi+rdi*2], bx
0x180006a02  mov     eax, ebx
0x180006a04  mov     rdi, [rsp+48h+var_18]
0x180006a09  add     rsp, 38h
0x180006a0d  pop     rsi
0x180006a0e  pop     rbx
0x180006a0f  retn
0x180006a10  mov     [rsi+rdi*2], bx
0x180006a14  mov     ebx, 8007007Ah
0x180006a19  mov     rdi, [rsp+48h+var_18]
0x180006a1e  mov     eax, ebx
0x180006a20  add     rsp, 38h
0x180006a24  pop     rsi
0x180006a25  pop     rbx
0x180006a26  retn
0x180006a27  mov     eax, 80070057h
0x180006a2c  test    rdx, rdx
0x180006a2f  jz      short loc_180006A36
0x180006a31  xor     ebx, ebx
0x180006a33  mov     [rcx], bx
0x180006a36  add     rsp, 38h
0x180006a3a  pop     rsi
0x180006a3b  pop     rbx
0x180006a3c  retn
```
