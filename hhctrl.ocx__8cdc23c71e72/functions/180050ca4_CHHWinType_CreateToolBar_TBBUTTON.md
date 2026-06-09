# CHHWinType::CreateToolBar(_TBBUTTON *)

- ea: `0x180050ca4`
- end: `0x1800516ff`
- name: `?CreateToolBar@CHHWinType@@QEAAHPEAU_TBBUTTON@@@Z`
- size: `2651`
- prototype: `__int64 __fastcall(CHHWinType *__hidden this, struct _TBBUTTON *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18006eaf4`

## callees

- `0x180001728`
- `0x18000d5bc`
- `0x18001706c`
- `0x180025cf0`
- `0x180025ff4`
- `0x18004f878`
- `0x180050ca4`
- `0x180051928`
- `0x180064990`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!InsertMenuItemW` at `0x18005121d`
- `USER32!InsertMenuItemW` at `0x1800512d9`
- `USER32!InsertMenuItemW` at `0x180051373`
- `USER32!InsertMenuItemW` at `0x1800513aa`
- `USER32!InsertMenuItemW` at `0x18005121d`
- `USER32!InsertMenuItemW` at `0x1800512d9`
- `USER32!InsertMenuItemW` at `0x180051373`
- `USER32!InsertMenuItemW` at `0x1800513aa`
- `USER32!CreatePopupMenu` at `0x180050cda`
- `USER32!CreatePopupMenu` at `0x180050cda`

## pseudocode

```c
__int64 __fastcall CHHWinType::CreateToolBar(CHHWinType *this, struct _TBBUTTON *a2)
{
  HMENU PopupMenu; // rax
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  CTable *v6; // rbx
  bool v7; // cf
  int v8; // edi
  _BYTE *v9; // rax
  int v10; // ebx
  int v11; // r15d
  int v12; // ebx
  int v13; // edi
  int v14; // ebx
  int v15; // edi
  int v16; // ebx
  int v17; // ebx
  bool v18; // al
  int v19; // edi
  unsigned int v20; // ebx
  _BYTE *v21; // rax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  HMENU v24; // rcx
  UINT v25; // edx
  unsigned int v26; // ebx
  int v27; // r13d
  unsigned int v28; // r12d
  const char *v29; // r15
  int v30; // r9d
  int v31; // eax
  HMENU v32; // rcx
  UINT v33; // edx
  const char *v34; // r15
  int v35; // r9d
  int v36; // eax
  HMENU v37; // rcx
  UINT v38; // edx
  HMENU v39; // rcx
  UINT v40; // edx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  unsigned int v44; // eax
  unsigned int v45; // ebx
  __int64 v46; // rax
  __int64 v47; // rax
  unsigned int v48; // eax
  __int64 v49; // rcx
  int v50; // ebx
  int v51; // edi
  int v52; // ebx
  int v53; // edi
  int v54; // ebx
  int v55; // r9d
  int v56; // edi
  WCHAR *v57; // rbx
  __int64 v58; // rax
  const char *v59; // r8
  int v60; // eax
  WCHAR *v61; // rdx
  __int64 v62; // rax
  const char *v63; // r8
  unsigned int v65; // [rsp+20h] [rbp-E0h]
  unsigned int v66; // [rsp+20h] [rbp-E0h]
  MENUITEMINFOW mi; // [rsp+40h] [rbp-C0h] BYREF
  CTable *v68; // [rsp+90h] [rbp-70h]
  WCHAR v69[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v70[504]; // [rsp+A8h] [rbp-58h] BYREF

  PopupMenu = CreatePopupMenu();
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 72);
  *((_QWORD *)this + 84) = PopupMenu;
  if ( v5 )
    (**v5)(v5, 1);
  v68 = (CTable *)operator new(0x70u);
  v6 = v68;
  if ( v68 )
  {
    *((_DWORD *)v68 + 6) = 256;
    *(_QWORD *)v6 = &CTable::`vftable';
    *((_DWORD *)v6 + 7) = 64;
    CTable::InitializeTable(v6);
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 72) = v6;
  memset_0(&mi, 0, sizeof(mi));
  v7 = *((_DWORD *)this + 43) != 0;
  mi.cbSize = 80;
  *(_QWORD *)&mi.fMask = 31;
  v8 = CHHWinType::AddButtonToButtonArray(this, a2, 0, 2, 12, 200, v7 ? 4 : 8);
  if ( CHHWinType::AddButtonToButtonArray(this, a2, v8, 2, 13, 201, *((_DWORD *)this + 43) != 0 ? 8 : 4) )
    ++v8;
  v9 = (_BYTE *)*((_QWORD *)this + 17);
  if ( v9 && *v9 && CHHWinType::AddButtonToButtonArray(this, a2, v8, 2048, 9, 206, 4) )
    ++v8;
  v10 = v8 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v8, 0x400000, 14, 224, 4) )
    v10 = v8;
  v11 = v10 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v10, 0x200000, 8, 223, 4) )
    v11 = v10;
  v12 = v11 + 1;
  if ( g_fBiDi )
  {
    if ( !CHHWinType::AddButtonToButtonArray(this, a2, v11, 8, 0, 209, 4) )
      v12 = v11;
    v13 = v12 + 1;
    if ( !CHHWinType::AddButtonToButtonArray(this, a2, v12, 4, 1, 204, 4) )
      v13 = v12;
  }
  else
  {
    v13 = v11 + 1;
    if ( !CHHWinType::AddButtonToButtonArray(this, a2, v11, 4, 0, 204, 4) )
      v13 = v11;
    if ( CHHWinType::AddButtonToButtonArray(this, a2, v13, 8, 1, 209, 4) )
      ++v13;
  }
  v14 = v13 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v13, 16, 2, 202, 4) )
    v14 = v13;
  v15 = v14 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v14, 32, 3, 203, 4) )
    v15 = v14;
  if ( *((_QWORD *)this + 20) )
  {
    v16 = v15 + 1;
    if ( !CHHWinType::AddButtonToButtonArray(this, a2, v15, 64, 4, 205, 4) )
      v16 = v15;
    v15 = v16 + 1;
    if ( !CHHWinType::AddButtonToButtonArray(this, a2, v16, 128, 14, 211, 4) )
      v15 = v16;
    if ( CHHWinType::AddButtonToButtonArray(this, a2, v15, 256, 8, 212, 4) )
      ++v15;
  }
  v17 = v15 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v15, 0x100000, 16, 222, 4) )
    v17 = v15;
  v18 = CHHWinType::AddButtonToButtonArray(this, a2, v17, 0x2000, 7, 207, 4);
  mi.cbSize = 80;
  v19 = v17 + 1;
  *(_QWORD *)&mi.fMask = 19;
  mi.fState = 0;
  if ( !v18 )
    v19 = v17;
  memset(&mi.hSubMenu, 0, 32);
  v20 = 1;
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0xC9u, 1063, 0);
  if ( (*((_DWORD *)this + 42) & 0x800) != 0 )
  {
    v21 = (_BYTE *)*((_QWORD *)this + 17);
    if ( v21 )
    {
      if ( *v21 )
      {
        v20 = 2;
        CHHWinType::FillAndInsertMenuItem(this, &mi, 0xCEu, 1069, 1u);
      }
    }
  }
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0xCCu, 1064, v20);
  v65 = v20 + 1;
  v22 = v20 + 2;
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0xD1u, 1065, v65);
  if ( *((_QWORD *)this + 20) )
  {
    v23 = v22++;
    CHHWinType::FillAndInsertMenuItem(this, &mi, 0xCDu, 1066, v23);
  }
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0xCAu, 1067, v22);
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0xCBu, 1068, v22 + 1);
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0x177Cu, 1084, v22 + 2);
  v24 = (HMENU)*((_QWORD *)this + 84);
  v25 = v22 + 3;
  mi.fMask = 16;
  mi.fType = 2048;
  v26 = v22 + 4;
  InsertMenuItemW(v24, v25, 1, &mi);
  *(_QWORD *)&mi.fMask = 19;
  v27 = 0;
  CLanguage::_Init((CLanguage *)&off_18008B4C0);
  v28 = CodePageFromLCID((unsigned __int16)word_18008B4C8);
  if ( (*((_DWORD *)this + 42) & 0x40000) != 0 )
  {
    v29 = (const char *)*((_QWORD *)this + 27);
    if ( v29 )
    {
      wcscpy(v69, L"&1 ");
      memset_0(v70, 0, sizeof(v70));
      v31 = HHMultiByteToWideChar(v28, 1u, v29, v30, &v69[3], 253);
      if ( v31 )
      {
        mi.wID = 218;
        mi.dwTypeData = v69;
        v32 = (HMENU)*((_QWORD *)this + 84);
        v33 = v26;
        mi.cch = v31 + 2;
        ++v26;
        InsertMenuItemW(v32, v33, 1, &mi);
        v27 = 1;
      }
    }
  }
  if ( (*((_DWORD *)this + 42) & 0x80000) != 0 )
  {
    v34 = (const char *)*((_QWORD *)this + 28);
    if ( v34 )
    {
      wcscpy(v69, L"&2 ");
      memset_0(v70, 0, sizeof(v70));
      v36 = HHMultiByteToWideChar(v28, 1u, v34, v35, &v69[3], 253);
      if ( v36 )
      {
        mi.wID = 219;
        mi.dwTypeData = v69;
        v37 = (HMENU)*((_QWORD *)this + 84);
        v38 = v26++;
        mi.cch = v36 + 2;
        InsertMenuItemW(v37, v38, 1, &mi);
LABEL_56:
        v39 = (HMENU)*((_QWORD *)this + 84);
        v40 = v26;
        mi.fMask = 16;
        ++v26;
        mi.fType = 2048;
        InsertMenuItemW(v39, v40, 1, &mi);
        *(_QWORD *)&mi.fMask = 19;
        goto LABEL_57;
      }
    }
  }
  if ( v27 )
    goto LABEL_56;
LABEL_57:
  v41 = *((_QWORD *)this + 76);
  if ( v41 )
  {
    v42 = *(_QWORD *)(v41 + 48);
    if ( v42 )
    {
      v43 = *(_QWORD *)(v42 + 8);
      if ( v43 )
      {
        if ( *(_DWORD *)(v43 + 32) - 1 > 0 )
        {
          v44 = v26++;
          CHHWinType::FillAndInsertMenuItem(this, &mi, 0xDDu, 1070, v44);
        }
      }
    }
  }
  v66 = v26;
  v45 = v26 + 1;
  CHHWinType::FillAndInsertMenuItem(this, &mi, 0xCFu, 1071, v66);
  v46 = *((_QWORD *)this + 76);
  if ( v46 )
  {
    v47 = *(_QWORD *)(v46 + 128);
    if ( v47 )
    {
      if ( *(_QWORD *)(v47 + 24) )
      {
        v48 = v45++;
        CHHWinType::FillAndInsertMenuItem(this, &mi, 0xDCu, 1073, v48);
      }
    }
  }
  if ( v45 && CHHWinType::AddButtonToButtonArray(this, a2, v19, 4096, 10, 208, 4) )
  {
    v49 = v19++;
    a2[v49].fsStyle = 8;
    a2[v49].dwData = *((_QWORD *)this + 84);
  }
  v50 = v19 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v19, 512, 11, 210, 4) )
    v50 = v19;
  v51 = v50 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v50, 1024, 15, 213, 4) )
    v51 = v50;
  v52 = v51 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v51, 0x4000, 16, 214, 4) )
    v52 = v51;
  v53 = v52 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v52, 0x8000, 5, 215, 4) )
    v53 = v52;
  v54 = v53 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v53, 0x10000, 19, 216, 4) )
    v54 = v53;
  v56 = v54 + 1;
  if ( !CHHWinType::AddButtonToButtonArray(this, a2, v54, 0x20000, 6, 217, 4) )
    v56 = v54;
  if ( (*((_DWORD *)this + 5) & 0x10000) == 0 )
  {
    v57 = (WCHAR *)&psz;
    if ( (*((_DWORD *)this + 42) & 0x40000) != 0 )
    {
      v58 = v56;
      a2[v58].iBitmap = 17;
      a2[v58].idCommand = 218;
      a2[v58].fsState = 4;
      a2[v58].iString = v56;
      v59 = (const char *)*((_QWORD *)this + 27);
      if ( !v59 || (v60 = HHMultiByteToWideChar(v28, 1u, v59, v55, v69, 256), v61 = v69, !v60) )
        v61 = (WCHAR *)&psz;
      CTable::AddString(*((CTable **)this + 72), v61);
      ++v56;
    }
    if ( (*((_DWORD *)this + 42) & 0x80000) != 0 )
    {
      v62 = v56;
      a2[v62].iBitmap = 18;
      a2[v62].idCommand = 219;
      a2[v62].fsState = 4;
      a2[v62].iString = v56;
      v63 = (const char *)*((_QWORD *)this + 28);
      if ( v63 && (unsigned int)HHMultiByteToWideChar(v28, 1u, v63, v55, v69, 256) )
        v57 = v69;
      CTable::AddString(*((CTable **)this + 72), v57);
      ++v56;
    }
  }
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x180050ca4  mov     [rsp-8+arg_10], rbx
0x180050ca9  push    rbp
0x180050caa  push    rsi
0x180050cab  push    rdi
0x180050cac  push    r12
0x180050cae  push    r13
0x180050cb0  push    r14
0x180050cb2  push    r15
0x180050cb4  lea     rbp, [rsp-1B0h]
0x180050cbc  sub     rsp, 2B0h
0x180050cc3  mov     rax, cs:__security_cookie
0x180050cca  xor     rax, rsp
0x180050ccd  mov     [rbp+1E0h+var_40], rax
0x180050cd4  mov     r14, rdx
0x180050cd7  mov     rsi, rcx
0x180050cda  call    cs:__imp_CreatePopupMenu
0x180050ce0  mov     rcx, [rsi+240h]
0x180050ce7  xor     r12d, r12d
0x180050cea  mov     [rsi+2A0h], rax
0x180050cf1  mov     r13d, 1
0x180050cf7  test    rcx, rcx
0x180050cfa  jz      short loc_180050D0A
0x180050cfc  mov     rax, [rcx]
0x180050cff  mov     edx, r13d
0x180050d02  mov     rax, [rax]
0x180050d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d0a  mov     ecx, 70h ; 'p'; Size
0x180050d0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050d14  mov     [rbp+1E0h+var_250], rax
0x180050d18  mov     rbx, rax
0x180050d1b  test    rax, rax
0x180050d1e  jz      short loc_180050D42
0x180050d20  lea     rax, ??_7CTable@@6B@; const CTable::`vftable'
0x180050d27  mov     dword ptr [rbx+18h], 100h
0x180050d2e  mov     rcx, rbx; this
0x180050d31  mov     [rbx], rax
0x180050d34  mov     dword ptr [rbx+1Ch], 40h ; '@'
0x180050d3b  call    ?InitializeTable@CTable@@IEAAXXZ; CTable::InitializeTable(void)
0x180050d40  jmp     short loc_180050D45
0x180050d42  mov     rbx, r12
0x180050d45  mov     [rsi+240h], rbx
0x180050d4c  lea     rcx, [rsp+2E0h+mi]; void *
0x180050d51  mov     ebx, 50h ; 'P'
0x180050d56  xor     edx, edx; Val
0x180050d58  mov     r8d, ebx; Size
0x180050d5b  call    memset_0
0x180050d60  mov     eax, [rsi+0ACh]
0x180050d66  mov     rdx, r14; struct _TBBUTTON *
0x180050d69  neg     eax
0x180050d6b  mov     [rsp+2E0h+mi.cbSize], ebx
0x180050d6f  mov     ebx, 2
0x180050d74  mov     qword ptr [rsp+2E0h+mi.fMask], 1Fh
0x180050d7d  sbb     cl, cl
0x180050d7f  mov     r9d, ebx; int
0x180050d82  and     cl, 0FCh
0x180050d85  xor     r8d, r8d; int
0x180050d88  add     cl, 8
0x180050d8b  mov     [rsp+2E0h+var_2B0], cl; char
0x180050d8f  mov     rcx, rsi; this
0x180050d92  mov     [rsp+2E0h+var_2B8], 0C8h; int
0x180050d9a  mov     dword ptr [rsp+2E0h+var_2C0], 0Ch; int
0x180050da2  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050da7  movzx   edi, al
0x180050daa  mov     r9d, ebx; int
0x180050dad  mov     eax, [rsi+0ACh]
0x180050db3  mov     r8d, edi; int
0x180050db6  neg     eax
0x180050db8  mov     rdx, r14; struct _TBBUTTON *
0x180050dbb  sbb     cl, cl
0x180050dbd  and     cl, 4
0x180050dc0  add     cl, 4
0x180050dc3  mov     [rsp+2E0h+var_2B0], cl; char
0x180050dc7  mov     rcx, rsi; this
0x180050dca  mov     [rsp+2E0h+var_2B8], 0C9h; int
0x180050dd2  mov     dword ptr [rsp+2E0h+var_2C0], 0Dh; int
0x180050dda  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050ddf  test    al, al
0x180050de1  jz      short loc_180050DE5
0x180050de3  inc     edi
0x180050de5  mov     rax, [rsi+88h]
0x180050dec  test    rax, rax
0x180050def  jz      short loc_180050E26
0x180050df1  cmp     [rax], r12b
0x180050df4  jz      short loc_180050E26
0x180050df6  mov     [rsp+2E0h+var_2B0], 4; char
0x180050dfb  mov     r9d, 800h; int
0x180050e01  mov     [rsp+2E0h+var_2B8], 0CEh; int
0x180050e09  mov     r8d, edi; int
0x180050e0c  mov     rdx, r14; struct _TBBUTTON *
0x180050e0f  mov     dword ptr [rsp+2E0h+var_2C0], 9; int
0x180050e17  mov     rcx, rsi; this
0x180050e1a  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050e1f  test    al, al
0x180050e21  jz      short loc_180050E26
0x180050e23  add     edi, r13d
0x180050e26  mov     [rsp+2E0h+var_2B0], 4; char
0x180050e2b  mov     r9d, 400000h; int
0x180050e31  mov     [rsp+2E0h+var_2B8], 0E0h; int
0x180050e39  mov     r8d, edi; int
0x180050e3c  mov     rdx, r14; struct _TBBUTTON *
0x180050e3f  mov     dword ptr [rsp+2E0h+var_2C0], 0Eh; int
0x180050e47  mov     rcx, rsi; this
0x180050e4a  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050e4f  test    al, al
0x180050e51  mov     [rsp+2E0h+var_2B0], 4; char
0x180050e56  lea     ebx, [rdi+1]
0x180050e59  mov     [rsp+2E0h+var_2B8], 0DFh; int
0x180050e61  cmovz   ebx, edi
0x180050e64  mov     dword ptr [rsp+2E0h+var_2C0], 8; int
0x180050e6c  mov     r8d, ebx; int
0x180050e6f  mov     r9d, 200000h; int
0x180050e75  mov     rdx, r14; struct _TBBUTTON *
0x180050e78  mov     rcx, rsi; this
0x180050e7b  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050e80  test    al, al
0x180050e82  mov     [rsp+2E0h+var_2B0], 4; char
0x180050e87  lea     r15d, [rbx+1]
0x180050e8b  mov     rdx, r14; struct _TBBUTTON *
0x180050e8e  cmovz   r15d, ebx
0x180050e92  mov     rcx, rsi; this
0x180050e95  cmp     cs:?g_fBiDi@@3HA, r12d; int g_fBiDi
0x180050e9c  mov     r8d, r15d; int
0x180050e9f  lea     ebx, [r15+1]
0x180050ea3  jz      short loc_180050EF3
0x180050ea5  mov     [rsp+2E0h+var_2B8], 0D1h; int
0x180050ead  mov     r9d, 8; int
0x180050eb3  mov     dword ptr [rsp+2E0h+var_2C0], r12d; int
0x180050eb8  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050ebd  test    al, al
0x180050ebf  mov     [rsp+2E0h+var_2B0], 4; char
0x180050ec4  mov     [rsp+2E0h+var_2B8], 0CCh; int
0x180050ecc  mov     r9d, 4; int
0x180050ed2  cmovz   ebx, r15d
0x180050ed6  mov     dword ptr [rsp+2E0h+var_2C0], r13d; int
0x180050edb  mov     r8d, ebx; int
0x180050ede  mov     rdx, r14; struct _TBBUTTON *
0x180050ee1  mov     rcx, rsi; this
0x180050ee4  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050ee9  test    al, al
0x180050eeb  lea     edi, [rbx+1]
0x180050eee  cmovz   edi, ebx
0x180050ef1  jmp     short loc_180050F3F
0x180050ef3  mov     [rsp+2E0h+var_2B8], 0CCh; int
0x180050efb  mov     r9d, 4; int
0x180050f01  mov     dword ptr [rsp+2E0h+var_2C0], r12d; int
0x180050f06  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050f0b  test    al, al
0x180050f0d  mov     [rsp+2E0h+var_2B0], 4; char
0x180050f12  mov     edi, ebx
0x180050f14  mov     [rsp+2E0h+var_2B8], 0D1h; int
0x180050f1c  cmovz   edi, r15d
0x180050f20  mov     dword ptr [rsp+2E0h+var_2C0], r13d; int
0x180050f25  mov     r8d, edi; int
0x180050f28  mov     r9d, 8; int
0x180050f2e  mov     rdx, r14; struct _TBBUTTON *
0x180050f31  mov     rcx, rsi; this
0x180050f34  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050f39  test    al, al
0x180050f3b  jz      short loc_180050F3F
0x180050f3d  inc     edi
0x180050f3f  mov     r15d, 2
0x180050f45  mov     [rsp+2E0h+var_2B0], 4; char
0x180050f4a  mov     [rsp+2E0h+var_2B8], 0CAh; int
0x180050f52  mov     r8d, edi; int
0x180050f55  mov     rdx, r14; struct _TBBUTTON *
0x180050f58  mov     dword ptr [rsp+2E0h+var_2C0], r15d; int
0x180050f5d  mov     rcx, rsi; this
0x180050f60  lea     r9d, [r15+0Eh]; int
0x180050f64  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050f69  test    al, al
0x180050f6b  mov     [rsp+2E0h+var_2B0], 4; char
0x180050f70  lea     ebx, [rdi+1]
0x180050f73  mov     [rsp+2E0h+var_2B8], 0CBh; int
0x180050f7b  cmovz   ebx, edi
0x180050f7e  mov     dword ptr [rsp+2E0h+var_2C0], 3; int
0x180050f86  mov     r8d, ebx; int
0x180050f89  lea     r9d, [r15+1Eh]; int
0x180050f8d  mov     rdx, r14; struct _TBBUTTON *
0x180050f90  mov     rcx, rsi; this
0x180050f93  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050f98  test    al, al
0x180050f9a  lea     edi, [rbx+1]
0x180050f9d  cmovz   edi, ebx
0x180050fa0  cmp     [rsi+0A0h], r12
0x180050fa7  jz      loc_18005103A
0x180050fad  mov     [rsp+2E0h+var_2B0], 4; char
0x180050fb2  lea     r9d, [r15+3Eh]; int
0x180050fb6  mov     [rsp+2E0h+var_2B8], 0CDh; int
0x180050fbe  mov     r8d, edi; int
0x180050fc1  mov     rdx, r14; struct _TBBUTTON *
0x180050fc4  mov     dword ptr [rsp+2E0h+var_2C0], 4; int
0x180050fcc  mov     rcx, rsi; this
0x180050fcf  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180050fd4  test    al, al
0x180050fd6  mov     [rsp+2E0h+var_2B0], 4; char
0x180050fdb  lea     ebx, [rdi+1]
0x180050fde  mov     [rsp+2E0h+var_2B8], 0D3h; int
0x180050fe6  cmovz   ebx, edi
0x180050fe9  mov     dword ptr [rsp+2E0h+var_2C0], 0Eh; int
0x180050ff1  mov     r8d, ebx; int
0x180050ff4  lea     r9d, [r15+7Eh]; int
0x180050ff8  mov     rdx, r14; struct _TBBUTTON *
0x180050ffb  mov     rcx, rsi; this
0x180050ffe  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180051003  test    al, al
0x180051005  mov     [rsp+2E0h+var_2B0], 4; char
0x18005100a  lea     edi, [rbx+1]
0x18005100d  mov     [rsp+2E0h+var_2B8], 0D4h; int
0x180051015  cmovz   edi, ebx
0x180051018  mov     dword ptr [rsp+2E0h+var_2C0], 8; int
0x180051020  mov     r8d, edi; int
0x180051023  mov     r9d, 100h; int
0x180051029  mov     rdx, r14; struct _TBBUTTON *
0x18005102c  mov     rcx, rsi; this
0x18005102f  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180051034  test    al, al
0x180051036  jz      short loc_18005103A
0x180051038  inc     edi
0x18005103a  mov     [rsp+2E0h+var_2B0], 4; char
0x18005103f  mov     r9d, 100000h; int
0x180051045  mov     [rsp+2E0h+var_2B8], 0DEh; int
0x18005104d  mov     r8d, edi; int
0x180051050  mov     rdx, r14; struct _TBBUTTON *
0x180051053  mov     dword ptr [rsp+2E0h+var_2C0], 10h; int
0x18005105b  mov     rcx, rsi; this
0x18005105e  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180051063  test    al, al
0x180051065  mov     [rsp+2E0h+var_2B0], 4; char
0x18005106a  lea     ebx, [rdi+1]
0x18005106d  mov     [rsp+2E0h+var_2B8], 0CFh; int
0x180051075  cmovz   ebx, edi
0x180051078  mov     dword ptr [rsp+2E0h+var_2C0], 7; int
0x180051080  mov     r8d, ebx; int
0x180051083  mov     r9d, 2000h; int
0x180051089  mov     rdx, r14; struct _TBBUTTON *
0x18005108c  mov     rcx, rsi; this
0x18005108f  call    ?AddButtonToButtonArray@CHHWinType@@AEAA_NPEAU_TBBUTTON@@HHHHE@Z; CHHWinType::AddButtonToButtonArray(_TBBUTTON *,int,int,int,int,uchar)
0x180051094  test    al, al
0x180051096  mov     [rsp+2E0h+mi.cbSize], 50h ; 'P'
0x18005109e  lea     edi, [rbx+1]
0x1800510a1  mov     qword ptr [rsp+2E0h+mi.fMask], 13h
0x1800510aa  xorps   xmm0, xmm0
0x1800510ad  mov     [rsp+2E0h+mi.fState], r12d
0x1800510b2  cmovz   edi, ebx
0x1800510b5  mov     [rsp+2E0h+mi.hSubMenu], r12
0x1800510ba  mov     r9d, 427h; int
0x1800510c0  movdqa  xmmword ptr [rsp+2E0h+mi.hbmpChecked], xmm0
0x1800510c6  mov     r8d, 0C9h; unsigned int
0x1800510cc  mov     [rsp+2E0h+mi.dwItemData], r12
0x1800510d1  lea     rdx, [rsp+2E0h+mi]; struct tagMENUITEMINFOW *
0x1800510d6  mov     dword ptr [rsp+2E0h+var_2C0], r12d; unsigned int
0x1800510db  mov     rcx, rsi; this
0x1800510de  mov     ebx, r13d
0x1800510e1  call    ?FillAndInsertMenuItem@CHHWinType@@AEAAXAEAUtagMENUITEMINFOW@@IHI@Z; CHHWinType::FillAndInsertMenuItem(tagMENUITEMINFOW &,uint,int,uint)
0x1800510e6  test    dword ptr [rsi+0A8h], 800h
0x1800510f0  jz      short loc_180051124
0x1800510f2  mov     rax, [rsi+88h]
0x1800510f9  test    rax, rax
0x1800510fc  jz      short loc_180051124
0x1800510fe  cmp     [rax], r12b
0x180051101  jz      short loc_180051124
0x180051103  mov     r9d, 42Dh; int
0x180051109  mov     dword ptr [rsp+2E0h+var_2C0], r13d; unsigned int
0x18005110e  mov     r8d, 0CEh; unsigned int
0x180051114  lea     rdx, [rsp+2E0h+mi]; struct tagMENUITEMINFOW *
0x180051119  mov     rcx, rsi; this
0x18005111c  mov     ebx, r15d
0x18005111f  call    ?FillAndInsertMenuItem@CHHWinType@@AEAAXAEAUtagMENUITEMINFOW@@IHI@Z; CHHWinType::FillAndInsertMenuItem(tagMENUITEMINFOW &,uint,int,uint)
0x180051124  mov     eax, ebx
0x180051126  lea     rdx, [rsp+2E0h+mi]; struct tagMENUITEMINFOW *
0x18005112b  mov     r9d, 428h; int
0x180051131  mov     dword ptr [rsp+2E0h+var_2C0], eax; unsigned int
0x180051135  mov     r8d, 0CCh; unsigned int
0x18005113b  mov     rcx, rsi; this
0x18005113e  add     ebx, r13d
0x180051141  call    ?FillAndInsertMenuItem@CHHWinType@@AEAAXAEAUtagMENUITEMINFOW@@IHI@Z; CHHWinType::FillAndInsertMenuItem(tagMENUITEMINFOW &,uint,int,uint)
0x180051146  mov     eax, ebx
0x180051148  lea     rdx, [rsp+2E0h+mi]; struct tagMENUITEMINFOW *
0x18005114d  mov     r9d, 429h; int
0x180051153  mov     dword ptr [rsp+2E0h+var_2C0], eax; unsigned int
0x180051157  mov     r8d, 0D1h; unsigned int
0x18005115d  mov     rcx, rsi; this
0x180051160  add     ebx, r13d
0x180051163  call    ?FillAndInsertMenuItem@CHHWinType@@AEAAXAEAUtagMENUITEMINFOW@@IHI@Z; CHHWinType::FillAndInsertMenuItem(tagMENUITEMINFOW &,uint,int,uint)
0x180051168  cmp     [rsi+0A0h], r12
0x18005116f  jz      short loc_180051193
0x180051171  mov     eax, ebx
0x180051173  lea     rdx, [rsp+2E0h+mi]; struct tagMENUITEMINFOW *
0x180051178  add     ebx, r13d
0x18005117b  mov     dword ptr [rsp+2E0h+var_2C0], eax; unsigned int
0x18005117f  mov     r9d, 42Ah; int
0x180051185  mov     r8d, 0CDh; unsigned int
0x18005118b  mov     rcx, rsi; this
0x18005118e  call    ?FillAndInsertMenuItem@CHHWinType@@AEAAXAEAUtagMENUITEMINFOW@@IHI@Z; CHHWinType::FillAndInsertMenuItem(tagMENUITEMINFOW &,uint,int,uint)
0x180051193  mov     eax, ebx
0x180051195  lea     rdx, [rsp+2E0h+mi]; struct tagMENUITEMINFOW *
0x18005119a  mov     r9d, 42Bh; int
0x1800511a0  mov     dword ptr [rsp+2E0h+var_2C0], eax; unsigned int
0x1800511a4  mov     r8d, 0CAh; unsigned int
0x1800511aa  mov     rcx, rsi; this
  ... truncated ...
```
