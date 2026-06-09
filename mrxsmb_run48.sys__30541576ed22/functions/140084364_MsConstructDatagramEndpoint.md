# MsConstructDatagramEndpoint

- ea: `0x140084364`
- end: `0x1400845e0`
- name: `MsConstructDatagramEndpoint`
- size: `636`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140091980`

## callees

- `0x140010f94`
- `0x14003838c`
- `0x140059f00`
- `0x140084364`
- `0x1400845e8`
- `0x140091370`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140084425`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x140084425`
- `ntoskrnl!ExAllocatePool2` at `0x140084458`
- `ntoskrnl!ExAllocatePool2` at `0x140084458`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x1400844b4`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x1400844b4`

## pseudocode

```c
__int64 __fastcall MsConstructDatagramEndpoint(PCUNICODE_STRING SourceString, __int64 a2, __int64 *a3)
{
  __int64 ServerTransport; // rdi
  NTSTATUS v7; // ebx
  ULONG v8; // ebx
  unsigned int v9; // eax
  __int64 Pool2; // rax
  __int64 v11; // rsi
  USHORT Length; // ax
  struct _STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_5716763046b23c415144ab311ccc76f0_Traceguids, SourceString);
  }
  ServerTransport = SmbMmAllocateServerTransport(1, a2);
  if ( ServerTransport )
  {
    v8 = RtlxUnicodeStringToOemSize(SourceString) - 1;
    v9 = 42;
    *(_DWORD *)(ServerTransport + 32) = 42;
    if ( v8 > 0x10 )
    {
      v9 = v8 + 42;
      *(_DWORD *)(ServerTransport + 32) = v8 + 42;
    }
    Pool2 = ExAllocatePool2(66, v9, 1834182468);
    *(_QWORD *)(ServerTransport + 40) = Pool2;
    v11 = Pool2;
    if ( !Pool2 )
    {
      v7 = -1073741670;
LABEL_37:
      MsDereferenceDatagramEndpoint(ServerTransport);
      return (unsigned int)v7;
    }
    *(_DWORD *)Pool2 = 1;
    *(_WORD *)(Pool2 + 4) = 18;
    if ( v8 > 0x10 )
      *(_WORD *)(Pool2 + 4) = v8 + 2;
    *(_DWORD *)(Pool2 + 6) = 131089;
    DestinationString.Buffer = (PCHAR)(Pool2 + 10);
    DestinationString.MaximumLength = v8 + 1;
    v7 = RtlUpcaseUnicodeStringToOemString(&DestinationString, SourceString, 0);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          &WPP_5716763046b23c415144ab311ccc76f0_Traceguids,
          (unsigned int)v7);
      }
      goto LABEL_37;
    }
    Length = DestinationString.Length;
    if ( DestinationString.Length <= 0x10u )
    {
      memmove(&DestinationString.Buffer[DestinationString.Length], "                ", 16LL - DestinationString.Length);
      Length = DestinationString.Length;
    }
    if ( DestinationString.Buffer[Length - 1] == 42 )
    {
      if ( Length <= 0x10u )
      {
        if ( Length < 2u || DestinationString.Buffer[Length - 2] != 42 )
        {
          DestinationString.Buffer[Length - 1] = 32;
          DestinationString.Buffer[15] = 28;
          goto LABEL_36;
        }
      }
      else if ( Length != 17 || DestinationString.Buffer[15] != 42 )
      {
        v7 = -1073741634;
        goto LABEL_36;
      }
      if ( Length > 0x10u )
      {
        *(_WORD *)(v11 + 4) = 18;
      }
      else
      {
        DestinationString.Buffer[Length - 1] = 32;
        DestinationString.Buffer[DestinationString.Length - 2] = 32;
      }
      DestinationString.Buffer[15] = 27;
    }
    else
    {
      DestinationString.Buffer[15] = 0;
    }
LABEL_36:
    *(_DWORD *)(ServerTransport + 12) = 0;
    if ( v7 >= 0 )
    {
      *a3 = ServerTransport;
      return (unsigned int)v7;
    }
    goto LABEL_37;
  }
  v7 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_5716763046b23c415144ab311ccc76f0_Traceguids, 3221225626LL);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140084364  push    rbp
0x140084366  push    rbx
0x140084367  push    rsi
0x140084368  push    rdi
0x140084369  push    r12
0x14008436b  push    r13
0x14008436d  push    r14
0x14008436f  push    r15
0x140084371  mov     rbp, rsp
0x140084374  sub     rsp, 38h
0x140084378  xorps   xmm0, xmm0
0x14008437b  mov     r15, r8
0x14008437e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140084382  mov     rbx, rdx
0x140084385  mov     r14, rcx
0x140084388  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008438f  lea     rsi, WPP_GLOBAL_Control
0x140084396  cmp     rcx, rsi
0x140084399  jz      short loc_1400843C0
0x14008439b  mov     eax, [rcx+2Ch]
0x14008439e  test    al, 2
0x1400843a0  jz      short loc_1400843C0
0x1400843a2  cmp     byte ptr [rcx+29h], 4
0x1400843a6  jb      short loc_1400843C0
0x1400843a8  mov     rcx, [rcx+18h]
0x1400843ac  lea     r8, WPP_5716763046b23c415144ab311ccc76f0_Traceguids
0x1400843b3  mov     edx, 0Ah
0x1400843b8  mov     r9, r14
0x1400843bb  call    WPP_SF_Z
0x1400843c0  mov     r12d, 1
0x1400843c6  mov     rdx, rbx
0x1400843c9  mov     ecx, r12d
0x1400843cc  call    SmbMmAllocateServerTransport
0x1400843d1  mov     rdi, rax
0x1400843d4  test    rax, rax
0x1400843d7  jnz     short loc_140084422
0x1400843d9  mov     ebx, 0C000009Ah
0x1400843de  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400843e5  cmp     rcx, rsi
0x1400843e8  jz      loc_1400845CC
0x1400843ee  mov     eax, [rcx+2Ch]
0x1400843f1  test    r12b, al
0x1400843f4  jz      loc_1400845CC
0x1400843fa  cmp     [rcx+29h], r12b
0x1400843fe  jb      loc_1400845CC
0x140084404  mov     rcx, [rcx+18h]
0x140084408  lea     edx, [rdi+0Bh]
0x14008440b  mov     r9d, 0C000009Ah
0x140084411  lea     r8, WPP_5716763046b23c415144ab311ccc76f0_Traceguids
0x140084418  call    WPP_SF_d
0x14008441d  jmp     loc_1400845CC
0x140084422  mov     rcx, r14; UnicodeString
0x140084425  call    cs:__imp_RtlxUnicodeStringToOemSize
0x14008442c  nop     dword ptr [rax+rax+00h]
0x140084431  lea     ebx, [rax-1]
0x140084434  mov     eax, 2Ah ; '*'
0x140084439  mov     [rdi+20h], eax
0x14008443c  lea     r13d, [rax-1Ah]
0x140084440  cmp     ebx, r13d
0x140084443  jbe     short loc_14008444B
0x140084445  lea     eax, [rbx+2Ah]
0x140084448  mov     [rdi+20h], eax
0x14008444b  mov     edx, eax
0x14008444d  mov     ecx, 42h ; 'B'
0x140084452  mov     r8d, 6D536744h
0x140084458  call    cs:__imp_ExAllocatePool2
0x14008445f  nop     dword ptr [rax+rax+00h]
0x140084464  mov     [rdi+28h], rax
0x140084468  mov     rsi, rax
0x14008446b  test    rax, rax
0x14008446e  jnz     short loc_14008447A
0x140084470  mov     ebx, 0C000009Ah
0x140084475  jmp     loc_1400845BF
0x14008447a  mov     [rax], r12d
0x14008447d  mov     word ptr [rax+4], 12h
0x140084483  cmp     ebx, r13d
0x140084486  jbe     short loc_140084493
0x140084488  mov     eax, 2
0x14008448d  add     eax, ebx
0x14008448f  mov     [rsi+4], ax
0x140084493  mov     dword ptr [rsi+6], 20011h
0x14008449a  lea     rax, [rsi+0Ah]
0x14008449e  add     bx, r12w
0x1400844a2  mov     [rbp+DestinationString.Buffer], rax
0x1400844a6  xor     r8d, r8d; AllocateDestinationString
0x1400844a9  mov     [rbp+DestinationString.MaximumLength], bx
0x1400844ad  mov     rdx, r14; SourceString
0x1400844b0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400844b4  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x1400844bb  nop     dword ptr [rax+rax+00h]
0x1400844c0  mov     ebx, eax
0x1400844c2  test    eax, eax
0x1400844c4  jns     short loc_140084510
0x1400844c6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400844cd  lea     rax, WPP_GLOBAL_Control
0x1400844d4  cmp     rcx, rax
0x1400844d7  jz      loc_1400845BF
0x1400844dd  mov     edx, [rcx+2Ch]
0x1400844e0  test    r12b, dl
0x1400844e3  jz      loc_1400845BF
0x1400844e9  cmp     [rcx+29h], r12b
0x1400844ed  jb      loc_1400845BF
0x1400844f3  mov     rcx, [rcx+18h]
0x1400844f7  lea     r8, WPP_5716763046b23c415144ab311ccc76f0_Traceguids
0x1400844fe  mov     edx, 0Ch
0x140084503  mov     r9d, ebx
0x140084506  call    WPP_SF_d
0x14008450b  jmp     loc_1400845BF
0x140084510  movzx   eax, [rbp+DestinationString.Length]
0x140084514  cmp     ax, r13w
0x140084518  ja      short loc_140084536
0x14008451a  mov     ecx, eax
0x14008451c  lea     rdx, asc_140062A50; "                "
0x140084523  add     rcx, [rbp+DestinationString.Buffer]; void *
0x140084527  mov     r8, r13
0x14008452a  sub     r8, rax; Size
0x14008452d  call    memmove
0x140084532  movzx   eax, [rbp+DestinationString.Length]
0x140084536  mov     rcx, [rbp+DestinationString.Buffer]
0x14008453a  movzx   edx, ax
0x14008453d  cmp     byte ptr [rdx+rcx-1], 2Ah ; '*'
0x140084542  jnz     short loc_1400845B0
0x140084544  cmp     ax, r13w
0x140084548  jbe     short loc_140084564
0x14008454a  mov     r8d, 11h
0x140084550  cmp     ax, r8w
0x140084554  jnz     short loc_14008455D
0x140084556  cmp     byte ptr [rdx+rcx-2], 2Ah ; '*'
0x14008455b  jz      short loc_140084577
0x14008455d  mov     ebx, 0C00000BEh
0x140084562  jmp     short loc_1400845B4
0x140084564  mov     r8d, 2
0x14008456a  cmp     ax, r8w
0x14008456e  jb      short loc_1400845A1
0x140084570  cmp     byte ptr [rdx+rcx-2], 2Ah ; '*'
0x140084575  jnz     short loc_1400845A1
0x140084577  cmp     ax, r13w
0x14008457b  ja      short loc_140084591
0x14008457d  mov     byte ptr [rdx+rcx-1], 20h ; ' '
0x140084582  movzx   ecx, [rbp+DestinationString.Length]
0x140084586  mov     rax, [rbp+DestinationString.Buffer]
0x14008458a  mov     byte ptr [rcx+rax-2], 20h ; ' '
0x14008458f  jmp     short loc_140084597
0x140084591  mov     word ptr [rsi+4], 12h
0x140084597  mov     rax, [rbp+DestinationString.Buffer]
0x14008459b  mov     byte ptr [rax+0Fh], 1Bh
0x14008459f  jmp     short loc_1400845B4
0x1400845a1  mov     byte ptr [rdx+rcx-1], 20h ; ' '
0x1400845a6  mov     rax, [rbp+DestinationString.Buffer]
0x1400845aa  mov     byte ptr [rax+0Fh], 1Ch
0x1400845ae  jmp     short loc_1400845B4
0x1400845b0  mov     byte ptr [rcx+0Fh], 0
0x1400845b4  mov     dword ptr [rdi+0Ch], 0
0x1400845bb  test    ebx, ebx
0x1400845bd  jns     short loc_1400845C9
0x1400845bf  mov     rcx, rdi
0x1400845c2  call    MsDereferenceDatagramEndpoint
0x1400845c7  jmp     short loc_1400845CC
0x1400845c9  mov     [r15], rdi
0x1400845cc  mov     eax, ebx
0x1400845ce  add     rsp, 38h
0x1400845d2  pop     r15
0x1400845d4  pop     r14
0x1400845d6  pop     r13
0x1400845d8  pop     r12
0x1400845da  pop     rdi
0x1400845db  pop     rsi
0x1400845dc  pop     rbx
0x1400845dd  pop     rbp
0x1400845de  retn
```
