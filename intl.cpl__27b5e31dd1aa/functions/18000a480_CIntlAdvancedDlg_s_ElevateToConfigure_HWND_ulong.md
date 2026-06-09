# CIntlAdvancedDlg::s_ElevateToConfigure(HWND__ *,ulong)

- ea: `0x18000a480`
- end: `0x18000a62f`
- name: `?s_ElevateToConfigure@CIntlAdvancedDlg@@SAJPEAUHWND__@@K@Z`
- size: `431`
- prototype: `__int64 __fastcall(HWND hwndOwner, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008e80`

## callees

- `0x1800028c4`
- `0x180009128`
- `0x180009218`
- `0x18000a480`
- `0x180026d2c`
- `0x180029c84`
- `0x18002b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a5d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000a604`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000a604`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a4bb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a4bb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a51d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a51d`
- `USER32!DialogBoxParamW` at `0x18000a5b9`
- `USER32!DialogBoxParamW` at `0x18000a5b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIntlAdvancedDlg::s_ElevateToConfigure(HWND hwndOwner, int a2)
{
  HWND v3; // rbp
  HRESULT v4; // edi
  DWORD v5; // edx
  const struct _GUID *v6; // rdx
  const struct _GUID *v7; // r8
  char *v8; // rbx
  IUnknown *v9; // rax
  int v10; // esi
  INT_PTR (__stdcall *v11)(HWND, UINT, WPARAM, LPARAM); // r9
  __int64 v12; // rdx
  IUnknown *pProxy; // [rsp+80h] [rbp+18h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+88h] [rbp+20h] BYREF

  v3 = hwndOwner;
  if ( !__PAIR64__(g_bIsLUAEnabled, g_bAdmin_Privileges) )
  {
    v4 = -2147467259;
    v5 = 1260;
LABEL_22:
    Intl_ShowSystemErrorMessage(hwndOwner, v5);
    return (unsigned int)v4;
  }
  v4 = CoInitializeEx(0, 6u);
  if ( v4 >= 0 )
  {
    pProxy = 0;
    if ( CoCreateInstanceAsAdmin(v3, v6, v7, (void **)&pProxy) < 0 )
      goto LABEL_19;
    v4 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 3u, 0, 0);
    if ( v4 < 0 )
    {
LABEL_18:
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
LABEL_19:
      CoUninitialize();
      if ( v4 >= 0 )
        return (unsigned int)v4;
      goto LABEL_20;
    }
    v8 = (char *)operator new(0x20u);
    if ( v8 )
    {
      v9 = pProxy;
      *(_QWORD *)(v8 + 4) = 0;
      *((_DWORD *)v8 + 3) = 0;
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = v9;
      picce.dwSize = 8;
      picce.dwICC = 0x4000;
      InitCommonControlsEx(&picce);
    }
    else
    {
      v8 = 0;
    }
    if ( !v8 )
    {
      v4 = -2147024882;
      goto LABEL_18;
    }
    v10 = a2 - 2102;
    if ( v10 )
    {
      if ( v10 != 2 )
      {
LABEL_15:
        CIntlAdvancedDlg::~CIntlAdvancedDlg((CIntlAdvancedDlg *)v8);
        operator delete(v8);
        goto LABEL_18;
      }
      v11 = CIntlAdvancedDlg::s_CopySettings_DlgProc;
      v12 = 700;
    }
    else
    {
      v11 = (INT_PTR (__stdcall *)(HWND, UINT, WPARAM, LPARAM))CIntlAdvancedDlg::s_SysLocale_DlgProc;
      v12 = 800;
    }
    if ( !DialogBoxParamW(hInstance, (LPCWSTR)v12, v3, v11, (LPARAM)v8) )
      GetLastError();
    goto LABEL_15;
  }
LABEL_20:
  if ( v4 != -2147023673 )
  {
    v5 = v4;
    hwndOwner = v3;
    goto LABEL_22;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a480  mov     [rsp+arg_0], rbx
0x18000a485  push    rbp
0x18000a486  push    rsi
0x18000a487  push    rdi
0x18000a488  sub     rsp, 50h
0x18000a48c  mov     esi, edx
0x18000a48e  mov     rbp, rcx
0x18000a491  cmp     cs:?g_bIsLUAEnabled@@3HA, 0; int g_bIsLUAEnabled
0x18000a498  jnz     short loc_18000A4B2
0x18000a49a  cmp     cs:?g_bAdmin_Privileges@@3HA, 0; int g_bAdmin_Privileges
0x18000a4a1  jnz     short loc_18000A4B2
0x18000a4a3  mov     edi, 80004005h
0x18000a4a8  mov     edx, 4ECh
0x18000a4ad  jmp     loc_18000A61B
0x18000a4b2  mov     ebx, 6
0x18000a4b7  mov     edx, ebx; dwCoInit
0x18000a4b9  xor     ecx, ecx; pvReserved
0x18000a4bb  call    cs:__imp_CoInitializeEx
0x18000a4c1  mov     edi, eax
0x18000a4c3  test    eax, eax
0x18000a4c5  js      loc_18000A60E
0x18000a4cb  mov     [rsp+68h+pProxy], 0
0x18000a4d7  lea     r9, [rsp+68h+pProxy]; void **
0x18000a4df  mov     rcx, rbp; HWND
0x18000a4e2  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18000a4e7  test    eax, eax
0x18000a4e9  js      loc_18000A604
0x18000a4ef  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x18000a4f7  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a500  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a508  mov     [rsp+68h+dwAuthnLevel], ebx; dwAuthnLevel
0x18000a50c  xor     r9d, r9d; pServerPrincName
0x18000a50f  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a512  mov     r8d, edx; dwAuthzSvc
0x18000a515  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a51d  call    cs:__imp_CoSetProxyBlanket
0x18000a523  mov     edi, eax
0x18000a525  test    eax, eax
0x18000a527  js      loc_18000A5F0
0x18000a52d  lea     ecx, [rbx+1Ah]; Size
0x18000a530  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a535  mov     rbx, rax
0x18000a538  mov     [rsp+68h+var_28], rax
0x18000a53d  test    rax, rax
0x18000a540  jz      short loc_18000A58A
0x18000a542  mov     rax, [rsp+68h+pProxy]
0x18000a54a  mov     qword ptr [rbx+4], 0
0x18000a552  mov     dword ptr [rbx+0Ch], 0
0x18000a559  mov     qword ptr [rbx+10h], 0
0x18000a561  mov     [rbx+18h], rax
0x18000a565  mov     [rsp+68h+picce.dwSize], 8
0x18000a570  mov     [rsp+68h+picce.dwICC], 4000h
0x18000a57b  lea     rcx, [rsp+68h+picce]; picce
0x18000a583  call    InitCommonControlsEx
0x18000a588  jmp     short loc_18000A58C
0x18000a58a  xor     ebx, ebx
0x18000a58c  test    rbx, rbx
0x18000a58f  jz      short loc_18000A5EB
0x18000a591  sub     esi, 836h
0x18000a597  jz      short loc_18000A5DD
0x18000a599  cmp     esi, 2
0x18000a59c  jnz     short loc_18000A5CA
0x18000a59e  lea     r9, ?s_CopySettings_DlgProc@CIntlAdvancedDlg@@KA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000a5a5  mov     edx, 2BCh; lpTemplateName
0x18000a5aa  mov     qword ptr [rsp+68h+dwAuthnLevel], rbx; dwInitParam
0x18000a5af  mov     r8, rbp; hWndParent
0x18000a5b2  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000a5b9  call    cs:__imp_DialogBoxParamW
0x18000a5bf  test    rax, rax
0x18000a5c2  jnz     short loc_18000A5CA
0x18000a5c4  call    cs:__imp_GetLastError
0x18000a5ca  mov     rcx, rbx; this
0x18000a5cd  call    ??1CIntlAdvancedDlg@@QEAA@XZ; CIntlAdvancedDlg::~CIntlAdvancedDlg(void)
0x18000a5d2  mov     rcx, rbx
0x18000a5d5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a5db  jmp     short loc_18000A5F0
0x18000a5dd  lea     r9, ?s_SysLocale_DlgProc@CIntlAdvancedDlg@@KA_JPEAUHWND__@@I_K_J@Z; CIntlAdvancedDlg::s_SysLocale_DlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000a5e4  mov     edx, 320h
0x18000a5e9  jmp     short loc_18000A5AA
0x18000a5eb  mov     edi, 8007000Eh
0x18000a5f0  mov     rcx, [rsp+68h+pProxy]
0x18000a5f8  mov     rax, [rcx]
0x18000a5fb  mov     rax, [rax+10h]
0x18000a5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a604  call    cs:__imp_CoUninitialize
0x18000a60a  test    edi, edi
0x18000a60c  jns     short loc_18000A620
0x18000a60e  cmp     edi, 800704C7h
0x18000a614  jz      short loc_18000A620
0x18000a616  mov     edx, edi; dwMessageId
0x18000a618  mov     rcx, rbp; hwndOwner
0x18000a61b  call    ?Intl_ShowSystemErrorMessage@@YAXPEAUHWND__@@K@Z; Intl_ShowSystemErrorMessage(HWND__ *,ulong)
0x18000a620  mov     eax, edi
0x18000a622  mov     rbx, [rsp+68h+arg_0]
0x18000a627  add     rsp, 50h
0x18000a62b  pop     rdi
0x18000a62c  pop     rsi
0x18000a62d  pop     rbp
0x18000a62e  retn
```
