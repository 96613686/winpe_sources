# MupSaveStrippedFileName

- ea: `0x14001cac0`
- end: `0x14001cb70`
- name: `MupSaveStrippedFileName`
- size: `176`
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
- `0x14001cac0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001cb19`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001cb19`

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
0x14001cac0  push    rbx
0x14001cac2  push    rbp
0x14001cac3  push    rsi
0x14001cac4  push    rdi
0x14001cac5  push    r14
0x14001cac7  push    r15
0x14001cac9  sub     rsp, 28h
0x14001cacd  movzx   ebx, dl
0x14001cad0  mov     rdi, rcx
0x14001cad3  mov     r14d, 38h ; '8'
0x14001cad9  mov     r15d, 48h ; 'H'
0x14001cadf  nop
0x14001cae0  mov     eax, [rdi+0A0h]
0x14001cae6  test    bl, bl
0x14001cae8  mov     esi, 80h
0x14001caed  mov     ebp, 70h ; 'p'
0x14001caf2  cmovz   rsi, r15
0x14001caf6  cmovz   rbp, r14
0x14001cafa  add     rsi, rdi
0x14001cafd  dec     eax
0x14001caff  cmp     eax, 1
0x14001cb02  ja      short loc_14001CB14
0x14001cb04  movups  xmm0, xmmword ptr [rbp+rdi+0]
0x14001cb09  movups  xmmword ptr [rsi], xmm0
0x14001cb0c  test    bl, bl
0x14001cb0e  jz      short loc_14001CB62
0x14001cb10  xor     bl, bl
0x14001cb12  jmp     short loc_14001CAE0
0x14001cb14  xor     edx, edx; SourceString
0x14001cb16  mov     rcx, rsi; DestinationString
0x14001cb19  call    cs:__imp_RtlInitUnicodeString
0x14001cb20  nop     dword ptr [rax+rax+00h]
0x14001cb25  movzx   edx, word ptr [rbp+rdi+0]
0x14001cb2a  shr     edx, 1
0x14001cb2c  jz      short loc_14001CB0C
0x14001cb2e  mov     r9, [rbp+rdi+8]
0x14001cb33  add     r9, 2
0x14001cb37  dec     edx
0x14001cb39  mov     rcx, r9
0x14001cb3c  mov     r8d, edx
0x14001cb3f  call    MupFindMatchingChar
0x14001cb44  test    rax, rax
0x14001cb47  jz      short loc_14001CB0C
0x14001cb49  mov     [rsi+8], rax
0x14001cb4d  sub     rax, r9
0x14001cb50  sar     rax, 1
0x14001cb53  sub     dx, ax
0x14001cb56  add     dx, dx
0x14001cb59  mov     [rsi], dx
0x14001cb5c  mov     [rsi+2], dx
0x14001cb60  jmp     short loc_14001CB0C
0x14001cb62  add     rsp, 28h
0x14001cb66  pop     r15
0x14001cb68  pop     r14
0x14001cb6a  pop     rdi
0x14001cb6b  pop     rsi
0x14001cb6c  pop     rbp
0x14001cb6d  pop     rbx
0x14001cb6e  retn
```
