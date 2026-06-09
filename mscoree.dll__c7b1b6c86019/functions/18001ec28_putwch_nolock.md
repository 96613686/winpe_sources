# _putwch_nolock

- ea: `0x18001ec28`
- end: `0x18001ec8c`
- name: `_putwch_nolock`
- size: `100`
- prototype: `wint_t __cdecl(wchar_t Character)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b808`

## callees

- `0x18001ec28`
- `0x18001fdb0`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x18001ec71`
- `KERNEL32!WriteConsoleW` at `0x18001ec71`

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
0x18001ec28  mov     [rsp+Buffer], cx
0x18001ec2d  sub     rsp, 38h
0x18001ec31  mov     rcx, cs:_confh
0x18001ec38  mov     [rsp+38h+NumberOfCharsWritten], 0
0x18001ec40  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18001ec44  jnz     short loc_18001EC52
0x18001ec46  call    __initconout
0x18001ec4b  mov     rcx, cs:_confh; hConsoleOutput
0x18001ec52  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ec56  jz      short loc_18001EC82
0x18001ec58  lea     r9, [rsp+38h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x18001ec5d  mov     [rsp+38h+lpReserved], 0; lpReserved
0x18001ec66  mov     r8d, 1; nNumberOfCharsToWrite
0x18001ec6c  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18001ec71  call    cs:__imp_WriteConsoleW
0x18001ec77  test    eax, eax
0x18001ec79  jz      short loc_18001EC82
0x18001ec7b  movzx   eax, [rsp+38h+Buffer]
0x18001ec80  jmp     short loc_18001EC87
0x18001ec82  mov     eax, 0FFFFh
0x18001ec87  add     rsp, 38h
0x18001ec8b  retn
```
