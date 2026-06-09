# CObjectMgr::InsertObject(CTxtRange *,_reobject *,IUndoBuilder *,int)

- ea: `0x18011036c`
- end: `0x18011086f`
- name: `?InsertObject@CObjectMgr@@QEAAJPEAVCTxtRange@@PEAU_reobject@@PEAVIUndoBuilder@@H@Z`
- size: `1283`
- prototype: `int(CObjectMgr *__hidden this, struct CTxtRange *, struct _reobject *, struct IUndoBuilder *, int)`
- caller_count: `6`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cf0f4`
- `0x1800cf408`
- `0x180123ddc`
- `0x1801678f0`
- `0x1801775a0`
- `0x180183a1c`

## callees

- `0x18000f430`
- `0x1800117e4`
- `0x180013b84`
- `0x180014128`
- `0x180020474`
- `0x180032260`
- `0x18003ec20`
- `0x18003ed40`
- `0x18004bed8`
- `0x18008b170`
- `0x1800b2660`
- `0x1800f0cb8`
- `0x18011036c`
- `0x18012b3c8`
- `0x18012bd00`
- `0x1801364bc`
- `0x18013ce80`
- `0x180148de4`
- `0x1801643c8`
- `0x18016441c`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801105c8`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801105c8`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801106e8`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180110712`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180110750`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801107a2`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801106e8`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180110712`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180110750`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801107a2`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18011073e`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18011073e`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x1801106ca`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x1801106ca`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x1801106fd`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x1801106fd`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18011075f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18011078c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801107b1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18011075f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18011078c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801107b1`

## pseudocode

```c
__int64 __fastcall CObjectMgr::InsertObject(
        CObjectMgr *this,
        struct CTxtRange *a2,
        struct _reobject *a3,
        struct IUndoBuilder *a4,
        int a5)
{
  CTxtPtr *v5; // r12
  __int64 v8; // rdx
  __int64 v10; // rax
  CTxtEdit *v11; // r13
  LPOLECLIENTSITE polesite; // r14
  __int64 v13; // rdx
  CTxtStory *v14; // rbp
  __int64 result; // rax
  int v16; // ecx
  int v17; // edx
  int v18; // eax
  struct IUndoBuilder *v19; // rax
  unsigned int v20; // edi
  int v21; // edx
  __int64 v22; // rcx
  const struct CCharFormat *CF; // rax
  CObjectMgr *v24; // rcx
  unsigned int v25; // ebx
  DWORD dwFlags; // eax
  struct CDocInfo *DocInfo; // rbp
  HDC ScreenDC; // rax
  HDC CompatibleDC; // r15
  __int64 v30; // r11
  int v31; // r11^4
  __int64 v32; // r11
  HDC v33; // rax
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v35; // r12
  HGDIOBJ v36; // r13
  HBRUSH SolidBrush; // rdi
  HGDIOBJ v38; // rbx
  void *v39; // rcx
  int v40; // [rsp+50h] [rbp-78h]
  LONG h; // [rsp+50h] [rbp-78h]
  LONG wa; // [rsp+58h] [rbp-70h]
  struct tagRECT v44; // [rsp+60h] [rbp-68h] BYREF

  v5 = (struct CTxtRange *)((char *)a2 + 24);
  v8 = *((_QWORD *)a2 + 3);
  v10 = v8 - 8;
  if ( v8 )
    v11 = *(CTxtEdit **)(v10 + 48);
  else
    v11 = 0;
  polesite = a3->polesite;
  v13 = -v8;
  v14 = (CTxtStory *)(v10 & -(__int64)(v13 != 0));
  if ( !polesite
    || !COleObject::EnsureNmp((COleObject *)a3->polesite, (struct CTxtStory *)(v10 & -(__int64)(v13 != 0)), (int)a3) )
  {
    return 2147500037LL;
  }
  result = CTxtStory::InitObjects(v14);
  if ( !(_DWORD)result )
  {
    polesite[9].lpVtbl = (struct IOleClientSiteVtbl *)v14;
    v16 = *((_DWORD *)a2 + 26);
    v17 = -v16;
    if ( v16 > 0 )
      v17 = *((_DWORD *)a2 + 26);
    v18 = *((_DWORD *)a2 + 10) - v16;
    if ( v16 < 0 )
      v18 = *((_DWORD *)a2 + 10);
    LODWORD(polesite[10].lpVtbl) = ~v18;
    v19 = 0;
    if ( (a3->dwFlags & 0x400) == 0 )
      v19 = a4;
    v20 = 0;
    *(_QWORD *)&v44.left = v19;
    if ( a5 && v17 == 1 )
    {
      v21 = *((_DWORD *)a2 + 26);
      if ( v21 > 0 )
      {
        CRchTxtPtr::Move((struct CTxtRange *)((char *)a2 + 8), -v21);
        *((_DWORD *)a2 + 26) = -*((_DWORD *)a2 + 26);
      }
      if ( CTxtPtr::GetChar(v5) == 32 && (*(_DWORD *)CTxtEdit::GetCharFormat(v11, *((_WORD *)a2 + 56)) & 0x100) == 0 )
        v20 = 64;
    }
    CTxtRange::CheckTableSelection(a2, v17, 1, 0, v20, 0);
    v22 = *((_QWORD *)this + 3);
    if ( !v22
      || (result = (*(__int64 (__fastcall **)(__int64, CLSID *, LPSTORAGE, __int64))(*(_QWORD *)v22 + 48LL))(
                     v22,
                     &a3->clsid,
                     a3->pstg,
                     0xFFFFFFFFLL),
          !(_DWORD)result) )
    {
      if ( !a5 )
        goto LABEL_27;
      v40 = *(_DWORD *)CRchTxtPtr::GetCFBackward((struct CTxtRange *)((char *)a2 + 8));
      CF = CRchTxtPtr::GetCF((struct CTxtRange *)((char *)a2 + 8));
      if ( !*((_DWORD *)a2 + 10) || (v40 & *(_DWORD *)CF & 0x800000) != 0 && (*(_DWORD *)CF & 0x100) != 0 )
        v20 |= 0x18u;
      if ( (*(unsigned int (__fastcall **)(struct CTxtRange *, __int64, const unsigned __int16 *, _QWORD, _DWORD, _QWORD, unsigned int, _DWORD))(*(_QWORD *)a2 + 888LL))(
             a2,
             1,
             &szEmbedding,
             *(_QWORD *)&v44.left,
             0,
             0,
             v20,
             0) == 1 )
      {
LABEL_27:
        if ( CTxtPtr::GetPrevChar(v5) == 0xFFFC )
        {
          result = COleObject::InitFromREOBJECT(
                     (COleObject *)polesite,
                     (struct CTxtStory *)((*((_QWORD *)a2 + 3) - 8LL) & -(__int64)(*((_QWORD *)a2 + 3) != 0)),
                     *((_DWORD *)a2 + 10) - 1,
                     a3);
          if ( (_DWORD)result )
            return result;
          v25 = CObjectMgr::RestoreObject(v24, (struct COleObject *)polesite);
          dwFlags = a3->dwFlags;
          if ( (dwFlags & 0x400) == 0 )
          {
            if ( (dwFlags & 0x200) != 0 )
              CTxtEdit::OnSetTypographyOptions(v11, 0x10u, 16);
            if ( !v25 && (WORD1(polesite[19].lpVtbl) & 0x1000) != 0 )
              CTxtStory::ModifyBlobCount(v14, 1);
            return v25;
          }
          DocInfo = CTxtEdit::GetDocInfo(v11);
          if ( DocInfo )
          {
            ScreenDC = CW32System::GetScreenDC();
            CompatibleDC = CreateCompatibleDC(ScreenDC);
            if ( CompatibleDC )
            {
              if ( *((_BYTE *)DocInfo + 139) == 0xFF )
              {
                v30 = *(__int64 *)((char *)&polesite[10].lpVtbl + 4);
                *((_BYTE *)DocInfo + 139) = 3;
                *((_DWORD *)DocInfo + 42) = 6553700;
                *((_WORD *)DocInfo + 86) = CW32System::MulDivFunc(v30, 72, 127);
                *((_WORD *)DocInfo + 87) = CW32System::MulDivFunc(v31, 72, 127);
              }
              wa = CW32System::MulDivFunc(
                     *((__int16 *)DocInfo + 84) * *((__int16 *)DocInfo + 86) / 100,
                     *(_DWORD *)(*((_QWORD *)v11 + 17) + 52LL),
                     1440);
              h = CW32System::MulDivFunc(
                    *((__int16 *)DocInfo + 87) * *((__int16 *)DocInfo + 85) / 100,
                    *(_DWORD *)(v32 + 56),
                    1440);
              v44.bottom = h;
              *(_QWORD *)&v44.left = 0;
              v44.right = wa;
              v33 = CW32System::GetScreenDC();
              CompatibleBitmap = CreateCompatibleBitmap(v33, wa, h);
              v35 = CompatibleBitmap;
              if ( CompatibleBitmap )
              {
                v36 = SelectObject(CompatibleDC, CompatibleBitmap);
                SolidBrush = CreateSolidBrush(*((_DWORD *)DocInfo + 32));
                v38 = SelectObject(CompatibleDC, SolidBrush);
                PatBlt(CompatibleDC, 0, 0, wa, h, 0xF00021u);
                SelectObject(CompatibleDC, v38);
                DeleteObject(SolidBrush);
                CW32System::OleDraw(
                  (struct IUnknown *)polesite[7].lpVtbl,
                  HIDWORD(polesite[18].lpVtbl),
                  CompatibleDC,
                  &v44);
                v39 = (void *)*((_QWORD *)DocInfo + 12);
                if ( v39 )
                  DeleteObject(v39);
                *((_QWORD *)DocInfo + 12) = v35;
                SelectObject(CompatibleDC, v36);
              }
              DeleteObject(CompatibleDC);
            }
            CTxtRange::Set(a2, *((_DWORD *)a2 + 10), 1);
            (*(void (__fastcall **)(struct CTxtRange *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, int, _DWORD))(*(_QWORD *)a2 + 888LL))(
              a2,
              0,
              0,
              0,
              0,
              0,
              32,
              0);
            return 1;
          }
        }
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18011036c  push    rbx
0x18011036e  push    rbp
0x18011036f  push    rsi
0x180110370  push    rdi
0x180110371  push    r12
0x180110373  push    r13
0x180110375  push    r14
0x180110377  push    r15
0x180110379  sub     rsp, 88h
0x180110380  mov     rax, cs:__security_cookie
0x180110387  xor     rax, rsp
0x18011038a  mov     [rsp+0C8h+var_58], rax
0x18011038f  lea     r12, [rdx+18h]
0x180110393  mov     qword ptr [rsp+0C8h+w], rcx
0x180110398  mov     rsi, rdx
0x18011039b  mov     rbx, r9
0x18011039e  mov     rdx, [r12]
0x1801103a2  mov     r15, r8
0x1801103a5  lea     rax, [rdx-8]
0x1801103a9  test    rdx, rdx
0x1801103ac  jz      short loc_1801103B4
0x1801103ae  mov     r13, [rax+30h]
0x1801103b2  jmp     short loc_1801103B7
0x1801103b4  xor     r13d, r13d
0x1801103b7  mov     r14, [r8+28h]
0x1801103bb  neg     rdx
0x1801103be  sbb     rbp, rbp
0x1801103c1  and     rbp, rax
0x1801103c4  test    r14, r14
0x1801103c7  jz      loc_180110848
0x1801103cd  mov     rdx, rbp; struct CTxtStory *
0x1801103d0  mov     rcx, r14; this
0x1801103d3  call    ?EnsureNmp@COleObject@@QEAAHPEAVCTxtStory@@H@Z; COleObject::EnsureNmp(CTxtStory *,int)
0x1801103d8  test    eax, eax
0x1801103da  jz      loc_180110848
0x1801103e0  mov     rcx, rbp; this
0x1801103e3  call    ?InitObjects@CTxtStory@@QEAAJXZ; CTxtStory::InitObjects(void)
0x1801103e8  test    eax, eax
0x1801103ea  jnz     loc_18011084D
0x1801103f0  mov     [r14+48h], rbp
0x1801103f4  mov     ecx, [rsi+68h]
0x1801103f7  mov     edx, ecx
0x1801103f9  mov     eax, [rsi+28h]
0x1801103fc  neg     edx
0x1801103fe  cmovs   edx, ecx
0x180110401  sub     eax, ecx
0x180110403  test    ecx, ecx
0x180110405  cmovs   eax, [rsi+28h]
0x180110409  not     eax
0x18011040b  mov     [r14+50h], eax
0x18011040f  mov     eax, 0
0x180110414  test    dword ptr [r15+3Ch], 400h
0x18011041c  cmovz   rax, rbx
0x180110420  mov     ebx, [rsp+0C8h+arg_20]
0x180110427  xor     edi, edi
0x180110429  mov     qword ptr [rsp+0C8h+var_68.left], rax
0x18011042e  test    ebx, ebx
0x180110430  jz      short loc_18011047D
0x180110432  cmp     edx, 1
0x180110435  jnz     short loc_18011047D
0x180110437  mov     edx, [rsi+68h]
0x18011043a  test    edx, edx
0x18011043c  jle     short loc_180110451
0x18011043e  neg     edx; int
0x180110440  lea     rcx, [rsi+8]; this
0x180110444  call    ?Move@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Move(long)
0x180110449  mov     eax, [rsi+68h]
0x18011044c  neg     eax
0x18011044e  mov     [rsi+68h], eax
0x180110451  mov     rcx, r12; this
0x180110454  call    ?GetChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetChar(void)
0x180110459  mov     ecx, 20h ; ' '
0x18011045e  cmp     ax, cx
0x180110461  jnz     short loc_18011047D
0x180110463  movzx   edx, word ptr [rsi+70h]; __int16
0x180110467  mov     rcx, r13; this
0x18011046a  call    ?GetCharFormat@CTxtEdit@@QEBAPEBVCCharFormat@@F@Z; CTxtEdit::GetCharFormat(short)
0x18011046f  test    dword ptr [rax], 100h
0x180110475  mov     eax, 40h ; '@'
0x18011047a  cmovz   edi, eax
0x18011047d  xor     r9d, r9d; int *
0x180110480  mov     qword ptr [rsp+0C8h+rop], 0; int *
0x180110489  mov     rcx, rsi; this
0x18011048c  mov     [rsp+0C8h+h], edi; unsigned int
0x180110490  lea     r8d, [r9+1]; int
0x180110494  call    ?CheckTableSelection@CTxtRange@@QEAAHHHPEAHK0@Z; CTxtRange::CheckTableSelection(int,int,int *,ulong,int *)
0x180110499  mov     rax, qword ptr [rsp+0C8h+w]
0x18011049e  mov     rcx, [rax+18h]
0x1801104a2  test    rcx, rcx
0x1801104a5  jz      short loc_1801104C7
0x1801104a7  mov     rax, [rcx]
0x1801104aa  lea     rdx, [r15+8]
0x1801104ae  mov     r8, [r15+20h]
0x1801104b2  or      r9d, 0FFFFFFFFh
0x1801104b6  mov     rax, [rax+30h]
0x1801104ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801104bf  test    eax, eax
0x1801104c1  jnz     loc_18011084D
0x1801104c7  test    ebx, ebx
0x1801104c9  jz      loc_180110553
0x1801104cf  lea     rcx, [rsi+8]; this
0x1801104d3  call    ?GetCFBackward@CRchTxtPtr@@QEAAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCFBackward(void)
0x1801104d8  lea     rcx, [rsi+8]; this
0x1801104dc  mov     eax, [rax]
0x1801104de  mov     [rsp+0C8h+var_78], eax
0x1801104e2  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x1801104e7  cmp     dword ptr [rsi+28h], 0
0x1801104eb  jz      short loc_180110507
0x1801104ed  mov     edx, [rax]
0x1801104ef  mov     eax, edx
0x1801104f1  and     eax, [rsp+0C8h+var_78]
0x1801104f5  bt      eax, 17h
0x1801104f9  setb    cl
0x1801104fc  bt      edx, 8
0x180110500  setb    al
0x180110503  test    al, cl
0x180110505  jz      short loc_18011050A
0x180110507  or      edi, 18h
0x18011050a  mov     rax, [rsi]
0x18011050d  lea     r8, ?szEmbedding@@3QBGB; ushort const near * const szEmbedding
0x180110514  mov     r9, qword ptr [rsp+0C8h+var_68.left]
0x180110519  mov     edx, 1
0x18011051e  mov     [rsp+0C8h+var_90], 0
0x180110526  mov     rcx, rsi
0x180110529  mov     [rsp+0C8h+var_98], edi
0x18011052d  mov     rax, [rax+378h]
0x180110534  mov     qword ptr [rsp+0C8h+rop], 0
0x18011053d  mov     [rsp+0C8h+h], 0
0x180110545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011054a  cmp     eax, 1
0x18011054d  jnz     loc_180110848
0x180110553  mov     rcx, r12; this
0x180110556  call    ?GetPrevChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetPrevChar(void)
0x18011055b  mov     ecx, 0FFFCh
0x180110560  cmp     ax, cx
0x180110563  jnz     loc_180110848
0x180110569  mov     rcx, [rsi+18h]
0x18011056d  mov     r9, r15; struct _reobject *
0x180110570  mov     r8d, [rsi+28h]
0x180110574  dec     r8d; int
0x180110577  lea     rax, [rcx-8]
0x18011057b  neg     rcx
0x18011057e  mov     rcx, r14; this
0x180110581  sbb     rdx, rdx
0x180110584  and     rdx, rax; struct CTxtStory *
0x180110587  call    ?InitFromREOBJECT@COleObject@@QEAAJPEAVCTxtStory@@JPEAU_reobject@@@Z; COleObject::InitFromREOBJECT(CTxtStory *,long,_reobject *)
0x18011058c  test    eax, eax
0x18011058e  jnz     loc_18011084D
0x180110594  mov     rdx, r14; struct COleObject *
0x180110597  call    ?RestoreObject@CObjectMgr@@QEAAJPEAVCOleObject@@@Z; CObjectMgr::RestoreObject(COleObject *)
0x18011059c  mov     ebx, eax
0x18011059e  mov     eax, [r15+3Ch]
0x1801105a2  bt      eax, 0Ah
0x1801105a6  jnb     loc_180110810
0x1801105ac  mov     rcx, r13; this
0x1801105af  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x1801105b4  mov     rbp, rax
0x1801105b7  test    rax, rax
0x1801105ba  jz      loc_180110848
0x1801105c0  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x1801105c5  mov     rcx, rax; hdc
0x1801105c8  call    cs:__imp_CreateCompatibleDC
0x1801105cf  nop     dword ptr [rax+rax+00h]
0x1801105d4  mov     r15, rax
0x1801105d7  test    rax, rax
0x1801105da  jz      loc_1801107BD
0x1801105e0  cmp     byte ptr [rbp+8Bh], 0FFh
0x1801105e7  jnz     short loc_180110632
0x1801105e9  mov     r11, [r14+54h]
0x1801105ed  mov     edi, 7Fh
0x1801105f2  mov     r8d, edi; int
0x1801105f5  mov     byte ptr [rbp+8Bh], 3
0x1801105fc  mov     ecx, r11d; int
0x1801105ff  mov     dword ptr [rbp+0A8h], 640064h
0x180110609  lea     ebx, [rdi-37h]
0x18011060c  mov     edx, ebx; int
0x18011060e  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180110613  shr     r11, 20h
0x180110617  mov     r8d, edi; int
0x18011061a  mov     ecx, r11d; int
0x18011061d  mov     [rbp+0ACh], ax
0x180110624  mov     edx, ebx; int
0x180110626  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18011062b  mov     [rbp+0AEh], ax
0x180110632  movsx   eax, word ptr [rbp+0A8h]
0x180110639  mov     r12d, 51EB851Fh
0x18011063f  movsx   ecx, word ptr [rbp+0ACh]
0x180110646  mov     edi, 5A0h
0x18011064b  mov     r11, [r13+88h]
0x180110652  mov     r8d, edi; int
0x180110655  imul    ecx, eax
0x180110658  mov     eax, r12d
0x18011065b  imul    ecx
0x18011065d  mov     ecx, edx
0x18011065f  sar     ecx, 5
0x180110662  mov     edx, ecx
0x180110664  shr     edx, 1Fh
0x180110667  add     ecx, edx; int
0x180110669  mov     edx, [r11+34h]; int
0x18011066d  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180110672  movsx   ecx, word ptr [rbp+0AEh]
0x180110679  mov     ebx, eax
0x18011067b  movsx   edx, word ptr [rbp+0AAh]
0x180110682  mov     r8d, edi; int
0x180110685  imul    edx, ecx
0x180110688  mov     [rsp+0C8h+w], eax
0x18011068c  mov     eax, r12d
0x18011068f  imul    edx
0x180110691  mov     ecx, edx
0x180110693  sar     ecx, 5
0x180110696  mov     edx, ecx
0x180110698  shr     edx, 1Fh
0x18011069b  add     ecx, edx; int
0x18011069d  mov     edx, [r11+38h]; int
0x1801106a1  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x1801106a6  mov     edi, eax
0x1801106a8  mov     [rsp+0C8h+var_78], eax
0x1801106ac  mov     [rsp+0C8h+var_68.bottom], eax
0x1801106b0  mov     qword ptr [rsp+0C8h+var_68.left], 0
0x1801106b9  mov     [rsp+0C8h+var_68.right], ebx
0x1801106bd  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x1801106c2  mov     rcx, rax; hdc
0x1801106c5  mov     r8d, edi; cy
0x1801106c8  mov     edx, ebx; cx
0x1801106ca  call    cs:__imp_CreateCompatibleBitmap
0x1801106d1  nop     dword ptr [rax+rax+00h]
0x1801106d6  mov     r12, rax
0x1801106d9  test    rax, rax
0x1801106dc  jz      loc_1801107AE
0x1801106e2  mov     rdx, rax; h
0x1801106e5  mov     rcx, r15; hdc
0x1801106e8  call    cs:__imp_SelectObject
0x1801106ef  nop     dword ptr [rax+rax+00h]
0x1801106f4  mov     ecx, [rbp+80h]; color
0x1801106fa  mov     r13, rax
0x1801106fd  call    cs:__imp_CreateSolidBrush
0x180110704  nop     dword ptr [rax+rax+00h]
0x180110709  mov     rdx, rax; h
0x18011070c  mov     rcx, r15; hdc
0x18011070f  mov     rdi, rax
0x180110712  call    cs:__imp_SelectObject
0x180110719  nop     dword ptr [rax+rax+00h]
0x18011071e  mov     r9d, [rsp+0C8h+w]; w
0x180110723  xor     r8d, r8d; y
0x180110726  mov     rbx, rax
0x180110729  mov     [rsp+0C8h+rop], 0F00021h; rop
0x180110731  mov     eax, [rsp+0C8h+var_78]
0x180110735  xor     edx, edx; x
0x180110737  mov     rcx, r15; hdc
0x18011073a  mov     [rsp+0C8h+h], eax; h
0x18011073e  call    cs:__imp_PatBlt
0x180110745  nop     dword ptr [rax+rax+00h]
0x18011074a  mov     rdx, rbx; h
0x18011074d  mov     rcx, r15; hdc
0x180110750  call    cs:__imp_SelectObject
0x180110757  nop     dword ptr [rax+rax+00h]
0x18011075c  mov     rcx, rdi; ho
0x18011075f  call    cs:__imp_DeleteObject
0x180110766  nop     dword ptr [rax+rax+00h]
0x18011076b  mov     edx, [r14+94h]; unsigned int
0x180110772  lea     r9, [rsp+0C8h+var_68]; struct tagRECT *
0x180110777  mov     rcx, [r14+38h]; struct IUnknown *
0x18011077b  mov     r8, r15; HDC
0x18011077e  call    ?OleDraw@CW32System@@SAJPEAUIUnknown@@KPEAUHDC__@@PEBUtagRECT@@@Z; CW32System::OleDraw(IUnknown *,ulong,HDC__ *,tagRECT const *)
0x180110783  mov     rcx, [rbp+60h]; ho
0x180110787  test    rcx, rcx
0x18011078a  jz      short loc_180110798
0x18011078c  call    cs:__imp_DeleteObject
0x180110793  nop     dword ptr [rax+rax+00h]
0x180110798  mov     rdx, r13; h
0x18011079b  mov     [rbp+60h], r12
0x18011079f  mov     rcx, r15; hdc
0x1801107a2  call    cs:__imp_SelectObject
0x1801107a9  nop     dword ptr [rax+rax+00h]
0x1801107ae  mov     rcx, r15; ho
0x1801107b1  call    cs:__imp_DeleteObject
0x1801107b8  nop     dword ptr [rax+rax+00h]
0x1801107bd  mov     edx, [rsi+28h]; int
0x1801107c0  mov     r8d, 1; int
0x1801107c6  mov     rcx, rsi; this
0x1801107c9  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x1801107ce  mov     rax, [rsi]
0x1801107d1  xor     r9d, r9d
0x1801107d4  mov     [rsp+0C8h+var_90], 0
0x1801107dc  xor     r8d, r8d
0x1801107df  mov     [rsp+0C8h+var_98], 20h ; ' '
0x1801107e7  xor     edx, edx
0x1801107e9  mov     qword ptr [rsp+0C8h+rop], 0
0x1801107f2  mov     rcx, rsi
0x1801107f5  mov     rax, [rax+378h]
0x1801107fc  mov     [rsp+0C8h+h], 0
0x180110804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110809  mov     ebx, 1
0x18011080e  jmp     short loc_180110844
0x180110810  bt      eax, 9
0x180110814  jnb     short loc_180110826
0x180110816  mov     edx, 10h; unsigned __int64
0x18011081b  mov     rcx, r13; this
0x18011081e  mov     r8d, edx; __int64
0x180110821  call    ?OnSetTypographyOptions@CTxtEdit@@QEAAJ_K_J@Z; CTxtEdit::OnSetTypographyOptions(unsigned __int64,__int64)
  ... truncated ...
```
