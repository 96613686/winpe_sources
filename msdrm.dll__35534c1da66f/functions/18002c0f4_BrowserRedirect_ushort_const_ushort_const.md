# BrowserRedirect(ushort const *,ushort const *)

- ea: `0x18002c0f4`
- end: `0x18002c388`
- name: `?BrowserRedirect@@YAJPEBG0@Z`
- size: `660`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043da8`

## callees

- `0x180001244`
- `0x180001284`
- `0x1800046c8`
- `0x18002c0f4`
- `0x18002dc18`
- `0x18002f020`
- `0x18002f1a0`
- `0x18002f97c`
- `0x18002f9d4`
- `0x180030770`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18002c15b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18002c15b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002c36e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002c36e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002c1aa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002c1aa`
- `ATL!__imp_AtlModuleInit` at `0x18002c18f`
- `ATL!__imp_AtlModuleInit` at `0x18002c18f`
- `ATL!__imp_AtlModuleTerm` at `0x18002c35f`
- `ATL!__imp_AtlModuleTerm` at `0x18002c35f`
- `USER32!GetActiveWindow` at `0x18002c2da`
- `USER32!GetActiveWindow` at `0x18002c2da`

## string_xrefs

- `0x18002c154`: `msdrm.dll`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall BrowserRedirect(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HRESULT v5; // esi
  _QWORD *v6; // rdi
  CDRMCTridentDlg *v7; // rax
  CDRMCTridentDlg *v8; // r14
  const unsigned __int16 *v9; // rdx
  CWebBrowser *v10; // rcx
  HWND ActiveWindow; // rax
  struct IDispatch *v13[8]; // [rsp+28h] [rbp-40h] BYREF
  int v14; // [rsp+80h] [rbp+18h]

  v13[1] = (struct IDispatch *)-2LL;
  v14 = 0;
  v13[0] = 0;
  if ( a1 && a2 )
  {
    _RTLTRACE("[msdrm]+BrowserRedirect: ActualUrl = %S AbortUrl = %S\n", a1, a2);
    ModuleHandleW = GetModuleHandleW(L"msdrm.dll");
    qword_180084CA8 = (__int64)&ATL::GUID_ATLVer30;
    _Module = 248;
    dword_180084C90 = 769;
    if ( (int)AtlModuleInit(&_Module, 0, ModuleHandleW) >= 0 )
      dword_180084CD0 = 1;
    v5 = CoInitializeEx(0, 2u);
    if ( v5 >= 0 )
    {
      v14 = 1;
      v6 = operator new(0x70u);
      if ( v6 )
      {
        *v6 = &CuDRMActivation::`vftable';
        v6[9] = 100;
        *((_DWORD *)v6 + 2) = -2147168447;
        v6[2] = 0;
        v6[3] = 0;
        v6[4] = 0;
        v6[6] = 0;
        v6[7] = 0;
        v6[8] = 0;
        v6[10] = 0;
        v6[11] = 0;
        v6[12] = 0;
        *((_DWORD *)v6 + 26) = 0;
        v6[5] = 0;
        *((_BYTE *)v6 + 108) = 1;
        v7 = (CDRMCTridentDlg *)operator new(0x50u);
        v8 = v7;
        if ( v7 )
        {
          *((_QWORD *)v7 + 1) = 0;
          *((_QWORD *)v7 + 5) = 0;
          *((_QWORD *)v7 + 6) = 0;
          *(_QWORD *)v7 = &CDRMCTridentDlg::`vftable';
          *((_QWORD *)v7 + 8) = 0;
          *((_QWORD *)v7 + 7) = 0;
          *((_QWORD *)v7 + 9) = 0;
          v5 = CDRMCTridentDlg::Init(v7);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IDispatch **))*v6)(v6, &IID_IDispatch, v13);
            if ( v5 >= 0 )
            {
              CDRMCTridentDlg::SetExternalObject(v8, v9, v13[0]);
              v5 = CDRMCTridentDlg::SetURL(v8, a1);
              if ( v5 >= 0 )
              {
                v10 = (CWebBrowser *)*((_QWORD *)v8 + 8);
                if ( !v10 || (v5 = CWebBrowser::SetAbortUrl(v10, a2), v5 >= 0) )
                {
                  ActiveWindow = GetActiveWindow();
                  v5 = CDRMCTridentDlg::LaunchTrident(v8, ActiveWindow);
                }
              }
            }
          }
          (*(void (__fastcall **)(CDRMCTridentDlg *, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
        }
        else
        {
          v5 = -2147024882;
        }
        CuDRMActivation::~CuDRMActivation((CuDRMActivation *)v6);
        operator delete(v6);
      }
      else
      {
        v5 = -2147024882;
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  AtlModuleTerm(&_Module);
  if ( v14 )
    CoUninitialize();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c0f4  push    rsi
0x18002c0f6  push    rdi
0x18002c0f7  push    r12
0x18002c0f9  push    r14
0x18002c0fb  push    r15
0x18002c0fd  sub     rsp, 40h
0x18002c101  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18002c10a  mov     [rsp+68h+arg_8], rbx
0x18002c10f  mov     r12, rdx
0x18002c112  mov     r15, rcx
0x18002c115  xor     ebx, ebx
0x18002c117  mov     [rsp+68h+arg_10], ebx
0x18002c11e  mov     [rsp+68h+var_48], rbx
0x18002c123  mov     [rsp+68h+arg_18], rbx
0x18002c12b  mov     [rsp+68h+var_40], rbx
0x18002c130  test    rcx, rcx
0x18002c133  jz      loc_18002C310
0x18002c139  test    rdx, rdx
0x18002c13c  jz      loc_18002C310
0x18002c142  mov     r8, rdx
0x18002c145  mov     rdx, rcx
0x18002c148  lea     rcx, aMsdrmBrowserre; "[msdrm]+BrowserRedirect: ActualUrl = %S"...
0x18002c14f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002c154  lea     rcx, ?g_wszMODULENAME@@3QBGB; "msdrm.dll"
0x18002c15b  call    cs:__imp_GetModuleHandleW
0x18002c161  lea     rcx, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x18002c168  mov     cs:qword_180084CA8, rcx
0x18002c16f  mov     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18002c179  mov     cs:dword_180084C90, 301h
0x18002c183  mov     r8, rax
0x18002c186  xor     edx, edx
0x18002c188  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18002c18f  call    cs:__imp_AtlModuleInit
0x18002c195  test    eax, eax
0x18002c197  js      short loc_18002C1A3
0x18002c199  mov     cs:dword_180084CD0, 1
0x18002c1a3  mov     edx, 2; dwCoInit
0x18002c1a8  xor     ecx, ecx; pvReserved
0x18002c1aa  call    cs:__imp_CoInitializeEx
0x18002c1b0  mov     esi, eax
0x18002c1b2  test    eax, eax
0x18002c1b4  jns     short loc_18002C1BB
0x18002c1b6  jmp     loc_18002C358
0x18002c1bb  mov     [rsp+68h+arg_10], 1
0x18002c1c6  mov     ecx, 70h ; 'p'; Size
0x18002c1cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c1d0  mov     rdi, rax
0x18002c1d3  test    rax, rax
0x18002c1d6  jz      loc_18002C301
0x18002c1dc  lea     rax, ??_7CuDRMActivation@@6B@; const CuDRMActivation::`vftable'
0x18002c1e3  mov     [rdi], rax
0x18002c1e6  mov     qword ptr [rdi+48h], 64h ; 'd'
0x18002c1ee  mov     dword ptr [rdi+8], 8004CF41h
0x18002c1f5  mov     [rdi+10h], rbx
0x18002c1f9  mov     [rdi+18h], rbx
0x18002c1fd  mov     [rdi+20h], rbx
0x18002c201  mov     [rdi+30h], rbx
0x18002c205  mov     [rdi+38h], rbx
0x18002c209  mov     [rdi+40h], rbx
0x18002c20d  mov     [rdi+50h], rbx
0x18002c211  mov     [rdi+58h], rbx
0x18002c215  mov     [rdi+60h], rbx
0x18002c219  mov     [rdi+68h], ebx
0x18002c21c  mov     [rdi+28h], rbx
0x18002c220  mov     byte ptr [rdi+6Ch], 1
0x18002c224  mov     [rsp+68h+arg_18], rdi
0x18002c22c  mov     ecx, 50h ; 'P'; Size
0x18002c231  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c236  mov     r14, rax
0x18002c239  test    rax, rax
0x18002c23c  jz      loc_18002C2F5
0x18002c242  mov     [rax+8], rbx
0x18002c246  mov     [rax+28h], rbx
0x18002c24a  mov     [rax+30h], rbx
0x18002c24e  lea     rax, ??_7CDRMCTridentDlg@@6B@; const CDRMCTridentDlg::`vftable'
0x18002c255  mov     [r14], rax
0x18002c258  mov     [r14+40h], rbx
0x18002c25c  mov     [r14+38h], rbx
0x18002c260  mov     [r14+48h], rbx
0x18002c264  mov     [rsp+68h+var_48], r14
0x18002c269  mov     rcx, r14; this
0x18002c26c  call    ?Init@CDRMCTridentDlg@@QEAAJXZ; CDRMCTridentDlg::Init(void)
0x18002c271  mov     esi, eax
0x18002c273  test    eax, eax
0x18002c275  jns     short loc_18002C27C
0x18002c277  jmp     loc_18002C32F
0x18002c27c  mov     rax, [rdi]
0x18002c27f  lea     r8, [rsp+68h+var_40]
0x18002c284  lea     rdx, IID_IDispatch
0x18002c28b  mov     rcx, rdi
0x18002c28e  mov     rax, [rax]
0x18002c291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c296  mov     esi, eax
0x18002c298  test    eax, eax
0x18002c29a  jns     short loc_18002C2A1
0x18002c29c  jmp     loc_18002C32F
0x18002c2a1  mov     r8, [rsp+68h+var_40]; struct IDispatch *
0x18002c2a6  mov     rcx, r14; this
0x18002c2a9  call    ?SetExternalObject@CDRMCTridentDlg@@QEAAJPEBGPEAUIDispatch@@@Z; CDRMCTridentDlg::SetExternalObject(ushort const *,IDispatch *)
0x18002c2ae  mov     rdx, r15; unsigned __int16 *
0x18002c2b1  mov     rcx, r14; this
0x18002c2b4  call    ?SetURL@CDRMCTridentDlg@@QEAAJPEAG@Z; CDRMCTridentDlg::SetURL(ushort *)
0x18002c2b9  mov     esi, eax
0x18002c2bb  test    eax, eax
0x18002c2bd  jns     short loc_18002C2C1
0x18002c2bf  jmp     short loc_18002C32F
0x18002c2c1  mov     rcx, [r14+40h]; this
0x18002c2c5  test    rcx, rcx
0x18002c2c8  jz      short loc_18002C2DA
0x18002c2ca  mov     rdx, r12; unsigned __int16 *
0x18002c2cd  call    ?SetAbortUrl@CWebBrowser@@QEAAJPEBG@Z; CWebBrowser::SetAbortUrl(ushort const *)
0x18002c2d2  mov     esi, eax
0x18002c2d4  test    eax, eax
0x18002c2d6  jns     short loc_18002C2DA
0x18002c2d8  jmp     short loc_18002C32F
0x18002c2da  call    cs:__imp_GetActiveWindow
0x18002c2e0  mov     rdx, rax; HWND
0x18002c2e3  mov     rcx, r14; this
0x18002c2e6  call    ?LaunchTrident@CDRMCTridentDlg@@QEAAJPEAUHWND__@@@Z; CDRMCTridentDlg::LaunchTrident(HWND__ *)
0x18002c2eb  mov     esi, eax
0x18002c2ed  test    eax, eax
0x18002c2ef  jns     short loc_18002C2F3
0x18002c2f1  jmp     short loc_18002C32F
0x18002c2f3  jmp     short loc_18002C32F
0x18002c2f5  mov     [rsp+68h+var_48], rbx
0x18002c2fa  mov     esi, 8007000Eh
0x18002c2ff  jmp     short loc_18002C348
0x18002c301  mov     [rsp+68h+arg_18], rbx
0x18002c309  mov     esi, 8007000Eh
0x18002c30e  jmp     short loc_18002C358
0x18002c310  mov     esi, 80070057h
0x18002c315  jmp     short loc_18002C358
0x18002c317  mov     r14, [rsp+68h+var_48]
0x18002c31c  xor     ebx, ebx
0x18002c31e  mov     esi, [rsp+68h+arg_0]
0x18002c322  mov     rdi, [rsp+68h+arg_18]
0x18002c32a  test    r14, r14
0x18002c32d  jz      short loc_18002C343
0x18002c32f  mov     rax, [r14]
0x18002c332  mov     edx, 1
0x18002c337  mov     rcx, r14
0x18002c33a  mov     rax, [rax+18h]
0x18002c33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c343  test    rdi, rdi
0x18002c346  jz      short loc_18002C358
0x18002c348  mov     rcx, rdi; this
0x18002c34b  call    ??1CuDRMActivation@@QEAA@XZ; CuDRMActivation::~CuDRMActivation(void)
0x18002c350  mov     rcx, rdi; Block
0x18002c353  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c358  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18002c35f  call    cs:__imp_AtlModuleTerm
0x18002c365  cmp     [rsp+68h+arg_10], ebx
0x18002c36c  jz      short loc_18002C374
0x18002c36e  call    cs:__imp_CoUninitialize
0x18002c374  mov     eax, esi
0x18002c376  mov     rbx, [rsp+68h+arg_8]
0x18002c37b  add     rsp, 40h
0x18002c37f  pop     r15
0x18002c381  pop     r14
0x18002c383  pop     r12
0x18002c385  pop     rdi
0x18002c386  pop     rsi
0x18002c387  retn
```
