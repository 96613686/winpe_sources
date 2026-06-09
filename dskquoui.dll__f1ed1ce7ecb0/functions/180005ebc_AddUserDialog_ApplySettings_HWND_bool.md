# AddUserDialog::ApplySettings(HWND__ *,bool)

- ea: `0x180005ebc`
- end: `0x1800064c5`
- name: `?ApplySettings@AddUserDialog@@AEAAJPEAUHWND__@@_N@Z`
- size: `1545`
- prototype: `int(AddUserDialog *__hidden this, HWND, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006c54`

## callees

- `0x180001510`
- `0x180005ebc`
- `0x180006ec0`
- `0x1800110fc`
- `0x18001583c`
- `0x180015870`
- `0x180015b60`
- `0x180015bd0`
- `0x180015cf0`
- `0x180015dc0`
- `0x180015f60`
- `0x180016b5c`
- `0x180019d24`
- `0x180019ee0`
- `0x18001abb8`
- `0x18001f010`

## import_xrefs

- `SHLWAPI!StrCmpNW` at `0x1800060d5`
- `SHLWAPI!StrCmpNW` at `0x1800060d5`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1800060b1`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1800060b1`
- `USER32!IsWindowVisible` at `0x180005fb0`
- `USER32!IsWindowVisible` at `0x1800063db`
- `USER32!IsWindowVisible` at `0x180005fb0`
- `USER32!IsWindowVisible` at `0x1800063db`
- `USER32!GetParent` at `0x180005fc2`
- `USER32!GetParent` at `0x180005fc2`
- `USER32!SendMessageW` at `0x180006362`
- `USER32!SendMessageW` at `0x180006362`
- `USER32!SetCursor` at `0x180005f0c`
- `USER32!SetCursor` at `0x180006496`
- `USER32!SetCursor` at `0x180005f0c`
- `USER32!SetCursor` at `0x180006496`
- `USER32!LoadCursorW` at `0x180005f03`
- `USER32!LoadCursorW` at `0x180005f03`
- `USER32!ShowCursor` at `0x180005f26`
- `USER32!ShowCursor` at `0x180006488`
- `USER32!ShowCursor` at `0x180005f26`
- `USER32!ShowCursor` at `0x180006488`
- `USER32!IsDlgButtonChecked` at `0x180005f35`
- `USER32!IsDlgButtonChecked` at `0x180005f35`

## string_xrefs

- `0x1800060cb`: `LDAP://<SID=`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AddUserDialog::ApplySettings(AddUserDialog *this, HWND a2)
{
  signed int v4; // r14d
  HCURSOR CursorW; // rax
  HCURSOR v6; // rbx
  __int64 v7; // rax
  HWND Parent; // rax
  bool v9; // r13
  signed int v10; // ebx
  __int64 v11; // r12
  const unsigned __int16 *v12; // r14
  int v13; // edi
  const WCHAR *v14; // rax
  __int64 v15; // r9
  const WCHAR *v16; // r15
  __int64 v17; // rdx
  __int64 v18; // r8
  _BYTE *v19; // r11
  _WORD *v20; // r15
  _BYTE *v21; // r10
  char v22; // di
  char v23; // dl
  int v24; // r8d
  _QWORD *v25; // r15
  __int64 (__fastcall *v26)(_QWORD *, _BYTE *, __int64, LPARAM *); // rdi
  int v27; // eax
  __int64 v28; // rdi
  _QWORD *v29; // rax
  _QWORD *v30; // rdx
  LPARAM v31; // rcx
  PointerList *v32; // rcx
  unsigned int v33; // edi
  unsigned int v34; // r8d
  BOOL v35; // eax
  HWND v36; // rcx
  void **v38; // [rsp+30h] [rbp-D0h] BYREF
  int v39; // [rsp+38h] [rbp-C8h]
  LPARAM lParam; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v41; // [rsp+48h] [rbp-B8h]
  int v42; // [rsp+50h] [rbp-B0h]
  signed int v43; // [rsp+54h] [rbp-ACh]
  LPARAM dwInitParam; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+60h] [rbp-A0h]
  int v46; // [rsp+64h] [rbp-9Ch]
  int v47; // [rsp+68h] [rbp-98h]
  int v48; // [rsp+6Ch] [rbp-94h]
  int v49; // [rsp+78h] [rbp-88h]
  HWND hWnd; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h]
  HWND v52; // [rsp+90h] [rbp-70h]
  HCURSOR v53; // [rsp+98h] [rbp-68h]
  char v54[8]; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR *v55; // [rsp+A8h] [rbp-58h]
  char v56[8]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v57; // [rsp+B8h] [rbp-48h]
  void **v58; // [rsp+C0h] [rbp-40h]
  int v59; // [rsp+C8h] [rbp-38h]
  _QWORD *v60; // [rsp+D0h] [rbp-30h]
  HCURSOR v61; // [rsp+D8h] [rbp-28h]
  void **v62; // [rsp+E0h] [rbp-20h]
  BOOL v63; // [rsp+E8h] [rbp-18h]
  __int64 v64; // [rsp+F0h] [rbp-10h]
  void **v65; // [rsp+F8h] [rbp-8h]
  int v66; // [rsp+100h] [rbp+0h]
  LPARAM v67; // [rsp+108h] [rbp+8h]
  _BYTE v68[80]; // [rsp+110h] [rbp+10h] BYREF

  v52 = a2;
  v4 = **((_DWORD **)this + 9);
  v43 = v4;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v6 = SetCursor(CursorW);
  v53 = v6;
  v61 = v6;
  ShowCursor(1);
  if ( IsDlgButtonChecked(a2, 1029) == 1 )
  {
    v7 = -1;
    *((_QWORD *)this + 3) = -1;
  }
  else
  {
    *((_QWORD *)this + 3) = **((_QWORD **)this + 21);
    v7 = **((_QWORD **)this + 20);
  }
  *((_QWORD *)this + 2) = v7;
  UndoList::Clear(*((UndoList **)this + 5));
  dwInitParam = (LPARAM)&ProgressDialog::`vftable';
  v45 = 147;
  v46 = 1049;
  v47 = 1054;
  v48 = 1055;
  v49 = 0;
  hWnd = 0;
  if ( v4 > 2
    && (!IsWindowVisible(a2) ? (Parent = GetParent(a2)) : (Parent = a2),
        ProgressDialog::Create((LPARAM)&dwInitParam, *((HINSTANCE *)this + 6), Parent)) )
  {
    ProgressDialog::ProgressBarInit((ProgressDialog *)&dwInitParam, 0, v4, 1u);
    ProgressDialog::SetDescription((ProgressDialog *)&dwInitParam, (const unsigned __int16 *)0x9EA2);
    ProgressDialog::Show((ProgressDialog *)&dwInitParam);
    v9 = 0;
    LODWORD(v41) = 0;
  }
  else
  {
    v9 = 0;
    LODWORD(v41) = 0;
    if ( v4 <= 0 )
      goto LABEL_68;
  }
  v51 = 48;
  v42 = 5;
  v10 = (int)v41;
  do
  {
    if ( v9 )
      break;
    v11 = *((_QWORD *)this + 9);
    v12 = *(const unsigned __int16 **)(v11 + 48LL * v10 + 32);
    if ( !v12 || !*v12 )
    {
      v12 = *(const unsigned __int16 **)(v11 + 48LL * v10 + 8);
      if ( !v12 )
      {
        ProgressDialog::ProgressBarAdvance((ProgressDialog *)&dwInitParam, 0xFFFFFFFF);
        goto LABEL_66;
      }
    }
    ProgressDialog::SetFileName((ProgressDialog *)&dwInitParam, v12);
    v39 = 0;
    lParam = 0;
    v38 = &com_autoptr<IDiskQuotaControl>::`vftable';
    v41 = (_QWORD *)*((_QWORD *)this + 4);
    v13 = -2147024883;
    v14 = CharUpperW(*(LPWSTR *)(v11 + 48LL * v10 + 16));
    v16 = v14;
    if ( !v14 || StrCmpNW(v14, L"LDAP://<SID=", 12) )
      goto LABEL_35;
    v15 = 68;
    v19 = v68;
    v13 = 0;
    v20 = v16 + 12;
    do
    {
      if ( !*v20 )
        goto LABEL_33;
      if ( *v20 == 62 )
        break;
      if ( (int)v15 <= 0 )
      {
        v13 = -2147024774;
        goto LABEL_35;
      }
      v15 = (unsigned int)(v15 - 1);
      v21 = v19++;
      *v21 = 0;
      v18 = 0;
      v22 = 0;
      while ( 1 )
      {
        v17 = (unsigned __int16)v20[(unsigned int)v18];
        if ( (unsigned __int16)(v17 - v51) > 9u )
          break;
        v23 = v17 - 48;
LABEL_28:
        LOBYTE(v17) = v22 | (v23 << *((_DWORD *)&qword_180021AD0 + (unsigned int)v18));
        v22 = v17;
        *v21 = v17;
        v18 = (unsigned int)(v18 + 1);
        if ( (int)v18 >= 2 )
        {
          v13 = 0;
          goto LABEL_31;
        }
      }
      if ( (unsigned __int16)(v17 - 65) <= (unsigned __int16)v42 )
      {
        v23 = v17 - 55;
        goto LABEL_28;
      }
      v13 = -2147024883;
LABEL_31:
      v20 += 2;
    }
    while ( v13 >= 0 );
    if ( v13 < 0 )
      goto LABEL_35;
LABEL_33:
    if ( *v20 != 62 )
    {
      v13 = -2147024883;
      goto LABEL_35;
    }
    v25 = v41;
    v26 = *(__int64 (__fastcall **)(_QWORD *, _BYTE *, __int64, LPARAM *))(*v41 + 128LL);
    if ( v39 )
      ((void (__fastcall *)(void ***, __int64, __int64, __int64))*v38)(&v38, v17, v18, v15);
    lParam = 0;
    v39 = 1;
    v27 = v26(v25, v68, 2, &lParam);
    v13 = v27;
    if ( v27 < 0 )
      goto LABEL_35;
    if ( v27 == 1 )
      goto LABEL_52;
    v13 = (*(__int64 (__fastcall **)(LPARAM, _QWORD, __int64))(*(_QWORD *)lParam + 120LL))(
            lParam,
            *((_QWORD *)this + 2),
            1);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(LPARAM, _QWORD, __int64))(*(_QWORD *)lParam + 112LL))(
              lParam,
              *((_QWORD *)this + 3),
              1);
      if ( v13 >= 0 )
      {
        v28 = *((_QWORD *)this + 4);
        v63 = v28 != 0;
        v64 = v28;
        v62 = &com_autoptr<IDiskQuotaControl>::`vftable';
        v66 = v39;
        v39 = 0;
        v67 = lParam;
        v65 = &com_autoptr<IDiskQuotaControl>::`vftable';
        (*(void (__fastcall **)(LPARAM))(*(_QWORD *)lParam + 8LL))(lParam);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
        v29 = operator new(0x30u);
        v30 = v29;
        v41 = v29;
        if ( v29 )
        {
          v31 = lParam;
          v29[1] = *((_QWORD *)this + 4);
          v29[2] = v31;
          v29[3] = 0;
          v29[5] = 0;
          v29[4] = 0;
          *v29 = &UndoAdd::`vftable';
          v59 = 1;
        }
        else
        {
          v30 = 0;
          v59 = 0;
        }
        v60 = v30;
        v58 = &autoptr<UndoDelete>::`vftable';
        v32 = (PointerList *)*((_QWORD *)this + 5);
        v30[3] = v32;
        PointerList::Append(v32, v30);
        SendMessageW(*((HWND *)this + 8), 0x5F6u, 0, lParam);
        v39 = 0;
        goto LABEL_60;
      }
    }
LABEL_35:
    if ( v13 == -2147467259 )
    {
      v24 = 40570;
LABEL_55:
      v33 = 17;
      CString::CString((CString *)v56, *((HINSTANCE *)this + 6), v24, v15);
      goto LABEL_56;
    }
    if ( (unsigned __int16)v13 == 5 )
    {
      v33 = 49;
      CString::CString((CString *)v56, *((HINSTANCE *)this + 6), 40569, v15);
      goto LABEL_56;
    }
    if ( (unsigned __int16)v13 == 1316 )
    {
LABEL_52:
      v33 = 49;
      CString::CString((CString *)v56, *((HINSTANCE *)this + 6), 40550, v15);
      goto LABEL_56;
    }
    if ( (unsigned __int16)v13 != 1317 )
    {
      v24 = 40568;
      goto LABEL_55;
    }
    v33 = 49;
    CString::CString((CString *)v56, *((HINSTANCE *)this + 6), 40551, v15);
LABEL_56:
    CString::CString((CString *)v54, *((HINSTANCE *)this + 6), 40608, *v57, v12);
    if ( !hWnd || (v35 = IsWindowVisible(hWnd), v36 = hWnd, !v35) )
      v36 = v52;
    v9 = (unsigned int)DiskQuotaMsgBox(v36, *v55, v34, v33) == 2;
    CString::~CString((CString *)v54);
    CString::~CString((CString *)v56);
LABEL_60:
    ProgressDialog::ProgressBarAdvance((ProgressDialog *)&dwInitParam, 0xFFFFFFFF);
    if ( v9 || (v9 = 0, v49) )
      v9 = 1;
    v38 = &com_autoptr<IDiskQuotaControl>::`vftable';
    if ( v39 && lParam )
      (*(void (__fastcall **)(LPARAM))(*(_QWORD *)lParam + 16LL))(lParam);
LABEL_66:
    ++v10;
  }
  while ( v10 < v43 );
  v6 = v53;
LABEL_68:
  ProgressDialog::~ProgressDialog((ProgressDialog *)&dwInitParam);
  ShowCursor(0);
  if ( v6 )
    SetCursor(v6);
  return 0;
}

```

## disassembly

```asm
0x180005ebc  mov     [rsp-8+arg_10], rbx
0x180005ec1  push    rbp
0x180005ec2  push    rsi
0x180005ec3  push    rdi
0x180005ec4  push    r12
0x180005ec6  push    r13
0x180005ec8  push    r14
0x180005eca  push    r15
0x180005ecc  lea     rbp, [rsp-70h]
0x180005ed1  sub     rsp, 170h
0x180005ed8  mov     rax, cs:__security_cookie
0x180005edf  xor     rax, rsp
0x180005ee2  mov     [rbp+0A0h+var_40], rax
0x180005ee6  mov     rdi, rdx
0x180005ee9  mov     [rbp+0A0h+var_110], rdx
0x180005eed  mov     rsi, rcx
0x180005ef0  mov     rax, [rcx+48h]
0x180005ef4  mov     r14d, [rax]
0x180005ef7  mov     [rsp+1A0h+var_14C], r14d
0x180005efc  mov     edx, 7F02h; lpCursorName
0x180005f01  xor     ecx, ecx; hInstance
0x180005f03  call    cs:__imp_LoadCursorW
0x180005f09  mov     rcx, rax; hCursor
0x180005f0c  call    cs:__imp_SetCursor
0x180005f12  mov     rbx, rax
0x180005f15  mov     [rbp+0A0h+var_108], rax
0x180005f19  mov     [rbp+0A0h+var_C8], rax
0x180005f1d  mov     r15d, 1
0x180005f23  mov     ecx, r15d; bShow
0x180005f26  call    cs:__imp_ShowCursor
0x180005f2c  nop
0x180005f2d  mov     edx, 405h; nIDButton
0x180005f32  mov     rcx, rdi; hDlg
0x180005f35  call    cs:__imp_IsDlgButtonChecked
0x180005f3b  cmp     eax, r15d
0x180005f3e  jnz     short loc_180005F4A
0x180005f40  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005f44  mov     [rsi+18h], rax
0x180005f48  jmp     short loc_180005F62
0x180005f4a  mov     rax, [rsi+0A8h]
0x180005f51  mov     rcx, [rax]
0x180005f54  mov     [rsi+18h], rcx
0x180005f58  mov     rax, [rsi+0A0h]
0x180005f5f  mov     rax, [rax]
0x180005f62  mov     [rsi+10h], rax
0x180005f66  mov     rcx, [rsi+28h]; this
0x180005f6a  call    ?Clear@UndoList@@QEAAXXZ; UndoList::Clear(void)
0x180005f6f  lea     rax, ??_7ProgressDialog@@6B@; const ProgressDialog::`vftable'
0x180005f76  mov     [rsp+1A0h+dwInitParam], rax
0x180005f7b  mov     [rsp+1A0h+var_140], 93h
0x180005f83  mov     [rsp+1A0h+var_13C], 419h
0x180005f8b  mov     [rsp+1A0h+var_138], 41Eh
0x180005f93  mov     [rsp+1A0h+var_134], 41Fh
0x180005f9b  xor     r12d, r12d
0x180005f9e  mov     [rsp+1A0h+var_128], r12d
0x180005fa3  mov     [rbp+0A0h+hWnd], r12
0x180005fa7  cmp     r14d, 2
0x180005fab  jle     short loc_180006012
0x180005fad  mov     rcx, rdi; hWnd
0x180005fb0  call    cs:__imp_IsWindowVisible
0x180005fb6  test    eax, eax
0x180005fb8  jz      short loc_180005FBF
0x180005fba  mov     rax, rdi
0x180005fbd  jmp     short loc_180005FC8
0x180005fbf  mov     rcx, rdi; hWnd
0x180005fc2  call    cs:__imp_GetParent
0x180005fc8  mov     r8, rax; hWndParent
0x180005fcb  mov     rdx, [rsi+30h]; hInstance
0x180005fcf  lea     rcx, [rsp+1A0h+dwInitParam]; dwInitParam
0x180005fd4  call    ?Create@ProgressDialog@@UEAAHPEAUHINSTANCE__@@PEAUHWND__@@@Z; ProgressDialog::Create(HINSTANCE__ *,HWND__ *)
0x180005fd9  test    eax, eax
0x180005fdb  jz      short loc_180006012
0x180005fdd  mov     r9d, r15d; unsigned int
0x180005fe0  mov     r8d, r14d; unsigned int
0x180005fe3  xor     edx, edx; unsigned int
0x180005fe5  lea     rcx, [rsp+1A0h+dwInitParam]; this
0x180005fea  call    ?ProgressBarInit@ProgressDialog@@UEAAHIII@Z; ProgressDialog::ProgressBarInit(uint,uint,uint)
0x180005fef  mov     edx, 9EA2h; unsigned __int16 *
0x180005ff4  lea     rcx, [rsp+1A0h+dwInitParam]; this
0x180005ff9  call    ?SetDescription@ProgressDialog@@UEAAXPEBG@Z; ProgressDialog::SetDescription(ushort const *)
0x180005ffe  lea     rcx, [rsp+1A0h+dwInitParam]; this
0x180006003  call    ?Show@ProgressDialog@@UEAAXXZ; ProgressDialog::Show(void)
0x180006008  mov     r13b, r12b
0x18000600b  mov     dword ptr [rsp+1A0h+var_158], r12d
0x180006010  jmp     short loc_180006023
0x180006012  mov     r13b, r12b
0x180006015  mov     dword ptr [rsp+1A0h+var_158], r12d
0x18000601a  test    r14d, r14d
0x18000601d  jle     loc_18000647B
0x180006023  mov     [rbp+0A0h+var_118], 30h ; '0'
0x18000602b  mov     [rsp+1A0h+var_150], 5
0x180006033  mov     ebx, dword ptr [rsp+1A0h+var_158]
0x180006037  test    r13b, r13b
0x18000603a  jnz     loc_180006477
0x180006040  movsxd  rax, ebx
0x180006043  lea     r15, [rax+rax*2]
0x180006047  add     r15, r15
0x18000604a  mov     r12, [rsi+48h]
0x18000604e  mov     r14, [r12+r15*8+20h]
0x180006053  xor     edi, edi
0x180006055  test    r14, r14
0x180006058  jz      short loc_180006060
0x18000605a  cmp     [r14], di
0x18000605e  jnz     short loc_18000607C
0x180006060  mov     r14, [r12+r15*8+8]
0x180006065  test    r14, r14
0x180006068  jnz     short loc_18000607C
0x18000606a  or      edx, 0FFFFFFFFh; unsigned int
0x18000606d  lea     rcx, [rsp+1A0h+dwInitParam]; this
0x180006072  call    ?ProgressBarAdvance@ProgressDialog@@UEAAII@Z; ProgressDialog::ProgressBarAdvance(uint)
0x180006077  jmp     loc_18000646B
0x18000607c  mov     rdx, r14; unsigned __int16 *
0x18000607f  lea     rcx, [rsp+1A0h+dwInitParam]; this
0x180006084  call    ?SetFileName@ProgressDialog@@UEAAXPEBG@Z; ProgressDialog::SetFileName(ushort const *)
0x180006089  mov     [rsp+1A0h+var_168], edi
0x18000608d  mov     [rsp+1A0h+lParam], rdi
0x180006092  lea     rax, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x180006099  mov     [rsp+1A0h+var_170], rax
0x18000609e  mov     rax, [rsi+20h]
0x1800060a2  mov     [rsp+1A0h+var_158], rax
0x1800060a7  mov     edi, 8007000Dh
0x1800060ac  mov     rcx, [r12+r15*8+10h]; lpsz
0x1800060b1  call    cs:__imp_CharUpperW
0x1800060b7  mov     r15, rax
0x1800060ba  xor     r12d, r12d
0x1800060bd  test    rax, rax
0x1800060c0  jz      loc_180006192
0x1800060c6  lea     r8d, [r12+0Ch]; nChar
0x1800060cb  lea     rdx, psz2; "LDAP://<SID="
0x1800060d2  mov     rcx, rax; psz1
0x1800060d5  call    cs:__imp_StrCmpNW
0x1800060db  test    eax, eax
0x1800060dd  jnz     loc_180006192
0x1800060e3  lea     r9d, [r12+44h]
0x1800060e8  lea     r11, [rbp+0A0h+var_90]
0x1800060ec  mov     edi, r12d
0x1800060ef  add     r15, 18h
0x1800060f3  cmp     [r15], r12w
0x1800060f7  jz      loc_180006182
0x1800060fd  mov     eax, 3Eh ; '>'
0x180006102  cmp     ax, [r15]
0x180006106  jz      short loc_18000617E
0x180006108  test    r9d, r9d
0x18000610b  jle     loc_1800061D8
0x180006111  dec     r9d
0x180006114  mov     r10, r11
0x180006117  inc     r11
0x18000611a  mov     [r10], r12b
0x18000611d  mov     r8d, r12d
0x180006120  mov     dil, r12b
0x180006123  mov     ecx, r8d
0x180006126  movzx   edx, word ptr [r15+rcx*2]
0x18000612b  movzx   eax, dx
0x18000612e  sub     ax, word ptr [rbp+0A0h+var_118]
0x180006132  cmp     ax, 9
0x180006136  ja      short loc_18000613D
0x180006138  sub     dl, 30h ; '0'
0x18000613b  jmp     short loc_18000614A
0x18000613d  lea     eax, [rdx-41h]
0x180006140  cmp     ax, word ptr [rsp+1A0h+var_150]
0x180006145  ja      short loc_18000616D
0x180006147  sub     dl, 37h ; '7'
0x18000614a  lea     rax, qword_180021AD0
0x180006151  mov     ecx, [rax+rcx*4]
0x180006154  shl     dl, cl
0x180006156  or      dl, dil
0x180006159  mov     dil, dl
0x18000615c  mov     [r10], dl
0x18000615f  inc     r8d
0x180006162  cmp     r8d, 2
0x180006166  jl      short loc_180006123
0x180006168  mov     edi, r12d
0x18000616b  jmp     short loc_180006172
0x18000616d  mov     edi, 8007000Dh
0x180006172  add     r15, 4
0x180006176  test    edi, edi
0x180006178  jns     loc_1800060F3
0x18000617e  test    edi, edi
0x180006180  js      short loc_18000619A
0x180006182  mov     eax, 3Eh ; '>'
0x180006187  cmp     ax, [r15]
0x18000618b  jz      short loc_1800061DF
0x18000618d  mov     edi, 8007000Dh
0x180006192  test    edi, edi
0x180006194  jns     loc_18000641C
0x18000619a  mov     r15d, 1
0x1800061a0  cmp     edi, 80004005h
0x1800061a6  jz      loc_180006399
0x1800061ac  movzx   ecx, di
0x1800061af  sub     ecx, 5
0x1800061b2  jz      loc_18000638C
0x1800061b8  sub     ecx, 51Fh
0x1800061be  jz      loc_18000637F
0x1800061c4  cmp     ecx, 1
0x1800061c7  jz      loc_180006372
0x1800061cd  mov     r8d, 9E78h
0x1800061d3  jmp     loc_18000639F
0x1800061d8  mov     edi, 8007007Ah
0x1800061dd  jmp     short loc_180006192
0x1800061df  mov     r15, [rsp+1A0h+var_158]
0x1800061e4  mov     rax, [r15]
0x1800061e7  mov     rdi, [rax+80h]
0x1800061ee  cmp     [rsp+1A0h+var_168], r12d
0x1800061f3  jz      short loc_180006207
0x1800061f5  mov     rax, [rsp+1A0h+var_170]
0x1800061fa  lea     rcx, [rsp+1A0h+var_170]
0x1800061ff  mov     rax, [rax]
0x180006202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006207  mov     [rsp+1A0h+lParam], r12
0x18000620c  mov     [rsp+1A0h+var_168], 1
0x180006214  lea     r9, [rsp+1A0h+lParam]
0x180006219  mov     r8d, 2
0x18000621f  lea     rdx, [rbp+0A0h+var_90]
0x180006223  mov     rcx, r15
0x180006226  mov     rax, rdi
0x180006229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622e  mov     edi, eax
0x180006230  mov     r15d, 1
0x180006236  test    eax, eax
0x180006238  js      loc_1800061A0
0x18000623e  cmp     eax, r15d
0x180006241  jz      loc_18000637F
0x180006247  mov     rcx, [rsp+1A0h+lParam]
0x18000624c  mov     rax, [rcx]
0x18000624f  mov     r8d, r15d
0x180006252  mov     rdx, [rsi+10h]
0x180006256  mov     rax, [rax+78h]
0x18000625a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000625f  mov     edi, eax
0x180006261  test    eax, eax
0x180006263  js      loc_1800061A0
0x180006269  mov     rcx, [rsp+1A0h+lParam]
0x18000626e  mov     rax, [rcx]
0x180006271  mov     r8d, r15d
0x180006274  mov     rdx, [rsi+18h]
0x180006278  mov     rax, [rax+70h]
0x18000627c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006281  mov     edi, eax
0x180006283  test    eax, eax
0x180006285  js      loc_1800061A0
0x18000628b  mov     rdi, [rsi+20h]
0x18000628f  mov     eax, r12d
0x180006292  test    rdi, rdi
0x180006295  setnz   al
0x180006298  mov     [rbp+0A0h+var_B8], eax
0x18000629b  mov     [rbp+0A0h+var_B0], rdi
0x18000629f  lea     rax, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x1800062a6  mov     [rbp+0A0h+var_C0], rax
0x1800062aa  mov     eax, [rsp+1A0h+var_168]
0x1800062ae  mov     [rbp+0A0h+var_A0], eax
0x1800062b1  mov     [rsp+1A0h+var_168], r12d
0x1800062b6  mov     rcx, [rsp+1A0h+lParam]
0x1800062bb  mov     [rbp+0A0h+var_98], rcx
0x1800062bf  lea     r14, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x1800062c6  mov     [rbp+0A0h+var_A8], r14
0x1800062ca  mov     rax, [rcx]
0x1800062cd  mov     rax, [rax+8]
0x1800062d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d6  mov     rax, [rdi]
0x1800062d9  mov     rcx, rdi
0x1800062dc  mov     rax, [rax+8]
0x1800062e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e5  lea     ecx, [r15+2Fh]; uBytes
0x1800062e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800062ee  mov     rdx, rax
0x1800062f1  mov     [rsp+1A0h+var_158], rax
0x1800062f6  test    rax, rax
0x1800062f9  jz      short loc_18000632D
0x1800062fb  mov     rcx, [rsp+1A0h+lParam]
0x180006300  mov     rax, [rsi+20h]
0x180006304  mov     [rdx+8], rax
0x180006308  mov     [rdx+10h], rcx
0x18000630c  mov     [rdx+18h], r12
0x180006310  mov     [rdx+28h], r12
0x180006314  mov     [rdx+20h], r12
0x180006318  lea     rax, ??_7UndoAdd@@6B@; const UndoAdd::`vftable'
0x18000631f  mov     [rdx], rax
0x180006322  test    rdx, rdx
0x180006325  jz      short loc_180006330
0x180006327  mov     [rbp+0A0h+var_D8], r15d
0x18000632b  jmp     short loc_180006334
0x18000632d  mov     rdx, r12; void *
0x180006330  mov     [rbp+0A0h+var_D8], r12d
0x180006334  mov     [rbp+0A0h+var_D0], rdx
0x180006338  lea     rax, ??_7?$autoptr@VUndoDelete@@@@6B@; const autoptr<UndoDelete>::`vftable'
0x18000633f  mov     [rbp+0A0h+var_E0], rax
0x180006343  mov     rcx, [rsi+28h]; this
0x180006347  mov     [rdx+18h], rcx
0x18000634b  call    ?Append@PointerList@@QEAAXPEBX@Z; PointerList::Append(void const *)
0x180006350  nop
0x180006351  mov     r9, [rsp+1A0h+lParam]; lParam
0x180006356  xor     r8d, r8d; wParam
0x180006359  mov     edx, 5F6h; Msg
0x18000635e  mov     rcx, [rsi+40h]; hWnd
0x180006362  call    cs:__imp_SendMessageW
0x180006368  mov     [rsp+1A0h+var_168], r12d
0x18000636d  jmp     loc_180006429
0x180006372  mov     edi, 31h ; '1'
0x180006377  mov     r8d, 9E67h
0x18000637d  jmp     short loc_1800063A4
  ... truncated ...
```
