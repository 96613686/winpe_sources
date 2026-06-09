# ClasspMpdevFindSupportedDevice

- ea: `0x14005c7a0`
- end: `0x14005c825`
- name: `ClasspMpdevFindSupportedDevice`
- size: `133`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14005cbc4`

## callees

- `0x14005c7a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14005c7ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005c7ca`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14005c7f4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14005c7f4`

## pseudocode

```c
char __fastcall ClasspMpdevFindSupportedDevice(PCUNICODE_STRING String2, __int64 a2)
{
  const WCHAR *v2; // rbx
  unsigned __int16 Length; // si
  LONG v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(const WCHAR **)(a2 + 8);
  Length = String2->Length;
  DestinationString = 0;
  while ( *v2 )
  {
    RtlInitUnicodeString(&DestinationString, v2);
    if ( DestinationString.Length >= 0x12u )
    {
      if ( DestinationString.Length < String2->Length )
        String2->Length = DestinationString.Length;
      v5 = RtlCompareUnicodeString(&DestinationString, String2, 1u);
      String2->Length = Length;
      if ( !v5 )
        return 1;
    }
    v2 += (unsigned __int64)DestinationString.MaximumLength >> 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14005c7a0  push    rbx
0x14005c7a2  push    rbp
0x14005c7a3  push    rsi
0x14005c7a4  push    rdi
0x14005c7a5  sub     rsp, 38h
0x14005c7a9  mov     rbx, [rdx+8]
0x14005c7ad  xorps   xmm0, xmm0
0x14005c7b0  movzx   esi, word ptr [rcx]
0x14005c7b3  mov     rdi, rcx
0x14005c7b6  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14005c7bb  xor     ebp, ebp
0x14005c7bd  cmp     [rbx], bp
0x14005c7c0  jz      short loc_14005C819
0x14005c7c2  mov     rdx, rbx; SourceString
0x14005c7c5  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14005c7ca  call    cs:__imp_RtlInitUnicodeString
0x14005c7d1  nop     dword ptr [rax+rax+00h]
0x14005c7d6  movzx   eax, [rsp+58h+DestinationString.Length]
0x14005c7db  cmp     ax, 12h
0x14005c7df  jb      short loc_14005C807
0x14005c7e1  cmp     ax, [rdi]
0x14005c7e4  jnb     short loc_14005C7E9
0x14005c7e6  mov     [rdi], ax
0x14005c7e9  mov     r8b, 1; CaseInSensitive
0x14005c7ec  lea     rcx, [rsp+58h+DestinationString]; String1
0x14005c7f1  mov     rdx, rdi; String2
0x14005c7f4  call    cs:__imp_RtlCompareUnicodeString
0x14005c7fb  nop     dword ptr [rax+rax+00h]
0x14005c800  mov     [rdi], si
0x14005c803  test    eax, eax
0x14005c805  jz      short loc_14005C815
0x14005c807  movzx   eax, [rsp+58h+DestinationString.MaximumLength]
0x14005c80c  shr     rax, 1
0x14005c80f  lea     rbx, [rbx+rax*2]
0x14005c813  jmp     short loc_14005C7BD
0x14005c815  mov     al, 1
0x14005c817  jmp     short loc_14005C81B
0x14005c819  xor     al, al
0x14005c81b  add     rsp, 38h
0x14005c81f  pop     rdi
0x14005c820  pop     rsi
0x14005c821  pop     rbp
0x14005c822  pop     rbx
0x14005c823  retn
```
