# CMagellan::TrackUpdateMagellanMButtonDown(CTxtEdit &,tagPOINT)

- ea: `0x18006e61c`
- end: `0x18006ea15`
- name: `?TrackUpdateMagellanMButtonDown@CMagellan@@QEAAXAEAVCTxtEdit@@UtagPOINT@@@Z`
- size: `1017`
- prototype: `void __fastcall(CMagellan *__hidden this, struct CTxtEdit *, struct tagPOINT)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1800412d4`

## callees

- `0x180038bd0`
- `0x18003aeb0`
- `0x18003d2c0`
- `0x18004222c`
- `0x18005634c`
- `0x1800566ac`
- `0x180056994`
- `0x180056d74`
- `0x18006e61c`
- `0x18008f86c`
- `0x18008f890`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!InflateRect` at `0x18006e69f`
- `USER32!InflateRect` at `0x18006e69f`
- `GDI32!DeleteObject` at `0x18006e776`
- `GDI32!DeleteObject` at `0x18006e776`

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
0x18006e61c  mov     [rsp-8+arg_18], rbx
0x18006e621  push    rbp
0x18006e622  push    rsi
0x18006e623  push    rdi
0x18006e624  push    r12
0x18006e626  push    r13
0x18006e628  push    r14
0x18006e62a  push    r15
0x18006e62c  lea     rbp, [rsp-27h]
0x18006e631  sub     rsp, 0D0h
0x18006e638  mov     rax, cs:__security_cookie
0x18006e63f  xor     rax, rsp
0x18006e642  mov     [rbp+57h+var_38], rax
0x18006e646  mov     rsi, [rdx+40h]
0x18006e64a  mov     rdi, rcx
0x18006e64d  mov     eax, [rcx+14h]
0x18006e650  mov     r12, r8
0x18006e653  mov     [rbp+57h+rc.top], eax
0x18006e656  xorps   xmm0, xmm0
0x18006e659  mov     [rbp+57h+var_A8], rdx
0x18006e65d  xor     r14d, r14d
0x18006e660  mov     qword ptr [rbp+57h+rc.right], r14
0x18006e664  mov     rbx, r8
0x18006e667  mov     [rbp+57h+rc.bottom], eax
0x18006e66a  mov     eax, [rcx+10h]
0x18006e66d  mov     [rbp+57h+rc.right], eax
0x18006e670  mov     [rbp+57h+rc.left], eax
0x18006e673  movups  [rbp+57h+var_48], xmm0
0x18006e677  movsx   eax, word ptr [rsi+26h]
0x18006e67b  add     eax, 0Ch
0x18006e67e  shr     r12, 20h
0x18006e682  imul    ecx, eax, 3Ch ; '<'
0x18006e685  mov     eax, 0B60B60B7h
0x18006e68a  imul    ecx
0x18006e68c  add     edx, ecx
0x18006e68e  lea     rcx, [rbp+57h+rc]; lprc
0x18006e692  sar     edx, 0Ah
0x18006e695  mov     eax, edx
0x18006e697  shr     eax, 1Fh
0x18006e69a  add     edx, eax; dx
0x18006e69c  mov     r8d, edx; dy
0x18006e69f  call    cs:__imp_InflateRect
0x18006e6a5  test    dword ptr [rsi+38h], 800h
0x18006e6ac  lea     ecx, [r14+2]
0x18006e6b0  mov     [rbp+57h+var_D0], r14d
0x18006e6b4  mov     r13d, r14d
0x18006e6b7  mov     r15d, r14d
0x18006e6ba  lea     eax, [rcx-1]
0x18006e6bd  jz      short loc_18006E6E0
0x18006e6bf  movzx   r14d, ax
0x18006e6c3  cmp     r12d, [rbp+57h+rc.top]
0x18006e6c7  jl      short loc_18006E6CF
0x18006e6c9  cmp     r12d, [rbp+57h+rc.bottom]
0x18006e6cd  jle     short loc_18006E6E0
0x18006e6cf  mov     r13d, eax
0x18006e6d2  mov     word ptr [rbp+57h+var_D0], ax
0x18006e6d6  cmp     r12d, [rdi+14h]
0x18006e6da  jl      short loc_18006E6E0
0x18006e6dc  mov     word ptr [rbp+57h+var_D0], cx
0x18006e6e0  mov     rcx, rsi; this
0x18006e6e3  call    ?IsHScrollEnabled@CDisplay@@QEAAHXZ; CDisplay::IsHScrollEnabled(void)
0x18006e6e8  test    eax, eax
0x18006e6ea  jz      short loc_18006E721
0x18006e6ec  mov     rcx, [rbp+57h+var_A8]; this
0x18006e6f0  call    ?TxGetScrollBars@CTxtEdit@@QEBAKXZ; CTxtEdit::TxGetScrollBars(void)
0x18006e6f5  bt      eax, 14h
0x18006e6f9  jnb     short loc_18006E721
0x18006e6fb  or      r14w, 2
0x18006e700  cmp     ebx, [rbp+57h+rc.left]
0x18006e703  jl      short loc_18006E70A
0x18006e705  cmp     ebx, [rbp+57h+rc.right]
0x18006e708  jle     short loc_18006E721
0x18006e70a  cmp     ebx, [rdi+10h]
0x18006e70d  mov     eax, 6
0x18006e712  lea     ecx, [rax-3]
0x18006e715  lea     r15d, [rax-5]
0x18006e719  cmovge  ax, cx
0x18006e71d  add     word ptr [rbp+57h+var_D0], ax
0x18006e721  movdqa  xmm0, cs:__xmm@0076007a007700740073007800750000
0x18006e729  mov     eax, 79h ; 'y'
0x18006e72e  movzx   ecx, r14w
0x18006e732  mov     [rbp+57h+var_C8], 7D0000h
0x18006e739  mov     [rbp+57h+var_C4], 7E007Fh
0x18006e740  movdqu  [rbp+57h+var_70], xmm0
0x18006e745  movzx   r14d, word ptr [rbp+rcx*2+57h+var_C8]
0x18006e74b  mov     [rbp+57h+var_60], ax
0x18006e74f  mov     qword ptr [rbp+57h+var_B8.x], rcx
0x18006e753  cmp     r14w, [rdi+2]
0x18006e758  jz      short loc_18006E7AB
0x18006e75a  cmp     qword ptr [rdi+8], 0
0x18006e75f  jz      short loc_18006E784
0x18006e761  xor     r9d, r9d; HDC
0x18006e764  xor     r8d, r8d; int
0x18006e767  mov     rdx, rsi; struct CDisplay *
0x18006e76a  mov     rcx, rdi; this
0x18006e76d  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x18006e772  mov     rcx, [rdi+8]; ho
0x18006e776  call    cs:__imp_DeleteObject
0x18006e77c  mov     qword ptr [rdi+8], 0
0x18006e784  mov     rdx, r14; unsigned __int16 *
0x18006e787  mov     [rdi+2], r14w
0x18006e78c  call    ?LoadBitmap@CW32System@@SAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; CW32System::LoadBitmap(HINSTANCE__ *,ushort const *)
0x18006e791  xor     r9d, r9d; HDC
0x18006e794  mov     [rdi+8], rax
0x18006e798  mov     rdx, rsi; struct CDisplay *
0x18006e79b  mov     rcx, rdi; this
0x18006e79e  lea     r8d, [r9+1]; int
0x18006e7a2  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x18006e7a7  mov     rcx, qword ptr [rbp+57h+var_B8.x]
0x18006e7ab  test    r13d, r13d
0x18006e7ae  jnz     short loc_18006E7E1
0x18006e7b0  test    r15d, r15d
0x18006e7b3  jnz     short loc_18006E7E1
0x18006e7b5  mov     [rbp+57h+var_C8], 710000h
0x18006e7bc  mov     [rbp+57h+var_C4], 720070h
0x18006e7c3  movzx   eax, word ptr [rbp+rcx*2+57h+var_C8]
0x18006e7c8  mov     rcx, rsi; this
0x18006e7cb  mov     word ptr [rbp+57h+var_D0], ax
0x18006e7cf  call    ?FinishSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::FinishSmoothVScroll(void)
0x18006e7d4  mov     r14, [rbp+57h+var_A8]
0x18006e7d8  add     r14, 30h ; '0'
0x18006e7dc  jmp     loc_18006E9B0
0x18006e7e1  movzx   eax, word ptr [rbp+57h+var_D0]
0x18006e7e5  lea     rdx, [rbp+57h+var_48]
0x18006e7e9  mov     r14, [rbp+57h+var_A8]
0x18006e7ed  add     r14, 30h ; '0'
0x18006e7f1  movzx   eax, word ptr [rbp+rax*2+57h+var_70]
0x18006e7f6  mov     word ptr [rbp+57h+var_D0], ax
0x18006e7fa  mov     rcx, [r14]
0x18006e7fd  mov     rax, [rcx]
0x18006e800  mov     rax, [rax+0C0h]
0x18006e807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e80c  mov     ecx, dword ptr [rbp+57h+var_48+4]
0x18006e80f  sub     ebx, [rdi+10h]
0x18006e812  movzx   eax, word ptr [rbp+57h+var_48+8]
0x18006e816  sub     ax, word ptr [rbp+57h+var_48]
0x18006e81a  movzx   edx, ax
0x18006e81d  movzx   eax, word ptr [rbp+57h+var_48+0Ch]
0x18006e821  sub     ax, cx
0x18006e824  movzx   r8d, ax; int
0x18006e828  mov     eax, r8d
0x18006e82b  mov     [rbp+57h+var_C8], r8d
0x18006e82f  shr     eax, 1
0x18006e831  add     eax, ecx
0x18006e833  mov     [rbp+57h+var_B0], eax
0x18006e836  lea     ecx, [r8+r8]
0x18006e83a  movzx   eax, dx
0x18006e83d  shr     edx, 1
0x18006e83f  shr     ax, 1
0x18006e842  add     edx, ebx
0x18006e844  add     edx, dword ptr [rbp+57h+var_48]
0x18006e847  sub     ax, 2
0x18006e84b  mov     [rbp+57h+var_CC], ax
0x18006e84f  mov     eax, r12d
0x18006e852  sub     eax, [rdi+14h]
0x18006e855  mov     r9d, eax
0x18006e858  mov     [rbp+57h+var_B8.x], edx
0x18006e85b  neg     r9d
0x18006e85e  cmovs   r9d, eax
0x18006e862  mov     eax, 66666667h
0x18006e867  imul    ecx
0x18006e869  mov     [rbp+57h+var_AC], r9d
0x18006e86d  sar     edx, 1
0x18006e86f  mov     eax, edx
0x18006e871  shr     eax, 1Fh
0x18006e874  add     edx, eax
0x18006e876  cmp     r9d, edx
0x18006e879  jl      short loc_18006E8B9
0x18006e87b  mov     rcx, rsi; this
0x18006e87e  mov     [rbp+57h+var_C0], 1
0x18006e885  call    ?CheckRemoveSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::CheckRemoveSmoothVScroll(void)
0x18006e88a  xor     ecx, ecx
0x18006e88c  test    r13d, r13d
0x18006e88f  jz      short loc_18006E90F
0x18006e891  mov     edx, [rdi+14h]
0x18006e894  xor     r8d, r8d
0x18006e897  mov     rax, [rsi]
0x18006e89a  sub     edx, r12d
0x18006e89d  sar     edx, 1Fh
0x18006e8a0  mov     rcx, rsi
0x18006e8a3  and     dx, 1
0x18006e8a7  add     dx, 2
0x18006e8ab  mov     rax, [rax+128h]
0x18006e8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8b7  jmp     short loc_18006E90D
0x18006e8b9  mov     ecx, 4
0x18006e8be  imul    eax, r9d, 0FAh
0x18006e8c5  mov     [rbp+57h+var_C0], 0
0x18006e8cc  cdq
0x18006e8cd  idiv    ecx
0x18006e8cf  mov     edx, r9d; int
0x18006e8d2  mov     ecx, eax; int
0x18006e8d4  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18006e8d9  xor     ecx, ecx
0x18006e8db  mov     r9d, eax
0x18006e8de  test    eax, eax
0x18006e8e0  lea     eax, [rcx+1]
0x18006e8e3  cmovz   r9d, eax; int
0x18006e8e7  test    r13d, r13d
0x18006e8ea  jz      short loc_18006E90F
0x18006e8ec  mov     eax, [rbp+57h+var_C8]
0x18006e8ef  xor     r8d, r8d; unsigned __int16
0x18006e8f2  mov     edx, [rdi+14h]
0x18006e8f5  mov     [rsp+100h+var_D8], ecx; int
0x18006e8f9  sub     edx, r12d; int
0x18006e8fc  mov     rcx, rsi; this
0x18006e8ff  lea     eax, [rax+rax*4]
0x18006e902  add     eax, eax
0x18006e904  mov     [rsp+100h+var_E0], eax; int
0x18006e908  call    ?SmoothVScroll@CDisplay@@QEAAXHGHHH@Z; CDisplay::SmoothVScroll(int,ushort,int,int,int)
0x18006e90d  xor     ecx, ecx
0x18006e90f  test    r15d, r15d
0x18006e912  jz      short loc_18006E930
0x18006e914  mov     eax, [rbp+57h+var_B0]
0x18006e917  xor     r9d, r9d; unsigned __int16
0x18006e91a  movzx   r8d, [rbp+57h+var_CC]; unsigned __int16
0x18006e91f  mov     rcx, rsi; this
0x18006e922  mov     [rbp+57h+var_B8.y], eax
0x18006e925  mov     rdx, qword ptr [rbp+57h+var_B8.x]; struct tagPOINT
0x18006e929  call    ?AutoScroll@CDisplay@@QEAAHUtagPOINT@@GG@Z; CDisplay::AutoScroll(tagPOINT,ushort,ushort)
0x18006e92e  xor     ecx, ecx
0x18006e930  mov     rax, [rbp+57h+var_A8]
0x18006e934  test    byte ptr [rax+0B0h], 8
0x18006e93b  jz      short loc_18006E9B0
0x18006e93d  test    r15d, r15d
0x18006e940  jnz     short loc_18006E947
0x18006e942  test    r13d, r13d
0x18006e945  jz      short loc_18006E9B0
0x18006e947  mov     [rbp+57h+var_A0], rcx
0x18006e94b  xorps   xmm0, xmm0
0x18006e94e  mov     rax, rcx
0x18006e951  movdqu  [rbp+57h+var_98], xmm0
0x18006e956  test    r15d, r15d
0x18006e959  jz      short loc_18006E96F
0x18006e95b  mov     [rbp+57h+var_88], 114h
0x18006e962  cmp     [rbp+57h+var_C0], ecx
0x18006e965  jz      short loc_18006E96B
0x18006e967  test    ebx, ebx
0x18006e969  jmp     short loc_18006E97E
0x18006e96b  test    ebx, ebx
0x18006e96d  jmp     short loc_18006E98A
0x18006e96f  mov     [rbp+57h+var_88], 115h
0x18006e976  cmp     [rbp+57h+var_C0], ecx
0x18006e979  jz      short loc_18006E987
0x18006e97b  cmp     [rbp+57h+var_AC], ecx
0x18006e97e  setnle  al
0x18006e981  add     rax, 2
0x18006e985  jmp     short loc_18006E98D
0x18006e987  cmp     [rbp+57h+var_AC], ecx
0x18006e98a  setnle  al
0x18006e98d  mov     [rbp+57h+var_7C], rcx
0x18006e991  lea     r8, [rbp+57h+var_A0]
0x18006e995  mov     rcx, [r14]
0x18006e998  mov     edx, 700h
0x18006e99d  mov     [rbp+57h+var_84], rax
0x18006e9a1  mov     rax, [rcx]
0x18006e9a4  mov     rax, [rax+130h]
0x18006e9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e9b0  mov     rbx, [r14]
0x18006e9b3  mov     rax, [rbx]
0x18006e9b6  mov     rdi, [rax+98h]
0x18006e9bd  movzx   eax, word ptr [rbp+57h+var_D0]
0x18006e9c1  test    ax, ax
0x18006e9c4  jz      short loc_18006E9D6
0x18006e9c6  mov     rcx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18006e9cd  mov     edx, eax; unsigned __int16 *
0x18006e9cf  call    ?LoadCursor@CW32System@@SAPEAUHICON__@@PEAUHINSTANCE__@@PEBG@Z; CW32System::LoadCursor(HINSTANCE__ *,ushort const *)
0x18006e9d4  jmp     short loc_18006E9DD
0x18006e9d6  mov     rax, cs:?_hcurArrow@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurArrow
0x18006e9dd  mov     rdx, rax
0x18006e9e0  xor     r8d, r8d
0x18006e9e3  mov     rax, rdi
0x18006e9e6  mov     rcx, rbx
0x18006e9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e9ee  mov     rcx, [rbp+57h+var_38]
0x18006e9f2  xor     rcx, rsp; StackCookie
0x18006e9f5  call    __security_check_cookie
0x18006e9fa  mov     rbx, [rsp+100h+arg_18]
0x18006ea02  add     rsp, 0D0h
0x18006ea09  pop     r15
0x18006ea0b  pop     r14
0x18006ea0d  pop     r13
0x18006ea0f  pop     r12
0x18006ea11  pop     rdi
0x18006ea12  pop     rsi
0x18006ea13  pop     rbp
0x18006ea14  retn
```
