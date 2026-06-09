# RtlUnicodeStringValidateWorker

- ea: `0x140001280`
- end: `0x1400012c2`
- name: `RtlUnicodeStringValidateWorker`
- size: `66`
- prototype: `NTSTATUS __stdcall(PCUNICODE_STRING SourceString, const size_t cchMax, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009410`

## callees

- `0x140001280`

## pseudocode

```c
NTSTATUS __stdcall RtlUnicodeStringValidateWorker(PCUNICODE_STRING SourceString, const size_t cchMax, ULONG dwFlags)
{
  USHORT Length; // r8
  USHORT MaximumLength; // dx

  Length = SourceString->Length;
  if ( (SourceString->Length & 1) != 0 )
    return -1073741811;
  MaximumLength = SourceString->MaximumLength;
  if ( (MaximumLength & 1) != 0
    || Length > MaximumLength
    || MaximumLength == 0xFFFF
    || !SourceString->Buffer && (Length || MaximumLength) )
  {
    return -1073741811;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140001280  movzx   r8d, word ptr [rcx]
0x140001284  test    r8b, 1
0x140001288  jnz     short loc_1400012AE
0x14000128a  movzx   edx, word ptr [rcx+2]
0x14000128e  test    dl, 1
0x140001291  jnz     short loc_1400012AE
0x140001293  cmp     r8w, dx
0x140001297  ja      short loc_1400012AE
0x140001299  mov     eax, 0FFFEh
0x14000129e  cmp     dx, ax
0x1400012a1  ja      short loc_1400012AE
0x1400012a3  cmp     qword ptr [rcx+8], 0
0x1400012a8  jz      short loc_1400012B5
0x1400012aa  xor     eax, eax
0x1400012ac  retn
0x1400012ae  mov     eax, 0C000000Dh
0x1400012b3  retn
0x1400012b5  test    r8w, r8w
0x1400012b9  jnz     short loc_1400012AE
0x1400012bb  test    dx, dx
0x1400012be  jnz     short loc_1400012AE
0x1400012c0  jmp     short loc_1400012AA
```
