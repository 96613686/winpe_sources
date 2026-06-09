# MupSaveProviderStrippedFileName

- ea: `0x14001ca00`
- end: `0x14001caac`
- name: `MupSaveProviderStrippedFileName`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400145b0`
- `0x140019548`
- `0x14001a8d0`

## callees

- `0x140001040`
- `0x14001ca00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001ca55`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ca55`

## pseudocode

```c
void __fastcall MupSaveProviderStrippedFileName(__int64 a1, char a2)
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
    if ( !a2 )
      break;
    a2 = 0;
  }
}

```

## disassembly

```asm
0x14001ca00  push    rbx
0x14001ca02  push    rbp
0x14001ca03  push    rsi
0x14001ca04  push    rdi
0x14001ca05  push    r14
0x14001ca07  push    r15
0x14001ca09  sub     rsp, 28h
0x14001ca0d  movzx   ebx, dl
0x14001ca10  mov     rdi, rcx
0x14001ca13  mov     r14d, 28h ; '('
0x14001ca19  mov     r15d, 38h ; '8'
0x14001ca1f  nop
0x14001ca20  test    bl, bl
0x14001ca22  mov     esi, 70h ; 'p'
0x14001ca27  mov     ebp, 60h ; '`'
0x14001ca2c  cmovz   rsi, r15
0x14001ca30  cmovz   rbp, r14
0x14001ca34  add     rsi, rdi
0x14001ca37  cmp     dword ptr [rdi+0A0h], 1
0x14001ca3e  jnz     short loc_14001CA50
0x14001ca40  movups  xmm0, xmmword ptr [rbp+rdi+0]
0x14001ca45  movups  xmmword ptr [rsi], xmm0
0x14001ca48  test    bl, bl
0x14001ca4a  jz      short loc_14001CA9E
0x14001ca4c  xor     bl, bl
0x14001ca4e  jmp     short loc_14001CA20
0x14001ca50  xor     edx, edx; SourceString
0x14001ca52  mov     rcx, rsi; DestinationString
0x14001ca55  call    cs:__imp_RtlInitUnicodeString
0x14001ca5c  nop     dword ptr [rax+rax+00h]
0x14001ca61  movzx   edx, word ptr [rbp+rdi+0]
0x14001ca66  shr     edx, 1
0x14001ca68  jz      short loc_14001CA48
0x14001ca6a  mov     r9, [rbp+rdi+8]
0x14001ca6f  add     r9, 2
0x14001ca73  dec     edx
0x14001ca75  mov     rcx, r9
0x14001ca78  mov     r8d, edx
0x14001ca7b  call    MupFindMatchingChar
0x14001ca80  test    rax, rax
0x14001ca83  jz      short loc_14001CA48
0x14001ca85  mov     [rsi+8], rax
0x14001ca89  sub     rax, r9
0x14001ca8c  sar     rax, 1
0x14001ca8f  sub     dx, ax
0x14001ca92  add     dx, dx
0x14001ca95  mov     [rsi], dx
0x14001ca98  mov     [rsi+2], dx
0x14001ca9c  jmp     short loc_14001CA48
0x14001ca9e  add     rsp, 28h
0x14001caa2  pop     r15
0x14001caa4  pop     r14
0x14001caa6  pop     rdi
0x14001caa7  pop     rsi
0x14001caa8  pop     rbp
0x14001caa9  pop     rbx
0x14001caaa  retn
```
