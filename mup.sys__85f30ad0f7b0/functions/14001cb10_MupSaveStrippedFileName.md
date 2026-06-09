# MupSaveStrippedFileName

- ea: `0x14001cb10`
- end: `0x14001cbc0`
- name: `MupSaveStrippedFileName`
- size: `176`
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
- `0x14001cb10`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001cb69`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001cb69`

## pseudocode

```c
void __fastcall MupSaveStrippedFileName(__int64 a1, char a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbp
  struct _UNICODE_STRING *v6; // rsi
  int v7; // edx
  WCHAR *MatchingChar; // rax
  __int16 v9; // dx
  __int64 v10; // r9
  USHORT v11; // dx

  while ( 1 )
  {
    v4 = 128;
    v5 = 112;
    if ( !a2 )
    {
      v4 = 72;
      v5 = 56;
    }
    v6 = (struct _UNICODE_STRING *)(a1 + v4);
    if ( (unsigned int)(*(_DWORD *)(a1 + 160) - 1) > 1 )
    {
      RtlInitUnicodeString(v6, 0);
      v7 = *(unsigned __int16 *)(v5 + a1) >> 1;
      if ( v7 )
      {
        MatchingChar = MupFindMatchingChar(
                         (_WORD *)(*(_QWORD *)(v5 + a1 + 8) + 2LL),
                         (unsigned int)(v7 - 1),
                         (unsigned int)(v7 - 1));
        if ( MatchingChar )
        {
          v6->Buffer = MatchingChar;
          v11 = 2 * (v9 - (((__int64)MatchingChar - v10) >> 1));
          v6->Length = v11;
          v6->MaximumLength = v11;
        }
      }
    }
    else
    {
      *v6 = *(struct _UNICODE_STRING *)(v5 + a1);
    }
    if ( !a2 )
      break;
    a2 = 0;
  }
}

```

## disassembly

```asm
0x14001cb10  push    rbx
0x14001cb12  push    rbp
0x14001cb13  push    rsi
0x14001cb14  push    rdi
0x14001cb15  push    r14
0x14001cb17  push    r15
0x14001cb19  sub     rsp, 28h
0x14001cb1d  movzx   ebx, dl
0x14001cb20  mov     rdi, rcx
0x14001cb23  mov     r14d, 38h ; '8'
0x14001cb29  mov     r15d, 48h ; 'H'
0x14001cb2f  nop
0x14001cb30  mov     eax, [rdi+0A0h]
0x14001cb36  test    bl, bl
0x14001cb38  mov     esi, 80h
0x14001cb3d  mov     ebp, 70h ; 'p'
0x14001cb42  cmovz   rsi, r15
0x14001cb46  cmovz   rbp, r14
0x14001cb4a  add     rsi, rdi
0x14001cb4d  dec     eax
0x14001cb4f  cmp     eax, 1
0x14001cb52  ja      short loc_14001CB64
0x14001cb54  movups  xmm0, xmmword ptr [rbp+rdi+0]
0x14001cb59  movups  xmmword ptr [rsi], xmm0
0x14001cb5c  test    bl, bl
0x14001cb5e  jz      short loc_14001CBB2
0x14001cb60  xor     bl, bl
0x14001cb62  jmp     short loc_14001CB30
0x14001cb64  xor     edx, edx; SourceString
0x14001cb66  mov     rcx, rsi; DestinationString
0x14001cb69  call    cs:__imp_RtlInitUnicodeString
0x14001cb70  nop     dword ptr [rax+rax+00h]
0x14001cb75  movzx   edx, word ptr [rbp+rdi+0]
0x14001cb7a  shr     edx, 1
0x14001cb7c  jz      short loc_14001CB5C
0x14001cb7e  mov     r9, [rbp+rdi+8]
0x14001cb83  add     r9, 2
0x14001cb87  dec     edx
0x14001cb89  mov     rcx, r9
0x14001cb8c  mov     r8d, edx
0x14001cb8f  call    MupFindMatchingChar
0x14001cb94  test    rax, rax
0x14001cb97  jz      short loc_14001CB5C
0x14001cb99  mov     [rsi+8], rax
0x14001cb9d  sub     rax, r9
0x14001cba0  sar     rax, 1
0x14001cba3  sub     dx, ax
0x14001cba6  add     dx, dx
0x14001cba9  mov     [rsi], dx
0x14001cbac  mov     [rsi+2], dx
0x14001cbb0  jmp     short loc_14001CB5C
0x14001cbb2  add     rsp, 28h
0x14001cbb6  pop     r15
0x14001cbb8  pop     r14
0x14001cbba  pop     rdi
0x14001cbbb  pop     rsi
0x14001cbbc  pop     rbp
0x14001cbbd  pop     rbx
0x14001cbbe  retn
```
