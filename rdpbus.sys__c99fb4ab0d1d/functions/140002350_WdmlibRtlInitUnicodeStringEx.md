# WdmlibRtlInitUnicodeStringEx

- ea: `0x140002350`
- end: `0x140002396`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140009f4c`
- `0x14000a134`
- `0x14000a2a0`
- `0x14000a5c8`
- `0x14000a628`
- `0x14000a964`
- `0x14000aa0c`

## callees

- `0x140002350`

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
0x140002350  xor     r9d, r9d
0x140002353  test    rdx, rdx
0x140002356  jz      short loc_14000237E
0x140002358  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000235c  inc     rax
0x14000235f  cmp     [rdx+rax*2], r9w
0x140002364  jnz     short loc_14000235C
0x140002366  cmp     rax, 7FFEh
0x14000236c  jbe     short loc_140002375
0x14000236e  mov     eax, 0C0000106h
0x140002373  retn
0x140002375  add     ax, ax
0x140002378  lea     r8d, [rax+2]
0x14000237c  jmp     short loc_140002387
0x14000237e  mov     rdx, r9
0x140002381  mov     r8d, r9d
0x140002384  mov     eax, r9d
0x140002387  mov     [rcx], ax
0x14000238a  xor     eax, eax
0x14000238c  mov     [rcx+2], r8w
0x140002391  mov     [rcx+8], rdx
0x140002395  retn
```
