# CUIFSchemeOfc10::DrawCtrlBitmap(HDC__ *,tagRECT const *,HBITMAP__ *,HBITMAP__ *,ulong)

- ea: `0x1800dbbc0`
- end: `0x1800dbedb`
- name: `?DrawCtrlBitmap@CUIFSchemeOfc10@@UEAAXPEAUHDC__@@PEBUtagRECT@@PEAUHBITMAP__@@2K@Z`
- size: `795`
- prototype: `void(CUIFSchemeOfc10 *__hidden this, HDC, const struct tagRECT *, HBITMAP, HBITMAP, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800d9a94`
- `0x1800d9e38`
- `0x1800da020`
- `0x1800da328`
- `0x1800da514`
- `0x1800dbbc0`
- `0x18010a010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800dbeab`
- `GDI32!DeleteObject` at `0x1800dbebb`
- `GDI32!DeleteObject` at `0x1800dbec4`
- `GDI32!DeleteObject` at `0x1800dbeab`
- `GDI32!DeleteObject` at `0x1800dbebb`
- `GDI32!DeleteObject` at `0x1800dbec4`
- `GDI32!GetStockObject` at `0x1800dbc22`
- `GDI32!GetStockObject` at `0x1800dbc22`

## pseudocode

```c
void __fastcall CUIFSchemeOfc10::DrawCtrlBitmap(
        CUIFSchemeOfc10 *this,
        HDC a2,
        const struct tagRECT *a3,
        HBITMAP a4,
        HBITMAP a5,
        unsigned int a6)
{
  __int64 v10; // rbx
  unsigned int v11; // eax
  HBRUSH v12; // rax
  HBRUSH StockObject; // rax
  HBITMAP v14; // r12
  __int64 v15; // rax
  LONG top; // esi
  int v17; // ebp
  LONG left; // ebx
  int v19; // edi
  HBRUSH v20; // rax
  int (*v21)(HDC, __int64, unsigned __int64, int, int); // r8
  unsigned int v22; // eax
  bool v23; // zf
  unsigned int v24; // edi
  HBRUSH v25; // rbx
  HBRUSH v26; // rax
  HBITMAP v27; // rbx
  unsigned int v28; // edi
  __int64 (__fastcall *v29)(CUIFSchemeOfc10 *, __int64); // rax
  HBRUSH v30; // rbx
  HBRUSH v31; // rax
  HBITMAP DisabledBitmap; // rax
  HBRUSH v33; // rax
  HBRUSH v34; // [rsp+20h] [rbp-88h]
  HBRUSH v35; // [rsp+20h] [rbp-88h]
  HBRUSH v36; // [rsp+20h] [rbp-88h]
  HBRUSH v37; // [rsp+20h] [rbp-88h]
  struct tagRECT v38; // [rsp+50h] [rbp-58h] BYREF

  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    v10 = *(_QWORD *)this;
    v11 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 216LL))(this, a6);
    v12 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(v10 + 16))(this, v11);
    a4 = CUIMirrorBitmap(a4, v12);
    StockObject = (HBRUSH)GetStockObject(4);
    v14 = CUIMirrorBitmap(a5, StockObject);
  }
  else
  {
    v14 = a5;
  }
  if ( (a6 & 0x31) == 1 )
  {
    v15 = *(_QWORD *)this;
    if ( !v14 )
    {
      top = a3->top;
      v17 = a3->bottom - top;
      left = a3->left;
      v19 = a3->right - a3->left;
      v20 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(v15 + 16))(this, 12);
      CUIDrawState(a2, v20, v21, (__int64)a4, (unsigned __int64)v34, left + 1, top + 1, v19, v17, 0x84u);
      CUIDrawState(
        a2,
        0,
        (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)(a3->bottom - a3->top),
        (__int64)a4,
        (unsigned __int64)v35,
        a3->left - 1,
        a3->top - 1,
        a3->right - a3->left,
        a3->bottom - a3->top,
        4u);
      goto LABEL_19;
    }
    v22 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(v15 + 216))(this, a6);
    v23 = (*((_BYTE *)this + 8) & 1) == 0;
    v24 = v22;
    v38 = *a3;
    if ( !v23 )
    {
      ++v38.left;
      ++v38.top;
    }
    v25 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(*(_QWORD *)this + 16LL))(this, 12);
    v26 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(this, v24);
    v27 = CreateShadowMaskBmp(&v38, a4, v14, v26, v25);
    if ( v27 )
    {
      CUIDrawState(
        a2,
        0,
        (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)(v38.bottom - v38.top),
        (__int64)v27,
        (unsigned __int64)v36,
        v38.left,
        v38.top,
        v38.right - v38.left,
        v38.bottom - v38.top,
        4u);
LABEL_18:
      DeleteObject(v27);
    }
  }
  else
  {
    if ( v14 )
    {
      v28 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 216LL))(this, a6);
      v29 = *(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(*(_QWORD *)this + 16LL);
      if ( (a6 & 0x20) != 0 )
      {
        v30 = (HBRUSH)v29(this, 11);
        v31 = (HBRUSH)(*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, _QWORD))(*(_QWORD *)this + 16LL))(this, v28);
        DisabledBitmap = CreateDisabledBitmap(a3, v14, v31, v30, 0);
      }
      else
      {
        v33 = (HBRUSH)v29(this, v28);
        DisabledBitmap = CreateMaskBmp(a3, a4, v14, v33, 0, 0);
      }
      v27 = DisabledBitmap;
      CUIDrawState(
        a2,
        0,
        (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->left,
        (__int64)DisabledBitmap,
        (unsigned __int64)v37,
        a3->left,
        a3->top,
        a3->right - a3->left,
        a3->bottom - a3->top,
        4u);
      goto LABEL_18;
    }
    CUIDrawState(
      a2,
      0,
      (int (*)(HDC, __int64, unsigned __int64, int, int))(unsigned int)a3->top,
      (__int64)a4,
      (unsigned __int64)v34,
      a3->left,
      a3->top,
      a3->right - a3->left,
      a3->bottom - a3->top,
      (a6 & 0x20) != 0 ? 164 : 4);
  }
LABEL_19:
  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    DeleteObject(a4);
    DeleteObject(v14);
  }
}

```

## disassembly

```asm
0x1800dbbc0  mov     [rsp+hdc], rdx
0x1800dbbc5  push    rbx
0x1800dbbc6  push    rbp
0x1800dbbc7  push    rsi
0x1800dbbc8  push    rdi
0x1800dbbc9  push    r12
0x1800dbbcb  push    r13
0x1800dbbcd  push    r14
0x1800dbbcf  push    r15
0x1800dbbd1  sub     rsp, 68h
0x1800dbbd5  test    byte ptr [rcx+8], 1
0x1800dbbd9  mov     r13, r9
0x1800dbbdc  mov     edi, [rsp+0A8h+arg_28]
0x1800dbbe3  mov     r15, r8
0x1800dbbe6  mov     rsi, rdx
0x1800dbbe9  mov     r14, rcx
0x1800dbbec  mov     ebp, 4
0x1800dbbf1  jz      short loc_1800DBC3D
0x1800dbbf3  mov     rbx, [rcx]
0x1800dbbf6  mov     edx, edi
0x1800dbbf8  mov     rax, [rbx+0D8h]
0x1800dbbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc04  mov     edx, eax
0x1800dbc06  mov     rcx, r14
0x1800dbc09  mov     rax, [rbx+10h]
0x1800dbc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc12  mov     rdx, rax; hbr
0x1800dbc15  mov     rcx, r13; HBITMAP
0x1800dbc18  call    ?CUIMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@PEAUHBRUSH__@@@Z; CUIMirrorBitmap(HBITMAP__ *,HBRUSH__ *)
0x1800dbc1d  mov     ecx, ebp; i
0x1800dbc1f  mov     r13, rax
0x1800dbc22  call    cs:__imp_GetStockObject
0x1800dbc28  mov     rcx, [rsp+0A8h+arg_20]; HBITMAP
0x1800dbc30  mov     rdx, rax; hbr
0x1800dbc33  call    ?CUIMirrorBitmap@@YAPEAUHBITMAP__@@PEAU1@PEAUHBRUSH__@@@Z; CUIMirrorBitmap(HBITMAP__ *,HBRUSH__ *)
0x1800dbc38  mov     r12, rax
0x1800dbc3b  jmp     short loc_1800DBC45
0x1800dbc3d  mov     r12, [rsp+0A8h+arg_20]
0x1800dbc45  mov     eax, edi
0x1800dbc47  and     al, 31h
0x1800dbc49  cmp     al, 1
0x1800dbc4b  jnz     loc_1800DBD97
0x1800dbc51  mov     rax, [r14]
0x1800dbc54  mov     rcx, r14
0x1800dbc57  test    r12, r12
0x1800dbc5a  jnz     loc_1800DBCF0
0x1800dbc60  mov     ebp, [r15+0Ch]
0x1800dbc64  lea     edx, [r12+0Ch]
0x1800dbc69  mov     edi, [r15+8]
0x1800dbc6d  mov     esi, [r15+4]
0x1800dbc71  sub     ebp, esi
0x1800dbc73  mov     ebx, [r15]
0x1800dbc76  sub     edi, ebx
0x1800dbc78  mov     rax, [rax+10h]
0x1800dbc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc81  mov     [rsp+0A8h+var_60], 84h; unsigned int
0x1800dbc89  lea     ecx, [rsi+1]
0x1800dbc8c  mov     [rsp+0A8h+var_68], ebp; int
0x1800dbc90  lea     edx, [rbx+1]
0x1800dbc93  mov     [rsp+0A8h+var_70], edi; int
0x1800dbc97  mov     r9, r13; __int64
0x1800dbc9a  mov     [rsp+0A8h+var_78], ecx; int
0x1800dbc9e  mov     rcx, [rsp+0A8h+hdc]; hdc
0x1800dbca6  mov     [rsp+0A8h+var_80], edx; int
0x1800dbcaa  mov     rdx, rax; hbrFore
0x1800dbcad  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dbcb2  mov     ecx, [r15]
0x1800dbcb5  mov     eax, [r15+4]
0x1800dbcb9  mov     r8d, [r15+0Ch]
0x1800dbcbd  mov     edx, [r15+8]
0x1800dbcc1  sub     r8d, eax
0x1800dbcc4  sub     edx, ecx
0x1800dbcc6  mov     [rsp+0A8h+var_60], 4
0x1800dbcce  mov     [rsp+0A8h+var_68], r8d
0x1800dbcd3  dec     eax
0x1800dbcd5  dec     ecx
0x1800dbcd7  mov     [rsp+0A8h+var_70], edx
0x1800dbcdb  mov     [rsp+0A8h+var_78], eax
0x1800dbcdf  mov     [rsp+0A8h+var_80], ecx
0x1800dbce3  mov     rcx, [rsp+0A8h+hdc]
0x1800dbceb  jmp     loc_1800DBDDB
0x1800dbcf0  mov     rax, [rax+0D8h]
0x1800dbcf7  mov     edx, edi
0x1800dbcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbcfe  test    byte ptr [r14+8], 1
0x1800dbd03  mov     edi, eax
0x1800dbd05  movups  xmm0, xmmword ptr [r15]
0x1800dbd09  movdqu  xmmword ptr [rsp+0A8h+var_58.left], xmm0
0x1800dbd0f  jz      short loc_1800DBD19
0x1800dbd11  inc     [rsp+0A8h+var_58.left]
0x1800dbd15  inc     [rsp+0A8h+var_58.top]
0x1800dbd19  mov     rcx, [r14]
0x1800dbd1c  mov     edx, 0Ch
0x1800dbd21  mov     rax, [rcx+10h]
0x1800dbd25  mov     rcx, r14
0x1800dbd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbd2d  mov     rcx, [r14]
0x1800dbd30  mov     rbx, rax
0x1800dbd33  mov     edx, edi
0x1800dbd35  mov     rax, [rcx+10h]
0x1800dbd39  mov     rcx, r14
0x1800dbd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbd41  mov     r9, rax; HBRUSH
0x1800dbd44  mov     [rsp+0A8h+var_88], rbx; HBRUSH
0x1800dbd49  mov     r8, r12; HBITMAP
0x1800dbd4c  lea     rcx, [rsp+0A8h+var_58]; struct tagRECT *
0x1800dbd51  mov     rdx, r13; HBITMAP
0x1800dbd54  call    ?CreateShadowMaskBmp@@YAPEAUHBITMAP__@@PEAUtagRECT@@PEAU1@1PEAUHBRUSH__@@2@Z; CreateShadowMaskBmp(tagRECT *,HBITMAP__ *,HBITMAP__ *,HBRUSH__ *,HBRUSH__ *)
0x1800dbd59  mov     rbx, rax
0x1800dbd5c  test    rax, rax
0x1800dbd5f  jz      loc_1800DBEB1
0x1800dbd65  mov     r9d, [rsp+0A8h+var_58.top]
0x1800dbd6a  mov     edx, [rsp+0A8h+var_58.left]
0x1800dbd6e  mov     r8d, [rsp+0A8h+var_58.bottom]
0x1800dbd73  mov     ecx, [rsp+0A8h+var_58.right]
0x1800dbd77  sub     r8d, r9d
0x1800dbd7a  mov     [rsp+0A8h+var_60], ebp
0x1800dbd7e  sub     ecx, edx
0x1800dbd80  mov     [rsp+0A8h+var_68], r8d
0x1800dbd85  mov     [rsp+0A8h+var_70], ecx
0x1800dbd89  mov     [rsp+0A8h+var_78], r9d
0x1800dbd8e  mov     [rsp+0A8h+var_80], edx
0x1800dbd92  jmp     loc_1800DBE9B
0x1800dbd97  mov     ebx, edi
0x1800dbd99  and     ebx, 20h
0x1800dbd9c  test    r12, r12
0x1800dbd9f  jnz     short loc_1800DBDEA
0x1800dbda1  mov     ecx, [r15+0Ch]
0x1800dbda5  neg     ebx
0x1800dbda7  mov     r8d, [r15+4]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dbdab  mov     r9d, [r15]
0x1800dbdae  sbb     edx, edx
0x1800dbdb0  mov     eax, [r15+8]
0x1800dbdb4  sub     ecx, r8d
0x1800dbdb7  and     edx, 0A0h
0x1800dbdbd  add     edx, ebp
0x1800dbdbf  mov     [rsp+0A8h+var_60], edx; unsigned int
0x1800dbdc3  sub     eax, r9d
0x1800dbdc6  mov     [rsp+0A8h+var_68], ecx; int
0x1800dbdca  mov     rcx, rsi; hdc
0x1800dbdcd  mov     [rsp+0A8h+var_70], eax; int
0x1800dbdd1  mov     [rsp+0A8h+var_78], r8d; int
0x1800dbdd6  mov     [rsp+0A8h+var_80], r9d; int
0x1800dbddb  xor     edx, edx; hbrFore
0x1800dbddd  mov     r9, r13; __int64
0x1800dbde0  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dbde5  jmp     loc_1800DBEB1
0x1800dbdea  mov     rax, [r14]
0x1800dbded  mov     edx, edi
0x1800dbdef  mov     rcx, r14
0x1800dbdf2  mov     rax, [rax+0D8h]
0x1800dbdf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbdfe  mov     rcx, [r14]
0x1800dbe01  mov     edi, eax
0x1800dbe03  mov     rax, [rcx+10h]
0x1800dbe07  mov     rcx, r14
0x1800dbe0a  test    ebx, ebx
0x1800dbe0c  jz      short loc_1800DBE47
0x1800dbe0e  mov     edx, 0Bh
0x1800dbe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbe18  mov     rcx, [r14]
0x1800dbe1b  mov     rbx, rax
0x1800dbe1e  mov     edx, edi
0x1800dbe20  mov     rax, [rcx+10h]
0x1800dbe24  mov     rcx, r14
0x1800dbe27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbe2c  mov     r9, rbx; HBRUSH
0x1800dbe2f  mov     dword ptr [rsp+0A8h+var_88], 0; int
0x1800dbe37  mov     r8, rax; HBRUSH
0x1800dbe3a  mov     rdx, r12; HBITMAP
0x1800dbe3d  mov     rcx, r15; struct tagRECT *
0x1800dbe40  call    ?CreateDisabledBitmap@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@PEAUHBRUSH__@@2H@Z; CreateDisabledBitmap(tagRECT const *,HBITMAP__ *,HBRUSH__ *,HBRUSH__ *,int)
0x1800dbe45  jmp     short loc_1800DBE6F
0x1800dbe47  mov     edx, edi
0x1800dbe49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbe4e  mov     r9, rax; HBRUSH
0x1800dbe51  mov     [rsp+0A8h+var_80], 0; unsigned int
0x1800dbe59  mov     r8, r12; HBITMAP
0x1800dbe5c  mov     dword ptr [rsp+0A8h+var_88], 0; unsigned __int64
0x1800dbe64  mov     rdx, r13; HBITMAP
0x1800dbe67  mov     rcx, r15; struct tagRECT *
0x1800dbe6a  call    ?CreateMaskBmp@@YAPEAUHBITMAP__@@PEBUtagRECT@@PEAU1@1PEAUHBRUSH__@@KK@Z; CreateMaskBmp(tagRECT const *,HBITMAP__ *,HBITMAP__ *,HBRUSH__ *,ulong,ulong)
0x1800dbe6f  mov     edx, [r15+4]
0x1800dbe73  mov     rbx, rax
0x1800dbe76  mov     r8d, [r15]; int (*)(HDC, __int64, unsigned __int64, int, int)
0x1800dbe79  mov     ecx, [r15+0Ch]
0x1800dbe7d  mov     eax, [r15+8]
0x1800dbe81  sub     ecx, edx
0x1800dbe83  mov     [rsp+0A8h+var_60], ebp; unsigned int
0x1800dbe87  sub     eax, r8d
0x1800dbe8a  mov     [rsp+0A8h+var_68], ecx; int
0x1800dbe8e  mov     [rsp+0A8h+var_70], eax; int
0x1800dbe92  mov     [rsp+0A8h+var_78], edx; int
0x1800dbe96  mov     [rsp+0A8h+var_80], r8d; int
0x1800dbe9b  mov     r9, rbx; __int64
0x1800dbe9e  xor     edx, edx; hbrFore
0x1800dbea0  mov     rcx, rsi; hdc
0x1800dbea3  call    ?CUIDrawState@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_J_KHH@Z23HHHHI@Z; CUIDrawState(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,unsigned __int64,int,int),__int64,unsigned __int64,int,int,int,int,uint)
0x1800dbea8  mov     rcx, rbx; ho
0x1800dbeab  call    cs:__imp_DeleteObject
0x1800dbeb1  test    byte ptr [r14+8], 1
0x1800dbeb6  jz      short loc_1800DBECA
0x1800dbeb8  mov     rcx, r13; ho
0x1800dbebb  call    cs:__imp_DeleteObject
0x1800dbec1  mov     rcx, r12; ho
0x1800dbec4  call    cs:__imp_DeleteObject
0x1800dbeca  add     rsp, 68h
0x1800dbece  pop     r15
0x1800dbed0  pop     r14
0x1800dbed2  pop     r13
0x1800dbed4  pop     r12
0x1800dbed6  pop     rdi
0x1800dbed7  pop     rsi
0x1800dbed8  pop     rbp
0x1800dbed9  pop     rbx
0x1800dbeda  retn
```
