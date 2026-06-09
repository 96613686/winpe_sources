# CscPath_FindFileName(ushort const *)

- ea: `0x180032a30`
- end: `0x180032a80`
- name: `?CscPath_FindFileName@@YAPEBGPEBG@Z`
- size: `80`
- prototype: `const unsigned __int16 *__fastcall(PCWSTR SourceString)`
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001bd40`
- `0x18001e290`
- `0x18001eaa4`
- `0x180020958`
- `0x18003990c`
- `0x1800409c8`

## callees

- `0x180032a30`

## import_xrefs

- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180032a63`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180032a63`
- `ntdll!RtlInitUnicodeString` at `0x180032a49`
- `ntdll!RtlInitUnicodeString` at `0x180032a49`

## pseudocode

```c
const unsigned __int16 *__fastcall CscPath_FindFileName(PCWSTR SourceString)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  ULONG LengthOut; // [rsp+48h] [rbp+10h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  LengthOut = 0;
  if ( RtlGetLengthWithoutLastFullDosOrNtPathElement(0, &DestinationString.Length, &LengthOut) < 0 )
    return SourceString;
  else
    return &SourceString[LengthOut];
}

```

## disassembly

```asm
0x180032a30  push    rbx
0x180032a32  sub     rsp, 30h
0x180032a36  mov     rbx, rcx
0x180032a39  xorps   xmm0, xmm0
0x180032a3c  mov     rdx, rcx; SourceString
0x180032a3f  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180032a44  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180032a49  call    cs:__imp_RtlInitUnicodeString
0x180032a4f  lea     r8, [rsp+38h+LengthOut]; LengthOut
0x180032a54  mov     [rsp+38h+LengthOut], 0
0x180032a5c  lea     rdx, [rsp+38h+DestinationString]; Path
0x180032a61  xor     ecx, ecx; Flags
0x180032a63  call    cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement
0x180032a69  test    eax, eax
0x180032a6b  js      short loc_180032A77
0x180032a6d  mov     eax, [rsp+38h+LengthOut]
0x180032a71  lea     rax, [rbx+rax*2]
0x180032a75  jmp     short loc_180032A7A
0x180032a77  mov     rax, rbx
0x180032a7a  add     rsp, 30h
0x180032a7e  pop     rbx
0x180032a7f  retn
```
