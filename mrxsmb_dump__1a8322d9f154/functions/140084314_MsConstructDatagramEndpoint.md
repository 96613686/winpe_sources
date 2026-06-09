# MsConstructDatagramEndpoint

- ea: `0x140084314`
- end: `0x140084590`
- name: `MsConstructDatagramEndpoint`
- size: `636`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140091930`

## callees

- `0x140010f94`
- `0x14003838c`
- `0x140059f00`
- `0x140084314`
- `0x140084598`
- `0x140091320`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x1400843d5`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x1400843d5`
- `ntoskrnl!ExAllocatePool2` at `0x140084408`
- `ntoskrnl!ExAllocatePool2` at `0x140084408`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x140084464`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x140084464`

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
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_5716763046b23c415144ab311ccc76f0_Traceguids, SourceString);
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
          WPP_5716763046b23c415144ab311ccc76f0_Traceguids,
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_5716763046b23c415144ab311ccc76f0_Traceguids, 3221225626LL);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140084314  push    rbp
0x140084316  push    rbx
0x140084317  push    rsi
0x140084318  push    rdi
0x140084319  push    r12
0x14008431b  push    r13
0x14008431d  push    r14
0x14008431f  push    r15
0x140084321  mov     rbp, rsp
0x140084324  sub     rsp, 38h
0x140084328  xorps   xmm0, xmm0
0x14008432b  mov     r15, r8
0x14008432e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140084332  mov     rbx, rdx
0x140084335  mov     r14, rcx
0x140084338  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008433f  lea     rsi, WPP_GLOBAL_Control
0x140084346  cmp     rcx, rsi
0x140084349  jz      short loc_140084370
0x14008434b  mov     eax, [rcx+2Ch]
0x14008434e  test    al, 2
0x140084350  jz      short loc_140084370
0x140084352  cmp     byte ptr [rcx+29h], 4
0x140084356  jb      short loc_140084370
0x140084358  mov     rcx, [rcx+18h]
0x14008435c  lea     r8, WPP_5716763046b23c415144ab311ccc76f0_Traceguids
0x140084363  mov     edx, 0Ah
0x140084368  mov     r9, r14
0x14008436b  call    WPP_SF_Z
0x140084370  mov     r12d, 1
0x140084376  mov     rdx, rbx
0x140084379  mov     ecx, r12d
0x14008437c  call    SmbMmAllocateServerTransport
0x140084381  mov     rdi, rax
0x140084384  test    rax, rax
0x140084387  jnz     short loc_1400843D2
0x140084389  mov     ebx, 0C000009Ah
0x14008438e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140084395  cmp     rcx, rsi
0x140084398  jz      loc_14008457C
0x14008439e  mov     eax, [rcx+2Ch]
0x1400843a1  test    r12b, al
0x1400843a4  jz      loc_14008457C
0x1400843aa  cmp     [rcx+29h], r12b
0x1400843ae  jb      loc_14008457C
0x1400843b4  mov     rcx, [rcx+18h]
0x1400843b8  lea     edx, [rdi+0Bh]
0x1400843bb  mov     r9d, 0C000009Ah
0x1400843c1  lea     r8, WPP_5716763046b23c415144ab311ccc76f0_Traceguids
0x1400843c8  call    WPP_SF_d
0x1400843cd  jmp     loc_14008457C
0x1400843d2  mov     rcx, r14; UnicodeString
0x1400843d5  call    cs:__imp_RtlxUnicodeStringToOemSize
0x1400843dc  nop     dword ptr [rax+rax+00h]
0x1400843e1  lea     ebx, [rax-1]
0x1400843e4  mov     eax, 2Ah ; '*'
0x1400843e9  mov     [rdi+20h], eax
0x1400843ec  lea     r13d, [rax-1Ah]
0x1400843f0  cmp     ebx, r13d
0x1400843f3  jbe     short loc_1400843FB
0x1400843f5  lea     eax, [rbx+2Ah]
0x1400843f8  mov     [rdi+20h], eax
0x1400843fb  mov     edx, eax
0x1400843fd  mov     ecx, 42h ; 'B'
0x140084402  mov     r8d, 6D536744h
0x140084408  call    cs:__imp_ExAllocatePool2
0x14008440f  nop     dword ptr [rax+rax+00h]
0x140084414  mov     [rdi+28h], rax
0x140084418  mov     rsi, rax
0x14008441b  test    rax, rax
0x14008441e  jnz     short loc_14008442A
0x140084420  mov     ebx, 0C000009Ah
0x140084425  jmp     loc_14008456F
0x14008442a  mov     [rax], r12d
0x14008442d  mov     word ptr [rax+4], 12h
0x140084433  cmp     ebx, r13d
0x140084436  jbe     short loc_140084443
0x140084438  mov     eax, 2
0x14008443d  add     eax, ebx
0x14008443f  mov     [rsi+4], ax
0x140084443  mov     dword ptr [rsi+6], 20011h
0x14008444a  lea     rax, [rsi+0Ah]
0x14008444e  add     bx, r12w
0x140084452  mov     [rbp+DestinationString.Buffer], rax
0x140084456  xor     r8d, r8d; AllocateDestinationString
0x140084459  mov     [rbp+DestinationString.MaximumLength], bx
0x14008445d  mov     rdx, r14; SourceString
0x140084460  lea     rcx, [rbp+DestinationString]; DestinationString
0x140084464  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x14008446b  nop     dword ptr [rax+rax+00h]
0x140084470  mov     ebx, eax
0x140084472  test    eax, eax
0x140084474  jns     short loc_1400844C0
0x140084476  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008447d  lea     rax, WPP_GLOBAL_Control
0x140084484  cmp     rcx, rax
0x140084487  jz      loc_14008456F
0x14008448d  mov     edx, [rcx+2Ch]
0x140084490  test    r12b, dl
0x140084493  jz      loc_14008456F
0x140084499  cmp     [rcx+29h], r12b
0x14008449d  jb      loc_14008456F
0x1400844a3  mov     rcx, [rcx+18h]
0x1400844a7  lea     r8, WPP_5716763046b23c415144ab311ccc76f0_Traceguids
0x1400844ae  mov     edx, 0Ch
0x1400844b3  mov     r9d, ebx
0x1400844b6  call    WPP_SF_d
0x1400844bb  jmp     loc_14008456F
0x1400844c0  movzx   eax, [rbp+DestinationString.Length]
0x1400844c4  cmp     ax, r13w
0x1400844c8  ja      short loc_1400844E6
0x1400844ca  mov     ecx, eax
0x1400844cc  lea     rdx, asc_140062A40; "                "
0x1400844d3  add     rcx, [rbp+DestinationString.Buffer]; void *
0x1400844d7  mov     r8, r13
0x1400844da  sub     r8, rax; Size
0x1400844dd  call    memmove
0x1400844e2  movzx   eax, [rbp+DestinationString.Length]
0x1400844e6  mov     rcx, [rbp+DestinationString.Buffer]
0x1400844ea  movzx   edx, ax
0x1400844ed  cmp     byte ptr [rdx+rcx-1], 2Ah ; '*'
0x1400844f2  jnz     short loc_140084560
0x1400844f4  cmp     ax, r13w
0x1400844f8  jbe     short loc_140084514
0x1400844fa  mov     r8d, 11h
0x140084500  cmp     ax, r8w
0x140084504  jnz     short loc_14008450D
0x140084506  cmp     byte ptr [rdx+rcx-2], 2Ah ; '*'
0x14008450b  jz      short loc_140084527
0x14008450d  mov     ebx, 0C00000BEh
0x140084512  jmp     short loc_140084564
0x140084514  mov     r8d, 2
0x14008451a  cmp     ax, r8w
0x14008451e  jb      short loc_140084551
0x140084520  cmp     byte ptr [rdx+rcx-2], 2Ah ; '*'
0x140084525  jnz     short loc_140084551
0x140084527  cmp     ax, r13w
0x14008452b  ja      short loc_140084541
0x14008452d  mov     byte ptr [rdx+rcx-1], 20h ; ' '
0x140084532  movzx   ecx, [rbp+DestinationString.Length]
0x140084536  mov     rax, [rbp+DestinationString.Buffer]
0x14008453a  mov     byte ptr [rcx+rax-2], 20h ; ' '
0x14008453f  jmp     short loc_140084547
0x140084541  mov     word ptr [rsi+4], 12h
0x140084547  mov     rax, [rbp+DestinationString.Buffer]
0x14008454b  mov     byte ptr [rax+0Fh], 1Bh
0x14008454f  jmp     short loc_140084564
0x140084551  mov     byte ptr [rdx+rcx-1], 20h ; ' '
0x140084556  mov     rax, [rbp+DestinationString.Buffer]
0x14008455a  mov     byte ptr [rax+0Fh], 1Ch
0x14008455e  jmp     short loc_140084564
0x140084560  mov     byte ptr [rcx+0Fh], 0
0x140084564  mov     dword ptr [rdi+0Ch], 0
0x14008456b  test    ebx, ebx
0x14008456d  jns     short loc_140084579
0x14008456f  mov     rcx, rdi
0x140084572  call    MsDereferenceDatagramEndpoint
0x140084577  jmp     short loc_14008457C
0x140084579  mov     [r15], rdi
0x14008457c  mov     eax, ebx
0x14008457e  add     rsp, 38h
0x140084582  pop     r15
0x140084584  pop     r14
0x140084586  pop     r13
0x140084588  pop     r12
0x14008458a  pop     rdi
0x14008458b  pop     rsi
0x14008458c  pop     rbx
0x14008458d  pop     rbp
0x14008458e  retn
```
