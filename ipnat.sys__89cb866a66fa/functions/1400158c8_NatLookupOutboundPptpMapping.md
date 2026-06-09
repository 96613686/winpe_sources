# NatLookupOutboundPptpMapping

- ea: `0x1400158c8`
- end: `0x1400159bc`
- name: `NatLookupOutboundPptpMapping`
- size: `244`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140014bac`
- `0x140015be8`
- `0x1400166d0`

## callees

- `0x14000218c`
- `0x14000bbfc`
- `0x1400158c8`

## pseudocode

```c
__int64 *__fastcall NatLookupOutboundPptpMapping(unsigned __int64 a1, unsigned __int16 a2, __int64 **a3)
{
  __int64 *i; // rax
  __int64 *v7; // rbx
  int v9; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v9 = a2;
    WPP_SF_id(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x20u,
      (__int64)WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids,
      a1,
      v9);
  }
  for ( i = (__int64 *)qword_1400320D0; ; i = (__int64 *)*i )
  {
    if ( i == &qword_1400320D0 )
      goto LABEL_11;
    v7 = i - 2;
    if ( a1 <= i[2] )
    {
      if ( a1 < i[2] )
        goto LABEL_11;
      if ( a2 <= *((_WORD *)v7 + 26) )
        break;
    }
  }
  if ( a2 < *((_WORD *)v7 + 26) )
  {
LABEL_11:
    if ( a3 )
      *a3 = i;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x22u,
        (__int64)WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x21u,
      (__int64)WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x1400158c8  push    rbx
0x1400158ca  push    rbp
0x1400158cb  push    rsi
0x1400158cc  push    rdi
0x1400158cd  push    r12
0x1400158cf  sub     rsp, 30h
0x1400158d3  mov     rsi, r8
0x1400158d6  movzx   edi, dx
0x1400158d9  mov     rbp, rcx
0x1400158dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158e3  lea     r12, WPP_GLOBAL_Control
0x1400158ea  cmp     rcx, r12
0x1400158ed  jz      short loc_140015918
0x1400158ef  mov     eax, [rcx+2Ch]
0x1400158f2  test    al, 1
0x1400158f4  jz      short loc_140015918
0x1400158f6  cmp     byte ptr [rcx+29h], 6
0x1400158fa  jb      short loc_140015918
0x1400158fc  mov     rcx, [rcx+18h]
0x140015900  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140015907  mov     edx, 20h ; ' '
0x14001590c  mov     [rsp+58h+var_38], edi
0x140015910  mov     r9, rbp
0x140015913  call    WPP_SF_id
0x140015918  mov     rax, cs:qword_1400320D0
0x14001591f  lea     rdx, qword_1400320D0
0x140015926  jmp     short loc_14001593D
0x140015928  lea     rbx, [rax-10h]
0x14001592c  cmp     rbp, [rbx+20h]
0x140015930  ja      short loc_14001593A
0x140015932  jb      short loc_140015942
0x140015934  cmp     di, [rbx+34h]
0x140015938  jbe     short loc_140015986
0x14001593a  mov     rax, [rax]
0x14001593d  cmp     rax, rdx
0x140015940  jnz     short loc_140015928
0x140015942  test    rsi, rsi
0x140015945  jz      short loc_14001594A
0x140015947  mov     [rsi], rax
0x14001594a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015951  cmp     rcx, r12
0x140015954  jz      short loc_140015978
0x140015956  mov     eax, [rcx+2Ch]
0x140015959  test    al, 1
0x14001595b  jz      short loc_140015978
0x14001595d  cmp     byte ptr [rcx+29h], 6
0x140015961  jb      short loc_140015978
0x140015963  mov     rcx, [rcx+18h]
0x140015967  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x14001596e  mov     edx, 22h ; '"'
0x140015973  call    WPP_SF_
0x140015978  xor     eax, eax
0x14001597a  add     rsp, 30h
0x14001597e  pop     r12
0x140015980  pop     rdi
0x140015981  pop     rsi
0x140015982  pop     rbp
0x140015983  pop     rbx
0x140015984  retn
0x140015986  jb      short loc_140015942
0x140015988  mov     rcx, cs:WPP_GLOBAL_Control
0x14001598f  cmp     rcx, r12
0x140015992  jz      short loc_1400159B7
0x140015994  mov     edx, [rcx+2Ch]
0x140015997  test    dl, 1
0x14001599a  jz      short loc_1400159B7
0x14001599c  cmp     byte ptr [rcx+29h], 6
0x1400159a0  jb      short loc_1400159B7
0x1400159a2  mov     rcx, [rcx+18h]
0x1400159a6  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x1400159ad  mov     edx, 21h ; '!'
0x1400159b2  call    WPP_SF_
0x1400159b7  mov     rax, rbx
0x1400159ba  jmp     short loc_14001597A
```
