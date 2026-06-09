# CRichEdDoc::AttachWin(HWND__ *,tagRECT *)

- ea: `0x180064430`
- end: `0x180064845`
- name: `?AttachWin@CRichEdDoc@@EEAAJPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `1045`
- prototype: `int(CRichEdDoc *__hidden this, HWND, struct tagRECT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002098`
- `0x1800247c8`
- `0x1800299d0`
- `0x180064430`
- `0x180066a88`
- `0x1800672a4`
- `0x18006c9b0`
- `0x1800cb45c`
- `0x1800cc9ba`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!FInitializeRichEdit` at `0x18006446c`
- `MSOERT2!FInitializeRichEdit` at `0x18006446c`
- `MSOERT2!SetFontOnRichEd` at `0x1800646eb`
- `MSOERT2!SetFontOnRichEd` at `0x1800646eb`
- `MSOERT2!GetRichEdClassStringW` at `0x18006447a`
- `MSOERT2!GetRichEdClassStringW` at `0x18006447a`
- `GDI32!DeleteObject` at `0x1800646f4`
- `GDI32!DeleteObject` at `0x1800646f4`
- `KERNEL32!GetLastError` at `0x18006451e`
- `KERNEL32!GetLastError` at `0x18006451e`
- `USER32!SendMessageA` at `0x18006471e`
- `USER32!SendMessageA` at `0x180064739`
- `USER32!SendMessageA` at `0x180064751`
- `USER32!SendMessageA` at `0x18006476b`
- `USER32!SendMessageA` at `0x18006471e`
- `USER32!SendMessageA` at `0x180064739`
- `USER32!SendMessageA` at `0x180064751`
- `USER32!SendMessageA` at `0x18006476b`
- `USER32!GetClassInfoExA` at `0x1800644b1`
- `USER32!GetClassInfoExA` at `0x1800644b1`
- `USER32!LoadCursorA` at `0x1800644e4`
- `USER32!LoadCursorA` at `0x1800644e4`
- `USER32!GetSysColorBrush` at `0x1800644f2`
- `USER32!GetSysColorBrush` at `0x1800644f2`
- `USER32!RegisterClassExA` at `0x180064513`
- `USER32!RegisterClassExA` at `0x180064513`
- `USER32!GetWindowLongA` at `0x1800645b5`
- `USER32!GetWindowLongA` at `0x1800645b5`
- `USER32!CreateWindowExW` at `0x180064619`
- `USER32!CreateWindowExW` at `0x180064619`
- `OLEAUT32!__imp_VariantInit` at `0x18006465e`
- `OLEAUT32!__imp_VariantInit` at `0x180064668`
- `OLEAUT32!__imp_VariantInit` at `0x18006465e`
- `OLEAUT32!__imp_VariantInit` at `0x180064668`

## pseudocode

```c
__int64 __fastcall CRichEdDoc::AttachWin(unsigned __int64 this, HWND a2, struct tagRECT *a3)
{
  const unsigned __int16 *RichEdClassStringW; // rax
  const WCHAR *v7; // r12
  unsigned int v8; // ebx
  HBRUSH SysColorBrush; // rax
  __int64 Window; // rax
  int LastError; // ebx
  LONG WindowLongA; // eax
  HWND v13; // rax
  char *v14; // r14
  int (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rcx
  BSTR bstrVal; // rbx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, struct IOleCommandTarget **); // rcx
  HWND v18; // rdx
  unsigned int v19; // r8d
  CSimpleHeader *v20; // rax
  CSimpleHeader *v21; // rax
  _QWORD *v22; // r14
  struct IOleCommandTarget *v24; // [rsp+60h] [rbp-79h] BYREF
  VARIANTARG v25; // [rsp+68h] [rbp-71h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-59h] BYREF
  tagWNDCLASSEXA wcx; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v28; // [rsp+158h] [rbp+7Fh] BYREF

  memset_0(&wcx, 0, sizeof(wcx));
  v28 = 0;
  if ( !FInitializeRichEdit(1) )
    return 2147500037LL;
  RichEdClassStringW = GetRichEdClassStringW();
  wcx.cbSize = 80;
  v7 = RichEdClassStringW;
  v8 = *(_DWORD *)(this - 32 + 728) != 0 ? 0xFFFFF800 : 0;
  if ( !GetClassInfoExA(g_hInst, "RichEdDoc Class", &wcx) )
  {
    wcx.style = 0;
    wcx.lpfnWndProc = (WNDPROC)CRichEdDoc::s_WndProc;
    wcx.hInstance = g_hInst;
    *(_QWORD *)&wcx.cbClsExtra = 0;
    wcx.hIcon = 0;
    wcx.hCursor = LoadCursorA(0, (LPCSTR)0x7F00);
    SysColorBrush = GetSysColorBrush(15);
    wcx.lpszMenuName = 0;
    wcx.hbrBackground = SysColorBrush;
    wcx.lpszClassName = "RichEdDoc Class";
    wcx.hIconSm = 0;
    if ( !RegisterClassExA(&wcx) && GetLastError() != 1410 )
      return 2147500037LL;
  }
  Window = SHFusionCreateWindowEx(
             0x200u,
             "RichEdDoc Class",
             a3->left,
             a3->top,
             a3->right - a3->left,
             a3->bottom - a3->top,
             a2,
             0,
             g_hInst,
             (LPVOID)(this - 32));
  *(_QWORD *)(this + 128) = Window;
  if ( Window )
  {
    WindowLongA = GetWindowLongA(a2, -20);
    v13 = CreateWindowExW(
            (WindowLongA & 0x400000) != 0 ? 0x5000 : 0,
            v7,
            0,
            v8 + 1344342020,
            0,
            0,
            a3->right - a3->left,
            a3->bottom - a3->top,
            *(HWND *)(this + 128),
            0,
            g_hInst,
            0);
    *(_QWORD *)(this + 704) = v13;
    v14 = (char *)(this + 656);
    if ( v13 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      memset(&v25, 0, sizeof(v25));
      VariantInit(&pvarg);
      VariantInit(&v25);
      v15 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v14;
      v25.vt = 0x4000;
      v25.llVal = *(_QWORD *)(this + 704);
      if ( (**v15)(v15, &IID_IOleCommandTarget, &v28) >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v28 + 32LL))(v28, &CMDSETID_MimeEditHost, 28);
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v28);
      }
      bstrVal = pvarg.bstrVal;
      if ( pvarg.llVal )
      {
        SetFontOnRichEd(*(HWND *)(this + 704), (HFONT)pvarg.llVal);
        DeleteObject(bstrVal);
      }
      CRichEdDoc::_SetEditMode((CRichEdDoc *)(this - 32), *(_DWORD *)(this + 696));
      SendMessageA(*(HWND *)(this + 704), 0x459u, 1u, 0);
      SendMessageA(*(HWND *)(this + 704), 0x445u, 0, 67633153);
      SendMessageA(*(HWND *)(this + 704), 0x45Bu, 1u, 0);
      SendMessageA(*(HWND *)(this + 704), 0xD3u, 1u, 10);
    }
    else
    {
      HrGetLastError();
    }
    v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IOleCommandTarget **))v14;
    v24 = 0;
    LastError = (**v17)(v17, &IID_IOleCommandTarget, &v24);
    if ( LastError < 0 )
    {
      v22 = (_QWORD *)(this + 728);
    }
    else
    {
      v20 = (CSimpleHeader *)operator new(0xA8u);
      if ( v20 )
        v21 = CSimpleHeader::CSimpleHeader(v20, v24);
      else
        v21 = 0;
      v22 = (_QWORD *)(this + 728);
      *(_QWORD *)(this + 728) = v21;
    }
    if ( *v22 )
    {
      LastError = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*v22 + 8LL) + 24LL))(
                    *v22 + 8LL,
                    this & ((unsigned __int128)-(__int128)(this - 32) >> 64));
      if ( LastError >= 0 )
        LastError = (*(__int64 (__fastcall **)(_QWORD, bool))(*(_QWORD *)*v22 + 40LL))(
                      *v22,
                      *(_DWORD *)(this + 716) == 1);
    }
    CRichEdDoc::_OnSize((CRichEdDoc *)(this - 32), v18, v19, a3->right - a3->left, a3->bottom - a3->top);
  }
  else
  {
    LastError = HrGetLastError();
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180064430  push    rbp
0x180064432  push    rbx
0x180064433  push    rsi
0x180064434  push    rdi
0x180064435  push    r12
0x180064437  push    r13
0x180064439  push    r14
0x18006443b  push    r15
0x18006443d  lea     rbp, [rsp-1Fh]
0x180064442  sub     rsp, 0F8h
0x180064449  mov     r14, rdx
0x18006444c  mov     rsi, r8
0x18006444f  xor     edx, edx; Val
0x180064451  mov     rdi, rcx
0x180064454  lea     rcx, [rbp+57h+wcx]; void *
0x180064458  lea     r8d, [rdx+50h]; Size
0x18006445c  call    memset_0
0x180064461  xor     r13d, r13d
0x180064464  mov     [rbp+57h+arg_18], r13
0x180064468  lea     ecx, [r13+1]
0x18006446c  call    cs:__imp_?FInitializeRichEdit@@YAHH@Z; FInitializeRichEdit(int)
0x180064472  test    eax, eax
0x180064474  jz      loc_18006482C
0x18006447a  call    cs:__imp_?GetRichEdClassStringW@@YAPEBGXZ; GetRichEdClassStringW(void)
0x180064480  lea     r15, [rdi-20h]
0x180064484  mov     [rbp+57h+wcx.cbSize], 50h ; 'P'
0x18006448b  mov     ecx, [r15+2D8h]
0x180064492  lea     r8, [rbp+57h+wcx]; lpwcx
0x180064496  neg     ecx
0x180064498  lea     rdx, c_szRichEdDocWndClass; "RichEdDoc Class"
0x18006449f  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800644a6  mov     r12, rax
0x1800644a9  sbb     ebx, ebx
0x1800644ab  and     ebx, 0FFFFF800h
0x1800644b1  call    cs:__imp_GetClassInfoExA
0x1800644b7  test    eax, eax
0x1800644b9  jnz     short loc_18006452F
0x1800644bb  lea     rax, ?s_WndProc@CRichEdDoc@@CA_JPEAUHWND__@@I_K_J@Z; CRichEdDoc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800644c2  mov     [rbp+57h+wcx.style], r13d
0x1800644c6  mov     [rbp+57h+wcx.lpfnWndProc], rax
0x1800644ca  mov     edx, 7F00h; lpCursorName
0x1800644cf  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800644d6  xor     ecx, ecx; hInstance
0x1800644d8  mov     [rbp+57h+wcx.hInstance], rax
0x1800644dc  mov     qword ptr [rbp+57h+wcx.cbClsExtra], r13
0x1800644e0  mov     [rbp+57h+wcx.hIcon], r13
0x1800644e4  call    cs:__imp_LoadCursorA
0x1800644ea  lea     ecx, [r13+0Fh]; nIndex
0x1800644ee  mov     [rbp+57h+wcx.hCursor], rax
0x1800644f2  call    cs:__imp_GetSysColorBrush
0x1800644f8  lea     rcx, [rbp+57h+wcx]; WNDCLASSEXA *
0x1800644fc  mov     [rbp+57h+wcx.lpszMenuName], r13
0x180064500  mov     [rbp+57h+wcx.hbrBackground], rax
0x180064504  lea     rax, c_szRichEdDocWndClass; "RichEdDoc Class"
0x18006450b  mov     [rbp+57h+wcx.lpszClassName], rax
0x18006450f  mov     [rbp+57h+wcx.hIconSm], r13
0x180064513  call    cs:__imp_RegisterClassExA
0x180064519  test    ax, ax
0x18006451c  jnz     short loc_18006452F
0x18006451e  call    cs:__imp_GetLastError
0x180064524  cmp     eax, 582h
0x180064529  jnz     loc_18006482C
0x18006452f  mov     r9d, [rsi+4]
0x180064533  lea     rdx, c_szRichEdDocWndClass; "RichEdDoc Class"
0x18006453a  mov     r10d, [rsi]
0x18006453d  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180064544  mov     r8d, [rsi+0Ch]
0x180064548  mov     ecx, [rsi+8]
0x18006454b  sub     r8d, r9d
0x18006454e  mov     [rsp+130h+lpParam], r15; LPVOID
0x180064553  sub     ecx, r10d
0x180064556  mov     [rsp+130h+hInstance], rax; HINSTANCE
0x18006455b  mov     [rsp+130h+hMenu], r13; HMENU
0x180064560  mov     [rsp+130h+hWndParent], r14; HWND
0x180064565  mov     [rsp+130h+nHeight], r8d; int
0x18006456a  mov     [rsp+130h+nWidth], ecx; int
0x18006456e  mov     ecx, 200h; dwExStyle
0x180064573  mov     [rsp+130h+Y], r9d; int
0x180064578  mov     r9d, 56000000h
0x18006457e  mov     [rsp+130h+X], r10d; int
0x180064583  call    SHFusionCreateWindowEx
0x180064588  mov     [rdi+80h], rax
0x18006458f  test    rax, rax
0x180064592  jnz     short loc_1800645AD
0x180064594  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180064599  mov     ebx, eax
0x18006459b  test    eax, eax
0x18006459d  js      loc_180064828
0x1800645a3  mov     ebx, 80004005h
0x1800645a8  jmp     loc_180064828
0x1800645ad  mov     edx, 0FFFFFFECh; nIndex
0x1800645b2  mov     rcx, r14; hWnd
0x1800645b5  call    cs:__imp_GetWindowLongA
0x1800645bb  mov     r8d, [rsi+0Ch]
0x1800645bf  lea     r9d, [rbx+50210804h]; dwStyle
0x1800645c6  mov     edx, [rsi+8]
0x1800645c9  and     eax, 400000h
0x1800645ce  mov     [rsp+130h+lpParam], r13; lpParam
0x1800645d3  neg     eax
0x1800645d5  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800645dc  mov     [rsp+130h+hInstance], rax; hInstance
0x1800645e1  sbb     ecx, ecx
0x1800645e3  sub     r8d, [rsi+4]
0x1800645e7  and     ecx, 5000h; dwExStyle
0x1800645ed  sub     edx, [rsi]
0x1800645ef  mov     rax, [rdi+80h]
0x1800645f6  mov     [rsp+130h+hMenu], r13; hMenu
0x1800645fb  mov     [rsp+130h+hWndParent], rax; hWndParent
0x180064600  mov     [rsp+130h+nHeight], r8d; nHeight
0x180064605  xor     r8d, r8d; lpWindowName
0x180064608  mov     [rsp+130h+nWidth], edx; nWidth
0x18006460c  mov     rdx, r12; lpClassName
0x18006460f  mov     [rsp+130h+Y], r13d; Y
0x180064614  mov     [rsp+130h+X], r13d; X
0x180064619  call    cs:__imp_CreateWindowExW
0x18006461f  mov     [rdi+2C0h], rax
0x180064626  lea     r14, [rdi+290h]
0x18006462d  test    rax, rax
0x180064630  jnz     short loc_180064642
0x180064632  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180064637  mov     r12d, 1
0x18006463d  jmp     loc_180064771
0x180064642  xor     eax, eax
0x180064644  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180064648  xorps   xmm0, xmm0
0x18006464b  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18006464f  xorps   xmm1, xmm1
0x180064652  mov     qword ptr [rbp+57h+var_C8+10h], rax
0x180064656  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18006465a  movups  xmmword ptr [rbp+57h+var_C8], xmm1
0x18006465e  call    cs:__imp_VariantInit
0x180064664  lea     rcx, [rbp+57h+var_C8]; pvarg
0x180064668  call    cs:__imp_VariantInit
0x18006466e  mov     rcx, [r14]
0x180064671  lea     r8, [rbp+57h+arg_18]
0x180064675  mov     eax, 4000h
0x18006467a  lea     rdx, IID_IOleCommandTarget
0x180064681  mov     word ptr [rbp+57h+var_C8], ax
0x180064685  mov     rax, [rdi+2C0h]
0x18006468c  mov     qword ptr [rbp+57h+var_C8+8], rax
0x180064690  mov     rax, [rcx]
0x180064693  mov     rax, [rax]
0x180064696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006469b  test    eax, eax
0x18006469d  js      short loc_1800646D8
0x18006469f  mov     rcx, [rbp+57h+arg_18]
0x1800646a3  lea     rdx, [rbp+57h+pvarg]
0x1800646a7  mov     qword ptr [rsp+130h+Y], rdx
0x1800646ac  xor     r9d, r9d
0x1800646af  lea     rdx, [rbp+57h+var_C8]
0x1800646b3  mov     qword ptr [rsp+130h+X], rdx
0x1800646b8  lea     rdx, CMDSETID_MimeEditHost
0x1800646bf  mov     rax, [rcx]
0x1800646c2  lea     r8d, [r9+1Ch]
0x1800646c6  mov     rax, [rax+20h]
0x1800646ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646cf  lea     rcx, [rbp+57h+arg_18]
0x1800646d3  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800646d8  mov     rbx, qword ptr [rbp+57h+pvarg+8]
0x1800646dc  test    rbx, rbx
0x1800646df  jz      short loc_1800646FA
0x1800646e1  mov     rcx, [rdi+2C0h]
0x1800646e8  mov     rdx, rbx
0x1800646eb  call    cs:__imp_?SetFontOnRichEd@@YAXPEAUHWND__@@PEAUHFONT__@@@Z; SetFontOnRichEd(HWND__ *,HFONT__ *)
0x1800646f1  mov     rcx, rbx; ho
0x1800646f4  call    cs:__imp_DeleteObject
0x1800646fa  mov     edx, [rdi+2B8h]; int
0x180064700  mov     rcx, r15; this
0x180064703  call    ?_SetEditMode@CRichEdDoc@@AEAAJH@Z; CRichEdDoc::_SetEditMode(int)
0x180064708  mov     rcx, [rdi+2C0h]; hWnd
0x18006470f  xor     r9d, r9d; lParam
0x180064712  mov     edx, 459h; Msg
0x180064717  lea     r12d, [r9+1]
0x18006471b  mov     r8d, r12d; wParam
0x18006471e  call    cs:__imp_SendMessageA
0x180064724  mov     rcx, [rdi+2C0h]; hWnd
0x18006472b  mov     r9d, 4080001h; lParam
0x180064731  xor     r8d, r8d; wParam
0x180064734  mov     edx, 445h; Msg
0x180064739  call    cs:__imp_SendMessageA
0x18006473f  mov     rcx, [rdi+2C0h]; hWnd
0x180064746  xor     r9d, r9d; lParam
0x180064749  mov     r8d, r12d; wParam
0x18006474c  mov     edx, 45Bh; Msg
0x180064751  call    cs:__imp_SendMessageA
0x180064757  mov     rcx, [rdi+2C0h]; hWnd
0x18006475e  lea     r9d, [r12+9]; lParam
0x180064763  mov     r8d, r12d; wParam
0x180064766  mov     edx, 0D3h; Msg
0x18006476b  call    cs:__imp_SendMessageA
0x180064771  mov     rcx, [r14]
0x180064774  lea     r8, [rbp+57h+var_D0]
0x180064778  mov     [rbp+57h+var_D0], r13
0x18006477c  lea     rdx, IID_IOleCommandTarget
0x180064783  mov     rax, [rcx]
0x180064786  mov     rax, [rax]
0x180064789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006478e  mov     ebx, eax
0x180064790  test    eax, eax
0x180064792  js      short loc_1800647C0
0x180064794  mov     ecx, 0A8h; Size
0x180064799  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006479e  test    rax, rax
0x1800647a1  jz      short loc_1800647B1
0x1800647a3  mov     rdx, [rbp+57h+var_D0]; struct IOleCommandTarget *
0x1800647a7  mov     rcx, rax; this
0x1800647aa  call    ??0CSimpleHeader@@QEAA@PEAUIOleCommandTarget@@@Z; CSimpleHeader::CSimpleHeader(IOleCommandTarget *)
0x1800647af  jmp     short loc_1800647B4
0x1800647b1  mov     rax, r13
0x1800647b4  lea     r14, [rdi+2D8h]
0x1800647bb  mov     [r14], rax
0x1800647be  jmp     short loc_1800647C7
0x1800647c0  lea     r14, [rdi+2D8h]
0x1800647c7  mov     rcx, [r14]
0x1800647ca  test    rcx, rcx
0x1800647cd  jz      short loc_18006480F
0x1800647cf  add     rcx, 8
0x1800647d3  mov     rax, r15
0x1800647d6  neg     rax
0x1800647d9  sbb     rdx, rdx
0x1800647dc  mov     r8, [rcx]
0x1800647df  and     rdx, rdi
0x1800647e2  mov     rax, [r8+18h]
0x1800647e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800647eb  mov     ebx, eax
0x1800647ed  test    eax, eax
0x1800647ef  js      short loc_18006480F
0x1800647f1  mov     rcx, [r14]
0x1800647f4  mov     edx, r13d
0x1800647f7  cmp     [rdi+2CCh], r12d
0x1800647fe  setz    dl
0x180064801  mov     rax, [rcx]
0x180064804  mov     rax, [rax+28h]
0x180064808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006480d  mov     ebx, eax
0x18006480f  mov     eax, [rsi+0Ch]
0x180064812  mov     rcx, r15; this
0x180064815  mov     r9d, [rsi+8]
0x180064819  sub     eax, [rsi+4]
0x18006481c  sub     r9d, [rsi]; int
0x18006481f  mov     [rsp+130h+X], eax; int
0x180064823  call    ?_OnSize@CRichEdDoc@@AEAAXPEAUHWND__@@IHH@Z; CRichEdDoc::_OnSize(HWND__ *,uint,int,int)
0x180064828  mov     eax, ebx
0x18006482a  jmp     short loc_180064831
0x18006482c  mov     eax, 80004005h
0x180064831  add     rsp, 0F8h
0x180064838  pop     r15
0x18006483a  pop     r14
0x18006483c  pop     r13
0x18006483e  pop     r12
0x180064840  pop     rdi
0x180064841  pop     rsi
0x180064842  pop     rbx
0x180064843  pop     rbp
0x180064844  retn
```
