# ATL::AtlAxWindowProc

- ea: `0x140026880`
- end: `0x140026ac6`
- name: `ATL::AtlAxWindowProc`
- size: `582`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140026880`
- `0x14003ce40`
- `0x140062396`
- `0x1400c9074`
- `0x1400e9e10`
- `0x1400e9ed0`
- `0x1400f3010`

## import_xrefs

- `USER32!GetWindowTextW` at `0x14002695d`
- `USER32!GetWindowTextW` at `0x14002695d`
- `USER32!DefWindowProcW` at `0x1400268c8`
- `USER32!DefWindowProcW` at `0x1400268c8`
- `USER32!SetWindowLongPtrW` at `0x140026a3e`
- `USER32!SetWindowLongPtrW` at `0x140026a3e`
- `USER32!SetWindowLongW` at `0x140026a88`
- `USER32!SetWindowLongW` at `0x140026a88`
- `USER32!GetWindowLongW` at `0x140026a5f`
- `USER32!GetWindowLongW` at `0x140026a73`
- `USER32!GetWindowLongW` at `0x140026a5f`
- `USER32!GetWindowLongW` at `0x140026a73`
- `USER32!GetWindowTextLengthW` at `0x140026920`
- `USER32!GetWindowTextLengthW` at `0x140026920`
- `USER32!GetWindowLongPtrW` at `0x1400268f0`
- `USER32!GetWindowLongPtrW` at `0x1400268f0`
- `USER32!GetWindow` at `0x140026a4c`
- `USER32!GetWindow` at `0x140026a4c`
- `USER32!SetWindowTextW` at `0x14002696d`
- `USER32!SetWindowTextW` at `0x14002696d`
- `ole32!OleInitialize` at `0x140026917`
- `ole32!OleInitialize` at `0x140026917`
- `ole32!OleUninitialize` at `0x14002690d`
- `ole32!OleUninitialize` at `0x14002690d`
- `ole32!CreateStreamOnHGlobal` at `0x1400269e8`
- `ole32!CreateStreamOnHGlobal` at `0x1400269e8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1400269a6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1400269a6`
- `KERNEL32!GlobalLock` at `0x1400269bb`
- `KERNEL32!GlobalLock` at `0x1400269bb`
- `KERNEL32!GlobalUnlock` at `0x1400269d6`
- `KERNEL32!GlobalUnlock` at `0x1400269d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LRESULT __fastcall ATL::AtlAxWindowProc(HWND hWnd, UINT Msg, WPARAM wParam, unsigned __int16 **lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  int v10; // r8d
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  int v16; // eax
  unsigned __int16 *v17; // rcx
  SIZE_T v18; // r15
  __int64 v19; // r8
  HGLOBAL v20; // rax
  void *v21; // r12
  void *v22; // rax
  HWND Window; // rax
  LONG WindowLongW; // eax
  __int64 v25; // [rsp+28h] [rbp-18h]
  __int64 v26; // [rsp+30h] [rbp-10h]
  WCHAR String[4]; // [rsp+40h] [rbp+0h] BYREF
  int (__fastcall ***v28)(_QWORD, GUID *, LONG_PTR *); // [rsp+48h] [rbp+8h] BYREF
  LONG_PTR dwNewLong; // [rsp+50h] [rbp+10h] BYREF

  if ( Msg != 1 )
  {
    if ( Msg == 130 )
    {
      WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
      if ( WindowLongPtrW )
        (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
      OleUninitialize();
    }
    return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
  }
  OleInitialize(0);
  v10 = GetWindowTextLengthW(hWnd) + 1;
  v11 = 2LL * v10;
  v12 = v11 + 15;
  if ( v11 + 15 < v11 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
  v14 = alloca(v13);
  v15 = alloca(v13);
  GetWindowTextW(hWnd, String, v10);
  SetWindowTextW(hWnd, &WindowName);
  dwNewLong = 0;
  v16 = 0;
  if ( lParam && (v17 = *lParam) != 0 )
  {
    v16 = *v17;
    v18 = *v17;
  }
  else
  {
    v18 = 0;
  }
  v19 = 0;
  *(_QWORD *)String = 0;
  if ( v16 )
  {
    v20 = GlobalAlloc(0x42u, v18);
    v21 = v20;
    if ( !v20 )
      goto LABEL_23;
    v22 = GlobalLock(v20);
    memcpy_0(v22, *lParam + 1, v18);
    GlobalUnlock(v21);
    CreateStreamOnHGlobal(v21, 1, (LPSTREAM *)String);
    v19 = *(_QWORD *)String;
  }
  v28 = 0;
  if ( (int)AtlAxCreateControlEx(String, (__int64)hWnd, v19, &v28, 0, v25, v26) >= 0
    && (**v28)(v28, &IID_IAxWinHostWindow, &dwNewLong) >= 0 )
  {
    SetWindowLongPtrW(hWnd, -21, dwNewLong);
    Window = GetWindow(hWnd, 5u);
    if ( Window && (GetWindowLongW(Window, -20) & 0x10000) != 0 )
    {
      WindowLongW = GetWindowLongW(hWnd, -20);
      SetWindowLongW(hWnd, -20, WindowLongW | 0x10000);
    }
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&v28);
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(String);
    return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
  }
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&v28);
LABEL_23:
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(String);
  return -1;
}

```

## disassembly

```asm
0x140026880  push    rbp
0x140026882  push    rbx
0x140026883  push    rsi
0x140026884  push    rdi
0x140026885  push    r12
0x140026887  push    r13
0x140026889  push    r14
0x14002688b  push    r15
0x14002688d  sub     rsp, 68h
0x140026891  lea     rbp, [rsp+40h]
0x140026896  mov     rax, cs:__security_cookie
0x14002689d  xor     rax, rbp
0x1400268a0  mov     [rbp+60h+var_48], rax
0x1400268a4  mov     rsi, r9
0x1400268a7  mov     r14, r8
0x1400268aa  mov     ebx, edx
0x1400268ac  mov     rdi, rcx
0x1400268af  mov     eax, edx
0x1400268b1  sub     eax, 1
0x1400268b4  jz      short loc_140026915
0x1400268b6  cmp     eax, 81h
0x1400268bb  jz      short loc_1400268EB
0x1400268bd  mov     r9, rsi; lParam
0x1400268c0  mov     r8, r14; wParam
0x1400268c3  mov     edx, ebx; Msg
0x1400268c5  mov     rcx, rdi; hWnd
0x1400268c8  call    cs:__imp_DefWindowProcW
0x1400268ce  mov     rcx, [rbp+60h+var_48]
0x1400268d2  xor     rcx, rbp; StackCookie
0x1400268d5  call    __security_check_cookie
0x1400268da  lea     rsp, [rbp+28h]
0x1400268de  pop     r15
0x1400268e0  pop     r14
0x1400268e2  pop     r13
0x1400268e4  pop     r12
0x1400268e6  pop     rdi
0x1400268e7  pop     rsi
0x1400268e8  pop     rbx
0x1400268e9  pop     rbp
0x1400268ea  retn
0x1400268eb  mov     edx, 0FFFFFFEBh; nIndex
0x1400268f0  call    cs:__imp_GetWindowLongPtrW
0x1400268f6  mov     rdx, rax
0x1400268f9  test    rax, rax
0x1400268fc  jz      short loc_14002690D
0x1400268fe  mov     rcx, [rax]
0x140026901  mov     rax, [rcx+10h]
0x140026905  mov     rcx, rdx
0x140026908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002690d  call    cs:__imp_OleUninitialize
0x140026913  jmp     short loc_1400268BD
0x140026915  xor     ecx, ecx; pvReserved
0x140026917  call    cs:__imp_OleInitialize
0x14002691d  mov     rcx, rdi; hWnd
0x140026920  call    cs:__imp_GetWindowTextLengthW
0x140026926  lea     r8d, [rax+1]
0x14002692a  movsxd  rax, r8d
0x14002692d  add     rax, rax
0x140026930  lea     rcx, [rax+0Fh]
0x140026934  cmp     rcx, rax
0x140026937  ja      short loc_140026943
0x140026939  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140026943  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140026947  mov     rax, rcx
0x14002694a  call    _alloca_probe
0x14002694f  sub     rsp, rcx
0x140026952  lea     r13, [rsp+0A0h+String]
0x140026957  mov     rdx, r13; lpString
0x14002695a  mov     rcx, rdi; hWnd
0x14002695d  call    cs:__imp_GetWindowTextW
0x140026963  lea     rdx, WindowName; lpString
0x14002696a  mov     rcx, rdi; hWnd
0x14002696d  call    cs:__imp_SetWindowTextW
0x140026973  xor     edx, edx
0x140026975  mov     [rbp+60h+dwNewLong], rdx
0x140026979  mov     eax, edx
0x14002697b  test    rsi, rsi
0x14002697e  jz      short loc_140026990
0x140026980  mov     rcx, [rsi]
0x140026983  test    rcx, rcx
0x140026986  jz      short loc_140026990
0x140026988  movzx   eax, word ptr [rcx]
0x14002698b  mov     r15d, eax
0x14002698e  jmp     short loc_140026993
0x140026990  mov     r15, rdx
0x140026993  mov     r8, rdx
0x140026996  mov     qword ptr [rbp+60h+String], rdx
0x14002699a  test    eax, eax
0x14002699c  jz      short loc_1400269F4
0x14002699e  mov     rdx, r15; dwBytes
0x1400269a1  mov     ecx, 42h ; 'B'; uFlags
0x1400269a6  call    cs:__imp_GlobalAlloc
0x1400269ac  mov     r12, rax
0x1400269af  test    rax, rax
0x1400269b2  jz      loc_140026AB1
0x1400269b8  mov     rcx, rax; hMem
0x1400269bb  call    cs:__imp_GlobalLock
0x1400269c1  mov     rdx, [rsi]
0x1400269c4  add     rdx, 2; Src
0x1400269c8  mov     r8, r15; Size
0x1400269cb  mov     rcx, rax; void *
0x1400269ce  call    memcpy_0
0x1400269d3  mov     rcx, r12; hMem
0x1400269d6  call    cs:__imp_GlobalUnlock
0x1400269dc  lea     r8, [rbp+60h+String]; ppstm
0x1400269e0  mov     edx, 1; fDeleteOnRelease
0x1400269e5  mov     rcx, r12; hGlobal
0x1400269e8  call    cs:__imp_CreateStreamOnHGlobal
0x1400269ee  mov     r8, qword ptr [rbp+60h+String]
0x1400269f2  xor     edx, edx
0x1400269f4  mov     [rbp+60h+var_58], rdx
0x1400269f8  mov     [rsp+0A0h+var_80], rdx; __int64
0x1400269fd  lea     r9, [rbp+60h+var_58]
0x140026a01  mov     rdx, rdi
0x140026a04  mov     rcx, r13; psz
0x140026a07  call    AtlAxCreateControlEx
0x140026a0c  test    eax, eax
0x140026a0e  js      loc_140026AA7
0x140026a14  mov     rcx, [rbp+60h+var_58]
0x140026a18  mov     rax, [rcx]
0x140026a1b  lea     r8, [rbp+60h+dwNewLong]
0x140026a1f  lea     rdx, IID_IAxWinHostWindow
0x140026a26  mov     rax, [rax]
0x140026a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026a2e  test    eax, eax
0x140026a30  js      short loc_140026AA7
0x140026a32  mov     r8, [rbp+60h+dwNewLong]; dwNewLong
0x140026a36  mov     edx, 0FFFFFFEBh; nIndex
0x140026a3b  mov     rcx, rdi; hWnd
0x140026a3e  call    cs:__imp_SetWindowLongPtrW
0x140026a44  mov     edx, 5; uCmd
0x140026a49  mov     rcx, rdi; hWnd
0x140026a4c  call    cs:__imp_GetWindow
0x140026a52  test    rax, rax
0x140026a55  jz      short loc_140026A8F
0x140026a57  mov     edx, 0FFFFFFECh; nIndex
0x140026a5c  mov     rcx, rax; hWnd
0x140026a5f  call    cs:__imp_GetWindowLongW
0x140026a65  bt      eax, 10h
0x140026a69  jnb     short loc_140026A8F
0x140026a6b  mov     edx, 0FFFFFFECh; nIndex
0x140026a70  mov     rcx, rdi; hWnd
0x140026a73  call    cs:__imp_GetWindowLongW
0x140026a79  bts     eax, 10h
0x140026a7d  mov     r8d, eax; dwNewLong
0x140026a80  mov     edx, 0FFFFFFECh; nIndex
0x140026a85  mov     rcx, rdi; hWnd
0x140026a88  call    cs:__imp_SetWindowLongW
0x140026a8e  nop
0x140026a8f  lea     rcx, [rbp+60h+var_58]
0x140026a93  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140026a98  nop
0x140026a99  lea     rcx, [rbp+60h+String]
0x140026a9d  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140026aa2  jmp     loc_1400268BD
0x140026aa7  lea     rcx, [rbp+60h+var_58]
0x140026aab  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140026ab0  nop
0x140026ab1  lea     rcx, [rbp+60h+String]
0x140026ab5  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140026aba  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140026ac1  jmp     loc_1400268CE
```
