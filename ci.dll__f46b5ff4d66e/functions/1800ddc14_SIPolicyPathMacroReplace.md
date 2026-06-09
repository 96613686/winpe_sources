# SIPolicyPathMacroReplace

- ea: `0x1800ddc14`
- end: `0x1800ddd37`
- name: `SIPolicyPathMacroReplace`
- size: `291`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1, PCUNICODE_STRING SourceString, PUNICODE_STRING Destination)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800a22cc`
- `0x1800dda44`

## callees

- `0x1800ddc14`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800ddd01`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800ddd01`
- `ntoskrnl!ExAllocatePool2` at `0x1800ddcc3`
- `ntoskrnl!ExAllocatePool2` at `0x1800ddcc3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800ddd15`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800ddd15`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800ddc6b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800ddc6b`

## pseudocode

```c
__int64 __fastcall SIPolicyPathMacroReplace(
        PCUNICODE_STRING String2,
        PCUNICODE_STRING String1,
        PCUNICODE_STRING SourceString,
        PUNICODE_STRING Destination)
{
  __int64 Length; // rax
  unsigned __int64 v6; // rcx
  int v10; // r9d
  USHORT v11; // dx
  WCHAR *Pool2; // rax
  __int64 v14; // rcx
  USHORT v15; // ax
  UNICODE_STRING Source; // [rsp+20h] [rbp-38h] BYREF

  Length = String1->Length;
  v6 = String2->Length;
  Source = 0;
  if ( (unsigned __int16)v6 < (unsigned __int16)Length
    || v6 > Length + 2 && String2->Buffer[(unsigned __int64)(unsigned int)Length >> 1] != 92 )
  {
    return 3221225485LL;
  }
  if ( !RtlPrefixUnicodeString(String1, String2, 1u) )
    return 3221225485LL;
  v10 = String1->Length;
  if ( (unsigned __int16)(-2 - SourceString->Length) < String2->Length - v10 )
    return 3221225485LL;
  v11 = String2->Length + SourceString->Length - v10;
  Destination->Length = v11;
  Destination->MaximumLength = v11;
  Pool2 = (WCHAR *)ExAllocatePool2(258, v11, 1919109443);
  Destination->Buffer = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  v14 = String1->Length;
  v15 = String2->Length - v14;
  Source.Buffer = (PWSTR)((char *)String2->Buffer + v14);
  Source.MaximumLength = v15;
  Source.Length = v15;
  RtlCopyUnicodeString(Destination, SourceString);
  RtlAppendUnicodeStringToString(Destination, &Source);
  return 0;
}

```

## disassembly

```asm
0x1800ddc14  push    rbx
0x1800ddc16  push    rsi
0x1800ddc17  push    rdi
0x1800ddc18  push    r14
0x1800ddc1a  push    r15
0x1800ddc1c  sub     rsp, 30h
0x1800ddc20  movzx   eax, word ptr [rdx]
0x1800ddc23  mov     rdi, rcx
0x1800ddc26  movzx   ecx, word ptr [rcx]
0x1800ddc29  xorps   xmm0, xmm0
0x1800ddc2c  mov     r14, r9
0x1800ddc2f  mov     r15, r8
0x1800ddc32  mov     rsi, rdx
0x1800ddc35  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x1800ddc3a  cmp     cx, ax
0x1800ddc3d  jb      loc_1800DDD25
0x1800ddc43  lea     r9, [rax+2]
0x1800ddc47  mov     r10d, eax
0x1800ddc4a  cmp     rcx, r9
0x1800ddc4d  jbe     short loc_1800DDC62
0x1800ddc4f  mov     rax, [rdi+8]
0x1800ddc53  shr     r10, 1
0x1800ddc56  cmp     word ptr [rax+r10*2], 5Ch ; '\'
0x1800ddc5c  jnz     loc_1800DDD25
0x1800ddc62  mov     r8b, 1; CaseInSensitive
0x1800ddc65  mov     rdx, rdi; String2
0x1800ddc68  mov     rcx, rsi; String1
0x1800ddc6b  call    cs:__imp_RtlPrefixUnicodeString
0x1800ddc72  nop     dword ptr [rax+rax+00h]
0x1800ddc77  test    al, al
0x1800ddc79  jz      loc_1800DDD25
0x1800ddc7f  movzx   r8d, word ptr [rdi]
0x1800ddc83  mov     eax, 0FFFEh
0x1800ddc88  movzx   edx, word ptr [r15]
0x1800ddc8c  mov     ecx, r8d
0x1800ddc8f  movzx   r9d, word ptr [rsi]
0x1800ddc93  sub     ax, dx
0x1800ddc96  sub     ecx, r9d
0x1800ddc99  movzx   eax, ax
0x1800ddc9c  cmp     eax, ecx
0x1800ddc9e  jl      loc_1800DDD25
0x1800ddca4  sub     dx, r9w
0x1800ddca8  mov     ecx, 102h
0x1800ddcad  add     dx, r8w
0x1800ddcb1  mov     r8d, 72634943h
0x1800ddcb7  movzx   edx, dx
0x1800ddcba  mov     [r14], dx
0x1800ddcbe  mov     [r14+2], dx
0x1800ddcc3  call    cs:__imp_ExAllocatePool2
0x1800ddcca  nop     dword ptr [rax+rax+00h]
0x1800ddccf  mov     [r14+8], rax
0x1800ddcd3  test    rax, rax
0x1800ddcd6  jnz     short loc_1800DDCDF
0x1800ddcd8  mov     eax, 0C0000017h
0x1800ddcdd  jmp     short loc_1800DDD2A
0x1800ddcdf  movzx   ecx, word ptr [rsi]
0x1800ddce2  mov     rdx, r15; SourceString
0x1800ddce5  movzx   eax, word ptr [rdi]
0x1800ddce8  sub     ax, cx
0x1800ddceb  add     rcx, [rdi+8]
0x1800ddcef  mov     [rsp+58h+Source.Buffer], rcx
0x1800ddcf4  mov     rcx, r14; DestinationString
0x1800ddcf7  mov     [rsp+58h+Source.MaximumLength], ax
0x1800ddcfc  mov     [rsp+58h+Source.Length], ax
0x1800ddd01  call    cs:__imp_RtlCopyUnicodeString
0x1800ddd08  nop     dword ptr [rax+rax+00h]
0x1800ddd0d  lea     rdx, [rsp+58h+Source]; Source
0x1800ddd12  mov     rcx, r14; Destination
0x1800ddd15  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800ddd1c  nop     dword ptr [rax+rax+00h]
0x1800ddd21  xor     eax, eax
0x1800ddd23  jmp     short loc_1800DDD2A
0x1800ddd25  mov     eax, 0C000000Dh
0x1800ddd2a  add     rsp, 30h
0x1800ddd2e  pop     r15
0x1800ddd30  pop     r14
0x1800ddd32  pop     rdi
0x1800ddd33  pop     rsi
0x1800ddd34  pop     rbx
0x1800ddd35  retn
```
