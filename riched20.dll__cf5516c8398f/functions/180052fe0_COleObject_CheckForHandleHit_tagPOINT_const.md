# COleObject::CheckForHandleHit(tagPOINT const &)

- ea: `0x180052fe0`
- end: `0x1800531c9`
- name: `?CheckForHandleHit@COleObject@@QEAAPEAGAEBUtagPOINT@@@Z`
- size: `489`
- prototype: `unsigned __int16 *(COleObject *__hidden this, const struct tagPOINT *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180031010`
- `0x180054714`

## callees

- `0x180052fe0`
- `0x180054afc`
- `0x180091140`

## import_xrefs

- `USER32!CopyRect` at `0x180053040`
- `USER32!CopyRect` at `0x180053040`
- `USER32!PtInRect` at `0x18005307c`
- `USER32!PtInRect` at `0x18005307c`
- `USER32!InflateRect` at `0x18005306f`
- `USER32!InflateRect` at `0x180053096`
- `USER32!InflateRect` at `0x18005306f`
- `USER32!InflateRect` at `0x180053096`

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
0x180052fe0  mov     [rsp-18h+arg_10], rbx
0x180052fe5  mov     [rsp-18h+arg_18], rsi
0x180052fea  push    rbp
0x180052feb  push    rdi
0x180052fec  push    r14
0x180052fee  mov     rbp, rsp
0x180052ff1  sub     rsp, 40h
0x180052ff5  mov     rax, cs:__security_cookie
0x180052ffc  xor     rax, rsp
0x180052fff  mov     [rbp+var_10], rax
0x180053003  mov     esi, 1
0x180053008  xorps   xmm0, xmm0
0x18005300b  mov     rdi, rdx
0x18005300e  mov     rbx, rcx
0x180053011  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180053015  test    [rcx+90h], sil
0x18005301c  jz      loc_1800531A8
0x180053022  mov     rax, [rcx+40h]
0x180053026  test    rax, rax
0x180053029  jz      short loc_180053038
0x18005302b  test    byte ptr [rax+0B4h], 4
0x180053032  jnz     loc_1800531A8
0x180053038  lea     rdx, [rcx+58h]; lprcSrc
0x18005303c  lea     rcx, [rbp+rcDst]; lprcDst
0x180053040  call    cs:__imp_CopyRect
0x180053046  movzx   eax, word ptr [rbx+9Ch]
0x18005304d  test    ax, ax
0x180053050  jnz     short loc_18005305B
0x180053052  mov     [rbx+9Ch], si
0x180053059  jmp     short loc_18005305E
0x18005305b  movzx   esi, ax
0x18005305e  movsx   eax, si
0x180053061  lea     rcx, [rbp+rcDst]; lprc
0x180053065  mov     edx, 0FFFFFFFAh
0x18005306a  sub     edx, eax; dx
0x18005306c  mov     r8d, edx; dy
0x18005306f  call    cs:__imp_InflateRect
0x180053075  mov     rdx, [rdi]; pt
0x180053078  lea     rcx, [rbp+rcDst]; lprc
0x18005307c  call    cs:__imp_PtInRect
0x180053082  test    eax, eax
0x180053084  jnz     loc_1800531A8
0x18005308a  lea     ebx, [rax+6]
0x18005308d  mov     r8d, ebx; dy
0x180053090  lea     rcx, [rbp+rcDst]; lprc
0x180053094  mov     edx, ebx; dx
0x180053096  call    cs:__imp_InflateRect
0x18005309c  mov     r8d, [rbp+rcDst.top]; int
0x1800530a0  mov     r9, rdi; struct tagPOINT *
0x1800530a3  mov     edx, [rbp+rcDst.left]; int
0x1800530a6  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x1800530ab  test    eax, eax
0x1800530ad  jnz     loc_1800531A1
0x1800530b3  mov     r8d, [rbp+rcDst.bottom]
0x1800530b7  mov     r9, rdi; struct tagPOINT *
0x1800530ba  mov     edx, [rbp+rcDst.right]
0x1800530bd  add     r8d, 0FFFFFFFAh; int
0x1800530c1  add     edx, 0FFFFFFFAh; int
0x1800530c4  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x1800530c9  test    eax, eax
0x1800530cb  jnz     loc_1800531A1
0x1800530d1  mov     eax, [rbp+rcDst.bottom]
0x1800530d4  lea     esi, [rbx-4]
0x1800530d7  sub     eax, [rbp+rcDst.top]
0x1800530da  mov     r9, rdi; struct tagPOINT *
0x1800530dd  sub     eax, ebx
0x1800530df  cdq
0x1800530e0  idiv    esi
0x1800530e2  mov     edx, [rbp+rcDst.left]; int
0x1800530e5  add     eax, [rbp+rcDst.top]
0x1800530e8  mov     r8d, eax; int
0x1800530eb  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x1800530f0  test    eax, eax
0x1800530f2  jnz     loc_18005319A
0x1800530f8  mov     eax, [rbp+rcDst.bottom]
0x1800530fb  mov     r9, rdi; struct tagPOINT *
0x1800530fe  sub     eax, [rbp+rcDst.top]
0x180053101  sub     eax, ebx
0x180053103  cdq
0x180053104  idiv    esi
0x180053106  mov     edx, [rbp+rcDst.right]
0x180053109  add     eax, [rbp+rcDst.top]
0x18005310c  add     edx, 0FFFFFFFAh; int
0x18005310f  mov     r8d, eax; int
0x180053112  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180053117  test    eax, eax
0x180053119  jnz     short loc_18005319A
0x18005311b  mov     r8d, [rbp+rcDst.bottom]
0x18005311f  mov     r9, rdi; struct tagPOINT *
0x180053122  mov     edx, [rbp+rcDst.left]; int
0x180053125  add     r8d, 0FFFFFFFAh; int
0x180053129  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x18005312e  test    eax, eax
0x180053130  jnz     short loc_180053193
0x180053132  mov     edx, [rbp+rcDst.right]
0x180053135  mov     r9, rdi; struct tagPOINT *
0x180053138  mov     r8d, [rbp+rcDst.top]; int
0x18005313c  add     edx, 0FFFFFFFAh; int
0x18005313f  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180053144  test    eax, eax
0x180053146  jnz     short loc_180053193
0x180053148  mov     eax, [rbp+rcDst.right]
0x18005314b  mov     r9, rdi; struct tagPOINT *
0x18005314e  sub     eax, [rbp+rcDst.left]
0x180053151  mov     r8d, [rbp+rcDst.top]; int
0x180053155  sub     eax, ebx
0x180053157  cdq
0x180053158  idiv    esi
0x18005315a  add     eax, [rbp+rcDst.left]
0x18005315d  mov     edx, eax; int
0x18005315f  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180053164  test    eax, eax
0x180053166  jnz     short loc_18005318C
0x180053168  mov     eax, [rbp+rcDst.right]
0x18005316b  mov     r9, rdi; struct tagPOINT *
0x18005316e  sub     eax, [rbp+rcDst.left]
0x180053171  mov     r8d, [rbp+rcDst.bottom]
0x180053175  sub     eax, ebx
0x180053177  cdq
0x180053178  add     r8d, 0FFFFFFFAh; int
0x18005317c  idiv    esi
0x18005317e  add     eax, [rbp+rcDst.left]
0x180053181  mov     edx, eax; int
0x180053183  call    ?InHandle@COleObject@@AEAAHHHAEBUtagPOINT@@@Z; COleObject::InHandle(int,int,tagPOINT const &)
0x180053188  test    eax, eax
0x18005318a  jz      short loc_1800531A8
0x18005318c  mov     eax, 7F85h
0x180053191  jmp     short loc_1800531AA
0x180053193  mov     eax, 7F83h
0x180053198  jmp     short loc_1800531AA
0x18005319a  mov     eax, 7F84h
0x18005319f  jmp     short loc_1800531AA
0x1800531a1  mov     eax, 7F82h
0x1800531a6  jmp     short loc_1800531AA
0x1800531a8  xor     eax, eax
0x1800531aa  mov     rcx, [rbp+var_10]
0x1800531ae  xor     rcx, rsp; StackCookie
0x1800531b1  call    __security_check_cookie
0x1800531b6  mov     rbx, [rsp+40h+arg_10]
0x1800531bb  mov     rsi, [rsp+40h+arg_18]
0x1800531c0  add     rsp, 40h
0x1800531c4  pop     r14
0x1800531c6  pop     rdi
0x1800531c7  pop     rbp
0x1800531c8  retn
```
