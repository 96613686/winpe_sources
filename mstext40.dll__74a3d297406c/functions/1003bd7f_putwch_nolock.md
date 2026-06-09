# __putwch_nolock

- ea: `0x1003bd7f`
- end: `0x1003bdc2`
- name: `__putwch_nolock`
- size: `67`
- prototype: `wint_t __cdecl(wchar_t Character)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100374c1`

## callees

- `0x1003bd7f`
- `0x1003cd3f`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x1003bdb0`
- `KERNEL32!WriteConsoleW` at `0x1003bdb0`

## pseudocode

```c
wint_t __cdecl _putwch_nolock(wchar_t Character)
{
  HANDLE v1; // eax
  DWORD NumberOfCharsWritten; // [esp+0h] [ebp-4h] BYREF

  v1 = _confh;
  if ( _confh == (HANDLE)-2 )
  {
    __initconout();
    v1 = _confh;
  }
  if ( v1 == (HANDLE)-1 || !WriteConsoleW(v1, &Character, 1u, &NumberOfCharsWritten, 0) )
    return -1;
  else
    return Character;
}

```

## disassembly

```asm
0x1003bd7f  push    ebp
0x1003bd80  mov     ebp, esp
0x1003bd82  push    ecx
0x1003bd83  mov     eax, __confh
0x1003bd88  cmp     eax, 0FFFFFFFEh
0x1003bd8b  jnz     short loc_1003BD97
0x1003bd8d  call    ___initconout
0x1003bd92  mov     eax, __confh
0x1003bd97  cmp     eax, 0FFFFFFFFh
0x1003bd9a  jnz     short loc_1003BDA3
0x1003bd9c  mov     eax, 0FFFFh
0x1003bda1  jmp     short loc_1003BDBE
0x1003bda3  push    0; lpReserved
0x1003bda5  lea     ecx, [ebp+NumberOfCharsWritten]
0x1003bda8  push    ecx; lpNumberOfCharsWritten
0x1003bda9  push    1; nNumberOfCharsToWrite
0x1003bdab  lea     ecx, [ebp+Character]
0x1003bdae  push    ecx; lpBuffer
0x1003bdaf  push    eax; hConsoleOutput
0x1003bdb0  call    ds:__imp__WriteConsoleW@20
0x1003bdb6  test    eax, eax
0x1003bdb8  jz      short loc_1003BD9C
0x1003bdba  mov     ax, [ebp+Character]
0x1003bdbe  mov     esp, ebp
0x1003bdc0  pop     ebp
0x1003bdc1  retn
```
