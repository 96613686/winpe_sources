# CUIFSchemeDef::DrawCtrlBitmap(HDC__ *,tagRECT const *,HBITMAP__ *,HBITMAP__ *,ulong)

- ea: `0x1800db930`
- end: `0x1800dbbb3`
- name: `?DrawCtrlBitmap@CUIFSchemeDef@@UEAAXPEAUHDC__@@PEBUtagRECT@@PEAUHBITMAP__@@2K@Z`
- size: `643`
- prototype: `void(CUIFSchemeDef *__hidden this, HDC, const struct tagRECT *, HBITMAP, HBITMAP, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18006c598`
- `0x1800d9a6c`
- `0x1800d9a94`
- `0x1800d9e38`
- `0x1800da020`
- `0x1800da278`
- `0x1800da328`
- `0x1800dab08`
- `0x1800dadac`
- `0x1800db930`
- `0x1800de4d4`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800db9cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800db9cc`
- `USER32!GetSysColor` at `0x1800dbb07`
- `USER32!GetSysColor` at `0x1800dbb14`
- `USER32!GetSysColor` at `0x1800dbb07`
- `USER32!GetSysColor` at `0x1800dbb14`
- `GDI32!DeleteObject` at `0x1800dbb75`
- `GDI32!DeleteObject` at `0x1800dbb83`
- `GDI32!DeleteObject` at `0x1800dbb93`
- `GDI32!DeleteObject` at `0x1800dbb9c`
- `GDI32!DeleteObject` at `0x1800dbb75`
- `GDI32!DeleteObject` at `0x1800dbb83`
- `GDI32!DeleteObject` at `0x1800dbb93`
- `GDI32!DeleteObject` at `0x1800dbb9c`
- `GDI32!GetStockObject` at `0x1800db977`
- `GDI32!GetStockObject` at `0x1800db977`

## pseudocode

```c
void __fastcall CUIFSchemeDef::DrawCtrlBitmap(
        CUIFSchemeDef *this,
        HDC a2,
        const struct tagRECT *a3,
        HBITMAP a4,
        HBITMAP a5,
        char a6)
{
  HBRUSH v10; // rax
  HBRUSH StockObject; // rax
  HBITMAP v12; // r15
  HBRUSH DitherBrush; // rsi
  CBitmapDC *v14; // rax
  int v15; // edx
  CBitmapDC *v16; // rax
  HDC *v17; // rbx
  unsigned int v18; // edx
  int v19; // r13d
  HBRUSH v20; // rbx
  HBRUSH v21; // rax
  HBITMAP DisabledBitmap; // rax
  DWORD SysColor; // ebx
  DWORD v24; // eax
  HBITMAP v25; // rbx
  unsigned __int64 v26; // [rsp+20h] [rbp-88h]
  unsigned __int64 v27; // [rsp+20h] [rbp-88h]
  int v28; // [rsp+30h] [rbp-78h]
  int v29; // [rsp+38h] [rbp-70h]

  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    v10 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeDef *, __int64))(*(_QWORD *)this + 16LL))(this, 9);
    a4 = CUIMirrorBitmap(a4, v10);
    StockObject = (HBRUSH)GetStockObject(4);
    v12 = CUIMirrorBitmap(a5, StockObject);
  }
  else
  {
    v12 = a5;
  }
  DitherBrush = (HBRUSH)ProcessAlphaBitmap(a2, a4, *((_DWORD *)this + 2) & 1);
  if ( DitherBrush )
  {
    v14 = (CBitmapDC *)LocalAlloc(0x40u, 0x20u);
    if ( v14 )
    {
      v16 = CBitmapDC::CBitmapDC(v14, v15);
      v17 = (HDC *)v16;
      if ( v16 )
      {
        CBitmapDC::SetBitmap(v16, (HBITMAP)DitherBrush);
        CUIAlphaBlend(
          a2,
          a3->left,
          a3->top,
          a3->right - a3->left,
          a3->bottom - a3->top,
          v17[3],
          v28,
          v29,
          a3->right - a3->left,
          a3->bottom - a3->top,
          (struct _BLENDFUNCTION)33488896);
        CBitmapDC::`scalar deleting destructor'((CBitmapDC *)v17, v18);
      }
    }
LABEL_18:
    DeleteObject(DitherBrush);
    goto LABEL_19;
  }
  if ( !v12 )
  {
    CUIDrawState(
      a2,
      0,
      (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->top,
      (__int64)a4,
      v26,
      a3->left,
      a3->top,
      a3->right - a3->left,
      a3->bottom - a3->top,
      (a6 & 0x20) != 0 ? 164 : 4);
    goto LABEL_19;
  }
  v19 = 0;
  if ( (a6 & 0x20) != 0 )
  {
    DitherBrush = 0;
    v20 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeDef *, __int64))(*(_QWORD *)this + 16LL))(this, 11);
    v21 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeDef *, __int64))(*(_QWORD *)this + 16LL))(this, 9);
    DisabledBitmap = CreateDisabledBitmap(a3, v12, v21, v20, 1);
  }
  else
  {
    DitherBrush = (HBRUSH)16;
    if ( (a6 & 0x12) == 0x10 )
    {
      DitherBrush = CreateDitherBrush();
      v19 = 1;
    }
    SysColor = GetSysColor(20);
    v24 = GetSysColor(15);
    DisabledBitmap = CreateMaskBmp(a3, a4, v12, DitherBrush, v24, SysColor);
  }
  v25 = DisabledBitmap;
  if ( DisabledBitmap )
  {
    CUIDrawState(
      a2,
      0,
      (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->left,
      (__int64)DisabledBitmap,
      v27,
      a3->left,
      a3->top,
      a3->right - a3->left,
      a3->bottom - a3->top,
      4u);
    DeleteObject(v25);
  }
  if ( v19 )
    goto LABEL_18;
LABEL_19:
  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    DeleteObject(a4);
    DeleteObject(v12);
  }
}

```

## disassembly

```asm
0x1800db930  push    rbx
0x1800db932  push    rbp
0x1800db933  push    rsi
0x1800db934  push    rdi
0x1800db935  push    r12
0x1800db937  push    r13
0x1800db939  push    r14
0x1800db93b  push    r15
0x1800db93d  sub     rsp, 68h
0x1800db941  test    byte ptr [rcx+8], 1
0x1800db945  mov     rbp, r9
0x1800db948  mov     rdi, r8
0x1800db94b  mov     r12, rdx
0x1800db94e  mov     r14, rcx
0x1800db951  jz      short loc_1800DB992
0x1800db953  mov     rax, [rcx]
0x1800db956  mov     edx, 9
0x1800db95b  mov     rax, [rax+10h]
0x1800db95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db964  mov     rdx, rax; hbr
0x1800db967  mov     rcx, rbp; HBITMAP
0x1800db96a  call    ?CUIMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@PEAUHBRUSH__@@@Z; CUIMirrorBitmap(HBITMAP__ *,HBRUSH__ *)
0x1800db96f  mov     ecx, 4; i
0x1800db974  mov     rbp, rax
0x1800db977  call    cs:__imp_GetStockObject
0x1800db97d  mov     rcx, [rsp+0A8h+arg_20]; HBITMAP
0x1800db985  mov     rdx, rax; hbr
0x1800db988  call    ?CUIMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@PEAUHBRUSH__@@@Z; CUIMirrorBitmap(HBITMAP__ *,HBRUSH__ *)
0x1800db98d  mov     r15, rax
0x1800db990  jmp     short loc_1800DB99A
0x1800db992  mov     r15, [rsp+0A8h+arg_20]
0x1800db99a  mov     r8d, [r14+8]
0x1800db99e  mov     rdx, rbp; hbm
0x1800db9a1  and     r8d, 1; int
0x1800db9a5  mov     rcx, r12; hdc
0x1800db9a8  call    ?ProcessAlphaBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAU1@H@Z; ProcessAlphaBitmap(HDC__ *,HBITMAP__ *,int)
0x1800db9ad  mov     rsi, rax
0x1800db9b0  test    rax, rax
0x1800db9b3  jz      loc_1800DBA43
0x1800db9b9  mov     edx, 20h ; ' '; uBytes
0x1800db9be  mov     dword ptr [rsp+0A8h+arg_0.BlendOp], 1FF0000h
0x1800db9c9  lea     ecx, [rdx+20h]; uFlags
0x1800db9cc  call    cs:__imp_LocalAlloc
0x1800db9d2  test    rax, rax
0x1800db9d5  jz      loc_1800DBB80
0x1800db9db  mov     rcx, rax; this
0x1800db9de  call    ??0CBitmapDC@@QEAA@H@Z; CBitmapDC::CBitmapDC(int)
0x1800db9e3  mov     rbx, rax
0x1800db9e6  test    rax, rax
0x1800db9e9  jz      loc_1800DBB80
0x1800db9ef  mov     rdx, rsi; HBITMAP
0x1800db9f2  mov     rcx, rax; this
0x1800db9f5  call    ?SetBitmap@CBitmapDC@@QEAAHPEAUHBITMAP__@@@Z; CBitmapDC::SetBitmap(HBITMAP__ *)
0x1800db9fa  mov     ecx, [rdi+0Ch]
0x1800db9fd  mov     r8d, [rdi+4]; int
0x1800dba01  sub     ecx, r8d
0x1800dba04  mov     r9d, [rdi+8]
0x1800dba08  mov     eax, dword ptr [rsp+0A8h+arg_0.BlendOp]
0x1800dba0f  sub     r9d, [rdi]; int
0x1800dba12  mov     edx, [rdi]; int
0x1800dba14  mov     dword ptr [rsp+0A8h+var_58.BlendOp], eax; struct _BLENDFUNCTION
0x1800dba18  mov     rax, [rbx+18h]
0x1800dba1c  mov     [rsp+0A8h+var_60], ecx; int
0x1800dba20  mov     [rsp+0A8h+var_68], r9d; int
0x1800dba25  mov     [rsp+0A8h+var_80], rax; HDC
0x1800dba2a  mov     [rsp+0A8h+var_88], ecx; int
0x1800dba2e  mov     rcx, r12; HDC
0x1800dba31  call    ?CUIAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z; CUIAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x1800dba36  mov     rcx, rbx; this
0x1800dba39  call    ??_GCBitmapDC@@QEAAPEAXI@Z; CBitmapDC::`scalar deleting destructor'(uint)
0x1800dba3e  jmp     loc_1800DBB80
0x1800dba43  mov     ecx, [rsp+0A8h+arg_28]
0x1800dba4a  mov     eax, ecx
0x1800dba4c  and     eax, 20h
0x1800dba4f  test    r15, r15
0x1800dba52  jnz     short loc_1800DBA9C
0x1800dba54  mov     r9d, [rdi]
0x1800dba57  neg     eax
0x1800dba59  mov     ecx, [rdi+0Ch]
0x1800dba5c  mov     r8d, [rdi+4]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dba60  sbb     edx, edx
0x1800dba62  mov     eax, [rdi+8]
0x1800dba65  and     edx, 0A0h
0x1800dba6b  add     edx, 4
0x1800dba6e  sub     ecx, r8d
0x1800dba71  mov     [rsp+0A8h+var_60], edx; unsigned int
0x1800dba75  sub     eax, r9d
0x1800dba78  mov     [rsp+0A8h+var_68], ecx; int
0x1800dba7c  xor     edx, edx; hbrFore
0x1800dba7e  mov     [rsp+0A8h+var_70], eax; int
0x1800dba82  mov     rcx, r12; hdc
0x1800dba85  mov     [rsp+0A8h+var_78], r8d; int
0x1800dba8a  mov     dword ptr [rsp+0A8h+var_80], r9d; int
0x1800dba8f  mov     r9, rbp; __int64
0x1800dba92  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dba97  jmp     loc_1800DBB89
0x1800dba9c  xor     r13d, r13d
0x1800dba9f  test    eax, eax
0x1800dbaa1  jz      short loc_1800DBAE7
0x1800dbaa3  mov     rax, [r14]
0x1800dbaa6  xor     esi, esi
0x1800dbaa8  mov     rcx, r14
0x1800dbaab  mov     rax, [rax+10h]
0x1800dbaaf  lea     edx, [rsi+0Bh]
0x1800dbab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbab7  mov     rcx, [r14]
0x1800dbaba  lea     edx, [rsi+9]
0x1800dbabd  mov     rbx, rax
0x1800dbac0  mov     rax, [rcx+10h]
0x1800dbac4  mov     rcx, r14
0x1800dbac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbacc  mov     r9, rbx; HBRUSH
0x1800dbacf  mov     [rsp+0A8h+var_88], 1; int
0x1800dbad7  mov     r8, rax; HBRUSH
0x1800dbada  mov     rdx, r15; HBITMAP
0x1800dbadd  mov     rcx, rdi; struct tagRECT *
0x1800dbae0  call    ?CreateDisabledBitmap@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@PEAUHBRUSH__@@2H@Z; CreateDisabledBitmap(tagRECT const *,HBITMAP__ *,HBRUSH__ *,HBRUSH__ *,int)
0x1800dbae5  jmp     short loc_1800DBB33
0x1800dbae7  and     cl, 12h
0x1800dbaea  mov     esi, 10h
0x1800dbaef  cmp     cl, sil
0x1800dbaf2  jnz     short loc_1800DBB02
0x1800dbaf4  call    ?CreateDitherBrush@@YAPEAUHBRUSH__@@XZ; CreateDitherBrush(void)
0x1800dbaf9  mov     rsi, rax
0x1800dbafc  mov     r13d, 1
0x1800dbb02  mov     ecx, 14h; nIndex
0x1800dbb07  call    cs:__imp_GetSysColor
0x1800dbb0d  mov     ecx, 0Fh; nIndex
0x1800dbb12  mov     ebx, eax
0x1800dbb14  call    cs:__imp_GetSysColor
0x1800dbb1a  mov     r9, rsi; HBRUSH
0x1800dbb1d  mov     dword ptr [rsp+0A8h+var_80], ebx; unsigned int
0x1800dbb21  mov     r8, r15; HBITMAP
0x1800dbb24  mov     [rsp+0A8h+var_88], eax; unsigned __int64
0x1800dbb28  mov     rdx, rbp; HBITMAP
0x1800dbb2b  mov     rcx, rdi; struct tagRECT *
0x1800dbb2e  call    ?CreateMaskBmp@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@1PEAUHBRUSH__@@KK@Z; CreateMaskBmp(tagRECT const *,HBITMAP__ *,HBITMAP__ *,HBRUSH__ *,ulong,ulong)
0x1800dbb33  mov     rbx, rax
0x1800dbb36  test    rax, rax
0x1800dbb39  jz      short loc_1800DBB7B
0x1800dbb3b  mov     edx, [rdi+4]
0x1800dbb3e  mov     r9, rbx; __int64
0x1800dbb41  mov     ecx, [rdi+0Ch]
0x1800dbb44  mov     r8d, [rdi]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dbb47  sub     ecx, edx
0x1800dbb49  mov     eax, [rdi+8]
0x1800dbb4c  mov     [rsp+0A8h+var_60], 4; unsigned int
0x1800dbb54  sub     eax, r8d
0x1800dbb57  mov     [rsp+0A8h+var_68], ecx; int
0x1800dbb5b  mov     rcx, r12; hdc
0x1800dbb5e  mov     [rsp+0A8h+var_70], eax; int
0x1800dbb62  mov     [rsp+0A8h+var_78], edx; int
0x1800dbb66  xor     edx, edx; hbrFore
0x1800dbb68  mov     dword ptr [rsp+0A8h+var_80], r8d; int
0x1800dbb6d  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dbb72  mov     rcx, rbx; ho
0x1800dbb75  call    cs:__imp_DeleteObject
0x1800dbb7b  test    r13d, r13d
0x1800dbb7e  jz      short loc_1800DBB89
0x1800dbb80  mov     rcx, rsi; ho
0x1800dbb83  call    cs:__imp_DeleteObject
0x1800dbb89  test    byte ptr [r14+8], 1
0x1800dbb8e  jz      short loc_1800DBBA2
0x1800dbb90  mov     rcx, rbp; ho
0x1800dbb93  call    cs:__imp_DeleteObject
0x1800dbb99  mov     rcx, r15; ho
0x1800dbb9c  call    cs:__imp_DeleteObject
0x1800dbba2  add     rsp, 68h
0x1800dbba6  pop     r15
0x1800dbba8  pop     r14
0x1800dbbaa  pop     r13
0x1800dbbac  pop     r12
0x1800dbbae  pop     rdi
0x1800dbbaf  pop     rsi
0x1800dbbb0  pop     rbp
0x1800dbbb1  pop     rbx
0x1800dbbb2  retn
```
