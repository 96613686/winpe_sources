# CTxtEdit::TxDraw(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,tagRECT *,int (*)(ulong),ulong,long)

- ea: `0x180084910`
- end: `0x180084d72`
- name: `?TxDraw@CTxtEdit@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3PEAUtagRECT@@P6AHK@ZKJ@Z`
- size: `1122`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, int@<r8d>, void *@<r9>, struct tagDVTARGETDEVICE *, HDC hdc, HDC, const struct _RECTL *, const struct _RECTL *, struct tagRECT *, int (*)(unsigned int), unsigned int, int)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x18000bac0`
- `0x18001e720`
- `0x18001e8f8`
- `0x18002a6f0`
- `0x18002a790`
- `0x18003e42c`
- `0x1800412c0`
- `0x180042f94`
- `0x18004c12c`
- `0x1800556b0`
- `0x1800566f0`
- `0x18005d214`
- `0x18005e2e4`
- `0x18008455c`
- `0x1800845c0`
- `0x180084910`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `GDI32!LPtoDP` at `0x180084aa9`
- `GDI32!LPtoDP` at `0x180084add`
- `GDI32!LPtoDP` at `0x180084b11`
- `GDI32!LPtoDP` at `0x180084aa9`
- `GDI32!LPtoDP` at `0x180084add`
- `GDI32!LPtoDP` at `0x180084b11`
- `GDI32!GetDeviceCaps` at `0x180084a70`
- `GDI32!GetDeviceCaps` at `0x180084a70`
- `GDI32!DeleteDC` at `0x180084be6`
- `GDI32!DeleteDC` at `0x180084be6`
- `GDI32!RestoreDC` at `0x180084bd2`
- `GDI32!RestoreDC` at `0x180084bd2`
- `GDI32!GetMapMode` at `0x180084a54`
- `GDI32!GetMapMode` at `0x180084a54`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxDraw(
        CDisplay **this,
        unsigned int a2,
        int a3,
        void *a4,
        struct tagDVTARGETDEVICE *a5,
        HDC hdc,
        HDC a7,
        struct tagRECT *a8,
        struct tagRECT *a9,
        struct tagRECT *a10,
        int (*a11)(unsigned int),
        unsigned int a12,
        int a13)
{
  HDC v15; // rdi
  struct tagRECT *v16; // r12
  __int64 v17; // rcx
  unsigned int v18; // edi
  HDC v19; // r15
  HDC IC; // rax
  int v21; // r13d
  CDisplay *v22; // rcx
  HDC v23; // r8
  struct tagDVTARGETDEVICE *v24; // r9
  COleObject *v25; // rbx
  CDisplay *v27; // rax
  HDC v28; // r8
  CDisplay *v29; // rbx
  int (*v30)(unsigned int); // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+38h] [rbp-C8h]
  struct tagRECT *v32; // [rsp+40h] [rbp-C0h]
  struct tagRECT *v33; // [rsp+48h] [rbp-B8h]
  struct tagRECT v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  HDC v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  _QWORD v40[7]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[32]; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPOINT pt[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct tagPOINT v43[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct tagPOINT v44[2]; // [rsp+F8h] [rbp-8h] BYREF

  v15 = a7;
  v16 = a8;
  v32 = a9;
  v33 = a10;
  *(_QWORD *)&v36.left = a4;
  CMagellanBMPStateWrap::CMagellanBMPStateWrap((CMagellanBMPStateWrap *)&v37, (struct CTxtEdit *)this, hdc);
  *(_OWORD *)&pt[0].x = 0;
  *(_OWORD *)&v43[0].x = 0;
  *(_OWORD *)&v44[0].x = 0;
  CCallMgr::CCallMgr((CCallMgr *)v41, (struct CTxtEdit *)this);
  if ( !a13 )
  {
    v17 = *((_QWORD *)this[8] + 6);
    if ( v17 )
    {
      *(_DWORD *)(v17 + 16) |= 4u;
      v18 = -2147418113;
      goto LABEL_39;
    }
  }
  if ( a2 != 1 && a2 != 8 )
  {
    v18 = -2147221397;
    goto LABEL_39;
  }
  if ( !a8 && (*((_BYTE *)this + 180) & 8) == 0 || a7 && !a5 )
  {
    v18 = -2147024809;
    goto LABEL_39;
  }
  v19 = 0;
  if ( !a7 && a5 )
  {
    IC = CW32System::CreateIC(
           (unsigned __int16 *)((char *)a5 + a5->tdDriverNameOffset),
           (unsigned __int16 *)((char *)a5 + a5->tdDeviceNameOffset),
           (unsigned __int16 *)((char *)a5 + a5->tdPortNameOffset),
           (const struct _devicemodeW *)((char *)a5 + a5->tdExtDevmodeOffset));
    v19 = IC;
    if ( !IC )
    {
      v18 = -2147467259;
      goto LABEL_39;
    }
    v15 = IC;
  }
  v21 = 0;
  if ( GetMapMode(hdc) != 1 && GetDeviceCaps(hdc, 2) != 5 )
  {
    v21 = 1;
    if ( a8 )
    {
      *(struct tagRECT *)&pt[0].x = *a8;
      v16 = (struct tagRECT *)pt;
      LPtoDP(hdc, pt, 2);
    }
    if ( a9 )
    {
      v32 = (struct tagRECT *)v43;
      *(struct tagRECT *)&v43[0].x = *a9;
      LPtoDP(hdc, v43, 2);
    }
    if ( a10 )
    {
      v33 = (struct tagRECT *)v44;
      *(struct tagRECT *)&v44[0].x = *a10;
      LPtoDP(hdc, v44, 2);
    }
    ConvertDrawDCMapping(hdc);
  }
  v40[0] = 0;
  v40[3] = 0;
  v40[2] = 0;
  v22 = this[8];
  v40[1] = this;
  CDisplay::SetDrawInfo(v22, (struct CDrawInfo *)v40, a2, a3, *(void **)&v36.left, a5, v15);
  if ( !a13 || !a5 )
  {
    v18 = 1;
    if ( v32 )
      goto LABEL_46;
    if ( (*((_BYTE *)this + 180) & 8) != 0 )
    {
      if ( a13 )
        goto LABEL_46;
    }
    else if ( a13 != -1 )
    {
      goto LABEL_46;
    }
    v18 = CDisplay::Draw(this[8], hdc, v23, v16, 0, v33, v30, v31);
    if ( v18 != 1 )
      goto LABEL_29;
LABEL_46:
    v27 = (CDisplay *)(*(__int64 (__fastcall **)(CDisplay *))(*(_QWORD *)this[8] + 376LL))(this[8]);
    v29 = v27;
    if ( v27 )
    {
      *((_DWORD *)v27 + 14) |= 0x80u;
      v18 = CDisplay::Draw(v27, hdc, v28, v16, v32, v33, v30, v31);
      (*(void (__fastcall **)(CDisplay *, __int64))(*(_QWORD *)v29 + 72LL))(v29, 1);
    }
    goto LABEL_29;
  }
  v36 = *v16;
  v18 = CTxtEdit::FormatAndPrint((CTxtEdit *)this, hdc, v15, v24, &v36, v32);
  CTxtEdit::OnFormatRange(this, 0, 0, 0);
LABEL_29:
  CDisplay::ReleaseDrawInfo(this[8]);
  if ( v21 )
    RestoreDC(hdc, -1);
  if ( v19 )
    DeleteDC(v19);
  if ( this[17] )
  {
    if ( ((_BYTE)this[23] & 0xC0) != 0 )
    {
      v25 = (COleObject *)*((_QWORD *)CTxtEdit::GetObjectMgr((CTxtEdit *)this) + 5);
      if ( v25 )
      {
        *((_WORD *)this + 92) ^= (*((_WORD *)this + 92) ^ (((*((_WORD *)this + 92) >> 6) - 1) << 6)) & 0xC0;
        if ( (*((_DWORD *)v25 + 40) & 0x400) != 0 )
        {
          COleObject::FetchObjectExtents(v25);
          *((_DWORD *)v25 + 40) &= ~0x400u;
        }
        COleObject::ResetPosRect(v25, 0);
        COleObject::OnReposition(v25, 0, 0);
      }
    }
  }
LABEL_39:
  CCallMgr::~CCallMgr((CCallMgr *)v41);
  CMagellan::InvertMagellanDownBMP((HGDIOBJ *)(v39 + 24), *(struct CDisplay **)(v39 + 64), v37, v38);
  return v18;
}

```

## disassembly

```asm
0x180084910  push    rbp
0x180084912  push    rbx
0x180084913  push    rsi
0x180084914  push    rdi
0x180084915  push    r12
0x180084917  push    r13
0x180084919  push    r14
0x18008491b  push    r15
0x18008491d  lea     rbp, [rsp-18h]
0x180084922  sub     rsp, 118h
0x180084929  mov     rax, cs:__security_cookie
0x180084930  xor     rax, rsp
0x180084933  mov     [rbp+50h+var_48], rax
0x180084937  mov     rax, [rbp+50h+arg_40]
0x18008493e  mov     r15d, edx
0x180084941  mov     r14, [rbp+50h+hdc]
0x180084948  mov     rsi, rcx
0x18008494b  mov     rbx, [rbp+50h+arg_20]
0x180084952  mov     rdi, [rbp+50h+arg_30]
0x180084959  mov     r12, [rbp+50h+arg_38]
0x180084960  mov     [rsp+150h+var_110], rax
0x180084965  mov     rax, [rbp+50h+arg_48]
0x18008496c  mov     [rsp+150h+var_FC], edx
0x180084970  mov     rdx, rcx; struct CTxtEdit *
0x180084973  mov     [rsp+150h+var_100], r8d
0x180084978  lea     rcx, [rsp+150h+var_E8]; this
0x18008497d  mov     r8, r14; HDC
0x180084980  mov     [rsp+150h+var_108], rax
0x180084985  mov     qword ptr [rsp+150h+var_F8.left], r9
0x18008498a  call    ??0CMagellanBMPStateWrap@@QEAA@AEAVCTxtEdit@@PEAUHDC__@@@Z; CMagellanBMPStateWrap::CMagellanBMPStateWrap(CTxtEdit &,HDC__ *)
0x18008498f  xorps   xmm0, xmm0
0x180084992  lea     rcx, [rbp+50h+var_98]; this
0x180084996  xorps   xmm1, xmm1
0x180084999  mov     rdx, rsi; struct CTxtEdit *
0x18008499c  movups  xmmword ptr [rbp+50h+pt.x], xmm0
0x1800849a0  movups  xmmword ptr [rbp+50h+var_68.x], xmm1
0x1800849a4  movups  xmmword ptr [rbp+50h+var_58.x], xmm0
0x1800849a8  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x1800849ad  cmp     [rbp+50h+arg_60], 0
0x1800849b4  jnz     short loc_1800849D1
0x1800849b6  mov     rax, [rsi+40h]
0x1800849ba  mov     rcx, [rax+30h]
0x1800849be  test    rcx, rcx
0x1800849c1  jz      short loc_1800849D1
0x1800849c3  or      dword ptr [rcx+10h], 4
0x1800849c7  mov     edi, 8000FFFFh
0x1800849cc  jmp     loc_180084C76
0x1800849d1  cmp     r15d, 1
0x1800849d5  jz      short loc_1800849E7
0x1800849d7  cmp     r15d, 8
0x1800849db  jz      short loc_1800849E7
0x1800849dd  mov     edi, 8004006Bh
0x1800849e2  jmp     loc_180084C76
0x1800849e7  test    r12, r12
0x1800849ea  jnz     short loc_1800849F5
0x1800849ec  test    byte ptr [rsi+0B4h], 8
0x1800849f3  jz      short loc_1800849FF
0x1800849f5  test    rdi, rdi
0x1800849f8  jz      short loc_180084A09
0x1800849fa  test    rbx, rbx
0x1800849fd  jnz     short loc_180084A09
0x1800849ff  mov     edi, 80070057h
0x180084a04  jmp     loc_180084C76
0x180084a09  xor     r15d, r15d
0x180084a0c  test    rdi, rdi
0x180084a0f  jnz     short loc_180084A4E
0x180084a11  test    rbx, rbx
0x180084a14  jz      short loc_180084A4E
0x180084a16  movzx   r9d, word ptr [rbx+0Ah]
0x180084a1b  movzx   r8d, word ptr [rbx+8]
0x180084a20  add     r9, rbx; struct _devicemodeW *
0x180084a23  movzx   edx, word ptr [rbx+6]
0x180084a27  add     r8, rbx; unsigned __int16 *
0x180084a2a  movzx   ecx, word ptr [rbx+4]
0x180084a2e  add     rdx, rbx; unsigned __int16 *
0x180084a31  add     rcx, rbx; unsigned __int16 *
0x180084a34  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x180084a39  mov     r15, rax
0x180084a3c  test    rax, rax
0x180084a3f  jnz     short loc_180084A4B
0x180084a41  mov     edi, 80004005h
0x180084a46  jmp     loc_180084C76
0x180084a4b  mov     rdi, rax
0x180084a4e  mov     rcx, r14; hdc
0x180084a51  xor     r13d, r13d
0x180084a54  call    cs:__imp_GetMapMode
0x180084a5b  nop     dword ptr [rax+rax+00h]
0x180084a60  cmp     eax, 1
0x180084a63  jz      loc_180084B25
0x180084a69  lea     edx, [r13+2]; index
0x180084a6d  mov     rcx, r14; hdc
0x180084a70  call    cs:__imp_GetDeviceCaps
0x180084a77  nop     dword ptr [rax+rax+00h]
0x180084a7c  cmp     eax, 5
0x180084a7f  jz      loc_180084B25
0x180084a85  mov     r13d, 1
0x180084a8b  test    r12, r12
0x180084a8e  jz      short loc_180084AB5
0x180084a90  movups  xmm0, xmmword ptr [r12]
0x180084a95  lea     r8d, [r13+1]; c
0x180084a99  mov     rcx, r14; hdc
0x180084a9c  lea     rdx, [rbp+50h+pt]; lppt
0x180084aa0  movdqu  xmmword ptr [rbp+50h+pt.x], xmm0
0x180084aa5  lea     r12, [rbp+50h+pt]
0x180084aa9  call    cs:__imp_LPtoDP
0x180084ab0  nop     dword ptr [rax+rax+00h]
0x180084ab5  mov     rax, [rsp+150h+var_110]
0x180084aba  test    rax, rax
0x180084abd  jz      short loc_180084AE9
0x180084abf  movups  xmm0, xmmword ptr [rax]
0x180084ac2  lea     rax, [rbp+50h+var_68]
0x180084ac6  mov     r8d, 2; c
0x180084acc  lea     rdx, [rbp+50h+var_68]; lppt
0x180084ad0  mov     [rsp+150h+var_110], rax
0x180084ad5  mov     rcx, r14; hdc
0x180084ad8  movdqu  xmmword ptr [rbp+50h+var_68.x], xmm0
0x180084add  call    cs:__imp_LPtoDP
0x180084ae4  nop     dword ptr [rax+rax+00h]
0x180084ae9  mov     rax, [rsp+150h+var_108]
0x180084aee  test    rax, rax
0x180084af1  jz      short loc_180084B1D
0x180084af3  movups  xmm0, xmmword ptr [rax]
0x180084af6  lea     rax, [rbp+50h+var_58]
0x180084afa  mov     r8d, 2; c
0x180084b00  lea     rdx, [rbp+50h+var_58]; lppt
0x180084b04  mov     [rsp+150h+var_108], rax
0x180084b09  mov     rcx, r14; hdc
0x180084b0c  movdqu  xmmword ptr [rbp+50h+var_58.x], xmm0
0x180084b11  call    cs:__imp_LPtoDP
0x180084b18  nop     dword ptr [rax+rax+00h]
0x180084b1d  mov     rcx, r14; hdc
0x180084b20  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x180084b25  mov     rax, qword ptr [rsp+150h+var_F8.left]
0x180084b2a  lea     rdx, [rbp+50h+var_D0]; struct CDrawInfo *
0x180084b2e  mov     r9d, [rsp+150h+var_100]; int
0x180084b33  xor     ecx, ecx
0x180084b35  mov     r8d, [rsp+150h+var_FC]; unsigned int
0x180084b3a  mov     [rbp+50h+var_D0], rcx
0x180084b3e  mov     [rbp+50h+var_B8], rcx
0x180084b42  mov     [rbp+50h+var_C0], rcx
0x180084b46  mov     rcx, [rsi+40h]; this
0x180084b4a  mov     [rsp+150h+var_120], rdi; int (*)(unsigned int)
0x180084b4f  mov     [rsp+150h+var_128], rbx; struct tagDVTARGETDEVICE *
0x180084b54  mov     [rbp+50h+var_C8], rsi
0x180084b58  mov     [rsp+150h+var_130], rax; void *
0x180084b5d  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x180084b62  mov     ecx, [rbp+50h+arg_60]
0x180084b68  test    ecx, ecx
0x180084b6a  jz      loc_180084CBE
0x180084b70  test    rbx, rbx
0x180084b73  jz      loc_180084CBE
0x180084b79  mov     rax, [rsp+150h+var_110]
0x180084b7e  mov     r8, rdi; HDC
0x180084b81  movups  xmm0, xmmword ptr [r12]
0x180084b86  mov     [rsp+150h+var_128], rax; struct tagRECT *
0x180084b8b  mov     rdx, r14; HDC
0x180084b8e  lea     rax, [rsp+150h+var_F8]
0x180084b93  mov     rcx, rsi; this
0x180084b96  mov     [rsp+150h+var_130], rax; struct tagRECT *
0x180084b9b  movdqu  xmmword ptr [rsp+150h+var_F8.left], xmm0
0x180084ba1  call    ?FormatAndPrint@CTxtEdit@@QEAAJPEAUHDC__@@0PEAUtagDVTARGETDEVICE@@PEAUtagRECT@@2@Z; CTxtEdit::FormatAndPrint(HDC__ *,HDC__ *,tagDVTARGETDEVICE *,tagRECT *,tagRECT *)
0x180084ba6  xor     r8d, r8d
0x180084ba9  xor     r9d, r9d
0x180084bac  xor     edx, edx
0x180084bae  mov     rcx, rsi
0x180084bb1  mov     edi, eax
0x180084bb3  call    ?OnFormatRange@CTxtEdit@@AEAA_JPEAU_formatrange@@USPrintControl@@H@Z; CTxtEdit::OnFormatRange(_formatrange *,SPrintControl,int)
0x180084bb8  mov     r12d, 1
0x180084bbe  mov     rcx, [rsi+40h]; this
0x180084bc2  call    ?ReleaseDrawInfo@CDisplay@@QEAAXXZ; CDisplay::ReleaseDrawInfo(void)
0x180084bc7  test    r13d, r13d
0x180084bca  jz      short loc_180084BDE
0x180084bcc  or      edx, 0FFFFFFFFh; nSavedDC
0x180084bcf  mov     rcx, r14; hdc
0x180084bd2  call    cs:__imp_RestoreDC
0x180084bd9  nop     dword ptr [rax+rax+00h]
0x180084bde  test    r15, r15
0x180084be1  jz      short loc_180084BF2
0x180084be3  mov     rcx, r15; hdc
0x180084be6  call    cs:__imp_DeleteDC
0x180084bed  nop     dword ptr [rax+rax+00h]
0x180084bf2  cmp     qword ptr [rsi+88h], 0
0x180084bfa  jz      short loc_180084C76
0x180084bfc  mov     r14d, 0C0h
0x180084c02  test    [rsi+0B8h], r14b
0x180084c09  jz      short loc_180084C76
0x180084c0b  mov     rcx, rsi; this
0x180084c0e  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x180084c13  mov     rbx, [rax+28h]
0x180084c17  test    rbx, rbx
0x180084c1a  jz      short loc_180084C76
0x180084c1c  movzx   eax, word ptr [rsi+0B8h]
0x180084c23  movzx   ecx, ax
0x180084c26  shr     cx, 6
0x180084c2a  sub     cx, r12w
0x180084c2e  shl     cx, 6
0x180084c32  xor     cx, ax
0x180084c35  and     cx, r14w
0x180084c39  xor     cx, ax
0x180084c3c  mov     [rsi+0B8h], cx
0x180084c43  test    dword ptr [rbx+0A0h], 400h
0x180084c4d  jz      short loc_180084C5F
0x180084c4f  mov     rcx, rbx; this
0x180084c52  call    ?FetchObjectExtents@COleObject@@QEAAXXZ; COleObject::FetchObjectExtents(void)
0x180084c57  btr     dword ptr [rbx+0A0h], 0Ah
0x180084c5f  xor     edx, edx; int *
0x180084c61  mov     rcx, rbx; this
0x180084c64  call    ?ResetPosRect@COleObject@@QEAAXPEAJ@Z; COleObject::ResetPosRect(long *)
0x180084c69  xor     r8d, r8d; int
0x180084c6c  xor     edx, edx; int
0x180084c6e  mov     rcx, rbx; this
0x180084c71  call    ?OnReposition@COleObject@@QEAAXJJ@Z; COleObject::OnReposition(long,long)
0x180084c76  lea     rcx, [rbp+50h+var_98]; this
0x180084c7a  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180084c7f  mov     rdx, [rsp+150h+var_D8]
0x180084c84  mov     r9, [rsp+150h+var_E0]; HDC
0x180084c89  mov     r8d, [rsp+150h+var_E8]; int
0x180084c8e  lea     rcx, [rdx+18h]; this
0x180084c92  mov     rdx, [rdx+40h]; struct CDisplay *
0x180084c96  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x180084c9b  mov     eax, edi
0x180084c9d  mov     rcx, [rbp+50h+var_48]
0x180084ca1  xor     rcx, rsp; StackCookie
0x180084ca4  call    __security_check_cookie
0x180084ca9  add     rsp, 118h
0x180084cb0  pop     r15
0x180084cb2  pop     r14
0x180084cb4  pop     r13
0x180084cb6  pop     r12
0x180084cb8  pop     rdi
0x180084cb9  pop     rsi
0x180084cba  pop     rbx
0x180084cbb  pop     rbp
0x180084cbc  retn
0x180084cbe  cmp     [rsp+150h+var_110], 0
0x180084cc4  mov     ebx, 1
0x180084cc9  mov     edi, ebx
0x180084ccb  jnz     short loc_180084D0D
0x180084ccd  test    byte ptr [rsi+0B4h], 8
0x180084cd4  jz      short loc_180084CDC
0x180084cd6  test    ecx, ecx
0x180084cd8  jz      short loc_180084CE1
0x180084cda  jmp     short loc_180084D0D
0x180084cdc  cmp     ecx, 0FFFFFFFFh
0x180084cdf  jnz     short loc_180084D0D
0x180084ce1  mov     rax, [rsp+150h+var_108]
0x180084ce6  mov     r9, r12; struct tagRECT *
0x180084ce9  mov     rcx, [rsi+40h]; this
0x180084ced  mov     rdx, r14; hdc
0x180084cf0  mov     [rsp+150h+var_128], rax; struct tagRECT *
0x180084cf5  mov     [rsp+150h+var_130], 0; struct tagRECT *
0x180084cfe  call    ?Draw@CDisplay@@QEAAJPEAUHDC__@@0PEBUtagRECT@@11P6AHK@ZK@Z; CDisplay::Draw(HDC__ *,HDC__ *,tagRECT const *,tagRECT const *,tagRECT const *,int (*)(ulong),ulong)
0x180084d03  mov     edi, eax
0x180084d05  cmp     eax, ebx
0x180084d07  jnz     loc_180084BB8
0x180084d0d  mov     rcx, [rsi+40h]
0x180084d11  mov     rax, [rcx]
0x180084d14  mov     rax, [rax+178h]
0x180084d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d20  mov     rbx, rax
0x180084d23  test    rax, rax
0x180084d26  jz      loc_180084BB8
0x180084d2c  bts     dword ptr [rax+38h], 7
0x180084d31  mov     r9, r12; struct tagRECT *
0x180084d34  mov     rax, [rsp+150h+var_108]
0x180084d39  mov     rdx, r14; hdc
0x180084d3c  mov     [rsp+150h+var_128], rax; struct tagRECT *
0x180084d41  mov     rcx, rbx; this
0x180084d44  mov     rax, [rsp+150h+var_110]
0x180084d49  mov     [rsp+150h+var_130], rax; struct tagRECT *
0x180084d4e  call    ?Draw@CDisplay@@QEAAJPEAUHDC__@@0PEBUtagRECT@@11P6AHK@ZK@Z; CDisplay::Draw(HDC__ *,HDC__ *,tagRECT const *,tagRECT const *,tagRECT const *,int (*)(ulong),ulong)
0x180084d53  mov     r8, [rbx]
0x180084d56  mov     edi, eax
0x180084d58  mov     r12d, 1
0x180084d5e  mov     rcx, rbx
0x180084d61  mov     edx, r12d
0x180084d64  mov     rax, [r8+48h]
0x180084d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d6d  jmp     loc_180084BBE
```
