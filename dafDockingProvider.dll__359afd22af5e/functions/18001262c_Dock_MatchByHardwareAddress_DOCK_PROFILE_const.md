# Dock::MatchByHardwareAddress(_DOCK_PROFILE const *)

- ea: `0x18001262c`
- end: `0x18001268f`
- name: `?MatchByHardwareAddress@Dock@@QEBA_NPEBU_DOCK_PROFILE@@@Z`
- size: `99`
- prototype: `bool __fastcall(Dock *__hidden this, const struct _DOCK_PROFILE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800116c0`
- `0x180011b30`

## callees

- `0x18001262c`

## pseudocode

```c
bool __fastcall Dock::MatchByHardwareAddress(Dock *this, const struct _DOCK_PROFILE *a2)
{
  int v3; // r8d
  int v6; // edx

  if ( *((_BYTE *)this + 1744) )
  {
    v3 = *((_DWORD *)this + 570) - *((_DWORD *)a2 + 132);
    if ( !v3 )
      v3 = *((unsigned __int16 *)this + 1142) - *((unsigned __int16 *)a2 + 266);
    return v3 == 0;
  }
  if ( *((_BYTE *)this + 587) )
  {
    v6 = *((_DWORD *)this + 280) - *((_DWORD *)a2 + 132);
    if ( !v6 )
      v6 = *((unsigned __int16 *)this + 562) - *((unsigned __int16 *)a2 + 266);
    return v6 == 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001262c  cmp     byte ptr [rcx+6D0h], 0
0x180012633  mov     rax, rdx
0x180012636  jz      short loc_180012661
0x180012638  mov     r8d, [rcx+8E8h]
0x18001263f  sub     r8d, [rdx+210h]
0x180012646  jnz     short loc_18001265A
0x180012648  movzx   r8d, word ptr [rcx+8ECh]
0x180012650  movzx   eax, word ptr [rdx+214h]
0x180012657  sub     r8d, eax
0x18001265a  test    r8d, r8d
0x18001265d  setz    al
0x180012660  retn
0x180012661  cmp     byte ptr [rcx+24Bh], 0
0x180012668  jz      short loc_18001268C
0x18001266a  mov     edx, [rcx+460h]
0x180012670  sub     edx, [rax+210h]
0x180012676  jnz     short loc_180012688
0x180012678  movzx   edx, word ptr [rcx+464h]
0x18001267f  movzx   eax, word ptr [rax+214h]
0x180012686  sub     edx, eax
0x180012688  test    edx, edx
0x18001268a  jmp     short loc_18001265D
0x18001268c  xor     al, al
0x18001268e  retn
```
