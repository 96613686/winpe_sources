# RasDiagTrace(char const *,...)

- ea: `0x18000ca8c`
- end: `0x18000cb26`
- name: `?RasDiagTrace@@YAXPEBDZZ`
- size: `154`
- prototype: `void(const char *Format, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e60`
- `0x18000ad60`
- `0x18000baec`
- `0x18000c000`
- `0x18000c164`
- `0x18000c310`
- `0x18000c7f0`
- `0x18000c8cc`

## callees

- `0x18000ca8c`
- `0x18000df10`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000cadd`
- `msvcrt!_vsnprintf` at `0x18000cadd`
- `KERNEL32!OutputDebugStringA` at `0x18000cb01`
- `KERNEL32!OutputDebugStringA` at `0x18000cb01`

## pseudocode

```c
void RasDiagTrace(const char *Format, ...)
{
  const char *v1; // r8
  char Buffer[272]; // [rsp+30h] [rbp-128h] BYREF
  va_list va; // [rsp+168h] [rbp+10h] BYREF

  va_start(va, Format);
  v1 = &byte_180013F17;
  if ( Format )
    v1 = Format;
  if ( (unsigned int)_vsnprintf(Buffer, 0x104u, v1, va) >= 0x104 )
    Buffer[260] = 0;
  OutputDebugStringA(Buffer);
}

```

## disassembly

```asm
0x18000ca8c  mov     r11, rsp
0x18000ca8f  mov     [r11+8], rcx
0x18000ca93  mov     [r11+10h], rdx
0x18000ca97  mov     [r11+18h], r8
0x18000ca9b  mov     [r11+20h], r9
0x18000ca9f  sub     rsp, 158h
0x18000caa6  mov     rax, cs:__security_cookie
0x18000caad  xor     rax, rsp
0x18000cab0  mov     [rsp+158h+var_18], rax
0x18000cab8  test    rcx, rcx
0x18000cabb  mov     [rsp+158h+var_138], 0
0x18000cac4  lea     r8, byte_180013F17
0x18000cacb  mov     edx, 104h; BufferCount
0x18000cad0  cmovnz  r8, rcx; Format
0x18000cad4  lea     r9, [r11+10h]; ArgList
0x18000cad8  lea     rcx, [rsp+158h+Buffer]; Buffer
0x18000cadd  call    cs:__imp__vsnprintf
0x18000cae4  nop     dword ptr [rax+rax+00h]
0x18000cae9  test    eax, eax
0x18000caeb  js      short loc_18000CAF4
0x18000caed  cmp     eax, 104h
0x18000caf2  jb      short loc_18000CAFC
0x18000caf4  mov     [rsp+158h+var_24], 0
0x18000cafc  lea     rcx, [rsp+158h+Buffer]; lpOutputString
0x18000cb01  call    cs:__imp_OutputDebugStringA
0x18000cb08  nop     dword ptr [rax+rax+00h]
0x18000cb0d  mov     rcx, [rsp+158h+var_18]
0x18000cb15  xor     rcx, rsp; StackCookie
0x18000cb18  call    __security_check_cookie
0x18000cb1d  add     rsp, 158h
0x18000cb24  retn
```
