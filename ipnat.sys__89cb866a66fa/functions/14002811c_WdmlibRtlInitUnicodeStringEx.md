# WdmlibRtlInitUnicodeStringEx

- ea: `0x14002811c`
- end: `0x140028162`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140043a6c`
- `0x140043c54`
- `0x140043dc0`
- `0x14004403c`
- `0x140044110`
- `0x14004444c`
- `0x1400444f4`

## callees

- `0x14002811c`

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
0x14002811c  xor     r9d, r9d
0x14002811f  test    rdx, rdx
0x140028122  jz      short loc_14002814A
0x140028124  or      rax, 0FFFFFFFFFFFFFFFFh
0x140028128  inc     rax
0x14002812b  cmp     [rdx+rax*2], r9w
0x140028130  jnz     short loc_140028128
0x140028132  cmp     rax, 7FFEh
0x140028138  jbe     short loc_140028141
0x14002813a  mov     eax, 0C0000106h
0x14002813f  retn
0x140028141  add     ax, ax
0x140028144  lea     r8d, [rax+2]
0x140028148  jmp     short loc_140028153
0x14002814a  mov     rdx, r9
0x14002814d  mov     r8d, r9d
0x140028150  mov     eax, r9d
0x140028153  mov     [rcx], ax
0x140028156  xor     eax, eax
0x140028158  mov     [rcx+2], r8w
0x14002815d  mov     [rcx+8], rdx
0x140028161  retn
```
