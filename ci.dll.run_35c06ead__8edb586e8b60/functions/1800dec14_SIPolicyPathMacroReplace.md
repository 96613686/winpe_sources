# SIPolicyPathMacroReplace

- ea: `0x1800dec14`
- end: `0x1800ded37`
- name: `SIPolicyPathMacroReplace`
- size: `291`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1, PCUNICODE_STRING SourceString, PUNICODE_STRING Destination)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800a3d98`
- `0x1800dea44`

## callees

- `0x1800dec14`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800ded01`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800ded01`
- `ntoskrnl!ExAllocatePool2` at `0x1800decc3`
- `ntoskrnl!ExAllocatePool2` at `0x1800decc3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800ded15`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800ded15`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800dec6b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1800dec6b`

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
0x1800dec14  push    rbx
0x1800dec16  push    rsi
0x1800dec17  push    rdi
0x1800dec18  push    r14
0x1800dec1a  push    r15
0x1800dec1c  sub     rsp, 30h
0x1800dec20  movzx   eax, word ptr [rdx]
0x1800dec23  mov     rdi, rcx
0x1800dec26  movzx   ecx, word ptr [rcx]
0x1800dec29  xorps   xmm0, xmm0
0x1800dec2c  mov     r14, r9
0x1800dec2f  mov     r15, r8
0x1800dec32  mov     rsi, rdx
0x1800dec35  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x1800dec3a  cmp     cx, ax
0x1800dec3d  jb      loc_1800DED25
0x1800dec43  lea     r9, [rax+2]
0x1800dec47  mov     r10d, eax
0x1800dec4a  cmp     rcx, r9
0x1800dec4d  jbe     short loc_1800DEC62
0x1800dec4f  mov     rax, [rdi+8]
0x1800dec53  shr     r10, 1
0x1800dec56  cmp     word ptr [rax+r10*2], 5Ch ; '\'
0x1800dec5c  jnz     loc_1800DED25
0x1800dec62  mov     r8b, 1; CaseInSensitive
0x1800dec65  mov     rdx, rdi; String2
0x1800dec68  mov     rcx, rsi; String1
0x1800dec6b  call    cs:__imp_RtlPrefixUnicodeString
0x1800dec72  nop     dword ptr [rax+rax+00h]
0x1800dec77  test    al, al
0x1800dec79  jz      loc_1800DED25
0x1800dec7f  movzx   r8d, word ptr [rdi]
0x1800dec83  mov     eax, 0FFFEh
0x1800dec88  movzx   edx, word ptr [r15]
0x1800dec8c  mov     ecx, r8d
0x1800dec8f  movzx   r9d, word ptr [rsi]
0x1800dec93  sub     ax, dx
0x1800dec96  sub     ecx, r9d
0x1800dec99  movzx   eax, ax
0x1800dec9c  cmp     eax, ecx
0x1800dec9e  jl      loc_1800DED25
0x1800deca4  sub     dx, r9w
0x1800deca8  mov     ecx, 102h
0x1800decad  add     dx, r8w
0x1800decb1  mov     r8d, 72634943h
0x1800decb7  movzx   edx, dx
0x1800decba  mov     [r14], dx
0x1800decbe  mov     [r14+2], dx
0x1800decc3  call    cs:__imp_ExAllocatePool2
0x1800decca  nop     dword ptr [rax+rax+00h]
0x1800deccf  mov     [r14+8], rax
0x1800decd3  test    rax, rax
0x1800decd6  jnz     short loc_1800DECDF
0x1800decd8  mov     eax, 0C0000017h
0x1800decdd  jmp     short loc_1800DED2A
0x1800decdf  movzx   ecx, word ptr [rsi]
0x1800dece2  mov     rdx, r15; SourceString
0x1800dece5  movzx   eax, word ptr [rdi]
0x1800dece8  sub     ax, cx
0x1800deceb  add     rcx, [rdi+8]
0x1800decef  mov     [rsp+58h+Source.Buffer], rcx
0x1800decf4  mov     rcx, r14; DestinationString
0x1800decf7  mov     [rsp+58h+Source.MaximumLength], ax
0x1800decfc  mov     [rsp+58h+Source.Length], ax
0x1800ded01  call    cs:__imp_RtlCopyUnicodeString
0x1800ded08  nop     dword ptr [rax+rax+00h]
0x1800ded0d  lea     rdx, [rsp+58h+Source]; Source
0x1800ded12  mov     rcx, r14; Destination
0x1800ded15  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800ded1c  nop     dword ptr [rax+rax+00h]
0x1800ded21  xor     eax, eax
0x1800ded23  jmp     short loc_1800DED2A
0x1800ded25  mov     eax, 0C000000Dh
0x1800ded2a  add     rsp, 30h
0x1800ded2e  pop     r15
0x1800ded30  pop     r14
0x1800ded32  pop     rdi
0x1800ded33  pop     rsi
0x1800ded34  pop     rbx
0x1800ded35  retn
```
