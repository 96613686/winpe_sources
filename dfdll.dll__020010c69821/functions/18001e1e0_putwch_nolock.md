# _putwch_nolock

- ea: `0x18001e1e0`
- end: `0x18001e239`
- name: `_putwch_nolock`
- size: `89`
- prototype: `wint_t __cdecl(wchar_t Character)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d7b0`

## callees

- `0x18001e1e0`
- `0x18001e7d0`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x18001e225`
- `KERNEL32!WriteConsoleW` at `0x18001e225`

## pseudocode

```c
wint_t __cdecl putwch_nolock(wchar_t Character)
{
  HANDLE v1; // rcx
  wint_t Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD NumberOfCharsWritten; // [rsp+48h] [rbp+10h] BYREF

  Buffer = Character;
  v1 = _dcrt_lowio_console_output_handle;
  if ( _dcrt_lowio_console_output_handle == (HANDLE)-2LL )
  {
    _dcrt_lowio_initialize_console_output();
    v1 = _dcrt_lowio_console_output_handle;
  }
  if ( v1 == (HANDLE)-1LL || !WriteConsoleW(v1, &Buffer, 1u, &NumberOfCharsWritten, 0) )
    return -1;
  else
    return Buffer;
}

```

## disassembly

```asm
0x18001e1e0  mov     [rsp+Buffer], cx
0x18001e1e5  sub     rsp, 38h
0x18001e1e9  mov     rcx, cs:__dcrt_lowio_console_output_handle
0x18001e1f0  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18001e1f4  jnz     short loc_18001E202
0x18001e1f6  call    __dcrt_lowio_initialize_console_output
0x18001e1fb  mov     rcx, cs:__dcrt_lowio_console_output_handle; hConsoleOutput
0x18001e202  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e206  jnz     short loc_18001E20F
0x18001e208  mov     eax, 0FFFFh
0x18001e20d  jmp     short loc_18001E234
0x18001e20f  and     [rsp+38h+var_18], 0
0x18001e215  lea     r9, [rsp+38h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x18001e21a  mov     r8d, 1; nNumberOfCharsToWrite
0x18001e220  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18001e225  call    cs:__imp_WriteConsoleW
0x18001e22b  test    eax, eax
0x18001e22d  jz      short loc_18001E208
0x18001e22f  movzx   eax, [rsp+38h+Buffer]
0x18001e234  add     rsp, 38h
0x18001e238  retn
```
