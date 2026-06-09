# _putwch_nolock

- ea: `0x18001e648`
- end: `0x18001e6ac`
- name: `_putwch_nolock`
- size: `100`
- prototype: `wint_t __cdecl(wchar_t Character)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e560`
- `0x18001e610`
- `0x180020434`
- `0x180021a24`
- `0x180023314`
- `0x180045130`
- `0x180045188`
- `0x180045280`
- `0x180045e80`
- `0x1800472a0`

## callees

- `0x18001e648`
- `0x180023b08`

## import_xrefs

- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x18001e691`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x18001e691`

## pseudocode

```c
wint_t __cdecl putwch_nolock(wchar_t Character)
{
  HANDLE v1; // rcx
  wint_t Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD NumberOfCharsWritten; // [rsp+48h] [rbp+10h] BYREF

  Buffer = Character;
  v1 = confh;
  NumberOfCharsWritten = 0;
  if ( confh == (HANDLE)-2LL )
  {
    _initconout();
    v1 = confh;
  }
  if ( v1 == (HANDLE)-1LL || !WriteConsoleW(v1, &Buffer, 1u, &NumberOfCharsWritten, 0) )
    return -1;
  else
    return Buffer;
}

```

## disassembly

```asm
0x18001e648  mov     [rsp+Buffer], cx
0x18001e64d  sub     rsp, 38h
0x18001e651  mov     rcx, cs:_confh
0x18001e658  mov     [rsp+38h+NumberOfCharsWritten], 0
0x18001e660  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18001e664  jnz     short loc_18001E672
0x18001e666  call    __initconout
0x18001e66b  mov     rcx, cs:_confh; hConsoleOutput
0x18001e672  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e676  jz      short loc_18001E6A2
0x18001e678  lea     r9, [rsp+38h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x18001e67d  mov     [rsp+38h+lpReserved], 0; lpReserved
0x18001e686  mov     r8d, 1; nNumberOfCharsToWrite
0x18001e68c  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18001e691  call    cs:__imp_WriteConsoleW
0x18001e697  test    eax, eax
0x18001e699  jz      short loc_18001E6A2
0x18001e69b  movzx   eax, [rsp+38h+Buffer]
0x18001e6a0  jmp     short loc_18001E6A7
0x18001e6a2  mov     eax, 0FFFFh
0x18001e6a7  add     rsp, 38h
0x18001e6ab  retn
```
