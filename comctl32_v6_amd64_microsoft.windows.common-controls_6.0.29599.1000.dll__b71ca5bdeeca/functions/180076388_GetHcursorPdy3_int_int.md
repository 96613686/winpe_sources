# _GetHcursorPdy3(int *,int *)

- ea: `0x180076388`
- end: `0x1800765b3`
- name: `?_GetHcursorPdy3@@YAXPEAH0@Z`
- size: `555`
- prototype: `void __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800753c8`

## callees

- `0x180076388`
- `0x180114520`
- `0x1801d0bd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180076555`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180076555`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180076489`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180076489`
- `GDI32!DeleteObject` at `0x180076577`
- `GDI32!DeleteObject` at `0x180076586`
- `GDI32!DeleteObject` at `0x180076577`
- `GDI32!DeleteObject` at `0x180076586`
- `GDI32!GetObjectW` at `0x180076419`
- `GDI32!GetObjectW` at `0x180076419`
- `GDI32!GetBitmapBits` at `0x1800764b4`
- `GDI32!GetBitmapBits` at `0x1800764b4`
- `USER32!GetIconInfo` at `0x1800763f3`
- `USER32!GetIconInfo` at `0x1800763f3`
- `USER32!GetCursor` at `0x1800763c5`
- `USER32!GetCursor` at `0x1800763c5`

## pseudocode

```c
void __fastcall _GetHcursorPdy3(int *a1, int *a2)
{
  HCURSOR Cursor; // rax
  int v5; // edi
  LONG v6; // r15d
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // rax
  void *v10; // rsp
  ICONINFO *p_piconinfo; // rbx
  ICONINFO *v12; // rax
  unsigned __int64 v13; // rax
  int v14; // r8d
  int v15; // edx
  __int64 v16; // rdx
  int v17; // ecx
  unsigned __int64 v18; // rcx
  __int64 v19; // [rsp+0h] [rbp-20h] BYREF
  ICONINFO piconinfo; // [rsp+20h] [rbp+0h] BYREF
  _OWORD pv[2]; // [rsp+40h] [rbp+20h] BYREF

  *a2 = 0;
  *a1 = 0;
  Cursor = GetCursor();
  if ( !Cursor )
    return;
  *a2 = 16;
  *a1 = 16;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !GetIconInfo(Cursor, &piconinfo) )
    return;
  memset(pv, 0, sizeof(pv));
  if ( GetObjectW(piconinfo.hbmMask, 32, pv) )
  {
    v5 = DWORD1(pv[0]) * DWORD2(pv[0]);
    v6 = 2 * DWORD1(pv[0]) * DWORD2(pv[0]);
    v7 = v6 + 16LL;
    v8 = v7 & -(__int64)(v6 < v7);
    if ( v8 )
    {
      if ( v8 > 0x400 )
      {
        v12 = (ICONINFO *)malloc(v7 & -(__int64)(v6 < v7));
        p_piconinfo = v12;
        if ( !v12 )
          goto LABEL_13;
        v12->fIcon = 56797;
LABEL_12:
        p_piconinfo = (ICONINFO *)((char *)p_piconinfo + 16);
LABEL_13:
        if ( p_piconinfo )
        {
          if ( GetBitmapBits(piconinfo.hbmMask, v6, p_piconinfo) )
          {
            v13 = (unsigned __int64)(DWORD1(pv[0]) * DWORD2(pv[0])) >> 4;
            if ( piconinfo.hbmColor )
            {
              v14 = 0;
            }
            else
            {
              v14 = v13 - 1;
              LODWORD(v13) = (int)v13 / 2;
            }
            v15 = v5 - 1;
            if ( (int)v13 < v5 )
              v15 = v13;
            v16 = (unsigned int)(v15 - 1);
            if ( (int)v16 >= 0 )
            {
              v17 = 0;
              if ( v14 < v5 )
                v17 = v14;
              do
              {
                if ( *((_WORD *)&p_piconinfo->fIcon + v16) != 0xFFFF )
                  break;
                if ( v17 > 0 )
                {
                  if ( *((_WORD *)&p_piconinfo->fIcon + v17) )
                    break;
                  --v17;
                }
                v16 = (unsigned int)(v16 - 1);
              }
              while ( (int)v16 >= 0 );
            }
            v18 = SDWORD2(pv[0]);
            *a2 = 16LL * ((int)v16 + 1) / (unsigned __int64)SDWORD1(pv[0]) - piconinfo.yHotspot;
            *a1 = 16LL * ((int)v16 + 1) / v18 - piconinfo.xHotspot;
          }
          if ( LODWORD(p_piconinfo[-1].hbmMask) == 56797 )
            free(&p_piconinfo[-1].hbmMask);
          goto LABEL_32;
        }
        goto LABEL_31;
      }
      v9 = v8 + 15;
      if ( v8 + 15 < v8 )
        v9 = 0xFFFFFFFFFFFFFF0LL;
      v10 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
      p_piconinfo = &piconinfo;
      if ( &v19 != (__int64 *)-32LL )
      {
        piconinfo.fIcon = 52428;
        goto LABEL_12;
      }
    }
LABEL_31:
    *a2 = DWORD2(pv[0]) - piconinfo.yHotspot;
    *a1 = DWORD1(pv[0]) - piconinfo.xHotspot;
  }
LABEL_32:
  if ( piconinfo.hbmColor )
    DeleteObject(piconinfo.hbmColor);
  if ( piconinfo.hbmMask )
    DeleteObject(piconinfo.hbmMask);
}

```

## disassembly

```asm
0x180076388  push    rbp
0x18007638a  push    rdi
0x18007638b  push    r12
0x18007638d  push    r14
0x18007638f  push    r15
0x180076391  sub     rsp, 70h
0x180076395  lea     rbp, [rsp+20h]
0x18007639a  mov     [rbp+70h+arg_10], rbx
0x1800763a1  mov     [rbp+70h+arg_18], rsi
0x1800763a8  mov     rax, cs:__security_cookie
0x1800763af  xor     rax, rbp
0x1800763b2  mov     [rbp+70h+var_30], rax
0x1800763b6  xor     r12d, r12d
0x1800763b9  mov     r14, rdx
0x1800763bc  mov     [rdx], r12d
0x1800763bf  mov     rsi, rcx
0x1800763c2  mov     [rcx], r12d
0x1800763c5  call    cs:__imp_GetCursor
0x1800763cb  test    rax, rax
0x1800763ce  jz      loc_18007658C
0x1800763d4  xorps   xmm0, xmm0
0x1800763d7  mov     dword ptr [r14], 10h
0x1800763de  lea     rdx, [rbp+70h+piconinfo]; piconinfo
0x1800763e2  mov     dword ptr [rsi], 10h
0x1800763e8  mov     rcx, rax; hIcon
0x1800763eb  movups  xmmword ptr [rbp+70h+piconinfo.fIcon], xmm0
0x1800763ef  movups  xmmword ptr [rbp+70h+piconinfo.hbmMask], xmm0
0x1800763f3  call    cs:__imp_GetIconInfo
0x1800763f9  test    eax, eax
0x1800763fb  jz      loc_18007658C
0x180076401  mov     rcx, [rbp+70h+piconinfo.hbmMask]; h
0x180076405  lea     r8, [rbp+70h+pv]; pv
0x180076409  xorps   xmm0, xmm0
0x18007640c  lea     edx, [r12+20h]; c
0x180076411  movups  [rbp+70h+pv], xmm0
0x180076415  movups  [rbp+70h+var_40], xmm0
0x180076419  call    cs:__imp_GetObjectW
0x18007641f  test    eax, eax
0x180076421  jz      loc_18007656E
0x180076427  mov     edi, dword ptr [rbp+70h+pv+8]
0x18007642a  imul    edi, dword ptr [rbp+70h+pv+4]
0x18007642e  lea     r15d, [rdi+rdi]
0x180076432  movsxd  rax, r15d
0x180076435  lea     rcx, [rax+10h]
0x180076439  cmp     rax, rcx
0x18007643c  sbb     rdx, rdx
0x18007643f  and     rdx, rcx
0x180076442  jz      loc_18007655D
0x180076448  cmp     rdx, 400h
0x18007644f  ja      short loc_180076486
0x180076451  lea     rax, [rdx+0Fh]
0x180076455  cmp     rax, rdx
0x180076458  ja      short loc_180076464
0x18007645a  mov     rax, 0FFFFFFFFFFFFFF0h
0x180076464  and     rax, 0FFFFFFFFFFFFFFF0h
0x180076468  call    _alloca_probe
0x18007646d  sub     rsp, rax
0x180076470  lea     rbx, [rsp+90h+piconinfo]
0x180076475  test    rbx, rbx
0x180076478  jz      loc_18007655D
0x18007647e  mov     dword ptr [rbx], 0CCCCh
0x180076484  jmp     short loc_18007649D
0x180076486  mov     rcx, rdx; Size
0x180076489  call    cs:__imp_malloc
0x18007648f  mov     rbx, rax
0x180076492  test    rax, rax
0x180076495  jz      short loc_1800764A1
0x180076497  mov     dword ptr [rax], 0DDDDh
0x18007649d  add     rbx, 10h
0x1800764a1  test    rbx, rbx
0x1800764a4  jz      loc_18007655D
0x1800764aa  mov     rcx, [rbp+70h+piconinfo.hbmMask]; hbit
0x1800764ae  mov     r8, rbx; lpvBits
0x1800764b1  mov     edx, r15d; cb
0x1800764b4  call    cs:__imp_GetBitmapBits
0x1800764ba  test    eax, eax
0x1800764bc  jz      loc_180076549
0x1800764c2  mov     eax, dword ptr [rbp+70h+pv+8]
0x1800764c5  imul    eax, dword ptr [rbp+70h+pv+4]
0x1800764c9  cdqe
0x1800764cb  shr     rax, 4
0x1800764cf  cmp     [rbp+70h+piconinfo.hbmColor], r12
0x1800764d3  jnz     short loc_1800764E0
0x1800764d5  lea     r8d, [rax-1]
0x1800764d9  cdq
0x1800764da  sub     eax, edx
0x1800764dc  sar     eax, 1
0x1800764de  jmp     short loc_1800764E3
0x1800764e0  mov     r8d, r12d
0x1800764e3  cmp     eax, edi
0x1800764e5  lea     edx, [rdi-1]
0x1800764e8  cmovl   edx, eax
0x1800764eb  sub     edx, 1
0x1800764ee  js      short loc_18007651C
0x1800764f0  cmp     r8d, edi
0x1800764f3  mov     ecx, r12d
0x1800764f6  cmovl   ecx, r8d
0x1800764fa  mov     r8d, 0FFFFh
0x180076500  cmp     [rbx+rdx*2], r8w
0x180076505  jnz     short loc_18007651C
0x180076507  test    ecx, ecx
0x180076509  jle     short loc_180076517
0x18007650b  movsxd  rax, ecx
0x18007650e  cmp     [rbx+rax*2], r12w
0x180076513  jnz     short loc_18007651C
0x180076515  dec     ecx
0x180076517  sub     edx, 1
0x18007651a  jns     short loc_1800764FA
0x18007651c  movsxd  rcx, dword ptr [rbp+70h+pv+4]
0x180076520  lea     eax, [rdx+1]
0x180076523  movsxd  r8, eax
0x180076526  xor     edx, edx
0x180076528  shl     r8, 4
0x18007652c  mov     rax, r8
0x18007652f  div     rcx
0x180076532  movsxd  rcx, dword ptr [rbp+70h+pv+8]
0x180076536  xor     edx, edx
0x180076538  sub     eax, [rbp+70h+piconinfo.yHotspot]
0x18007653b  mov     [r14], eax
0x18007653e  mov     rax, r8
0x180076541  div     rcx
0x180076544  sub     eax, [rbp+70h+piconinfo.xHotspot]
0x180076547  mov     [rsi], eax
0x180076549  lea     rcx, [rbx-10h]; Block
0x18007654d  cmp     dword ptr [rcx], 0DDDDh
0x180076553  jnz     short loc_18007656E
0x180076555  call    cs:__imp_free
0x18007655b  jmp     short loc_18007656E
0x18007655d  mov     eax, dword ptr [rbp+70h+pv+8]
0x180076560  sub     eax, [rbp+70h+piconinfo.yHotspot]
0x180076563  mov     [r14], eax
0x180076566  mov     eax, dword ptr [rbp+70h+pv+4]
0x180076569  sub     eax, [rbp+70h+piconinfo.xHotspot]
0x18007656c  mov     [rsi], eax
0x18007656e  mov     rcx, [rbp+70h+piconinfo.hbmColor]; ho
0x180076572  test    rcx, rcx
0x180076575  jz      short loc_18007657D
0x180076577  call    cs:__imp_DeleteObject
0x18007657d  mov     rcx, [rbp+70h+piconinfo.hbmMask]; ho
0x180076581  test    rcx, rcx
0x180076584  jz      short loc_18007658C
0x180076586  call    cs:__imp_DeleteObject
0x18007658c  mov     rcx, [rbp+70h+var_30]
0x180076590  xor     rcx, rbp; StackCookie
0x180076593  call    __security_check_cookie
0x180076598  mov     rbx, [rbp+70h+arg_10]
0x18007659f  mov     rsi, [rbp+70h+arg_18]
0x1800765a6  lea     rsp, [rbp+50h]
0x1800765aa  pop     r15
0x1800765ac  pop     r14
0x1800765ae  pop     r12
0x1800765b0  pop     rdi
0x1800765b1  pop     rbp
0x1800765b2  retn
```
