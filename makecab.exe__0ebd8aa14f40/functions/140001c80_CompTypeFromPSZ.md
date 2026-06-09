# CompTypeFromPSZ

- ea: `0x140001c80`
- end: `0x140001cea`
- name: `CompTypeFromPSZ`
- size: `106`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002790`
- `0x1400084d8`

## callees

- `0x140001c80`
- `0x140008620`

## import_xrefs

- `msvcrt!_stricmp` at `0x140001c97`
- `msvcrt!_stricmp` at `0x140001cb2`
- `msvcrt!_stricmp` at `0x140001c97`
- `msvcrt!_stricmp` at `0x140001cb2`

## string_xrefs

- `0x140001ccd`: `Invalid Compression Type: %1`

## pseudocode

```c
__int64 __fastcall CompTypeFromPSZ(char *String1, __int64 a2)
{
  if ( !_stricmp(String1, "MSZIP") )
    return 1;
  if ( !_stricmp(String1, "LZX") )
    return 3;
  ErrSet(a2, "Invalid Compression Type: %1", "%s", String1);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140001c80  mov     [rsp+arg_0], rbx
0x140001c85  push    rdi
0x140001c86  sub     rsp, 20h
0x140001c8a  mov     rdi, rdx
0x140001c8d  mov     rbx, rcx
0x140001c90  lea     rdx, aMszip; "MSZIP"
0x140001c97  call    cs:__imp__stricmp
0x140001c9d  test    eax, eax
0x140001c9f  jnz     short loc_140001CA8
0x140001ca1  mov     eax, 1
0x140001ca6  jmp     short loc_140001CDF
0x140001ca8  lea     rdx, aLzx; "LZX"
0x140001caf  mov     rcx, rbx; String1
0x140001cb2  call    cs:__imp__stricmp
0x140001cb8  test    eax, eax
0x140001cba  jnz     short loc_140001CC3
0x140001cbc  mov     eax, 3
0x140001cc1  jmp     short loc_140001CDF
0x140001cc3  mov     r9, rbx
0x140001cc6  lea     r8, aS_4; "%s"
0x140001ccd  lea     rdx, aInvalidCompres; "Invalid Compression Type: %1"
0x140001cd4  mov     rcx, rdi
0x140001cd7  call    ErrSet
0x140001cdc  or      eax, 0FFFFFFFFh
0x140001cdf  mov     rbx, [rsp+28h+arg_0]
0x140001ce4  add     rsp, 20h
0x140001ce8  pop     rdi
0x140001ce9  retn
```
