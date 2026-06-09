# FlatSB_Internal_SBTrackInit

- ea: `0x1800335f0`
- end: `0x1800338e8`
- name: `FlatSB_Internal_SBTrackInit`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180034af0`

## callees

- `0x1800115f0`
- `0x180031b84`
- `0x180031eac`
- `0x180032bc4`
- `0x1800335f0`
- `0x1800338f0`

## import_xrefs

- `USER32!SetCapture` at `0x180033831`
- `USER32!SetCapture` at `0x180033898`
- `USER32!SetCapture` at `0x180033831`
- `USER32!SetCapture` at `0x180033898`
- `USER32!CopyRect` at `0x180033790`
- `USER32!CopyRect` at `0x1800338a8`
- `USER32!CopyRect` at `0x180033790`
- `USER32!CopyRect` at `0x1800338a8`
- `USER32!InflateRect` at `0x1800337f9`
- `USER32!InflateRect` at `0x1800337f9`
- `USER32!GetWindowRect` at `0x18003364d`
- `USER32!GetWindowRect` at `0x18003364d`

## pseudocode

```c
void __fastcall FlatSB_Internal_SBTrackInit(const RECT *a1, HWND a2, int a3, int a4, int a5)
{
  unsigned int v8; // esi
  int v9; // r15d
  int v10; // ebp
  int left; // edi
  RECT *p_top; // rcx
  int *p_left; // rdx
  int v14; // eax
  int right; // r8d
  LONG *p_right; // rdi
  int bottom; // ecx
  LONG v18; // eax
  int v19; // ecx
  RECT *v20; // r14
  int top; // eax
  __int64 v22; // rcx
  int v23; // r8d
  int v24; // edx
  LONG v25; // edx
  LONG v26; // edx
  LONG v27; // ecx
  unsigned __int64 v28; // rbp
  struct tagRECT Rect; // [rsp+20h] [rbp-58h] BYREF

  Rect = 0;
  if ( a4 == 6 )
  {
    v8 = 0;
  }
  else
  {
    if ( a4 != 7 )
      return;
    v8 = 1;
  }
  GetWindowRect(a2, &Rect);
  v9 = (__int16)a3 - Rect.left;
  v10 = SHIWORD(a3) - Rect.top;
  if ( a1 )
  {
    left = a1[17].left;
    if ( v8 )
      left >>= 2;
  }
  else
  {
    LOBYTE(left) = 0;
  }
  a1[6].bottom = 0;
  if ( (left & 3) == 3 )
    goto LABEL_41;
  *(_QWORD *)&a1[8].left = 0;
  a1[6].top = 0;
  a1[7].left = v8;
  a1[7].top = v8 ^ 1;
  FlatSB_Internal_CalcSBStuff(a1, v8);
  a1[6].bottom = 1;
  *(_QWORD *)&a1[5].right = FlatSB_Internal_TrackBox;
  p_top = (RECT *)&a1[9].top;
  p_left = &a1[9].left;
  if ( v8 )
  {
    p_left = &a1[9].top;
    p_top = (RECT *)&a1[9];
  }
  p_top->left = a1[2].left;
  *p_left = a1[3].top;
  p_top->right = a1[2].right;
  p_left[2] = a1[1].right;
  v14 = v9;
  right = a1[3].right;
  if ( v8 )
    v14 = v10;
  a1->bottom = v14;
  if ( v14 < right )
  {
    if ( (left & 1) == 0 )
    {
      p_right = &a1[4].right;
      a1[4].right = 0;
      p_left[2] = right;
      goto LABEL_33;
    }
    goto LABEL_40;
  }
  bottom = a1[1].bottom;
  if ( v14 >= bottom )
  {
    if ( (left & 2) == 0 )
    {
      p_right = &a1[4].right;
      a1[4].right = 1;
      *p_left = bottom;
      goto LABEL_33;
    }
LABEL_40:
    a1[6].bottom = 0;
LABEL_41:
    *(_QWORD *)&a1[5].right = 0;
    return;
  }
  p_right = &a1[4].right;
  if ( v14 >= a1[3].left )
  {
    v19 = a1[2].bottom;
    if ( v14 < v19 )
      goto LABEL_25;
    *p_right = 3;
    *p_left = v19;
    v18 = a1[1].bottom;
  }
  else
  {
    *p_right = 2;
    *p_left = right;
    v18 = a1[3].left;
  }
  p_left[2] = v18;
LABEL_33:
  while ( a5 && (unsigned int)*p_right > 1 )
  {
    if ( *p_right == 4 )
    {
      a1[1].top = a1[3].bottom / -2;
      break;
    }
LABEL_25:
    if ( a1[1].bottom - a1[3].right <= a1[3].bottom )
      goto LABEL_40;
    v20 = (RECT *)&a1[11];
    *p_right = 4;
    a1[6].right = v8;
    CopyRect((LPRECT)&a1[11], a1 + 9);
    top = a1[19].top;
    if ( top >= 0 )
    {
      v22 = *(_QWORD *)&a1->left;
      if ( v8 )
      {
        v23 = *(_DWORD *)(v22 + 20) * top;
        v24 = top * (a1[11].right - v20->left);
      }
      else
      {
        v23 = top * (a1[11].bottom - a1[11].top);
        v24 = *(_DWORD *)(v22 + 8) * top;
      }
      InflateRect((LPRECT)&a1[11], v24, v23);
    }
    else
    {
      a1[11].top = 0x80000000;
      v20->left = 0x80000000;
      a1[11].right = 0x7FFFFFFF;
      a1[11].bottom = 0x7FFFFFFF;
    }
    v25 = a1[3].left;
    *(_QWORD *)&a1[5].right = FlatSB_Internal_TrackThumb;
    a1[1].left = v25;
    a1[2].top = v25;
    v26 = v25 - a1->bottom;
    v27 = a1[v8 + 18].left;
    a1[5].top = v27;
    a1[5].left = v27;
    a1[4].bottom = v27;
    a1[1].top = v26;
    SetCapture(a2);
    FlatSB_Internal_DoScroll(a1, 5, (unsigned int)a1[4].bottom, v8);
    FlatSB_Internal_DrawThumb(a1, v8);
  }
  v28 = (unsigned __int16)v9 | (unsigned __int64)((unsigned __int16)v10 << 16);
  if ( *p_right != 4 )
  {
    a1[6].right = v8;
    SetCapture(a2);
    CopyRect((LPRECT)&a1[11], a1 + 9);
  }
  FlatSB_Internal_SBTrackLoop(a1, v28);
}

```

## disassembly

```asm
0x1800335f0  mov     [rsp+arg_18], rbx
0x1800335f5  push    rbp
0x1800335f6  push    rsi
0x1800335f7  push    rdi
0x1800335f8  push    r12
0x1800335fa  push    r13
0x1800335fc  push    r14
0x1800335fe  push    r15
0x180033600  sub     rsp, 40h
0x180033604  mov     rax, cs:__security_cookie
0x18003360b  xor     rax, rsp
0x18003360e  mov     [rsp+78h+var_48], rax
0x180033613  xor     r14d, r14d
0x180033616  xorps   xmm0, xmm0
0x180033619  mov     rdi, r8
0x18003361c  mov     r12, rdx
0x18003361f  mov     rbx, rcx
0x180033622  mov     r13d, 1
0x180033628  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x18003362d  cmp     r9d, 6
0x180033631  jnz     short loc_180033638
0x180033633  mov     esi, r14d
0x180033636  jmp     short loc_180033645
0x180033638  cmp     r9d, 7
0x18003363c  jnz     loc_1800338C3
0x180033642  mov     esi, r13d
0x180033645  lea     rdx, [rsp+78h+Rect]; lpRect
0x18003364a  mov     rcx, r12; hWnd
0x18003364d  call    cs:__imp_GetWindowRect
0x180033653  movsx   r15d, di
0x180033657  sub     r15d, [rsp+78h+Rect.left]
0x18003365c  shr     rdi, 10h
0x180033660  movsx   ebp, di
0x180033663  sub     ebp, [rsp+78h+Rect.top]
0x180033667  test    rbx, rbx
0x18003366a  jnz     short loc_180033671
0x18003366c  mov     edi, r14d
0x18003366f  jmp     short loc_18003367E
0x180033671  mov     edi, [rbx+110h]
0x180033677  test    esi, esi
0x180033679  jz      short loc_18003367E
0x18003367b  sar     edi, 2
0x18003367e  mov     eax, edi
0x180033680  mov     [rbx+6Ch], r14d
0x180033684  and     eax, 3
0x180033687  cmp     al, 3
0x180033689  jz      loc_1800338BF
0x18003368f  mov     [rbx+80h], r14
0x180033696  mov     eax, esi
0x180033698  mov     [rbx+64h], r14d
0x18003369c  xor     eax, r13d
0x18003369f  mov     [rbx+70h], esi
0x1800336a2  mov     edx, esi
0x1800336a4  mov     rcx, rbx
0x1800336a7  mov     [rbx+74h], eax
0x1800336aa  call    FlatSB_Internal_CalcSBStuff
0x1800336af  mov     [rbx+6Ch], r13d
0x1800336b3  lea     rax, FlatSB_Internal_TrackBox
0x1800336ba  mov     [rbx+58h], rax
0x1800336be  lea     r13, [rbx+90h]
0x1800336c5  mov     eax, [rbx+20h]
0x1800336c8  lea     rcx, [r13+4]
0x1800336cc  test    esi, esi
0x1800336ce  mov     rdx, r13
0x1800336d1  cmovnz  rdx, rcx
0x1800336d5  cmovnz  rcx, r13
0x1800336d9  mov     [rcx], eax
0x1800336db  mov     eax, [rbx+34h]
0x1800336de  mov     [rdx], eax
0x1800336e0  mov     eax, [rbx+28h]
0x1800336e3  mov     [rcx+8], eax
0x1800336e6  mov     eax, [rbx+18h]
0x1800336e9  mov     [rdx+8], eax
0x1800336ec  mov     eax, r15d
0x1800336ef  mov     r8d, [rbx+38h]
0x1800336f3  cmovnz  eax, ebp
0x1800336f6  mov     [rbx+0Ch], eax
0x1800336f9  cmp     eax, r8d
0x1800336fc  jge     short loc_180033718
0x1800336fe  test    dil, 1
0x180033702  jnz     loc_1800338BB
0x180033708  lea     rdi, [rbx+48h]
0x18003370c  mov     [rdi], r14d
0x18003370f  mov     [rdx+8], r8d
0x180033713  jmp     loc_180033858
0x180033718  mov     ecx, [rbx+1Ch]
0x18003371b  cmp     eax, ecx
0x18003371d  jl      short loc_18003373A
0x18003371f  test    dil, 2
0x180033723  jnz     loc_1800338BB
0x180033729  lea     rdi, [rbx+48h]
0x18003372d  mov     dword ptr [rdi], 1
0x180033733  mov     [rdx], ecx
0x180033735  jmp     loc_180033858
0x18003373a  lea     rdi, [rbx+48h]
0x18003373e  cmp     eax, [rbx+30h]
0x180033741  jge     short loc_180033757
0x180033743  mov     dword ptr [rdi], 2
0x180033749  mov     [rdx], r8d
0x18003374c  mov     eax, [rbx+30h]
0x18003374f  mov     [rdx+8], eax
0x180033752  jmp     loc_180033858
0x180033757  mov     ecx, [rbx+2Ch]
0x18003375a  cmp     eax, ecx
0x18003375c  jl      short loc_18003376B
0x18003375e  mov     dword ptr [rdi], 3
0x180033764  mov     [rdx], ecx
0x180033766  mov     eax, [rbx+1Ch]
0x180033769  jmp     short loc_18003374F
0x18003376b  mov     eax, [rbx+1Ch]
0x18003376e  sub     eax, [rbx+38h]
0x180033771  cmp     eax, [rbx+3Ch]
0x180033774  jle     loc_1800338BB
0x18003377a  lea     r14, [rbx+0B0h]
0x180033781  mov     dword ptr [rdi], 4
0x180033787  mov     rcx, r14; lprcDst
0x18003378a  mov     [rbx+68h], esi
0x18003378d  mov     rdx, r13; lprcSrc
0x180033790  call    cs:__imp_CopyRect
0x180033796  mov     eax, [rbx+134h]
0x18003379c  test    eax, eax
0x18003379e  jns     short loc_1800337C1
0x1800337a0  mov     eax, 80000000h
0x1800337a5  mov     [rbx+0B4h], eax
0x1800337ab  mov     [r14], eax
0x1800337ae  mov     eax, 7FFFFFFFh
0x1800337b3  mov     [rbx+0B8h], eax
0x1800337b9  mov     [rbx+0BCh], eax
0x1800337bf  jmp     short loc_1800337FF
0x1800337c1  mov     rcx, [rbx]
0x1800337c4  test    esi, esi
0x1800337c6  jz      short loc_1800337DE
0x1800337c8  mov     edx, [rbx+0B8h]
0x1800337ce  mov     r8d, eax
0x1800337d1  imul    r8d, [rcx+14h]
0x1800337d6  sub     edx, [r14]
0x1800337d9  imul    edx, eax
0x1800337dc  jmp     short loc_1800337F6
0x1800337de  mov     r8d, [rbx+0BCh]
0x1800337e5  sub     r8d, [rbx+0B4h]
0x1800337ec  imul    r8d, eax; dy
0x1800337f0  imul    eax, [rcx+8]
0x1800337f4  mov     edx, eax; dx
0x1800337f6  mov     rcx, r14; lprc
0x1800337f9  call    cs:__imp_InflateRect
0x1800337ff  mov     edx, [rbx+30h]
0x180033802  lea     rax, FlatSB_Internal_TrackThumb
0x180033809  mov     [rbx+58h], rax
0x18003380d  mov     [rbx+10h], edx
0x180033810  mov     [rbx+24h], edx
0x180033813  sub     edx, [rbx+0Ch]
0x180033816  mov     eax, esi
0x180033818  add     rax, 12h
0x18003381c  add     rax, rax
0x18003381f  mov     ecx, [rbx+rax*8]
0x180033822  mov     [rbx+54h], ecx
0x180033825  mov     [rbx+50h], ecx
0x180033828  mov     [rbx+4Ch], ecx
0x18003382b  mov     rcx, r12; hWnd
0x18003382e  mov     [rbx+14h], edx
0x180033831  call    cs:__imp_SetCapture
0x180033837  mov     r8d, [rbx+4Ch]
0x18003383b  mov     r9d, esi
0x18003383e  mov     edx, 5
0x180033843  mov     rcx, rbx
0x180033846  call    FlatSB_Internal_DoScroll
0x18003384b  mov     edx, esi
0x18003384d  mov     rcx, rbx
0x180033850  call    FlatSB_Internal_DrawThumb
0x180033855  xor     r14d, r14d
0x180033858  cmp     [rsp+78h+arg_20], r14d
0x180033860  jz      short loc_18003387D
0x180033862  cmp     dword ptr [rdi], 1
0x180033865  jbe     short loc_18003387D
0x180033867  cmp     dword ptr [rdi], 4
0x18003386a  jnz     loc_18003376B
0x180033870  mov     eax, [rbx+3Ch]
0x180033873  cdq
0x180033874  sub     eax, edx
0x180033876  sar     eax, 1
0x180033878  neg     eax
0x18003387a  mov     [rbx+14h], eax
0x18003387d  movzx   ecx, bp
0x180033880  shl     ecx, 10h
0x180033883  movsxd  rbp, ecx
0x180033886  movzx   eax, r15w
0x18003388a  or      rbp, rax
0x18003388d  cmp     dword ptr [rdi], 4
0x180033890  jz      short loc_1800338AE
0x180033892  mov     rcx, r12; hWnd
0x180033895  mov     [rbx+68h], esi
0x180033898  call    cs:__imp_SetCapture
0x18003389e  lea     rcx, [rbx+0B0h]; lprcDst
0x1800338a5  mov     rdx, r13; lprcSrc
0x1800338a8  call    cs:__imp_CopyRect
0x1800338ae  mov     rdx, rbp
0x1800338b1  mov     rcx, rbx
0x1800338b4  call    FlatSB_Internal_SBTrackLoop
0x1800338b9  jmp     short loc_1800338C3
0x1800338bb  mov     [rbx+6Ch], r14d
0x1800338bf  mov     [rbx+58h], r14
0x1800338c3  mov     rcx, [rsp+78h+var_48]
0x1800338c8  xor     rcx, rsp; StackCookie
0x1800338cb  call    __security_check_cookie
0x1800338d0  mov     rbx, [rsp+78h+arg_18]
0x1800338d8  add     rsp, 40h
0x1800338dc  pop     r15
0x1800338de  pop     r14
0x1800338e0  pop     r13
0x1800338e2  pop     r12
0x1800338e4  pop     rdi
0x1800338e5  pop     rsi
0x1800338e6  pop     rbp
0x1800338e7  retn
```
