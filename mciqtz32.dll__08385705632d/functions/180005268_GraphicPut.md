# GraphicPut

- ea: `0x180005268`
- end: `0x18000537d`
- name: `GraphicPut`
- size: `277`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180001460`
- `0x180002d20`
- `0x180005268`

## import_xrefs

- `USER32!SetRectEmpty` at `0x1800052aa`
- `USER32!SetRectEmpty` at `0x1800052aa`

## pseudocode

```c
unsigned int __fastcall GraphicPut(struct _MCIGRAPHIC *a1, int a2, LONG *a3)
{
  int v7; // r8d
  int v8; // r9d
  LONG v9; // edx
  LONG v10; // ecx
  LONG v11; // edx
  LONG v12; // ecx
  struct tagRECT rc; // [rsp+20h] [rbp-20h] BYREF

  rc = 0;
  if ( (a2 & 0x180000) != 0 )
    return 274;
  SetRectEmpty(&rc);
  v7 = a2 & 0x660000;
  if ( (a2 & 0x660000) == 0 )
    return 273;
  v8 = a2 & 0x10000;
  if ( v7 == 0x20000 )
    goto LABEL_7;
  if ( v7 == 0x40000 )
  {
    if ( v8 )
    {
      v11 = a3[3];
      rc.left = a3[2];
      rc.right = a3[4] + rc.left;
      v12 = a3[5];
      rc.top = v11;
      rc.bottom = v11 + v12;
    }
    if ( (a2 & 0x400000) == 0 )
      goto LABEL_9;
    return 284;
  }
  if ( ((v7 - 0x200000) & 0xFF9FFFFF) != 0 )
    return 284;
LABEL_7:
  if ( v8 )
  {
    v9 = a3[3];
    rc.left = a3[2];
    rc.right = a3[4] + rc.left;
    v10 = a3[5];
    rc.top = v9;
    rc.bottom = v9 + v10;
  }
LABEL_9:
  if ( (a2 & 0x20) != 0 )
    return 0;
  else
    return DevicePut(a1, (struct tagRECT *)((unsigned __int64)&rc & -(__int64)(v8 != 0)), v7);
}

```

## disassembly

```asm
0x180005268  mov     [rsp-18h+arg_18], rbx
0x18000526d  push    rbp
0x18000526e  push    rsi
0x18000526f  push    rdi
0x180005270  mov     rbp, rsp
0x180005273  sub     rsp, 40h
0x180005277  mov     rax, cs:__security_cookie
0x18000527e  xor     rax, rsp
0x180005281  mov     [rbp+var_10], rax
0x180005285  xorps   xmm0, xmm0
0x180005288  mov     rbx, r8
0x18000528b  mov     edi, edx
0x18000528d  mov     rsi, rcx
0x180005290  movups  xmmword ptr [rbp+rc.left], xmm0
0x180005294  test    edx, 180000h
0x18000529a  jz      short loc_1800052A6
0x18000529c  mov     eax, 112h
0x1800052a1  jmp     loc_180005364
0x1800052a6  lea     rcx, [rbp+rc]; lprc
0x1800052aa  call    cs:__imp_SetRectEmpty
0x1800052b0  mov     r8d, edi
0x1800052b3  and     r8d, 660000h; unsigned int
0x1800052ba  jz      loc_18000535F
0x1800052c0  mov     r9d, edi
0x1800052c3  and     r9d, 10000h
0x1800052ca  cmp     r8d, 20000h
0x1800052d1  jz      short loc_1800052F3
0x1800052d3  cmp     r8d, 40000h
0x1800052da  jz      short loc_18000531C
0x1800052dc  lea     eax, [r8-200000h]
0x1800052e3  test    eax, 0FF9FFFFFh
0x1800052e8  jnz     short loc_180005341
0x1800052ea  cmp     r8d, 800000h
0x1800052f1  jz      short loc_180005341
0x1800052f3  test    r9d, r9d
0x1800052f6  jz      short loc_180005312
0x1800052f8  mov     ecx, [rbx+8]
0x1800052fb  mov     edx, [rbx+0Ch]
0x1800052fe  mov     [rbp+rc.left], ecx
0x180005301  add     ecx, [rbx+10h]
0x180005304  mov     [rbp+rc.right], ecx
0x180005307  mov     ecx, [rbx+14h]
0x18000530a  add     ecx, edx
0x18000530c  mov     [rbp+rc.top], edx
0x18000530f  mov     [rbp+rc.bottom], ecx
0x180005312  test    dil, 20h
0x180005316  jz      short loc_180005348
0x180005318  xor     eax, eax
0x18000531a  jmp     short loc_180005364
0x18000531c  test    r9d, r9d
0x18000531f  jz      short loc_18000533B
0x180005321  mov     ecx, [rbx+8]
0x180005324  mov     edx, [rbx+0Ch]
0x180005327  mov     [rbp+rc.left], ecx
0x18000532a  add     ecx, [rbx+10h]
0x18000532d  mov     [rbp+rc.right], ecx
0x180005330  mov     ecx, [rbx+14h]
0x180005333  add     ecx, edx
0x180005335  mov     [rbp+rc.top], edx
0x180005338  mov     [rbp+rc.bottom], ecx
0x18000533b  bt      edi, 16h
0x18000533f  jnb     short loc_180005312
0x180005341  mov     eax, 11Ch
0x180005346  jmp     short loc_180005364
0x180005348  neg     r9d
0x18000534b  lea     rax, [rbp+rc]
0x18000534f  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005352  sbb     rdx, rdx
0x180005355  and     rdx, rax; struct tagRECT *
0x180005358  call    ?DevicePut@@YAKPEAU_MCIGRAPHIC@@PEAUtagRECT@@K@Z; DevicePut(_MCIGRAPHIC *,tagRECT *,ulong)
0x18000535d  jmp     short loc_180005364
0x18000535f  mov     eax, 111h
0x180005364  mov     rcx, [rbp+var_10]
0x180005368  xor     rcx, rsp; StackCookie
0x18000536b  call    __security_check_cookie
0x180005370  mov     rbx, [rsp+40h+arg_18]
0x180005375  add     rsp, 40h
0x180005379  pop     rdi
0x18000537a  pop     rsi
0x18000537b  pop     rbp
0x18000537c  retn
```
