# ListView_RecomputeLabelSize

- ea: `0x180076150`
- end: `0x180076480`
- name: `ListView_RecomputeLabelSize`
- size: `816`
- prototype: ``
- caller_count: `12`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800526a8`
- `0x180052cf8`
- `0x180058f1c`
- `0x18005bcc0`
- `0x1800748e8`
- `0x180075640`
- `0x180075c34`
- `0x180078bbc`
- `0x18007a07c`
- `0x18007a350`
- `0x18007a700`
- `0x18007ad0c`

## callees

- `0x1800115f0`
- `0x18002fcd0`
- `0x180055de0`
- `0x180076150`
- `0x180077570`
- `0x1800775f8`
- `0x180077784`
- `0x1800777e4`
- `0x18008ea60`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800762a6`
- `KERNEL32!lstrlenW` at `0x1800762a6`
- `KERNEL32!lstrcmpW` at `0x1800763d6`
- `KERNEL32!lstrcmpW` at `0x1800763d6`
- `USER32!SetRectEmpty` at `0x180076246`
- `USER32!SetRectEmpty` at `0x180076246`
- `USER32!DrawTextW` at `0x180076322`
- `USER32!DrawTextW` at `0x180076358`
- `USER32!DrawTextW` at `0x1800763bd`
- `USER32!DrawTextW` at `0x180076322`
- `USER32!DrawTextW` at `0x180076358`
- `USER32!DrawTextW` at `0x1800763bd`

## pseudocode

```c
__int16 __fastcall ListView_RecomputeLabelSize(__int64 a1, __int64 a2, unsigned int a3, HDC a4, int a5)
{
  __int64 v9; // r15
  __int64 v10; // rbx
  WCHAR *v11; // rax
  LONG v12; // eax
  __int64 v13; // rcx
  WCHAR *v14; // rdx
  WCHAR *v15; // rcx
  int v16; // r14d
  LONG v17; // edx
  HDC v18; // rcx
  UINT format; // ebx
  WCHAR *v20; // rcx
  __int64 v21; // rdx
  WCHAR *v22; // rax
  WCHAR *v23; // rcx
  __int16 v24; // ax
  __int16 v25; // cx
  __int128 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h]
  __int128 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  HDC v31[18]; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT v32; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT v33; // [rsp+110h] [rbp+10h] BYREF
  struct tagRECT rc; // [rsp+120h] [rbp+20h] BYREF
  WCHAR String[272]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR chText[272]; // [rsp+350h] [rbp+250h] BYREF

  rc = 0;
  v33 = 0;
  v32 = 0;
  memset(v31, 0, 0x88u);
  v30 = 0;
  v9 = 2147483646;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  if ( !a5 || *(_QWORD *)a2 == -1 )
  {
    *(_QWORD *)((char *)&v27 + 4) = a3;
    v10 = 264;
    LODWORD(v27) = 5;
    LODWORD(v29) = 264;
    *((_QWORD *)&v28 + 1) = String;
    LODWORD(v28) = 0;
    String[0] = 0;
    ListView_OnGetItem(a1, &v27);
    v11 = (WCHAR *)*((_QWORD *)&v28 + 1);
    if ( !*((_QWORD *)&v28 + 1) )
    {
      LOWORD(v12) = SetRectEmpty(&rc);
      v33 = rc;
      v32 = rc;
      goto LABEL_33;
    }
    if ( *((WCHAR **)&v28 + 1) != String )
    {
      v13 = 2147483646;
      v14 = String;
      do
      {
        if ( !v13 )
          break;
        if ( !*v11 )
          break;
        *v14++ = *v11++;
        --v13;
        --v10;
      }
      while ( v10 );
      v15 = v14 - 1;
      if ( v10 )
        v15 = v14;
      *v15 = 0;
    }
  }
  else
  {
    Str_GetPtrW(*(void **)a2, String);
    *((_QWORD *)&v29 + 1) = *(_QWORD *)(a2 + 32);
  }
  v16 = lstrlenW(String);
  v17 = *(_DWORD *)(a1 + 264) - 2 * g_cxLabelMargin;
  v32.bottom = 0;
  v32.right = v17;
  *(_QWORD *)&v32.left = 0;
  rc = v32;
  v33 = v32;
  if ( v16 <= 0 )
  {
    v12 = *(_DWORD *)(a1 + 128);
    v32.bottom = v12;
    v33.bottom = v12;
  }
  else
  {
    if ( a4 )
    {
      v18 = a4;
      v31[4] = a4;
    }
    else
    {
      ListView_BeginFakeCustomDraw(a1, v31, &v27);
      ListView_BeginFakeItemDraw(v31);
      v18 = v31[4];
    }
    format = 11297;
    DrawTextW(v18, String, v16, &rc, 0x2C21u);
    if ( *(char *)(a1 + 16) >= 0 )
    {
      format = 11281;
      if ( g_uiACP == 949 )
        format = 535569;
    }
    DrawTextW(v31[4], String, v16, &v32, format);
    v20 = String;
    v21 = 271;
    v22 = chText;
    do
    {
      if ( !v9 )
        break;
      if ( !*v20 )
        break;
      *v22++ = *v20++;
      --v9;
      --v21;
    }
    while ( v21 );
    v23 = v22 - 1;
    if ( v21 )
      v23 = v22;
    *v23 = 0;
    DrawTextW(v31[4], chText, v16, &v33, format | 0x50000);
    LOWORD(v12) = v32.bottom;
    if ( v33.bottom == v32.bottom )
    {
      v12 = lstrcmpW(String, chText);
      if ( v12 )
        ++v33.bottom;
    }
    if ( !a4 )
    {
      ListView_EndFakeItemDraw(v31);
      LOWORD(v12) = ListView_EndFakeCustomDraw(v31);
    }
  }
LABEL_33:
  if ( a2 )
  {
    v24 = LOWORD(rc.right) + 2 * g_cxLabelMargin - LOWORD(rc.left);
    *(_WORD *)(a2 + 20) = LOWORD(v32.right) + 2 * g_cxLabelMargin - LOWORD(v32.left);
    v25 = g_cyEdge;
    *(_WORD *)(a2 + 18) = v24;
    if ( *(char *)(a1 + 16) < 0 )
      v25 = 0;
    LOWORD(v12) = LOWORD(v33.bottom) + v25 - LOWORD(v33.top);
    *(_WORD *)(a2 + 24) = LOWORD(v32.bottom) + v25 - LOWORD(v32.top);
    *(_WORD *)(a2 + 22) = v12;
  }
  return v12;
}

```

## disassembly

```asm
0x180076150  push    rbp
0x180076152  push    rbx
0x180076153  push    rsi
0x180076154  push    rdi
0x180076155  push    r12
0x180076157  push    r13
0x180076159  push    r14
0x18007615b  push    r15
0x18007615d  lea     rbp, [rsp-488h]
0x180076165  sub     rsp, 588h
0x18007616c  mov     rax, cs:__security_cookie
0x180076173  xor     rax, rsp
0x180076176  mov     [rbp+4C0h+var_50], rax
0x18007617d  xorps   xmm0, xmm0
0x180076180  mov     ebx, r8d
0x180076183  mov     rdi, rdx
0x180076186  mov     rsi, rcx
0x180076189  xorps   xmm1, xmm1
0x18007618c  lea     rcx, [rsp+5C0h+var_550]; void *
0x180076191  xor     edx, edx; Val
0x180076193  mov     r8d, 88h; Size
0x180076199  movups  xmmword ptr [rbp+4C0h+rc.left], xmm0
0x18007619d  mov     r12, r9
0x1800761a0  movups  xmmword ptr [rbp+4C0h+var_4B0.left], xmm1
0x1800761a4  movups  xmmword ptr [rbp+4C0h+var_4C0.left], xmm0
0x1800761a8  call    memset
0x1800761ad  xorps   xmm0, xmm0
0x1800761b0  xor     eax, eax
0x1800761b2  xor     r13d, r13d
0x1800761b5  mov     [rsp+5C0h+var_560], rax
0x1800761ba  mov     r15d, 7FFFFFFEh
0x1800761c0  movups  [rsp+5C0h+var_590], xmm0
0x1800761c5  movups  [rsp+5C0h+var_580], xmm0
0x1800761ca  movups  [rsp+5C0h+var_570], xmm0
0x1800761cf  cmp     [rbp+4C0h+arg_20], r13d
0x1800761d6  jz      short loc_1800761FE
0x1800761d8  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800761dc  jz      short loc_1800761FE
0x1800761de  mov     rcx, [rdi]; Src
0x1800761e1  lea     rdx, [rbp+4C0h+String]; void *
0x1800761e5  mov     r8d, 109h
0x1800761eb  call    Str_GetPtrW
0x1800761f0  mov     rax, [rdi+20h]
0x1800761f4  mov     qword ptr [rsp+5C0h+var_570+8], rax
0x1800761f9  jmp     loc_1800762A2
0x1800761fe  mov     dword ptr [rsp+5C0h+var_590+4], ebx
0x180076202  lea     rax, [rbp+4C0h+String]
0x180076206  mov     ebx, 108h
0x18007620b  mov     dword ptr [rsp+5C0h+var_590], 5
0x180076213  lea     rdx, [rsp+5C0h+var_590]
0x180076218  mov     dword ptr [rsp+5C0h+var_570], ebx
0x18007621c  mov     rcx, rsi
0x18007621f  mov     dword ptr [rsp+5C0h+var_590+8], r13d
0x180076224  mov     qword ptr [rsp+5C0h+var_580+8], rax
0x180076229  mov     dword ptr [rsp+5C0h+var_580], r13d
0x18007622e  mov     [rbp+4C0h+String], r13w
0x180076233  call    ListView_OnGetItem
0x180076238  mov     rax, qword ptr [rsp+5C0h+var_580+8]
0x18007623d  test    rax, rax
0x180076240  jnz     short loc_18007625F
0x180076242  lea     rcx, [rbp+4C0h+rc]; lprc
0x180076246  call    cs:__imp_SetRectEmpty
0x18007624c  movaps  xmm0, xmmword ptr [rbp+4C0h+rc.left]
0x180076250  movdqa  xmmword ptr [rbp+4C0h+var_4B0.left], xmm0
0x180076255  movdqa  xmmword ptr [rbp+4C0h+var_4C0.left], xmm0
0x18007625a  jmp     loc_18007640A
0x18007625f  lea     rcx, [rbp+4C0h+String]
0x180076263  cmp     rax, rcx
0x180076266  jz      short loc_1800762A2
0x180076268  mov     rcx, r15
0x18007626b  lea     rdx, [rbp+4C0h+String]
0x18007626f  test    rcx, rcx
0x180076272  jz      short loc_180076293
0x180076274  movzx   r8d, word ptr [rax]
0x180076278  test    r8w, r8w
0x18007627c  jz      short loc_180076293
0x18007627e  mov     [rdx], r8w
0x180076282  add     rax, 2
0x180076286  add     rdx, 2
0x18007628a  dec     rcx
0x18007628d  sub     rbx, 1
0x180076291  jnz     short loc_18007626F
0x180076293  test    rbx, rbx
0x180076296  lea     rcx, [rdx-2]
0x18007629a  cmovnz  rcx, rdx
0x18007629e  mov     [rcx], r13w
0x1800762a2  lea     rcx, [rbp+4C0h+String]; lpString
0x1800762a6  call    cs:__imp_lstrlenW
0x1800762ac  mov     ecx, cs:g_cxLabelMargin
0x1800762b2  mov     r14d, eax
0x1800762b5  mov     edx, [rsi+108h]
0x1800762bb  add     ecx, ecx
0x1800762bd  sub     edx, ecx
0x1800762bf  mov     [rbp+4C0h+var_4C0.bottom], r13d
0x1800762c3  mov     [rbp+4C0h+var_4C0.right], edx
0x1800762c6  mov     qword ptr [rbp+4C0h+var_4C0.left], r13
0x1800762ca  movaps  xmm0, xmmword ptr [rbp+4C0h+var_4C0.left]
0x1800762ce  movdqa  xmmword ptr [rbp+4C0h+rc.left], xmm0
0x1800762d3  movdqa  xmmword ptr [rbp+4C0h+var_4B0.left], xmm0
0x1800762d8  test    eax, eax
0x1800762da  jle     loc_1800763FE
0x1800762e0  test    r12, r12
0x1800762e3  jnz     short loc_180076307
0x1800762e5  lea     r8, [rsp+5C0h+var_590]
0x1800762ea  mov     rcx, rsi
0x1800762ed  lea     rdx, [rsp+5C0h+var_550]
0x1800762f2  call    ListView_BeginFakeCustomDraw
0x1800762f7  lea     rcx, [rsp+5C0h+var_550]
0x1800762fc  call    ListView_BeginFakeItemDraw
0x180076301  mov     rcx, [rbp+4C0h+hdc]
0x180076305  jmp     short loc_18007630E
0x180076307  mov     rcx, r12; hdc
0x18007630a  mov     [rbp+4C0h+hdc], rcx
0x18007630e  mov     ebx, 2C21h
0x180076313  lea     r9, [rbp+4C0h+rc]; lprc
0x180076317  mov     r8d, r14d; cchText
0x18007631a  mov     [rsp+5C0h+format], ebx; format
0x18007631e  lea     rdx, [rbp+4C0h+String]; lpchText
0x180076322  call    cs:__imp_DrawTextW
0x180076328  test    byte ptr [rsi+10h], 80h
0x18007632c  jnz     short loc_180076345
0x18007632e  cmp     cs:g_uiACP, 3B5h
0x180076338  mov     ebx, 2C11h
0x18007633d  mov     eax, 82C11h
0x180076342  cmovz   ebx, eax
0x180076345  mov     rcx, [rbp+4C0h+hdc]; hdc
0x180076349  lea     r9, [rbp+4C0h+var_4C0]; lprc
0x18007634d  mov     r8d, r14d; cchText
0x180076350  mov     [rsp+5C0h+format], ebx; format
0x180076354  lea     rdx, [rbp+4C0h+String]; lpchText
0x180076358  call    cs:__imp_DrawTextW
0x18007635e  lea     rcx, [rbp+4C0h+String]
0x180076362  mov     edx, 10Fh
0x180076367  lea     rax, [rbp+4C0h+chText]
0x18007636e  test    r15, r15
0x180076371  jz      short loc_180076392
0x180076373  movzx   r8d, word ptr [rcx]
0x180076377  test    r8w, r8w
0x18007637b  jz      short loc_180076392
0x18007637d  mov     [rax], r8w
0x180076381  add     rcx, 2
0x180076385  add     rax, 2
0x180076389  dec     r15
0x18007638c  sub     rdx, 1
0x180076390  jnz     short loc_18007636E
0x180076392  test    rdx, rdx
0x180076395  lea     rcx, [rax-2]
0x180076399  lea     r9, [rbp+4C0h+var_4B0]; lprc
0x18007639d  mov     r8d, r14d; cchText
0x1800763a0  cmovnz  rcx, rax
0x1800763a4  lea     rdx, [rbp+4C0h+chText]; lpchText
0x1800763ab  or      ebx, 50000h
0x1800763b1  mov     [rsp+5C0h+format], ebx; format
0x1800763b5  mov     [rcx], r13w
0x1800763b9  mov     rcx, [rbp+4C0h+hdc]; hdc
0x1800763bd  call    cs:__imp_DrawTextW
0x1800763c3  mov     eax, [rbp+4C0h+var_4C0.bottom]
0x1800763c6  cmp     [rbp+4C0h+var_4B0.bottom], eax
0x1800763c9  jnz     short loc_1800763E3
0x1800763cb  lea     rdx, [rbp+4C0h+chText]; lpString2
0x1800763d2  lea     rcx, [rbp+4C0h+String]; lpString1
0x1800763d6  call    cs:__imp_lstrcmpW
0x1800763dc  test    eax, eax
0x1800763de  jz      short loc_1800763E3
0x1800763e0  inc     [rbp+4C0h+var_4B0.bottom]
0x1800763e3  test    r12, r12
0x1800763e6  jnz     short loc_18007640A
0x1800763e8  lea     rcx, [rsp+5C0h+var_550]
0x1800763ed  call    ListView_EndFakeItemDraw
0x1800763f2  lea     rcx, [rsp+5C0h+var_550]
0x1800763f7  call    ListView_EndFakeCustomDraw
0x1800763fc  jmp     short loc_18007640A
0x1800763fe  mov     eax, [rsi+80h]
0x180076404  mov     [rbp+4C0h+var_4C0.bottom], eax
0x180076407  mov     [rbp+4C0h+var_4B0.bottom], eax
0x18007640a  test    rdi, rdi
0x18007640d  jz      short loc_18007645D
0x18007640f  movzx   ecx, word ptr cs:g_cxLabelMargin
0x180076416  add     cx, cx
0x180076419  movzx   eax, cx
0x18007641c  sub     cx, word ptr [rbp+4C0h+var_4C0.left]
0x180076420  sub     ax, word ptr [rbp+4C0h+rc.left]
0x180076424  add     ax, word ptr [rbp+4C0h+rc.right]
0x180076428  add     cx, word ptr [rbp+4C0h+var_4C0.right]
0x18007642c  mov     [rdi+14h], cx
0x180076430  mov     ecx, cs:g_cyEdge
0x180076436  mov     [rdi+12h], ax
0x18007643a  test    byte ptr [rsi+10h], 80h
0x18007643e  cmovnz  ecx, r13d
0x180076442  movzx   eax, cx
0x180076445  sub     cx, word ptr [rbp+4C0h+var_4C0.top]
0x180076449  sub     ax, word ptr [rbp+4C0h+var_4B0.top]
0x18007644d  add     ax, word ptr [rbp+4C0h+var_4B0.bottom]
0x180076451  add     cx, word ptr [rbp+4C0h+var_4C0.bottom]
0x180076455  mov     [rdi+18h], cx
0x180076459  mov     [rdi+16h], ax
0x18007645d  mov     rcx, [rbp+4C0h+var_50]
0x180076464  xor     rcx, rsp; StackCookie
0x180076467  call    __security_check_cookie
0x18007646c  add     rsp, 588h
0x180076473  pop     r15
0x180076475  pop     r14
0x180076477  pop     r13
0x180076479  pop     r12
0x18007647b  pop     rdi
0x18007647c  pop     rsi
0x18007647d  pop     rbx
0x18007647e  pop     rbp
0x18007647f  retn
```
