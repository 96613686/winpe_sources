# authunix_create_default

- ea: `0x14000b030`
- end: `0x14000b0bf`
- name: `authunix_create_default`
- size: `143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001b5c`

## callees

- `0x14000add4`
- `0x14000b030`
- `0x140018350`

## import_xrefs

- `msvcrt!wcstombs` at `0x14000b073`
- `msvcrt!wcstombs` at `0x14000b073`
- `WS2_32!GetHostNameW` at `0x14000b056`
- `WS2_32!GetHostNameW` at `0x14000b056`

## pseudocode

```c
_OWORD *authunix_create_default()
{
  __int64 v0; // r9
  _BYTE v2[64]; // [rsp+30h] [rbp-358h] BYREF
  char Dest[256]; // [rsp+70h] [rbp-318h] BYREF
  WCHAR name[256]; // [rsp+170h] [rbp-218h] BYREF

  if ( GetHostNameW(name, 255) || wcstombs(Dest, name, 0xFFu) == -1 )
    return 0;
  Dest[255] = 0;
  return authunix_create((__int64)Dest, -2, 0xFFFFFFFE, v0, (__int64)v2);
}

```

## disassembly

```asm
0x14000b030  sub     rsp, 388h
0x14000b037  mov     rax, cs:__security_cookie
0x14000b03e  xor     rax, rsp
0x14000b041  mov     [rsp+388h+var_18], rax
0x14000b049  mov     edx, 0FFh; namelen
0x14000b04e  lea     rcx, [rsp+388h+name]; name
0x14000b056  call    cs:__imp_GetHostNameW
0x14000b05c  test    eax, eax
0x14000b05e  jnz     short loc_14000B0A5
0x14000b060  mov     r8d, 0FFh; MaxCount
0x14000b066  lea     rdx, [rsp+388h+name]; Source
0x14000b06e  lea     rcx, [rsp+388h+Dest]; Dest
0x14000b073  call    cs:__imp_wcstombs
0x14000b079  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b07d  jz      short loc_14000B0A5
0x14000b07f  mov     edx, 0FFFFFFFEh
0x14000b084  mov     [rsp+388h+var_219], 0
0x14000b08c  lea     rax, [rsp+388h+var_358]
0x14000b091  mov     r8d, edx
0x14000b094  lea     rcx, [rsp+388h+Dest]
0x14000b099  mov     [rsp+388h+var_368], rax
0x14000b09e  call    authunix_create
0x14000b0a3  jmp     short loc_14000B0A7
0x14000b0a5  xor     eax, eax
0x14000b0a7  mov     rcx, [rsp+388h+var_18]
0x14000b0af  xor     rcx, rsp; StackCookie
0x14000b0b2  call    __security_check_cookie
0x14000b0b7  add     rsp, 388h
0x14000b0be  retn
```
