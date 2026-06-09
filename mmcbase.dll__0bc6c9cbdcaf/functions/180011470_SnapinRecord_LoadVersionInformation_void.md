# SnapinRecord::LoadVersionInformation(void)

- ea: `0x180011470`
- end: `0x1800119d6`
- name: `?LoadVersionInformation@SnapinRecord@@AEAAXXZ`
- size: `1382`
- prototype: `void __fastcall(SnapinRecord *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180011290`

## callees

- `0x1800064b4`
- `0x18000715c`
- `0x180007310`
- `0x180008630`
- `0x180010fe0`
- `0x180011028`
- `0x180011118`
- `0x180011470`
- `0x1800121b4`
- `0x180012260`
- `0x18001d010`

## import_xrefs

- `msvcrt!free` at `0x1800119bf`
- `msvcrt!free` at `0x1800119bf`
- `msvcrt!malloc` at `0x1800115a3`
- `msvcrt!malloc` at `0x1800115a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011628`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180011707`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180011729`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180011707`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180011729`
- `VERSION!GetFileVersionInfoSizeW` at `0x18001152a`
- `VERSION!GetFileVersionInfoSizeW` at `0x18001152a`
- `VERSION!GetFileVersionInfoW` at `0x180011615`
- `VERSION!GetFileVersionInfoW` at `0x180011615`

## string_xrefs

- `0x180011966`: `Comments`
- `0x18001187f`: `CompanyName`

## pseudocode

```c
void __fastcall SnapinRecord::LoadVersionInformation(SnapinRecord *this)
{
  unsigned __int16 *v1; // r15
  unsigned int v3; // r11d
  unsigned int v4; // r11d
  unsigned int v5; // r11d
  unsigned int v6; // r11d
  unsigned int v7; // r11d
  __int64 v8; // rax
  const WCHAR *v9; // rax
  DWORD FileVersionInfoSizeW; // eax
  DWORD v11; // edi
  __int64 v12; // rbx
  int v13; // eax
  int v14; // edx
  void *v15; // r14
  DWORD v16; // ebx
  const WCHAR *v17; // rax
  SnapinRecord *v18; // rcx
  signed int LastError; // eax
  char v20; // r15
  __int64 v21; // rbx
  int v22; // eax
  int v23; // r8d
  int VersionValue; // eax
  LANGID UserDefaultLangID; // ax
  LANGID v26; // ax
  unsigned int v27; // edx
  void *v28; // r11
  unsigned int v29; // edx
  void *v30; // r11
  unsigned int *v31; // r11
  unsigned int v32; // eax
  int v33; // eax
  SnapinRecord *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  unsigned __int16 *v37; // rbx
  int v38; // eax
  SnapinRecord *v39; // rcx
  int v40; // eax
  SnapinRecord *v41; // rcx
  int v42; // eax
  SnapinRecord *v43; // rcx
  int v44; // eax
  SnapinRecord *v45; // rcx
  int v46; // eax
  SnapinRecord *v47; // rcx
  unsigned __int16 *v48; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v49; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v50; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v51; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v52; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v53; // [rsp+28h] [rbp-30h]
  void **v54; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v55; // [rsp+38h] [rbp-20h]
  __int64 v56; // [rsp+40h] [rbp-18h]
  int v57; // [rsp+48h] [rbp-10h]
  unsigned __int16 *v58; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v59; // [rsp+A8h] [rbp+50h] BYREF
  DWORD dwHandle; // [rsp+B0h] [rbp+58h] BYREF
  void *v61; // [rsp+B8h] [rbp+60h] BYREF

  v1 = (unsigned __int16 *)((char *)this + 2872);
  v58 = (unsigned __int16 *)((char *)this + 2872);
  StringCchCopyW((unsigned __int16 *)this + 1436, 0x80u, L"Unknown");
  StringCchCopyW((unsigned __int16 *)this + 1052, v3, L"Unknown");
  StringCchCopyW((unsigned __int16 *)this + 924, v4, L"Unknown");
  StringCchCopyW((unsigned __int16 *)this + 1180, v5, L"Unknown");
  StringCchCopyW((unsigned __int16 *)this + 1308, v6, L"Unknown");
  StringCchCopyW((unsigned __int16 *)this + 1564, v7, L"Unknown");
  v8 = *(_QWORD *)this;
  dwHandle = 0;
  v9 = (const WCHAR *)(*(__int64 (__fastcall **)(SnapinRecord *))(v8 + 24))(this);
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(v9, &dwHandle);
  v11 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      v12 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 24LL))(this);
      v13 = (**(__int64 (__fastcall ***)(SnapinRecord *))this)(this);
      v14 = 33;
LABEL_5:
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v14,
        (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
        v13,
        v12);
      return;
    }
    return;
  }
  v15 = malloc(FileVersionInfoSizeW);
  if ( v15 )
  {
    v16 = dwHandle;
    v17 = (const WCHAR *)(*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 24LL))(this);
    if ( !GetFileVersionInfoW(v17, v16, v11, v15) )
    {
      LastError = GetLastError();
      v20 = LastError;
      if ( LastError > 0 )
        v20 = LastError;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v21 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 24LL))(this);
        v22 = (**(__int64 (__fastcall ***)(SnapinRecord *))this)(this);
        WPP_SF_SSd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, v23, v22, v21, v20);
      }
      v1 = v58;
    }
    v61 = 0;
    v59 = 0;
    LODWORD(v58) = 0;
    VersionValue = SnapinRecord::GetVersionValue(
                     v18,
                     (unsigned __int8 *)v15,
                     L"\\VarFileInfo\\",
                     L"Translation",
                     &v61,
                     &v59);
    if ( VersionValue < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          36,
          WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          (unsigned int)VersionValue);
      goto LABEL_57;
    }
    UserDefaultLangID = GetUserDefaultLangID();
    if ( GetLanguageCode(v61, v59, UserDefaultLangID, (unsigned int *)&v58, 0)
      || (v26 = GetUserDefaultLangID(), GetLanguageCode(v61, v59, v26, (unsigned int *)&v58, 1))
      || GetLanguageCode(v28, v27, 0, (unsigned int *)&v58, 1)
      || GetLanguageCode(v30, v29, 9u, (unsigned int *)&v58, 1) )
    {
      v32 = (unsigned int)v58;
    }
    else
    {
      v32 = *v31;
    }
    v54 = &CStr::`vftable';
    v56 = 0;
    v55 = (unsigned __int16 *)&CStr::s_rgwchEmptyStringBuffer;
    v57 = 0;
    v33 = CStr::Format((CStr *)&v54, L"\\StringFileInfo\\%04X%04X\\", (unsigned __int16)v32, HIWORD(v32));
    if ( v33 >= 0 )
    {
      v37 = v55;
      v38 = SnapinRecord::GetVersionValue(
              v34,
              (unsigned __int8 *)v15,
              v55,
              L"FileDescription",
              (unsigned __int16 *)this + 924,
              v48);
      if ( v38 < 0 )
      {
        v39 = (SnapinRecord *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            38,
            WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
            (unsigned int)v38);
      }
      v40 = SnapinRecord::GetVersionValue(
              v39,
              (unsigned __int8 *)v15,
              v37,
              L"FileVersion",
              (unsigned __int16 *)this + 1052,
              v49);
      if ( v40 < 0 )
      {
        v41 = (SnapinRecord *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            39,
            WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
            (unsigned int)v40);
      }
      v42 = SnapinRecord::GetVersionValue(v41, (unsigned __int8 *)v15, v37, L"CompanyName", v1, v50);
      if ( v42 < 0 )
      {
        v43 = (SnapinRecord *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            40,
            WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
            (unsigned int)v42);
      }
      v44 = SnapinRecord::GetVersionValue(
              v43,
              (unsigned __int8 *)v15,
              v37,
              L"ProductName",
              (unsigned __int16 *)this + 1180,
              v51);
      if ( v44 < 0 )
      {
        v45 = (SnapinRecord *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            41,
            WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
            (unsigned int)v44);
      }
      v46 = SnapinRecord::GetVersionValue(
              v45,
              (unsigned __int8 *)v15,
              v37,
              L"ProductVersion",
              (unsigned __int16 *)this + 1308,
              v52);
      if ( v46 < 0 )
      {
        v47 = (SnapinRecord *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            42,
            WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
            (unsigned int)v46);
      }
      v33 = SnapinRecord::GetVersionValue(
              v47,
              (unsigned __int8 *)v15,
              v37,
              L"Comments",
              (unsigned __int16 *)this + 1564,
              v53);
      if ( v33 >= 0 )
        goto LABEL_56;
      v35 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
        goto LABEL_56;
      v36 = 43;
    }
    else
    {
      v35 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 3u )
        goto LABEL_56;
      v36 = 37;
    }
    WPP_SF_d(*(_QWORD *)(v35 + 16), v36, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, (unsigned int)v33);
LABEL_56:
    v54 = &CStr::`vftable';
    CStr::Empty((CStr *)&v54);
LABEL_57:
    free(v15);
    return;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v12 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 24LL))(this);
    v13 = (**(__int64 (__fastcall ***)(SnapinRecord *))this)(this);
    v14 = 34;
    goto LABEL_5;
  }
}

```

## disassembly

```asm
0x180011470  push    rbp
0x180011472  push    rbx
0x180011473  push    rsi
0x180011474  push    rdi
0x180011475  push    r12
0x180011477  push    r13
0x180011479  push    r14
0x18001147b  push    r15
0x18001147d  mov     rbp, rsp
0x180011480  sub     rsp, 58h
0x180011484  lea     r15, [rcx+0B38h]
0x18001148b  mov     rsi, rcx
0x18001148e  lea     rbx, ?s_szUnknown@SnapinRecord@@0QBGB; "Unknown"
0x180011495  mov     [rbp+arg_0], r15
0x180011499  mov     r11d, 80h
0x18001149f  mov     r8, rbx; unsigned __int16 *
0x1800114a2  mov     edx, r11d; unsigned __int64
0x1800114a5  mov     rcx, r15; unsigned __int16 *
0x1800114a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800114ad  lea     r13, [rsi+838h]
0x1800114b4  mov     r8, rbx; unsigned __int16 *
0x1800114b7  mov     rcx, r13; unsigned __int16 *
0x1800114ba  mov     edx, r11d; unsigned __int64
0x1800114bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800114c2  lea     r12, [rsi+738h]
0x1800114c9  mov     r8, rbx; unsigned __int16 *
0x1800114cc  mov     rcx, r12; unsigned __int16 *
0x1800114cf  mov     edx, r11d; unsigned __int64
0x1800114d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800114d7  lea     rcx, [rsi+938h]; unsigned __int16 *
0x1800114de  mov     r8, rbx; unsigned __int16 *
0x1800114e1  mov     edx, r11d; unsigned __int64
0x1800114e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800114e9  lea     rcx, [rsi+0A38h]; unsigned __int16 *
0x1800114f0  mov     r8, rbx; unsigned __int16 *
0x1800114f3  mov     edx, r11d; unsigned __int64
0x1800114f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800114fb  lea     rcx, [rsi+0C38h]; unsigned __int16 *
0x180011502  mov     r8, rbx; unsigned __int16 *
0x180011505  mov     edx, r11d; unsigned __int64
0x180011508  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001150d  mov     rax, [rsi]
0x180011510  mov     rcx, rsi
0x180011513  mov     [rbp+dwHandle], 0
0x18001151a  mov     rax, [rax+18h]
0x18001151e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011523  mov     rcx, rax; lptstrFilename
0x180011526  lea     rdx, [rbp+dwHandle]; lpdwHandle
0x18001152a  call    cs:__imp_GetFileVersionInfoSizeW
0x180011530  mov     edi, eax
0x180011532  test    eax, eax
0x180011534  jnz     short loc_1800115A0
0x180011536  mov     rax, cs:WPP_GLOBAL_Control
0x18001153d  lea     rdi, WPP_GLOBAL_Control
0x180011544  cmp     rax, rdi
0x180011547  jz      loc_1800119C5
0x18001154d  cmp     byte ptr [rax+19h], 3
0x180011551  jb      loc_1800119C5
0x180011557  mov     rax, [rsi]
0x18001155a  mov     rcx, rsi
0x18001155d  mov     rax, [rax+18h]
0x180011561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011566  mov     rcx, [rsi]
0x180011569  mov     rbx, rax
0x18001156c  mov     rax, [rcx]
0x18001156f  mov     rcx, rsi
0x180011572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011577  mov     edx, 21h ; '!'
0x18001157c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011583  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x18001158a  mov     r9, rax
0x18001158d  mov     [rsp+58h+var_38], rbx
0x180011592  mov     rcx, [rcx+10h]
0x180011596  call    WPP_SF_SS
0x18001159b  jmp     loc_1800119C5
0x1800115a0  mov     rcx, rdi; Size
0x1800115a3  call    cs:__imp_malloc
0x1800115a9  mov     r14, rax
0x1800115ac  test    rax, rax
0x1800115af  jnz     short loc_1800115F8
0x1800115b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800115b8  lea     rdi, WPP_GLOBAL_Control
0x1800115bf  cmp     rax, rdi
0x1800115c2  jz      loc_1800119C5
0x1800115c8  cmp     byte ptr [rax+19h], 2
0x1800115cc  jb      loc_1800119C5
0x1800115d2  mov     rax, [rsi]
0x1800115d5  mov     rcx, rsi
0x1800115d8  mov     rax, [rax+18h]
0x1800115dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115e1  mov     rcx, [rsi]
0x1800115e4  mov     rbx, rax
0x1800115e7  mov     rax, [rcx]
0x1800115ea  mov     rcx, rsi
0x1800115ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115f2  lea     edx, [r14+22h]
0x1800115f6  jmp     short loc_18001157C
0x1800115f8  mov     rax, [rsi]
0x1800115fb  mov     rcx, rsi
0x1800115fe  mov     ebx, [rbp+dwHandle]
0x180011601  mov     rax, [rax+18h]
0x180011605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160a  mov     r9, r14; lpData
0x18001160d  mov     r8d, edi; dwLen
0x180011610  mov     edx, ebx; dwHandle
0x180011612  mov     rcx, rax; lptstrFilename
0x180011615  call    cs:__imp_GetFileVersionInfoW
0x18001161b  xor     ebx, ebx
0x18001161d  lea     rdi, WPP_GLOBAL_Control
0x180011624  test    eax, eax
0x180011626  jnz     short loc_18001169A
0x180011628  call    cs:__imp_GetLastError
0x18001162e  mov     r15d, eax
0x180011631  test    eax, eax
0x180011633  jle     short loc_180011640
0x180011635  movzx   r15d, ax
0x180011639  or      r15d, 80070000h
0x180011640  mov     rax, cs:WPP_GLOBAL_Control
0x180011647  cmp     rax, rdi
0x18001164a  jz      short loc_180011696
0x18001164c  cmp     byte ptr [rax+19h], 2
0x180011650  jb      short loc_180011696
0x180011652  mov     rax, [rsi]
0x180011655  mov     rcx, rsi
0x180011658  mov     rax, [rax+18h]
0x18001165c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011661  mov     rcx, [rsi]
0x180011664  mov     rbx, rax
0x180011667  mov     rax, [rcx]
0x18001166a  mov     rcx, rsi
0x18001166d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011672  mov     rcx, cs:WPP_GLOBAL_Control
0x180011679  mov     edx, 23h ; '#'
0x18001167e  mov     dword ptr [rsp+58h+var_30], r15d
0x180011683  mov     r9, rax
0x180011686  mov     [rsp+58h+var_38], rbx
0x18001168b  mov     rcx, [rcx+10h]
0x18001168f  call    WPP_SF_SSd
0x180011694  xor     ebx, ebx
0x180011696  mov     r15, [rbp+arg_0]
0x18001169a  lea     rax, [rbp+arg_8]
0x18001169e  mov     [rbp+arg_18], rbx
0x1800116a2  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x1800116a7  lea     r9, aTranslation; "Translation"
0x1800116ae  lea     rax, [rbp+arg_18]
0x1800116b2  mov     [rbp+arg_8], ebx
0x1800116b5  lea     r8, aVarfileinfo; "\\VarFileInfo\\"
0x1800116bc  mov     [rsp+58h+var_38], rax; void **
0x1800116c1  mov     rdx, r14; unsigned __int8 *
0x1800116c4  mov     dword ptr [rbp+arg_0], ebx
0x1800116c7  call    ?GetVersionValue@SnapinRecord@@AEAAJPEAEPEBG1AEAPEAXAEAI@Z; SnapinRecord::GetVersionValue(uchar *,ushort const *,ushort const *,void * &,uint &)
0x1800116cc  test    eax, eax
0x1800116ce  jns     short loc_180011707
0x1800116d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116d7  cmp     rcx, rdi
0x1800116da  jz      loc_1800119BC
0x1800116e0  cmp     byte ptr [rcx+19h], 3
0x1800116e4  jb      loc_1800119BC
0x1800116ea  mov     rcx, [rcx+10h]
0x1800116ee  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x1800116f5  mov     edx, 24h ; '$'
0x1800116fa  mov     r9d, eax
0x1800116fd  call    WPP_SF_d
0x180011702  jmp     loc_1800119BC
0x180011707  call    cs:__imp_GetUserDefaultLangID
0x18001170d  mov     rcx, [rbp+arg_18]; void *
0x180011711  lea     r9, [rbp+arg_0]; unsigned int *
0x180011715  mov     edx, [rbp+arg_8]; unsigned int
0x180011718  movzx   r8d, ax; unsigned __int16
0x18001171c  mov     byte ptr [rsp+58h+var_38], bl; bool
0x180011720  call    ?GetLanguageCode@@YA_NPEAXIGAEAK_N@Z; GetLanguageCode(void *,uint,ushort,ulong &,bool)
0x180011725  test    al, al
0x180011727  jnz     short loc_180011787
0x180011729  call    cs:__imp_GetUserDefaultLangID
0x18001172f  mov     r11, [rbp+arg_18]
0x180011733  lea     r9, [rbp+arg_0]; unsigned int *
0x180011737  mov     edx, [rbp+arg_8]; unsigned int
0x18001173a  mov     rcx, r11; void *
0x18001173d  movzx   r8d, ax; unsigned __int16
0x180011741  mov     byte ptr [rsp+58h+var_38], 1; bool
0x180011746  call    ?GetLanguageCode@@YA_NPEAXIGAEAK_N@Z; GetLanguageCode(void *,uint,ushort,ulong &,bool)
0x18001174b  test    al, al
0x18001174d  jnz     short loc_180011787
0x18001174f  xor     r8d, r8d; unsigned __int16
0x180011752  mov     byte ptr [rsp+58h+var_38], 1; bool
0x180011757  lea     r9, [rbp+arg_0]; unsigned int *
0x18001175b  mov     rcx, r11; void *
0x18001175e  call    ?GetLanguageCode@@YA_NPEAXIGAEAK_N@Z; GetLanguageCode(void *,uint,ushort,ulong &,bool)
0x180011763  test    al, al
0x180011765  jnz     short loc_180011787
0x180011767  mov     r8d, 9; unsigned __int16
0x18001176d  mov     byte ptr [rsp+58h+var_38], 1; bool
0x180011772  lea     r9, [rbp+arg_0]; unsigned int *
0x180011776  mov     rcx, r11; void *
0x180011779  call    ?GetLanguageCode@@YA_NPEAXIGAEAK_N@Z; GetLanguageCode(void *,uint,ushort,ulong &,bool)
0x18001177e  test    al, al
0x180011780  jnz     short loc_180011787
0x180011782  mov     eax, [r11]
0x180011785  jmp     short loc_18001178A
0x180011787  mov     eax, dword ptr [rbp+arg_0]
0x18001178a  lea     rcx, ??_7CStr@@6B@; const CStr::`vftable'
0x180011791  movzx   r8d, ax
0x180011795  mov     [rbp+var_28], rcx
0x180011799  lea     rdx, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\"
0x1800117a0  lea     rcx, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x1800117a7  mov     [rbp+var_18], 0
0x1800117af  mov     r9d, eax
0x1800117b2  mov     [rbp+var_20], rcx
0x1800117b6  lea     rcx, [rbp+var_28]; this
0x1800117ba  shr     r9d, 10h
0x1800117be  mov     [rbp+var_10], ebx
0x1800117c1  call    ?Format@CStr@@QEAAJPEBGZZ; CStr::Format(ushort const *,...)
0x1800117c6  test    eax, eax
0x1800117c8  jns     short loc_1800117EE
0x1800117ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117d1  cmp     rcx, rdi
0x1800117d4  jz      loc_1800119A8
0x1800117da  cmp     byte ptr [rcx+19h], 3
0x1800117de  jb      loc_1800119A8
0x1800117e4  mov     edx, 25h ; '%'
0x1800117e9  jmp     loc_180011995
0x1800117ee  mov     rbx, [rbp+var_20]
0x1800117f2  lea     r9, aFiledescriptio; "FileDescription"
0x1800117f9  mov     r8, rbx; unsigned __int16 *
0x1800117fc  mov     [rsp+58h+var_38], r12; unsigned __int16 *
0x180011801  mov     rdx, r14; unsigned __int8 *
0x180011804  call    ?GetVersionValue@SnapinRecord@@AEAAJPEAEPEBG1PEAG_K@Z; SnapinRecord::GetVersionValue(uchar *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180011809  mov     r12b, 5
0x18001180c  test    eax, eax
0x18001180e  jns     short loc_18001183A
0x180011810  mov     rcx, cs:WPP_GLOBAL_Control
0x180011817  cmp     rcx, rdi
0x18001181a  jz      short loc_18001183A
0x18001181c  cmp     [rcx+19h], r12b
0x180011820  jb      short loc_18001183A
0x180011822  mov     rcx, [rcx+10h]
0x180011826  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x18001182d  mov     edx, 26h ; '&'
0x180011832  mov     r9d, eax
0x180011835  call    WPP_SF_d
0x18001183a  lea     r9, aFileversion; "FileVersion"
0x180011841  mov     [rsp+58h+var_38], r13; unsigned __int16 *
0x180011846  mov     r8, rbx; unsigned __int16 *
0x180011849  mov     rdx, r14; unsigned __int8 *
0x18001184c  call    ?GetVersionValue@SnapinRecord@@AEAAJPEAEPEBG1PEAG_K@Z; SnapinRecord::GetVersionValue(uchar *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180011851  test    eax, eax
0x180011853  jns     short loc_18001187F
0x180011855  mov     rcx, cs:WPP_GLOBAL_Control
0x18001185c  cmp     rcx, rdi
0x18001185f  jz      short loc_18001187F
0x180011861  cmp     [rcx+19h], r12b
0x180011865  jb      short loc_18001187F
0x180011867  mov     rcx, [rcx+10h]
0x18001186b  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180011872  mov     edx, 27h ; '''
0x180011877  mov     r9d, eax
0x18001187a  call    WPP_SF_d
0x18001187f  lea     r9, aCompanyname; "CompanyName"
0x180011886  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x18001188b  mov     r8, rbx; unsigned __int16 *
0x18001188e  mov     rdx, r14; unsigned __int8 *
0x180011891  call    ?GetVersionValue@SnapinRecord@@AEAAJPEAEPEBG1PEAG_K@Z; SnapinRecord::GetVersionValue(uchar *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180011896  test    eax, eax
0x180011898  jns     short loc_1800118C4
0x18001189a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118a1  cmp     rcx, rdi
0x1800118a4  jz      short loc_1800118C4
0x1800118a6  cmp     [rcx+19h], r12b
0x1800118aa  jb      short loc_1800118C4
0x1800118ac  mov     rcx, [rcx+10h]
0x1800118b0  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x1800118b7  mov     edx, 28h ; '('
0x1800118bc  mov     r9d, eax
0x1800118bf  call    WPP_SF_d
0x1800118c4  lea     rax, [rsi+938h]
0x1800118cb  mov     r8, rbx; unsigned __int16 *
0x1800118ce  lea     r9, aProductname; "ProductName"
0x1800118d5  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800118da  mov     rdx, r14; unsigned __int8 *
0x1800118dd  call    ?GetVersionValue@SnapinRecord@@AEAAJPEAEPEBG1PEAG_K@Z; SnapinRecord::GetVersionValue(uchar *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x1800118e2  test    eax, eax
0x1800118e4  jns     short loc_180011910
0x1800118e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118ed  cmp     rcx, rdi
0x1800118f0  jz      short loc_180011910
0x1800118f2  cmp     [rcx+19h], r12b
0x1800118f6  jb      short loc_180011910
0x1800118f8  mov     rcx, [rcx+10h]
0x1800118fc  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180011903  mov     edx, 29h ; ')'
0x180011908  mov     r9d, eax
0x18001190b  call    WPP_SF_d
0x180011910  lea     rax, [rsi+0A38h]
0x180011917  mov     r8, rbx; unsigned __int16 *
0x18001191a  lea     r9, aProductversion; "ProductVersion"
0x180011921  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180011926  mov     rdx, r14; unsigned __int8 *
0x180011929  call    ?GetVersionValue@SnapinRecord@@AEAAJPEAEPEBG1PEAG_K@Z; SnapinRecord::GetVersionValue(uchar *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x18001192e  test    eax, eax
0x180011930  jns     short loc_18001195C
  ... truncated ...
```
