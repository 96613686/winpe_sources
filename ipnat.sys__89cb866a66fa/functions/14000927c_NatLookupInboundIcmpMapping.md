# NatLookupInboundIcmpMapping

- ea: `0x14000927c`
- end: `0x140009378`
- name: `NatLookupInboundIcmpMapping`
- size: `252`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140008a54`
- `0x14000a80c`
- `0x14000adb8`
- `0x14000b5a8`

## callees

- `0x14000218c`
- `0x14000927c`
- `0x14000bbfc`

## pseudocode

```c
PVOID *__fastcall NatLookupInboundIcmpMapping(unsigned __int64 a1, unsigned __int16 a2, PVOID **a3)
{
  PVOID *i; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_id(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, a1, a2);
  }
  if ( a3 )
    *a3 = 0;
  for ( i = (PVOID *)IcmpMappingList; ; i = (PVOID *)*i )
  {
    if ( i == &IcmpMappingList )
      goto LABEL_13;
    if ( a1 <= (unsigned __int64)i[5] )
    {
      if ( a1 < (unsigned __int64)i[5] )
        goto LABEL_13;
      if ( a2 <= *((_WORD *)i + 25) )
        break;
    }
  }
  if ( a2 < *((_WORD *)i + 25) )
  {
LABEL_13:
    if ( a3 )
      *a3 = i;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x21u,
        (__int64)WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x20u,
      (__int64)WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
  }
  return i;
}

```

## disassembly

```asm
0x14000927c  push    rbx
0x14000927e  push    rbp
0x14000927f  push    rsi
0x140009280  push    rdi
0x140009281  push    r12
0x140009283  sub     rsp, 30h
0x140009287  mov     rdi, r8
0x14000928a  movzx   esi, dx
0x14000928d  mov     rbp, rcx
0x140009290  mov     rcx, cs:WPP_GLOBAL_Control
0x140009297  lea     r12, WPP_GLOBAL_Control
0x14000929e  cmp     rcx, r12
0x1400092a1  jz      short loc_1400092CC
0x1400092a3  mov     eax, [rcx+2Ch]
0x1400092a6  test    al, 1
0x1400092a8  jz      short loc_1400092CC
0x1400092aa  cmp     byte ptr [rcx+29h], 6
0x1400092ae  jb      short loc_1400092CC
0x1400092b0  mov     rcx, [rcx+18h]
0x1400092b4  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x1400092bb  mov     edx, 1Fh
0x1400092c0  mov     [rsp+58h+var_38], esi
0x1400092c4  mov     r9, rbp
0x1400092c7  call    WPP_SF_id
0x1400092cc  test    rdi, rdi
0x1400092cf  jz      short loc_1400092D8
0x1400092d1  mov     qword ptr [rdi], 0
0x1400092d8  mov     rbx, cs:IcmpMappingList
0x1400092df  lea     rcx, IcmpMappingList
0x1400092e6  jmp     short loc_1400092F9
0x1400092e8  cmp     rbp, [rbx+28h]
0x1400092ec  ja      short loc_1400092F6
0x1400092ee  jb      short loc_1400092FE
0x1400092f0  cmp     si, [rbx+32h]
0x1400092f4  jbe     short loc_140009342
0x1400092f6  mov     rbx, [rbx]
0x1400092f9  cmp     rbx, rcx
0x1400092fc  jnz     short loc_1400092E8
0x1400092fe  test    rdi, rdi
0x140009301  jz      short loc_140009306
0x140009303  mov     [rdi], rbx
0x140009306  mov     rcx, cs:WPP_GLOBAL_Control
0x14000930d  cmp     rcx, r12
0x140009310  jz      short loc_140009334
0x140009312  mov     eax, [rcx+2Ch]
0x140009315  test    al, 1
0x140009317  jz      short loc_140009334
0x140009319  cmp     byte ptr [rcx+29h], 6
0x14000931d  jb      short loc_140009334
0x14000931f  mov     rcx, [rcx+18h]
0x140009323  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x14000932a  mov     edx, 21h ; '!'
0x14000932f  call    WPP_SF_
0x140009334  xor     eax, eax
0x140009336  add     rsp, 30h
0x14000933a  pop     r12
0x14000933c  pop     rdi
0x14000933d  pop     rsi
0x14000933e  pop     rbp
0x14000933f  pop     rbx
0x140009340  retn
0x140009342  jb      short loc_1400092FE
0x140009344  mov     rcx, cs:WPP_GLOBAL_Control
0x14000934b  cmp     rcx, r12
0x14000934e  jz      short loc_140009373
0x140009350  mov     edx, [rcx+2Ch]
0x140009353  test    dl, 1
0x140009356  jz      short loc_140009373
0x140009358  cmp     byte ptr [rcx+29h], 6
0x14000935c  jb      short loc_140009373
0x14000935e  mov     rcx, [rcx+18h]
0x140009362  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140009369  mov     edx, 20h ; ' '
0x14000936e  call    WPP_SF_
0x140009373  mov     rax, rbx
0x140009376  jmp     short loc_140009336
```
