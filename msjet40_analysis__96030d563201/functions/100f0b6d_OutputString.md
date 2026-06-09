# _OutputString

- ea: `0x100f0b6d`
- end: `0x100f0bee`
- name: `_OutputString`
- size: `129`
- prototype: `int __cdecl(char *Format, char ArgList)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100f001a`
- `0x100f04df`

## callees

- `0x100f0b6d`
- `0x10122f60`
- `0x10123a87`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100f0bc1`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100f0bc1`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100f0bda`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100f0bda`

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
0x100f0b6d  mov     edi, edi
0x100f0b6f  push    ebp
0x100f0b70  mov     ebp, esp
0x100f0b72  sub     esp, 404h
0x100f0b78  mov     eax, ___security_cookie
0x100f0b7d  xor     eax, ebp
0x100f0b7f  mov     [ebp+var_4], eax
0x100f0b82  push    esi
0x100f0b83  lea     eax, [ebp+ArgList]
0x100f0b86  mov     esi, 3FFh
0x100f0b8b  push    eax; ArgList
0x100f0b8c  push    [ebp+Format]; Format
0x100f0b8f  lea     eax, [ebp+Buffer]
0x100f0b95  push    esi; BufferCount
0x100f0b96  push    eax; Buffer
0x100f0b97  call    __vsnprintf
0x100f0b9c  add     esp, 10h
0x100f0b9f  test    eax, eax
0x100f0ba1  js      short loc_100F0BA9
0x100f0ba3  cmp     eax, esi
0x100f0ba5  ja      short loc_100F0BA9
0x100f0ba7  jnz     short loc_100F0BAD
0x100f0ba9  mov     [ebp+var_5], 0
0x100f0bad  mov     eax, Stream
0x100f0bb2  pop     esi
0x100f0bb3  test    eax, eax
0x100f0bb5  jnz     short loc_100F0BD2
0x100f0bb7  push    offset aA; "a"
0x100f0bbc  push    offset FileName; "showplan.out"
0x100f0bc1  call    ds:__imp__fopen
0x100f0bc7  mov     Stream, eax
0x100f0bcc  pop     ecx
0x100f0bcd  pop     ecx
0x100f0bce  test    eax, eax
0x100f0bd0  jz      short loc_100F0BE2
0x100f0bd2  push    eax
0x100f0bd3  lea     eax, [ebp+Buffer]
0x100f0bd9  push    eax
0x100f0bda  call    ds:__imp___o_fputs
0x100f0be0  pop     ecx
0x100f0be1  pop     ecx
0x100f0be2  mov     ecx, [ebp+var_4]
0x100f0be5  xor     ecx, ebp; StackCookie
0x100f0be7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100f0bec  leave
0x100f0bed  retn
```
