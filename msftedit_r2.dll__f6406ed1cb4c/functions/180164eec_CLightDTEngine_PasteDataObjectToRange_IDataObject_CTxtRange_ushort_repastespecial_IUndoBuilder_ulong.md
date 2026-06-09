# CLightDTEngine::PasteDataObjectToRange(IDataObject *,CTxtRange *,ushort,_repastespecial *,IUndoBuilder *,ulong)

- ea: `0x180164eec`
- end: `0x180165964`
- name: `?PasteDataObjectToRange@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@GPEAU_repastespecial@@PEAVIUndoBuilder@@K@Z`
- size: `2680`
- prototype: `__int64 __fastcall(CLightDTEngine *this, struct IDataObject *, struct CTxtRange *, unsigned __int16, struct _repastespecial *, struct IUndoBuilder *, unsigned int)`
- caller_count: `2`
- callee_count: `24`
- tags: ``

## callers

- `0x18012f45c`
- `0x18016d994`

## callees

- `0x18001b1e0`
- `0x18004b2c8`
- `0x18008a47c`
- `0x18008cd48`
- `0x180096704`
- `0x18009caac`
- `0x1800b2c1c`
- `0x1800b6418`
- `0x1800f4b1c`
- `0x1800f902c`
- `0x1801018a8`
- `0x18012c68c`
- `0x18012eb24`
- `0x180135018`
- `0x180149110`
- `0x1801494f8`
- `0x18014afe4`
- `0x180164af0`
- `0x180164eec`
- `0x18016596c`
- `0x18016c5f0`
- `0x18017a350`
- `0x180209568`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180165878`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801658b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180165878`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801658b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180165527`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180165798`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180165527`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180165798`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180165262`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180165262`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180165234`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180165234`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801650b8`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801650b8`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::PasteDataObjectToRange(
        CLightDTEngine *this,
        struct IDataObject *a2,
        struct CTxtRange *a3,
        unsigned __int16 a4,
        struct _repastespecial *a5,
        struct IUndoBuilder *a6,
        unsigned int a7)
{
  unsigned __int64 v7; // r11
  int v11; // r14d
  bool v12; // cf
  __int64 v13; // rsi
  struct IRichEditOleCallback *RECallback; // rax
  __int64 v15; // rdx
  struct IUndoBuilder *v16; // r8
  struct IDataObject *v17; // r10
  __int64 v18; // r11
  bool v19; // zf
  int v20; // eax
  int inserted; // edi
  int v22; // eax
  __int64 v23; // rdx
  struct _repastespecial *v24; // r12
  bool v25; // r14
  HWND ClipboardOwner; // rax
  HWND v27; // r14
  int Window; // eax
  __int64 v29; // rdx
  struct IDataObject *v30; // rcx
  unsigned int v32; // esi
  struct IUndoBuilder *dwParam; // rcx
  int v34; // eax
  int v35; // r14d
  CTxtEdit *v36; // rcx
  struct IUndoBuilder *v37; // r12
  int v38; // esi
  struct IDataObject *v39; // r14
  __int64 v40; // r8
  CTxtEdit *v41; // rcx
  HBITMAP v42; // r13
  CTxtEdit *v43; // rcx
  struct tagFORMATETC *v44; // rdx
  int v45; // eax
  int v46; // eax
  HBITMAP hBitmap; // r14
  int v48; // eax
  bool v49; // r8
  struct _repastespecial *v50; // r9
  unsigned __int64 v51; // rcx
  HBITMAP v52; // r8
  unsigned __int16 *v53; // rax
  int OleObjFromDataObj; // eax
  char v55; // si
  __int16 *v56; // rcx
  struct IUndoBuilder *v57; // [rsp+30h] [rbp-89h]
  int v58; // [rsp+58h] [rbp-61h] BYREF
  CDataTransferObj *v59; // [rsp+60h] [rbp-59h] BYREF
  char *v60; // [rsp+68h] [rbp-51h]
  HBITMAP v61; // [rsp+70h] [rbp-49h]
  struct tagFORMATETC *v62; // [rsp+78h] [rbp-41h]
  __int128 v63; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int64 v64; // [rsp+90h] [rbp-29h]
  __int64 v65; // [rsp+98h] [rbp-21h]
  struct tagSTGMEDIUM v66; // [rsp+A0h] [rbp-19h] BYREF
  struct IRichEditOleCallback *v67; // [rsp+B8h] [rbp-1h]
  __int64 v68; // [rsp+C0h] [rbp+7h]
  HWND hWndNewOwner; // [rsp+108h] [rbp+4Fh] BYREF
  struct IDataObject *v70; // [rsp+110h] [rbp+57h] BYREF
  struct CTxtRange *v71; // [rsp+118h] [rbp+5Fh]

  v71 = a3;
  v70 = a2;
  v7 = *(_QWORD *)this;
  v11 = *(_DWORD *)(*(_QWORD *)this + 176LL) >> 19;
  memset(&v66, 0, sizeof(v66));
  v12 = *(_WORD *)(v7 + 56) != 0;
  v58 = v11;
  v13 = ((v7 & -(__int64)v12) + 48) & -(__int64)((v7 & -(__int64)v12) != 0);
  RECallback = CTxtEdit::GetRECallback((CTxtEdit *)v7);
  v19 = (*(_BYTE *)(v18 + 176) & 4) == 0;
  v67 = RECallback;
  if ( !v19 )
    return 2147942405LL;
  v68 = v15;
  if ( *(_DWORD *)(v18 + 280) >= (int)v16 || *((_BYTE *)this + 28) != (_BYTE)v16 )
    goto LABEL_6;
  v64 = 2048;
  v63 = 0;
  v20 = CTxtEdit::TxNotify((CTxtEdit *)v18, 0x800u, &v63);
  v16 = 0;
  if ( !v20 )
    return 2147942405LL;
  v17 = v70;
  *((_BYTE *)this + 28) = 1;
LABEL_6:
  inserted = -2147221404;
  if ( v17 )
    goto LABEL_30;
  if ( !*((_QWORD *)this + 2) )
    goto LABEL_12;
  v22 = (*(__int64 (__fastcall **)(struct IClipboard *))(*(_QWORD *)g_pIClipboard + 40LL))(g_pIClipboard);
  v16 = 0;
  if ( !v22 && !*((_BYTE *)this + 24) )
  {
    v70 = (struct IDataObject *)*((_QWORD *)this + 2);
    ((void (__fastcall *)(struct IDataObject *, __int64, _QWORD))v70->lpVtbl->AddRef)(v70, v23, 0);
    v16 = 0;
  }
  v17 = v70;
  if ( v70 )
  {
LABEL_30:
    v24 = a5;
  }
  else
  {
LABEL_12:
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
    v24 = a5;
    v57 = (struct IUndoBuilder *)&v70;
    inserted = (*(__int64 (__fastcall **)(struct IClipboard *, struct CTxtRange *, _QWORD, struct _repastespecial *, unsigned int))(*(_QWORD *)g_pIClipboard + 16LL))(
                 g_pIClipboard,
                 a3,
                 a4,
                 a5,
                 a7);
    v25 = (*(_DWORD *)(*(_QWORD *)this + 280LL) & 0x2000000) != 0;
    (*(void (**)(void))(**(_QWORD **)this + 16LL))();
    if ( inserted == 1 )
      return 0;
    v16 = 0;
    if ( v25 )
      return 0;
    if ( *((_BYTE *)this + 28) )
    {
      if ( v13 )
        *(_DWORD *)(v13 + 12) |= 0x800u;
      *((_BYTE *)this + 28) = 0;
    }
    if ( inserted >= 0 )
    {
      v17 = v70;
      if ( v70 )
      {
        LOBYTE(v11) = v58;
        goto LABEL_31;
      }
      return 0;
    }
    ClipboardOwner = GetClipboardOwner();
    v16 = 0;
    v27 = ClipboardOwner;
    hWndNewOwner = 0;
    if ( ClipboardOwner
      && (Window = CTxtEdit::TxGetWindow(*(CTxtEdit **)this, &hWndNewOwner), v16 = 0, !Window)
      && v27 == hWndNewOwner )
    {
      v30 = (struct IDataObject *)*((_QWORD *)this + 2);
      v70 = v30;
      if ( !v30 )
        goto LABEL_25;
      ((void (__fastcall *)(struct IDataObject *, __int64, _QWORD))v30->lpVtbl->AddRef)(v30, v29, 0);
      v17 = v70;
      v16 = 0;
      LOBYTE(v11) = v58;
    }
    else
    {
      LOBYTE(v11) = v58;
      v17 = 0;
      v70 = 0;
    }
  }
LABEL_31:
  LOBYTE(hWndNewOwner) = (_BYTE)v16;
  if ( *((_BYTE *)this + 28) != (_BYTE)v16 )
  {
    if ( v13 )
    {
      *(_DWORD *)(v13 + 12) |= 0x800u;
      v17 = v70;
    }
    *((_BYTE *)this + 28) = (_BYTE)v16;
  }
  v32 = a7;
  *((_BYTE *)this + 25) = 1;
  if ( v17 && (v32 & 1) == 0 && v67 )
  {
    LOWORD(v58) = a4;
    dwParam = v16;
    if ( v24 && v24->dwAspect == 4 )
      dwParam = (struct IUndoBuilder *)v24->dwParam;
    v57 = dwParam;
    v34 = ((__int64 (__fastcall *)(struct IRichEditOleCallback *, struct IDataObject *, int *, _QWORD, int))v67->lpVtbl->QueryAcceptData)(
            v67,
            v17,
            &v58,
            (v32 >> 1) & 1,
            1);
    v16 = 0;
    inserted = 0;
    if ( v34 != 262448 )
      inserted = v34;
    if ( inserted && inserted != -2147467263 )
      goto LABEL_169;
    if ( (_WORD)v58 )
    {
      if ( a4 )
      {
        if ( a4 != (_WORD)v58 )
        {
          inserted = -2147221404;
          goto LABEL_169;
        }
        goto LABEL_51;
      }
    }
    else if ( a4 )
    {
LABEL_51:
      v17 = v70;
      goto LABEL_52;
    }
    a4 = v58;
    goto LABEL_51;
  }
LABEL_52:
  v35 = v11 & 1;
  v58 = v35;
  if ( !v17 )
  {
    v36 = *(CTxtEdit **)this;
    hWndNewOwner = (HWND)v16;
    if ( !(unsigned int)CTxtEdit::TxGetWindow(v36, &hWndNewOwner) && OpenClipboard(hWndNewOwner) )
    {
      inserted = CLightDTEngine::PasteFromClipboard(this, a3, a4, a6, v32, v35);
      CloseClipboard();
    }
    if ( inserted >= 0 )
      return (unsigned int)inserted;
LABEL_25:
    CTxtEdit::Beep(*(CTxtEdit **)this);
    return (unsigned int)inserted;
  }
  if ( a4 == 1 )
  {
    if ( v35 || (*(_WORD *)(*(_QWORD *)this + 276LL) & 0x400) != 0 )
      goto LABEL_68;
    LOWORD(v63) = 13;
    *(_DWORD *)((char *)&v63 + 2) = 0;
    WORD3(v63) = 0;
    v65 = 0;
    *((_QWORD *)&v63 + 1) = v16;
    v64 = (unsigned int)v16 | 0xFFFFFFFF00000000uLL;
    if ( ((unsigned int (__fastcall *)(struct IDataObject *, __int128 *))v17->lpVtbl->QueryGetData)(v17, &v63) )
    {
      LODWORD(v65) = 1;
      if ( ((unsigned int (__fastcall *)(struct IDataObject *, __int128 *))v70->lpVtbl->QueryGetData)(v70, &v63) )
        goto LABEL_68;
      a4 = 13;
    }
    else
    {
      a4 = 13;
    }
  }
  else if ( a4 != 13 )
  {
    goto LABEL_68;
  }
  if ( (*(_WORD *)(*(_QWORD *)this + 276LL) & 0x400) != 0 )
    a4 = 1;
LABEL_68:
  CDisplay::Freeze(*(CDisplay **)(*(_QWORD *)this + 136LL));
  v37 = a6;
  v38 = 0;
  if ( a6 )
  {
    (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)a6 + 48LL))(a6);
    (**(void (__fastcall ***)(struct IUndoBuilder *, __int64))v37)(v37, 5);
  }
  if ( !a4 )
  {
    v39 = v70;
    if ( v70 != *((struct IDataObject **)this + 2) || *((_BYTE *)this + 24) )
      goto LABEL_77;
    v59 = 0;
    if ( !((__int64 (__fastcall *)(struct IDataObject *, GUID *, CDataTransferObj **))v70->lpVtbl->QueryInterface)(
            v70,
            &IID_IRichEditDO,
            &v59)
      && v59 )
    {
      CTxtRange::AdjustEndEOP(a3, 0, v40);
      inserted = CDataTransferObj::InsertIntoRange(v59, a3, v37);
      (*(void (__fastcall **)(CDataTransferObj *))(*(_QWORD *)v59 + 16LL))(v59);
      goto LABEL_168;
    }
  }
  v39 = v70;
LABEL_77:
  v41 = *(CTxtEdit **)this;
  v62 = &g_rgFETC;
  v42 = 0;
  LODWORD(v59) = 0;
  v61 = 0;
  v60 = 0;
  if ( (unsigned int)CTxtEdit::IsPlaceHolderStorySelected(v41) )
  {
    v43 = *(CTxtEdit **)this;
    LOBYTE(hWndNewOwner) = 1;
    CTxtEdit::OnSelectStory(v43, 0xFFFFFFFFFFFFFFFFuLL, 0);
    v39 = v70;
  }
  v44 = &g_rgFETC;
  while ( v38 < 26 )
  {
    if ( (!a4 || a4 == v44->cfFormat)
      && ((unsigned int)CRchTxtPtr::IsRich((struct CTxtRange *)((char *)v71 + 8))
       && (*(_DWORD *)(*(_QWORD *)this + 176LL) & 0x10) == 0
       || (*((_BYTE *)&g_rgDOI + 4 * v38) & 2) != 0) )
    {
      if ( ((unsigned int (__fastcall *)(struct IDataObject *))v39->lpVtbl->QueryGetData)(v39)
        || v38 == 17 && (*(_WORD *)(*(_QWORD *)this + 276LL) & 0x400) != 0
        || (*(_DWORD *)(*(_QWORD *)this + 180LL) & 0x4000) != 0 && ((unsigned int)(v38 - 8) <= 2 || v38 == 13) )
      {
        goto LABEL_135;
      }
      if ( (unsigned int)v38 <= 0x14 )
      {
        v45 = 1376260;
        if ( _bittest(&v45, v38) )
          goto LABEL_100;
      }
      v46 = v38 - 1;
      if ( v58 )
      {
        if ( (v46 & 0xFFFFFFED) == 0 && v38 != 19 || (unsigned int)(v38 - 22) <= 2 || !v38 )
          goto LABEL_135;
      }
      else if ( (v46 & 0xFFFFFFED) == 0 && v38 != 19
             || (unsigned int)(v38 - 22) <= 2
             || (unsigned int)(v38 - 8) <= 2
             || !v38 )
      {
LABEL_100:
        if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC *, struct tagSTGMEDIUM *))v70->lpVtbl->GetData)(
               v70,
               v62,
               &v66) )
        {
          goto LABEL_135;
        }
        hBitmap = v66.hBitmap;
        v61 = v66.hBitmap;
        v60 = (char *)GlobalLock(v66.hBitmap);
        if ( !v60 )
        {
          CW32System::ReleaseStgMedium(&v66);
          inserted = -2147024882;
          goto LABEL_168;
        }
        if ( (unsigned int)(v38 - 1) <= 1 || v38 == 16 )
        {
          v48 = CW32System::GlobalSize(hBitmap);
          if ( !IsRTF(v60, v48, v49) )
          {
            v38 = 18;
            goto LABEL_114;
          }
        }
        if ( !v38 && *(_QWORD *)(*(_QWORD *)this + 552LL) )
          goto LABEL_135;
LABEL_114:
        CTxtRange::AdjustEndEOP(v71, 0, 0);
        LODWORD(v59) = 1;
        if ( v38 > 12 )
        {
          if ( v38 > 19 )
          {
            if ( v38 == 20 )
            {
LABEL_147:
              v42 = (HBITMAP)CW32System::TextHGlobalAtoW(hBitmap);
              v53 = (unsigned __int16 *)GlobalLock(v42);
              if ( v53 )
              {
                v52 = v42;
                goto LABEL_160;
              }
              inserted = -2147024882;
LABEL_162:
              v55 = v38 + 1;
            }
            else
            {
              if ( v38 == 21 )
                goto LABEL_162;
              if ( v38 == 22 || (unsigned int)(v38 - 23) < 2 )
                goto LABEL_157;
LABEL_156:
              LODWORD(v59) = 0;
              v55 = 0;
            }
            *(_WORD *)(*(_QWORD *)this + 278LL) ^= ((unsigned __int8)*(_WORD *)(*(_QWORD *)this + 278LL)
                                                  ^ (unsigned __int8)(4 * v55))
                                                 & 0x7C;
            if ( hBitmap )
            {
              GlobalUnlock(hBitmap);
              CW32System::ReleaseStgMedium(&v66);
            }
            break;
          }
          if ( v38 == 19 )
          {
            if ( (*(_DWORD *)(*(_QWORD *)this + 180LL) & 0x4000) != 0 )
            {
              OleObjFromDataObj = CLightDTEngine::CreateOleObjFromDataObj(this, v70, v71, a5, 19, v37);
              goto LABEL_150;
            }
            v66.tymed = 1;
            inserted = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, struct tagSTGMEDIUM *))v70->lpVtbl->GetData)(
                         v70,
                         &word_1802E1C00,
                         &v66);
            if ( !inserted
              && !CTxtRange::InsertImageHelper(v71, 0, 0, 0, 0, *(const unsigned __int16 **)v66.hBitmap, 0, 0, v37) )
            {
              goto LABEL_162;
            }
            goto LABEL_132;
          }
          v52 = hBitmap;
          v51 = (unsigned int)(v38 - 13);
          if ( v38 != 13 )
          {
            if ( v38 != 14 )
            {
              if ( v38 != 15 )
              {
                if ( v38 != 16 )
                {
                  if ( v38 != 17 )
                    goto LABEL_147;
                  v53 = (unsigned __int16 *)v60;
LABEL_160:
                  inserted = CLightDTEngine::HGlobalToRange((CTxtEdit **)this, v38, v52, v53, v71, v37, a7);
                  if ( v42 )
                  {
                    GlobalUnlock(v42);
                    CW32System::GlobalFree(v42);
                  }
                  goto LABEL_162;
                }
LABEL_157:
                OleObjFromDataObj = CLightDTEngine::HGlobalToRange(
                                      (CTxtEdit **)this,
                                      v38,
                                      hBitmap,
                                      (unsigned __int16 *)v60,
                                      v71,
                                      v37,
                                      a7);
LABEL_150:
                inserted = OleObjFromDataObj;
                goto LABEL_162;
              }
              goto LABEL_132;
            }
            v51 = *(_DWORD *)(*(_QWORD *)this + 180LL) >> 14;
            if ( (*(_DWORD *)(*(_QWORD *)this + 180LL) & 0x4000) != 0 )
            {
              OleObjFromDataObj = CLightDTEngine::CreateOleObjFromDataObj(this, v70, v71, a5, 14, v37);
              goto LABEL_150;
            }
          }
        }
        else
        {
          if ( v38 == 12 )
            goto LABEL_132;
          if ( v38 <= 6 )
          {
            if ( v38 != 6 )
            {
              if ( (unsigned int)v38 < 4 )
                goto LABEL_157;
              LODWORD(v51) = v38 - 4;
              if ( v38 != 4 )
                goto LABEL_120;
LABEL_132:
              if ( (*(_BYTE *)(*(_QWORD *)this + 276LL) & 0x40) == 0 )
              {
                if ( v67 )
                {
                  inserted = CLightDTEngine::CreateOleObjFromDataObj(this, v70, v71, a5, v38, v37);
                  if ( inserted >= 0 )
                    goto LABEL_162;
                }
              }
            }
LABEL_135:
            v39 = v70;
            v44 = v62;
            goto LABEL_136;
          }
          if ( v38 == 7 )
            goto LABEL_132;
          v51 = (unsigned int)(v38 - 8);
          if ( v38 != 8 )
          {
            v51 = (unsigned int)(v38 - 9);
            if ( v38 != 9 )
            {
              v51 = (unsigned int)(v38 - 10);
              if ( v38 != 10 )
              {
LABEL_120:
                if ( (_DWORD)v51 != 1 )
                  goto LABEL_156;
                goto LABEL_132;
              }
            }
          }
        }
        inserted = CLightDTEngine::CreateImageFromDataObj((CLightDTEngine *)v51, v70, v71, v50, v38, v57);
        if ( inserted >= 0 )
          goto LABEL_162;
        goto LABEL_132;
      }
      hBitmap = v61;
      goto LABEL_114;
    }
LABEL_136:
    ++v38;
    v62 = ++v44;
  }
  if ( !(_DWORD)v59 && v58 )
    inserted = -2147221404;
LABEL_168:
  CDisplay::Thaw(*(CDisplay **)(*(_QWORD *)this + 136LL));
LABEL_169:
  if ( !v68 && v70 )
    ((void (__fastcall *)(struct IDataObject *))v70->lpVtbl->Release)(v70);
  if ( (_BYTE)hWndNewOwner )
  {
    if ( !(unsigned int)CTxtEdit::GetAdjustedTextLength(*(CTxtEdit **)this, 0) )
      CTxtEdit::OnSelectStory((CTxtEdit *)v56, v56[165], 0);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180164eec  mov     rax, rsp
0x180164eef  mov     [rax+20h], rbx
0x180164ef3  mov     [rax+18h], r8
0x180164ef7  mov     [rax+10h], rdx
0x180164efb  push    rbp
0x180164efc  push    rsi
0x180164efd  push    rdi
0x180164efe  push    r12
0x180164f00  push    r13
0x180164f02  push    r14
0x180164f04  push    r15
0x180164f06  lea     rbp, [rax-47h]
0x180164f0a  sub     rsp, 0C0h
0x180164f11  mov     r11, [rcx]
0x180164f14  mov     rbx, rcx
0x180164f17  mov     r13, r8
0x180164f1a  xorps   xmm0, xmm0
0x180164f1d  xor     r8d, r8d
0x180164f20  movzx   r15d, r9w
0x180164f24  mov     r10, rdx
0x180164f27  mov     r14d, [r11+0B0h]
0x180164f2e  shr     r14d, 13h
0x180164f32  mov     qword ptr [rbp+3Fh+var_58.tymed], r8
0x180164f36  movdqu  xmmword ptr [rbp+3Fh+var_58.8], xmm0
0x180164f3b  movzx   eax, word ptr [r11+38h]
0x180164f40  neg     ax
0x180164f43  mov     [rbp+3Fh+var_A0], r14d
0x180164f47  sbb     rcx, rcx
0x180164f4a  and     rcx, r11
0x180164f4d  lea     rax, [rcx+30h]
0x180164f51  neg     rcx
0x180164f54  mov     rcx, r11; this
0x180164f57  sbb     rsi, rsi
0x180164f5a  and     rsi, rax
0x180164f5d  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x180164f62  test    byte ptr [r11+0B0h], 4
0x180164f6a  mov     [rbp+3Fh+var_40], rax
0x180164f6e  jnz     loc_180165943
0x180164f74  mov     ecx, 800h
0x180164f79  mov     [rbp+3Fh+var_38], rdx
0x180164f7d  cmp     [r11+118h], r8d
0x180164f84  jge     short loc_180164FBA
0x180164f86  cmp     [rbx+1Ch], r8b
0x180164f8a  jnz     short loc_180164FBA
0x180164f8c  xor     eax, eax
0x180164f8e  lea     r8, [rbp+3Fh+var_78]; void *
0x180164f92  mov     [rbp+3Fh+var_68], rax
0x180164f96  mov     edx, ecx; unsigned int
0x180164f98  mov     dword ptr [rbp+3Fh+var_68], ecx
0x180164f9b  mov     rcx, r11; this
0x180164f9e  movups  [rbp+3Fh+var_78], xmm0
0x180164fa2  call    ?TxNotify@CTxtEdit@@QEAAJKPEAX@Z; CTxtEdit::TxNotify(ulong,void *)
0x180164fa7  xor     r8d, r8d
0x180164faa  test    eax, eax
0x180164fac  jz      loc_180165943
0x180164fb2  mov     r10, [rbp+3Fh+arg_8]
0x180164fb6  mov     byte ptr [rbx+1Ch], 1
0x180164fba  mov     edi, 80040064h
0x180164fbf  test    r10, r10
0x180164fc2  jnz     loc_180165135
0x180164fc8  mov     rdx, [rbx+10h]
0x180164fcc  test    rdx, rdx
0x180164fcf  jz      short loc_180165015
0x180164fd1  mov     rcx, cs:?g_pIClipboard@@3PEAVIClipboard@@EA; IClipboard * g_pIClipboard
0x180164fd8  mov     rax, [rcx]
0x180164fdb  mov     rax, [rax+28h]
0x180164fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164fe4  xor     r8d, r8d
0x180164fe7  test    eax, eax
0x180164fe9  jnz     short loc_180165008
0x180164feb  cmp     [rbx+18h], r8b
0x180164fef  jnz     short loc_180165008
0x180164ff1  mov     rcx, [rbx+10h]
0x180164ff5  mov     [rbp+3Fh+arg_8], rcx
0x180164ff9  mov     rax, [rcx]
0x180164ffc  mov     rax, [rax+8]
0x180165000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165005  xor     r8d, r8d
0x180165008  mov     r10, [rbp+3Fh+arg_8]
0x18016500c  test    r10, r10
0x18016500f  jnz     loc_180165135
0x180165015  mov     rcx, [rbx]
0x180165018  mov     rax, [rcx]
0x18016501b  mov     rax, [rax+8]
0x18016501f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165024  mov     rcx, cs:?g_pIClipboard@@3PEAVIClipboard@@EA; IClipboard * g_pIClipboard
0x18016502b  lea     rdx, [rbp+3Fh+arg_8]
0x18016502f  mov     r12, [rbp+3Fh+arg_20]
0x180165033  movzx   r8d, r15w
0x180165037  mov     [rsp+0F0h+var_C8], rdx
0x18016503c  mov     r9, r12
0x18016503f  mov     edx, [rbp+3Fh+arg_30]
0x180165042  mov     rax, [rcx]
0x180165045  mov     dword ptr [rsp+0F0h+var_D0], edx
0x180165049  mov     rdx, r13
0x18016504c  mov     rax, [rax+10h]
0x180165050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165055  mov     rcx, [rbx]
0x180165058  mov     edi, eax
0x18016505a  mov     rdx, [rcx]
0x18016505d  mov     r14d, [rcx+118h]
0x180165064  shr     r14d, 19h
0x180165068  and     r14b, 1
0x18016506c  mov     rax, [rdx+10h]
0x180165070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165075  mov     edx, 1
0x18016507a  cmp     edi, edx
0x18016507c  jz      loc_18016512E
0x180165082  xor     r8d, r8d
0x180165085  test    r14b, r14b
0x180165088  jnz     loc_18016512E
0x18016508e  cmp     [rbx+1Ch], r8b
0x180165092  jz      short loc_1801650A2
0x180165094  test    rsi, rsi
0x180165097  jz      short loc_18016509E
0x180165099  bts     dword ptr [rsi+0Ch], 0Bh
0x18016509e  mov     [rbx+1Ch], r8b
0x1801650a2  test    edi, edi
0x1801650a4  js      short loc_1801650B8
0x1801650a6  mov     r10, [rbp+3Fh+arg_8]
0x1801650aa  test    r10, r10
0x1801650ad  jz      short loc_18016512E
0x1801650af  mov     r14d, [rbp+3Fh+var_A0]
0x1801650b3  jmp     loc_18016513E
0x1801650b8  call    cs:__imp_GetClipboardOwner
0x1801650bf  nop     dword ptr [rax+rax+00h]
0x1801650c4  xor     r8d, r8d
0x1801650c7  mov     r14, rax
0x1801650ca  mov     [rbp+3Fh+hWndNewOwner], r8
0x1801650ce  test    rax, rax
0x1801650d1  jz      short loc_180165121
0x1801650d3  mov     rcx, [rbx]; this
0x1801650d6  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x1801650da  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x1801650df  xor     r8d, r8d
0x1801650e2  test    eax, eax
0x1801650e4  jnz     short loc_180165121
0x1801650e6  cmp     r14, [rbp+3Fh+hWndNewOwner]
0x1801650ea  jnz     short loc_180165121
0x1801650ec  mov     rcx, [rbx+10h]
0x1801650f0  mov     [rbp+3Fh+arg_8], rcx
0x1801650f4  test    rcx, rcx
0x1801650f7  jnz     short loc_180165108
0x1801650f9  mov     rcx, [rbx]; this
0x1801650fc  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x180165101  mov     eax, edi
0x180165103  jmp     loc_180165948
0x180165108  mov     rax, [rcx]
0x18016510b  mov     rax, [rax+8]
0x18016510f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165114  mov     r10, [rbp+3Fh+arg_8]
0x180165118  xor     r8d, r8d
0x18016511b  mov     r14d, [rbp+3Fh+var_A0]
0x18016511f  jmp     short loc_180165139
0x180165121  mov     r14d, [rbp+3Fh+var_A0]
0x180165125  mov     r10, r8
0x180165128  mov     [rbp+3Fh+arg_8], r8
0x18016512c  jmp     short loc_180165139
0x18016512e  xor     eax, eax
0x180165130  jmp     loc_180165948
0x180165135  mov     r12, [rbp+3Fh+arg_20]
0x180165139  mov     edx, 1
0x18016513e  mov     byte ptr [rbp+3Fh+hWndNewOwner], r8b
0x180165142  cmp     [rbx+1Ch], r8b
0x180165146  jz      short loc_18016515A
0x180165148  test    rsi, rsi
0x18016514b  jz      short loc_180165156
0x18016514d  bts     dword ptr [rsi+0Ch], 0Bh
0x180165152  mov     r10, [rbp+3Fh+arg_8]
0x180165156  mov     [rbx+1Ch], r8b
0x18016515a  mov     esi, [rbp+3Fh+arg_30]
0x18016515d  mov     [rbx+19h], dl
0x180165160  test    r10, r10
0x180165163  jz      loc_180165210
0x180165169  test    dl, sil
0x18016516c  jnz     loc_180165210
0x180165172  mov     r11, [rbp+3Fh+var_40]
0x180165176  test    r11, r11
0x180165179  jz      loc_180165210
0x18016517f  mov     word ptr [rbp+3Fh+var_A0], r15w
0x180165184  mov     rcx, r8
0x180165187  test    r12, r12
0x18016518a  jz      short loc_180165198
0x18016518c  cmp     dword ptr [r12], 4
0x180165191  jnz     short loc_180165198
0x180165193  mov     rcx, [r12+4]
0x180165198  mov     rax, [r11]
0x18016519b  lea     r8, [rbp+3Fh+var_A0]
0x18016519f  mov     [rsp+0F0h+var_C8], rcx; struct IUndoBuilder *
0x1801651a4  mov     r9d, esi
0x1801651a7  shr     r9d, 1
0x1801651aa  mov     rcx, r11
0x1801651ad  and     r9d, edx
0x1801651b0  mov     dword ptr [rsp+0F0h+var_D0], edx
0x1801651b4  mov     rax, [rax+40h]
0x1801651b8  mov     rdx, r10
0x1801651bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801651c0  xor     r8d, r8d
0x1801651c3  cmp     eax, 40130h
0x1801651c8  mov     edi, r8d
0x1801651cb  cmovnz  edi, eax
0x1801651ce  test    edi, edi
0x1801651d0  jz      short loc_1801651DE
0x1801651d2  cmp     edi, 80004001h
0x1801651d8  jnz     loc_1801658F4
0x1801651de  movzx   eax, word ptr [rbp+3Fh+var_A0]
0x1801651e2  test    ax, ax
0x1801651e5  jz      short loc_1801651FD
0x1801651e7  test    r15w, r15w
0x1801651eb  jz      short loc_180165203
0x1801651ed  cmp     r15w, ax
0x1801651f1  jz      short loc_180165207
0x1801651f3  mov     edi, 80040064h
0x1801651f8  jmp     loc_1801658F4
0x1801651fd  test    r15w, r15w
0x180165201  jnz     short loc_180165207
0x180165203  movzx   r15d, ax
0x180165207  mov     r10, [rbp+3Fh+arg_8]
0x18016520b  mov     edx, 1
0x180165210  and     r14d, edx
0x180165213  mov     [rbp+3Fh+var_A0], r14d
0x180165217  test    r10, r10
0x18016521a  jnz     short loc_18016527B
0x18016521c  mov     rcx, [rbx]; this
0x18016521f  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x180165223  mov     [rbp+3Fh+hWndNewOwner], r8
0x180165227  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18016522c  test    eax, eax
0x18016522e  jnz     short loc_18016526E
0x180165230  mov     rcx, [rbp+3Fh+hWndNewOwner]; hWndNewOwner
0x180165234  call    cs:__imp_OpenClipboard
0x18016523b  nop     dword ptr [rax+rax+00h]
0x180165240  test    eax, eax
0x180165242  jz      short loc_18016526E
0x180165244  mov     r9, [rbp+3Fh+arg_28]; struct IUndoBuilder *
0x180165248  movzx   r8d, r15w; unsigned __int16
0x18016524c  mov     dword ptr [rsp+0F0h+var_C8], r14d; int
0x180165251  mov     rdx, r13; struct CTxtRange *
0x180165254  mov     rcx, rbx; this
0x180165257  mov     dword ptr [rsp+0F0h+var_D0], esi; unsigned int
0x18016525b  call    ?PasteFromClipboard@CLightDTEngine@@AEAAJPEAVCTxtRange@@GPEAVIUndoBuilder@@KH@Z; CLightDTEngine::PasteFromClipboard(CTxtRange *,ushort,IUndoBuilder *,ulong,int)
0x180165260  mov     edi, eax
0x180165262  call    cs:__imp_CloseClipboard
0x180165269  nop     dword ptr [rax+rax+00h]
0x18016526e  test    edi, edi
0x180165270  jns     loc_180165101
0x180165276  jmp     loc_1801650F9
0x18016527b  mov     esi, 0Dh
0x180165280  mov     r12d, 400h
0x180165286  cmp     r15w, dx
0x18016528a  jnz     short loc_180165308
0x18016528c  test    r14d, r14d
0x18016528f  jnz     loc_18016531F
0x180165295  mov     rax, [rbx]
0x180165298  test    [rax+114h], r12w
0x1801652a0  jnz     short loc_18016531F
0x1801652a2  xor     eax, eax
0x1801652a4  mov     word ptr [rbp+3Fh+var_78], si
0x1801652a8  mov     dword ptr [rbp+3Fh+var_78+2], eax
0x1801652ab  lea     rdx, [rbp+3Fh+var_78]
0x1801652af  mov     word ptr [rbp+3Fh+var_78+6], ax
0x1801652b3  mov     rcx, r10
0x1801652b6  mov     [rbp+3Fh+var_60], rax
0x1801652ba  mov     qword ptr [rbp+3Fh+var_78+8], r8
0x1801652be  mov     dword ptr [rbp+3Fh+var_68], r8d
0x1801652c2  mov     dword ptr [rbp+3Fh+var_68+4], 0FFFFFFFFh
0x1801652c9  mov     rax, [r10]
0x1801652cc  mov     rax, [rax+28h]
0x1801652d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801652d5  test    eax, eax
0x1801652d7  jnz     short loc_1801652E3
0x1801652d9  mov     r15d, esi
0x1801652dc  mov     edx, 1
0x1801652e1  jmp     short loc_18016530E
0x1801652e3  mov     rcx, [rbp+3Fh+arg_8]
0x1801652e7  lea     rdx, [rbp+3Fh+var_78]
0x1801652eb  mov     dword ptr [rbp+3Fh+var_60], 1
0x1801652f2  mov     rax, [rcx]
0x1801652f5  mov     rax, [rax+28h]
0x1801652f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801652fe  test    eax, eax
0x180165300  jnz     short loc_18016531F
0x180165302  movzx   r15d, si
0x180165306  jmp     short loc_1801652DC
0x180165308  cmp     r15w, si
0x18016530c  jnz     short loc_18016531F
0x18016530e  mov     rax, [rbx]
0x180165311  test    [rax+114h], r12w
0x180165319  jz      short loc_18016531F
0x18016531b  movzx   r15d, dx
0x18016531f  mov     rcx, [rbx]
0x180165322  mov     rcx, [rcx+88h]; this
0x180165329  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18016532e  mov     r12, [rbp+3Fh+arg_28]
0x180165332  xor     esi, esi
0x180165334  test    r12, r12
0x180165337  jz      short loc_18016535B
0x180165339  mov     rax, [r12]
0x18016533d  mov     rcx, r12
0x180165340  mov     rax, [rax+30h]
  ... truncated ...
```
