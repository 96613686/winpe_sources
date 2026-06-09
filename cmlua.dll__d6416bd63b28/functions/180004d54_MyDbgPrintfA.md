# MyDbgPrintfA

- ea: `0x180004d54`
- end: `0x180004e15`
- name: `MyDbgPrintfA`
- size: `193`
- prototype: `__int64(_QWORD, const char *, ...)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ec0`
- `0x1800035ec`
- `0x180004630`
- `0x180004aac`
- `0x180004ffc`
- `0x18000510c`

## callees

- `0x180004c60`
- `0x180004d54`
- `0x1800054b0`
- `0x180006010`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180004da4`
- `msvcrt!_vsnprintf` at `0x180004da4`

## pseudocode

```c
unsigned int MyDbgPrintfA(unsigned int a1, const char *a2, ...)
{
  const char *v3; // r8
  unsigned int result; // eax
  char Buffer[512]; // [rsp+30h] [rbp-218h] BYREF
  va_list va; // [rsp+260h] [rbp+18h] BYREF

  va_start(va, a2);
  v3 = (const char *)&dword_180009F8C;
  if ( a2 )
    v3 = a2;
  result = _vsnprintf(Buffer, 0x1FFu, v3, va);
  if ( result >= 0x200 )
  {
    Buffer[0] = 0;
  }
  else if ( result != 511 )
  {
    goto LABEL_8;
  }
  Buffer[511] = 0;
LABEL_8:
  if ( a1 != -1 )
  {
    if ( g_pTracePrintfEx )
    {
      DuplicatePercentileSymbol(Buffer, 512);
      return ((__int64 (__fastcall *)(_QWORD, __int64, char *))g_pTracePrintfEx)(a1, 12, Buffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004d54  mov     r11, rsp
0x180004d57  mov     [r11+10h], rdx
0x180004d5b  mov     [r11+18h], r8
0x180004d5f  mov     [r11+20h], r9
0x180004d63  push    rdi
0x180004d64  sub     rsp, 240h
0x180004d6b  mov     rax, cs:__security_cookie
0x180004d72  xor     rax, rsp
0x180004d75  mov     [rsp+248h+var_18], rax
0x180004d7d  test    rdx, rdx
0x180004d80  mov     [rsp+248h+var_228], 0
0x180004d89  mov     edi, ecx
0x180004d8b  lea     r8, dword_180009F8C
0x180004d92  cmovnz  r8, rdx; Format
0x180004d96  lea     r9, [r11+18h]; ArgList
0x180004d9a  mov     edx, 1FFh; BufferCount
0x180004d9f  lea     rcx, [rsp+248h+Buffer]; Buffer
0x180004da4  call    cs:__imp__vsnprintf
0x180004daa  test    eax, eax
0x180004dac  js      short loc_180004DB9
0x180004dae  cmp     eax, 1FFh
0x180004db3  ja      short loc_180004DB9
0x180004db5  jnz     short loc_180004DC6
0x180004db7  jmp     short loc_180004DBE
0x180004db9  mov     [rsp+248h+Buffer], 0
0x180004dbe  mov     [rsp+248h+var_19], 0
0x180004dc6  cmp     edi, 0FFFFFFFFh
0x180004dc9  jz      short loc_180004DFC
0x180004dcb  cmp     cs:g_pTracePrintfEx, 0
0x180004dd3  jz      short loc_180004DFC
0x180004dd5  mov     edx, 200h
0x180004dda  lea     rcx, [rsp+248h+Buffer]
0x180004ddf  call    DuplicatePercentileSymbol
0x180004de4  mov     rax, cs:g_pTracePrintfEx
0x180004deb  lea     r8, [rsp+248h+Buffer]
0x180004df0  mov     edx, 0Ch
0x180004df5  mov     ecx, edi
0x180004df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dfc  mov     rcx, [rsp+248h+var_18]
0x180004e04  xor     rcx, rsp; StackCookie
0x180004e07  call    __security_check_cookie
0x180004e0c  add     rsp, 240h
0x180004e13  pop     rdi
0x180004e14  retn
```
