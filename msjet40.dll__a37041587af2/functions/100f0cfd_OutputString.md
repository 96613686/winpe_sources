# _OutputString

- ea: `0x100f0cfd`
- end: `0x100f0d7e`
- name: `_OutputString`
- size: `129`
- prototype: `int __cdecl(char *Format, char ArgList)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100f01aa`
- `0x100f066f`

## callees

- `0x100f0cfd`
- `0x10123110`
- `0x10123c37`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100f0d51`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100f0d51`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100f0d6a`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100f0d6a`

## pseudocode

```c
FILE *OutputString(char *Format, ...)
{
  FILE *result; // eax
  char Buffer[1024]; // [esp+4h] [ebp-404h] BYREF
  va_list va; // [esp+414h] [ebp+Ch] BYREF

  va_start(va, Format);
  if ( (unsigned int)_vsnprintf(Buffer, 0x3FFu, Format, va) > 0x3FE )
    Buffer[1023] = 0;
  result = Stream;
  if ( Stream )
    return (FILE *)__o_fputs(Buffer, result);
  result = _fopen("showplan.out", "a");
  Stream = result;
  if ( result )
    return (FILE *)__o_fputs(Buffer, result);
  return result;
}

```

## disassembly

```asm
0x100f0cfd  mov     edi, edi
0x100f0cff  push    ebp
0x100f0d00  mov     ebp, esp
0x100f0d02  sub     esp, 404h
0x100f0d08  mov     eax, ___security_cookie
0x100f0d0d  xor     eax, ebp
0x100f0d0f  mov     [ebp+var_4], eax
0x100f0d12  push    esi
0x100f0d13  lea     eax, [ebp+ArgList]
0x100f0d16  mov     esi, 3FFh
0x100f0d1b  push    eax; ArgList
0x100f0d1c  push    [ebp+Format]; Format
0x100f0d1f  lea     eax, [ebp+Buffer]
0x100f0d25  push    esi; BufferCount
0x100f0d26  push    eax; Buffer
0x100f0d27  call    __vsnprintf
0x100f0d2c  add     esp, 10h
0x100f0d2f  test    eax, eax
0x100f0d31  js      short loc_100F0D39
0x100f0d33  cmp     eax, esi
0x100f0d35  ja      short loc_100F0D39
0x100f0d37  jnz     short loc_100F0D3D
0x100f0d39  mov     [ebp+var_5], 0
0x100f0d3d  mov     eax, Stream
0x100f0d42  pop     esi
0x100f0d43  test    eax, eax
0x100f0d45  jnz     short loc_100F0D62
0x100f0d47  push    offset aA; "a"
0x100f0d4c  push    offset FileName; "showplan.out"
0x100f0d51  call    ds:__imp__fopen
0x100f0d57  mov     Stream, eax
0x100f0d5c  pop     ecx
0x100f0d5d  pop     ecx
0x100f0d5e  test    eax, eax
0x100f0d60  jz      short loc_100F0D72
0x100f0d62  push    eax
0x100f0d63  lea     eax, [ebp+Buffer]
0x100f0d69  push    eax
0x100f0d6a  call    ds:__imp___o_fputs
0x100f0d70  pop     ecx
0x100f0d71  pop     ecx
0x100f0d72  mov     ecx, [ebp+var_4]
0x100f0d75  xor     ecx, ebp; StackCookie
0x100f0d77  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100f0d7c  leave
0x100f0d7d  retn
```
