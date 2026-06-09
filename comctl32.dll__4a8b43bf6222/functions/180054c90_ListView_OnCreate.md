# ListView_OnCreate

- ea: `0x180054c90`
- end: `0x180055064`
- name: `ListView_OnCreate`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x180017bac`
- `0x1800184b8`
- `0x18002eab0`
- `0x18002ec60`
- `0x180054c90`
- `0x180058000`
- `0x180058390`
- `0x180058600`
- `0x18005bde8`
- `0x1800791a4`
- `0x18008691c`
- `0x18008ab60`
- `0x180090020`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180054d14`
- `ADVAPI32!RegOpenKeyExW` at `0x180054d14`
- `ADVAPI32!RegQueryValueExW` at `0x180054d51`
- `ADVAPI32!RegQueryValueExW` at `0x180054d51`
- `ADVAPI32!RegCloseKey` at `0x180054d61`
- `ADVAPI32!RegCloseKey` at `0x180054d61`
- `USER32!GetClientRect` at `0x180055007`
- `USER32!GetClientRect` at `0x180055007`
- `USER32!SendMessageW` at `0x180055020`
- `USER32!SendMessageW` at `0x180055038`
- `USER32!SendMessageW` at `0x180055020`
- `USER32!SendMessageW` at `0x180055038`
- `USER32!GetDoubleClickTime` at `0x180055041`
- `USER32!GetDoubleClickTime` at `0x180055041`
- `USER32!RedrawWindow` at `0x180054f7d`
- `USER32!RedrawWindow` at `0x180054f7d`
- `USER32!CreateWindowExW` at `0x180054fc4`
- `USER32!CreateWindowExW` at `0x180054fc4`
- `USER32!SetTimer` at `0x180055054`
- `USER32!SetTimer` at `0x180055054`

## pseudocode

```c
__int64 __fastcall ListView_OnCreate(__int64 a1, _DWORD *a2)
{
  bool v4; // zf
  int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // eax
  HDPA v9; // rax
  HDPA v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdx
  char v15; // al
  int v16; // ecx
  int v17; // eax
  __int64 v18; // rdx
  HWND Window; // rax
  HWND v20; // rbx
  UINT DoubleClickTime; // eax
  BYTE Data[4]; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-25h] BYREF
  DWORD Type; // [rsp+68h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  LPARAM lParam; // [rsp+80h] [rbp-9h] BYREF
  HWND v27; // [rsp+88h] [rbp-1h]
  __int64 v28; // [rsp+90h] [rbp+7h]
  struct tagRECT Rect; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v30; // [rsp+A8h] [rbp+1Fh]
  __int64 v31; // [rsp+B0h] [rbp+27h]
  __int64 v32; // [rsp+B8h] [rbp+2Fh]

  CCCreateWindow();
  InitDitherBrush();
  CIInitialize(a1, *(_QWORD *)a1, a2);
  v4 = (*(_DWORD *)(a1 + 16) & 0x10000000) == 0;
  *(_DWORD *)(a1 + 80) = a2[18];
  if ( !v4 )
    *(_DWORD *)(a1 + 72) |= 2u;
  hKey = 0;
  v5 = 1;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"UseDoubleClickTimer", 0, &Type, Data, &cbData) )
      v5 = *(_DWORD *)Data;
    RegCloseKey(hKey);
  }
  g_bUseDblClickTimer = v5;
  if ( (*(_DWORD *)(a1 + 16) & 0x1000) != 0 )
  {
    v6 = LVRange_Create();
    *(_QWORD *)(a1 + 496) = v6;
    if ( v6 )
    {
      v7 = LVRange_Create();
      *(_QWORD *)(a1 + 504) = v7;
      if ( v7 )
        goto LABEL_10;
    }
  }
  else
  {
    v9 = DPA_CreateEx(16, *(HANDLE *)(a1 + 120));
    *(_QWORD *)(a1 + 64) = v9;
    if ( v9 )
    {
      v10 = DPA_CreateEx(16, *(HANDLE *)(a1 + 120));
      *(_QWORD *)(a1 + 288) = v10;
      if ( v10 )
      {
LABEL_10:
        *(_DWORD *)(a1 + 548) = -1;
        *(_DWORD *)(a1 + 544) = -1;
        *(_DWORD *)(a1 + 532) = -1;
        *(_DWORD *)(a1 + 336) = -1;
        *(_DWORD *)(a1 + 144) = -1;
        *(_DWORD *)(a1 + 140) = -1;
        *(_DWORD *)(a1 + 216) = -1;
        *(_DWORD *)(a1 + 320) = -1;
        *(_DWORD *)(a1 + 304) = 0x7FFFFFFF;
        *(_DWORD *)(a1 + 164) = a2[9];
        *(_DWORD *)(a1 + 168) = a2[8];
        if ( (*(_DWORD *)(a1 + 16) & 3) == 2 )
          *(_DWORD *)(a1 + 72) |= 0x20u;
        ListView_OnSetFont(a1, 0, 0);
        *(_DWORD *)(a1 + 252) = *(_DWORD *)(a1 + 240) + 16 * *(_DWORD *)(a1 + 132);
        v8 = *(_DWORD *)(a1 + 16);
        if ( (v8 & 0x400) != 0 && (v8 & 3) == 1 )
          *(_DWORD *)(a1 + 256) = *(_DWORD *)(a1 + 472);
        else
          *(_DWORD *)(a1 + 472) = *(_DWORD *)(a1 + 256);
        ListView_OnSetIconSpacing(a1, -1);
        ListView_UpdateScrollBars(a1);
        v14 = g_clrWindow;
        *(_DWORD *)(a1 + 104) = -16777216;
        *(_DWORD *)(a1 + 108) = -16777216;
        *(_DWORD *)(a1 + 616) = -16777216;
        *(_DWORD *)(a1 + 96) = -1;
        ListView_OnSetBkColor(a1, v14);
        v15 = *(_DWORD *)(a1 + 16) & 3;
        *(_DWORD *)(a1 + 452) = 0x7FFFFFFF;
        if ( v15 == 1 )
          ListView_RInitialize(a1, 0);
        v16 = *(_DWORD *)(a1 + 16);
        if ( (v16 & 0x8000000) != 0 )
        {
          v17 = *(_DWORD *)(a1 + 96);
          v18 = g_clrBtnFace;
          *(_DWORD *)(a1 + 16) = v16 | 0x8000000;
          *(_DWORD *)(a1 + 100) = v17;
          ListView_OnSetBkColor(a1, v18);
          RedrawWindow(*(HWND *)a1, 0, 0, 5u);
        }
        Window = CreateWindowExW(0, L"tooltips_class32", 0, 0x80000002, 0, 0, 0, 0, 0, 0, g_hinst, 0);
        *(_QWORD *)(a1 + 208) = Window;
        if ( Window )
        {
          v27 = *(HWND *)a1;
          *(_QWORD *)&Rect.left = 0;
          *(_QWORD *)&Rect.right = 0;
          v32 = 0;
          lParam = 0x10000000040LL;
          v28 = 0;
          v30 = 0;
          v31 = -1;
          GetClientRect(v27, &Rect);
          SendMessageW(*(HWND *)(a1 + 208), 0x432u, 0, (LPARAM)&lParam);
          SendMessageW(*(HWND *)(a1 + 208), 0x30u, *(_QWORD *)(a1 + 88), 0);
        }
        v20 = *(HWND *)a1;
        DoubleClickTime = GetDoubleClickTime();
        SetTimer(v20, 0x2Du, DoubleClickTime, 0);
        return 1;
      }
      DPA_Destroy(*(HDPA *)(a1 + 64));
    }
  }
  v11 = *(_QWORD *)(a1 + 496);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = *(_QWORD *)(a1 + 504);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x180054c90  mov     [rsp-8+arg_10], rbx
0x180054c95  mov     [rsp-8+arg_18], rsi
0x180054c9a  push    rbp
0x180054c9b  push    rdi
0x180054c9c  push    r14
0x180054c9e  lea     rbp, [rsp-47h]
0x180054ca3  sub     rsp, 0D0h
0x180054caa  mov     rax, cs:__security_cookie
0x180054cb1  xor     rax, rsp
0x180054cb4  mov     [rbp+57h+var_20], rax
0x180054cb8  mov     rsi, rdx
0x180054cbb  mov     rbx, rcx
0x180054cbe  call    CCCreateWindow
0x180054cc3  call    InitDitherBrush
0x180054cc8  mov     rdx, [rbx]
0x180054ccb  mov     r8, rsi
0x180054cce  mov     rcx, rbx
0x180054cd1  call    CIInitialize
0x180054cd6  test    dword ptr [rbx+10h], 10000000h
0x180054cdd  mov     eax, [rsi+48h]
0x180054ce0  mov     [rbx+50h], eax
0x180054ce3  jz      short loc_180054CE9
0x180054ce5  or      dword ptr [rbx+48h], 2
0x180054ce9  xor     r14d, r14d
0x180054cec  lea     rax, [rbp+57h+hKey]
0x180054cf0  mov     r9d, 20019h; samDesired
0x180054cf6  mov     [rbp+57h+hKey], r14
0x180054cfa  xor     r8d, r8d; ulOptions
0x180054cfd  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180054d02  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180054d09  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180054d10  lea     edi, [r14+1]
0x180054d14  call    cs:__imp_RegOpenKeyExW
0x180054d1a  test    eax, eax
0x180054d1c  jnz     short loc_180054D67
0x180054d1e  mov     rcx, [rbp+57h+hKey]; hKey
0x180054d22  lea     rax, [rbp+57h+cbData]
0x180054d26  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180054d2b  lea     r9, [rbp+57h+Type]; lpType
0x180054d2f  lea     rax, [rbp+57h+Data]
0x180054d33  mov     [rbp+57h+Type], r14d
0x180054d37  xor     r8d, r8d; lpReserved
0x180054d3a  mov     [rsp+0E0h+phkResult], rax; lpData
0x180054d3f  lea     rdx, aUsedoubleclick; "UseDoubleClickTimer"
0x180054d46  mov     dword ptr [rbp+57h+Data], r14d
0x180054d4a  mov     [rbp+57h+cbData], 4
0x180054d51  call    cs:__imp_RegQueryValueExW
0x180054d57  mov     rcx, [rbp+57h+hKey]; hKey
0x180054d5b  test    eax, eax
0x180054d5d  cmovz   edi, dword ptr [rbp+57h+Data]
0x180054d61  call    cs:__imp_RegCloseKey
0x180054d67  mov     cs:g_bUseDblClickTimer, edi
0x180054d6d  test    dword ptr [rbx+10h], 1000h
0x180054d74  jz      loc_180054E54
0x180054d7a  call    LVRange_Create
0x180054d7f  mov     [rbx+1F0h], rax
0x180054d86  test    rax, rax
0x180054d89  jz      loc_180054E91
0x180054d8f  call    LVRange_Create
0x180054d94  mov     [rbx+1F8h], rax
0x180054d9b  test    rax, rax
0x180054d9e  jz      loc_180054E91
0x180054da4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180054da8  mov     dword ptr [rbx+224h], 0FFFFFFFFh
0x180054db2  mov     [rbx+220h], edi
0x180054db8  mov     [rbx+214h], edi
0x180054dbe  mov     [rbx+150h], edi
0x180054dc4  mov     [rbx+90h], edi
0x180054dca  mov     [rbx+8Ch], edi
0x180054dd0  mov     [rbx+0D8h], edi
0x180054dd6  mov     [rbx+140h], edi
0x180054ddc  mov     dword ptr [rbx+130h], 7FFFFFFFh
0x180054de6  mov     eax, [rsi+24h]
0x180054de9  mov     [rbx+0A4h], eax
0x180054def  mov     eax, [rsi+20h]
0x180054df2  mov     sil, 3
0x180054df5  mov     [rbx+0A8h], eax
0x180054dfb  mov     eax, [rbx+10h]
0x180054dfe  and     al, sil
0x180054e01  cmp     al, 2
0x180054e03  jnz     short loc_180054E09
0x180054e05  or      dword ptr [rbx+48h], 20h
0x180054e09  xor     r8d, r8d
0x180054e0c  xor     edx, edx
0x180054e0e  mov     rcx, rbx
0x180054e11  call    ListView_OnSetFont
0x180054e16  mov     eax, [rbx+84h]
0x180054e1c  shl     eax, 4
0x180054e1f  add     eax, [rbx+0F0h]
0x180054e25  mov     [rbx+0FCh], eax
0x180054e2b  mov     eax, [rbx+10h]
0x180054e2e  bt      eax, 0Ah
0x180054e32  jnb     loc_180054EE7
0x180054e38  and     al, sil
0x180054e3b  cmp     al, 1
0x180054e3d  jnz     loc_180054EE7
0x180054e43  mov     eax, [rbx+1D8h]
0x180054e49  mov     [rbx+100h], eax
0x180054e4f  jmp     loc_180054EF3
0x180054e54  mov     rdx, [rbx+78h]; hheap
0x180054e58  mov     edi, 10h
0x180054e5d  mov     ecx, edi; cpGrow
0x180054e5f  call    DPA_CreateEx
0x180054e64  mov     [rbx+40h], rax
0x180054e68  test    rax, rax
0x180054e6b  jz      short loc_180054E91
0x180054e6d  mov     rdx, [rbx+78h]; hheap
0x180054e71  mov     ecx, edi; cpGrow
0x180054e73  call    DPA_CreateEx
0x180054e78  mov     [rbx+120h], rax
0x180054e7f  test    rax, rax
0x180054e82  jnz     loc_180054DA4
0x180054e88  mov     rcx, [rbx+40h]; hdpa
0x180054e8c  call    DPA_Destroy
0x180054e91  mov     rcx, [rbx+1F0h]
0x180054e98  test    rcx, rcx
0x180054e9b  jz      short loc_180054EA9
0x180054e9d  mov     rax, [rcx]
0x180054ea0  mov     rax, [rax+10h]
0x180054ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ea9  mov     rcx, [rbx+1F8h]
0x180054eb0  test    rcx, rcx
0x180054eb3  jz      short loc_180054EC1
0x180054eb5  mov     rax, [rcx]
0x180054eb8  mov     rax, [rax+10h]
0x180054ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ec1  xor     eax, eax
0x180054ec3  mov     rcx, [rbp+57h+var_20]
0x180054ec7  xor     rcx, rsp; StackCookie
0x180054eca  call    __security_check_cookie
0x180054ecf  lea     r11, [rsp+0E0h+var_10]
0x180054ed7  mov     rbx, [r11+30h]
0x180054edb  mov     rsi, [r11+38h]
0x180054edf  mov     rsp, r11
0x180054ee2  pop     r14
0x180054ee4  pop     rdi
0x180054ee5  pop     rbp
0x180054ee6  retn
0x180054ee7  mov     eax, [rbx+100h]
0x180054eed  mov     [rbx+1D8h], eax
0x180054ef3  mov     rdx, rdi
0x180054ef6  mov     rcx, rbx
0x180054ef9  call    ListView_OnSetIconSpacing
0x180054efe  mov     rcx, rbx
0x180054f01  call    ListView_UpdateScrollBars
0x180054f06  mov     edx, cs:g_clrWindow
0x180054f0c  mov     eax, 0FF000000h
0x180054f11  mov     rcx, rbx
0x180054f14  mov     [rbx+68h], eax
0x180054f17  mov     [rbx+6Ch], eax
0x180054f1a  mov     [rbx+268h], eax
0x180054f20  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x180054f27  call    ListView_OnSetBkColor
0x180054f2c  mov     eax, [rbx+10h]
0x180054f2f  and     al, sil
0x180054f32  mov     dword ptr [rbx+1C4h], 7FFFFFFFh
0x180054f3c  cmp     al, 1
0x180054f3e  jnz     short loc_180054F4A
0x180054f40  xor     edx, edx
0x180054f42  mov     rcx, rbx
0x180054f45  call    ListView_RInitialize
0x180054f4a  mov     ecx, [rbx+10h]
0x180054f4d  mov     edx, 8000000h
0x180054f52  test    edx, ecx
0x180054f54  jz      short loc_180054F83
0x180054f56  mov     eax, [rbx+60h]
0x180054f59  or      ecx, edx
0x180054f5b  mov     edx, cs:g_clrBtnFace
0x180054f61  mov     [rbx+10h], ecx
0x180054f64  mov     rcx, rbx
0x180054f67  mov     [rbx+64h], eax
0x180054f6a  call    ListView_OnSetBkColor
0x180054f6f  mov     rcx, [rbx]; hWnd
0x180054f72  mov     r9d, 5; flags
0x180054f78  xor     r8d, r8d; hrgnUpdate
0x180054f7b  xor     edx, edx; lprcUpdate
0x180054f7d  call    cs:__imp_RedrawWindow
0x180054f83  mov     rax, cs:g_hinst
0x180054f8a  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x180054f91  mov     [rsp+0E0h+lpParam], r14; lpParam
0x180054f96  mov     r9d, 80000002h; dwStyle
0x180054f9c  mov     [rsp+0E0h+hInstance], rax; hInstance
0x180054fa1  xor     r8d, r8d; lpWindowName
0x180054fa4  mov     [rsp+0E0h+hMenu], r14; hMenu
0x180054fa9  xor     ecx, ecx; dwExStyle
0x180054fab  mov     [rsp+0E0h+hWndParent], r14; hWndParent
0x180054fb0  mov     [rsp+0E0h+nHeight], r14d; nHeight
0x180054fb5  mov     [rsp+0E0h+nWidth], r14d; nWidth
0x180054fba  mov     dword ptr [rsp+0E0h+lpcbData], r14d; Y
0x180054fbf  mov     dword ptr [rsp+0E0h+phkResult], r14d; X
0x180054fc4  call    cs:__imp_CreateWindowExW
0x180054fca  mov     [rbx+0D0h], rax
0x180054fd1  test    rax, rax
0x180054fd4  jz      short loc_18005503E
0x180054fd6  mov     rcx, [rbx]; hWnd
0x180054fd9  lea     rdx, [rbp+57h+Rect]; lpRect
0x180054fdd  mov     [rbp+57h+var_58], rcx
0x180054fe1  mov     qword ptr [rbp+57h+Rect.left], r14
0x180054fe5  mov     qword ptr [rbp+57h+Rect.right], r14
0x180054fe9  mov     [rbp+57h+var_28], r14
0x180054fed  mov     dword ptr [rbp+57h+lParam], 40h ; '@'
0x180054ff4  mov     dword ptr [rbp+57h+lParam+4], 100h
0x180054ffb  mov     [rbp+57h+var_50], r14
0x180054fff  mov     [rbp+57h+var_38], r14
0x180055003  mov     [rbp+57h+var_30], rdi
0x180055007  call    cs:__imp_GetClientRect
0x18005500d  mov     rcx, [rbx+0D0h]; hWnd
0x180055014  lea     r9, [rbp+57h+lParam]; lParam
0x180055018  xor     r8d, r8d; wParam
0x18005501b  mov     edx, 432h; Msg
0x180055020  call    cs:__imp_SendMessageW
0x180055026  mov     r8, [rbx+58h]; wParam
0x18005502a  xor     r9d, r9d; lParam
0x18005502d  mov     rcx, [rbx+0D0h]; hWnd
0x180055034  lea     edx, [r9+30h]; Msg
0x180055038  call    cs:__imp_SendMessageW
0x18005503e  mov     rbx, [rbx]
0x180055041  call    cs:__imp_GetDoubleClickTime
0x180055047  xor     r9d, r9d; lpTimerFunc
0x18005504a  mov     rcx, rbx; hWnd
0x18005504d  mov     r8d, eax; uElapse
0x180055050  lea     edx, [r9+2Dh]; nIDEvent
0x180055054  call    cs:__imp_SetTimer
0x18005505a  mov     eax, 1
0x18005505f  jmp     loc_180054EC3
```
