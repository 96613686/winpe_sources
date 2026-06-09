# WdmlibRtlInitUnicodeStringEx

- ea: `0x140007e0c`
- end: `0x140007e52`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001854c`
- `0x140018734`
- `0x1400188a0`
- `0x140018b1c`
- `0x140018bf0`
- `0x140018f2c`
- `0x140018fd4`

## callees

- `0x140007e0c`

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
0x140007e0c  xor     r9d, r9d
0x140007e0f  test    rdx, rdx
0x140007e12  jz      short loc_140007E3A
0x140007e14  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007e18  inc     rax
0x140007e1b  cmp     [rdx+rax*2], r9w
0x140007e20  jnz     short loc_140007E18
0x140007e22  cmp     rax, 7FFEh
0x140007e28  jbe     short loc_140007E31
0x140007e2a  mov     eax, 0C0000106h
0x140007e2f  retn
0x140007e31  add     ax, ax
0x140007e34  lea     r8d, [rax+2]
0x140007e38  jmp     short loc_140007E43
0x140007e3a  mov     rdx, r9
0x140007e3d  mov     r8d, r9d
0x140007e40  mov     eax, r9d
0x140007e43  mov     [rcx], ax
0x140007e46  xor     eax, eax
0x140007e48  mov     [rcx+2], r8w
0x140007e4d  mov     [rcx+8], rdx
0x140007e51  retn
```
