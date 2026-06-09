# MupSaveProviderStrippedFileName

- ea: `0x14001ca50`
- end: `0x14001cafc`
- name: `MupSaveProviderStrippedFileName`
- size: `172`
- prototype: `void __fastcall(__int64, char)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140014600`
- `0x140019598`
- `0x14001a920`

## callees

- `0x140001040`
- `0x14001ca50`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001caa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001caa5`

## pseudocode

```c
void __fastcall MupSaveProviderStrippedFileName(__int64 a1, char a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbp
  struct _UNICODE_STRING *v6; // rsi
  int v7; // edx
  __int64 MatchingChar; // rax
  __int16 v9; // dx
  __int64 v10; // r9
  USHORT v11; // dx

  while ( 1 )
  {
    v4 = 112;
    v5 = 96;
    if ( !a2 )
    {
      v4 = 56;
      v5 = 40;
    }
    v6 = (struct _UNICODE_STRING *)(a1 + v4);
    if ( *(_DWORD *)(a1 + 160) == 1 )
    {
      *v6 = *(struct _UNICODE_STRING *)(v5 + a1);
    }
    else
    {
      RtlInitUnicodeString(v6, 0);
      v7 = *(unsigned __int16 *)(v5 + a1) >> 1;
      if ( v7 )
      {
        MatchingChar = MupFindMatchingChar(
                         *(_QWORD *)(v5 + a1 + 8) + 2LL,
                         (unsigned int)(v7 - 1),
                         (unsigned int)(v7 - 1));
        if ( MatchingChar )
        {
          v6->Buffer = (PWSTR)MatchingChar;
          v11 = 2 * (v9 - ((MatchingChar - v10) >> 1));
          v6->Length = v11;
          v6->MaximumLength = v11;
        }
      }
    }
    if ( !a2 )
      break;
    a2 = 0;
  }
}

```

## disassembly

```asm
0x14001ca50  push    rbx
0x14001ca52  push    rbp
0x14001ca53  push    rsi
0x14001ca54  push    rdi
0x14001ca55  push    r14
0x14001ca57  push    r15
0x14001ca59  sub     rsp, 28h
0x14001ca5d  movzx   ebx, dl
0x14001ca60  mov     rdi, rcx
0x14001ca63  mov     r14d, 28h ; '('
0x14001ca69  mov     r15d, 38h ; '8'
0x14001ca6f  nop
0x14001ca70  test    bl, bl
0x14001ca72  mov     esi, 70h ; 'p'
0x14001ca77  mov     ebp, 60h ; '`'
0x14001ca7c  cmovz   rsi, r15
0x14001ca80  cmovz   rbp, r14
0x14001ca84  add     rsi, rdi
0x14001ca87  cmp     dword ptr [rdi+0A0h], 1
0x14001ca8e  jnz     short loc_14001CAA0
0x14001ca90  movups  xmm0, xmmword ptr [rbp+rdi+0]
0x14001ca95  movups  xmmword ptr [rsi], xmm0
0x14001ca98  test    bl, bl
0x14001ca9a  jz      short loc_14001CAEE
0x14001ca9c  xor     bl, bl
0x14001ca9e  jmp     short loc_14001CA70
0x14001caa0  xor     edx, edx; SourceString
0x14001caa2  mov     rcx, rsi; DestinationString
0x14001caa5  call    cs:__imp_RtlInitUnicodeString
0x14001caac  nop     dword ptr [rax+rax+00h]
0x14001cab1  movzx   edx, word ptr [rbp+rdi+0]
0x14001cab6  shr     edx, 1
0x14001cab8  jz      short loc_14001CA98
0x14001caba  mov     r9, [rbp+rdi+8]
0x14001cabf  add     r9, 2
0x14001cac3  dec     edx
0x14001cac5  mov     rcx, r9
0x14001cac8  mov     r8d, edx
0x14001cacb  call    MupFindMatchingChar
0x14001cad0  test    rax, rax
0x14001cad3  jz      short loc_14001CA98
0x14001cad5  mov     [rsi+8], rax
0x14001cad9  sub     rax, r9
0x14001cadc  sar     rax, 1
0x14001cadf  sub     dx, ax
0x14001cae2  add     dx, dx
0x14001cae5  mov     [rsi], dx
0x14001cae8  mov     [rsi+2], dx
0x14001caec  jmp     short loc_14001CA98
0x14001caee  add     rsp, 28h
0x14001caf2  pop     r15
0x14001caf4  pop     r14
0x14001caf6  pop     rdi
0x14001caf7  pop     rsi
0x14001caf8  pop     rbp
0x14001caf9  pop     rbx
0x14001cafa  retn
```
