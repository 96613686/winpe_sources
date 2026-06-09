# DetailsView::OnCmdDelete(void)

- ea: `0x18000c8c4`
- end: `0x18000d130`
- name: `?OnCmdDelete@DetailsView@@AEAA_JXZ`
- size: `2156`
- prototype: `__int64 __fastcall(DetailsView *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000de10`

## callees

- `0x180006eb4`
- `0x180006ec0`
- `0x180006fa0`
- `0x180007698`
- `0x180008aac`
- `0x18000c8c4`
- `0x1800101b4`
- `0x180010758`
- `0x1800110fc`
- `0x180011160`
- `0x18001127c`
- `0x1800112e8`
- `0x180011d08`
- `0x180011e00`
- `0x18001583c`
- `0x180015870`
- `0x180015b60`
- `0x180015bd0`
- `0x180015cf0`
- `0x180015f60`
- `0x180016b5c`
- `0x180019d24`
- `0x180019dd0`
- `0x180019ee0`
- `0x18001a468`
- `0x18001ab24`
- `0x18001abb8`
- `0x18001ad0c`
- `0x18001c210`
- `0x18001ce34`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000ca8b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000ca8b`
- `USER32!EnableWindow` at `0x18000c9ff`
- `USER32!EnableWindow` at `0x18000d0d2`
- `USER32!EnableWindow` at `0x18000c9ff`
- `USER32!EnableWindow` at `0x18000d0d2`
- `USER32!SendMessageW` at `0x18000c8ef`
- `USER32!SendMessageW` at `0x18000c909`
- `USER32!SendMessageW` at `0x18000c997`
- `USER32!SendMessageW` at `0x18000ca4c`
- `USER32!SendMessageW` at `0x18000cac1`
- `USER32!SendMessageW` at `0x18000cc85`
- `USER32!SendMessageW` at `0x18000cf9f`
- `USER32!SendMessageW` at `0x18000d0b8`
- `USER32!SendMessageW` at `0x18000c8ef`
- `USER32!SendMessageW` at `0x18000c909`
- `USER32!SendMessageW` at `0x18000c997`
- `USER32!SendMessageW` at `0x18000ca4c`
- `USER32!SendMessageW` at `0x18000cac1`
- `USER32!SendMessageW` at `0x18000cc85`
- `USER32!SendMessageW` at `0x18000cf9f`
- `USER32!SendMessageW` at `0x18000d0b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DetailsView::OnCmdDelete(DetailsView *this)
{
  unsigned int v2; // r8d
  unsigned int v3; // eax
  HWND v4; // rbx
  signed int v5; // edi
  HWND v6; // rdi
  signed int v7; // r14d
  unsigned int v8; // eax
  struct IDiskQuotaUser *v9; // rsi
  unsigned int v10; // r8d
  HWND v11; // rcx
  int v12; // eax
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  PointerList *v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  int v19; // r12d
  int v20; // esi
  __int64 v21; // r14
  __int64 v22; // rsi
  struct IDiskQuotaUser *v23; // rsi
  int v24; // eax
  bool v25; // zf
  struct IDiskQuotaUser v26; // rax
  _QWORD *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  PointerList *v30; // rcx
  signed int v31; // r14d
  signed int i; // r12d
  unsigned int v33; // r8d
  unsigned int v34; // r8d
  struct IDiskQuotaUser *v36; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 v37; // [rsp+38h] [rbp-1D0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-1C8h] BYREF
  void *v39; // [rsp+48h] [rbp-1C0h] BYREF
  LPCWSTR *v40; // [rsp+50h] [rbp-1B8h]
  _QWORD *v41; // [rsp+58h] [rbp-1B0h]
  int v42; // [rsp+60h] [rbp-1A8h]
  _BYTE v43[4]; // [rsp+64h] [rbp-1A4h] BYREF
  LPARAM dwInitParam; // [rsp+68h] [rbp-1A0h] BYREF
  int v45; // [rsp+70h] [rbp-198h]
  int v46; // [rsp+74h] [rbp-194h]
  int v47; // [rsp+78h] [rbp-190h]
  int v48; // [rsp+7Ch] [rbp-18Ch]
  int v49; // [rsp+88h] [rbp-180h]
  HWND v50; // [rsp+90h] [rbp-178h]
  struct _RTL_CRITICAL_SECTION *p_CriticalSection; // [rsp+98h] [rbp-170h]
  int v52; // [rsp+A0h] [rbp-168h]
  _QWORD *v53; // [rsp+A8h] [rbp-160h]
  _BYTE pExceptionObject[16]; // [rsp+B0h] [rbp-158h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-148h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-140h]
  int v57; // [rsp+D0h] [rbp-138h]
  __int64 v58; // [rsp+D8h] [rbp-130h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+E0h] [rbp-128h] BYREF
  HWND v60; // [rsp+110h] [rbp-F8h]
  HWND v61; // [rsp+118h] [rbp-F0h]
  HINSTANCE hInstance[29]; // [rsp+120h] [rbp-E8h] BYREF
  int v64; // [rsp+210h] [rbp+8h]
  struct IDiskQuotaUser *v65; // [rsp+218h] [rbp+10h] BYREF
  int v66; // [rsp+220h] [rbp+18h]
  signed int v67; // [rsp+228h] [rbp+20h]

  if ( (unsigned int)SendMessageW(*((HWND *)this + 13), 0x1032u, 0, 0) == 1
    && (v3 = SendMessageW(*((HWND *)this + 13), 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2), v3 != -1)
    && (v65 = 0, PointerList::Retrieve((DetailsView *)((char *)this + 40), (void **)&v65, v3))
    && v65
    && (unsigned int)UserIsAdministrator(v65)
    || (unsigned int)DiskQuotaMsgBox(*((HWND *)this + 13), 0x9E81u, v2, 0x34u) != 7 )
  {
    UndoList::Clear(*((UndoList **)this + 24));
    v60 = (HWND)*((_QWORD *)this + 13);
    v4 = v60;
    v36 = 0;
    v5 = SendMessageW(v60, 0x1032u, 0, 0);
    dwInitParam = (LPARAM)&ProgressDialog::`vftable';
    v45 = 147;
    v46 = 1049;
    v47 = 1054;
    v48 = 1055;
    v49 = 0;
    v50 = 0;
    if ( v5 > 2 && ProgressDialog::Create((LPARAM)&dwInitParam, g_hInstDll, *((HWND *)this + 12)) )
    {
      EnableWindow(v4, 0);
      ProgressDialog::ProgressBarInit((ProgressDialog *)&dwInitParam, 0, v5, 1u);
      ProgressDialog::SetDescription((ProgressDialog *)&dwInitParam, (const unsigned __int16 *)0x9E47);
      ProgressDialog::Show((ProgressDialog *)&dwInitParam);
    }
    v6 = (HWND)*((_QWORD *)this + 13);
    v61 = v6;
    SendMessageW(v6, 0xBu, 0, 0);
    v55 = (__int64)&CArray<IDiskQuotaUser *>::`vftable';
    v56 = 0;
    v57 = 8;
    v58 = 0;
    if ( !InitializeCriticalSectionAndSpinCount(&CriticalSection, 0) )
    {
      CSyncException::CSyncException(pExceptionObject);
      throw (CSyncException *)pExceptionObject;
    }
    LODWORD(v65) = 0;
    v7 = -1;
    v38 = 0;
    v37 = 0;
    while ( 1 )
    {
      v8 = SendMessageW(*((HWND *)this + 13), 0x100Cu, v7, 2);
      v7 = v8;
      if ( v8 == -1 || v49 )
        break;
      if ( PointerList::Retrieve((DetailsView *)((char *)this + 40), (void **)&v36, v8) )
      {
        v9 = v36;
        if ( (unsigned int)UserIsAdministrator(v36) )
        {
          CString::CString((CString *)&v39, g_hInstDll, 40583);
          v11 = v50;
          if ( !v50 )
            v11 = (HWND)*((_QWORD *)this + 13);
          DiskQuotaMsgBox(v11, *v40, v10, 0x30u);
          CString::~CString((CString *)&v39);
        }
        else
        {
          ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))v9->lpVtbl->GetQuotaLimitText)(v9, &v38);
          ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))v9->lpVtbl->GetQuotaUsedText)(v9, &v37);
          v12 = (*(__int64 (__fastcall **)(_QWORD, struct IDiskQuotaUser *))(**((_QWORD **)this + 22) + 144LL))(
                  *((_QWORD *)this + 22),
                  v9);
          LODWORD(v65) = v12;
          if ( v12 < 0 )
          {
            if ( (_WORD)v12 == 80 )
              CArray<IDiskQuotaUser *>::Append(&v55, &v36);
          }
          else
          {
            if ( UserWasReallyDeleted(*((struct IDiskQuotaControl **)this + 22), v9) )
            {
              ((void (__fastcall *)(struct IDiskQuotaUser *))v9->lpVtbl->GetName)(v9);
              try
              {
                v13 = operator new(0x30u);
                if ( v13 )
                {
                  v14 = v37;
                  v15 = v38;
                  v13[1] = 0;
                  v13[2] = v9;
                  v13[3] = 0;
                  v13[5] = v15;
                  v13[4] = v14;
                  *v13 = &UndoDelete::`vftable';
                  v52 = 1;
                }
                else
                {
                  v52 = 0;
                  v13 = 0;
                }
                v53 = v13;
                p_CriticalSection = (struct _RTL_CRITICAL_SECTION *)&autoptr<UndoDelete>::`vftable';
                v16 = (PointerList *)*((_QWORD *)this + 24);
                v13[3] = v16;
                PointerList::Append(v16, v13);
              }
              catch ( CAllocException )
              {
                ((void (__fastcall *)(struct IDiskQuotaUser *))v36->lpVtbl->GetSidLength)(v36);
                EnableWindow(*((HWND *)this + 12), 1);
                throw;
              }
              SendMessageW(*((HWND *)this + 13), 0x1008u, v7, 0);
              PointerList::Remove((DetailsView *)((char *)this + 40), (void **)&v36, v7);
              ((void (__fastcall *)(struct IDiskQuotaUser *))v36->lpVtbl->GetSidLength)(v36);
              --v7;
            }
            else
            {
              ((void (__fastcall *)(struct IDiskQuotaUser *, __int64, __int64))v9->lpVtbl->GetAccountStatus)(v9, v38, 1);
              ((void (__fastcall *)(struct IDiskQuotaUser *, __int64, __int64))v9->lpVtbl[1].GetID)(v9, v37, 1);
            }
            ProgressDialog::ProgressBarAdvance((ProgressDialog *)&dwInitParam, 0xFFFFFFFF);
          }
        }
      }
    }
    if ( SHIDWORD(v56) > 0 )
    {
      ProgressDialog::SetDescription((ProgressDialog *)&dwInitParam, (const unsigned __int16 *)0x9EB9);
      LODWORD(v17) = (_DWORD)v50;
      if ( !v50 )
        v17 = *((_QWORD *)this + 13);
      CFileOwnerDialog::CFileOwnerDialog((int)hInstance, (int)g_hInstDll, v17, **((_QWORD **)this + 36), (__int64)&v55);
      SHFusionDialogBoxParam(
        hInstance[0],
        (LPCWSTR)0x98,
        (HWND)hInstance[1],
        (DLGPROC)CFileOwnerDialog::DlgProc,
        (LPARAM)hInstance);
      ProgressDialog::SetDescription((ProgressDialog *)&dwInitParam, (const unsigned __int16 *)0x9E47);
      v18 = HIDWORD(v56);
      v42 = HIDWORD(v56);
      v19 = 0;
      v64 = 0;
      v20 = 0;
      while ( 1 )
      {
        v66 = v20;
        if ( v20 >= v18 )
          break;
        p_CriticalSection = &CriticalSection;
        EnterCriticalSection(&CriticalSection);
        v52 = 1;
        if ( v20 < 0 || v20 >= SHIDWORD(v56) )
        {
          CMemoryException::CMemoryException(v43, 2);
          throw (CMemoryException *)v43;
        }
        v21 = v20;
        v22 = v58;
        v52 = 0;
        LeaveCriticalSection(&CriticalSection);
        v23 = *(struct IDiskQuotaUser **)(v22 + 8 * v21);
        v36 = v23;
        ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))v23->lpVtbl->GetQuotaLimitText)(v23, &v38);
        ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))v23->lpVtbl->GetQuotaUsedText)(v23, &v37);
        v24 = (*(__int64 (__fastcall **)(_QWORD, struct IDiskQuotaUser *))(**((_QWORD **)this + 22) + 144LL))(
                *((_QWORD *)this + 22),
                v23);
        LODWORD(v65) = v24;
        if ( v24 < 0 )
        {
          if ( (_WORD)v24 == 80 )
            v64 = ++v19;
        }
        else
        {
          v25 = !UserWasReallyDeleted(*((struct IDiskQuotaControl **)this + 22), v23);
          v26.lpVtbl = v23->lpVtbl;
          if ( v25 )
          {
            ((void (__fastcall *)(struct IDiskQuotaUser *, __int64, __int64))v26.lpVtbl->GetAccountStatus)(v23, v38, 1);
            ((void (__fastcall *)(struct IDiskQuotaUser *, __int64, __int64))v23->lpVtbl[1].GetID)(v23, v37, 1);
          }
          else
          {
            ((void (__fastcall *)(struct IDiskQuotaUser *))v26.lpVtbl->GetName)(v23);
            try
            {
              v27 = operator new(0x30u);
              if ( v27 )
              {
                v28 = v37;
                v29 = v38;
                v27[1] = 0;
                v27[2] = v23;
                v27[3] = 0;
                v27[5] = v29;
                v27[4] = v28;
                *v27 = &UndoDelete::`vftable';
                LODWORD(v40) = 1;
              }
              else
              {
                LODWORD(v40) = 0;
                v27 = 0;
              }
              v41 = v27;
              v39 = &autoptr<UndoDelete>::`vftable';
              v30 = (PointerList *)*((_QWORD *)this + 24);
              v27[3] = v30;
              PointerList::Append(v30, v27);
            }
            catch ( CAllocException )
            {
              ((void (__fastcall *)(struct IDiskQuotaUser *))v36->lpVtbl->GetSidLength)(v36);
              throw;
            }
            v31 = -1;
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
            v67 = StructureList::Count((DetailsView *)((char *)this + 40));
            v39 = 0;
            for ( i = 0; i < v67; ++i )
            {
              if ( v31 != -1 )
                break;
              if ( PointerList::Retrieve((DetailsView *)((char *)this + 40), &v39, i) && v39 && v23 == v39 )
                v31 = i;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
            if ( v31 != -1 )
            {
              SendMessageW(*((HWND *)this + 13), 0x1008u, v31, 0);
              PointerList::Remove((DetailsView *)((char *)this + 40), (void **)&v36, v31);
              ((void (__fastcall *)(struct IDiskQuotaUser *))v36->lpVtbl->GetSidLength)(v36);
            }
            v19 = v64;
          }
          ProgressDialog::ProgressBarAdvance((ProgressDialog *)&dwInitParam, 0xFFFFFFFF);
        }
        v20 = v66 + 1;
        v18 = v42;
      }
      if ( v19 > 0 )
      {
        CString::CString((CString *)&v39);
        if ( v19 == 1 )
          CString::Format((CString *)&v39, g_hInstDll, 0x9E7Bu);
        else
          CString::Format((CString *)&v39, g_hInstDll, 0x9E7Cu, (unsigned int)v19);
        DiskQuotaMsgBox(*((HWND *)this + 13), *v40, v33, 0x40u);
        CString::~CString((CString *)&v39);
      }
      CFileOwnerDialog::~CFileOwnerDialog((CFileOwnerDialog *)hInstance);
    }
    DetailsView::ShowItemCountInStatusBar(this);
    if ( (int)v65 < 0 && (_WORD)v65 != 80 )
      DiskQuotaMsgBox(*((HWND *)this + 13), 0x9E7Du, v34, 0x10u);
    CArray<IDiskQuotaUser *>::~CArray<IDiskQuotaUser *>((__int64)&v55);
    SendMessageW(v6, 0xBu, 1u, 0);
    ProgressDialog::~ProgressDialog((ProgressDialog *)&dwInitParam);
    EnableWindow(v4, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c8c4  mov     [rsp+arg_0], rcx
0x18000c8c9  push    rbx
0x18000c8ca  push    rsi
0x18000c8cb  push    rdi
0x18000c8cc  push    r12
0x18000c8ce  push    r13
0x18000c8d0  push    r14
0x18000c8d2  push    r15
0x18000c8d4  sub     rsp, 1D0h
0x18000c8db  mov     r13, rcx
0x18000c8de  xor     r9d, r9d; lParam
0x18000c8e1  xor     r8d, r8d; wParam
0x18000c8e4  mov     edi, 1032h
0x18000c8e9  mov     edx, edi; Msg
0x18000c8eb  mov     rcx, [rcx+68h]; hWnd
0x18000c8ef  call    cs:__imp_SendMessageW
0x18000c8f5  cmp     eax, 1
0x18000c8f8  jnz     short loc_18000C94F
0x18000c8fa  lea     r9d, [rax+1]; lParam
0x18000c8fe  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18000c902  lea     edx, [rdi-26h]; Msg
0x18000c905  mov     rcx, [r13+68h]; hWnd
0x18000c909  call    cs:__imp_SendMessageW
0x18000c90f  xor     r15d, r15d
0x18000c912  cmp     eax, 0FFFFFFFFh
0x18000c915  jz      short loc_18000C952
0x18000c917  mov     [rsp+208h+arg_8], r15
0x18000c91f  lea     rcx, [r13+28h]; this
0x18000c923  mov     r8d, eax; unsigned int
0x18000c926  lea     rdx, [rsp+208h+arg_8]; void **
0x18000c92e  call    ?Retrieve@PointerList@@QEAAHPEAPEAXI@Z; PointerList::Retrieve(void * *,uint)
0x18000c933  test    eax, eax
0x18000c935  jz      short loc_18000C952
0x18000c937  mov     rcx, [rsp+208h+arg_8]; struct IDiskQuotaUser *
0x18000c93f  test    rcx, rcx
0x18000c942  jz      short loc_18000C952
0x18000c944  call    ?UserIsAdministrator@@YAHPEAUIDiskQuotaUser@@@Z; UserIsAdministrator(IDiskQuotaUser *)
0x18000c949  test    eax, eax
0x18000c94b  jnz     short loc_18000C96F
0x18000c94d  jmp     short loc_18000C952
0x18000c94f  xor     r15d, r15d
0x18000c952  mov     edx, 9E81h; unsigned int
0x18000c957  mov     r9d, 34h ; '4'; unsigned int
0x18000c95d  mov     rcx, [r13+68h]; hWnd
0x18000c961  call    ?DiskQuotaMsgBox@@YAHPEAUHWND__@@III@Z; DiskQuotaMsgBox(HWND__ *,uint,uint,uint)
0x18000c966  cmp     eax, 7
0x18000c969  jz      loc_18000D0D8
0x18000c96f  mov     rcx, [r13+0C0h]; this
0x18000c976  call    ?Clear@UndoList@@QEAAXXZ; UndoList::Clear(void)
0x18000c97b  mov     rbx, [r13+68h]
0x18000c97f  mov     [rsp+208h+var_F8], rbx
0x18000c987  mov     [rsp+208h+var_1D8], r15
0x18000c98c  xor     r9d, r9d; lParam
0x18000c98f  xor     r8d, r8d; wParam
0x18000c992  mov     edx, edi; Msg
0x18000c994  mov     rcx, rbx; hWnd
0x18000c997  call    cs:__imp_SendMessageW
0x18000c99d  mov     rdi, rax
0x18000c9a0  lea     rax, ??_7ProgressDialog@@6B@; const ProgressDialog::`vftable'
0x18000c9a7  mov     [rsp+208h+dwInitParam], rax
0x18000c9ac  mov     [rsp+208h+var_198], 93h
0x18000c9b4  mov     [rsp+208h+var_194], 419h
0x18000c9bc  mov     [rsp+208h+var_190], 41Eh
0x18000c9c4  mov     [rsp+208h+var_18C], 41Fh
0x18000c9cc  mov     [rsp+208h+var_180], r15d
0x18000c9d4  mov     [rsp+208h+var_178], r15
0x18000c9dc  cmp     edi, 2
0x18000c9df  jle     short loc_18000CA33
0x18000c9e1  mov     r8, [r13+60h]; hWndParent
0x18000c9e5  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c9ec  lea     rcx, [rsp+208h+dwInitParam]; dwInitParam
0x18000c9f1  call    ?Create@ProgressDialog@@UEAAHPEAUHINSTANCE__@@PEAUHWND__@@@Z; ProgressDialog::Create(HINSTANCE__ *,HWND__ *)
0x18000c9f6  test    eax, eax
0x18000c9f8  jz      short loc_18000CA33
0x18000c9fa  xor     edx, edx; bEnable
0x18000c9fc  mov     rcx, rbx; hWnd
0x18000c9ff  call    cs:__imp_EnableWindow
0x18000ca05  mov     r9d, 1; unsigned int
0x18000ca0b  mov     r8d, edi; unsigned int
0x18000ca0e  xor     edx, edx; unsigned int
0x18000ca10  lea     rcx, [rsp+208h+dwInitParam]; this
0x18000ca15  call    ?ProgressBarInit@ProgressDialog@@UEAAHIII@Z; ProgressDialog::ProgressBarInit(uint,uint,uint)
0x18000ca1a  mov     edx, 9E47h; unsigned __int16 *
0x18000ca1f  lea     rcx, [rsp+208h+dwInitParam]; this
0x18000ca24  call    ?SetDescription@ProgressDialog@@UEAAXPEBG@Z; ProgressDialog::SetDescription(ushort const *)
0x18000ca29  lea     rcx, [rsp+208h+dwInitParam]; this
0x18000ca2e  call    ?Show@ProgressDialog@@UEAAXXZ; ProgressDialog::Show(void)
0x18000ca33  mov     rdi, [r13+68h]
0x18000ca37  mov     [rsp+208h+var_F0], rdi
0x18000ca3f  xor     r9d, r9d; lParam
0x18000ca42  xor     r8d, r8d; wParam
0x18000ca45  lea     edx, [r9+0Bh]; Msg
0x18000ca49  mov     rcx, rdi; hWnd
0x18000ca4c  call    cs:__imp_SendMessageW
0x18000ca52  nop
0x18000ca53  lea     rax, ??_7?$CArray@PEAUIDiskQuotaUser@@@@6B@; const CArray<IDiskQuotaUser *>::`vftable'
0x18000ca5a  mov     [rsp+208h+var_148], rax
0x18000ca62  mov     [rsp+208h+var_140], 0
0x18000ca6e  mov     [rsp+208h+var_138], 8
0x18000ca79  mov     [rsp+208h+var_130], r15
0x18000ca81  xor     edx, edx; dwSpinCount
0x18000ca83  lea     rcx, [rsp+208h+CriticalSection]; lpCriticalSection
0x18000ca8b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000ca91  test    eax, eax
0x18000ca93  jz      loc_18000D0ED
0x18000ca99  mov     dword ptr [rsp+208h+arg_8], r15d
0x18000caa1  or      r14d, 0FFFFFFFFh
0x18000caa5  mov     [rsp+208h+var_1C8], r15
0x18000caaa  mov     [rsp+208h+var_1D0], r15
0x18000caaf  movsxd  r8, r14d; wParam
0x18000cab2  mov     edx, 100Ch; Msg
0x18000cab7  mov     r9d, 2; lParam
0x18000cabd  mov     rcx, [r13+68h]; hWnd
0x18000cac1  call    cs:__imp_SendMessageW
0x18000cac7  mov     r14, rax
0x18000caca  cmp     eax, 0FFFFFFFFh
0x18000cacd  jz      loc_18000CCE3
0x18000cad3  cmp     [rsp+208h+var_180], r15d
0x18000cadb  jnz     loc_18000CCE3
0x18000cae1  mov     r8d, r14d; unsigned int
0x18000cae4  lea     rdx, [rsp+208h+var_1D8]; void **
0x18000cae9  lea     rcx, [r13+28h]; this
0x18000caed  call    ?Retrieve@PointerList@@QEAAHPEAPEAXI@Z; PointerList::Retrieve(void * *,uint)
0x18000caf2  test    eax, eax
0x18000caf4  jz      short loc_18000CAAF
0x18000caf6  mov     rsi, [rsp+208h+var_1D8]
0x18000cafb  mov     rcx, rsi; struct IDiskQuotaUser *
0x18000cafe  call    ?UserIsAdministrator@@YAHPEAUIDiskQuotaUser@@@Z; UserIsAdministrator(IDiskQuotaUser *)
0x18000cb03  test    eax, eax
0x18000cb05  jz      short loc_18000CB53
0x18000cb07  mov     r8d, 9E87h; int
0x18000cb0d  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18000cb14  lea     rcx, [rsp+208h+var_1C0]; this
0x18000cb19  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x18000cb1e  nop
0x18000cb1f  mov     rax, [rsp+208h+var_1B8]
0x18000cb24  mov     rcx, [rsp+208h+var_178]
0x18000cb2c  test    rcx, rcx
0x18000cb2f  jnz     short loc_18000CB35
0x18000cb31  mov     rcx, [r13+68h]; hWnd
0x18000cb35  mov     r9d, 30h ; '0'; unsigned int
0x18000cb3b  mov     rdx, [rax]; lpText
0x18000cb3e  call    ?DiskQuotaMsgBox@@YAHPEAUHWND__@@PEBGII@Z; DiskQuotaMsgBox(HWND__ *,ushort const *,uint,uint)
0x18000cb43  nop
0x18000cb44  lea     rcx, [rsp+208h+var_1C0]; this
0x18000cb49  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18000cb4e  jmp     loc_18000CAAF
0x18000cb53  mov     rax, [rsi]
0x18000cb56  lea     rdx, [rsp+208h+var_1C8]
0x18000cb5b  mov     rcx, rsi
0x18000cb5e  mov     rax, [rax+38h]
0x18000cb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb67  mov     rax, [rsi]
0x18000cb6a  lea     rdx, [rsp+208h+var_1D0]
0x18000cb6f  mov     rcx, rsi
0x18000cb72  mov     rax, [rax+48h]
0x18000cb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7b  mov     rcx, [r13+0B0h]
0x18000cb82  mov     rax, [rcx]
0x18000cb85  mov     rdx, rsi
0x18000cb88  mov     rax, [rax+90h]
0x18000cb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb94  mov     dword ptr [rsp+208h+arg_8], eax
0x18000cb9b  test    eax, eax
0x18000cb9d  js      loc_18000CCC2
0x18000cba3  mov     rdx, rsi; struct IDiskQuotaUser *
0x18000cba6  mov     rcx, [r13+0B0h]; struct IDiskQuotaControl *
0x18000cbad  call    ?UserWasReallyDeleted@@YA_NPEAUIDiskQuotaControl@@PEAUIDiskQuotaUser@@@Z; UserWasReallyDeleted(IDiskQuotaControl *,IDiskQuotaUser *)
0x18000cbb2  mov     rcx, rsi
0x18000cbb5  test    al, al
0x18000cbb7  jnz     short loc_18000CBEF
0x18000cbb9  mov     rdx, [rsi]
0x18000cbbc  mov     rax, [rdx+70h]
0x18000cbc0  mov     r8d, 1
0x18000cbc6  mov     rdx, [rsp+208h+var_1C8]
0x18000cbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd0  mov     rax, [rsi]
0x18000cbd3  mov     r8d, 1
0x18000cbd9  mov     rdx, [rsp+208h+var_1D0]
0x18000cbde  mov     rcx, rsi
0x18000cbe1  mov     rax, [rax+78h]
0x18000cbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbea  jmp     loc_18000CCB0
0x18000cbef  mov     rax, [rsi]
0x18000cbf2  mov     rax, [rax+8]
0x18000cbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbfb  nop
0x18000cbfc  mov     ecx, 30h ; '0'; uBytes
0x18000cc01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cc06  mov     rdx, rax
0x18000cc09  test    rax, rax
0x18000cc0c  jz      short loc_18000CC43
0x18000cc0e  mov     rcx, [rsp+208h+var_1D0]
0x18000cc13  mov     rax, [rsp+208h+var_1C8]
0x18000cc18  mov     [rdx+8], r15
0x18000cc1c  mov     [rdx+10h], rsi
0x18000cc20  mov     [rdx+18h], r15
0x18000cc24  mov     [rdx+28h], rax
0x18000cc28  mov     [rdx+20h], rcx
0x18000cc2c  lea     rax, ??_7UndoDelete@@6B@; const UndoDelete::`vftable'
0x18000cc33  mov     [rdx], rax
0x18000cc36  mov     [rsp+208h+var_168], 1
0x18000cc41  jmp     short loc_18000CC4E
0x18000cc43  mov     [rsp+208h+var_168], r15d
0x18000cc4b  mov     rdx, r15; void *
0x18000cc4e  mov     [rsp+208h+var_160], rdx
0x18000cc56  lea     rax, ??_7?$autoptr@VUndoDelete@@@@6B@; const autoptr<UndoDelete>::`vftable'
0x18000cc5d  mov     [rsp+208h+var_170], rax
0x18000cc65  mov     rcx, [r13+0C0h]; this
0x18000cc6c  mov     [rdx+18h], rcx
0x18000cc70  call    ?Append@PointerList@@QEAAXPEBX@Z; PointerList::Append(void const *)
0x18000cc75  nop
0x18000cc76  movsxd  r8, r14d; wParam
0x18000cc79  xor     r9d, r9d; lParam
0x18000cc7c  mov     edx, 1008h; Msg
0x18000cc81  mov     rcx, [r13+68h]; hWnd
0x18000cc85  call    cs:__imp_SendMessageW
0x18000cc8b  mov     r8d, r14d; unsigned int
0x18000cc8e  lea     rdx, [rsp+208h+var_1D8]; void **
0x18000cc93  lea     rcx, [r13+28h]; this
0x18000cc97  call    ?Remove@PointerList@@QEAAHPEAPEAXI@Z; PointerList::Remove(void * *,uint)
0x18000cc9c  mov     rcx, [rsp+208h+var_1D8]
0x18000cca1  mov     rax, [rcx]
0x18000cca4  mov     rax, [rax+10h]
0x18000cca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccad  dec     r14d
0x18000ccb0  or      edx, 0FFFFFFFFh; unsigned int
0x18000ccb3  lea     rcx, [rsp+208h+dwInitParam]; this
0x18000ccb8  call    ?ProgressBarAdvance@ProgressDialog@@UEAAII@Z; ProgressDialog::ProgressBarAdvance(uint)
0x18000ccbd  jmp     loc_18000CAAF
0x18000ccc2  cmp     ax, 50h ; 'P'
0x18000ccc6  jnz     loc_18000CAAF
0x18000cccc  lea     rdx, [rsp+208h+var_1D8]
0x18000ccd1  lea     rcx, [rsp+208h+var_148]
0x18000ccd9  call    ?Append@?$CArray@PEAUIDiskQuotaUser@@@@QEAAXAEBQEAUIDiskQuotaUser@@H@Z; CArray<IDiskQuotaUser *>::Append(IDiskQuotaUser * const &,int)
0x18000ccde  jmp     loc_18000CAAF
0x18000cce3  cmp     dword ptr [rsp+208h+var_140+4], r15d
0x18000cceb  jle     loc_18000D06E
0x18000ccf1  mov     edx, 9EB9h; unsigned __int16 *
0x18000ccf6  lea     rcx, [rsp+208h+dwInitParam]; this
0x18000ccfb  call    ?SetDescription@ProgressDialog@@UEAAXPEBG@Z; ProgressDialog::SetDescription(ushort const *)
0x18000cd00  mov     rax, [r13+120h]
0x18000cd07  mov     r8, [rsp+208h+var_178]
0x18000cd0f  test    r8, r8
0x18000cd12  jnz     short loc_18000CD18
0x18000cd14  mov     r8, [r13+68h]; int
0x18000cd18  lea     rcx, [rsp+208h+var_148]
0x18000cd20  mov     [rsp+208h+var_1E8], rcx; pExceptionObject
0x18000cd25  mov     r9, [rax]; int
0x18000cd28  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; int
0x18000cd2f  lea     rcx, [rsp+208h+hInstance]; int
0x18000cd37  call    ??0CFileOwnerDialog@@QEAA@PEAUHINSTANCE__@@PEAUHWND__@@PEBGAEBV?$CArray@PEAUIDiskQuotaUser@@@@@Z; CFileOwnerDialog::CFileOwnerDialog(HINSTANCE__ *,HWND__ *,ushort const *,CArray<IDiskQuotaUser *> const &)
0x18000cd3c  nop
0x18000cd3d  lea     rax, [rsp+208h+hInstance]
0x18000cd45  mov     [rsp+208h+var_1E8], rax; LPARAM
0x18000cd4a  lea     r9, ?DlgProc@CFileOwnerDialog@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000cd51  mov     r8, [rsp+208h+hWndParent]; hWndParent
0x18000cd59  mov     edx, 98h; lpTemplateName
0x18000cd5e  mov     rcx, [rsp+208h+hInstance]; hInstance
0x18000cd66  call    SHFusionDialogBoxParam
0x18000cd6b  mov     edx, 9E47h; unsigned __int16 *
0x18000cd70  lea     rcx, [rsp+208h+dwInitParam]; this
0x18000cd75  call    ?SetDescription@ProgressDialog@@UEAAXPEBG@Z; ProgressDialog::SetDescription(ushort const *)
0x18000cd7a  mov     eax, dword ptr [rsp+208h+var_140+4]
0x18000cd81  mov     [rsp+208h+var_1A8], eax
0x18000cd85  mov     r12d, r15d
0x18000cd88  mov     dword ptr [rsp+208h+arg_0], r15d
0x18000cd90  mov     esi, r15d
0x18000cd93  mov     [rsp+208h+arg_10], esi
0x18000cd9a  cmp     esi, eax
0x18000cd9c  jge     loc_18000D001
0x18000cda2  lea     rax, [rsp+208h+CriticalSection]
0x18000cdaa  mov     [rsp+208h+var_170], rax
0x18000cdb2  lea     rcx, [rsp+208h+CriticalSection]; lpCriticalSection
0x18000cdba  call    cs:__imp_EnterCriticalSection
0x18000cdc0  mov     [rsp+208h+var_168], 1
0x18000cdcb  test    esi, esi
0x18000cdcd  js      loc_18000D10F
0x18000cdd3  cmp     esi, dword ptr [rsp+208h+var_140+4]
0x18000cdda  jge     loc_18000D10F
0x18000cde0  movsxd  r14, esi
0x18000cde3  mov     rsi, [rsp+208h+var_130]
0x18000cdeb  mov     [rsp+208h+var_168], r15d
0x18000cdf3  lea     rcx, [rsp+208h+CriticalSection]; lpCriticalSection
0x18000cdfb  call    cs:__imp_LeaveCriticalSection
0x18000ce01  mov     rsi, [rsi+r14*8]
0x18000ce05  mov     [rsp+208h+var_1D8], rsi
0x18000ce0a  mov     rax, [rsi]
0x18000ce0d  lea     rdx, [rsp+208h+var_1C8]
0x18000ce12  mov     rcx, rsi
0x18000ce15  mov     rax, [rax+38h]
0x18000ce19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce1e  mov     rax, [rsi]
0x18000ce21  lea     rdx, [rsp+208h+var_1D0]
0x18000ce26  mov     rcx, rsi
0x18000ce29  mov     rax, [rax+48h]
0x18000ce2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce32  mov     rcx, [r13+0B0h]
0x18000ce39  mov     rax, [rcx]
0x18000ce3c  mov     rdx, rsi
  ... truncated ...
```
