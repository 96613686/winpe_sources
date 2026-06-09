# CLightDTEngine::PasteDataObjectToRange(IDataObject *,CTxtRange *,ushort,_repastespecial *,IUndoBuilder *,ulong)

- ea: `0x18006cc4c`
- end: `0x18006d384`
- name: `?PasteDataObjectToRange@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@GPEAU_repastespecial@@PEAVIUndoBuilder@@K@Z`
- size: `1848`
- prototype: `__int64 __fastcall(CTxtEdit **this, struct IDataObject *, struct CTxtRange *, __int16, struct _repastespecial *, struct IUndoBuilder *, unsigned int)`
- caller_count: `2`
- callee_count: `19`
- tags: ``

## callers

- `0x180049814`
- `0x18005e88c`

## callees

- `0x180006610`
- `0x18001d040`
- `0x18001db20`
- `0x1800202a0`
- `0x180032c68`
- `0x180038d20`
- `0x18003ffa8`
- `0x1800490f0`
- `0x18004a0c8`
- `0x18004a8fc`
- `0x18006c4c0`
- `0x18006c8b8`
- `0x18006cacc`
- `0x18006cc4c`
- `0x180071e68`
- `0x18008fe40`
- `0x180090508`
- `0x180090d48`
- `0x180092010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18006cf93`
- `KERNEL32!GlobalLock` at `0x18006d177`
- `KERNEL32!GlobalLock` at `0x18006d2bf`
- `KERNEL32!GlobalLock` at `0x18006cf93`
- `KERNEL32!GlobalLock` at `0x18006d177`
- `KERNEL32!GlobalLock` at `0x18006d2bf`
- `KERNEL32!GlobalUnlock` at `0x18006cfce`
- `KERNEL32!GlobalUnlock` at `0x18006cfe1`
- `KERNEL32!GlobalUnlock` at `0x18006d263`
- `KERNEL32!GlobalUnlock` at `0x18006d305`
- `KERNEL32!GlobalUnlock` at `0x18006cfce`
- `KERNEL32!GlobalUnlock` at `0x18006cfe1`
- `KERNEL32!GlobalUnlock` at `0x18006d263`
- `KERNEL32!GlobalUnlock` at `0x18006d305`
- `USER32!OpenClipboard` at `0x18006ceab`
- `USER32!OpenClipboard` at `0x18006ceab`
- `USER32!CloseClipboard` at `0x18006cff3`
- `USER32!CloseClipboard` at `0x18006cff3`
- `USER32!GetClipboardOwner` at `0x18006cd82`
- `USER32!GetClipboardOwner` at `0x18006cd82`
- `USER32!GetClipboardData` at `0x18006ced8`
- `USER32!GetClipboardData` at `0x18006cef1`
- `USER32!GetClipboardData` at `0x18006cf0e`
- `USER32!GetClipboardData` at `0x18006cf2a`
- `USER32!GetClipboardData` at `0x18006cf41`
- `USER32!GetClipboardData` at `0x18006cf6f`
- `USER32!GetClipboardData` at `0x18006ced8`
- `USER32!GetClipboardData` at `0x18006cef1`
- `USER32!GetClipboardData` at `0x18006cf0e`
- `USER32!GetClipboardData` at `0x18006cf2a`
- `USER32!GetClipboardData` at `0x18006cf41`
- `USER32!GetClipboardData` at `0x18006cf6f`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::PasteDataObjectToRange(
        CTxtEdit **this,
        struct IDataObject *a2,
        struct CTxtRange *a3,
        __int16 a4,
        struct _repastespecial *a5,
        struct IUndoBuilder *a6,
        unsigned int a7)
{
  __int16 v10; // ax
  int Clipboard; // ebx
  CTxtEdit *v12; // rax
  void *v13; // r15
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // r12
  HWND ClipboardOwner; // rdi
  struct IDataObject *v19; // rcx
  unsigned int v20; // r9d
  DWORD_PTR dwParam; // rcx
  int v22; // eax
  unsigned int v23; // r12d
  HANDLE ClipboardData; // rdi
  HANDLE v25; // rax
  void *v26; // rax
  void *v27; // rcx
  HANDLE v28; // rax
  unsigned __int16 *v29; // r9
  CDisplay *v30; // rcx
  struct IUndoBuilder *v31; // rdi
  unsigned int v32; // edi
  struct tagFORMATETC near **i; // rdx
  int v34; // eax
  int v35; // ecx
  char *v36; // rax
  HBITMAP v37; // r12
  int v38; // edi
  unsigned __int16 *v39; // rax
  int v40; // [rsp+40h] [rbp-51h]
  HBITMAP hMem; // [rsp+48h] [rbp-49h]
  struct tagFORMATETC near **v42; // [rsp+50h] [rbp-41h]
  unsigned __int16 *v43; // [rsp+58h] [rbp-39h]
  struct tagSTGMEDIUM v44; // [rsp+60h] [rbp-31h] BYREF
  __int16 v45; // [rsp+78h] [rbp-19h] BYREF
  int v46; // [rsp+7Ah] [rbp-17h]
  __int16 v47; // [rsp+7Eh] [rbp-13h]
  __int64 v48; // [rsp+80h] [rbp-11h]
  int v49; // [rsp+88h] [rbp-9h]
  int v50; // [rsp+8Ch] [rbp-5h]
  __int64 v51; // [rsp+90h] [rbp-1h]
  struct IDataObject *v52; // [rsp+98h] [rbp+7h]
  struct IDataObject *v53; // [rsp+E8h] [rbp+57h] BYREF
  HWND hWndNewOwner; // [rsp+F0h] [rbp+5Fh] BYREF

  v53 = a2;
  if ( !a3 )
    return 2147500037LL;
  if ( (*((_WORD *)CRchTxtPtr::GetPF((struct CTxtRange *)((char *)a3 + 8)) + 1) & 0x4000) == 0 )
    goto LABEL_10;
  if ( CTxtPtr::GetPrevChar((struct CTxtRange *)((char *)a3 + 24)) == 9
    && CTxtPtr::GetChar((struct CTxtRange *)((char *)a3 + 24)) == 13 )
  {
    v10 = *((_WORD *)a3 + 49);
    if ( (v10 & 2) != 0 )
    {
      Clipboard = -2147467259;
      goto LABEL_21;
    }
    *((_WORD *)a3 + 49) = v10 & 0xFFFE;
    CTxtRange::Advance(a3, -1);
  }
  if ( (*((_WORD *)a3 + 49) & 2) != 0 )
  {
    if ( (*((_WORD *)a3 + 49) & 0x100) == 0 )
      goto LABEL_10;
    return 2147500037LL;
  }
  if ( *((_DWORD *)a3 + 22) )
    return 2147500037LL;
LABEL_10:
  v12 = *this;
  Clipboard = -2147221404;
  v52 = v53;
  v13 = 0;
  v14 = (*((_DWORD *)v12 + 45) >> 19) & 1;
  memset(&v44, 0, sizeof(v44));
  v15 = *((_QWORD *)v12 + 17);
  v40 = v14;
  if ( v15 )
    v16 = *(_QWORD *)(v15 + 32);
  else
    v16 = 0;
  if ( v53 )
    goto LABEL_24;
  Clipboard = CW32System::OleGetClipboard(&v53);
  if ( Clipboard >= 0 )
    goto LABEL_24;
  ClipboardOwner = GetClipboardOwner();
  hWndNewOwner = 0;
  if ( !ClipboardOwner || (unsigned int)CTxtEdit::TxGetWindow(*this, &hWndNewOwner) || ClipboardOwner != hWndNewOwner )
  {
    if ( (unsigned int)CTxtEdit::TxGetWindow(*this, &hWndNewOwner) || !OpenClipboard(hWndNewOwner) )
      goto LABEL_21;
    CDisplay::Freeze(*((CDisplay **)*this + 8));
    if ( !v40 )
    {
      v23 = 0;
      ClipboardData = GetClipboardData((unsigned __int16)g_rgFETC);
      if ( ClipboardData )
        goto LABEL_50;
      v23 = 2;
      ClipboardData = GetClipboardData((unsigned __int16)xmmword_1800A3110);
      if ( ClipboardData )
        goto LABEL_50;
    }
    ClipboardData = GetClipboardData((unsigned __int16)xmmword_1800A30F0);
    v23 = 1;
    if ( ClipboardData || !v40 && (v23 = 11, (ClipboardData = GetClipboardData(0xDu)) != 0) )
    {
LABEL_50:
      v27 = ClipboardData;
    }
    else
    {
      v25 = GetClipboardData(1u);
      ClipboardData = v25;
      if ( !v25 )
      {
        v28 = GetClipboardData(8u);
        if ( v28 )
          Clipboard = CLightDTEngine::DIBToRange((CLightDTEngine *)this, v28, a3, a6);
LABEL_57:
        CDisplay::Thaw(*((CDisplay **)*this + 8));
        CloseClipboard();
        if ( Clipboard >= 0 )
          return (unsigned int)Clipboard;
LABEL_21:
        CTxtEdit::Beep(*this);
        return (unsigned int)Clipboard;
      }
      v26 = CW32System::TextHGlobalAtoW(v25);
      v13 = v26;
      if ( !v26 )
        goto LABEL_53;
      v23 = 12;
      v27 = v26;
    }
    v29 = (unsigned __int16 *)GlobalLock(v27);
    if ( v29 )
    {
      Clipboard = CLightDTEngine::HGlobalToRange((CLightDTEngine *)this, v23, ClipboardData, v29, a3, a6);
      goto LABEL_54;
    }
LABEL_53:
    Clipboard = -2147024882;
LABEL_54:
    if ( v13 )
    {
      GlobalUnlock(v13);
      CW32System::GlobalFree(v13);
    }
    else
    {
      GlobalUnlock(ClipboardData);
    }
    goto LABEL_57;
  }
  v19 = (struct IDataObject *)this[2];
  v53 = v19;
  if ( !v19 )
    goto LABEL_21;
  ((void (__fastcall *)(struct IDataObject *))v19->lpVtbl->AddRef)(v19);
  v14 = v40;
LABEL_24:
  v20 = a7;
  *((_BYTE *)this + 24) = 1;
  if ( (v20 & 1) != 0 || !v16 )
    goto LABEL_61;
  dwParam = 0;
  LOWORD(hWndNewOwner) = a4;
  if ( a5 && a5->dwAspect == 4 )
    dwParam = a5->dwParam;
  v22 = (*(__int64 (__fastcall **)(__int64, struct IDataObject *, HWND *, _QWORD, int, DWORD_PTR))(*(_QWORD *)v16 + 64LL))(
          v16,
          v53,
          &hWndNewOwner,
          (v20 >> 1) & 1,
          1,
          dwParam);
  Clipboard = 0;
  if ( v22 != 262448 )
    Clipboard = v22;
  if ( Clipboard && Clipboard != -2147467263 )
    goto LABEL_125;
  if ( (_WORD)hWndNewOwner )
  {
    if ( a4 )
    {
      if ( a4 != (_WORD)hWndNewOwner )
      {
        Clipboard = -2147221404;
        goto LABEL_125;
      }
      goto LABEL_61;
    }
  }
  else if ( a4 )
  {
    goto LABEL_61;
  }
  a4 = (__int16)hWndNewOwner;
LABEL_61:
  if ( a4 == 1 && !v14 )
  {
    v48 = 0;
    v46 = 0;
    v47 = 0;
    v51 = 0;
    v45 = 13;
    v49 = 0;
    v50 = -1;
    if ( !((unsigned int (__fastcall *)(struct IDataObject *, __int16 *))v53->lpVtbl->QueryGetData)(v53, &v45) )
      a4 = 13;
  }
  if ( (*((_BYTE *)*this + 180) & 4) != 0 )
  {
    Clipboard = -2147024891;
    goto LABEL_125;
  }
  v30 = (CDisplay *)*((_QWORD *)*this + 8);
  v42 = &g_rgFETC;
  hMem = 0;
  v43 = 0;
  LODWORD(hWndNewOwner) = 0;
  CDisplay::Freeze(v30);
  v31 = a6;
  if ( a6 )
  {
    (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)a6 + 48LL))(a6);
    (**(void (__fastcall ***)(struct IUndoBuilder *, __int64))v31)(v31, 5);
  }
  v32 = 0;
  for ( i = &g_rgFETC; ; v42 = i )
  {
    if ( v32 >= 0x11 )
    {
      v38 = (int)hWndNewOwner;
      goto LABEL_121;
    }
    if ( (!a4 || a4 == *(_WORD *)i) && ((*((_BYTE *)*this + 180) & 1) != 0 || (*((_BYTE *)&g_rgDOI + 4 * v32) & 2) != 0) )
      break;
LABEL_98:
    ++v32;
    i += 4;
  }
  if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC near **))v53->lpVtbl->QueryGetData)(
         v53,
         i) )
  {
    goto LABEL_97;
  }
  if ( v32 <= 0xE )
  {
    v34 = 21506;
    if ( _bittest(&v34, v32) )
      goto LABEL_81;
  }
  if ( v40 )
  {
    if ( v32 != 11 && v32 )
      goto LABEL_91;
LABEL_97:
    i = v42;
    goto LABEL_98;
  }
  if ( v32 > 0xB )
    goto LABEL_91;
  v35 = 2053;
  if ( !_bittest(&v35, v32) )
    goto LABEL_91;
LABEL_81:
  if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC near **, struct tagSTGMEDIUM *))v53->lpVtbl->GetData)(
         v53,
         v42,
         &v44) )
  {
    goto LABEL_97;
  }
  hMem = v44.hBitmap;
  v36 = (char *)GlobalLock(v44.hBitmap);
  v43 = (unsigned __int16 *)v36;
  if ( !v36 )
  {
    CW32System::ReleaseStgMedium(&v44);
    Clipboard = -2147024882;
    goto LABEL_124;
  }
  if ( (v32 <= 1 || v32 == 10) && !(unsigned int)IsRTF(v36) )
    v32 = 12;
LABEL_91:
  CTxtRange::AdjustEndEOP(a3, 0);
  LODWORD(hWndNewOwner) = 1;
  if ( v32 > 8 )
  {
    if ( v32 != 9 )
    {
      switch ( v32 )
      {
        case 0xAu:
LABEL_119:
          v37 = hMem;
          Clipboard = CLightDTEngine::HGlobalToRange((CLightDTEngine *)this, v32, hMem, v43, a3, a6);
          goto LABEL_103;
        case 0xBu:
          v39 = v43;
          v37 = hMem;
          goto LABEL_117;
        case 0xCu:
LABEL_114:
          v37 = hMem;
          v13 = CW32System::TextHGlobalAtoW(hMem);
          v39 = (unsigned __int16 *)GlobalLock(v13);
          if ( !v39 )
          {
            Clipboard = -2147024882;
            goto LABEL_103;
          }
LABEL_117:
          Clipboard = CLightDTEngine::HGlobalToRange((CLightDTEngine *)this, v32, 0, v39, a3, a6);
          if ( v13 )
          {
            GlobalUnlock(v13);
            CW32System::GlobalFree(v13);
          }
          goto LABEL_103;
      }
      if ( v32 != 13 )
      {
        if ( v32 != 14 )
        {
          if ( v32 - 15 >= 2 )
            goto LABEL_113;
          goto LABEL_102;
        }
        goto LABEL_114;
      }
    }
LABEL_101:
    Clipboard = CLightDTEngine::CreateOleObjFromDataObj((CLightDTEngine *)this, v53, a3, a5, v32, a6);
LABEL_102:
    v37 = hMem;
LABEL_103:
    v38 = (int)hWndNewOwner;
    goto LABEL_104;
  }
  if ( v32 == 8 )
    goto LABEL_101;
  if ( v32 <= 2 )
    goto LABEL_119;
  if ( v32 == 3 || v32 == 4 )
    goto LABEL_101;
  if ( v32 == 5 )
    goto LABEL_97;
  if ( v32 - 6 <= 1 )
    goto LABEL_101;
LABEL_113:
  v37 = hMem;
  v38 = 0;
LABEL_104:
  if ( v37 )
  {
    GlobalUnlock(v37);
    CW32System::ReleaseStgMedium(&v44);
  }
LABEL_121:
  if ( !v38 && v40 )
    Clipboard = -2147221404;
LABEL_124:
  CDisplay::Thaw(*((CDisplay **)*this + 8));
LABEL_125:
  if ( !v52 )
    ((void (__fastcall *)(struct IDataObject *))v53->lpVtbl->Release)(v53);
  return (unsigned int)Clipboard;
}

```

## disassembly

```asm
0x18006cc4c  mov     [rsp-8+arg_0], rbx
0x18006cc51  mov     [rsp-8+arg_8], rdx
0x18006cc56  push    rbp
0x18006cc57  push    rsi
0x18006cc58  push    rdi
0x18006cc59  push    r12
0x18006cc5b  push    r13
0x18006cc5d  push    r14
0x18006cc5f  push    r15
0x18006cc61  lea     rbp, [rsp-0Fh]
0x18006cc66  sub     rsp, 0A0h
0x18006cc6d  movzx   r13d, r9w
0x18006cc71  mov     r14, r8
0x18006cc74  mov     rsi, rcx
0x18006cc77  test    r8, r8
0x18006cc7a  jz      loc_18006CD48
0x18006cc80  lea     rcx, [r8+8]; this
0x18006cc84  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18006cc89  mov     edi, 9
0x18006cc8e  mov     ecx, 4000h
0x18006cc93  lea     ebx, [rdi+4]
0x18006cc96  test    [rax+2], cx
0x18006cc9a  jz      short loc_18006CCF2
0x18006cc9c  lea     rcx, [r14+18h]; this
0x18006cca0  call    ?GetPrevChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetPrevChar(void)
0x18006cca5  cmp     ax, di
0x18006cca8  jnz     short loc_18006CCE3
0x18006ccaa  lea     rcx, [r14+18h]; this
0x18006ccae  call    ?GetChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetChar(void)
0x18006ccb3  cmp     ax, bx
0x18006ccb6  jnz     short loc_18006CCE3
0x18006ccb8  movzx   eax, word ptr [r14+62h]
0x18006ccbd  test    al, 2
0x18006ccbf  jz      short loc_18006CCCB
0x18006ccc1  mov     ebx, 80004005h
0x18006ccc6  jmp     loc_18006CDC5
0x18006cccb  mov     ecx, 0FFFEh
0x18006ccd0  or      edx, 0FFFFFFFFh; int
0x18006ccd3  and     ax, cx
0x18006ccd6  mov     rcx, r14; this
0x18006ccd9  mov     [r14+62h], ax
0x18006ccde  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18006cce3  movzx   eax, word ptr [r14+62h]
0x18006cce8  test    al, 2
0x18006ccea  jz      short loc_18006CD3F
0x18006ccec  bt      eax, 8
0x18006ccf0  jb      short loc_18006CD48
0x18006ccf2  xor     r8d, r8d
0x18006ccf5  mov     rax, [rsi]
0x18006ccf8  xorps   xmm0, xmm0
0x18006ccfb  mov     rdx, [rbp+3Fh+arg_8]
0x18006ccff  mov     r10d, 1
0x18006cd05  mov     ebx, 80040064h
0x18006cd0a  mov     [rbp+3Fh+var_38], rdx
0x18006cd0e  mov     r15, r8
0x18006cd11  mov     edi, [rax+0B4h]
0x18006cd17  shr     edi, 13h
0x18006cd1a  and     edi, r10d
0x18006cd1d  mov     qword ptr [rbp+3Fh+var_70.tymed], 0
0x18006cd25  movdqu  xmmword ptr [rbp+3Fh+var_70.8], xmm0
0x18006cd2a  mov     rcx, [rax+88h]
0x18006cd31  mov     [rbp+3Fh+var_90], edi
0x18006cd34  test    rcx, rcx
0x18006cd37  jz      short loc_18006CD68
0x18006cd39  mov     r12, [rcx+20h]
0x18006cd3d  jmp     short loc_18006CD6B
0x18006cd3f  xor     r8d, r8d
0x18006cd42  cmp     [r14+58h], r8d
0x18006cd46  jz      short loc_18006CCF5
0x18006cd48  mov     eax, 80004005h
0x18006cd4d  mov     rbx, [rsp+0D0h+arg_0]
0x18006cd55  add     rsp, 0A0h
0x18006cd5c  pop     r15
0x18006cd5e  pop     r14
0x18006cd60  pop     r13
0x18006cd62  pop     r12
0x18006cd64  pop     rdi
0x18006cd65  pop     rsi
0x18006cd66  pop     rbp
0x18006cd67  retn
0x18006cd68  mov     r12, r8
0x18006cd6b  test    rdx, rdx
0x18006cd6e  jnz     short loc_18006CDEC
0x18006cd70  lea     rcx, [rbp+3Fh+arg_8]; struct IDataObject **
0x18006cd74  call    ?OleGetClipboard@CW32System@@SAJPEAPEAUIDataObject@@@Z; CW32System::OleGetClipboard(IDataObject * *)
0x18006cd79  xor     r8d, r8d
0x18006cd7c  mov     ebx, eax
0x18006cd7e  test    eax, eax
0x18006cd80  jns     short loc_18006CDE6
0x18006cd82  call    cs:__imp_GetClipboardOwner
0x18006cd88  mov     rdi, rax
0x18006cd8b  xor     eax, eax
0x18006cd8d  mov     [rbp+3Fh+hWndNewOwner], rax
0x18006cd91  test    rdi, rdi
0x18006cd94  jz      loc_18006CE91
0x18006cd9a  mov     rcx, [rsi]; this
0x18006cd9d  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x18006cda1  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006cda6  test    eax, eax
0x18006cda8  jnz     loc_18006CE91
0x18006cdae  cmp     rdi, [rbp+3Fh+hWndNewOwner]
0x18006cdb2  jnz     loc_18006CE91
0x18006cdb8  mov     rcx, [rsi+10h]
0x18006cdbc  mov     [rbp+3Fh+arg_8], rcx
0x18006cdc0  test    rcx, rcx
0x18006cdc3  jnz     short loc_18006CDD4
0x18006cdc5  mov     rcx, [rsi]; this
0x18006cdc8  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18006cdcd  mov     eax, ebx
0x18006cdcf  jmp     loc_18006CD4D
0x18006cdd4  mov     rax, [rcx]
0x18006cdd7  mov     rax, [rax+8]
0x18006cddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cde0  mov     edi, [rbp+3Fh+var_90]
0x18006cde3  xor     r8d, r8d
0x18006cde6  mov     r10d, 1
0x18006cdec  mov     r9d, [rbp+3Fh+arg_30]
0x18006cdf0  mov     [rsi+18h], r10b
0x18006cdf4  test    r10b, r9b
0x18006cdf7  jnz     loc_18006D016
0x18006cdfd  test    r12, r12
0x18006ce00  jz      loc_18006D016
0x18006ce06  mov     rax, [rbp+3Fh+arg_20]
0x18006ce0a  mov     rcx, r8
0x18006ce0d  mov     word ptr [rbp+3Fh+hWndNewOwner], r13w
0x18006ce12  test    rax, rax
0x18006ce15  jz      short loc_18006CE20
0x18006ce17  cmp     dword ptr [rax], 4
0x18006ce1a  jnz     short loc_18006CE20
0x18006ce1c  mov     rcx, [rax+4]
0x18006ce20  mov     rax, [r12]
0x18006ce24  lea     r8, [rbp+3Fh+hWndNewOwner]
0x18006ce28  mov     rdx, [rbp+3Fh+arg_8]
0x18006ce2c  mov     [rsp+0D0h+var_A8], rcx
0x18006ce31  mov     rcx, r12
0x18006ce34  shr     r9d, 1
0x18006ce37  mov     rax, [rax+40h]
0x18006ce3b  and     r9d, r10d
0x18006ce3e  mov     dword ptr [rsp+0D0h+var_B0], r10d
0x18006ce43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce48  xor     r8d, r8d
0x18006ce4b  cmp     eax, 40130h
0x18006ce50  mov     ebx, r8d
0x18006ce53  cmovnz  ebx, eax
0x18006ce56  test    ebx, ebx
0x18006ce58  jz      short loc_18006CE66
0x18006ce5a  cmp     ebx, 80004001h
0x18006ce60  jnz     loc_18006D364
0x18006ce66  movzx   eax, word ptr [rbp+3Fh+hWndNewOwner]
0x18006ce6a  test    ax, ax
0x18006ce6d  jz      loc_18006D006
0x18006ce73  test    r13w, r13w
0x18006ce77  jz      loc_18006D00C
0x18006ce7d  cmp     r13w, ax
0x18006ce81  jz      loc_18006D010
0x18006ce87  mov     ebx, 80040064h
0x18006ce8c  jmp     loc_18006D364
0x18006ce91  mov     rcx, [rsi]; this
0x18006ce94  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x18006ce98  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006ce9d  xor     edi, edi
0x18006ce9f  test    eax, eax
0x18006cea1  jnz     loc_18006CDC5
0x18006cea7  mov     rcx, [rbp+3Fh+hWndNewOwner]; hWndNewOwner
0x18006ceab  call    cs:__imp_OpenClipboard
0x18006ceb1  test    eax, eax
0x18006ceb3  jz      loc_18006CDC5
0x18006ceb9  mov     rcx, [rsi]
0x18006cebc  mov     rcx, [rcx+40h]; this
0x18006cec0  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18006cec5  mov     r13d, [rbp+3Fh+var_90]
0x18006cec9  test    r13d, r13d
0x18006cecc  jnz     short loc_18006CF07
0x18006cece  movzx   ecx, word ptr cs:?g_rgFETC@@3PAUtagFORMATETC@@A; uFormat
0x18006ced5  mov     r12d, edi
0x18006ced8  call    cs:__imp_GetClipboardData
0x18006cede  mov     rdi, rax
0x18006cee1  test    rax, rax
0x18006cee4  jnz     loc_18006CF90
0x18006ceea  movzx   ecx, word ptr cs:xmmword_1800A3110; uFormat
0x18006cef1  call    cs:__imp_GetClipboardData
0x18006cef7  lea     r12d, [r13+2]
0x18006cefb  mov     rdi, rax
0x18006cefe  test    rax, rax
0x18006cf01  jnz     loc_18006CF90
0x18006cf07  movzx   ecx, word ptr cs:xmmword_1800A30F0; uFormat
0x18006cf0e  call    cs:__imp_GetClipboardData
0x18006cf14  mov     rdi, rax
0x18006cf17  mov     r12d, 1
0x18006cf1d  test    rax, rax
0x18006cf20  jnz     short loc_18006CF90
0x18006cf22  test    r13d, r13d
0x18006cf25  jnz     short loc_18006CF3C
0x18006cf27  lea     ecx, [rax+0Dh]; uFormat
0x18006cf2a  call    cs:__imp_GetClipboardData
0x18006cf30  lea     r12d, [r13+0Bh]
0x18006cf34  mov     rdi, rax
0x18006cf37  test    rax, rax
0x18006cf3a  jnz     short loc_18006CF90
0x18006cf3c  mov     ecx, 1; uFormat
0x18006cf41  call    cs:__imp_GetClipboardData
0x18006cf47  mov     rdi, rax
0x18006cf4a  test    rax, rax
0x18006cf4d  jz      short loc_18006CF6A
0x18006cf4f  mov     rcx, rax; hMem
0x18006cf52  call    ?TextHGlobalAtoW@CW32System@@SAPEAXPEAX@Z; CW32System::TextHGlobalAtoW(void *)
0x18006cf57  mov     r15, rax
0x18006cf5a  test    rax, rax
0x18006cf5d  jz      short loc_18006CFC1
0x18006cf5f  mov     r12d, 0Ch
0x18006cf65  mov     rcx, rax
0x18006cf68  jmp     short loc_18006CF93
0x18006cf6a  mov     ecx, 8; uFormat
0x18006cf6f  call    cs:__imp_GetClipboardData
0x18006cf75  test    rax, rax
0x18006cf78  jz      short loc_18006CFE7
0x18006cf7a  mov     r9, [rbp+3Fh+arg_28]; struct IUndoBuilder *
0x18006cf7e  mov     r8, r14; struct CTxtRange *
0x18006cf81  mov     rdx, rax; void *
0x18006cf84  mov     rcx, rsi; this
0x18006cf87  call    ?DIBToRange@CLightDTEngine@@IEAAJPEAXPEAVCTxtRange@@PEAVIUndoBuilder@@@Z; CLightDTEngine::DIBToRange(void *,CTxtRange *,IUndoBuilder *)
0x18006cf8c  mov     ebx, eax
0x18006cf8e  jmp     short loc_18006CFE7
0x18006cf90  mov     rcx, rdi; hMem
0x18006cf93  call    cs:__imp_GlobalLock
0x18006cf99  mov     r9, rax; unsigned __int16 *
0x18006cf9c  test    rax, rax
0x18006cf9f  jz      short loc_18006CFC1
0x18006cfa1  mov     rax, [rbp+3Fh+arg_28]
0x18006cfa5  mov     r8, rdi; void *
0x18006cfa8  mov     [rsp+0D0h+var_A8], rax; struct IUndoBuilder *
0x18006cfad  mov     edx, r12d; unsigned int
0x18006cfb0  mov     rcx, rsi; this
0x18006cfb3  mov     [rsp+0D0h+var_B0], r14; struct CTxtRange *
0x18006cfb8  call    ?HGlobalToRange@CLightDTEngine@@IEAAJKPEAXPEAGPEAVCTxtRange@@PEAVIUndoBuilder@@@Z; CLightDTEngine::HGlobalToRange(ulong,void *,ushort *,CTxtRange *,IUndoBuilder *)
0x18006cfbd  mov     ebx, eax
0x18006cfbf  jmp     short loc_18006CFC6
0x18006cfc1  mov     ebx, 8007000Eh
0x18006cfc6  test    r15, r15
0x18006cfc9  jz      short loc_18006CFDE
0x18006cfcb  mov     rcx, r15; hMem
0x18006cfce  call    cs:__imp_GlobalUnlock
0x18006cfd4  mov     rcx, r15; void *
0x18006cfd7  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18006cfdc  jmp     short loc_18006CFE7
0x18006cfde  mov     rcx, rdi; hMem
0x18006cfe1  call    cs:__imp_GlobalUnlock
0x18006cfe7  mov     rcx, [rsi]
0x18006cfea  mov     rcx, [rcx+40h]; this
0x18006cfee  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x18006cff3  call    cs:__imp_CloseClipboard
0x18006cff9  test    ebx, ebx
0x18006cffb  jns     loc_18006CDCD
0x18006d001  jmp     loc_18006CDC5
0x18006d006  test    r13w, r13w
0x18006d00a  jnz     short loc_18006D010
0x18006d00c  movzx   r13d, ax
0x18006d010  mov     r10d, 1
0x18006d016  cmp     r13w, r10w
0x18006d01a  jnz     short loc_18006D063
0x18006d01c  test    edi, edi
0x18006d01e  jnz     short loc_18006D063
0x18006d020  mov     rcx, [rbp+3Fh+arg_8]
0x18006d024  lea     rdx, [rbp+3Fh+var_58]
0x18006d028  xor     eax, eax
0x18006d02a  mov     [rbp+3Fh+var_50], r8
0x18006d02e  mov     [rbp+3Fh+var_56], eax
0x18006d031  mov     edi, 0Dh
0x18006d036  mov     [rbp+3Fh+var_52], ax
0x18006d03a  mov     [rbp+3Fh+var_40], rax
0x18006d03e  mov     [rbp+3Fh+var_58], di
0x18006d042  mov     [rbp+3Fh+var_48], r8d
0x18006d046  mov     [rbp+3Fh+var_44], 0FFFFFFFFh
0x18006d04d  mov     rax, [rcx]
0x18006d050  mov     rax, [rax+28h]
0x18006d054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d059  xor     r8d, r8d
0x18006d05c  test    eax, eax
0x18006d05e  jnz     short loc_18006D063
0x18006d060  mov     r13d, edi
0x18006d063  mov     rcx, [rsi]
0x18006d066  test    byte ptr [rcx+0B4h], 4
0x18006d06d  jz      short loc_18006D079
0x18006d06f  mov     ebx, 80070005h
0x18006d074  jmp     loc_18006D364
0x18006d079  mov     rcx, [rcx+40h]; this
0x18006d07d  lea     rdx, ?g_rgFETC@@3PAUtagFORMATETC@@A; tagFORMATETC near * g_rgFETC
0x18006d084  mov     [rbp+3Fh+var_80], rdx
0x18006d088  mov     [rbp+3Fh+hMem], r8
0x18006d08c  mov     [rbp+3Fh+var_78], r8
0x18006d090  mov     dword ptr [rbp+3Fh+hWndNewOwner], r8d
0x18006d094  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18006d099  mov     rdi, [rbp+3Fh+arg_28]
0x18006d09d  xor     eax, eax
0x18006d09f  test    rdi, rdi
0x18006d0a2  jz      short loc_18006D0C8
0x18006d0a4  mov     rax, [rdi]
0x18006d0a7  mov     rcx, rdi
0x18006d0aa  mov     rax, [rax+30h]
0x18006d0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
