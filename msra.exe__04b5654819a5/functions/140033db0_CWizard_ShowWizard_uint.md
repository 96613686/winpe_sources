# CWizard::ShowWizard(uint)

- ea: `0x140033db0`
- end: `0x140034143`
- name: `?ShowWizard@CWizard@@QEAAJI@Z`
- size: `915`
- prototype: `__int64 __fastcall(CWizard *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140016bd4`

## callees

- `0x140002463`
- `0x140033db0`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `COMCTL32!PropertySheetW` at `0x1400340c9`
- `COMCTL32!PropertySheetW` at `0x1400340c9`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033e63`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033e8a`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033eb1`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033ed8`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033eff`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f26`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f4d`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f74`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f9b`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033fc2`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033fe9`
- `COMCTL32!CreatePropertySheetPageW` at `0x140034011`
- `COMCTL32!CreatePropertySheetPageW` at `0x140034034`
- `COMCTL32!CreatePropertySheetPageW` at `0x14003405b`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033e63`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033e8a`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033eb1`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033ed8`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033eff`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f26`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f4d`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f74`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033f9b`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033fc2`
- `COMCTL32!CreatePropertySheetPageW` at `0x140033fe9`
- `COMCTL32!CreatePropertySheetPageW` at `0x140034011`
- `COMCTL32!CreatePropertySheetPageW` at `0x140034034`
- `COMCTL32!CreatePropertySheetPageW` at `0x14003405b`

## pseudocode

```c
__int64 __fastcall CWizard::ShowWizard(CWizard *this, unsigned int a2)
{
  UINT v4; // edi
  HPROPSHEETPAGE v5; // rax
  HPROPSHEETPAGE v6; // rax
  HPROPSHEETPAGE v7; // rax
  HPROPSHEETPAGE v8; // rax
  HPROPSHEETPAGE v9; // rax
  HPROPSHEETPAGE v10; // rax
  HPROPSHEETPAGE v11; // rax
  HPROPSHEETPAGE v12; // rax
  HPROPSHEETPAGE v13; // rax
  HPROPSHEETPAGE v14; // rax
  HPROPSHEETPAGE v15; // rax
  HPROPSHEETPAGE v16; // rax
  HPROPSHEETPAGE v17; // rax
  unsigned int v18; // ebx
  int v19; // eax
  CEventLogger *v20; // rcx
  CEventLogger *v21; // rax
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+30h] [rbp-D0h] BYREF
  PROPSHEETHEADERW_V2 v24; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v25[14]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&constPropSheetPagePointer, 0, sizeof(constPropSheetPagePointer));
  memset_0(v25, 0, sizeof(v25));
  memset_0(&v24, 0, sizeof(v24));
  v4 = a2 < 0xE ? a2 : 0;
  if ( v4 == 6 )
  {
    *((_DWORD *)this + 8) = 1;
    v4 = 8;
  }
  constPropSheetPagePointer.dwSize = 104;
  constPropSheetPagePointer.dwFlags = 4096;
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)512;
  constPropSheetPagePointer.hInstance = (HINSTANCE)*((_QWORD *)_AtlModule + 76);
  constPropSheetPagePointer.pfnDlgProc = (DLGPROC)WizardDialogProc;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)107;
  v5 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)518;
  v25[0] = v5;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)108;
  v6 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)517;
  v25[1] = v6;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2001;
  v7 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)592;
  v25[2] = v7;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2004;
  v8 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)623;
  v25[3] = v8;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2005;
  v9 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)624;
  v25[4] = v9;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2006;
  v10 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)556;
  v25[5] = v10;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2011;
  v11 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)616;
  v25[7] = v11;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2009;
  v12 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)565;
  v25[6] = v12;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2012;
  v13 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)566;
  v25[8] = v13;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2013;
  v14 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)588;
  v25[9] = v14;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2010;
  v15 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2015;
  v25[10] = v15;
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)580;
  v16 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)580;
  v25[11] = v16;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2014;
  v17 = CreatePropertySheetPageW(&constPropSheetPagePointer);
  constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)533;
  v25[12] = v17;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)2016;
  v25[13] = CreatePropertySheetPageW(&constPropSheetPagePointer);
  v24.dwSize = 96;
  v24.hInstance = (HINSTANCE)*((_QWORD *)_AtlModule + 76);
  v24.ppsp = (LPCPROPSHEETPAGEW)v25;
  v18 = 0;
  v24.hwndParent = 0;
  v24.pszCaption = (LPCWSTR)100;
  v24.dwFlags = 16420;
  v24.nStartPage = v4;
  v19 = dword_140063734[3 * v4];
  v24.nPages = 14;
  v24.hIcon = (HICON)4003;
  *(_DWORD *)this = v19;
  if ( PropertySheetW(&v24) == -1 )
  {
    v18 = -2147467259;
    CEventLogger::LogError(
      v20,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\wizard.cpp",
      0x2ECu,
      L"CWizard::ShowWizard",
      0x80004005);
  }
  else
  {
    v21 = _AtlModule;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)v21 + 101) = 0;
  }
  return v18;
}

```

## disassembly

```asm
0x140033db0  mov     [rsp-8+arg_10], rbx
0x140033db5  push    rbp
0x140033db6  push    rsi
0x140033db7  push    rdi
0x140033db8  lea     rbp, [rsp-80h]
0x140033dbd  sub     rsp, 180h
0x140033dc4  mov     rax, cs:__security_cookie
0x140033dcb  xor     rax, rsp
0x140033dce  mov     [rbp+90h+var_20], rax
0x140033dd2  mov     ebx, edx
0x140033dd4  mov     rsi, rcx
0x140033dd7  xor     edx, edx; Val
0x140033dd9  lea     rcx, [rsp+190h+constPropSheetPagePointer]; void *
0x140033dde  lea     r8d, [rdx+68h]; Size
0x140033de2  call    memset_0
0x140033de7  xor     edx, edx; Val
0x140033de9  lea     rcx, [rbp+90h+var_90]; void *
0x140033ded  lea     r8d, [rdx+70h]; Size
0x140033df1  call    memset_0
0x140033df6  xor     edx, edx; Val
0x140033df8  lea     rcx, [rbp+90h+var_F0]; void *
0x140033dfc  lea     r8d, [rdx+60h]; Size
0x140033e00  call    memset_0
0x140033e05  cmp     ebx, 0Eh
0x140033e08  sbb     edi, edi
0x140033e0a  and     edi, ebx
0x140033e0c  cmp     edi, 6
0x140033e0f  jnz     short loc_140033E1D
0x140033e11  mov     dword ptr [rsi+20h], 1
0x140033e18  mov     edi, 8
0x140033e1d  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140033e24  mov     [rsp+190h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x140033e2c  mov     [rsp+190h+constPropSheetPagePointer.dwFlags], 1000h
0x140033e34  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 200h
0x140033e3d  mov     rcx, [rax+260h]
0x140033e44  lea     rax, ?WizardDialogProc@@YAHPEAUHWND__@@I_K_J@Z; WizardDialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x140033e4b  mov     [rsp+190h+constPropSheetPagePointer.hInstance], rcx
0x140033e50  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033e55  mov     [rsp+190h+constPropSheetPagePointer.pfnDlgProc], rax
0x140033e5a  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 6Bh ; 'k'
0x140033e63  call    cs:__imp_CreatePropertySheetPageW
0x140033e6a  nop     dword ptr [rax+rax+00h]
0x140033e6f  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033e74  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 206h
0x140033e7d  mov     [rbp+90h+var_90], rax
0x140033e81  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 6Ch ; 'l'
0x140033e8a  call    cs:__imp_CreatePropertySheetPageW
0x140033e91  nop     dword ptr [rax+rax+00h]
0x140033e96  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033e9b  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 205h
0x140033ea4  mov     [rbp+90h+var_88], rax
0x140033ea8  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7D1h
0x140033eb1  call    cs:__imp_CreatePropertySheetPageW
0x140033eb8  nop     dword ptr [rax+rax+00h]
0x140033ebd  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033ec2  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 250h
0x140033ecb  mov     [rbp+90h+var_80], rax
0x140033ecf  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7D4h
0x140033ed8  call    cs:__imp_CreatePropertySheetPageW
0x140033edf  nop     dword ptr [rax+rax+00h]
0x140033ee4  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033ee9  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 26Fh
0x140033ef2  mov     [rbp+90h+var_78], rax
0x140033ef6  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7D5h
0x140033eff  call    cs:__imp_CreatePropertySheetPageW
0x140033f06  nop     dword ptr [rax+rax+00h]
0x140033f0b  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033f10  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 270h
0x140033f19  mov     [rbp+90h+var_70], rax
0x140033f1d  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7D6h
0x140033f26  call    cs:__imp_CreatePropertySheetPageW
0x140033f2d  nop     dword ptr [rax+rax+00h]
0x140033f32  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033f37  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 22Ch
0x140033f40  mov     [rbp+90h+var_68], rax
0x140033f44  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7DBh
0x140033f4d  call    cs:__imp_CreatePropertySheetPageW
0x140033f54  nop     dword ptr [rax+rax+00h]
0x140033f59  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033f5e  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 268h
0x140033f67  mov     [rbp+90h+var_58], rax
0x140033f6b  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7D9h
0x140033f74  call    cs:__imp_CreatePropertySheetPageW
0x140033f7b  nop     dword ptr [rax+rax+00h]
0x140033f80  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033f85  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 235h
0x140033f8e  mov     [rbp+90h+var_60], rax
0x140033f92  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7DCh
0x140033f9b  call    cs:__imp_CreatePropertySheetPageW
0x140033fa2  nop     dword ptr [rax+rax+00h]
0x140033fa7  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033fac  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 236h
0x140033fb5  mov     [rbp+90h+var_50], rax
0x140033fb9  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7DDh
0x140033fc2  call    cs:__imp_CreatePropertySheetPageW
0x140033fc9  nop     dword ptr [rax+rax+00h]
0x140033fce  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140033fd3  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 24Ch
0x140033fdc  mov     [rbp+90h+var_48], rax
0x140033fe0  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7DAh
0x140033fe9  call    cs:__imp_CreatePropertySheetPageW
0x140033ff0  nop     dword ptr [rax+rax+00h]
0x140033ff5  mov     ebx, 244h
0x140033ffa  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7DFh
0x140034003  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140034008  mov     [rbp+90h+var_40], rax
0x14003400c  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], rbx
0x140034011  call    cs:__imp_CreatePropertySheetPageW
0x140034018  nop     dword ptr [rax+rax+00h]
0x14003401d  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140034022  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], rbx
0x140034027  mov     [rbp+90h+var_38], rax
0x14003402b  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7DEh
0x140034034  call    cs:__imp_CreatePropertySheetPageW
0x14003403b  nop     dword ptr [rax+rax+00h]
0x140034040  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x140034045  mov     [rsp+190h+constPropSheetPagePointer.pszHeaderTitle], 215h
0x14003404e  mov     [rbp+90h+var_30], rax
0x140034052  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], 7E0h
0x14003405b  call    cs:__imp_CreatePropertySheetPageW
0x140034062  nop     dword ptr [rax+rax+00h]
0x140034067  mov     [rbp+90h+var_28], rax
0x14003406b  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140034072  mov     [rbp+90h+var_F0.dwSize], 60h ; '`'
0x140034079  mov     rcx, [rax+260h]
0x140034080  mov     [rbp+90h+var_F0.hInstance], rcx
0x140034084  lea     rax, [rbp+90h+var_90]
0x140034088  mov     qword ptr [rbp+90h+var_F0.38h], rax
0x14003408c  lea     rcx, dword_140063734
0x140034093  mov     eax, edi
0x140034095  xor     ebx, ebx
0x140034097  mov     [rbp+90h+var_F0.hwndParent], rbx
0x14003409b  mov     [rbp+90h+var_F0.pszCaption], 64h ; 'd'
0x1400340a3  mov     [rbp+90h+var_F0.dwFlags], 4024h
0x1400340aa  lea     rax, [rax+rax*2]
0x1400340ae  mov     dword ptr [rbp+90h+var_F0.30h], edi
0x1400340b1  mov     eax, [rcx+rax*4]
0x1400340b4  lea     rcx, [rbp+90h+var_F0]; LPCPROPSHEETHEADERW
0x1400340b8  mov     [rbp+90h+var_F0.nPages], 0Eh
0x1400340bf  mov     qword ptr [rbp+90h+var_F0.18h], 0FA3h
0x1400340c7  mov     [rsi], eax
0x1400340c9  call    cs:__imp_PropertySheetW
0x1400340d0  nop     dword ptr [rax+rax+00h]
0x1400340d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400340d9  jnz     short loc_14003410F
0x1400340db  lea     rax, aCwizardShowwiz; "CWizard::ShowWizard"
0x1400340e2  mov     [rsp+190h+var_168], 80004005h; unsigned int
0x1400340ea  mov     r9d, 2ECh; unsigned int
0x1400340f0  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x1400340f5  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x1400340fc  mov     ebx, 80004005h
0x140034101  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140034108  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003410d  jmp     short loc_140034121
0x14003410f  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140034116  mov     [rsi+8], rbx
0x14003411a  mov     [rax+328h], rbx
0x140034121  mov     eax, ebx
0x140034123  mov     rcx, [rbp+90h+var_20]
0x140034127  xor     rcx, rsp; StackCookie
0x14003412a  call    __security_check_cookie
0x14003412f  mov     rbx, [rsp+190h+arg_10]
0x140034137  add     rsp, 180h
0x14003413e  pop     rdi
0x14003413f  pop     rsi
0x140034140  pop     rbp
0x140034141  retn
```
