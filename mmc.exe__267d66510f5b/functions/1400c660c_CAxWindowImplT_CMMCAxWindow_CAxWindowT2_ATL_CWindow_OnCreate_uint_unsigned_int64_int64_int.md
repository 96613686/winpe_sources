# CAxWindowImplT<CMMCAxWindow,CAxWindowT2<ATL::CWindow>>::OnCreate(uint,unsigned __int64,__int64,int &)

- ea: `0x1400c660c`
- end: `0x1400c67ed`
- name: `?OnCreate@?$CAxWindowImplT@VCMMCAxWindow@@V?$CAxWindowT2@VCWindow@ATL@@@@@@QEAA_JI_K_JAEAH@Z`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002c070`

## callees

- `0x14003ce40`
- `0x140062396`
- `0x1400c6504`
- `0x1400c660c`
- `0x1400e9e10`
- `0x1400e9ed0`
- `0x1400f3010`

## import_xrefs

- `USER32!GetWindowTextW` at `0x1400c667e`
- `USER32!GetWindowTextW` at `0x1400c667e`
- `USER32!SetWindowLongPtrW` at `0x1400c6757`
- `USER32!SetWindowLongPtrW` at `0x1400c6757`
- `USER32!SetWindowLongW` at `0x1400c67a1`
- `USER32!SetWindowLongW` at `0x1400c67a1`
- `USER32!GetWindowLongW` at `0x1400c677b`
- `USER32!GetWindowLongW` at `0x1400c6790`
- `USER32!GetWindowLongW` at `0x1400c677b`
- `USER32!GetWindowLongW` at `0x1400c6790`
- `USER32!GetWindowTextLengthW` at `0x1400c6640`
- `USER32!GetWindowTextLengthW` at `0x1400c6640`
- `USER32!GetWindow` at `0x1400c6766`
- `USER32!GetWindow` at `0x1400c6766`
- `USER32!SetWindowTextW` at `0x1400c668f`
- `USER32!SetWindowTextW` at `0x1400c668f`
- `ole32!OleInitialize` at `0x1400c6636`
- `ole32!OleInitialize` at `0x1400c6636`
- `ole32!CreateStreamOnHGlobal` at `0x1400c6702`
- `ole32!CreateStreamOnHGlobal` at `0x1400c6702`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1400c66b9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1400c66b9`
- `KERNEL32!GlobalLock` at `0x1400c66d5`
- `KERNEL32!GlobalLock` at `0x1400c66d5`
- `KERNEL32!GlobalUnlock` at `0x1400c66f0`
- `KERNEL32!GlobalUnlock` at `0x1400c66f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAxWindowImplT<CMMCAxWindow,CAxWindowT2<ATL::CWindow>>::OnCreate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 **a4,
        _DWORD *a5)
{
  int v7; // r8d
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  unsigned int v13; // edi
  HGLOBAL v14; // rax
  void *v15; // r14
  struct IStream *v16; // r8
  void *v17; // rax
  HWND Window; // rax
  LONG WindowLongW; // eax
  __int64 v20; // rbx
  struct IUnknown **v22; // [rsp+20h] [rbp-20h]
  const struct _GUID *v23; // [rsp+28h] [rbp-18h]
  struct IUnknown *v24; // [rsp+30h] [rbp-10h]
  WCHAR String[4]; // [rsp+40h] [rbp+0h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp+8h] BYREF
  LONG_PTR dwNewLong; // [rsp+50h] [rbp+10h] BYREF

  OleInitialize(0);
  v7 = GetWindowTextLengthW(*(HWND *)(a1 + 8)) + 1;
  v8 = 2LL * v7;
  v9 = v8 + 15;
  if ( v8 + 15 < v8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  GetWindowTextW(*(HWND *)(a1 + 8), String, v7);
  SetWindowTextW(*(HWND *)(a1 + 8), &WindowName);
  dwNewLong = 0;
  v13 = 0;
  if ( a4 && *a4 )
    v13 = **a4;
  v14 = GlobalAlloc(0x42u, v13);
  v15 = v14;
  v16 = 0;
  ppstm = 0;
  if ( v14 && v13 )
  {
    v17 = GlobalLock(v14);
    memcpy_0(v17, *a4 + 1, v13);
    GlobalUnlock(v15);
    CreateStreamOnHGlobal(v15, 1, &ppstm);
    v16 = ppstm;
  }
  *(_QWORD *)String = 0;
  if ( (int)MMCAxCreateControlEx(String, *(HWND *)(a1 + 8), v16, (struct IUnknown **)String, v22, v23, v24) < 0
    || (***(int (__fastcall ****)(_QWORD, GUID *, LONG_PTR *))String)(
         *(_QWORD *)String,
         &IID_IAxWinHostWindow,
         &dwNewLong) < 0 )
  {
    v20 = -1;
  }
  else
  {
    SetWindowLongPtrW(*(HWND *)(a1 + 8), -21, dwNewLong);
    Window = GetWindow(*(HWND *)(a1 + 8), 5u);
    if ( Window && (GetWindowLongW(Window, -20) & 0x10000) != 0 )
    {
      WindowLongW = GetWindowLongW(*(HWND *)(a1 + 8), -20);
      SetWindowLongW(*(HWND *)(a1 + 8), -20, WindowLongW | 0x10000);
    }
    *a5 = 1;
    v20 = 0;
  }
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(String);
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&ppstm);
  return v20;
}

```

## disassembly

```asm
0x1400c660c  push    rbp
0x1400c660e  push    rbx
0x1400c660f  push    rsi
0x1400c6610  push    rdi
0x1400c6611  push    r12
0x1400c6613  push    r14
0x1400c6615  push    r15
0x1400c6617  sub     rsp, 60h
0x1400c661b  lea     rbp, [rsp+40h]
0x1400c6620  mov     rax, cs:__security_cookie
0x1400c6627  xor     rax, rbp
0x1400c662a  mov     [rbp+50h+var_38], rax
0x1400c662e  mov     rsi, r9
0x1400c6631  mov     rbx, rcx
0x1400c6634  xor     ecx, ecx; pvReserved
0x1400c6636  call    cs:__imp_OleInitialize
0x1400c663c  mov     rcx, [rbx+8]; hWnd
0x1400c6640  call    cs:__imp_GetWindowTextLengthW
0x1400c6646  lea     r8d, [rax+1]
0x1400c664a  movsxd  rax, r8d
0x1400c664d  add     rax, rax
0x1400c6650  lea     rcx, [rax+0Fh]
0x1400c6654  cmp     rcx, rax
0x1400c6657  ja      short loc_1400C6663
0x1400c6659  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1400c6663  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400c6667  mov     rax, rcx
0x1400c666a  call    _alloca_probe
0x1400c666f  sub     rsp, rcx
0x1400c6672  lea     r12, [rsp+90h+String]
0x1400c6677  mov     rdx, r12; lpString
0x1400c667a  mov     rcx, [rbx+8]; hWnd
0x1400c667e  call    cs:__imp_GetWindowTextW
0x1400c6684  lea     rdx, WindowName; lpString
0x1400c668b  mov     rcx, [rbx+8]; hWnd
0x1400c668f  call    cs:__imp_SetWindowTextW
0x1400c6695  mov     [rbp+50h+dwNewLong], 0
0x1400c669d  xor     edi, edi
0x1400c669f  test    rsi, rsi
0x1400c66a2  jz      short loc_1400C66AF
0x1400c66a4  mov     rax, [rsi]
0x1400c66a7  test    rax, rax
0x1400c66aa  jz      short loc_1400C66AF
0x1400c66ac  movzx   edi, word ptr [rax]
0x1400c66af  mov     r15d, edi
0x1400c66b2  mov     edx, edi; dwBytes
0x1400c66b4  mov     ecx, 42h ; 'B'; uFlags
0x1400c66b9  call    cs:__imp_GlobalAlloc
0x1400c66bf  mov     r14, rax
0x1400c66c2  xor     r8d, r8d
0x1400c66c5  mov     [rbp+50h+ppstm], r8
0x1400c66c9  test    rax, rax
0x1400c66cc  jz      short loc_1400C670C
0x1400c66ce  test    edi, edi
0x1400c66d0  jz      short loc_1400C670C
0x1400c66d2  mov     rcx, rax; hMem
0x1400c66d5  call    cs:__imp_GlobalLock
0x1400c66db  mov     rdx, [rsi]
0x1400c66de  add     rdx, 2; Src
0x1400c66e2  mov     r8d, r15d; Size
0x1400c66e5  mov     rcx, rax; void *
0x1400c66e8  call    memcpy_0
0x1400c66ed  mov     rcx, r14; hMem
0x1400c66f0  call    cs:__imp_GlobalUnlock
0x1400c66f6  lea     r8, [rbp+50h+ppstm]; ppstm
0x1400c66fa  mov     edx, 1; fDeleteOnRelease
0x1400c66ff  mov     rcx, r14; hGlobal
0x1400c6702  call    cs:__imp_CreateStreamOnHGlobal
0x1400c6708  mov     r8, [rbp+50h+ppstm]; struct IStream *
0x1400c670c  mov     qword ptr [rbp+50h+String], 0
0x1400c6714  lea     r9, [rbp+50h+String]; struct IUnknown **
0x1400c6718  mov     rdx, [rbx+8]; HWND
0x1400c671c  mov     rcx, r12; psz
0x1400c671f  call    ?MMCAxCreateControlEx@@YAJPEBGPEAUHWND__@@PEAUIStream@@PEAPEAUIUnknown@@3AEBU_GUID@@PEAU3@@Z; MMCAxCreateControlEx(ushort const *,HWND__ *,IStream *,IUnknown * *,IUnknown * *,_GUID const &,IUnknown *)
0x1400c6724  test    eax, eax
0x1400c6726  js      loc_1400C67B8
0x1400c672c  mov     rcx, qword ptr [rbp+50h+String]
0x1400c6730  mov     rax, [rcx]
0x1400c6733  lea     r8, [rbp+50h+dwNewLong]
0x1400c6737  lea     rdx, IID_IAxWinHostWindow
0x1400c673e  mov     rax, [rax]
0x1400c6741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c6746  test    eax, eax
0x1400c6748  js      short loc_1400C67B8
0x1400c674a  mov     r8, [rbp+50h+dwNewLong]; dwNewLong
0x1400c674e  mov     edx, 0FFFFFFEBh; nIndex
0x1400c6753  mov     rcx, [rbx+8]; hWnd
0x1400c6757  call    cs:__imp_SetWindowLongPtrW
0x1400c675d  mov     edx, 5; uCmd
0x1400c6762  mov     rcx, [rbx+8]; hWnd
0x1400c6766  call    cs:__imp_GetWindow
0x1400c676c  test    rax, rax
0x1400c676f  jz      short loc_1400C67A7
0x1400c6771  mov     edi, 0FFFFFFECh
0x1400c6776  mov     edx, edi; nIndex
0x1400c6778  mov     rcx, rax; hWnd
0x1400c677b  call    cs:__imp_GetWindowLongW
0x1400c6781  mov     esi, 10000h
0x1400c6786  test    esi, eax
0x1400c6788  jz      short loc_1400C67A7
0x1400c678a  mov     edx, edi; nIndex
0x1400c678c  mov     rcx, [rbx+8]; hWnd
0x1400c6790  call    cs:__imp_GetWindowLongW
0x1400c6796  or      eax, esi
0x1400c6798  mov     r8d, eax; dwNewLong
0x1400c679b  mov     edx, edi; nIndex
0x1400c679d  mov     rcx, [rbx+8]; hWnd
0x1400c67a1  call    cs:__imp_SetWindowLongW
0x1400c67a7  mov     rax, [rbp+50h+arg_20]
0x1400c67ae  mov     dword ptr [rax], 1
0x1400c67b4  xor     ebx, ebx
0x1400c67b6  jmp     short loc_1400C67BC
0x1400c67b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400c67bc  lea     rcx, [rbp+50h+String]
0x1400c67c0  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x1400c67c5  nop
0x1400c67c6  lea     rcx, [rbp+50h+ppstm]
0x1400c67ca  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x1400c67cf  mov     rax, rbx
0x1400c67d2  mov     rcx, [rbp+50h+var_38]
0x1400c67d6  xor     rcx, rbp; StackCookie
0x1400c67d9  call    __security_check_cookie
0x1400c67de  lea     rsp, [rbp+20h]
0x1400c67e2  pop     r15
0x1400c67e4  pop     r14
0x1400c67e6  pop     r12
0x1400c67e8  pop     rdi
0x1400c67e9  pop     rsi
0x1400c67ea  pop     rbx
0x1400c67eb  pop     rbp
0x1400c67ec  retn
```
