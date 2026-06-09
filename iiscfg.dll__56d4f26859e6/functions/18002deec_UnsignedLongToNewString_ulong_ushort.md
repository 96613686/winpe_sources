# UnsignedLongToNewString(ulong,ushort * *)

- ea: `0x18002deec`
- end: `0x18002df95`
- name: `?UnsignedLongToNewString@@YAJKPEAPEAG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002c604`
- `0x18002d934`

## callees

- `0x18002deec`
- `0x18002e110`

## import_xrefs

- `msvcrt!_ultow` at `0x18002df1b`
- `msvcrt!_ultow` at `0x18002df1b`
- `msvcrt!wcscpy_s` at `0x18002df6b`
- `msvcrt!wcscpy_s` at `0x18002df6b`
- `ole32!CoTaskMemAlloc` at `0x18002df4b`
- `ole32!CoTaskMemAlloc` at `0x18002df4b`

## pseudocode

```c
__int64 __fastcall UnsignedLongToNewString(unsigned int a1, unsigned __int16 **a2)
{
  __int64 v3; // rax
  rsize_t v4; // rbx
  unsigned __int16 *v5; // rax
  wchar_t Buffer[40]; // [rsp+20h] [rbp-68h] BYREF

  _ultow(a1, Buffer, 10);
  v3 = -1;
  do
    ++v3;
  while ( Buffer[v3] );
  v4 = v3 + 1;
  v5 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v3 + 1, 2u));
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  wcscpy_s(v5, v4, Buffer);
  return 0;
}

```

## disassembly

```asm
0x18002deec  mov     [rsp+arg_10], rbx
0x18002def1  mov     [rsp+arg_18], rsi
0x18002def6  push    rdi
0x18002def7  sub     rsp, 80h
0x18002defe  mov     rax, cs:__security_cookie
0x18002df05  xor     rax, rsp
0x18002df08  mov     [rsp+88h+var_18], rax
0x18002df0d  mov     rdi, rdx
0x18002df10  mov     r8d, 0Ah; Radix
0x18002df16  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18002df1b  call    cs:__imp__ultow
0x18002df21  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002df25  lea     rcx, [rsp+88h+Buffer]
0x18002df2a  mov     rax, r8
0x18002df2d  xor     esi, esi
0x18002df2f  inc     rax
0x18002df32  cmp     [rcx+rax*2], si
0x18002df36  jnz     short loc_18002DF2F
0x18002df38  lea     rbx, [rax+1]
0x18002df3c  mov     eax, 2
0x18002df41  mul     rbx
0x18002df44  cmovb   rax, r8
0x18002df48  mov     rcx, rax; cb
0x18002df4b  call    cs:__imp_CoTaskMemAlloc
0x18002df51  mov     [rdi], rax
0x18002df54  test    rax, rax
0x18002df57  jnz     short loc_18002DF60
0x18002df59  mov     eax, 8007000Eh
0x18002df5e  jmp     short loc_18002DF73
0x18002df60  lea     r8, [rsp+88h+Buffer]; Source
0x18002df65  mov     rdx, rbx; SizeInWords
0x18002df68  mov     rcx, rax; Destination
0x18002df6b  call    cs:__imp_wcscpy_s
0x18002df71  xor     eax, eax
0x18002df73  mov     rcx, [rsp+88h+var_18]
0x18002df78  xor     rcx, rsp; StackCookie
0x18002df7b  call    __security_check_cookie
0x18002df80  lea     r11, [rsp+88h+var_8]
0x18002df88  mov     rbx, [r11+20h]
0x18002df8c  mov     rsi, [r11+28h]
0x18002df90  mov     rsp, r11
0x18002df93  pop     rdi
0x18002df94  retn
```
