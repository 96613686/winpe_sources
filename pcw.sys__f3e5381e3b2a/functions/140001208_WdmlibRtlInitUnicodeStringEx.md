# WdmlibRtlInitUnicodeStringEx

- ea: `0x140001208`
- end: `0x14000124e`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400100fc`
- `0x1400102e4`
- `0x140010450`
- `0x1400105cc`
- `0x1400106a0`
- `0x1400109dc`
- `0x140010a84`

## callees

- `0x140001208`

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
0x140001208  xor     r9d, r9d
0x14000120b  test    rdx, rdx
0x14000120e  jz      short loc_140001236
0x140001210  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001214  inc     rax
0x140001217  cmp     [rdx+rax*2], r9w
0x14000121c  jnz     short loc_140001214
0x14000121e  cmp     rax, 7FFEh
0x140001224  jbe     short loc_14000122D
0x140001226  mov     eax, 0C0000106h
0x14000122b  retn
0x14000122d  add     ax, ax
0x140001230  lea     r8d, [rax+2]
0x140001234  jmp     short loc_14000123F
0x140001236  mov     rdx, r9
0x140001239  mov     r8d, r9d
0x14000123c  mov     eax, r9d
0x14000123f  mov     [rcx], ax
0x140001242  xor     eax, eax
0x140001244  mov     [rcx+2], r8w
0x140001249  mov     [rcx+8], rdx
0x14000124d  retn
```
