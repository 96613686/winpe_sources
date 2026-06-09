# SIPolicyPathMacroReplace

- ea: `0x1800dec04`
- end: `0x1800ded27`
- name: `SIPolicyPathMacroReplace`
- size: `291`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1, PCUNICODE_STRING SourceString, PUNICODE_STRING Destination)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800a38fc`
- `0x1800dea34`

## callees

- `0x1800dec04`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800decf1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800decf1`
- `ntoskrnl!ExAllocatePool2` at `0x1800decb3`
- `ntoskrnl!ExAllocatePool2` at `0x1800decb3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800ded05`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800ded05`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800dec5b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800dec5b`

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
0x1800dec04  push    rbx
0x1800dec06  push    rsi
0x1800dec07  push    rdi
0x1800dec08  push    r14
0x1800dec0a  push    r15
0x1800dec0c  sub     rsp, 30h
0x1800dec10  movzx   eax, word ptr [rdx]
0x1800dec13  mov     rdi, rcx
0x1800dec16  movzx   ecx, word ptr [rcx]
0x1800dec19  xorps   xmm0, xmm0
0x1800dec1c  mov     r14, r9
0x1800dec1f  mov     r15, r8
0x1800dec22  mov     rsi, rdx
0x1800dec25  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x1800dec2a  cmp     cx, ax
0x1800dec2d  jb      loc_1800DED15
0x1800dec33  lea     r9, [rax+2]
0x1800dec37  mov     r10d, eax
0x1800dec3a  cmp     rcx, r9
0x1800dec3d  jbe     short loc_1800DEC52
0x1800dec3f  mov     rax, [rdi+8]
0x1800dec43  shr     r10, 1
0x1800dec46  cmp     word ptr [rax+r10*2], 5Ch ; '\'
0x1800dec4c  jnz     loc_1800DED15
0x1800dec52  mov     r8b, 1; CaseInSensitive
0x1800dec55  mov     rdx, rdi; String2
0x1800dec58  mov     rcx, rsi; String1
0x1800dec5b  call    cs:__imp_RtlPrefixUnicodeString
0x1800dec62  nop     dword ptr [rax+rax+00h]
0x1800dec67  test    al, al
0x1800dec69  jz      loc_1800DED15
0x1800dec6f  movzx   r8d, word ptr [rdi]
0x1800dec73  mov     eax, 0FFFEh
0x1800dec78  movzx   edx, word ptr [r15]
0x1800dec7c  mov     ecx, r8d
0x1800dec7f  movzx   r9d, word ptr [rsi]
0x1800dec83  sub     ax, dx
0x1800dec86  sub     ecx, r9d
0x1800dec89  movzx   eax, ax
0x1800dec8c  cmp     eax, ecx
0x1800dec8e  jl      loc_1800DED15
0x1800dec94  sub     dx, r9w
0x1800dec98  mov     ecx, 102h
0x1800dec9d  add     dx, r8w
0x1800deca1  mov     r8d, 72634943h
0x1800deca7  movzx   edx, dx
0x1800decaa  mov     [r14], dx
0x1800decae  mov     [r14+2], dx
0x1800decb3  call    cs:__imp_ExAllocatePool2
0x1800decba  nop     dword ptr [rax+rax+00h]
0x1800decbf  mov     [r14+8], rax
0x1800decc3  test    rax, rax
0x1800decc6  jnz     short loc_1800DECCF
0x1800decc8  mov     eax, 0C0000017h
0x1800deccd  jmp     short loc_1800DED1A
0x1800deccf  movzx   ecx, word ptr [rsi]
0x1800decd2  mov     rdx, r15; SourceString
0x1800decd5  movzx   eax, word ptr [rdi]
0x1800decd8  sub     ax, cx
0x1800decdb  add     rcx, [rdi+8]
0x1800decdf  mov     [rsp+58h+Source.Buffer], rcx
0x1800dece4  mov     rcx, r14; DestinationString
0x1800dece7  mov     [rsp+58h+Source.MaximumLength], ax
0x1800decec  mov     [rsp+58h+Source.Length], ax
0x1800decf1  call    cs:__imp_RtlCopyUnicodeString
0x1800decf8  nop     dword ptr [rax+rax+00h]
0x1800decfd  lea     rdx, [rsp+58h+Source]; Source
0x1800ded02  mov     rcx, r14; Destination
0x1800ded05  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800ded0c  nop     dword ptr [rax+rax+00h]
0x1800ded11  xor     eax, eax
0x1800ded13  jmp     short loc_1800DED1A
0x1800ded15  mov     eax, 0C000000Dh
0x1800ded1a  add     rsp, 30h
0x1800ded1e  pop     r15
0x1800ded20  pop     r14
0x1800ded22  pop     rdi
0x1800ded23  pop     rsi
0x1800ded24  pop     rbx
0x1800ded25  retn
```
