# COleObject::CheckForHandleHit(tagPOINT const &)

- ea: `0x180054428`
- end: `0x18005462a`
- name: `?CheckForHandleHit@COleObject@@QEAAPEAGAEBUtagPOINT@@@Z`
- size: `514`
- prototype: `unsigned __int16 *(COleObject *__hidden this, const struct tagPOINT *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002bbe0`
- `0x180055c28`

## callees

- `0x180054428`
- `0x180056050`
- `0x180093c00`

## import_xrefs

- `USER32!CopyRect` at `0x180054488`
- `USER32!CopyRect` at `0x180054488`
- `USER32!PtInRect` at `0x1800544d0`
- `USER32!PtInRect` at `0x1800544d0`
- `USER32!InflateRect` at `0x1800544bd`
- `USER32!InflateRect` at `0x1800544f0`
- `USER32!InflateRect` at `0x1800544bd`
- `USER32!InflateRect` at `0x1800544f0`

## pseudocode

```c
__int64 __fastcall COleObject::CheckForHandleHit(COleObject *this, const struct tagPOINT *a2)
{
  __int16 v2; // si
  __int64 v5; // rax
  COleObject *v6; // rcx
  COleObject *v7; // rcx
  COleObject *v8; // rcx
  COleObject *v9; // rcx
  COleObject *v10; // rcx
  COleObject *v11; // rcx
  COleObject *v12; // rcx
  COleObject *v13; // rcx
  struct tagRECT rcDst; // [rsp+20h] [rbp-20h] BYREF

  v2 = 1;
  rcDst = 0;
  if ( (*((_BYTE *)this + 144) & 1) != 0 )
  {
    v5 = *((_QWORD *)this + 8);
    if ( !v5 || (*(_BYTE *)(v5 + 180) & 4) == 0 )
    {
      CopyRect(&rcDst, (const RECT *)((char *)this + 88));
      if ( *((_WORD *)this + 78) )
        v2 = *((_WORD *)this + 78);
      else
        *((_WORD *)this + 78) = 1;
      InflateRect(&rcDst, -6 - v2, -6 - v2);
      if ( !PtInRect(&rcDst, *a2) )
      {
        InflateRect(&rcDst, 6, 6);
        if ( (unsigned int)COleObject::InHandle(v6, rcDst.left, rcDst.top, a2)
          || (unsigned int)COleObject::InHandle(v7, rcDst.right - 6, rcDst.bottom - 6, a2) )
        {
          return 32642;
        }
        if ( (unsigned int)COleObject::InHandle(v8, rcDst.left, rcDst.top + (rcDst.bottom - rcDst.top - 6) / 2, a2)
          || (unsigned int)COleObject::InHandle(v9, rcDst.right - 6, rcDst.top + (rcDst.bottom - rcDst.top - 6) / 2, a2) )
        {
          return 32644;
        }
        if ( (unsigned int)COleObject::InHandle(v10, rcDst.left, rcDst.bottom - 6, a2)
          || (unsigned int)COleObject::InHandle(v11, rcDst.right - 6, rcDst.top, a2) )
        {
          return 32643;
        }
        if ( (unsigned int)COleObject::InHandle(v12, rcDst.left + (rcDst.right - rcDst.left - 6) / 2, rcDst.top, a2)
          || (unsigned int)COleObject::InHandle(
                             v13,
                             rcDst.left + (rcDst.right - rcDst.left - 6) / 2,
                             rcDst.bottom - 6,
                             a2) )
        {
          return 32645;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180054428  mov     [rsp-18h+arg_10], rbx
0x18005442d  mov     [rsp-18h+arg_18], rsi
0x180054432  push    rbp
0x180054433  push    rdi
0x180054434  push    r14
0x180054436  mov     rbp, rsp
0x180054439  sub     rsp, 40h
0x18005443d  mov     rax, cs:__security_cookie
0x180054444  xor     rax, rsp
0x180054447  mov     [rbp+var_10], rax
0x18005444b  mov     esi, 1
0x180054450  xorps   xmm0, xmm0
0x180054453  mov     rdi, rdx
0x180054456  mov     rbx, rcx
0x180054459  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x18005445d  test    [rcx+90h], sil
0x180054464  jz      loc_180054608
0x18005446a  mov     rax, [rcx+40h]
0x18005446e  test    rax, rax
0x180054471  jz      short loc_180054480
0x180054473  test    byte ptr [rax+0B4h], 4
0x18005447a  jnz     loc_180054608
0x180054480  lea     rdx, [rcx+58h]; lprcSrc
0x180054484  lea     rcx, [rbp+rcDst]; lprcDst
0x180054488  call    cs:__imp_CopyRect
0x18005448f  nop     dword ptr [rax+rax+00h]
0x180054494  movzx   eax, word ptr [rbx+9Ch]
0x18005449b  test    ax, ax
0x18005449e  jnz     short loc_1800544A9
0x1800544a0  mov     [rbx+9Ch], si
0x1800544a7  jmp     short loc_1800544AC
0x1800544a9  movzx   esi, ax
0x1800544ac  movsx   eax, si
0x1800544af  lea     rcx, [rbp+rcDst]; lprc
0x1800544b3  mov     edx, 0FFFFFFFAh
0x1800544b8  sub     edx, eax; dx
0x1800544ba  mov     r8d, edx; dy
0x1800544bd  call    cs:__imp_InflateRect
0x1800544c4  nop     dword ptr [rax+rax+00h]
0x1800544c9  mov     rdx, [rdi]; pt
0x1800544cc  lea     rcx, [rbp+rcDst]; lprc
0x1800544d0  call    cs:__imp_PtInRect
0x1800544d7  nop     dword ptr [rax+rax+00h]
0x1800544dc  test    eax, eax
0x1800544de  jnz     loc_180054608
0x1800544e4  lea     ebx, [rax+6]
0x1800544e7  mov     r8d, ebx; dy
0x1800544ea  lea     rcx, [rbp+rcDst]; lprc
0x1800544ee  mov     edx, ebx; dx
0x1800544f0  call    cs:__imp_InflateRect
0x1800544f7  nop     dword ptr [rax+rax+00h]
0x1800544fc  mov     r8d, [rbp+rcDst.top]; int
0x180054500  mov     r9, rdi; struct tagPOINT *
0x180054503  mov     edx, [rbp+rcDst.left]; int
0x180054506  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x18005450b  test    eax, eax
0x18005450d  jnz     loc_180054601
0x180054513  mov     r8d, [rbp+rcDst.bottom]
0x180054517  mov     r9, rdi; struct tagPOINT *
0x18005451a  mov     edx, [rbp+rcDst.right]
0x18005451d  add     r8d, 0FFFFFFFAh; int
0x180054521  add     edx, 0FFFFFFFAh; int
0x180054524  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180054529  test    eax, eax
0x18005452b  jnz     loc_180054601
0x180054531  mov     eax, [rbp+rcDst.bottom]
0x180054534  lea     esi, [rbx-4]
0x180054537  sub     eax, [rbp+rcDst.top]
0x18005453a  mov     r9, rdi; struct tagPOINT *
0x18005453d  sub     eax, ebx
0x18005453f  cdq
0x180054540  idiv    esi
0x180054542  mov     edx, [rbp+rcDst.left]; int
0x180054545  add     eax, [rbp+rcDst.top]
0x180054548  mov     r8d, eax; int
0x18005454b  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180054550  test    eax, eax
0x180054552  jnz     loc_1800545FA
0x180054558  mov     eax, [rbp+rcDst.bottom]
0x18005455b  mov     r9, rdi; struct tagPOINT *
0x18005455e  sub     eax, [rbp+rcDst.top]
0x180054561  sub     eax, ebx
0x180054563  cdq
0x180054564  idiv    esi
0x180054566  mov     edx, [rbp+rcDst.right]
0x180054569  add     eax, [rbp+rcDst.top]
0x18005456c  add     edx, 0FFFFFFFAh; int
0x18005456f  mov     r8d, eax; int
0x180054572  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180054577  test    eax, eax
0x180054579  jnz     short loc_1800545FA
0x18005457b  mov     r8d, [rbp+rcDst.bottom]
0x18005457f  mov     r9, rdi; struct tagPOINT *
0x180054582  mov     edx, [rbp+rcDst.left]; int
0x180054585  add     r8d, 0FFFFFFFAh; int
0x180054589  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x18005458e  test    eax, eax
0x180054590  jnz     short loc_1800545F3
0x180054592  mov     edx, [rbp+rcDst.right]
0x180054595  mov     r9, rdi; struct tagPOINT *
0x180054598  mov     r8d, [rbp+rcDst.top]; int
0x18005459c  add     edx, 0FFFFFFFAh; int
0x18005459f  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x1800545a4  test    eax, eax
0x1800545a6  jnz     short loc_1800545F3
0x1800545a8  mov     eax, [rbp+rcDst.right]
0x1800545ab  mov     r9, rdi; struct tagPOINT *
0x1800545ae  sub     eax, [rbp+rcDst.left]
0x1800545b1  mov     r8d, [rbp+rcDst.top]; int
0x1800545b5  sub     eax, ebx
0x1800545b7  cdq
0x1800545b8  idiv    esi
0x1800545ba  add     eax, [rbp+rcDst.left]
0x1800545bd  mov     edx, eax; int
0x1800545bf  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x1800545c4  test    eax, eax
0x1800545c6  jnz     short loc_1800545EC
0x1800545c8  mov     eax, [rbp+rcDst.right]
0x1800545cb  mov     r9, rdi; struct tagPOINT *
0x1800545ce  sub     eax, [rbp+rcDst.left]
0x1800545d1  mov     r8d, [rbp+rcDst.bottom]
0x1800545d5  sub     eax, ebx
0x1800545d7  cdq
0x1800545d8  add     r8d, 0FFFFFFFAh; int
0x1800545dc  idiv    esi
0x1800545de  add     eax, [rbp+rcDst.left]
0x1800545e1  mov     edx, eax; int
0x1800545e3  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x1800545e8  test    eax, eax
0x1800545ea  jz      short loc_180054608
0x1800545ec  mov     eax, 7F85h
0x1800545f1  jmp     short loc_18005460A
0x1800545f3  mov     eax, 7F83h
0x1800545f8  jmp     short loc_18005460A
0x1800545fa  mov     eax, 7F84h
0x1800545ff  jmp     short loc_18005460A
0x180054601  mov     eax, 7F82h
0x180054606  jmp     short loc_18005460A
0x180054608  xor     eax, eax
0x18005460a  mov     rcx, [rbp+var_10]
0x18005460e  xor     rcx, rsp; StackCookie
0x180054611  call    __security_check_cookie
0x180054616  mov     rbx, [rsp+40h+arg_10]
0x18005461b  mov     rsi, [rsp+40h+arg_18]
0x180054620  add     rsp, 40h
0x180054624  pop     r14
0x180054626  pop     rdi
0x180054627  pop     rbp
0x180054628  retn
```
