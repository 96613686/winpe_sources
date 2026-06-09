# PWFieldSetText(ushort *,HWND__ *)

- ea: `0x1400231d8`
- end: `0x14002381d`
- name: `?PWFieldSetText@@YAJPEAGPEAUHWND__@@@Z`
- size: `1605`
- prototype: `__int64 __fastcall(unsigned __int16 *, HWND hwnd)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140024c44`

## callees

- `0x140002463`
- `0x1400231d8`
- `0x140025998`
- `0x140034ce4`
- `0x140036190`
- `0x1400369c0`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140023735`
- `KERNEL32!HeapFree` at `0x140023768`
- `KERNEL32!HeapFree` at `0x1400237ba`
- `KERNEL32!HeapFree` at `0x1400237e4`
- `KERNEL32!HeapFree` at `0x140023735`
- `KERNEL32!HeapFree` at `0x140023768`
- `KERNEL32!HeapFree` at `0x1400237ba`
- `KERNEL32!HeapFree` at `0x1400237e4`
- `KERNEL32!WideCharToMultiByte` at `0x1400234bd`
- `KERNEL32!WideCharToMultiByte` at `0x1400235cc`
- `KERNEL32!WideCharToMultiByte` at `0x1400234bd`
- `KERNEL32!WideCharToMultiByte` at `0x1400235cc`
- `KERNEL32!GetProcessHeap` at `0x14002326a`
- `KERNEL32!GetProcessHeap` at `0x140023456`
- `KERNEL32!GetProcessHeap` at `0x14002355d`
- `KERNEL32!GetProcessHeap` at `0x140023721`
- `KERNEL32!GetProcessHeap` at `0x140023754`
- `KERNEL32!GetProcessHeap` at `0x1400237a6`
- `KERNEL32!GetProcessHeap` at `0x1400237d0`
- `KERNEL32!GetProcessHeap` at `0x14002326a`
- `KERNEL32!GetProcessHeap` at `0x140023456`
- `KERNEL32!GetProcessHeap` at `0x14002355d`
- `KERNEL32!GetProcessHeap` at `0x140023721`
- `KERNEL32!GetProcessHeap` at `0x140023754`
- `KERNEL32!GetProcessHeap` at `0x1400237a6`
- `KERNEL32!GetProcessHeap` at `0x1400237d0`
- `KERNEL32!HeapAlloc` at `0x140023281`
- `KERNEL32!HeapAlloc` at `0x14002346b`
- `KERNEL32!HeapAlloc` at `0x140023576`
- `KERNEL32!HeapAlloc` at `0x140023281`
- `KERNEL32!HeapAlloc` at `0x14002346b`
- `KERNEL32!HeapAlloc` at `0x140023576`
- `USER32!SendMessageW` at `0x1400232e9`
- `USER32!SendMessageW` at `0x140023642`
- `USER32!SendMessageW` at `0x14002369a`
- `USER32!SendMessageW` at `0x1400236c2`
- `USER32!SendMessageW` at `0x1400232e9`
- `USER32!SendMessageW` at `0x140023642`
- `USER32!SendMessageW` at `0x14002369a`
- `USER32!SendMessageW` at `0x1400236c2`
- `USER32!GetCaretPos` at `0x1400236ab`
- `USER32!GetCaretPos` at `0x1400236ab`
- `USER32!SetFocus` at `0x14002367b`
- `USER32!SetFocus` at `0x14002367b`
- `USER32!GetSysColor` at `0x1400232fa`
- `USER32!GetSysColor` at `0x140023329`
- `USER32!GetSysColor` at `0x1400232fa`
- `USER32!GetSysColor` at `0x140023329`
- `USER32!SetWindowPos` at `0x140023706`
- `USER32!SetWindowPos` at `0x140023706`
- `USER32!GetClientRect` at `0x14002366c`
- `USER32!GetClientRect` at `0x1400236d5`
- `USER32!GetClientRect` at `0x14002366c`
- `USER32!GetClientRect` at `0x1400236d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400233f6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400233f6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002377c`
- `OLEAUT32!__imp_SysFreeString` at `0x140023790`
- `OLEAUT32!__imp_SysFreeString` at `0x14002377c`
- `OLEAUT32!__imp_SysFreeString` at `0x140023790`
- `UxTheme!IsAppThemed` at `0x14002343d`
- `UxTheme!IsAppThemed` at `0x14002343d`
- `UxTheme!GetThemeFont` at `0x1400233dd`
- `UxTheme!GetThemeFont` at `0x1400233dd`
- `UxTheme!OpenThemeData` at `0x1400233af`
- `UxTheme!OpenThemeData` at `0x1400233af`

## string_xrefs

- `0x1400233a5`: `TaskDialog`

## pseudocode

```c
__int64 __fastcall PWFieldSetText(unsigned __int16 *a1, HWND hwnd)
{
  __int64 v2; // rdi
  HWND v3; // r14
  WCHAR *v5; // rsi
  char *v6; // r15
  HANDLE ProcessHeap; // rax
  CEventLogger *v8; // rcx
  char *v9; // r12
  unsigned int v10; // ebx
  DWORD SysColor; // eax
  signed int ColorRTFString; // eax
  CEventLogger *v13; // rcx
  DWORD v14; // eax
  signed int v15; // eax
  CEventLogger *v16; // rcx
  signed int v17; // eax
  CEventLogger *v18; // rcx
  HTHEME v19; // rax
  WCHAR *lfFaceName; // rcx
  BSTR v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // ebx
  HANDLE v26; // rax
  void *v27; // r14
  CEventLogger *v28; // rcx
  unsigned int v29; // eax
  signed int v30; // eax
  CEventLogger *v31; // rcx
  unsigned int v32; // r9d
  __int64 v33; // rbx
  HANDLE v34; // rax
  void *v35; // rax
  CHAR *v36; // rbx
  __int64 v37; // rax
  void *v38; // r14
  HANDLE v39; // rax
  HANDLE v40; // rax
  char *v41; // rdi
  HANDLE v42; // rax
  char *v43; // rdi
  HANDLE v44; // rax
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-C0h] BYREF
  WPARAM wParam; // [rsp+48h] [rbp-B8h] BYREF
  char *v48; // [rsp+50h] [rbp-B0h] BYREF
  char *v49; // [rsp+58h] [rbp-A8h] BYREF
  struct tagPOINT Point; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem[2]; // [rsp+68h] [rbp-98h]
  const char *v52; // [rsp+78h] [rbp-88h]
  HWND hWnd; // [rsp+80h] [rbp-80h]
  struct tagRECT Rect; // [rsp+88h] [rbp-78h] BYREF
  LOGFONTW pFont; // [rsp+A0h] [rbp-60h] BYREF
  LPARAM lParam; // [rsp+100h] [rbp+0h] BYREF
  __int16 v57; // [rsp+10Ah] [rbp+Ah]

  v2 = 0;
  hWnd = hwnd;
  v3 = hwnd;
  wParam = 0;
  lpWideCharStr = 0;
  v52 = 0;
  *(_OWORD *)lpMem = 0;
  v5 = 0;
  memset_0(&pFont, 0, sizeof(pFont));
  Point = 0;
  v48 = 0;
  v49 = 0;
  Rect = 0;
  v6 = 0;
  memset_0(&lParam, 0, 0x9Cu);
  ProcessHeap = GetProcessHeap();
  v9 = (char *)HeapAlloc(ProcessHeap, 0, 0x400u);
  if ( !v9 )
  {
    v10 = -2147024882;
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x1726u,
      L"PWFieldSetText",
      0x8007000E);
    goto LABEL_43;
  }
  lParam = 0x100000000009CLL;
  v57 = 0;
  SendMessageW(v3, 0x447u, 0, (LPARAM)&lParam);
  SysColor = GetSysColor(5);
  ColorRTFString = MakeColorRTFString(SysColor, &v49);
  v10 = ColorRTFString;
  if ( ColorRTFString < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x1743u,
      L"PWFieldSetText",
      ColorRTFString);
    goto LABEL_43;
  }
  v14 = GetSysColor(8);
  v15 = MakeColorRTFString(v14, &v48);
  v10 = v15;
  if ( v15 < 0 )
  {
    CEventLogger::LogError(
      v16,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x1746u,
      L"PWFieldSetText",
      v15);
    goto LABEL_43;
  }
  if ( a1 )
  {
    v17 = EscapeBackslashes(a1, (unsigned __int16 **)&lpWideCharStr);
    v10 = v17;
    if ( v17 < 0 )
    {
      CEventLogger::LogError(
        v18,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0x1750u,
        L"PWFieldSetText",
        v17);
      v5 = (WCHAR *)lpWideCharStr;
      goto LABEL_43;
    }
    v19 = OpenThemeData(v3, L"TaskDialog");
    if ( v19 )
    {
      GetThemeFont(v19, 0, 2, 0, 210, &pFont);
      lfFaceName = pFont.lfFaceName;
    }
    else
    {
      lfFaceName = (WCHAR *)L"Segoe UI";
    }
    v21 = SysAllocString(lfFaceName);
    v5 = (WCHAR *)lpWideCharStr;
    v22 = -1;
    v6 = (char *)v21;
    v23 = -1;
    do
      ++v23;
    while ( lpWideCharStr[v23] );
    if ( v23 != 12 )
      goto LABEL_28;
    v24 = -1;
    do
      ++v24;
    while ( a1[v24] );
    if ( (_DWORD)v24 == 12 && IsAppThemed() )
    {
      v25 = 0;
      while ( 1 )
      {
        v26 = GetProcessHeap();
        v27 = HeapAlloc(v26, 0, 0x20u);
        v28 = (CEventLogger *)v25;
        lpMem[v25] = v27;
        if ( !v27 )
          break;
        v29 = WideCharToMultiByte(0xFDE9u, 0, &v5[4 * v25++], 4, (LPSTR)v27, 32, 0, 0);
        *((_BYTE *)v27 + v29) = 0;
        if ( v25 >= 3 )
        {
          v30 = StringCchPrintfA(
                  v9,
                  0x400u,
                  "{\\rtf\\ansi\\deff0{\\fonttbl{\\f0\\f%s;}}{\\colortbl;\\red0\\green0\\blue0;\\red200\\green220\\blue25"
                  "0;\\red255\\green255\\blue255;}\\f0\\fs24\\cf1{\\highlight2{%s}}\\cf1{\\highlight3{%s}}\\cf1{\\highlight2{%s}}}",
                  v6,
                  (const char *)lpMem[0],
                  (const char *)lpMem[1],
                  v52);
          v3 = hWnd;
          goto LABEL_35;
        }
      }
      v32 = 6004;
    }
    else
    {
LABEL_28:
      v33 = -1;
      do
        ++v33;
      while ( v5[v33] );
      v34 = GetProcessHeap();
      v35 = HeapAlloc(v34, 0, 4 * v33 + 4);
      v28 = 0;
      lpMem[0] = v35;
      v36 = (CHAR *)v35;
      if ( v35 )
      {
        v37 = -1;
        do
          ++v37;
        while ( v5[v37] );
        v36[WideCharToMultiByte(0xFDE9u, 0, v5, -1, v36, 4 * v37 + 4, 0, 0)] = 0;
        v30 = StringCchPrintfA(
                v9,
                0x400u,
                "{\\rtf\\ansi\\deff0{\\fonttbl{\\f0\\f%s;}}{\\colortbl;%s%s}\\f0\\fs24\\cf1{\\highlight2{%s}}}",
                v6,
                v48,
                v49,
                v36);
LABEL_35:
        v10 = v30;
        if ( v30 >= 0 )
        {
          wParam = 0xFDE900000000LL;
          SendMessageW(v3, 0x461u, (WPARAM)&wParam, (LPARAM)v9);
          do
            ++v22;
          while ( a1[v22] );
          if ( (unsigned int)v22 > 0x18 )
            LODWORD(v22) = 24;
          GetClientRect(v3, &Rect);
          SetFocus(v3);
          SendMessageW(v3, 0xB1u, (unsigned int)(v22 + 1), (unsigned int)(v22 + 1));
          GetCaretPos(&Point);
          SendMessageW(v3, 0xB1u, 0, 0);
          GetClientRect(v3, &Rect);
          SetWindowPos(v3, 0, 0, 0, Point.x + 4, Rect.bottom, 0x16u);
        }
        else
        {
          CEventLogger::LogError(
            v31,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
            0x17A7u,
            L"PWFieldSetText",
            v30);
        }
        goto LABEL_42;
      }
      v32 = 6030;
    }
    v10 = -2147024882;
    CEventLogger::LogError(
      v28,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      v32,
      L"PWFieldSetText",
      0x8007000E);
LABEL_42:
    v2 = 0;
    goto LABEL_43;
  }
  do
  {
LABEL_43:
    v38 = lpMem[v2];
    if ( v38 )
    {
      v39 = GetProcessHeap();
      HeapFree(v39, 0, v38);
      lpMem[v2] = 0;
    }
    ++v2;
  }
  while ( v2 != 3 );
  if ( v9 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v9);
  }
  if ( v5 )
    SysFreeString(v5);
  if ( v6 )
    SysFreeString((BSTR)v6);
  v41 = v48;
  if ( v48 )
  {
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v41);
  }
  v43 = v49;
  if ( v49 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v43);
  }
  return v10;
}

```

## disassembly

```asm
0x1400231d8  mov     [rsp-8+arg_10], rbx
0x1400231dd  push    rbp
0x1400231de  push    rsi
0x1400231df  push    rdi
0x1400231e0  push    r12
0x1400231e2  push    r13
0x1400231e4  push    r14
0x1400231e6  push    r15
0x1400231e8  lea     rbp, [rsp-0B0h]
0x1400231f0  sub     rsp, 1B0h
0x1400231f7  mov     rax, cs:__security_cookie
0x1400231fe  xor     rax, rsp
0x140023201  mov     [rbp+0E0h+var_40], rax
0x140023208  xor     edi, edi
0x14002320a  mov     [rbp+0E0h+hWnd], rdx
0x14002320e  mov     r14, rdx
0x140023211  mov     [rsp+1E0h+wParam], rdi
0x140023216  mov     r13, rcx
0x140023219  mov     [rsp+1E0h+lpWideCharStr], rdi
0x14002321e  xorps   xmm0, xmm0
0x140023221  lea     rcx, [rbp+0E0h+var_140]; void *
0x140023225  xor     eax, eax
0x140023227  lea     r8d, [rdi+5Ch]; Size
0x14002322b  xor     edx, edx; Val
0x14002322d  mov     [rsp+1E0h+var_168], rax
0x140023232  movups  xmmword ptr [rsp+1E0h+lpMem], xmm0
0x140023237  mov     esi, edi
0x140023239  call    memset_0
0x14002323e  xorps   xmm0, xmm0
0x140023241  mov     qword ptr [rsp+1E0h+Point.x], rdi
0x140023246  mov     ebx, 9Ch
0x14002324b  mov     [rsp+1E0h+var_190], rdi
0x140023250  mov     r8d, ebx; Size
0x140023253  mov     [rsp+1E0h+var_188], rdi
0x140023258  xor     edx, edx; Val
0x14002325a  lea     rcx, [rbp+0E0h+lParam]; void *
0x14002325e  movups  xmmword ptr [rbp+0E0h+Rect.left], xmm0
0x140023262  mov     r15d, edi
0x140023265  call    memset_0
0x14002326a  call    cs:__imp_GetProcessHeap
0x140023271  nop     dword ptr [rax+rax+00h]
0x140023276  xor     edx, edx; dwFlags
0x140023278  mov     r8d, 400h; dwBytes
0x14002327e  mov     rcx, rax; hHeap
0x140023281  call    cs:__imp_HeapAlloc
0x140023288  nop     dword ptr [rax+rax+00h]
0x14002328d  mov     r12, rax
0x140023290  test    rax, rax
0x140023293  jnz     short loc_1400232CC
0x140023295  mov     ebx, 8007000Eh
0x14002329a  mov     dword ptr [rsp+1E0h+pFont], 8007000Eh; unsigned int
0x1400232a2  mov     r9d, 1726h; unsigned int
0x1400232a8  lea     rax, aPwfieldsettext; "PWFieldSetText"
0x1400232af  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x1400232b6  mov     qword ptr [rsp+1E0h+iPropId], rax; unsigned __int16 *
0x1400232bb  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400232c2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400232c7  jmp     loc_140023714
0x1400232cc  lea     r9, [rbp+0E0h+lParam]; lParam
0x1400232d0  mov     dword ptr [rbp+0E0h+lParam], ebx
0x1400232d3  xor     r8d, r8d; wParam
0x1400232d6  mov     dword ptr [rbp+0E0h+lParam+4], 10000h
0x1400232dd  mov     edx, 447h; Msg
0x1400232e2  mov     [rbp+0E0h+var_D6], di
0x1400232e6  mov     rcx, r14; hWnd
0x1400232e9  call    cs:__imp_SendMessageW
0x1400232f0  nop     dword ptr [rax+rax+00h]
0x1400232f5  mov     ecx, 5; nIndex
0x1400232fa  call    cs:__imp_GetSysColor
0x140023301  nop     dword ptr [rax+rax+00h]
0x140023306  mov     ecx, eax; unsigned int
0x140023308  lea     rdx, [rsp+1E0h+var_188]; char **
0x14002330d  call    ?MakeColorRTFString@@YAJKPEAPEAD@Z; MakeColorRTFString(ulong,char * *)
0x140023312  mov     ebx, eax
0x140023314  test    eax, eax
0x140023316  jns     short loc_140023324
0x140023318  mov     dword ptr [rsp+1E0h+pFont], eax
0x14002331c  mov     r9d, 1743h
0x140023322  jmp     short loc_1400232A8
0x140023324  mov     ecx, 8; nIndex
0x140023329  call    cs:__imp_GetSysColor
0x140023330  nop     dword ptr [rax+rax+00h]
0x140023335  mov     ecx, eax; unsigned int
0x140023337  lea     rdx, [rsp+1E0h+var_190]; char **
0x14002333c  call    ?MakeColorRTFString@@YAJKPEAPEAD@Z; MakeColorRTFString(ulong,char * *)
0x140023341  mov     ebx, eax
0x140023343  test    eax, eax
0x140023345  jns     short loc_140023356
0x140023347  mov     dword ptr [rsp+1E0h+pFont], eax
0x14002334b  mov     r9d, 1746h
0x140023351  jmp     loc_1400232A8
0x140023356  test    r13, r13
0x140023359  jz      loc_140023714
0x14002335f  lea     rdx, [rsp+1E0h+lpWideCharStr]; unsigned __int16 **
0x140023364  mov     rcx, r13; unsigned __int16 *
0x140023367  call    ?EscapeBackslashes@@YAJPEAGPEAPEAG@Z; EscapeBackslashes(ushort *,ushort * *)
0x14002336c  mov     ebx, eax
0x14002336e  test    eax, eax
0x140023370  jns     short loc_1400233A5
0x140023372  mov     dword ptr [rsp+1E0h+pFont], eax; unsigned int
0x140023376  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14002337d  lea     rax, aPwfieldsettext; "PWFieldSetText"
0x140023384  mov     r9d, 1750h; unsigned int
0x14002338a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140023391  mov     qword ptr [rsp+1E0h+iPropId], rax; unsigned __int16 *
0x140023396  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002339b  mov     rsi, [rsp+1E0h+lpWideCharStr]
0x1400233a0  jmp     loc_140023714
0x1400233a5  lea     rdx, pszClassList; "TaskDialog"
0x1400233ac  mov     rcx, r14; hwnd
0x1400233af  call    cs:__imp_OpenThemeData
0x1400233b6  nop     dword ptr [rax+rax+00h]
0x1400233bb  test    rax, rax
0x1400233be  jz      short loc_1400233EF
0x1400233c0  xor     r9d, r9d; iStateId
0x1400233c3  lea     rcx, [rbp+0E0h+var_140]
0x1400233c7  mov     [rsp+1E0h+pFont], rcx; pFont
0x1400233cc  xor     edx, edx; hdc
0x1400233ce  mov     rcx, rax; hTheme
0x1400233d1  mov     [rsp+1E0h+iPropId], 0D2h; iPropId
0x1400233d9  lea     r8d, [r9+2]; iPartId
0x1400233dd  call    cs:__imp_GetThemeFont
0x1400233e4  nop     dword ptr [rax+rax+00h]
0x1400233e9  lea     rcx, [rbp+0E0h+var_140.lfFaceName]
0x1400233ed  jmp     short loc_1400233F6
0x1400233ef  lea     rcx, aSegoeUi; "Segoe UI"
0x1400233f6  call    cs:__imp_SysAllocString
0x1400233fd  nop     dword ptr [rax+rax+00h]
0x140023402  mov     rsi, [rsp+1E0h+lpWideCharStr]
0x140023407  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14002340b  mov     r15, rax
0x14002340e  xor     ecx, ecx
0x140023410  mov     rax, rdi
0x140023413  inc     rax
0x140023416  cmp     [rsi+rax*2], cx
0x14002341a  jnz     short loc_140023413
0x14002341c  cmp     rax, 0Ch
0x140023420  jnz     loc_140023551
0x140023426  mov     rax, rdi
0x140023429  inc     rax
0x14002342c  cmp     [r13+rax*2+0], cx
0x140023432  jnz     short loc_140023429
0x140023434  cmp     eax, 0Ch
0x140023437  jnz     loc_140023551
0x14002343d  call    cs:__imp_IsAppThemed
0x140023444  nop     dword ptr [rax+rax+00h]
0x140023449  xor     ecx, ecx
0x14002344b  cmp     eax, 1
0x14002344e  jnz     loc_140023551
0x140023454  mov     ebx, ecx
0x140023456  call    cs:__imp_GetProcessHeap
0x14002345d  nop     dword ptr [rax+rax+00h]
0x140023462  xor     edx, edx; dwFlags
0x140023464  mov     rcx, rax; hHeap
0x140023467  lea     r8d, [rdx+20h]; dwBytes
0x14002346b  call    cs:__imp_HeapAlloc
0x140023472  nop     dword ptr [rax+rax+00h]
0x140023477  mov     r14, rax
0x14002347a  movsxd  rcx, ebx; this
0x14002347d  mov     [rsp+rcx*8+1E0h+lpMem], rax
0x140023482  xor     eax, eax
0x140023484  test    r14, r14
0x140023487  jz      loc_14002351A
0x14002348d  mov     [rsp+1E0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x140023492  lea     ecx, ds:0[rbx*4]
0x140023499  movsxd  rdx, ecx
0x14002349c  lea     r9d, [rax+4]; cchWideChar
0x1400234a0  mov     [rsp+1E0h+lpDefaultChar], rax; lpDefaultChar
0x1400234a5  mov     ecx, 0FDE9h; CodePage
0x1400234aa  mov     dword ptr [rsp+1E0h+pFont], 20h ; ' '; cbMultiByte
0x1400234b2  mov     qword ptr [rsp+1E0h+iPropId], r14; lpMultiByteStr
0x1400234b7  lea     r8, [rsi+rdx*2]; lpWideCharStr
0x1400234bb  xor     edx, edx; dwFlags
0x1400234bd  call    cs:__imp_WideCharToMultiByte
0x1400234c4  nop     dword ptr [rax+rax+00h]
0x1400234c9  xor     ecx, ecx
0x1400234cb  mov     eax, eax
0x1400234cd  inc     ebx
0x1400234cf  mov     [rax+r14], cl
0x1400234d3  cmp     ebx, 3
0x1400234d6  jl      loc_140023456
0x1400234dc  mov     rax, [rsp+1E0h+var_168]
0x1400234e1  lea     r8, aRtfAnsiDeff0Fo; "{\\rtf\\ansi\\deff0{\\fonttbl{\\f0\\f%s"...
0x1400234e8  mov     [rsp+1E0h+lpDefaultChar], rax
0x1400234ed  mov     r9, r15
0x1400234f0  mov     rax, [rsp+1E0h+lpMem+8]
0x1400234f5  mov     edx, 400h; unsigned __int64
0x1400234fa  mov     [rsp+1E0h+pFont], rax
0x1400234ff  mov     rcx, r12; char *
0x140023502  mov     rax, [rsp+1E0h+lpMem]
0x140023507  mov     qword ptr [rsp+1E0h+iPropId], rax
0x14002350c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140023511  mov     r14, [rbp+0E0h+hWnd]
0x140023515  jmp     loc_14002360F
0x14002351a  mov     r9d, 1774h; unsigned int
0x140023520  mov     dword ptr [rsp+1E0h+pFont], 8007000Eh; unsigned int
0x140023528  mov     ebx, 8007000Eh
0x14002352d  lea     rax, aPwfieldsettext; "PWFieldSetText"
0x140023534  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14002353b  mov     qword ptr [rsp+1E0h+iPropId], rax; unsigned __int16 *
0x140023540  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140023547  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002354c  jmp     loc_140023712
0x140023551  mov     rbx, rdi
0x140023554  inc     rbx
0x140023557  cmp     [rsi+rbx*2], cx
0x14002355b  jnz     short loc_140023554
0x14002355d  call    cs:__imp_GetProcessHeap
0x140023564  nop     dword ptr [rax+rax+00h]
0x140023569  lea     r8, ds:4[rbx*4]; dwBytes
0x140023571  xor     edx, edx; dwFlags
0x140023573  mov     rcx, rax; hHeap
0x140023576  call    cs:__imp_HeapAlloc
0x14002357d  nop     dword ptr [rax+rax+00h]
0x140023582  xor     ecx, ecx
0x140023584  mov     [rsp+1E0h+lpMem], rax
0x140023589  mov     rbx, rax
0x14002358c  test    rax, rax
0x14002358f  jnz     short loc_140023599
0x140023591  mov     r9d, 178Eh
0x140023597  jmp     short loc_140023520
0x140023599  mov     rax, rdi
0x14002359c  inc     rax
0x14002359f  cmp     [rsi+rax*2], cx
0x1400235a3  jnz     short loc_14002359C
0x1400235a5  mov     [rsp+1E0h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x1400235aa  lea     eax, ds:4[rax*4]
0x1400235b1  mov     [rsp+1E0h+lpDefaultChar], rcx; lpDefaultChar
0x1400235b6  mov     r9d, edi; cchWideChar
0x1400235b9  mov     dword ptr [rsp+1E0h+pFont], eax; cbMultiByte
0x1400235bd  mov     ecx, 0FDE9h; CodePage
0x1400235c2  mov     r8, rsi; lpWideCharStr
0x1400235c5  mov     qword ptr [rsp+1E0h+iPropId], rbx; lpMultiByteStr
0x1400235ca  xor     edx, edx; dwFlags
0x1400235cc  call    cs:__imp_WideCharToMultiByte
0x1400235d3  nop     dword ptr [rax+rax+00h]
0x1400235d8  xor     ecx, ecx
0x1400235da  mov     [rsp+1E0h+lpDefaultChar], rbx
0x1400235df  mov     eax, eax
0x1400235e1  lea     r8, aRtfAnsiDeff0Fo_0; "{\\rtf\\ansi\\deff0{\\fonttbl{\\f0\\f%s"...
0x1400235e8  mov     r9, r15
0x1400235eb  mov     edx, 400h; unsigned __int64
0x1400235f0  mov     [rax+rbx], cl
0x1400235f3  mov     rcx, r12; char *
0x1400235f6  mov     rax, [rsp+1E0h+var_188]
0x1400235fb  mov     [rsp+1E0h+pFont], rax
0x140023600  mov     rax, [rsp+1E0h+var_190]
0x140023605  mov     qword ptr [rsp+1E0h+iPropId], rax
0x14002360a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14002360f  mov     ebx, eax
0x140023611  xor     eax, eax
0x140023613  test    ebx, ebx
0x140023615  jns     short loc_140023626
0x140023617  mov     dword ptr [rsp+1E0h+pFont], ebx
0x14002361b  mov     r9d, 17A7h
0x140023621  jmp     loc_14002352D
0x140023626  mov     r9, r12; lParam
0x140023629  mov     dword ptr [rsp+1E0h+wParam], eax
0x14002362d  lea     r8, [rsp+1E0h+wParam]; wParam
0x140023632  mov     dword ptr [rsp+1E0h+wParam+4], 0FDE9h
0x14002363a  mov     edx, 461h; Msg
0x14002363f  mov     rcx, r14; hWnd
0x140023642  call    cs:__imp_SendMessageW
0x140023649  nop     dword ptr [rax+rax+00h]
0x14002364e  xor     ecx, ecx
0x140023650  inc     rdi
0x140023653  cmp     [r13+rdi*2+0], cx
0x140023659  jnz     short loc_140023650
0x14002365b  mov     eax, 18h
0x140023660  lea     rdx, [rbp+0E0h+Rect]; lpRect
0x140023664  cmp     edi, eax
0x140023666  mov     rcx, r14; hWnd
0x140023669  cmova   edi, eax
0x14002366c  call    cs:__imp_GetClientRect
0x140023673  nop     dword ptr [rax+rax+00h]
0x140023678  mov     rcx, r14; hWnd
0x14002367b  call    cs:__imp_SetFocus
0x140023682  nop     dword ptr [rax+rax+00h]
0x140023687  lea     eax, [rdi+1]
0x14002368a  mov     rcx, r14; hWnd
0x14002368d  mov     edi, 0B1h
0x140023692  mov     r8d, eax; wParam
0x140023695  mov     edx, edi; Msg
0x140023697  mov     r9d, eax; lParam
0x14002369a  call    cs:__imp_SendMessageW
0x1400236a1  nop     dword ptr [rax+rax+00h]
0x1400236a6  lea     rcx, [rsp+1E0h+Point]; lpPoint
0x1400236ab  call    cs:__imp_GetCaretPos
0x1400236b2  nop     dword ptr [rax+rax+00h]
0x1400236b7  xor     r9d, r9d; lParam
0x1400236ba  xor     r8d, r8d; wParam
0x1400236bd  mov     edx, edi; Msg
0x1400236bf  mov     rcx, r14; hWnd
0x1400236c2  call    cs:__imp_SendMessageW
0x1400236c9  nop     dword ptr [rax+rax+00h]
0x1400236ce  lea     rdx, [rbp+0E0h+Rect]; lpRect
0x1400236d2  mov     rcx, r14; hWnd
0x1400236d5  call    cs:__imp_GetClientRect
0x1400236dc  nop     dword ptr [rax+rax+00h]
0x1400236e1  mov     edx, [rsp+1E0h+Point.x]
  ... truncated ...
```
