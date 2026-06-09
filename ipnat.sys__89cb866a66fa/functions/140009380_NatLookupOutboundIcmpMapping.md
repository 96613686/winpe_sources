# NatLookupOutboundIcmpMapping

- ea: `0x140009380`
- end: `0x140009480`
- name: `NatLookupOutboundIcmpMapping`
- size: `256`
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
- `0x140009380`
- `0x14000bbfc`

## pseudocode

```c
__int64 *__fastcall NatLookupOutboundIcmpMapping(unsigned __int64 a1, unsigned __int16 a2, __int64 **a3)
{
  __int64 *i; // rax
  __int64 *v7; // rdi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_id(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids, a1, a2);
  }
  if ( a3 )
    *a3 = 0;
  for ( i = (__int64 *)qword_14003E4B0; ; i = (__int64 *)*i )
  {
    if ( i == &qword_14003E4B0 )
      goto LABEL_13;
    v7 = i - 2;
    if ( a1 <= i[2] )
    {
      if ( a1 < i[2] )
        goto LABEL_13;
      if ( a2 <= *((_WORD *)v7 + 24) )
        break;
    }
  }
  if ( a2 < *((_WORD *)v7 + 24) )
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
        0x24u,
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
      0x23u,
      (__int64)WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x140009380  push    rbx
0x140009382  push    rbp
0x140009383  push    rsi
0x140009384  push    rdi
0x140009385  push    r12
0x140009387  sub     rsp, 30h
0x14000938b  mov     rbx, r8
0x14000938e  movzx   esi, dx
0x140009391  mov     rbp, rcx
0x140009394  mov     rcx, cs:WPP_GLOBAL_Control
0x14000939b  lea     r12, WPP_GLOBAL_Control
0x1400093a2  cmp     rcx, r12
0x1400093a5  jz      short loc_1400093D0
0x1400093a7  mov     eax, [rcx+2Ch]
0x1400093aa  test    al, 1
0x1400093ac  jz      short loc_1400093D0
0x1400093ae  cmp     byte ptr [rcx+29h], 6
0x1400093b2  jb      short loc_1400093D0
0x1400093b4  mov     rcx, [rcx+18h]
0x1400093b8  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x1400093bf  mov     edx, 22h ; '"'
0x1400093c4  mov     [rsp+58h+var_38], esi
0x1400093c8  mov     r9, rbp
0x1400093cb  call    WPP_SF_id
0x1400093d0  test    rbx, rbx
0x1400093d3  jz      short loc_1400093DC
0x1400093d5  mov     qword ptr [rbx], 0
0x1400093dc  mov     rax, cs:qword_14003E4B0
0x1400093e3  lea     rdx, qword_14003E4B0
0x1400093ea  jmp     short loc_140009401
0x1400093ec  lea     rdi, [rax-10h]
0x1400093f0  cmp     rbp, [rdi+20h]
0x1400093f4  ja      short loc_1400093FE
0x1400093f6  jb      short loc_140009406
0x1400093f8  cmp     si, [rdi+30h]
0x1400093fc  jbe     short loc_14000944A
0x1400093fe  mov     rax, [rax]
0x140009401  cmp     rax, rdx
0x140009404  jnz     short loc_1400093EC
0x140009406  test    rbx, rbx
0x140009409  jz      short loc_14000940E
0x14000940b  mov     [rbx], rax
0x14000940e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009415  cmp     rcx, r12
0x140009418  jz      short loc_14000943C
0x14000941a  mov     eax, [rcx+2Ch]
0x14000941d  test    al, 1
0x14000941f  jz      short loc_14000943C
0x140009421  cmp     byte ptr [rcx+29h], 6
0x140009425  jb      short loc_14000943C
0x140009427  mov     rcx, [rcx+18h]
0x14000942b  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140009432  mov     edx, 24h ; '$'
0x140009437  call    WPP_SF_
0x14000943c  xor     eax, eax
0x14000943e  add     rsp, 30h
0x140009442  pop     r12
0x140009444  pop     rdi
0x140009445  pop     rsi
0x140009446  pop     rbp
0x140009447  pop     rbx
0x140009448  retn
0x14000944a  jb      short loc_140009406
0x14000944c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009453  cmp     rcx, r12
0x140009456  jz      short loc_14000947B
0x140009458  mov     edx, [rcx+2Ch]
0x14000945b  test    dl, 1
0x14000945e  jz      short loc_14000947B
0x140009460  cmp     byte ptr [rcx+29h], 6
0x140009464  jb      short loc_14000947B
0x140009466  mov     rcx, [rcx+18h]
0x14000946a  lea     r8, WPP_73bb856522d9310d97ee5808f51e0a33_Traceguids
0x140009471  mov     edx, 23h ; '#'
0x140009476  call    WPP_SF_
0x14000947b  mov     rax, rdi
0x14000947e  jmp     short loc_14000943E
```
