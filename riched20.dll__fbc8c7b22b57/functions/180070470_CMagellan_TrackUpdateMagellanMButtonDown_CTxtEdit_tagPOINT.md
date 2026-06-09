# CMagellan::TrackUpdateMagellanMButtonDown(CTxtEdit &,tagPOINT)

- ea: `0x180070470`
- end: `0x180070876`
- name: `?TrackUpdateMagellanMButtonDown@CMagellan@@QEAAXAEAVCTxtEdit@@UtagPOINT@@@Z`
- size: `1030`
- prototype: `void __fastcall(CMagellan *__hidden this, struct CTxtEdit *, struct tagPOINT)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180041df8`

## callees

- `0x18001e720`
- `0x180039990`
- `0x18003dfb0`
- `0x180043044`
- `0x1800578cc`
- `0x180057c34`
- `0x180057f28`
- `0x180058318`
- `0x180070470`
- `0x180092190`
- `0x1800921c0`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!InflateRect` at `0x1800704f3`
- `USER32!InflateRect` at `0x1800704f3`
- `GDI32!DeleteObject` at `0x1800705d0`
- `GDI32!DeleteObject` at `0x1800705d0`

## pseudocode

```c
void __fastcall CMagellan::TrackUpdateMagellanMButtonDown(CMagellan *this, struct CTxtEdit *a2, struct tagPOINT a3)
{
  __int64 v3; // rsi
  unsigned __int16 v5; // r14
  LONG x; // ebx
  LONG y; // r12d
  int v8; // r13d
  int v9; // r15d
  __int16 v10; // ax
  struct tagPOINT v11; // rcx
  const unsigned __int16 *v12; // r14
  char *v13; // r14
  int v14; // ebx
  unsigned int v15; // r8d
  int v16; // eax
  int v17; // r9d
  __int64 v18; // rdx
  int v19; // r9d
  __int64 v20; // rax
  bool v21; // zf
  bool v22; // sf
  bool v23; // zf
  bool v24; // sf
  __int64 v25; // rcx
  __int64 v26; // rbx
  void (__fastcall *v27)(__int64, HICON, _QWORD); // rdi
  HICON Cursor; // rax
  unsigned __int16 v29; // [rsp+30h] [rbp-79h]
  unsigned __int16 v30; // [rsp+30h] [rbp-79h]
  unsigned __int16 v31; // [rsp+34h] [rbp-75h]
  int v32; // [rsp+38h] [rbp-71h]
  int v33; // [rsp+3Ch] [rbp-6Dh]
  int v34; // [rsp+40h] [rbp-69h]
  struct tagPOINT v35; // [rsp+48h] [rbp-61h]
  LONG v36; // [rsp+50h] [rbp-59h]
  int v37; // [rsp+54h] [rbp-55h]
  CTxtEdit *v38; // [rsp+58h] [rbp-51h]
  __int64 v39; // [rsp+60h] [rbp-49h] BYREF
  __int128 v40; // [rsp+68h] [rbp-41h]
  int v41; // [rsp+78h] [rbp-31h]
  __int64 v42; // [rsp+7Ch] [rbp-2Dh]
  __int64 v43; // [rsp+84h] [rbp-25h]
  __m128i si128; // [rsp+90h] [rbp-19h]
  __int16 v45; // [rsp+A0h] [rbp-9h]
  struct tagRECT rc; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v47; // [rsp+B8h] [rbp+Fh] BYREF

  v3 = *((_QWORD *)a2 + 8);
  rc.top = *((_DWORD *)this + 5);
  v38 = a2;
  v5 = 0;
  rc.right = 0;
  x = a3.x;
  rc.bottom = rc.top;
  rc.right = *((_DWORD *)this + 4);
  rc.left = rc.right;
  v47 = 0;
  y = a3.y;
  InflateRect(&rc, 60 * (*(__int16 *)(v3 + 38) + 12) / 1440, 60 * (*(__int16 *)(v3 + 38) + 12) / 1440);
  v29 = 0;
  v8 = 0;
  v9 = 0;
  if ( (*(_DWORD *)(v3 + 56) & 0x800) != 0 )
  {
    v5 = 1;
    if ( y < rc.top || y > rc.bottom )
    {
      v8 = 1;
      v29 = 1;
      if ( y >= *((_DWORD *)this + 5) )
        v29 = 2;
    }
  }
  if ( (unsigned int)CDisplay::IsHScrollEnabled((CDisplay *)v3) )
  {
    if ( (CTxtEdit::TxGetScrollBars(v38) & 0x100000) != 0 )
    {
      v5 |= 2u;
      if ( x < rc.left || x > rc.right )
      {
        v10 = 6;
        v9 = 1;
        if ( x >= *((_DWORD *)this + 4) )
          v10 = 3;
        v29 += v10;
      }
    }
  }
  v11 = (struct tagPOINT)v5;
  v32 = 8192000;
  v33 = 8257663;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v12 = (const unsigned __int16 *)*((unsigned __int16 *)&v32 + v5);
  v45 = 121;
  v35 = v11;
  if ( (_WORD)v12 != *((_WORD *)this + 1) )
  {
    if ( *((_QWORD *)this + 1) )
    {
      CMagellan::InvertMagellanDownBMP((HGDIOBJ *)this, (struct CDisplay *)v3, 0, 0);
      DeleteObject(*((HGDIOBJ *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
    *((_WORD *)this + 1) = (_WORD)v12;
    *((_QWORD *)this + 1) = CW32System::LoadBitmap(*(HINSTANCE *)&v11, v12);
    CMagellan::InvertMagellanDownBMP((HGDIOBJ *)this, (struct CDisplay *)v3, 1, 0);
    v11 = v35;
  }
  if ( !v8 && !v9 )
  {
    v32 = 7405568;
    v33 = 7471216;
    v30 = *((_WORD *)&v32 + *(_QWORD *)&v11);
    CDisplay::FinishSmoothVScroll((CDisplay *)v3);
    v13 = (char *)v38 + 48;
    goto LABEL_44;
  }
  v13 = (char *)v38 + 48;
  v30 = si128.m128i_u16[v29];
  (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)v38 + 6) + 192LL))(*((_QWORD *)v38 + 6), &v47);
  v14 = x - *((_DWORD *)this + 4);
  v15 = (unsigned __int16)(WORD6(v47) - WORD2(v47));
  v32 = v15;
  v36 = DWORD1(v47) + (v15 >> 1);
  v31 = ((unsigned __int16)(WORD4(v47) - v47) >> 1) - 2;
  v16 = y - *((_DWORD *)this + 5);
  v35.x = v47 + v14 + ((unsigned __int16)(WORD4(v47) - v47) >> 1);
  v17 = -v16;
  if ( v16 > 0 )
    v17 = v16;
  v37 = v17;
  if ( v17 < (int)(2 * v15) / 5 )
  {
    v34 = 0;
    v19 = CW32System::MulDiv(250 * v17 / 4, v17, v15);
    if ( !v19 )
      v19 = 1;
    if ( v8 )
      CDisplay::SmoothVScroll((CDisplay *)v3, *((_DWORD *)this + 5) - y, 0, v19, 10 * v32, 0);
  }
  else
  {
    v34 = 1;
    CDisplay::CheckRemoveSmoothVScroll((CDisplay *)v3);
    if ( v8 )
    {
      v18 = (unsigned int)((*((_DWORD *)this + 5) - y) >> 31);
      LOWORD(v18) = (v18 & 1) + 2;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v3 + 296LL))(v3, v18, 0);
    }
  }
  if ( v9 )
  {
    v35.y = v36;
    CDisplay::AutoScroll((CDisplay *)v3, v35, v31, 0);
  }
  if ( (*((_BYTE *)v38 + 176) & 8) != 0 && (v9 || v8) )
  {
    v39 = 0;
    v20 = 0;
    v40 = 0;
    if ( v9 )
    {
      v41 = 276;
      if ( v34 )
      {
        v21 = v14 == 0;
        v22 = v14 < 0;
LABEL_40:
        LOBYTE(v20) = !v22 && !v21;
        v20 += 2;
LABEL_43:
        v43 = 0;
        v25 = *(_QWORD *)v13;
        v42 = v20;
        (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 304LL))(v25, 1792, &v39);
        goto LABEL_44;
      }
      v23 = v14 == 0;
      v24 = v14 < 0;
    }
    else
    {
      v41 = 277;
      if ( v34 )
      {
        v21 = v37 == 0;
        v22 = v37 < 0;
        goto LABEL_40;
      }
      v23 = v37 == 0;
      v24 = v37 < 0;
    }
    LOBYTE(v20) = !v24 && !v23;
    goto LABEL_43;
  }
LABEL_44:
  v26 = *(_QWORD *)v13;
  v27 = *(void (__fastcall **)(__int64, HICON, _QWORD))(**(_QWORD **)v13 + 152LL);
  if ( v30 )
    Cursor = CW32System::LoadCursor(hinstRE, (const unsigned __int16 *)v30);
  else
    Cursor = CTxtEdit::_hcurArrow;
  v27(v26, Cursor, 0);
}

```

## disassembly

```asm
0x180070470  mov     [rsp-8+arg_18], rbx
0x180070475  push    rbp
0x180070476  push    rsi
0x180070477  push    rdi
0x180070478  push    r12
0x18007047a  push    r13
0x18007047c  push    r14
0x18007047e  push    r15
0x180070480  lea     rbp, [rsp-27h]
0x180070485  sub     rsp, 0D0h
0x18007048c  mov     rax, cs:__security_cookie
0x180070493  xor     rax, rsp
0x180070496  mov     [rbp+57h+var_38], rax
0x18007049a  mov     rsi, [rdx+40h]
0x18007049e  mov     rdi, rcx
0x1800704a1  mov     eax, [rcx+14h]
0x1800704a4  mov     r12, r8
0x1800704a7  mov     [rbp+57h+rc.top], eax
0x1800704aa  xorps   xmm0, xmm0
0x1800704ad  mov     [rbp+57h+var_A8], rdx
0x1800704b1  xor     r14d, r14d
0x1800704b4  mov     qword ptr [rbp+57h+rc.right], r14
0x1800704b8  mov     rbx, r8
0x1800704bb  mov     [rbp+57h+rc.bottom], eax
0x1800704be  mov     eax, [rcx+10h]
0x1800704c1  mov     [rbp+57h+rc.right], eax
0x1800704c4  mov     [rbp+57h+rc.left], eax
0x1800704c7  movups  [rbp+57h+var_48], xmm0
0x1800704cb  movsx   eax, word ptr [rsi+26h]
0x1800704cf  add     eax, 0Ch
0x1800704d2  shr     r12, 20h
0x1800704d6  imul    ecx, eax, 3Ch ; '<'
0x1800704d9  mov     eax, 0B60B60B7h
0x1800704de  imul    ecx
0x1800704e0  add     edx, ecx
0x1800704e2  lea     rcx, [rbp+57h+rc]; lprc
0x1800704e6  sar     edx, 0Ah
0x1800704e9  mov     eax, edx
0x1800704eb  shr     eax, 1Fh
0x1800704ee  add     edx, eax; dx
0x1800704f0  mov     r8d, edx; dy
0x1800704f3  call    cs:__imp_InflateRect
0x1800704fa  nop     dword ptr [rax+rax+00h]
0x1800704ff  test    dword ptr [rsi+38h], 800h
0x180070506  lea     ecx, [r14+2]
0x18007050a  mov     [rbp+57h+var_D0], r14d
0x18007050e  mov     r13d, r14d
0x180070511  mov     r15d, r14d
0x180070514  lea     eax, [rcx-1]
0x180070517  jz      short loc_18007053A
0x180070519  movzx   r14d, ax
0x18007051d  cmp     r12d, [rbp+57h+rc.top]
0x180070521  jl      short loc_180070529
0x180070523  cmp     r12d, [rbp+57h+rc.bottom]
0x180070527  jle     short loc_18007053A
0x180070529  mov     r13d, eax
0x18007052c  mov     word ptr [rbp+57h+var_D0], ax
0x180070530  cmp     r12d, [rdi+14h]
0x180070534  jl      short loc_18007053A
0x180070536  mov     word ptr [rbp+57h+var_D0], cx
0x18007053a  mov     rcx, rsi; this
0x18007053d  call    ?IsHScrollEnabled@CDisplay@@QEAAHXZ; CDisplay::IsHScrollEnabled(void)
0x180070542  test    eax, eax
0x180070544  jz      short loc_18007057B
0x180070546  mov     rcx, [rbp+57h+var_A8]; this
0x18007054a  call    ?TxGetScrollBars@CTxtEdit@@QEBAKXZ; CTxtEdit::TxGetScrollBars(void)
0x18007054f  bt      eax, 14h
0x180070553  jnb     short loc_18007057B
0x180070555  or      r14w, 2
0x18007055a  cmp     ebx, [rbp+57h+rc.left]
0x18007055d  jl      short loc_180070564
0x18007055f  cmp     ebx, [rbp+57h+rc.right]
0x180070562  jle     short loc_18007057B
0x180070564  cmp     ebx, [rdi+10h]
0x180070567  mov     eax, 6
0x18007056c  lea     ecx, [rax-3]
0x18007056f  lea     r15d, [rax-5]
0x180070573  cmovge  ax, cx
0x180070577  add     word ptr [rbp+57h+var_D0], ax
0x18007057b  movdqa  xmm0, cs:__xmm@0076007a007700740073007800750000
0x180070583  mov     eax, 79h ; 'y'
0x180070588  movzx   ecx, r14w
0x18007058c  mov     [rbp+57h+var_C8], 7D0000h
0x180070593  mov     [rbp+57h+var_C4], 7E007Fh
0x18007059a  movdqu  [rbp+57h+var_70], xmm0
0x18007059f  movzx   r14d, word ptr [rbp+rcx*2+57h+var_C8]
0x1800705a5  mov     [rbp+57h+var_60], ax
0x1800705a9  mov     qword ptr [rbp+57h+var_B8.x], rcx
0x1800705ad  cmp     r14w, [rdi+2]
0x1800705b2  jz      short loc_18007060B
0x1800705b4  cmp     qword ptr [rdi+8], 0
0x1800705b9  jz      short loc_1800705E4
0x1800705bb  xor     r9d, r9d; HDC
0x1800705be  xor     r8d, r8d; int
0x1800705c1  mov     rdx, rsi; struct CDisplay *
0x1800705c4  mov     rcx, rdi; this
0x1800705c7  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x1800705cc  mov     rcx, [rdi+8]; ho
0x1800705d0  call    cs:__imp_DeleteObject
0x1800705d7  nop     dword ptr [rax+rax+00h]
0x1800705dc  mov     qword ptr [rdi+8], 0
0x1800705e4  mov     rdx, r14; unsigned __int16 *
0x1800705e7  mov     [rdi+2], r14w
0x1800705ec  call    ?LoadBitmap@CW32System@@SAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; CW32System::LoadBitmap(HINSTANCE__ *,ushort const *)
0x1800705f1  xor     r9d, r9d; HDC
0x1800705f4  mov     [rdi+8], rax
0x1800705f8  mov     rdx, rsi; struct CDisplay *
0x1800705fb  mov     rcx, rdi; this
0x1800705fe  lea     r8d, [r9+1]; int
0x180070602  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x180070607  mov     rcx, qword ptr [rbp+57h+var_B8.x]
0x18007060b  test    r13d, r13d
0x18007060e  jnz     short loc_180070641
0x180070610  test    r15d, r15d
0x180070613  jnz     short loc_180070641
0x180070615  mov     [rbp+57h+var_C8], 710000h
0x18007061c  mov     [rbp+57h+var_C4], 720070h
0x180070623  movzx   eax, word ptr [rbp+rcx*2+57h+var_C8]
0x180070628  mov     rcx, rsi; this
0x18007062b  mov     word ptr [rbp+57h+var_D0], ax
0x18007062f  call    ?FinishSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::FinishSmoothVScroll(void)
0x180070634  mov     r14, [rbp+57h+var_A8]
0x180070638  add     r14, 30h ; '0'
0x18007063c  jmp     loc_180070810
0x180070641  movzx   eax, word ptr [rbp+57h+var_D0]
0x180070645  lea     rdx, [rbp+57h+var_48]
0x180070649  mov     r14, [rbp+57h+var_A8]
0x18007064d  add     r14, 30h ; '0'
0x180070651  movzx   eax, word ptr [rbp+rax*2+57h+var_70]
0x180070656  mov     word ptr [rbp+57h+var_D0], ax
0x18007065a  mov     rcx, [r14]
0x18007065d  mov     rax, [rcx]
0x180070660  mov     rax, [rax+0C0h]
0x180070667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007066c  mov     ecx, dword ptr [rbp+57h+var_48+4]
0x18007066f  sub     ebx, [rdi+10h]
0x180070672  movzx   eax, word ptr [rbp+57h+var_48+8]
0x180070676  sub     ax, word ptr [rbp+57h+var_48]
0x18007067a  movzx   edx, ax
0x18007067d  movzx   eax, word ptr [rbp+57h+var_48+0Ch]
0x180070681  sub     ax, cx
0x180070684  movzx   r8d, ax; int
0x180070688  mov     eax, r8d
0x18007068b  mov     [rbp+57h+var_C8], r8d
0x18007068f  shr     eax, 1
0x180070691  add     eax, ecx
0x180070693  mov     [rbp+57h+var_B0], eax
0x180070696  lea     ecx, [r8+r8]
0x18007069a  movzx   eax, dx
0x18007069d  shr     edx, 1
0x18007069f  shr     ax, 1
0x1800706a2  add     edx, ebx
0x1800706a4  add     edx, dword ptr [rbp+57h+var_48]
0x1800706a7  sub     ax, 2
0x1800706ab  mov     [rbp+57h+var_CC], ax
0x1800706af  mov     eax, r12d
0x1800706b2  sub     eax, [rdi+14h]
0x1800706b5  mov     r9d, eax
0x1800706b8  mov     [rbp+57h+var_B8.x], edx
0x1800706bb  neg     r9d
0x1800706be  cmovs   r9d, eax
0x1800706c2  mov     eax, 66666667h
0x1800706c7  imul    ecx
0x1800706c9  mov     [rbp+57h+var_AC], r9d
0x1800706cd  sar     edx, 1
0x1800706cf  mov     eax, edx
0x1800706d1  shr     eax, 1Fh
0x1800706d4  add     edx, eax
0x1800706d6  cmp     r9d, edx
0x1800706d9  jl      short loc_180070719
0x1800706db  mov     rcx, rsi; this
0x1800706de  mov     [rbp+57h+var_C0], 1
0x1800706e5  call    ?CheckRemoveSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::CheckRemoveSmoothVScroll(void)
0x1800706ea  xor     ecx, ecx
0x1800706ec  test    r13d, r13d
0x1800706ef  jz      short loc_18007076F
0x1800706f1  mov     edx, [rdi+14h]
0x1800706f4  xor     r8d, r8d
0x1800706f7  mov     rax, [rsi]
0x1800706fa  sub     edx, r12d
0x1800706fd  sar     edx, 1Fh
0x180070700  mov     rcx, rsi
0x180070703  and     dx, 1
0x180070707  add     dx, 2
0x18007070b  mov     rax, [rax+128h]
0x180070712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070717  jmp     short loc_18007076D
0x180070719  mov     ecx, 4
0x18007071e  imul    eax, r9d, 0FAh
0x180070725  mov     [rbp+57h+var_C0], 0
0x18007072c  cdq
0x18007072d  idiv    ecx
0x18007072f  mov     edx, r9d; int
0x180070732  mov     ecx, eax; int
0x180070734  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x180070739  xor     ecx, ecx
0x18007073b  mov     r9d, eax
0x18007073e  test    eax, eax
0x180070740  lea     eax, [rcx+1]
0x180070743  cmovz   r9d, eax; int
0x180070747  test    r13d, r13d
0x18007074a  jz      short loc_18007076F
0x18007074c  mov     eax, [rbp+57h+var_C8]
0x18007074f  xor     r8d, r8d; unsigned __int16
0x180070752  mov     edx, [rdi+14h]
0x180070755  mov     [rsp+100h+var_D8], ecx; int
0x180070759  sub     edx, r12d; int
0x18007075c  mov     rcx, rsi; this
0x18007075f  lea     eax, [rax+rax*4]
0x180070762  add     eax, eax
0x180070764  mov     [rsp+100h+var_E0], eax; int
0x180070768  call    ?SmoothVScroll@CDisplay@@QEAAXHGHHH@Z; CDisplay::SmoothVScroll(int,ushort,int,int,int)
0x18007076d  xor     ecx, ecx
0x18007076f  test    r15d, r15d
0x180070772  jz      short loc_180070790
0x180070774  mov     eax, [rbp+57h+var_B0]
0x180070777  xor     r9d, r9d; unsigned __int16
0x18007077a  movzx   r8d, [rbp+57h+var_CC]; unsigned __int16
0x18007077f  mov     rcx, rsi; this
0x180070782  mov     [rbp+57h+var_B8.y], eax
0x180070785  mov     rdx, qword ptr [rbp+57h+var_B8.x]; struct tagPOINT
0x180070789  call    ?AutoScroll@CDisplay@@QEAAHUtagPOINT@@GG@Z; CDisplay::AutoScroll(tagPOINT,ushort,ushort)
0x18007078e  xor     ecx, ecx
0x180070790  mov     rax, [rbp+57h+var_A8]
0x180070794  test    byte ptr [rax+0B0h], 8
0x18007079b  jz      short loc_180070810
0x18007079d  test    r15d, r15d
0x1800707a0  jnz     short loc_1800707A7
0x1800707a2  test    r13d, r13d
0x1800707a5  jz      short loc_180070810
0x1800707a7  mov     [rbp+57h+var_A0], rcx
0x1800707ab  xorps   xmm0, xmm0
0x1800707ae  mov     rax, rcx
0x1800707b1  movdqu  [rbp+57h+var_98], xmm0
0x1800707b6  test    r15d, r15d
0x1800707b9  jz      short loc_1800707CF
0x1800707bb  mov     [rbp+57h+var_88], 114h
0x1800707c2  cmp     [rbp+57h+var_C0], ecx
0x1800707c5  jz      short loc_1800707CB
0x1800707c7  test    ebx, ebx
0x1800707c9  jmp     short loc_1800707DE
0x1800707cb  test    ebx, ebx
0x1800707cd  jmp     short loc_1800707EA
0x1800707cf  mov     [rbp+57h+var_88], 115h
0x1800707d6  cmp     [rbp+57h+var_C0], ecx
0x1800707d9  jz      short loc_1800707E7
0x1800707db  cmp     [rbp+57h+var_AC], ecx
0x1800707de  setnle  al
0x1800707e1  add     rax, 2
0x1800707e5  jmp     short loc_1800707ED
0x1800707e7  cmp     [rbp+57h+var_AC], ecx
0x1800707ea  setnle  al
0x1800707ed  mov     [rbp+57h+var_7C], rcx
0x1800707f1  lea     r8, [rbp+57h+var_A0]
0x1800707f5  mov     rcx, [r14]
0x1800707f8  mov     edx, 700h
0x1800707fd  mov     [rbp+57h+var_84], rax
0x180070801  mov     rax, [rcx]
0x180070804  mov     rax, [rax+130h]
0x18007080b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070810  mov     rbx, [r14]
0x180070813  mov     rax, [rbx]
0x180070816  mov     rdi, [rax+98h]
0x18007081d  movzx   eax, word ptr [rbp+57h+var_D0]
0x180070821  test    ax, ax
0x180070824  jz      short loc_180070836
0x180070826  mov     rcx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18007082d  mov     edx, eax; unsigned __int16 *
0x18007082f  call    ?LoadCursor@CW32System@@SAPEAUHICON__@@PEAUHINSTANCE__@@PEBG@Z; CW32System::LoadCursor(HINSTANCE__ *,ushort const *)
0x180070834  jmp     short loc_18007083D
0x180070836  mov     rax, cs:?_hcurArrow@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurArrow
0x18007083d  mov     rdx, rax
0x180070840  xor     r8d, r8d
0x180070843  mov     rax, rdi
0x180070846  mov     rcx, rbx
0x180070849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007084e  mov     rcx, [rbp+57h+var_38]
0x180070852  xor     rcx, rsp; StackCookie
0x180070855  call    __security_check_cookie
0x18007085a  mov     rbx, [rsp+100h+arg_18]
0x180070862  add     rsp, 0D0h
0x180070869  pop     r15
0x18007086b  pop     r14
0x18007086d  pop     r13
0x18007086f  pop     r12
0x180070871  pop     rdi
0x180070872  pop     rsi
0x180070873  pop     rbp
0x180070874  retn
```
