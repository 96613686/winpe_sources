# CLightDTEngine::PasteDataObjectToRange(IDataObject *,CTxtRange *,ushort,_repastespecial *,IUndoBuilder *,ulong)

- ea: `0x18006e9a8`
- end: `0x18006f135`
- name: `?PasteDataObjectToRange@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@GPEAU_repastespecial@@PEAVIUndoBuilder@@K@Z`
- size: `1933`
- prototype: `__int64 __usercall@<rax>(CLightDTEngine *__hidden this@<rcx>, struct IDataObject *@<rdx>, struct CTxtRange *@<r8>, unsigned __int16@<r9w>, struct _repastespecial *, struct IUndoBuilder *, unsigned int)`
- caller_count: `2`
- callee_count: `20`
- tags: ``

## callers

- `0x18004a97c`
- `0x18005ffa8`

## callees

- `0x1800066b0`
- `0x1800182a0`
- `0x18001f4a0`
- `0x180022ad4`
- `0x18002d8e4`
- `0x180039afc`
- `0x180040b14`
- `0x18004a284`
- `0x18004b234`
- `0x18004bac8`
- `0x1800559d8`
- `0x18006e1f8`
- `0x18006e5fc`
- `0x18006e818`
- `0x18006e9a8`
- `0x180073d88`
- `0x1800927b8`
- `0x180092ed0`
- `0x1800937a8`
- `0x180095010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18006ecf2`
- `KERNEL32!GlobalLock` at `0x18006eeec`
- `KERNEL32!GlobalLock` at `0x18006f040`
- `KERNEL32!GlobalLock` at `0x18006ecf2`
- `KERNEL32!GlobalLock` at `0x18006eeec`
- `KERNEL32!GlobalLock` at `0x18006f040`
- `KERNEL32!GlobalUnlock` at `0x18006ed33`
- `KERNEL32!GlobalUnlock` at `0x18006ed4c`
- `KERNEL32!GlobalUnlock` at `0x18006efde`
- `KERNEL32!GlobalUnlock` at `0x18006f08f`
- `KERNEL32!GlobalUnlock` at `0x18006ed33`
- `KERNEL32!GlobalUnlock` at `0x18006ed4c`
- `KERNEL32!GlobalUnlock` at `0x18006efde`
- `KERNEL32!GlobalUnlock` at `0x18006f08f`
- `USER32!OpenClipboard` at `0x18006ebdd`
- `USER32!OpenClipboard` at `0x18006ebdd`
- `USER32!CloseClipboard` at `0x18006ed64`
- `USER32!CloseClipboard` at `0x18006ed64`
- `USER32!GetClipboardOwner` at `0x18006eab2`
- `USER32!GetClipboardOwner` at `0x18006eab2`
- `USER32!GetClipboardData` at `0x18006ec0c`
- `USER32!GetClipboardData` at `0x18006ec2b`
- `USER32!GetClipboardData` at `0x18006ec4e`
- `USER32!GetClipboardData` at `0x18006ec75`
- `USER32!GetClipboardData` at `0x18006ec94`
- `USER32!GetClipboardData` at `0x18006ecc8`
- `USER32!GetClipboardData` at `0x18006ec0c`
- `USER32!GetClipboardData` at `0x18006ec2b`
- `USER32!GetClipboardData` at `0x18006ec4e`
- `USER32!GetClipboardData` at `0x18006ec75`
- `USER32!GetClipboardData` at `0x18006ec94`
- `USER32!GetClipboardData` at `0x18006ecc8`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::PasteDataObjectToRange(
        CLightDTEngine *this,
        struct IDataObject *a2,
        struct CTxtRange *a3,
        __int16 a4,
        struct _repastespecial *a5,
        struct IUndoBuilder *a6,
        unsigned int a7)
{
  __int16 v10; // ax
  int Clipboard; // ebx
  __int16 v12; // ax
  CTxtEdit *v14; // rcx
  void *v15; // r15
  int v16; // r12d
  int v17; // r8d
  unsigned __int16 *v18; // r10
  __int64 v19; // rdx
  HWND ClipboardOwner; // rdi
  struct IDataObject *v21; // rcx
  unsigned int v23; // r9d
  DWORD_PTR dwParam; // rcx
  int v25; // eax
  unsigned int v26; // r12d
  HANDLE ClipboardData; // rdi
  HANDLE v28; // rax
  void *v29; // rax
  void *v30; // rcx
  HANDLE v31; // rax
  unsigned __int16 *v32; // r9
  CDisplay *v33; // rcx
  struct IUndoBuilder *v34; // rdi
  unsigned int v35; // edi
  struct tagFORMATETC near **i; // rdx
  int v37; // eax
  int v38; // ecx
  char *v39; // rax
  HBITMAP v40; // r12
  int v41; // edi
  unsigned __int16 *v42; // rax
  HBITMAP hMem; // [rsp+40h] [rbp-51h]
  int v44; // [rsp+48h] [rbp-49h]
  struct tagFORMATETC near **v45; // [rsp+50h] [rbp-41h]
  unsigned __int16 *RECallback; // [rsp+58h] [rbp-39h]
  unsigned __int16 *v47; // [rsp+58h] [rbp-39h]
  struct tagSTGMEDIUM v48; // [rsp+60h] [rbp-31h] BYREF
  __int16 v49; // [rsp+78h] [rbp-19h] BYREF
  int v50; // [rsp+7Ah] [rbp-17h]
  __int16 v51; // [rsp+7Eh] [rbp-13h]
  __int64 v52; // [rsp+80h] [rbp-11h]
  int v53; // [rsp+88h] [rbp-9h]
  int v54; // [rsp+8Ch] [rbp-5h]
  __int64 v55; // [rsp+90h] [rbp-1h]
  struct IDataObject *v56; // [rsp+98h] [rbp+7h]
  struct IDataObject *v57; // [rsp+E8h] [rbp+57h] BYREF
  HWND hWndNewOwner; // [rsp+F0h] [rbp+5Fh] BYREF

  v57 = a2;
  if ( !a3 )
    return 2147500037LL;
  if ( (*((_WORD *)CRchTxtPtr::GetPF((struct CTxtRange *)((char *)a3 + 8)) + 1) & 0x4000) != 0 )
  {
    if ( CTxtPtr::GetPrevChar((struct CTxtRange *)((char *)a3 + 24)) == 9
      && CTxtPtr::GetChar((struct CTxtRange *)((char *)a3 + 24)) == 13 )
    {
      v10 = *((_WORD *)a3 + 49);
      if ( (v10 & 2) != 0 )
      {
        Clipboard = -2147467259;
        goto LABEL_18;
      }
      *((_WORD *)a3 + 49) = v10 & 0xFFFE;
      CTxtRange::Advance(a3, -1);
    }
    v12 = *((_WORD *)a3 + 49);
    if ( !((v12 & 2) != 0 ? (v12 & 0x100) == 0 : *((_DWORD *)a3 + 22) == 0) )
      return 2147500037LL;
  }
  v14 = *(CTxtEdit **)this;
  Clipboard = -2147221404;
  v56 = v57;
  v15 = 0;
  v16 = (*((_DWORD *)v14 + 45) >> 19) & 1;
  memset(&v48, 0, sizeof(v48));
  v44 = v16;
  RECallback = (unsigned __int16 *)CTxtEdit::GetRECallback(v14);
  v18 = RECallback;
  if ( !v19 )
  {
    Clipboard = CW32System::OleGetClipboard(&v57);
    if ( Clipboard >= 0 )
    {
LABEL_21:
      v18 = RECallback;
      v17 = 1;
      goto LABEL_22;
    }
    ClipboardOwner = GetClipboardOwner();
    hWndNewOwner = 0;
    if ( ClipboardOwner
      && !(unsigned int)CTxtEdit::TxGetWindow(*(CTxtEdit **)this, &hWndNewOwner)
      && ClipboardOwner == hWndNewOwner )
    {
      v21 = (struct IDataObject *)*((_QWORD *)this + 2);
      v57 = v21;
      if ( !v21 )
        goto LABEL_18;
      ((void (__fastcall *)(struct IDataObject *))v21->lpVtbl->AddRef)(v21);
      goto LABEL_21;
    }
    if ( (unsigned int)CTxtEdit::TxGetWindow(*(CTxtEdit **)this, &hWndNewOwner) || !OpenClipboard(hWndNewOwner) )
      goto LABEL_18;
    CDisplay::Freeze(*(CDisplay **)(*(_QWORD *)this + 64LL));
    if ( !v16 )
    {
      v26 = 0;
      ClipboardData = GetClipboardData((unsigned __int16)g_rgFETC);
      if ( ClipboardData )
        goto LABEL_48;
      v26 = 2;
      ClipboardData = GetClipboardData((unsigned __int16)xmmword_1800A6210);
      if ( ClipboardData )
        goto LABEL_48;
    }
    ClipboardData = GetClipboardData((unsigned __int16)xmmword_1800A61F0);
    v26 = 1;
    if ( ClipboardData || !v44 && (ClipboardData = GetClipboardData(0xDu), v26 = 11, ClipboardData) )
    {
LABEL_48:
      v30 = ClipboardData;
    }
    else
    {
      v28 = GetClipboardData(1u);
      ClipboardData = v28;
      if ( !v28 )
      {
        v31 = GetClipboardData(8u);
        if ( v31 )
          Clipboard = CLightDTEngine::DIBToRange(this, v31, a3, a6);
LABEL_55:
        CDisplay::Thaw(*(CDisplay **)(*(_QWORD *)this + 64LL));
        CloseClipboard();
        if ( Clipboard >= 0 )
          return (unsigned int)Clipboard;
LABEL_18:
        CTxtEdit::Beep(*(CTxtEdit **)this);
        return (unsigned int)Clipboard;
      }
      v29 = CW32System::TextHGlobalAtoW(v28);
      v15 = v29;
      if ( !v29 )
        goto LABEL_51;
      v26 = 12;
      v30 = v29;
    }
    v32 = (unsigned __int16 *)GlobalLock(v30);
    if ( v32 )
    {
      Clipboard = CLightDTEngine::HGlobalToRange(this, v26, ClipboardData, v32, a3, a6);
      goto LABEL_52;
    }
LABEL_51:
    Clipboard = -2147024882;
LABEL_52:
    if ( v15 )
    {
      GlobalUnlock(v15);
      CW32System::GlobalFree(v15);
    }
    else
    {
      GlobalUnlock(ClipboardData);
    }
    goto LABEL_55;
  }
LABEL_22:
  v23 = a7;
  *((_BYTE *)this + 24) = v17;
  if ( ((unsigned __int8)v23 & (unsigned __int8)v17) != 0 || !v18 )
    goto LABEL_60;
  dwParam = 0;
  LOWORD(hWndNewOwner) = a4;
  if ( a5 && a5->dwAspect == 4 )
    dwParam = a5->dwParam;
  v25 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct IDataObject *, HWND *, _QWORD, int, DWORD_PTR))(*(_QWORD *)v18 + 64LL))(
          v18,
          v57,
          &hWndNewOwner,
          v17 & (v23 >> 1),
          v17,
          dwParam);
  Clipboard = 0;
  if ( v25 != 262448 )
    Clipboard = v25;
  if ( Clipboard && Clipboard != -2147467263 )
    goto LABEL_124;
  if ( (_WORD)hWndNewOwner )
  {
    if ( a4 )
    {
      if ( a4 != (_WORD)hWndNewOwner )
      {
        Clipboard = -2147221404;
        goto LABEL_124;
      }
      goto LABEL_59;
    }
    goto LABEL_58;
  }
  if ( !a4 )
LABEL_58:
    a4 = (__int16)hWndNewOwner;
LABEL_59:
  LOWORD(v17) = 1;
LABEL_60:
  if ( a4 == (_WORD)v17 && !v16 )
  {
    v52 = 0;
    v50 = 0;
    v51 = 0;
    v55 = 0;
    v49 = 13;
    v53 = 0;
    v54 = -1;
    if ( !((unsigned int (__fastcall *)(struct IDataObject *, __int16 *))v57->lpVtbl->QueryGetData)(v57, &v49) )
      a4 = 13;
  }
  if ( (*(_BYTE *)(*(_QWORD *)this + 180LL) & 4) != 0 )
  {
    Clipboard = -2147024891;
    goto LABEL_124;
  }
  v33 = *(CDisplay **)(*(_QWORD *)this + 64LL);
  v45 = &g_rgFETC;
  hMem = 0;
  v47 = 0;
  LODWORD(hWndNewOwner) = 0;
  CDisplay::Freeze(v33);
  v34 = a6;
  if ( a6 )
  {
    (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)a6 + 48LL))(a6);
    (**(void (__fastcall ***)(struct IUndoBuilder *, __int64))v34)(v34, 5);
  }
  v35 = 0;
  for ( i = &g_rgFETC; ; v45 = i )
  {
    if ( v35 >= 0x11 )
    {
      v41 = (int)hWndNewOwner;
      goto LABEL_120;
    }
    if ( (!a4 || a4 == *(_WORD *)i)
      && ((*(_BYTE *)(*(_QWORD *)this + 180LL) & 1) != 0 || (*((_BYTE *)&g_rgDOI + 4 * v35) & 2) != 0) )
    {
      break;
    }
LABEL_97:
    ++v35;
    i += 4;
  }
  if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC near **))v57->lpVtbl->QueryGetData)(
         v57,
         i) )
  {
    goto LABEL_96;
  }
  if ( v35 <= 0xE )
  {
    v37 = 21506;
    if ( _bittest(&v37, v35) )
      goto LABEL_80;
  }
  if ( v16 )
  {
    if ( v35 != 11 && v35 )
      goto LABEL_90;
LABEL_96:
    i = v45;
    goto LABEL_97;
  }
  if ( v35 > 0xB )
    goto LABEL_90;
  v38 = 2053;
  if ( !_bittest(&v38, v35) )
    goto LABEL_90;
LABEL_80:
  if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC near **, struct tagSTGMEDIUM *))v57->lpVtbl->GetData)(
         v57,
         v45,
         &v48) )
  {
    goto LABEL_96;
  }
  hMem = v48.hBitmap;
  v39 = (char *)GlobalLock(v48.hBitmap);
  v47 = (unsigned __int16 *)v39;
  if ( !v39 )
  {
    CW32System::ReleaseStgMedium(&v48);
    Clipboard = -2147024882;
    goto LABEL_123;
  }
  if ( (v35 <= 1 || v35 == 10) && !(unsigned int)IsRTF(v39) )
    v35 = 12;
LABEL_90:
  CTxtRange::AdjustEndEOP(a3, 0);
  LODWORD(hWndNewOwner) = 1;
  if ( v35 > 8 )
  {
    if ( v35 != 9 )
    {
      switch ( v35 )
      {
        case 0xAu:
LABEL_118:
          v40 = hMem;
          Clipboard = CLightDTEngine::HGlobalToRange(this, v35, hMem, v47, a3, a6);
          goto LABEL_102;
        case 0xBu:
          v42 = v47;
          v40 = hMem;
          goto LABEL_116;
        case 0xCu:
LABEL_113:
          v40 = hMem;
          v15 = CW32System::TextHGlobalAtoW(hMem);
          v42 = (unsigned __int16 *)GlobalLock(v15);
          if ( !v42 )
          {
            Clipboard = -2147024882;
            goto LABEL_102;
          }
LABEL_116:
          Clipboard = CLightDTEngine::HGlobalToRange(this, v35, 0, v42, a3, a6);
          if ( v15 )
          {
            GlobalUnlock(v15);
            CW32System::GlobalFree(v15);
          }
          goto LABEL_102;
      }
      if ( v35 != 13 )
      {
        if ( v35 != 14 )
        {
          if ( v35 - 15 >= 2 )
            goto LABEL_112;
          goto LABEL_101;
        }
        goto LABEL_113;
      }
    }
LABEL_100:
    Clipboard = CLightDTEngine::CreateOleObjFromDataObj(this, v57, a3, a5, v35, a6);
LABEL_101:
    v40 = hMem;
LABEL_102:
    v41 = (int)hWndNewOwner;
    goto LABEL_103;
  }
  if ( v35 == 8 )
    goto LABEL_100;
  if ( v35 <= 2 )
    goto LABEL_118;
  if ( v35 == 3 || v35 == 4 )
    goto LABEL_100;
  if ( v35 == 5 )
    goto LABEL_96;
  if ( v35 - 6 <= 1 )
    goto LABEL_100;
LABEL_112:
  v40 = hMem;
  v41 = 0;
LABEL_103:
  if ( v40 )
  {
    GlobalUnlock(v40);
    CW32System::ReleaseStgMedium(&v48);
  }
LABEL_120:
  if ( !v41 && v44 )
    Clipboard = -2147221404;
LABEL_123:
  CDisplay::Thaw(*(CDisplay **)(*(_QWORD *)this + 64LL));
LABEL_124:
  if ( !v56 )
    ((void (__fastcall *)(struct IDataObject *))v57->lpVtbl->Release)(v57);
  return (unsigned int)Clipboard;
}

```

## disassembly

```asm
0x18006e9a8  mov     [rsp-8+arg_0], rbx
0x18006e9ad  mov     [rsp-8+arg_8], rdx
0x18006e9b2  push    rbp
0x18006e9b3  push    rsi
0x18006e9b4  push    rdi
0x18006e9b5  push    r12
0x18006e9b7  push    r13
0x18006e9b9  push    r14
0x18006e9bb  push    r15
0x18006e9bd  lea     rbp, [rsp-0Fh]
0x18006e9c2  sub     rsp, 0A0h
0x18006e9c9  xor     edi, edi
0x18006e9cb  movzx   r13d, r9w
0x18006e9cf  mov     r14, r8
0x18006e9d2  mov     rsi, rcx
0x18006e9d5  test    r8, r8
0x18006e9d8  jz      loc_18006F114
0x18006e9de  lea     rcx, [r8+8]; this
0x18006e9e2  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18006e9e7  mov     ecx, 4000h
0x18006e9ec  lea     ebx, [rdi+0Dh]
0x18006e9ef  lea     r15d, [rdi+9]
0x18006e9f3  test    [rax+2], cx
0x18006e9f7  jz      short loc_18006EA5B
0x18006e9f9  lea     rcx, [r14+18h]; this
0x18006e9fd  call    ?GetPrevChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetPrevChar(void)
0x18006ea02  cmp     ax, r15w
0x18006ea06  jnz     short loc_18006EA41
0x18006ea08  lea     rcx, [r14+18h]; this
0x18006ea0c  call    ?GetChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetChar(void)
0x18006ea11  cmp     ax, bx
0x18006ea14  jnz     short loc_18006EA41
0x18006ea16  movzx   eax, word ptr [r14+62h]
0x18006ea1b  test    al, 2
0x18006ea1d  jz      short loc_18006EA29
0x18006ea1f  mov     ebx, 80004005h
0x18006ea24  jmp     loc_18006EAFD
0x18006ea29  mov     ecx, 0FFFEh
0x18006ea2e  or      edx, 0FFFFFFFFh; int
0x18006ea31  and     ax, cx
0x18006ea34  mov     rcx, r14; this
0x18006ea37  mov     [r14+62h], ax
0x18006ea3c  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18006ea41  movzx   eax, word ptr [r14+62h]
0x18006ea46  test    al, 2
0x18006ea48  jz      short loc_18006EA51
0x18006ea4a  test    eax, 100h
0x18006ea4f  jmp     short loc_18006EA55
0x18006ea51  cmp     [r14+58h], edi
0x18006ea55  jnz     loc_18006F114
0x18006ea5b  mov     rcx, [rsi]; this
0x18006ea5e  mov     r8d, 1
0x18006ea64  mov     rdx, [rbp+3Fh+arg_8]
0x18006ea68  xorps   xmm0, xmm0
0x18006ea6b  mov     ebx, 80040064h
0x18006ea70  mov     [rbp+3Fh+var_38], rdx
0x18006ea74  mov     r15, rdi
0x18006ea77  mov     r12d, [rcx+0B4h]
0x18006ea7e  shr     r12d, 13h
0x18006ea82  and     r12d, r8d
0x18006ea85  mov     qword ptr [rbp+3Fh+var_70.tymed], rdi
0x18006ea89  mov     [rbp+3Fh+var_88], r12d
0x18006ea8d  movdqu  xmmword ptr [rbp+3Fh+var_70.8], xmm0
0x18006ea92  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x18006ea97  mov     [rbp+3Fh+var_78], rax
0x18006ea9b  mov     r10, rax
0x18006ea9e  test    rdx, rdx
0x18006eaa1  jnz     short loc_18006EB22
0x18006eaa3  lea     rcx, [rbp+3Fh+arg_8]; struct IDataObject **
0x18006eaa7  call    ?OleGetClipboard@CW32System@@SAJPEAPEAUIDataObject@@@Z; CW32System::OleGetClipboard(IDataObject * *)
0x18006eaac  mov     ebx, eax
0x18006eaae  test    eax, eax
0x18006eab0  jns     short loc_18006EB18
0x18006eab2  call    cs:__imp_GetClipboardOwner
0x18006eab9  nop     dword ptr [rax+rax+00h]
0x18006eabe  mov     rdi, rax
0x18006eac1  xor     eax, eax
0x18006eac3  mov     [rbp+3Fh+hWndNewOwner], rax
0x18006eac7  test    rdi, rdi
0x18006eaca  jz      loc_18006EBC2
0x18006ead0  mov     rcx, [rsi]; this
0x18006ead3  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x18006ead7  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006eadc  test    eax, eax
0x18006eade  jnz     loc_18006EBC2
0x18006eae4  cmp     rdi, [rbp+3Fh+hWndNewOwner]
0x18006eae8  jnz     loc_18006EBC2
0x18006eaee  mov     rcx, [rsi+10h]
0x18006eaf2  xor     edi, edi
0x18006eaf4  mov     [rbp+3Fh+arg_8], rcx
0x18006eaf8  test    rcx, rcx
0x18006eafb  jnz     short loc_18006EB0C
0x18006eafd  mov     rcx, [rsi]; this
0x18006eb00  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18006eb05  mov     eax, ebx
0x18006eb07  jmp     loc_18006F119
0x18006eb0c  mov     rax, [rcx]
0x18006eb0f  mov     rax, [rax+8]
0x18006eb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb18  mov     r10, [rbp+3Fh+var_78]
0x18006eb1c  mov     r8d, 1
0x18006eb22  mov     r9d, [rbp+3Fh+arg_30]
0x18006eb26  mov     [rsi+18h], r8b
0x18006eb2a  test    r8b, r9b
0x18006eb2d  jnz     loc_18006ED8D
0x18006eb33  test    r10, r10
0x18006eb36  jz      loc_18006ED8D
0x18006eb3c  mov     rax, [rbp+3Fh+arg_20]
0x18006eb40  mov     rcx, rdi
0x18006eb43  mov     word ptr [rbp+3Fh+hWndNewOwner], r13w
0x18006eb48  test    rax, rax
0x18006eb4b  jz      short loc_18006EB56
0x18006eb4d  cmp     dword ptr [rax], 4
0x18006eb50  jnz     short loc_18006EB56
0x18006eb52  mov     rcx, [rax+4]
0x18006eb56  mov     rax, [r10]
0x18006eb59  mov     rdx, [rbp+3Fh+arg_8]
0x18006eb5d  mov     [rsp+0D0h+var_A8], rcx
0x18006eb62  mov     rcx, r10
0x18006eb65  shr     r9d, 1
0x18006eb68  mov     rax, [rax+40h]
0x18006eb6c  and     r9d, r8d
0x18006eb6f  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x18006eb74  lea     r8, [rbp+3Fh+hWndNewOwner]
0x18006eb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb7d  cmp     eax, 40130h
0x18006eb82  mov     ebx, edi
0x18006eb84  cmovnz  ebx, eax
0x18006eb87  test    ebx, ebx
0x18006eb89  jz      short loc_18006EB97
0x18006eb8b  cmp     ebx, 80004001h
0x18006eb91  jnz     loc_18006F0F4
0x18006eb97  movzx   eax, word ptr [rbp+3Fh+hWndNewOwner]
0x18006eb9b  test    ax, ax
0x18006eb9e  jz      loc_18006ED7D
0x18006eba4  test    r13w, r13w
0x18006eba8  jz      loc_18006ED83
0x18006ebae  cmp     r13w, ax
0x18006ebb2  jz      loc_18006ED87
0x18006ebb8  mov     ebx, 80040064h
0x18006ebbd  jmp     loc_18006F0F4
0x18006ebc2  mov     rcx, [rsi]; this
0x18006ebc5  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x18006ebc9  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006ebce  xor     r13d, r13d
0x18006ebd1  test    eax, eax
0x18006ebd3  jnz     loc_18006EAFD
0x18006ebd9  mov     rcx, [rbp+3Fh+hWndNewOwner]; hWndNewOwner
0x18006ebdd  call    cs:__imp_OpenClipboard
0x18006ebe4  nop     dword ptr [rax+rax+00h]
0x18006ebe9  test    eax, eax
0x18006ebeb  jz      loc_18006EAFD
0x18006ebf1  mov     rcx, [rsi]
0x18006ebf4  mov     rcx, [rcx+40h]; this
0x18006ebf8  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18006ebfd  test    r12d, r12d
0x18006ec00  jnz     short loc_18006EC47
0x18006ec02  movzx   ecx, word ptr cs:?g_rgFETC@@3PAUtagFORMATETC@@A; uFormat
0x18006ec09  mov     r12d, r13d
0x18006ec0c  call    cs:__imp_GetClipboardData
0x18006ec13  nop     dword ptr [rax+rax+00h]
0x18006ec18  mov     rdi, rax
0x18006ec1b  test    rax, rax
0x18006ec1e  jnz     loc_18006ECEF
0x18006ec24  movzx   ecx, word ptr cs:xmmword_1800A6210; uFormat
0x18006ec2b  call    cs:__imp_GetClipboardData
0x18006ec32  nop     dword ptr [rax+rax+00h]
0x18006ec37  lea     r12d, [r13+2]
0x18006ec3b  mov     rdi, rax
0x18006ec3e  test    rax, rax
0x18006ec41  jnz     loc_18006ECEF
0x18006ec47  movzx   ecx, word ptr cs:xmmword_1800A61F0; uFormat
0x18006ec4e  call    cs:__imp_GetClipboardData
0x18006ec55  nop     dword ptr [rax+rax+00h]
0x18006ec5a  mov     rdi, rax
0x18006ec5d  mov     r12d, 1
0x18006ec63  test    rax, rax
0x18006ec66  jnz     loc_18006ECEF
0x18006ec6c  cmp     [rbp+3Fh+var_88], r13d
0x18006ec70  jnz     short loc_18006EC8F
0x18006ec72  lea     ecx, [rax+0Dh]; uFormat
0x18006ec75  call    cs:__imp_GetClipboardData
0x18006ec7c  nop     dword ptr [rax+rax+00h]
0x18006ec81  mov     rdi, rax
0x18006ec84  mov     r12d, 0Bh
0x18006ec8a  test    rax, rax
0x18006ec8d  jnz     short loc_18006ECEF
0x18006ec8f  mov     ecx, 1; uFormat
0x18006ec94  call    cs:__imp_GetClipboardData
0x18006ec9b  nop     dword ptr [rax+rax+00h]
0x18006eca0  mov     rdi, rax
0x18006eca3  test    rax, rax
0x18006eca6  jz      short loc_18006ECC3
0x18006eca8  mov     rcx, rax; hMem
0x18006ecab  call    ?TextHGlobalAtoW@CW32System@@SAPEAXPEAX@Z; CW32System::TextHGlobalAtoW(void *)
0x18006ecb0  mov     r15, rax
0x18006ecb3  test    rax, rax
0x18006ecb6  jz      short loc_18006ED26
0x18006ecb8  mov     r12d, 0Ch
0x18006ecbe  mov     rcx, rax
0x18006ecc1  jmp     short loc_18006ECF2
0x18006ecc3  mov     ecx, 8; uFormat
0x18006ecc8  call    cs:__imp_GetClipboardData
0x18006eccf  nop     dword ptr [rax+rax+00h]
0x18006ecd4  test    rax, rax
0x18006ecd7  jz      short loc_18006ED58
0x18006ecd9  mov     r9, [rbp+3Fh+arg_28]; struct IUndoBuilder *
0x18006ecdd  mov     r8, r14; struct CTxtRange *
0x18006ece0  mov     rdx, rax; void *
0x18006ece3  mov     rcx, rsi; this
0x18006ece6  call    ?DIBToRange@CLightDTEngine@@IEAAJPEAXPEAVCTxtRange@@PEAVIUndoBuilder@@@Z; CLightDTEngine::DIBToRange(void *,CTxtRange *,IUndoBuilder *)
0x18006eceb  mov     ebx, eax
0x18006eced  jmp     short loc_18006ED58
0x18006ecef  mov     rcx, rdi; hMem
0x18006ecf2  call    cs:__imp_GlobalLock
0x18006ecf9  nop     dword ptr [rax+rax+00h]
0x18006ecfe  mov     r9, rax; unsigned __int16 *
0x18006ed01  test    rax, rax
0x18006ed04  jz      short loc_18006ED26
0x18006ed06  mov     rax, [rbp+3Fh+arg_28]
0x18006ed0a  mov     r8, rdi; void *
0x18006ed0d  mov     [rsp+0D0h+var_A8], rax; struct IUndoBuilder *
0x18006ed12  mov     edx, r12d; unsigned int
0x18006ed15  mov     rcx, rsi; this
0x18006ed18  mov     [rsp+0D0h+var_B0], r14; struct CTxtRange *
0x18006ed1d  call    ?HGlobalToRange@CLightDTEngine@@IEAAJKPEAXPEAGPEAVCTxtRange@@PEAVIUndoBuilder@@@Z; CLightDTEngine::HGlobalToRange(ulong,void *,ushort *,CTxtRange *,IUndoBuilder *)
0x18006ed22  mov     ebx, eax
0x18006ed24  jmp     short loc_18006ED2B
0x18006ed26  mov     ebx, 8007000Eh
0x18006ed2b  test    r15, r15
0x18006ed2e  jz      short loc_18006ED49
0x18006ed30  mov     rcx, r15; hMem
0x18006ed33  call    cs:__imp_GlobalUnlock
0x18006ed3a  nop     dword ptr [rax+rax+00h]
0x18006ed3f  mov     rcx, r15; void *
0x18006ed42  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18006ed47  jmp     short loc_18006ED58
0x18006ed49  mov     rcx, rdi; hMem
0x18006ed4c  call    cs:__imp_GlobalUnlock
0x18006ed53  nop     dword ptr [rax+rax+00h]
0x18006ed58  mov     rcx, [rsi]
0x18006ed5b  mov     rcx, [rcx+40h]; this
0x18006ed5f  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x18006ed64  call    cs:__imp_CloseClipboard
0x18006ed6b  nop     dword ptr [rax+rax+00h]
0x18006ed70  test    ebx, ebx
0x18006ed72  jns     loc_18006EB05
0x18006ed78  jmp     loc_18006EAFD
0x18006ed7d  test    r13w, r13w
0x18006ed81  jnz     short loc_18006ED87
0x18006ed83  movzx   r13d, ax
0x18006ed87  mov     r8d, 1
0x18006ed8d  cmp     r13w, r8w
0x18006ed91  jnz     short loc_18006EDD9
0x18006ed93  test    r12d, r12d
0x18006ed96  jnz     short loc_18006EDD9
0x18006ed98  mov     rcx, [rbp+3Fh+arg_8]
0x18006ed9c  lea     rdx, [rbp+3Fh+var_58]
0x18006eda0  xor     eax, eax
0x18006eda2  mov     [rbp+3Fh+var_50], rdi
0x18006eda6  mov     [rbp+3Fh+var_56], eax
0x18006eda9  mov     r12d, 0Dh
0x18006edaf  mov     [rbp+3Fh+var_52], ax
0x18006edb3  mov     [rbp+3Fh+var_40], rax
0x18006edb7  mov     [rbp+3Fh+var_58], r12w
0x18006edbc  mov     [rbp+3Fh+var_48], edi
0x18006edbf  mov     [rbp+3Fh+var_44], 0FFFFFFFFh
0x18006edc6  mov     rax, [rcx]
0x18006edc9  mov     rax, [rax+28h]
0x18006edcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006edd2  test    eax, eax
0x18006edd4  jnz     short loc_18006EDD9
0x18006edd6  mov     r13d, r12d
0x18006edd9  mov     rcx, [rsi]
0x18006eddc  test    byte ptr [rcx+0B4h], 4
0x18006ede3  jz      short loc_18006EDEF
0x18006ede5  mov     ebx, 80070005h
0x18006edea  jmp     loc_18006F0F4
0x18006edef  mov     rcx, [rcx+40h]; this
0x18006edf3  lea     rdx, ?g_rgFETC@@3PAUtagFORMATETC@@A; tagFORMATETC near * g_rgFETC
0x18006edfa  mov     [rbp+3Fh+var_80], rdx
0x18006edfe  mov     [rbp+3Fh+hMem], rdi
0x18006ee02  mov     [rbp+3Fh+var_78], rdi
0x18006ee06  mov     dword ptr [rbp+3Fh+hWndNewOwner], edi
0x18006ee09  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18006ee0e  mov     rdi, [rbp+3Fh+arg_28]
0x18006ee12  xor     eax, eax
0x18006ee14  test    rdi, rdi
0x18006ee17  jz      short loc_18006EE3D
0x18006ee19  mov     rax, [rdi]
0x18006ee1c  mov     rcx, rdi
0x18006ee1f  mov     rax, [rax+30h]
0x18006ee23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee28  mov     rax, [rdi]
0x18006ee2b  mov     edx, 5
0x18006ee30  mov     rcx, rdi
0x18006ee33  mov     rax, [rax]
0x18006ee36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee3b  xor     eax, eax
0x18006ee3d  mov     edi, eax
  ... truncated ...
```
