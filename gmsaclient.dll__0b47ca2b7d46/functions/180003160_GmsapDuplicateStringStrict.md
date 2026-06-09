# GmsapDuplicateStringStrict

- ea: `0x180003160`
- end: `0x1800031aa`
- name: `GmsapDuplicateStringStrict`
- size: `74`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002380`
- `0x180002b18`

## callees

- `0x180003160`
- `0x1800031b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180003183`
- `ntdll!RtlInitUnicodeString` at `0x180003183`

## pseudocode

```c
__int64 __fastcall GmsapDuplicateStringStrict(PCWSTR SourceString, __int64 a2)
{
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  if ( !SourceString || !a2 )
    return 3221225485LL;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  return GmsapDuplicateWStr(&DestinationString);
}

```

## disassembly

```asm
0x180003160  push    rbx
0x180003162  sub     rsp, 30h
0x180003166  mov     rbx, rdx
0x180003169  test    rcx, rcx
0x18000316c  jz      short loc_18000319E
0x18000316e  test    rdx, rdx
0x180003171  jz      short loc_18000319E
0x180003173  xorps   xmm0, xmm0
0x180003176  mov     rdx, rcx; SourceString
0x180003179  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18000317e  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180003183  call    cs:__imp_RtlInitUnicodeString
0x18000318a  nop     dword ptr [rax+rax+00h]
0x18000318f  mov     rdx, rbx
0x180003192  lea     rcx, [rsp+38h+DestinationString]; SourceString
0x180003197  call    GmsapDuplicateWStr
0x18000319c  jmp     short loc_1800031A3
0x18000319e  mov     eax, 0C000000Dh
0x1800031a3  add     rsp, 30h
0x1800031a7  pop     rbx
0x1800031a8  retn
```
