# PePropertySheet

- ea: `0x18001c2cc`
- end: `0x18001c959`
- name: `PePropertySheet`
- size: `1677`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800149b4`
- `0x180014b40`

## callees

- `0x18000f380`
- `0x1800188c0`
- `0x18001c2cc`
- `0x18002b058`
- `0x180039318`
- `0x1800394c4`
- `0x180039820`
- `0x18003bc38`
- `0x18003bea0`
- `0x18003c43c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001c736`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001c736`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001c816`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001c816`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c539`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c539`
- `USER32!DestroyIcon` at `0x18001c917`
- `USER32!DestroyIcon` at `0x18001c917`
- `rtutils!TracePrintfExA` at `0x18001c317`
- `rtutils!TracePrintfExA` at `0x18001c678`
- `rtutils!TracePrintfExA` at `0x18001c75d`
- `rtutils!TracePrintfExA` at `0x18001c77f`
- `rtutils!TracePrintfExA` at `0x18001c80d`
- `rtutils!TracePrintfExA` at `0x18001c8d6`
- `rtutils!TracePrintfExA` at `0x18001c930`
- `rtutils!TracePrintfExA` at `0x18001c317`
- `rtutils!TracePrintfExA` at `0x18001c678`
- `rtutils!TracePrintfExA` at `0x18001c75d`
- `rtutils!TracePrintfExA` at `0x18001c77f`
- `rtutils!TracePrintfExA` at `0x18001c80d`
- `rtutils!TracePrintfExA` at `0x18001c8d6`
- `rtutils!TracePrintfExA` at `0x18001c930`

## string_xrefs

- `0x18001c773`: `CreatePage failed`

## pseudocode

```c
void __fastcall PePropertySheet(__int64 a1)
{
  DWORD v2; // ecx
  __int64 v3; // rbx
  bool v4; // zf
  signed int v5; // esi
  int v6; // edx
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(HWND); // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  int *v11; // r14
  int v12; // ebx
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int64 v18; // rax
  __int64 v19; // r15
  int v20; // ebx
  HPROPSHEETPAGE PropertySheetPageW; // rax
  struct _PSP *v22; // r14
  unsigned int v23; // r14d
  HPROPSHEETPAGE v24; // rax
  WCHAR *v25; // rbx
  __int64 v26; // rax
  void *v27; // r14
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // r15d
  wchar_t *v31; // rax
  HRESULT v32; // eax
  HICON CurrentIconEntryType; // r14
  __int64 v34; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v36; // [rsp+40h] [rbp-C0h] BYREF
  PROPSHEETHEADERW_V2 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-50h]
  _OWORD v39[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-20h]
  _DWORD v41[2]; // [rsp+F0h] [rbp-10h] BYREF
  HINSTANCE v42; // [rsp+F8h] [rbp-8h]
  __int64 v43; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v44)(HWND); // [rsp+118h] [rbp+18h]
  __int64 v45; // [rsp+120h] [rbp+20h]
  int v46; // [rsp+158h] [rbp+58h] BYREF
  HINSTANCE v47; // [rsp+160h] [rbp+60h]
  __int64 v48; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v49)(); // [rsp+180h] [rbp+80h]
  int v50; // [rsp+1C0h] [rbp+C0h]
  HINSTANCE v51; // [rsp+1C8h] [rbp+C8h]
  __int64 v52; // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v53)(HWND); // [rsp+1E8h] [rbp+E8h]
  int v54; // [rsp+228h] [rbp+128h]
  HINSTANCE v55; // [rsp+230h] [rbp+130h]
  unsigned __int64 v56; // [rsp+238h] [rbp+138h]
  __int64 (__fastcall *v57)(HWND); // [rsp+250h] [rbp+150h]
  char v58; // [rsp+290h] [rbp+190h] BYREF

  v2 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "PePropertySheet");
    v2 = g_dwTraceId;
  }
  if ( !a1 || (v3 = *(_QWORD *)(a1 + 872)) == 0 || !*(_QWORD *)(a1 + 16) )
  {
    if ( v2 != -1 )
      TracePrintfExA(v2, 0xCu, "Invalid Input Argument.");
    return;
  }
  memset_0(v41, 0, 0x208u);
  v4 = *(_DWORD *)(v3 + 548) == 0;
  v42 = g_hinstDll;
  v41[0] = 104;
  if ( v4 )
  {
    v5 = 5;
    v6 = *(_DWORD *)(a1 + 28);
    if ( *(_DWORD *)(v3 + 24) == 2 )
    {
      v7 = v6 != 0 ? 1433LL : 1425LL;
    }
    else
    {
      if ( *(_DWORD *)(v3 + 24) != 5 )
      {
        if ( *(_DWORD *)(a1 + 324) )
        {
          v8 = GeDlgProcMultiple;
          v7 = v6 != 0 ? 554LL : 155LL;
        }
        else
        {
          v8 = GeDlgProcSingle;
          v7 = v6 != 0 ? 555LL : 156LL;
        }
        goto LABEL_15;
      }
      v7 = v6 != 0 ? 1434LL : 568LL;
    }
    v8 = GeDlgProc;
LABEL_15:
    v44 = v8;
    v47 = g_hinstDll;
    v43 = v7;
    v45 = a1;
    v46 = 104;
    if ( v6 )
    {
      v48 = 1780;
    }
    else
    {
      v9 = 167;
      if ( *(_DWORD *)(v3 + 24) != 1 )
        v9 = 1426;
      v48 = v9;
    }
    v50 = 104;
    v49 = OeDlgProc;
    v51 = g_hinstDll;
    if ( *(_DWORD *)(v3 + 24) == 1 )
    {
      v10 = 162LL - (v6 != 0);
    }
    else if ( *(_DWORD *)(v3 + 24) == 2 )
    {
      v10 = 154LL - (v6 != 0);
    }
    else
    {
      v10 = 164LL - (v6 != 0);
    }
    v52 = v10;
    v53 = LoDlgProc;
    v11 = (int *)&v58;
    v55 = g_hinstDll;
    v54 = 104;
    v56 = (-(__int64)(v6 != 0) & 0xFFFFFFFFFFFFFFF2uLL) + 165;
    v57 = NeDlgProc;
    goto LABEL_27;
  }
  v43 = 1436;
  v44 = GeProvDlgProc;
  v11 = &v46;
  v5 = 2;
  v45 = a1;
LABEL_27:
  if ( *(_DWORD *)(a1 + 28) )
  {
    --v5;
  }
  else
  {
    v36 = 0;
    if ( (CoCreateInstance(&CLSID_NetConnectionUiUtilities, 0, 1u, &IID_INetConnectionUiUtilities, &v36) < 0
       || (v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v36 + 48LL))(v36, 50),
           (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36),
           v12))
      && (unsigned int)FIsTcpipInstalled() )
    {
      *((_QWORD *)v11 + 1) = g_hinstDll;
      *v11 = 104;
      memset_0(&v37, 0, 0x68u);
      if ( (unsigned int)HrLoadHNetGetFirewallSettingsPage((__int64)&v37, a1) )
      {
        *((_QWORD *)v11 + 2) = 574;
        *((_QWORD *)v11 + 5) = SaUnavailDlgProc;
      }
      else
      {
        v13 = *(_OWORD *)&v37.hInstance;
        *(_OWORD *)v11 = *(_OWORD *)&v37.dwSize;
        v14 = *(_OWORD *)&v37.pszCaption;
        *((_OWORD *)v11 + 1) = v13;
        v15 = *(_OWORD *)&v37.nStartPage;
        *((_OWORD *)v11 + 2) = v14;
        v16 = *(_OWORD *)&v37.pfnCallback;
        *((_OWORD *)v11 + 3) = v15;
        v17 = *(_OWORD *)&v37.hplWatermark;
        *((_OWORD *)v11 + 4) = v16;
        *(_QWORD *)&v16 = v38;
        *((_OWORD *)v11 + 5) = v17;
        *((_QWORD *)v11 + 12) = v16;
      }
    }
    else
    {
      --v5;
    }
  }
  v18 = *(_QWORD *)(a1 + 16);
  if ( (*(_DWORD *)(v18 + 12) & 0x40000000) != 0 )
  {
    v19 = *(_QWORD *)(v18 + 552);
    v20 = 0;
    if ( v5 <= 0 )
      return;
    while ( 1 )
    {
      PropertySheetPageW = CreatePropertySheetPageW((LPCPROPSHEETPAGEW)&v41[26 * v20]);
      v22 = PropertySheetPageW;
      if ( !PropertySheetPageW )
        break;
      if ( !(*(unsigned int (__fastcall **)(HPROPSHEETPAGE, _QWORD))v19)(PropertySheetPageW, *(_QWORD *)(v19 + 8)) )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "AddPage failed");
        DestroyPropertySheetPage(v22);
        goto LABEL_58;
      }
      if ( ++v20 >= v5 )
        return;
    }
  }
  else
  {
    memset_0(&v37, 0, sizeof(v37));
    v40 = 0;
    v23 = 0;
    memset(v39, 0, sizeof(v39));
    if ( v5 <= 0 )
    {
LABEL_48:
      v25 = 0;
      v26 = PszFromId(g_hinstDll, 0x24Du);
      v27 = (void *)v26;
      if ( v26 )
      {
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(v26 + 2 * v28) );
        v29 = -1;
        do
          ++v29;
        while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 8LL) + 2 * v29) );
        v30 = v28 + v29 + 2;
        v31 = (wchar_t *)GlobalAlloc(0x40u, 2LL * v30);
        v25 = v31;
        if ( v31 )
        {
          v32 = StringCchPrintfExW(v31, v30, 0, 0, 0x100u, L"%s %s");
          if ( v32 < 0 && g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "PePropertySheet: StringCchPrintfExW failed. hr = 0x%x", v32);
        }
        else if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "Properties header allocation failed");
        }
        GlobalFree(v27);
      }
      CurrentIconEntryType = GetCurrentIconEntryType(*(_DWORD *)(*(_QWORD *)(a1 + 872) + 24LL), 1);
      memset_0(&v37.hwndParent, 0, 0x58u);
      v37.dwSize = 96;
      v34 = *(_QWORD *)(a1 + 16);
      v37.dwFlags = (CurrentIconEntryType != 0 ? 2 : 0) | 0x2000180;
      v37.hwndParent = *(HWND *)(v34 + 4);
      v37.hInstance = g_hinstDll;
      if ( v25 )
        v37.pszCaption = v25;
      else
        v37.pszCaption = *(LPCWSTR *)(*(_QWORD *)(a1 + 872) + 8LL);
      v37.nPages = v5;
      v37.ppsp = (LPCPROPSHEETPAGEW)v39;
      v37.hIcon = CurrentIconEntryType;
      v37.pfnCallback = (PFNPROPSHEETCALLBACK)UnHelpCallbackFunc;
      if ( PropertySheetW(&v37) == -1 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "PropertySheet failed");
        ErrorDlgUtil(*(HWND *)(*(_QWORD *)(a1 + 16) + 4LL), 0x13Eu, 0x27Bu, 0, ppv, 0x169u, 0xFAu);
      }
      Free0(v25);
      if ( CurrentIconEntryType )
        DestroyIcon(CurrentIconEntryType);
      return;
    }
    while ( 1 )
    {
      v24 = CreatePropertySheetPageW((LPCPROPSHEETPAGEW)&v41[26 * v23]);
      *((_QWORD *)v39 + v23) = v24;
      if ( !v24 )
        break;
      if ( (int)++v23 >= v5 )
        goto LABEL_48;
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CreatePage failed");
LABEL_58:
  ErrorDlgUtil(*(HWND *)(*(_QWORD *)(a1 + 16) + 4LL), 0x13Eu, 0x27Bu, 0, ppv, 0x169u, 0xFAu);
}

```

## disassembly

```asm
0x18001c2cc  push    rbp
0x18001c2ce  push    rbx
0x18001c2cf  push    rsi
0x18001c2d0  push    rdi
0x18001c2d1  push    r12
0x18001c2d3  push    r13
0x18001c2d5  push    r14
0x18001c2d7  push    r15
0x18001c2d9  lea     rbp, [rsp-218h]
0x18001c2e1  sub     rsp, 318h
0x18001c2e8  mov     rax, cs:__security_cookie
0x18001c2ef  xor     rax, rsp
0x18001c2f2  mov     [rbp+250h+var_50], rax
0x18001c2f9  mov     rdi, rcx
0x18001c2fc  or      r13d, 0FFFFFFFFh
0x18001c300  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c306  cmp     ecx, r13d
0x18001c309  jz      short loc_18001C323
0x18001c30b  lea     r8, aPepropertyshee_0; "PePropertySheet"
0x18001c312  mov     edx, 0Ch; dwFlags
0x18001c317  call    cs:__imp_TracePrintfExA
0x18001c31d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c323  xor     r12d, r12d
0x18001c326  test    rdi, rdi
0x18001c329  jz      loc_18001C91F
0x18001c32f  mov     rbx, [rdi+368h]
0x18001c336  test    rbx, rbx
0x18001c339  jz      loc_18001C91F
0x18001c33f  cmp     [rdi+10h], r12
0x18001c343  jz      loc_18001C91F
0x18001c349  xor     edx, edx; Val
0x18001c34b  lea     rcx, [rbp+250h+var_260]; void *
0x18001c34f  mov     r8d, 208h; Size
0x18001c355  call    memset_0
0x18001c35a  cmp     [rbx+224h], r12d
0x18001c361  lea     r15d, [r12+68h]
0x18001c366  mov     rax, cs:g_hinstDll
0x18001c36d  lea     r8d, [r12+1]; dwClsContext
0x18001c372  mov     [rbp+250h+var_258], rax
0x18001c376  mov     [rbp+250h+var_260], r15d
0x18001c37a  jnz     loc_18001C4EC
0x18001c380  cmp     dword ptr [rbx+18h], 2
0x18001c384  lea     esi, [r12+5]
0x18001c389  mov     edx, [rdi+1Ch]
0x18001c38c  mov     eax, edx
0x18001c38e  jnz     short loc_18001C3A8
0x18001c390  neg     eax
0x18001c392  sbb     rcx, rcx
0x18001c395  and     ecx, 8
0x18001c398  add     rcx, 591h
0x18001c39f  lea     rax, GeDlgProc
0x18001c3a6  jmp     short loc_18001C3FE
0x18001c3a8  cmp     [rbx+18h], esi
0x18001c3ab  jnz     short loc_18001C3C1
0x18001c3ad  neg     eax
0x18001c3af  sbb     rcx, rcx
0x18001c3b2  and     ecx, 362h
0x18001c3b8  add     rcx, 238h
0x18001c3bf  jmp     short loc_18001C39F
0x18001c3c1  cmp     [rdi+144h], r12d
0x18001c3c8  jz      short loc_18001C3E5
0x18001c3ca  neg     eax
0x18001c3cc  lea     rax, GeDlgProcMultiple
0x18001c3d3  sbb     rcx, rcx
0x18001c3d6  and     ecx, 18Fh
0x18001c3dc  add     rcx, 9Bh
0x18001c3e3  jmp     short loc_18001C3FE
0x18001c3e5  neg     eax
0x18001c3e7  lea     rax, GeDlgProcSingle
0x18001c3ee  sbb     rcx, rcx
0x18001c3f1  and     ecx, 18Fh
0x18001c3f7  add     rcx, 9Ch
0x18001c3fe  mov     [rbp+250h+var_238], rax
0x18001c402  mov     rax, cs:g_hinstDll
0x18001c409  mov     [rbp+250h+var_1F0], rax
0x18001c40d  mov     [rbp+250h+var_250], rcx
0x18001c411  mov     [rbp+250h+var_230], rdi
0x18001c415  mov     [rbp+250h+var_1F8], r15d
0x18001c419  test    edx, edx
0x18001c41b  jz      short loc_18001C427
0x18001c41d  mov     [rbp+250h+var_1E8], 6F4h
0x18001c425  jmp     short loc_18001C43C
0x18001c427  cmp     [rbx+18h], r8d
0x18001c42b  mov     eax, 0A7h
0x18001c430  mov     ecx, 592h
0x18001c435  cmovnz  eax, ecx
0x18001c438  mov     [rbp+250h+var_1E8], rax
0x18001c43c  lea     rax, OeDlgProc
0x18001c443  mov     [rbp+250h+var_190], r15d
0x18001c44a  mov     [rbp+250h+var_1D0], rax
0x18001c451  mov     rax, cs:g_hinstDll
0x18001c458  mov     [rbp+250h+var_188], rax
0x18001c45f  mov     eax, edx
0x18001c461  cmp     [rbx+18h], r8d
0x18001c465  jnz     short loc_18001C475
0x18001c467  neg     eax
0x18001c469  sbb     rcx, rcx
0x18001c46c  add     rcx, 0A2h
0x18001c473  jmp     short loc_18001C495
0x18001c475  cmp     dword ptr [rbx+18h], 2
0x18001c479  jnz     short loc_18001C489
0x18001c47b  neg     eax
0x18001c47d  sbb     rcx, rcx
0x18001c480  add     rcx, 9Ah
0x18001c487  jmp     short loc_18001C495
0x18001c489  neg     eax
0x18001c48b  sbb     rcx, rcx
0x18001c48e  add     rcx, 0A4h
0x18001c495  lea     rax, LoDlgProc
0x18001c49c  mov     [rbp+250h+var_180], rcx
0x18001c4a3  mov     [rbp+250h+var_168], rax
0x18001c4aa  lea     r14, [rbp+250h+var_C0]
0x18001c4b1  mov     rax, cs:g_hinstDll
0x18001c4b8  neg     edx
0x18001c4ba  mov     [rbp+250h+var_120], rax
0x18001c4c1  sbb     rax, rax
0x18001c4c4  mov     [rbp+250h+var_128], r15d
0x18001c4cb  and     rax, 0FFFFFFFFFFFFFFF2h
0x18001c4cf  add     rax, 0A5h
0x18001c4d5  mov     [rbp+250h+var_118], rax
0x18001c4dc  lea     rax, NeDlgProc
0x18001c4e3  mov     [rbp+250h+var_100], rax
0x18001c4ea  jmp     short loc_18001C50C
0x18001c4ec  lea     rax, GeProvDlgProc
0x18001c4f3  mov     [rbp+250h+var_250], 59Ch
0x18001c4fb  mov     [rbp+250h+var_238], rax
0x18001c4ff  lea     r14, [rbp+250h+var_1F8]
0x18001c503  mov     esi, 2
0x18001c508  mov     [rbp+250h+var_230], rdi
0x18001c50c  cmp     [rdi+1Ch], r12d
0x18001c510  jz      short loc_18001C51A
0x18001c512  sub     esi, r8d
0x18001c515  jmp     loc_18001C606
0x18001c51a  lea     rax, [rsp+350h+var_310]
0x18001c51f  mov     [rsp+350h+var_310], r12
0x18001c524  lea     r9, IID_INetConnectionUiUtilities; riid
0x18001c52b  mov     [rsp+350h+ppv], rax; int
0x18001c530  xor     edx, edx; pUnkOuter
0x18001c532  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x18001c539  call    cs:__imp_CoCreateInstance
0x18001c53f  test    eax, eax
0x18001c541  js      short loc_18001C570
0x18001c543  mov     rcx, [rsp+350h+var_310]
0x18001c548  mov     edx, 32h ; '2'
0x18001c54d  mov     rax, [rcx]
0x18001c550  mov     rax, [rax+30h]
0x18001c554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c559  mov     rcx, [rsp+350h+var_310]
0x18001c55e  mov     ebx, eax
0x18001c560  mov     rdx, [rcx]
0x18001c563  mov     rax, [rdx+10h]
0x18001c567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c56c  test    ebx, ebx
0x18001c56e  jz      short loc_18001C579
0x18001c570  call    FIsTcpipInstalled
0x18001c575  test    eax, eax
0x18001c577  jnz     short loc_18001C580
0x18001c579  dec     esi
0x18001c57b  jmp     loc_18001C606
0x18001c580  mov     rax, cs:g_hinstDll
0x18001c587  lea     rcx, [rsp+350h+var_300]; void *
0x18001c58c  mov     r8, r15; Size
0x18001c58f  mov     [r14+8], rax
0x18001c593  xor     edx, edx; Val
0x18001c595  mov     [r14], r15d
0x18001c598  call    memset_0
0x18001c59d  mov     rdx, rdi
0x18001c5a0  lea     rcx, [rsp+350h+var_300]
0x18001c5a5  call    HrLoadHNetGetFirewallSettingsPage
0x18001c5aa  test    eax, eax
0x18001c5ac  jnz     short loc_18001C5F3
0x18001c5ae  movaps  xmm0, xmmword ptr [rsp+350h+var_300.dwSize]
0x18001c5b3  movaps  xmm1, xmmword ptr [rsp+350h+var_300.hInstance]
0x18001c5b8  movups  xmmword ptr [r14], xmm0
0x18001c5bc  movaps  xmm0, xmmword ptr [rsp+350h+var_300.pszCaption]
0x18001c5c1  movups  xmmword ptr [r14+10h], xmm1
0x18001c5c6  movaps  xmm1, xmmword ptr [rbp+250h+var_300.30h]
0x18001c5ca  movups  xmmword ptr [r14+20h], xmm0
0x18001c5cf  movaps  xmm0, xmmword ptr [rbp+250h+var_300.pfnCallback]
0x18001c5d3  movups  xmmword ptr [r14+30h], xmm1
0x18001c5d8  movaps  xmm1, xmmword ptr [rbp+250h+var_300.hplWatermark]
0x18001c5dc  movups  xmmword ptr [r14+40h], xmm0
0x18001c5e1  movsd   xmm0, [rbp+250h+var_2A0]
0x18001c5e6  movups  xmmword ptr [r14+50h], xmm1
0x18001c5eb  movsd   qword ptr [r14+60h], xmm0
0x18001c5f1  jmp     short loc_18001C606
0x18001c5f3  lea     rax, SaUnavailDlgProc
0x18001c5fa  mov     qword ptr [r14+10h], 23Eh
0x18001c602  mov     [r14+28h], rax
0x18001c606  mov     rax, [rdi+10h]
0x18001c60a  test    dword ptr [rax+0Ch], 40000000h
0x18001c611  jz      short loc_18001C68B
0x18001c613  mov     r15, [rax+228h]
0x18001c61a  mov     ebx, r12d
0x18001c61d  test    esi, esi
0x18001c61f  jle     loc_18001C936
0x18001c625  mov     eax, ebx
0x18001c627  imul    rcx, rax, 68h ; 'h'
0x18001c62b  lea     rax, [rbp+250h+var_260]
0x18001c62f  add     rcx, rax; constPropSheetPagePointer
0x18001c632  call    CreatePropertySheetPageW
0x18001c637  mov     r14, rax
0x18001c63a  test    rax, rax
0x18001c63d  jz      loc_18001C768
0x18001c643  mov     rdx, [r15+8]
0x18001c647  mov     rcx, rax
0x18001c64a  mov     rax, [r15]
0x18001c64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c652  test    eax, eax
0x18001c654  jz      short loc_18001C661
0x18001c656  inc     ebx
0x18001c658  cmp     ebx, esi
0x18001c65a  jl      short loc_18001C625
0x18001c65c  jmp     loc_18001C936
0x18001c661  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c667  cmp     ecx, r13d
0x18001c66a  jz      short loc_18001C67E
0x18001c66c  lea     r8, aAddpageFailed; "AddPage failed"
0x18001c673  mov     edx, 0Ch; dwFlags
0x18001c678  call    cs:__imp_TracePrintfExA
0x18001c67e  mov     rcx, r14; HPROPSHEETPAGE
0x18001c681  call    DestroyPropertySheetPage
0x18001c686  jmp     loc_18001C785
0x18001c68b  xor     edx, edx; Val
0x18001c68d  lea     rcx, [rsp+350h+var_300]; void *
0x18001c692  lea     r8d, [rdx+60h]; Size
0x18001c696  call    memset_0
0x18001c69b  xor     eax, eax
0x18001c69d  xorps   xmm0, xmm0
0x18001c6a0  mov     [rbp+250h+var_270], rax
0x18001c6a4  mov     r14d, r12d
0x18001c6a7  movups  [rbp+250h+var_290], xmm0
0x18001c6ab  movups  [rbp+250h+var_280], xmm0
0x18001c6af  test    esi, esi
0x18001c6b1  jle     short loc_18001C6DC
0x18001c6b3  mov     ebx, r14d
0x18001c6b6  lea     rcx, [rbp+250h+var_260]
0x18001c6ba  imul    rax, rbx, 68h ; 'h'
0x18001c6be  add     rcx, rax; constPropSheetPagePointer
0x18001c6c1  call    CreatePropertySheetPageW
0x18001c6c6  mov     qword ptr [rbp+rbx*8+250h+var_290], rax
0x18001c6cb  test    rax, rax
0x18001c6ce  jz      loc_18001C768
0x18001c6d4  inc     r14d
0x18001c6d7  cmp     r14d, esi
0x18001c6da  jl      short loc_18001C6B3
0x18001c6dc  mov     rcx, cs:g_hinstDll; hInstance
0x18001c6e3  mov     edx, 24Dh; uID
0x18001c6e8  mov     rbx, r12
0x18001c6eb  call    PszFromId
0x18001c6f0  mov     r14, rax
0x18001c6f3  test    rax, rax
0x18001c6f6  jz      loc_18001C81C
0x18001c6fc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c700  inc     rcx
0x18001c703  cmp     [rax+rcx*2], r12w
0x18001c708  jnz     short loc_18001C700
0x18001c70a  mov     rax, [rdi+368h]
0x18001c711  mov     rdx, [rax+8]
0x18001c715  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c719  inc     rax
0x18001c71c  cmp     [rdx+rax*2], r12w
0x18001c721  jnz     short loc_18001C719
0x18001c723  lea     r15, [rax+2]
0x18001c727  add     r15, rcx
0x18001c72a  mov     ecx, 40h ; '@'; uFlags
0x18001c72f  mov     r15d, r15d
0x18001c732  lea     rdx, [r15+r15]; dwBytes
0x18001c736  call    cs:__imp_GlobalAlloc
0x18001c73c  mov     rbx, rax
0x18001c73f  test    rax, rax
0x18001c742  jnz     short loc_18001C7B5
0x18001c744  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c74a  cmp     ecx, r13d
0x18001c74d  jz      loc_18001C813
0x18001c753  lea     r8, aPropertiesHead; "Properties header allocation failed"
0x18001c75a  lea     edx, [rax+0Ch]; dwFlags
0x18001c75d  call    cs:__imp_TracePrintfExA
0x18001c763  jmp     loc_18001C813
0x18001c768  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c76e  cmp     ecx, r13d
0x18001c771  jz      short loc_18001C785
0x18001c773  lea     r8, aCreatepageFail; "CreatePage failed"
0x18001c77a  mov     edx, 0Ch; dwFlags
0x18001c77f  call    cs:__imp_TracePrintfExA
0x18001c785  mov     rcx, [rdi+10h]
0x18001c789  xor     r9d, r9d
0x18001c78c  mov     [rsp+350h+var_320], 0FAh; UINT
0x18001c794  mov     edx, 13Eh; uID
0x18001c799  mov     r8d, 27Bh; dwMessageId
0x18001c79f  mov     dword ptr [rsp+350h+pszFormat], 169h; UINT
0x18001c7a7  mov     rcx, [rcx+4]; hWnd
0x18001c7ab  call    ErrorDlgUtil
0x18001c7b0  jmp     loc_18001C936
0x18001c7b5  mov     rax, [rdi+368h]
0x18001c7bc  xor     r9d, r9d; pcchRemaining
0x18001c7bf  mov     [rsp+350h+var_318], r14
0x18001c7c4  xor     r8d, r8d; ppszDestEnd
0x18001c7c7  mov     rdx, r15; cchDest
0x18001c7ca  mov     rcx, rbx; pszDest
  ... truncated ...
```
