# CDRMCTridentDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x18002f3cc`
- end: `0x18002f75b`
- name: `?OnInitDialog@CDRMCTridentDlg@@QEAA_JI_K_JAEAH@Z`
- size: `911`
- prototype: `__int64 __fastcall(CDRMCTridentDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f910`

## callees

- `0x18002f3cc`
- `0x18002fe50`
- `0x180030a38`
- `0x180030b5c`
- `0x18005bd72`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f6ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f6f8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f6ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f6f8`
- `OLEAUT32!__imp_VariantInit` at `0x18002f4d6`
- `OLEAUT32!__imp_VariantInit` at `0x18002f6cc`
- `OLEAUT32!__imp_VariantInit` at `0x18002f6d6`
- `OLEAUT32!__imp_VariantInit` at `0x18002f4d6`
- `OLEAUT32!__imp_VariantInit` at `0x18002f6cc`
- `OLEAUT32!__imp_VariantInit` at `0x18002f6d6`
- `USER32!LoadCursorW` at `0x18002f5d8`
- `USER32!LoadCursorW` at `0x18002f5d8`
- `USER32!GetClientRect` at `0x18002f5a3`
- `USER32!GetClientRect` at `0x18002f5a3`
- `USER32!MoveWindow` at `0x18002f48e`
- `USER32!MoveWindow` at `0x18002f48e`
- `USER32!GetWindowRect` at `0x18002f440`
- `USER32!GetWindowRect` at `0x18002f440`
- `USER32!GetSystemMetrics` at `0x18002f460`
- `USER32!GetSystemMetrics` at `0x18002f460`

## pseudocode

```c
__int64 __fastcall CDRMCTridentDlg::OnInitDialog(HWND *this)
{
  __int64 result; // rax
  int v3; // edi
  int v4; // esi
  int SystemMetrics; // eax
  HWND v6; // rcx
  HWND v7; // rcx
  CWebBrowser *v8; // rdi
  HWND v9; // rsi
  unsigned __int16 v10; // ax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  HWND Window; // rax
  __int64 v15; // rcx
  const OLECHAR *v16; // rdi
  HWND v17; // rbx
  BSTR v18; // rax
  __int64 v19; // rcx
  int nHeight; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+48h] [rbp-B8h]
  unsigned int v22; // [rsp+60h] [rbp-A0h] BYREF
  __int128 p_pvarg; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  const WCHAR *v25; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v27; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-38h]
  WNDCLASSW WndClass; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v31; // [rsp+120h] [rbp+20h] BYREF
  tagRECT Rect; // [rsp+138h] [rbp+38h] BYREF

  v22 = 0;
  v25 = L"Init";
  memset(&pvarg, 0, sizeof(pvarg));
  v24 = 0;
  p_pvarg = 0;
  Rect = 0;
  if ( this[8] )
  {
    if ( GetWindowRect(this[1], &Rect) )
    {
      v3 = Rect.right - Rect.left;
      v4 = Rect.bottom - Rect.top;
      SystemMetrics = GetSystemMetrics(17);
      if ( SystemMetrics > 0 && SystemMetrics < v4 )
        MoveWindow(this[1], Rect.left, 0, SystemMetrics * v3 / v4, SystemMetrics, 1);
    }
    v6 = this[9];
    if ( v6
      && (*(int (__fastcall **)(HWND, GUID *, const WCHAR **, __int64, int, unsigned int *))(*(_QWORD *)v6 + 40LL))(
           v6,
           &GUID_NULL,
           &v25,
           1,
           2048,
           &v22) >= 0 )
    {
      VariantInit(&pvarg);
      v7 = this[9];
      pvarg.vt = 19;
      pvarg.lVal = *((_DWORD *)this + 2);
      p_pvarg = (unsigned __int64)&pvarg;
      v24 = 1;
      LOWORD(nHeight) = 1;
      (*(void (__fastcall **)(HWND, _QWORD, GUID *, __int64, int, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v7 + 48LL))(
        v7,
        v22,
        &GUID_NULL,
        2048,
        nHeight,
        &p_pvarg,
        0,
        0,
        0);
    }
    v8 = (CWebBrowser *)this[8];
    v9 = this[1];
    *(_OWORD *)&v31.vt = 0;
    memset_0(&WndClass, 0, sizeof(WndClass));
    if ( *((_QWORD *)v8 + 7) )
      CWebBrowser::CloseOleObject(v8);
    if ( *((_QWORD *)v8 + 9) )
    {
      memset_0(&WndClass, 0, sizeof(WndClass));
      GetClientRect(v9, (LPRECT)&v31);
      WndClass.style = 3;
      WndClass.lpszClassName = L"MSDRM Trident Window";
      WndClass.lpfnWndProc = (WNDPROC)MsdrmTridentWndProc;
      WndClass.hInstance = g_hInst;
      WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
      v10 = IsolationAwareRegisterClassW(&WndClass);
      if ( v10
        && (Window = IsolationAwareCreateWindowExW(
                       v10,
                       v11,
                       v12,
                       v13,
                       *(int *)&v31.vt,
                       v31.decVal.Hi32,
                       v31.lVal,
                       v31.cyVal.Hi,
                       v9,
                       v21,
                       WndClass.hInstance),
            (*((_QWORD *)v8 + 7) = Window) != 0) )
      {
        v15 = *((_QWORD *)v8 + 9);
        *((_QWORD *)v8 + 8) = v9;
        LODWORD(result) = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int64, int, HWND, VARIANTARG *))(*(_QWORD *)v15 + 88LL))(
                            v15,
                            4294967291LL,
                            0,
                            ((unsigned __int64)v8 + 8) & -(__int64)(v8 != 0),
                            -1,
                            Window,
                            &v31);
        if ( (int)result >= 0 )
        {
          v16 = (const OLECHAR *)this[7];
          if ( v16 )
          {
            v17 = this[8];
            memset(&v27, 0, sizeof(v27));
            memset(&v31, 0, sizeof(v31));
            v29 = 0;
            v28 = 0;
            VariantInit(&v27);
            VariantInit(&v31);
            v27.vt = 8;
            v31.vt = 8;
            v27.llVal = (LONGLONG)SysAllocString(v16);
            v18 = SysAllocString(0);
            v19 = *((_QWORD *)v17 + 10);
            v31.llVal = (LONGLONG)v18;
            (*(void (__fastcall **)(__int64, VARIANTARG *, __int128 *, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v19 + 416LL))(
              v19,
              &v27,
              &v28,
              &v31,
              &v28,
              &v28);
            LODWORD(result) = 0;
          }
        }
      }
      else
      {
        LODWORD(result) = GetLastError();
        if ( (int)result > 0 )
          LODWORD(result) = (unsigned __int16)result | 0x80070000;
        if ( (int)result >= 0 )
          LODWORD(result) = -2147467259;
      }
    }
    else
    {
      LODWORD(result) = -2147467261;
    }
  }
  else
  {
    LODWORD(result) = -2147024882;
  }
  return (int)result;
}

```

## disassembly

```asm
0x18002f3cc  mov     [rsp-8+arg_8], rbx
0x18002f3d1  mov     [rsp-8+arg_10], rsi
0x18002f3d6  push    rbp
0x18002f3d7  push    rdi
0x18002f3d8  push    r15
0x18002f3da  lea     rbp, [rsp-50h]
0x18002f3df  sub     rsp, 150h
0x18002f3e6  mov     rax, cs:__security_cookie
0x18002f3ed  xor     rax, rsp
0x18002f3f0  mov     [rbp+60h+var_18], rax
0x18002f3f4  lea     rax, String1; "Init"
0x18002f3fb  mov     [rsp+160h+var_100], 0
0x18002f403  xorps   xmm0, xmm0
0x18002f406  mov     [rbp+60h+var_E0], rax
0x18002f40a  xor     eax, eax
0x18002f40c  xorps   xmm1, xmm1
0x18002f40f  mov     rbx, rcx
0x18002f412  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x18002f416  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x18002f41a  mov     [rsp+160h+var_E8], rax
0x18002f41f  movups  [rsp+160h+var_F8], xmm1
0x18002f424  movups  xmmword ptr [rbp+60h+Rect.left], xmm0
0x18002f428  cmp     [rcx+40h], rax
0x18002f42c  jnz     short loc_18002F438
0x18002f42e  mov     eax, 8007000Eh
0x18002f433  jmp     loc_18002F735
0x18002f438  mov     rcx, [rcx+8]; hWnd
0x18002f43c  lea     rdx, [rbp+60h+Rect]; lpRect
0x18002f440  call    cs:__imp_GetWindowRect
0x18002f446  mov     r15d, 1
0x18002f44c  test    eax, eax
0x18002f44e  jz      short loc_18002F494
0x18002f450  mov     edi, [rbp+60h+Rect.right]
0x18002f453  lea     ecx, [r15+10h]; nIndex
0x18002f457  mov     esi, [rbp+60h+Rect.bottom]
0x18002f45a  sub     edi, [rbp+60h+Rect.left]
0x18002f45d  sub     esi, [rbp+60h+Rect.top]
0x18002f460  call    cs:__imp_GetSystemMetrics
0x18002f466  mov     ecx, eax
0x18002f468  test    eax, eax
0x18002f46a  jle     short loc_18002F494
0x18002f46c  cmp     eax, esi
0x18002f46e  jge     short loc_18002F494
0x18002f470  imul    edi, ecx
0x18002f473  xor     r8d, r8d; Y
0x18002f476  mov     [rsp+160h+bRepaint], r15d; bRepaint
0x18002f47b  mov     [rsp+160h+nHeight], ecx; nHeight
0x18002f47f  mov     rcx, [rbx+8]; hWnd
0x18002f483  mov     eax, edi
0x18002f485  cdq
0x18002f486  idiv    esi
0x18002f488  mov     edx, [rbp+60h+Rect.left]; X
0x18002f48b  mov     r9d, eax; nWidth
0x18002f48e  call    cs:__imp_MoveWindow
0x18002f494  mov     rcx, [rbx+48h]
0x18002f498  test    rcx, rcx
0x18002f49b  jz      loc_18002F54B
0x18002f4a1  mov     rax, [rcx]
0x18002f4a4  lea     rdx, [rsp+160h+var_100]
0x18002f4a9  mov     qword ptr [rsp+160h+bRepaint], rdx
0x18002f4ae  lea     r8, [rbp+60h+var_E0]
0x18002f4b2  mov     edi, 800h
0x18002f4b7  lea     rdx, GUID_NULL
0x18002f4be  mov     r9d, r15d
0x18002f4c1  mov     [rsp+160h+nHeight], edi
0x18002f4c5  mov     rax, [rax+28h]
0x18002f4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4ce  test    eax, eax
0x18002f4d0  js      short loc_18002F54B
0x18002f4d2  lea     rcx, [rbp+60h+pvarg]; pvarg
0x18002f4d6  call    cs:__imp_VariantInit
0x18002f4dc  mov     rcx, [rbx+48h]
0x18002f4e0  lea     rdx, [rsp+160h+var_F8]
0x18002f4e5  mov     [rsp+160h+var_120], 0
0x18002f4ee  lea     r8, GUID_NULL
0x18002f4f5  mov     eax, 13h
0x18002f4fa  mov     qword ptr [rsp+160h+var_128], 0
0x18002f503  mov     word ptr [rbp+60h+pvarg], ax
0x18002f507  mov     r9d, edi
0x18002f50a  mov     eax, [rbx+8]
0x18002f50d  mov     dword ptr [rbp+60h+pvarg+8], eax
0x18002f510  lea     rax, [rbp+60h+pvarg]
0x18002f514  mov     qword ptr [rsp+160h+var_F8], rax
0x18002f519  mov     [rsp+160h+var_E8], r15
0x18002f51e  mov     qword ptr [rsp+160h+var_F8+8], 0
0x18002f527  mov     rax, [rcx]
0x18002f52a  mov     qword ptr [rsp+160h+var_130], 0
0x18002f533  mov     qword ptr [rsp+160h+bRepaint], rdx
0x18002f538  mov     edx, [rsp+160h+var_100]
0x18002f53c  mov     rax, [rax+30h]
0x18002f540  mov     word ptr [rsp+160h+nHeight], r15w
0x18002f546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f54b  mov     rdi, [rbx+40h]
0x18002f54f  lea     rcx, [rbp+60h+WndClass]; void *
0x18002f553  mov     rsi, [rbx+8]
0x18002f557  xorps   xmm0, xmm0
0x18002f55a  mov     r15d, 48h ; 'H'
0x18002f560  xor     edx, edx; Val
0x18002f562  mov     r8d, r15d; Size
0x18002f565  movups  xmmword ptr [rbp+60h+var_40.left], xmm0
0x18002f569  call    memset_0
0x18002f56e  cmp     qword ptr [rdi+38h], 0
0x18002f573  jz      short loc_18002F57D
0x18002f575  mov     rcx, rdi; this
0x18002f578  call    ?CloseOleObject@CWebBrowser@@AEAAXXZ; CWebBrowser::CloseOleObject(void)
0x18002f57d  cmp     qword ptr [rdi+48h], 0
0x18002f582  jnz     short loc_18002F58E
0x18002f584  mov     eax, 80004003h
0x18002f589  jmp     loc_18002F735
0x18002f58e  mov     r8, r15; Size
0x18002f591  lea     rcx, [rbp+60h+WndClass]; void *
0x18002f595  xor     edx, edx; Val
0x18002f597  call    memset_0
0x18002f59c  lea     rdx, [rbp+60h+var_40]; lpRect
0x18002f5a0  mov     rcx, rsi; hWnd
0x18002f5a3  call    cs:__imp_GetClientRect
0x18002f5a9  lea     rax, ClassName; "MSDRM Trident Window"
0x18002f5b0  mov     [rbp+60h+WndClass.style], 3
0x18002f5b7  mov     [rbp+60h+WndClass.lpszClassName], rax
0x18002f5bb  mov     edx, 7F00h; lpCursorName
0x18002f5c0  lea     rax, ?MsdrmTridentWndProc@@YA_JPEAUHWND__@@I_K_J@Z; MsdrmTridentWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18002f5c7  xor     ecx, ecx; hInstance
0x18002f5c9  mov     [rbp+60h+WndClass.lpfnWndProc], rax
0x18002f5cd  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18002f5d4  mov     [rbp+60h+WndClass.hInstance], rax
0x18002f5d8  call    cs:__imp_LoadCursorW
0x18002f5de  lea     rcx, [rbp+60h+WndClass]; lpWndClass
0x18002f5e2  mov     [rbp+60h+WndClass.hCursor], rax
0x18002f5e6  call    IsolationAwareRegisterClassW
0x18002f5eb  movzx   ecx, ax; int
0x18002f5ee  xor     eax, eax
0x18002f5f0  cmp     ax, cx
0x18002f5f3  jnz     short loc_18002F616
0x18002f5f5  call    cs:__imp_GetLastError
0x18002f5fb  test    eax, eax
0x18002f5fd  jle     short loc_18002F607
0x18002f5ff  movzx   eax, ax
0x18002f602  or      eax, 80070000h
0x18002f607  test    eax, eax
0x18002f609  mov     ecx, 80004005h
0x18002f60e  cmovns  eax, ecx
0x18002f611  jmp     loc_18002F735
0x18002f616  mov     rax, [rbp+60h+WndClass.hInstance]
0x18002f61a  mov     [rsp+160h+var_110], rax; HINSTANCE
0x18002f61f  mov     eax, [rbp+60h+var_40.bottom]
0x18002f622  mov     [rsp+160h+var_120], rsi; HWND
0x18002f627  mov     [rsp+160h+var_128], eax; int
0x18002f62b  mov     eax, [rbp+60h+var_40.right]
0x18002f62e  mov     [rsp+160h+var_130], eax; int
0x18002f632  mov     eax, [rbp+60h+var_40.top]
0x18002f635  mov     [rsp+160h+bRepaint], eax; int
0x18002f639  mov     eax, [rbp+60h+var_40.left]
0x18002f63c  mov     [rsp+160h+nHeight], eax; int
0x18002f640  call    IsolationAwareCreateWindowExW
0x18002f645  mov     [rdi+38h], rax
0x18002f649  mov     r8, rax
0x18002f64c  test    rax, rax
0x18002f64f  jz      short loc_18002F5F5
0x18002f651  mov     rcx, [rdi+48h]
0x18002f655  lea     rax, [rdi+8]
0x18002f659  mov     [rdi+40h], rsi
0x18002f65d  neg     rdi
0x18002f660  sbb     r9, r9
0x18002f663  mov     rdx, [rcx]
0x18002f666  and     r9, rax
0x18002f669  mov     rax, [rdx+58h]
0x18002f66d  lea     rdx, [rbp+60h+var_40]
0x18002f671  mov     qword ptr [rsp+160h+var_130], rdx
0x18002f676  mov     qword ptr [rsp+160h+bRepaint], r8
0x18002f67b  xor     r8d, r8d
0x18002f67e  mov     [rsp+160h+nHeight], 0FFFFFFFFh
0x18002f686  lea     edx, [r8-5]
0x18002f68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f68f  test    eax, eax
0x18002f691  js      loc_18002F735
0x18002f697  mov     rdi, [rbx+38h]
0x18002f69b  test    rdi, rdi
0x18002f69e  jz      loc_18002F735
0x18002f6a4  mov     rbx, [rbx+40h]
0x18002f6a8  lea     rcx, [rbp+60h+var_C0]; pvarg
0x18002f6ac  xor     eax, eax
0x18002f6ae  xorps   xmm0, xmm0
0x18002f6b1  xorps   xmm1, xmm1
0x18002f6b4  mov     qword ptr [rbp+60h+var_C0+10h], rax
0x18002f6b8  movups  xmmword ptr [rbp+60h+var_C0], xmm0
0x18002f6bc  mov     [rbp+60h+var_30], rax
0x18002f6c0  movups  xmmword ptr [rbp+60h+var_40.left], xmm1
0x18002f6c4  mov     [rbp+60h+var_98], rax
0x18002f6c8  movups  [rbp+60h+var_A8], xmm0
0x18002f6cc  call    cs:__imp_VariantInit
0x18002f6d2  lea     rcx, [rbp+60h+var_40]; pvarg
0x18002f6d6  call    cs:__imp_VariantInit
0x18002f6dc  mov     eax, 8
0x18002f6e1  mov     rcx, rdi; psz
0x18002f6e4  mov     word ptr [rbp+60h+var_C0], ax
0x18002f6e8  mov     word ptr [rbp+60h+var_40.left], ax
0x18002f6ec  call    cs:__imp_SysAllocString
0x18002f6f2  xor     ecx, ecx; psz
0x18002f6f4  mov     qword ptr [rbp+60h+var_C0+8], rax
0x18002f6f8  call    cs:__imp_SysAllocString
0x18002f6fe  mov     rcx, [rbx+50h]
0x18002f702  lea     rdx, [rbp+60h+var_A8]
0x18002f706  mov     qword ptr [rsp+160h+bRepaint], rdx
0x18002f70b  lea     r9, [rbp+60h+var_40]
0x18002f70f  mov     qword ptr [rbp+60h+var_40.right], rax
0x18002f713  lea     rdx, [rbp+60h+var_A8]
0x18002f717  mov     qword ptr [rsp+160h+nHeight], rdx
0x18002f71c  lea     r8, [rbp+60h+var_A8]
0x18002f720  mov     rax, [rcx]
0x18002f723  lea     rdx, [rbp+60h+var_C0]
0x18002f727  mov     rax, [rax+1A0h]
0x18002f72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f733  xor     eax, eax
0x18002f735  cdqe
0x18002f737  mov     rcx, [rbp+60h+var_18]
0x18002f73b  xor     rcx, rsp; StackCookie
0x18002f73e  call    __security_check_cookie
0x18002f743  lea     r11, [rsp+160h+var_10]
0x18002f74b  mov     rbx, [r11+28h]
0x18002f74f  mov     rsi, [r11+30h]
0x18002f753  mov     rsp, r11
0x18002f756  pop     r15
0x18002f758  pop     rdi
0x18002f759  pop     rbp
0x18002f75a  retn
```
