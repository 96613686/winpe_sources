# WdmlibRtlInitUnicodeStringEx

- ea: `0x140006430`
- end: `0x140006476`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dfdc`
- `0x14000e1c4`
- `0x14000e330`
- `0x14000e658`
- `0x14000e6b8`
- `0x14000e9f4`
- `0x14000ea9c`

## callees

- `0x140006430`

## pseudocode

```c
NTSTATUS __stdcall WdmlibRtlInitUnicodeStringEx(PUNICODE_STRING DestinationString, PCWSTR SourceString)
{
  unsigned __int64 v2; // rax
  NTSTATUS result; // eax
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // r8

  if ( SourceString )
  {
    v2 = -1;
    do
      ++v2;
    while ( SourceString[v2] );
    if ( v2 > 0x7FFE )
      return -1073741562;
    v4 = 2 * v2;
    v5 = v4 + 2;
  }
  else
  {
    SourceString = 0;
    v5 = 0;
    v4 = 0;
  }
  DestinationString->Length = v4;
  result = 0;
  DestinationString->MaximumLength = v5;
  DestinationString->Buffer = (wchar_t *)SourceString;
  return result;
}

```

## disassembly

```asm
0x140006430  xor     r9d, r9d
0x140006433  test    rdx, rdx
0x140006436  jz      short loc_14000645E
0x140006438  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000643c  inc     rax
0x14000643f  cmp     [rdx+rax*2], r9w
0x140006444  jnz     short loc_14000643C
0x140006446  cmp     rax, 7FFEh
0x14000644c  jbe     short loc_140006455
0x14000644e  mov     eax, 0C0000106h
0x140006453  retn
0x140006455  add     ax, ax
0x140006458  lea     r8d, [rax+2]
0x14000645c  jmp     short loc_140006467
0x14000645e  mov     rdx, r9
0x140006461  mov     r8d, r9d
0x140006464  mov     eax, r9d
0x140006467  mov     [rcx], ax
0x14000646a  xor     eax, eax
0x14000646c  mov     [rcx+2], r8w
0x140006471  mov     [rcx+8], rdx
0x140006475  retn
```
