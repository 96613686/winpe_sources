# CDocHostUIHandler::ShowContextMenu(ulong,tagPOINT *,IUnknown *,IDispatch *)

- ea: `0x180018710`
- end: `0x1800189f4`
- name: `?ShowContextMenu@CDocHostUIHandler@@UEAAJKPEAUtagPOINT@@PEAUIUnknown@@PEAUIDispatch@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(CDocHostUIHandler *__hidden this, unsigned int, struct tagPOINT *, struct IUnknown *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180006708`
- `0x180018710`
- `0x180067798`
- `0x18006e4b8`
- `0x180078010`

## import_xrefs

- `USER32!AppendMenuW` at `0x180018779`
- `USER32!AppendMenuW` at `0x180018797`
- `USER32!AppendMenuW` at `0x1800187af`
- `USER32!AppendMenuW` at `0x1800187cb`
- `USER32!AppendMenuW` at `0x1800187df`
- `USER32!AppendMenuW` at `0x1800187fd`
- `USER32!AppendMenuW` at `0x180018811`
- `USER32!AppendMenuW` at `0x18001882d`
- `USER32!AppendMenuW` at `0x180018849`
- `USER32!AppendMenuW` at `0x18001886e`
- `USER32!AppendMenuW` at `0x180018883`
- `USER32!AppendMenuW` at `0x18001889f`
- `USER32!AppendMenuW` at `0x180018779`
- `USER32!AppendMenuW` at `0x180018797`
- `USER32!AppendMenuW` at `0x1800187af`
- `USER32!AppendMenuW` at `0x1800187cb`
- `USER32!AppendMenuW` at `0x1800187df`
- `USER32!AppendMenuW` at `0x1800187fd`
- `USER32!AppendMenuW` at `0x180018811`
- `USER32!AppendMenuW` at `0x18001882d`
- `USER32!AppendMenuW` at `0x180018849`
- `USER32!AppendMenuW` at `0x18001886e`
- `USER32!AppendMenuW` at `0x180018883`
- `USER32!AppendMenuW` at `0x18001889f`
- `USER32!TrackPopupMenu` at `0x180018924`
- `USER32!TrackPopupMenu` at `0x180018924`
- `USER32!GetDesktopWindow` at `0x1800188f6`
- `USER32!GetDesktopWindow` at `0x1800188f6`
- `USER32!GetActiveWindow` at `0x1800188e8`
- `USER32!GetActiveWindow` at `0x1800188e8`
- `USER32!CreatePopupMenu` at `0x180018742`
- `USER32!CreatePopupMenu` at `0x180018742`
- `USER32!DestroyMenu` at `0x18001892f`
- `USER32!DestroyMenu` at `0x18001892f`
- `OLEAUT32!__imp_VariantInit` at `0x1800188c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800188cb`
- `OLEAUT32!__imp_VariantInit` at `0x1800188c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800188cb`

## pseudocode

```c
__int64 __fastcall CDocHostUIHandler::ShowContextMenu(
        CDocHostUIHandler *this,
        int a2,
        struct tagPOINT *a3,
        struct IUnknown *a4)
{
  HMENU PopupMenu; // rdi
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax
  const WCHAR *v11; // rax
  const WCHAR *v12; // rax
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  const WCHAR *v15; // rax
  const WCHAR *StringResourceW; // rax
  HWND hWnd; // rbx
  int v18; // ebx
  LONG v19; // edx
  __int64 v20; // r8
  __int64 *v21; // rdx
  int v22; // edx
  VARIANTARG pvarg; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG v25; // [rsp+58h] [rbp-18h] BYREF

  if ( (a2 & 0xFFFFFFFA) == 0 && a2 != 4 )
  {
    PopupMenu = CreatePopupMenu();
    if ( !PopupMenu )
      return 0;
    if ( a2 )
    {
      if ( a2 != 1 )
      {
LABEL_9:
        StringResourceW = GetStringResourceW(0x43Au);
        AppendMenuW(PopupMenu, 0, 0xAu, StringResourceW);
        memset(&pvarg, 0, sizeof(pvarg));
        memset(&v25, 0, sizeof(v25));
        VariantInit(&pvarg);
        VariantInit(&v25);
        hWnd = *(HWND *)(*((_QWORD *)this + 2) + 176LL);
        if ( !(unsigned int)IsValidWindow(hWnd) )
          hWnd = GetActiveWindow();
        if ( !hWnd )
          hWnd = GetDesktopWindow();
        v18 = TrackPopupMenu(PopupMenu, 0x182u, a3->x, a3->y, 0, hWnd, 0);
        DestroyMenu(PopupMenu);
        if ( v18 < 1000 )
        {
          if ( v18 == 10 )
          {
            v19 = LOWORD(a3->x) | (LOWORD(a3->y) << 16);
            pvarg.vt = 3;
            pvarg.lVal = v19;
          }
          v20 = (unsigned int)v18;
          v21 = 0;
          goto LABEL_24;
        }
        if ( v18 >= 2000 )
        {
          v20 = (unsigned int)(v18 - 2000);
          v21 = CGID_IWebBrowserPriv;
LABEL_24:
          ((void (__fastcall *)(struct IUnknown *, __int64 *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))a4->lpVtbl[1].AddRef)(
            a4,
            v21,
            v20,
            0,
            &pvarg,
            &v25);
          return 0;
        }
        if ( v18 == 1204 )
        {
          v22 = 100;
LABEL_22:
          COleDispatchDriver::InvokeHelper(*(COleDispatchDriver **)(*((_QWORD *)this + 2) + 152LL), v22, 1u, 0, 0, 0);
          return 0;
        }
        if ( v18 == 1209 )
        {
          v22 = 101;
          goto LABEL_22;
        }
        return 0;
      }
      v15 = GetStringResourceW(0x43Bu);
      AppendMenuW(PopupMenu, 0, 0xCu, v15);
    }
    else
    {
      v9 = GetStringResourceW(0x428u);
      AppendMenuW(PopupMenu, 0, 0x4B4u, v9);
      v10 = GetStringResourceW(0x429u);
      AppendMenuW(PopupMenu, 0, 0x4B9u, v10);
      AppendMenuW(PopupMenu, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, 0);
      v11 = GetStringResourceW(0x438u);
      AppendMenuW(PopupMenu, 0, 0x11u, v11);
      AppendMenuW(PopupMenu, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, 0);
      v12 = GetStringResourceW(0x439u);
      AppendMenuW(PopupMenu, 0, 0x7D2u, v12);
      AppendMenuW(PopupMenu, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, 0);
      v13 = GetStringResourceW(0x42Fu);
      AppendMenuW(PopupMenu, 0, 6u, v13);
      v14 = GetStringResourceW(0x42Cu);
      AppendMenuW(PopupMenu, 0, 0x16u, v14);
    }
    AppendMenuW(PopupMenu, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, 0);
    goto LABEL_9;
  }
  return 1;
}

```

## disassembly

```asm
0x180018710  push    rbp
0x180018712  push    rbx
0x180018713  push    rsi
0x180018714  push    rdi
0x180018715  push    r13
0x180018717  push    r14
0x180018719  push    r15
0x18001871b  mov     rbp, rsp
0x18001871e  sub     rsp, 70h
0x180018722  mov     r15, r9
0x180018725  mov     r14, r8
0x180018728  mov     ebx, edx
0x18001872a  mov     r13, rcx
0x18001872d  test    edx, 0FFFFFFFAh
0x180018733  jnz     loc_1800189E0
0x180018739  cmp     edx, 4
0x18001873c  jz      loc_1800189E0
0x180018742  call    cs:__imp_CreatePopupMenu
0x180018748  mov     rdi, rax
0x18001874b  test    rax, rax
0x18001874e  jz      loc_1800189DC
0x180018754  mov     esi, 1
0x180018759  test    ebx, ebx
0x18001875b  jnz     loc_180018854
0x180018761  mov     ecx, 428h; uID
0x180018766  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001876b  mov     r9, rax; lpNewItem
0x18001876e  xor     edx, edx; uFlags
0x180018770  mov     r8d, 4B4h; uIDNewItem
0x180018776  mov     rcx, rdi; hMenu
0x180018779  call    cs:__imp_AppendMenuW
0x18001877f  mov     ecx, 429h; uID
0x180018784  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x180018789  mov     r9, rax; lpNewItem
0x18001878c  xor     edx, edx; uFlags
0x18001878e  mov     r8d, 4B9h; uIDNewItem
0x180018794  mov     rcx, rdi; hMenu
0x180018797  call    cs:__imp_AppendMenuW
0x18001879d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800187a1  xor     r9d, r9d; lpNewItem
0x1800187a4  mov     r8, rbx; uIDNewItem
0x1800187a7  mov     edx, 800h; uFlags
0x1800187ac  mov     rcx, rdi; hMenu
0x1800187af  call    cs:__imp_AppendMenuW
0x1800187b5  mov     ecx, 438h; uID
0x1800187ba  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x1800187bf  mov     r9, rax; lpNewItem
0x1800187c2  lea     r8d, [rsi+10h]; uIDNewItem
0x1800187c6  xor     edx, edx; uFlags
0x1800187c8  mov     rcx, rdi; hMenu
0x1800187cb  call    cs:__imp_AppendMenuW
0x1800187d1  xor     r9d, r9d; lpNewItem
0x1800187d4  mov     r8, rbx; uIDNewItem
0x1800187d7  mov     edx, 800h; uFlags
0x1800187dc  mov     rcx, rdi; hMenu
0x1800187df  call    cs:__imp_AppendMenuW
0x1800187e5  mov     ecx, 439h; uID
0x1800187ea  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x1800187ef  mov     r9, rax; lpNewItem
0x1800187f2  xor     edx, edx; uFlags
0x1800187f4  mov     r8d, 7D2h; uIDNewItem
0x1800187fa  mov     rcx, rdi; hMenu
0x1800187fd  call    cs:__imp_AppendMenuW
0x180018803  xor     r9d, r9d; lpNewItem
0x180018806  mov     r8, rbx; uIDNewItem
0x180018809  mov     edx, 800h; uFlags
0x18001880e  mov     rcx, rdi; hMenu
0x180018811  call    cs:__imp_AppendMenuW
0x180018817  mov     ecx, 42Fh; uID
0x18001881c  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x180018821  mov     r9, rax; lpNewItem
0x180018824  lea     r8d, [rsi+5]; uIDNewItem
0x180018828  xor     edx, edx; uFlags
0x18001882a  mov     rcx, rdi; hMenu
0x18001882d  call    cs:__imp_AppendMenuW
0x180018833  mov     ecx, 42Ch; uID
0x180018838  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001883d  mov     r9, rax; lpNewItem
0x180018840  lea     r8d, [rsi+15h]; uIDNewItem
0x180018844  xor     edx, edx; uFlags
0x180018846  mov     rcx, rdi; hMenu
0x180018849  call    cs:__imp_AppendMenuW
0x18001884f  mov     r8, rbx
0x180018852  jmp     short loc_180018878
0x180018854  cmp     ebx, esi
0x180018856  jnz     short loc_180018889
0x180018858  mov     ecx, 43Bh; uID
0x18001885d  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x180018862  xor     edx, edx; uFlags
0x180018864  mov     r9, rax; lpNewItem
0x180018867  mov     rcx, rdi; hMenu
0x18001886a  lea     r8d, [rdx+0Ch]; uIDNewItem
0x18001886e  call    cs:__imp_AppendMenuW
0x180018874  or      r8, 0FFFFFFFFFFFFFFFFh; uIDNewItem
0x180018878  xor     r9d, r9d; lpNewItem
0x18001887b  mov     edx, 800h; uFlags
0x180018880  mov     rcx, rdi; hMenu
0x180018883  call    cs:__imp_AppendMenuW
0x180018889  mov     ecx, 43Ah; uID
0x18001888e  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x180018893  xor     edx, edx; uFlags
0x180018895  mov     r9, rax; lpNewItem
0x180018898  mov     rcx, rdi; hMenu
0x18001889b  lea     r8d, [rdx+0Ah]; uIDNewItem
0x18001889f  call    cs:__imp_AppendMenuW
0x1800188a5  xor     eax, eax
0x1800188a7  lea     rcx, [rbp+pvarg]; pvarg
0x1800188ab  xorps   xmm0, xmm0
0x1800188ae  mov     qword ptr [rbp+pvarg+10h], rax
0x1800188b2  xorps   xmm1, xmm1
0x1800188b5  mov     qword ptr [rbp+var_18+10h], rax
0x1800188b9  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800188bd  movups  xmmword ptr [rbp+var_18], xmm1
0x1800188c1  call    cs:__imp_VariantInit
0x1800188c7  lea     rcx, [rbp+var_18]; pvarg
0x1800188cb  call    cs:__imp_VariantInit
0x1800188d1  mov     rax, [r13+10h]
0x1800188d5  mov     rbx, [rax+0B0h]
0x1800188dc  mov     rcx, rbx; HWND
0x1800188df  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x1800188e4  test    eax, eax
0x1800188e6  jnz     short loc_1800188F1
0x1800188e8  call    cs:__imp_GetActiveWindow
0x1800188ee  mov     rbx, rax
0x1800188f1  test    rbx, rbx
0x1800188f4  jnz     short loc_1800188FF
0x1800188f6  call    cs:__imp_GetDesktopWindow
0x1800188fc  mov     rbx, rax
0x1800188ff  mov     r9d, [r14+4]; y
0x180018903  mov     edx, 182h; uFlags
0x180018908  mov     r8d, [r14]; x
0x18001890b  mov     rcx, rdi; hMenu
0x18001890e  mov     [rsp+70h+prcRect], 0; prcRect
0x180018917  mov     [rsp+70h+hWnd], rbx; hWnd
0x18001891c  mov     [rsp+70h+nReserved], 0; nReserved
0x180018924  call    cs:__imp_TrackPopupMenu
0x18001892a  mov     rcx, rdi; hMenu
0x18001892d  mov     ebx, eax
0x18001892f  call    cs:__imp_DestroyMenu
0x180018935  cmp     ebx, 3E8h
0x18001893b  jge     short loc_180018961
0x18001893d  cmp     ebx, 0Ah
0x180018940  jnz     short loc_18001895A
0x180018942  movzx   edx, word ptr [r14+4]
0x180018947  lea     eax, [rbx-7]
0x18001894a  movzx   ecx, word ptr [r14]
0x18001894e  shl     edx, 10h
0x180018951  or      edx, ecx
0x180018953  mov     word ptr [rbp+pvarg], ax
0x180018957  mov     dword ptr [rbp+pvarg+8], edx
0x18001895a  mov     r8d, ebx
0x18001895d  xor     edx, edx
0x18001895f  jmp     short loc_1800189B8
0x180018961  cmp     ebx, 7D0h
0x180018967  jge     short loc_1800189AA
0x180018969  cmp     ebx, 4B4h
0x18001896f  jnz     short loc_180018978
0x180018971  mov     edx, 64h ; 'd'
0x180018976  jmp     short loc_180018985
0x180018978  cmp     ebx, 4B9h
0x18001897e  jnz     short loc_1800189DC
0x180018980  mov     edx, 65h ; 'e'; int
0x180018985  mov     rcx, [r13+10h]
0x180018989  xor     eax, eax
0x18001898b  mov     [rsp+70h+hWnd], rax; unsigned __int8 *
0x180018990  mov     r8d, esi; unsigned __int16
0x180018993  movzx   r9d, ax; unsigned __int16
0x180018997  mov     qword ptr [rsp+70h+nReserved], rax; void *
0x18001899c  mov     rcx, [rcx+98h]; this
0x1800189a3  call    ?InvokeHelper@COleDispatchDriver@@QEAAXJGGPEAXPEBEZZ; COleDispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1800189a8  jmp     short loc_1800189DC
0x1800189aa  lea     r8d, [rbx-7D0h]
0x1800189b1  lea     rdx, CGID_IWebBrowserPriv
0x1800189b8  mov     rax, [r15]
0x1800189bb  lea     rcx, [rbp+var_18]
0x1800189bf  mov     [rsp+70h+hWnd], rcx
0x1800189c4  xor     r9d, r9d
0x1800189c7  lea     rcx, [rbp+pvarg]
0x1800189cb  mov     qword ptr [rsp+70h+nReserved], rcx
0x1800189d0  mov     rcx, r15
0x1800189d3  mov     rax, [rax+20h]
0x1800189d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189dc  xor     eax, eax
0x1800189de  jmp     short loc_1800189E5
0x1800189e0  mov     eax, 1
0x1800189e5  add     rsp, 70h
0x1800189e9  pop     r15
0x1800189eb  pop     r14
0x1800189ed  pop     r13
0x1800189ef  pop     rdi
0x1800189f0  pop     rsi
0x1800189f1  pop     rbx
0x1800189f2  pop     rbp
0x1800189f3  retn
```
