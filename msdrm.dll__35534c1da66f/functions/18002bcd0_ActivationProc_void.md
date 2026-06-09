# ActivationProc(void *)

- ea: `0x18002bcd0`
- end: `0x18002c0ee`
- name: `?ActivationProc@@YAIPEAX@Z`
- size: `1054`
- prototype: `unsigned int __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180017358`
- `0x18002bcd0`
- `0x18002dc18`
- `0x18002e1c0`
- `0x18002e9a4`
- `0x18002ead8`
- `0x18002f020`
- `0x18002f1a0`
- `0x18002f97c`
- `0x18002f9d4`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bece`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bf85`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bece`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bf85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c04e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c04e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c09a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c0a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c09a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c0a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18002bceb`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18002bceb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002c0d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002c0d5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002bd3c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002bd3c`
- `api-ms-win-core-localization-obsolete-l1-1-0!GetUserDefaultUILanguage` at `0x18002beea`
- `api-ms-win-core-localization-obsolete-l1-1-0!GetUserDefaultUILanguage` at `0x18002beea`
- `ATL!__imp_AtlModuleInit` at `0x18002bd1f`
- `ATL!__imp_AtlModuleInit` at `0x18002bd1f`
- `ATL!__imp_AtlModuleTerm` at `0x18002c0c6`
- `ATL!__imp_AtlModuleTerm` at `0x18002c0c6`
- `USER32!GetActiveWindow` at `0x18002bf9c`
- `USER32!GetActiveWindow` at `0x18002bf9c`

## string_xrefs

- `0x18002bce4`: `msdrm.dll`
- `0x18002c008`: `http://go.microsoft.com/fwlink/?LinkId=5998&LANGID=%d`

## pseudocode

```c
__int64 __fastcall ActivationProc(unsigned int *Block)
{
  HMODULE ModuleHandleW; // rax
  HRESULT v3; // eax
  unsigned __int16 *v4; // r15
  void (__fastcall *v5)(bool, _QWORD, unsigned __int16 *, _QWORD); // r13
  int v6; // r12d
  unsigned __int16 *v7; // rbp
  CDRMCTridentDlg *v8; // rax
  int *v9; // rbx
  CDRMCTridentDlg *v10; // rax
  CDRMCTridentDlg *v11; // rdi
  int v12; // esi
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  int v18; // eax
  HWND ActiveWindow; // rax
  int Certificate; // eax
  unsigned __int16 *v21; // rax
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  int v26; // [rsp+80h] [rbp+8h]
  unsigned __int16 *v27; // [rsp+88h] [rbp+10h] BYREF
  struct IDispatch *v28; // [rsp+90h] [rbp+18h] BYREF
  CDRMCTridentDlg *v29; // [rsp+98h] [rbp+20h]

  ModuleHandleW = GetModuleHandleW(L"msdrm.dll");
  _Module = 248;
  qword_180084CA8 = (__int64)&ATL::GUID_ATLVer30;
  dword_180084C90 = 769;
  if ( (int)AtlModuleInit(&_Module, 0, ModuleHandleW) >= 0 )
    dword_180084CD0 = 1;
  v3 = CoInitializeEx(0, 2u);
  if ( !v3 || (v26 = 0, v3 == 1) )
    v26 = 1;
  v28 = 0;
  v4 = 0;
  v27 = 0;
  if ( Block )
  {
    v5 = (void (__fastcall *)(bool, _QWORD, unsigned __int16 *, _QWORD))*((_QWORD *)Block + 7);
    v6 = *Block;
    v7 = 0;
    v8 = (CDRMCTridentDlg *)operator new(0x70u);
    v29 = v8;
    v9 = (int *)v8;
    if ( !v8 )
    {
      v12 = -2147024882;
      goto LABEL_37;
    }
    *((_QWORD *)v8 + 9) = 100;
    *(_QWORD *)v8 = &CuDRMActivation::`vftable';
    *((_DWORD *)v8 + 2) = -2147168447;
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 11) = 0;
    *((_QWORD *)v8 + 12) = 0;
    *((_DWORD *)v8 + 26) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_BYTE *)v8 + 108) = 1;
    v10 = (CDRMCTridentDlg *)operator new(0x50u);
    v29 = v10;
    v11 = v10;
    if ( !v10 )
    {
      v12 = -2147024882;
      goto LABEL_35;
    }
    *((_QWORD *)v10 + 1) = 0;
    *((_QWORD *)v10 + 5) = 0;
    *((_QWORD *)v10 + 6) = 0;
    *(_QWORD *)v10 = &CDRMCTridentDlg::`vftable';
    *((_QWORD *)v10 + 8) = 0;
    *((_QWORD *)v10 + 7) = 0;
    *((_QWORD *)v10 + 9) = 0;
    v12 = CDRMCTridentDlg::Init(v10);
    if ( v12 < 0
      || (v12 = (**(__int64 (__fastcall ***)(int *, GUID *, struct IDispatch **))v9)(v9, &IID_IDispatch, &v28), v12 < 0)
      || (CDRMCTridentDlg::SetExternalObject(v11, v13, v28),
          v12 = CuDRMActivation::SetUserID(
                  (CuDRMActivation *)v9,
                  *((unsigned __int16 **)Block + 1),
                  *((unsigned __int16 **)Block + 2)),
          v12 < 0)
      || (v12 = CuDRMActivation::SetServer((CuDRMActivation *)v9, *((unsigned __int16 **)Block + 3)), v12 < 0) )
    {
LABEL_31:
      (*(void (__fastcall **)(CDRMCTridentDlg *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 1);
LABEL_35:
      CuDRMActivation::~CuDRMActivation((CuDRMActivation *)v9);
      operator delete(v9);
LABEL_37:
      operator delete(v7);
      v22 = (void *)*((_QWORD *)Block + 10);
      if ( v22 )
        SetEvent(v22);
      if ( v5 )
        v5((v6 & 1) == 0, (unsigned int)v12, v4, *((_QWORD *)Block + 8));
      operator delete(*((void **)Block + 3));
      operator delete(*((void **)Block + 1));
      operator delete(*((void **)Block + 2));
      v23 = (void *)*((_QWORD *)Block + 4);
      if ( v23 )
        CloseHandle(v23);
      v24 = (void *)*((_QWORD *)Block + 5);
      if ( v24 )
        CloseHandle(v24);
      operator delete(Block);
      operator delete(v4);
      goto LABEL_46;
    }
    *((_QWORD *)v9 + 12) = *((_QWORD *)Block + 4);
    *((_QWORD *)v9 + 7) = *((_QWORD *)Block + 8);
    *((_QWORD *)v9 + 6) = v5;
    if ( !WaitForSingleObject(*((HANDLE *)Block + 4), 0) )
    {
LABEL_14:
      v12 = -2147168447;
      goto LABEL_31;
    }
    if ( !Block[19] )
      Block[19] = GetUserDefaultUILanguage();
    v14 = *((_QWORD *)Block + 3);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      v16 = v15 + 42;
      v17 = (unsigned __int16 *)operator new[](saturated_mul(v15 + 42, 2u));
      v7 = v17;
      if ( !v17 )
        goto LABEL_21;
      v18 = StringCchPrintfW(
              v17,
              v16,
              L"%s%s%d",
              *((_QWORD *)Block + 3),
              L"/PassportRedirector.aspx?LANGID=",
              Block[19]);
    }
    else
    {
      v21 = (unsigned __int16 *)operator new[](0x7Eu);
      v7 = v21;
      if ( !v21 )
      {
LABEL_21:
        v12 = -2147024882;
        goto LABEL_31;
      }
      v18 = StringCchPrintfW(v21, 0x3Fu, L"http://go.microsoft.com/fwlink/?LinkId=5998&LANGID=%d", Block[19]);
    }
    v12 = v18;
    if ( v18 < 0 )
      goto LABEL_31;
    v12 = CDRMCTridentDlg::SetURL(v11, v7);
    if ( v12 < 0 )
      goto LABEL_31;
    if ( WaitForSingleObject(*((HANDLE *)Block + 4), 0) )
    {
      ActiveWindow = (HWND)*((_QWORD *)Block + 6);
      if ( !ActiveWindow )
      {
        ActiveWindow = GetActiveWindow();
        *((_QWORD *)Block + 6) = ActiveWindow;
      }
      v12 = CDRMCTridentDlg::LaunchTrident(v11, ActiveWindow);
      if ( v12 >= 0 )
      {
        Certificate = CuDRMActivation::GetCertificate((CuDRMActivation *)v9, &v27);
        v4 = v27;
        v12 = Certificate;
        if ( Certificate >= 0 )
          v12 = v9[2];
      }
      goto LABEL_31;
    }
    goto LABEL_14;
  }
LABEL_46:
  AtlModuleTerm(&_Module);
  if ( v26 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18002bcd0  push    rbx
0x18002bcd2  push    rbp
0x18002bcd3  push    rsi
0x18002bcd4  push    rdi
0x18002bcd5  push    r12
0x18002bcd7  push    r13
0x18002bcd9  push    r14
0x18002bcdb  push    r15
0x18002bcdd  sub     rsp, 38h
0x18002bce1  mov     r14, rcx
0x18002bce4  lea     rcx, ?g_wszMODULENAME@@3QBGB; "msdrm.dll"
0x18002bceb  call    cs:__imp_GetModuleHandleW
0x18002bcf1  lea     rcx, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x18002bcf8  mov     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18002bd02  mov     cs:qword_180084CA8, rcx
0x18002bd09  mov     r8, rax
0x18002bd0c  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18002bd13  mov     cs:dword_180084C90, 301h
0x18002bd1d  xor     edx, edx
0x18002bd1f  call    cs:__imp_AtlModuleInit
0x18002bd25  xor     esi, esi
0x18002bd27  test    eax, eax
0x18002bd29  js      short loc_18002BD35
0x18002bd2b  mov     cs:dword_180084CD0, 1
0x18002bd35  mov     edx, 2; dwCoInit
0x18002bd3a  xor     ecx, ecx; pvReserved
0x18002bd3c  call    cs:__imp_CoInitializeEx
0x18002bd42  test    eax, eax
0x18002bd44  jz      short loc_18002BD52
0x18002bd46  mov     [rsp+78h+arg_0], esi
0x18002bd4d  cmp     eax, 1
0x18002bd50  jnz     short loc_18002BD5D
0x18002bd52  mov     [rsp+78h+arg_0], 1
0x18002bd5d  mov     [rsp+78h+arg_10], rsi
0x18002bd65  mov     r15, rsi
0x18002bd68  mov     [rsp+78h+arg_8], rsi
0x18002bd70  test    r14, r14
0x18002bd73  jz      loc_18002C0BF
0x18002bd79  mov     r13, [r14+38h]
0x18002bd7d  mov     ecx, 70h ; 'p'; Size
0x18002bd82  mov     r12d, [r14]
0x18002bd85  mov     rbp, rsi
0x18002bd88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bd8d  mov     [rsp+78h+arg_18], rax
0x18002bd95  mov     rbx, rax
0x18002bd98  test    rax, rax
0x18002bd9b  jz      loc_18002C038
0x18002bda1  mov     qword ptr [rbx+48h], 64h ; 'd'
0x18002bda9  lea     rax, ??_7CuDRMActivation@@6B@; const CuDRMActivation::`vftable'
0x18002bdb0  mov     [rbx], rax
0x18002bdb3  mov     dword ptr [rbx+8], 8004CF41h
0x18002bdba  mov     [rbx+10h], rsi
0x18002bdbe  mov     [rbx+18h], rsi
0x18002bdc2  mov     [rbx+20h], rsi
0x18002bdc6  mov     [rbx+30h], rsi
0x18002bdca  mov     [rbx+38h], rsi
0x18002bdce  mov     [rbx+40h], rsi
0x18002bdd2  mov     [rbx+50h], rsi
0x18002bdd6  mov     [rbx+58h], rsi
0x18002bdda  mov     [rbx+60h], rsi
0x18002bdde  mov     [rbx+68h], esi
0x18002bde1  mov     [rbx+28h], rsi
0x18002bde5  mov     byte ptr [rbx+6Ch], 1
0x18002bde9  test    rbx, rbx
0x18002bdec  jz      loc_18002C038
0x18002bdf2  mov     ecx, 50h ; 'P'; Size
0x18002bdf7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bdfc  mov     [rsp+78h+arg_18], rax
0x18002be04  mov     rdi, rax
0x18002be07  test    rax, rax
0x18002be0a  jz      loc_18002C021
0x18002be10  mov     [rax+8], rsi
0x18002be14  mov     [rax+28h], rsi
0x18002be18  mov     [rax+30h], rsi
0x18002be1c  lea     rax, ??_7CDRMCTridentDlg@@6B@; const CDRMCTridentDlg::`vftable'
0x18002be23  mov     [rdi], rax
0x18002be26  mov     [rdi+40h], rsi
0x18002be2a  mov     [rdi+38h], rsi
0x18002be2e  mov     [rdi+48h], rsi
0x18002be32  test    rdi, rdi
0x18002be35  jz      loc_18002C021
0x18002be3b  mov     rcx, rdi; this
0x18002be3e  call    ?Init@CDRMCTridentDlg@@QEAAJXZ; CDRMCTridentDlg::Init(void)
0x18002be43  mov     esi, eax
0x18002be45  test    eax, eax
0x18002be47  js      loc_18002BFD8
0x18002be4d  mov     rax, [rbx]
0x18002be50  lea     r8, [rsp+78h+arg_10]
0x18002be58  lea     rdx, IID_IDispatch
0x18002be5f  mov     rcx, rbx
0x18002be62  mov     rax, [rax]
0x18002be65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be6a  mov     esi, eax
0x18002be6c  test    eax, eax
0x18002be6e  js      loc_18002BFD8
0x18002be74  mov     r8, [rsp+78h+arg_10]; struct IDispatch *
0x18002be7c  mov     rcx, rdi; this
0x18002be7f  call    ?SetExternalObject@CDRMCTridentDlg@@QEAAJPEBGPEAUIDispatch@@@Z; CDRMCTridentDlg::SetExternalObject(ushort const *,IDispatch *)
0x18002be84  mov     r8, [r14+10h]; unsigned __int16 *
0x18002be88  mov     rcx, rbx; this
0x18002be8b  mov     rdx, [r14+8]; unsigned __int16 *
0x18002be8f  call    ?SetUserID@CuDRMActivation@@QEAAJPEAG0@Z; CuDRMActivation::SetUserID(ushort *,ushort *)
0x18002be94  mov     esi, eax
0x18002be96  test    eax, eax
0x18002be98  js      loc_18002BFD8
0x18002be9e  mov     rdx, [r14+18h]; unsigned __int16 *
0x18002bea2  mov     rcx, rbx; this
0x18002bea5  call    ?SetServer@CuDRMActivation@@QEAAJPEAG@Z; CuDRMActivation::SetServer(ushort *)
0x18002beaa  mov     esi, eax
0x18002beac  test    eax, eax
0x18002beae  js      loc_18002BFD8
0x18002beb4  mov     rax, [r14+20h]
0x18002beb8  xor     edx, edx; dwMilliseconds
0x18002beba  mov     [rbx+60h], rax
0x18002bebe  mov     rax, [r14+40h]
0x18002bec2  mov     [rbx+38h], rax
0x18002bec6  mov     [rbx+30h], r13
0x18002beca  mov     rcx, [r14+20h]; hHandle
0x18002bece  call    cs:__imp_WaitForSingleObject
0x18002bed4  xor     esi, esi
0x18002bed6  test    eax, eax
0x18002bed8  jnz     short loc_18002BEE4
0x18002beda  mov     esi, 8004CF41h
0x18002bedf  jmp     loc_18002BFD8
0x18002bee4  cmp     [r14+4Ch], esi
0x18002bee8  jnz     short loc_18002BEF7
0x18002beea  call    cs:__imp_GetUserDefaultUILanguage
0x18002bef0  movzx   eax, ax
0x18002bef3  mov     [r14+4Ch], eax
0x18002bef7  mov     rdx, [r14+18h]
0x18002befb  test    rdx, rdx
0x18002befe  jz      loc_18002BFEE
0x18002bf04  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002bf08  mov     rcx, r8
0x18002bf0b  inc     rcx
0x18002bf0e  cmp     [rdx+rcx*2], si
0x18002bf12  jnz     short loc_18002BF0B
0x18002bf14  lea     rsi, [rcx+2Ah]
0x18002bf18  mov     eax, 2
0x18002bf1d  mul     rsi
0x18002bf20  cmovb   rax, r8
0x18002bf24  mov     rcx, rax; unsigned __int64
0x18002bf27  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002bf2c  mov     rbp, rax
0x18002bf2f  test    rax, rax
0x18002bf32  jnz     short loc_18002BF3E
0x18002bf34  mov     esi, 8007000Eh
0x18002bf39  jmp     loc_18002BFD8
0x18002bf3e  mov     eax, [r14+4Ch]
0x18002bf42  lea     r8, aSSD; "%s%s%d"
0x18002bf49  mov     r9, [r14+18h]
0x18002bf4d  mov     rdx, rsi; unsigned __int64
0x18002bf50  mov     [rsp+78h+var_50], eax
0x18002bf54  mov     rcx, rbp; unsigned __int16 *
0x18002bf57  lea     rax, ?g_wszPassportPadding@@3QBGB; "/PassportRedirector.aspx?LANGID="
0x18002bf5e  mov     [rsp+78h+var_58], rax
0x18002bf63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bf68  mov     esi, eax
0x18002bf6a  test    eax, eax
0x18002bf6c  js      short loc_18002BFD8
0x18002bf6e  mov     rdx, rbp; unsigned __int16 *
0x18002bf71  mov     rcx, rdi; this
0x18002bf74  call    ?SetURL@CDRMCTridentDlg@@QEAAJPEAG@Z; CDRMCTridentDlg::SetURL(ushort *)
0x18002bf79  mov     esi, eax
0x18002bf7b  test    eax, eax
0x18002bf7d  js      short loc_18002BFD8
0x18002bf7f  mov     rcx, [r14+20h]; hHandle
0x18002bf83  xor     edx, edx; dwMilliseconds
0x18002bf85  call    cs:__imp_WaitForSingleObject
0x18002bf8b  test    eax, eax
0x18002bf8d  jz      loc_18002BEDA
0x18002bf93  mov     rax, [r14+30h]
0x18002bf97  test    rax, rax
0x18002bf9a  jnz     short loc_18002BFA6
0x18002bf9c  call    cs:__imp_GetActiveWindow
0x18002bfa2  mov     [r14+30h], rax
0x18002bfa6  mov     rdx, rax; HWND
0x18002bfa9  mov     rcx, rdi; this
0x18002bfac  call    ?LaunchTrident@CDRMCTridentDlg@@QEAAJPEAUHWND__@@@Z; CDRMCTridentDlg::LaunchTrident(HWND__ *)
0x18002bfb1  mov     esi, eax
0x18002bfb3  test    eax, eax
0x18002bfb5  js      short loc_18002BFD8
0x18002bfb7  lea     rdx, [rsp+78h+arg_8]; unsigned __int16 **
0x18002bfbf  mov     rcx, rbx; this
0x18002bfc2  call    ?GetCertificate@CuDRMActivation@@QEAAJPEAPEAG@Z; CuDRMActivation::GetCertificate(ushort * *)
0x18002bfc7  mov     r15, [rsp+78h+arg_8]
0x18002bfcf  mov     esi, eax
0x18002bfd1  test    eax, eax
0x18002bfd3  js      short loc_18002BFD8
0x18002bfd5  mov     esi, [rbx+8]
0x18002bfd8  mov     rax, [rdi]
0x18002bfdb  mov     edx, 1
0x18002bfe0  mov     rcx, rdi
0x18002bfe3  mov     rax, [rax+18h]
0x18002bfe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfec  jmp     short loc_18002C026
0x18002bfee  mov     ecx, 7Eh ; '~'; unsigned __int64
0x18002bff3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002bff8  mov     rbp, rax
0x18002bffb  test    rax, rax
0x18002bffe  jz      loc_18002BF34
0x18002c004  mov     r9d, [r14+4Ch]
0x18002c008  lea     r8, ?g_wszPassportPages@@3QBGB; "http://go.microsoft.com/fwlink/?LinkId="...
0x18002c00f  mov     edx, 3Fh ; '?'; unsigned __int64
0x18002c014  mov     rcx, rax; unsigned __int16 *
0x18002c017  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c01c  jmp     loc_18002BF68
0x18002c021  mov     esi, 8007000Eh
0x18002c026  mov     rcx, rbx; this
0x18002c029  call    ??1CuDRMActivation@@QEAA@XZ; CuDRMActivation::~CuDRMActivation(void)
0x18002c02e  mov     rcx, rbx; Block
0x18002c031  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c036  jmp     short loc_18002C03D
0x18002c038  mov     esi, 8007000Eh
0x18002c03d  mov     rcx, rbp; Block
0x18002c040  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c045  mov     rcx, [r14+50h]; hEvent
0x18002c049  test    rcx, rcx
0x18002c04c  jz      short loc_18002C054
0x18002c04e  call    cs:__imp_SetEvent
0x18002c054  test    r13, r13
0x18002c057  jz      short loc_18002C074
0x18002c059  mov     r9, [r14+40h]
0x18002c05d  not     r12d
0x18002c060  and     r12d, 1
0x18002c064  mov     r8, r15
0x18002c067  mov     ecx, r12d
0x18002c06a  mov     edx, esi
0x18002c06c  mov     rax, r13
0x18002c06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c074  mov     rcx, [r14+18h]; Block
0x18002c078  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c07d  mov     rcx, [r14+8]; Block
0x18002c081  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c086  mov     rcx, [r14+10h]; Block
0x18002c08a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c08f  mov     rcx, [r14+20h]; hObject
0x18002c093  xor     esi, esi
0x18002c095  test    rcx, rcx
0x18002c098  jz      short loc_18002C0A0
0x18002c09a  call    cs:__imp_CloseHandle
0x18002c0a0  mov     rcx, [r14+28h]; hObject
0x18002c0a4  test    rcx, rcx
0x18002c0a7  jz      short loc_18002C0AF
0x18002c0a9  call    cs:__imp_CloseHandle
0x18002c0af  mov     rcx, r14; Block
0x18002c0b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c0b7  mov     rcx, r15; Block
0x18002c0ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c0bf  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18002c0c6  call    cs:__imp_AtlModuleTerm
0x18002c0cc  cmp     [rsp+78h+arg_0], esi
0x18002c0d3  jz      short loc_18002C0DB
0x18002c0d5  call    cs:__imp_CoUninitialize
0x18002c0db  xor     eax, eax
0x18002c0dd  add     rsp, 38h
0x18002c0e1  pop     r15
0x18002c0e3  pop     r14
0x18002c0e5  pop     r13
0x18002c0e7  pop     r12
0x18002c0e9  pop     rdi
0x18002c0ea  pop     rsi
0x18002c0eb  pop     rbp
0x18002c0ec  pop     rbx
0x18002c0ed  retn
```
