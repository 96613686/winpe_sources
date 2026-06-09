# CompareUnicodeShareNames

- ea: `0x180034714`
- end: `0x1800347ab`
- name: `CompareUnicodeShareNames`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d798`

## callees

- `0x180034714`
- `0x1800347b4`
- `0x180034804`
- `0x180034848`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180034795`
- `ntdll!RtlCompareUnicodeString` at `0x180034795`

## pseudocode

```c
bool __fastcall CompareUnicodeShareNames(unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  UNICODE_STRING String2; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-10h] BYREF

  v2 = *a1;
  v4 = *((_QWORD *)a1 + 1);
  String1 = 0;
  String2 = 0;
  NfsUnicodeStringInitFromBuffer(&String1, v4, v2);
  NfsUnicodeStringInitFromBuffer(&String2, *((_QWORD *)a2 + 1), *a2);
  SkipPrefixForwardSlash(&String1);
  SkipPrefixForwardSlash(&String2);
  if ( !String1.Length && !String2.Length )
    return 1;
  SkipSuffixForwardSlash(&String1);
  SkipSuffixForwardSlash(&String2);
  return RtlCompareUnicodeString(&String1, &String2, 1u) == 0;
}

```

## disassembly

```asm
0x180034714  mov     [rsp-8+arg_0], rbx
0x180034719  push    rbp
0x18003471a  mov     rbp, rsp
0x18003471d  sub     rsp, 40h
0x180034721  movzx   r8d, word ptr [rcx]
0x180034725  mov     rbx, rdx
0x180034728  mov     rdx, [rcx+8]
0x18003472c  xorps   xmm0, xmm0
0x18003472f  xorps   xmm1, xmm1
0x180034732  lea     rcx, [rbp+String1]
0x180034736  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18003473a  movups  xmmword ptr [rbp+String2.Length], xmm1
0x18003473e  call    NfsUnicodeStringInitFromBuffer
0x180034743  movzx   r8d, word ptr [rbx]
0x180034747  lea     rcx, [rbp+String2]
0x18003474b  mov     rdx, [rbx+8]
0x18003474f  call    NfsUnicodeStringInitFromBuffer
0x180034754  lea     rcx, [rbp+String1]
0x180034758  call    SkipPrefixForwardSlash
0x18003475d  lea     rcx, [rbp+String2]
0x180034761  call    SkipPrefixForwardSlash
0x180034766  xor     ebx, ebx
0x180034768  cmp     [rbp+String1.Length], bx
0x18003476c  jnz     short loc_180034778
0x18003476e  cmp     [rbp+String2.Length], bx
0x180034772  jnz     short loc_180034778
0x180034774  mov     al, 1
0x180034776  jmp     short loc_1800347A0
0x180034778  lea     rcx, [rbp+String1]
0x18003477c  call    SkipSuffixForwardSlash
0x180034781  lea     rcx, [rbp+String2]
0x180034785  call    SkipSuffixForwardSlash
0x18003478a  mov     r8b, 1; CaseInsensitive
0x18003478d  lea     rdx, [rbp+String2]; String2
0x180034791  lea     rcx, [rbp+String1]; String1
0x180034795  call    cs:__imp_RtlCompareUnicodeString
0x18003479b  test    eax, eax
0x18003479d  setz    al
0x1800347a0  mov     rbx, [rsp+40h+arg_0]
0x1800347a5  add     rsp, 40h
0x1800347a9  pop     rbp
0x1800347aa  retn
```
