# WdmlibRtlInitUnicodeStringEx

- ea: `0x140005d08`
- end: `0x140005d4e`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140021c84`
- `0x140021e6c`
- `0x140021fd8`
- `0x140022300`
- `0x140022360`
- `0x14002269c`
- `0x140022744`

## callees

- `0x140005d08`

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
0x140005d08  xor     r9d, r9d
0x140005d0b  test    rdx, rdx
0x140005d0e  jz      short loc_140005D36
0x140005d10  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005d14  inc     rax
0x140005d17  cmp     [rdx+rax*2], r9w
0x140005d1c  jnz     short loc_140005D14
0x140005d1e  cmp     rax, 7FFEh
0x140005d24  jbe     short loc_140005D2D
0x140005d26  mov     eax, 0C0000106h
0x140005d2b  retn
0x140005d2d  add     ax, ax
0x140005d30  lea     r8d, [rax+2]
0x140005d34  jmp     short loc_140005D3F
0x140005d36  mov     rdx, r9
0x140005d39  mov     r8d, r9d
0x140005d3c  mov     eax, r9d
0x140005d3f  mov     [rcx], ax
0x140005d42  xor     eax, eax
0x140005d44  mov     [rcx+2], r8w
0x140005d49  mov     [rcx+8], rdx
0x140005d4d  retn
```
