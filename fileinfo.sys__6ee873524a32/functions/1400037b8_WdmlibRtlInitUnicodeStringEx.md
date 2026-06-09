# WdmlibRtlInitUnicodeStringEx

- ea: `0x1400037b8`
- end: `0x1400037fe`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140011d2c`
- `0x140011f14`
- `0x140012080`
- `0x1400123a8`
- `0x140012408`
- `0x140012744`
- `0x1400127ec`

## callees

- `0x1400037b8`

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
0x1400037b8  xor     r9d, r9d
0x1400037bb  test    rdx, rdx
0x1400037be  jz      short loc_1400037E6
0x1400037c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400037c4  inc     rax
0x1400037c7  cmp     [rdx+rax*2], r9w
0x1400037cc  jnz     short loc_1400037C4
0x1400037ce  cmp     rax, 7FFEh
0x1400037d4  jbe     short loc_1400037DD
0x1400037d6  mov     eax, 0C0000106h
0x1400037db  retn
0x1400037dd  add     ax, ax
0x1400037e0  lea     r8d, [rax+2]
0x1400037e4  jmp     short loc_1400037EF
0x1400037e6  mov     rdx, r9
0x1400037e9  mov     r8d, r9d
0x1400037ec  mov     eax, r9d
0x1400037ef  mov     [rcx], ax
0x1400037f2  xor     eax, eax
0x1400037f4  mov     [rcx+2], r8w
0x1400037f9  mov     [rcx+8], rdx
0x1400037fd  retn
```
