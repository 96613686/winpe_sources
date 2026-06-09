# ListView_InvalidateItemEx

- ea: `0x180053f50`
- end: `0x18005413b`
- name: `ListView_InvalidateItemEx`
- size: `491`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int)`
- caller_count: `16`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180053eb8`
- `0x180054144`
- `0x180055608`
- `0x180058314`
- `0x180058588`
- `0x1800587e8`
- `0x180058f1c`
- `0x1800590f4`
- `0x180059798`
- `0x18005b080`
- `0x18005b600`
- `0x18005c0a0`
- `0x1800733e0`
- `0x180075640`
- `0x180075888`
- `0x180075c34`

## callees

- `0x1800115f0`
- `0x180052cf8`
- `0x180053f50`

## import_xrefs

- `GDI32!DeleteObject` at `0x18005410f`
- `GDI32!DeleteObject` at `0x18005410f`
- `GDI32!CombineRgn` at `0x180054106`
- `GDI32!CombineRgn` at `0x180054106`
- `GDI32!CreateRectRgnIndirect` at `0x1800540d1`
- `GDI32!CreateRectRgnIndirect` at `0x1800540d1`
- `USER32!RedrawWindow` at `0x18005406e`
- `USER32!RedrawWindow` at `0x18005406e`
- `USER32!InflateRect` at `0x18005405b`
- `USER32!InflateRect` at `0x18005405b`

## pseudocode

```c
void __fastcall ListView_InvalidateItemEx(__int64 a1, int a2, int a3, UINT a4, int a5)
{
  int v7; // ecx
  struct tagRECT *v8; // r9
  struct tagRECT *p_rc; // r10
  struct tagRECT *lprcDst; // r11
  struct tagRECT *v11; // rdi
  int v12; // eax
  int v13; // eax
  HRGN v14; // rax
  HRGN v15; // rdi
  HRGN v16; // rcx
  struct tagRECT rc; // [rsp+30h] [rbp-20h] BYREF

  if ( a2 == -1 )
    return;
  v7 = *(_DWORD *)(a1 + 16);
  LODWORD(v8) = 0;
  p_rc = 0;
  lprcDst = 0;
  LODWORD(v11) = 0;
  rc = 0;
  if ( (v7 & 0x1000) == 0 || (*(_DWORD *)(a1 + 72) & 0x2000) == 0 || (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
  {
    v12 = 0;
    if ( (v7 & 0x400) == 0 )
      v12 = a3;
    if ( v12 )
    {
      if ( (v7 & 3) != 1 || (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
      {
        p_rc = &rc;
        goto LABEL_16;
      }
      goto LABEL_15;
    }
  }
  if ( a5 == 1 )
  {
LABEL_15:
    v8 = &rc;
    goto LABEL_16;
  }
  if ( a5 == 2 )
    v11 = &rc;
  else
    lprcDst = &rc;
LABEL_16:
  if ( (*(_BYTE *)(a1 + 72) & 0x12) == 0x12 )
  {
    ListView_GetRects(a1, a2, (int)v11, (int)v8, lprcDst, p_rc);
    if ( *(_DWORD *)(a1 + 164) > rc.left && rc.right > 0 && *(_DWORD *)(a1 + 168) > rc.top && rc.bottom > 0 )
    {
      if ( (*(_DWORD *)(a1 + 76) & 0x8000) != 0 )
        InflateRect(&rc, g_cxIconMargin + 4, g_cyIconMargin + 4);
      RedrawWindow(*(HWND *)a1, &rc, 0, a4);
    }
  }
  else if ( (*(_BYTE *)(a1 + 72) & 0x10) == 0 )
  {
    v13 = *(_DWORD *)(a1 + 156);
    if ( v13 == -1 || a2 < v13 )
    {
      ListView_GetRects(a1, a2, (int)v11, (int)v8, lprcDst, p_rc);
      if ( *(_DWORD *)(a1 + 164) > rc.left && rc.right > 0 && *(_DWORD *)(a1 + 168) > rc.top && rc.bottom > 0 )
      {
        v14 = CreateRectRgnIndirect(&rc);
        v15 = v14;
        if ( v14 )
        {
          v16 = *(HRGN *)(a1 + 200);
          if ( v16 )
          {
            if ( v16 != (HRGN)1 )
              CombineRgn(v16, *(HRGN *)(a1 + 200), v14, 2);
            DeleteObject(v15);
          }
          else
          {
            *(_QWORD *)(a1 + 200) = v14;
          }
        }
        if ( (a4 & 4) != 0 )
          *(_DWORD *)(a1 + 72) |= 4u;
      }
    }
  }
}

```

## disassembly

```asm
0x180053f50  cmp     edx, 0FFFFFFFFh
0x180053f53  jz      locret_18005413A
0x180053f59  mov     [rsp-18h+arg_10], rbx
0x180053f5e  push    rbp
0x180053f5f  push    rsi
0x180053f60  push    rdi
0x180053f61  mov     rbp, rsp
0x180053f64  sub     rsp, 50h
0x180053f68  mov     rax, cs:__security_cookie
0x180053f6f  xor     rax, rsp
0x180053f72  mov     [rbp+var_10], rax
0x180053f76  mov     esi, r9d
0x180053f79  mov     rbx, rcx
0x180053f7c  mov     ecx, [rcx+10h]
0x180053f7f  xor     r9d, r9d
0x180053f82  xor     r10d, r10d
0x180053f85  xor     r11d, r11d
0x180053f88  xor     edi, edi
0x180053f8a  xorps   xmm0, xmm0
0x180053f8d  movups  xmmword ptr [rbp+rc.left], xmm0
0x180053f91  bt      ecx, 0Ch
0x180053f95  jnb     short loc_180053FA6
0x180053f97  test    dword ptr [rbx+48h], 2000h
0x180053f9e  jz      short loc_180053FA6
0x180053fa0  test    byte ptr [rbx+4Ch], 20h
0x180053fa4  jz      short loc_180053FC8
0x180053fa6  bt      ecx, 0Ah
0x180053faa  mov     eax, edi
0x180053fac  cmovnb  eax, r8d
0x180053fb0  test    eax, eax
0x180053fb2  jz      short loc_180053FC8
0x180053fb4  and     cl, 3
0x180053fb7  cmp     cl, 1
0x180053fba  jnz     short loc_180053FC2
0x180053fbc  test    byte ptr [rbx+4Ch], 20h
0x180053fc0  jz      short loc_180053FE1
0x180053fc2  lea     r10, [rbp+rc]
0x180053fc6  jmp     short loc_180053FE5
0x180053fc8  mov     eax, [rbp+arg_20]
0x180053fcb  sub     eax, 1
0x180053fce  jz      short loc_180053FE1
0x180053fd0  cmp     eax, 1
0x180053fd3  jz      short loc_180053FDB
0x180053fd5  lea     r11, [rbp+rc]
0x180053fd9  jmp     short loc_180053FE5
0x180053fdb  lea     rdi, [rbp+rc]
0x180053fdf  jmp     short loc_180053FE5
0x180053fe1  lea     r9, [rbp+rc]; int
0x180053fe5  mov     eax, [rbx+48h]
0x180053fe8  and     eax, 12h
0x180053feb  cmp     al, 12h
0x180053fed  jnz     loc_180054079
0x180053ff3  mov     [rsp+50h+var_28], r10; LPRECT
0x180053ff8  mov     r8, rdi; int
0x180053ffb  mov     rcx, rbx; int
0x180053ffe  mov     [rsp+50h+lprcDst], r11; lprcDst
0x180054003  call    ListView_GetRects
0x180054008  mov     eax, [rbp+rc.left]
0x18005400b  cmp     [rbx+0A4h], eax
0x180054011  jle     loc_18005411F
0x180054017  cmp     [rbp+rc.right], 0
0x18005401b  jle     loc_18005411F
0x180054021  mov     eax, [rbp+rc.top]
0x180054024  cmp     [rbx+0A8h], eax
0x18005402a  jle     loc_18005411F
0x180054030  cmp     [rbp+rc.bottom], 0
0x180054034  jle     loc_18005411F
0x18005403a  test    dword ptr [rbx+4Ch], 8000h
0x180054041  jz      short loc_180054061
0x180054043  mov     r8d, cs:g_cyIconMargin
0x18005404a  lea     rcx, [rbp+rc]; lprc
0x18005404e  mov     edx, cs:g_cxIconMargin
0x180054054  add     r8d, 4; dy
0x180054058  add     edx, 4; dx
0x18005405b  call    cs:__imp_InflateRect
0x180054061  mov     rcx, [rbx]; hWnd
0x180054064  lea     rdx, [rbp+rc]; lprcUpdate
0x180054068  mov     r9d, esi; flags
0x18005406b  xor     r8d, r8d; hrgnUpdate
0x18005406e  call    cs:__imp_RedrawWindow
0x180054074  jmp     loc_18005411F
0x180054079  test    byte ptr [rbx+48h], 10h
0x18005407d  jnz     loc_18005411F
0x180054083  mov     eax, [rbx+9Ch]
0x180054089  cmp     eax, 0FFFFFFFFh
0x18005408c  jz      short loc_180054096
0x18005408e  cmp     edx, eax
0x180054090  jge     loc_18005411F
0x180054096  mov     [rsp+50h+var_28], r10; LPRECT
0x18005409b  mov     r8, rdi; int
0x18005409e  mov     rcx, rbx; int
0x1800540a1  mov     [rsp+50h+lprcDst], r11; lprcDst
0x1800540a6  call    ListView_GetRects
0x1800540ab  mov     eax, [rbp+rc.left]
0x1800540ae  cmp     [rbx+0A4h], eax
0x1800540b4  jle     short loc_18005411F
0x1800540b6  cmp     [rbp+rc.right], 0
0x1800540ba  jle     short loc_18005411F
0x1800540bc  mov     eax, [rbp+rc.top]
0x1800540bf  cmp     [rbx+0A8h], eax
0x1800540c5  jle     short loc_18005411F
0x1800540c7  cmp     [rbp+rc.bottom], 0
0x1800540cb  jle     short loc_18005411F
0x1800540cd  lea     rcx, [rbp+rc]; lprect
0x1800540d1  call    cs:__imp_CreateRectRgnIndirect
0x1800540d7  mov     rdi, rax
0x1800540da  test    rax, rax
0x1800540dd  jz      short loc_180054115
0x1800540df  mov     rcx, [rbx+0C8h]; hrgnDst
0x1800540e6  test    rcx, rcx
0x1800540e9  jnz     short loc_1800540F4
0x1800540eb  mov     [rbx+0C8h], rax
0x1800540f2  jmp     short loc_180054115
0x1800540f4  cmp     rcx, 1
0x1800540f8  jz      short loc_18005410C
0x1800540fa  mov     r9d, 2; iMode
0x180054100  mov     r8, rdi; hrgnSrc2
0x180054103  mov     rdx, rcx; hrgnSrc1
0x180054106  call    cs:__imp_CombineRgn
0x18005410c  mov     rcx, rdi; ho
0x18005410f  call    cs:__imp_DeleteObject
0x180054115  test    sil, 4
0x180054119  jz      short loc_18005411F
0x18005411b  or      dword ptr [rbx+48h], 4
0x18005411f  mov     rcx, [rbp+var_10]
0x180054123  xor     rcx, rsp; StackCookie
0x180054126  call    __security_check_cookie
0x18005412b  mov     rbx, [rsp+50h+arg_10]
0x180054133  add     rsp, 50h
0x180054137  pop     rdi
0x180054138  pop     rsi
0x180054139  pop     rbp
0x18005413a  retn
```
