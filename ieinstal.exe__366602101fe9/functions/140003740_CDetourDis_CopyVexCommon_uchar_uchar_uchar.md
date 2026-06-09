# CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)

- ea: `0x140003740`
- end: `0x1400037f7`
- name: `?CopyVexCommon@CDetourDis@@IEAAPEAEEPEAE0@Z`
- size: `183`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, unsigned __int8, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400036c0`
- `0x1400036f0`

## callees

- `0x140003740`
- `0x140011010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyVexCommon(
        CDetourDis *this,
        char a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // r10

  *((_DWORD *)this + 3) = 1;
  switch ( a2 )
  {
    case 1:
      v4 = (__int64 *)(&CDetourDis::s_rceCopyTable0F + 2 * *a4);
      break;
    case 2:
      v4 = &qword_14001B190;
      break;
    case 3:
      v4 = &qword_14001B1A0;
      break;
    default:
      v4 = &qword_14001B1B0;
      break;
  }
  switch ( *(a4 - 1) & 3 )
  {
    case 1:
      *(_DWORD *)this = 1;
      break;
    case 2:
      *((_DWORD *)this + 5) = 1;
      return (unsigned __int8 *)((__int64 (__fastcall *)(CDetourDis *, __int64 *, unsigned __int8 *))v4[1])(
                                  this,
                                  v4,
                                  a3);
    case 3:
      *((_DWORD *)this + 4) = 1;
      return (unsigned __int8 *)((__int64 (__fastcall *)(CDetourDis *, __int64 *, unsigned __int8 *))v4[1])(
                                  this,
                                  v4,
                                  a3);
  }
  return (unsigned __int8 *)((__int64 (__fastcall *)(CDetourDis *, __int64 *, unsigned __int8 *))v4[1])(this, v4, a3);
}

```

## disassembly

```asm
0x140003740  sub     rsp, 38h
0x140003744  movzx   r10d, dl
0x140003748  mov     r11, rcx
0x14000374b  mov     dword ptr [rcx+0Ch], 1
0x140003752  sub     r10d, 1
0x140003756  jz      short loc_14000377F
0x140003758  sub     r10d, 1
0x14000375c  jz      short loc_140003776
0x14000375e  cmp     r10d, 1
0x140003762  jz      short loc_14000376D
0x140003764  lea     r10, qword_14001B1B0
0x14000376b  jmp     short loc_140003791
0x14000376d  lea     r10, qword_14001B1A0
0x140003774  jmp     short loc_140003791
0x140003776  lea     r10, qword_14001B190
0x14000377d  jmp     short loc_140003791
0x14000377f  movzx   r10d, byte ptr [r9]
0x140003783  lea     rax, ?s_rceCopyTable0F@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable0F
0x14000378a  shl     r10, 4
0x14000378e  add     r10, rax
0x140003791  movzx   ecx, byte ptr [r9-1]
0x140003796  and     ecx, 3
0x140003799  sub     ecx, 1
0x14000379c  jz      short loc_1400037DC
0x14000379e  sub     ecx, 1
0x1400037a1  jz      short loc_1400037C0
0x1400037a3  cmp     ecx, 1
0x1400037a6  jnz     short loc_1400037E3
0x1400037a8  mov     [r11+10h], ecx
0x1400037ac  mov     rdx, r10
0x1400037af  mov     rax, [r10+8]
0x1400037b3  mov     rcx, r11
0x1400037b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037bb  add     rsp, 38h
0x1400037bf  retn
0x1400037c0  mov     dword ptr [r11+14h], 1
0x1400037c8  mov     rdx, r10
0x1400037cb  mov     rax, [r10+8]
0x1400037cf  mov     rcx, r11
0x1400037d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037d7  add     rsp, 38h
0x1400037db  retn
0x1400037dc  mov     dword ptr [r11], 1
0x1400037e3  mov     rax, [r10+8]
0x1400037e7  mov     rdx, r10
0x1400037ea  mov     rcx, r11
0x1400037ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037f2  add     rsp, 38h
0x1400037f6  retn
```
