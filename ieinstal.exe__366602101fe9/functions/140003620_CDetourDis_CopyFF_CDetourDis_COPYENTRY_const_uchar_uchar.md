# CDetourDis::CopyFF(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x140003620`
- end: `0x1400036b4`
- name: `?CopyFF@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `148`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400030a0`
- `0x140003620`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyFF(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *v6; // r8
  unsigned __int8 v7; // al
  unsigned __int8 *v9; // rax

  v6 = CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)&qword_14001B180, a3, a4);
  v7 = a4[1];
  if ( ((v7 - 21) & 0xEF) != 0 )
  {
    if ( (((v7 & 0x30) - 16) & 0xEF) != 0 )
      return v6;
LABEL_3:
    **((_QWORD **)this + 4) = -1;
    return v6;
  }
  if ( (unsigned __int8)(*((_BYTE *)this + 24) - 100) <= 1u )
    goto LABEL_3;
  v9 = &a4[*(int *)(a4 + 2) + 6];
  if ( CDetourDis::s_fLimitReferencesToModule )
  {
    if ( v9 < CDetourDis::s_pbModuleBeg || v9 >= CDetourDis::s_pbModuleEnd )
      goto LABEL_3;
  }
  **((_QWORD **)this + 4) = *(_QWORD *)v9;
  return v6;
}

```

## disassembly

```asm
0x140003620  mov     [rsp+arg_0], rbx
0x140003625  push    rdi
0x140003626  sub     rsp, 20h
0x14000362a  lea     rdx, qword_14001B180; struct CDetourDis::COPYENTRY *
0x140003631  mov     rdi, r9
0x140003634  mov     rbx, rcx
0x140003637  call    ?CopyBytes@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x14000363c  mov     r8, rax
0x14000363f  movzx   eax, byte ptr [rdi+1]
0x140003643  lea     edx, [rax-15h]
0x140003646  test    dl, 0EFh
0x140003649  jz      short loc_14000366C
0x14000364b  and     al, 30h
0x14000364d  sub     al, 10h
0x14000364f  test    al, 0EFh
0x140003651  jnz     short loc_14000365E
0x140003653  mov     rax, [rbx+20h]
0x140003657  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x14000365e  mov     rax, r8
0x140003661  mov     rbx, [rsp+28h+arg_0]
0x140003666  add     rsp, 20h
0x14000366a  pop     rdi
0x14000366b  retn
0x14000366c  movzx   eax, byte ptr [rbx+18h]
0x140003670  sub     al, 64h ; 'd'
0x140003672  cmp     al, 1
0x140003674  jbe     short loc_140003653
0x140003676  movsxd  rax, dword ptr [rdi+2]
0x14000367a  add     rax, 6
0x14000367e  add     rax, rdi
0x140003681  cmp     cs:?s_fLimitReferencesToModule@CDetourDis@@1HA, 0; int CDetourDis::s_fLimitReferencesToModule
0x140003688  jz      short loc_14000369C
0x14000368a  cmp     rax, cs:?s_pbModuleBeg@CDetourDis@@1PEAEEA; uchar * CDetourDis::s_pbModuleBeg
0x140003691  jb      short loc_140003653
0x140003693  cmp     rax, cs:?s_pbModuleEnd@CDetourDis@@1PEAEEA; uchar * CDetourDis::s_pbModuleEnd
0x14000369a  jnb     short loc_140003653
0x14000369c  mov     rcx, [rbx+20h]
0x1400036a0  mov     rax, [rax]
0x1400036a3  mov     rbx, [rsp+28h+arg_0]
0x1400036a8  mov     [rcx], rax
0x1400036ab  mov     rax, r8
0x1400036ae  add     rsp, 20h
0x1400036b2  pop     rdi
0x1400036b3  retn
```
