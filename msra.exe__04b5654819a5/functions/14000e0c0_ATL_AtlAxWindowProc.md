# ATL::AtlAxWindowProc

- ea: `0x14000e0c0`
- end: `0x14000e4ef`
- name: `ATL::AtlAxWindowProc`
- size: `1071`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400044f8`
- `0x14000e0c0`
- `0x140019004`
- `0x14004ad80`
- `0x14004ae40`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000e2a0`
- `KERNEL32!GlobalAlloc` at `0x14000e2a0`
- `KERNEL32!GlobalUnlock` at `0x14000e30e`
- `KERNEL32!GlobalUnlock` at `0x14000e30e`
- `KERNEL32!GlobalLock` at `0x14000e2bb`
- `KERNEL32!GlobalLock` at `0x14000e2bb`
- `USER32!DefWindowProcW` at `0x14000e4a4`
- `USER32!DefWindowProcW` at `0x14000e4a4`
- `USER32!SetWindowLongW` at `0x14000e155`
- `USER32!SetWindowLongW` at `0x14000e155`
- `USER32!GetWindowLongW` at `0x14000e121`
- `USER32!GetWindowLongW` at `0x14000e13f`
- `USER32!GetWindowLongW` at `0x14000e121`
- `USER32!GetWindowLongW` at `0x14000e13f`
- `USER32!GetWindowLongPtrW` at `0x14000e16b`
- `USER32!GetWindowLongPtrW` at `0x14000e16b`
- `USER32!SetWindowLongPtrW` at `0x14000e44a`
- `USER32!SetWindowLongPtrW` at `0x14000e44a`
- `USER32!GetWindowTextLengthW` at `0x14000e1b0`
- `USER32!GetWindowTextLengthW` at `0x14000e1b0`
- `USER32!GetWindowTextW` at `0x14000e248`
- `USER32!GetWindowTextW` at `0x14000e248`
- `USER32!SetWindowTextW` at `0x14000e25e`
- `USER32!SetWindowTextW` at `0x14000e25e`
- `msvcrt!malloc` at `0x14000e20e`
- `msvcrt!malloc` at `0x14000e20e`
- `msvcrt!free` at `0x14000e42d`
- `msvcrt!free` at `0x14000e48c`
- `msvcrt!free` at `0x14000e42d`
- `msvcrt!free` at `0x14000e48c`
- `msvcrt!memcpy_s` at `0x14000e2d7`
- `msvcrt!memcpy_s` at `0x14000e2d7`
- `ole32!CreateStreamOnHGlobal` at `0x14000e326`
- `ole32!CreateStreamOnHGlobal` at `0x14000e326`
- `ole32!OleUninitialize` at `0x14000e18e`
- `ole32!OleUninitialize` at `0x14000e18e`
- `ole32!OleInitialize` at `0x14000e1a1`
- `ole32!OleInitialize` at `0x14000e1a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LRESULT __fastcall ATL::AtlAxWindowProc(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  LONG WindowLongW; // eax
  LONG_PTR WindowLongPtrW; // rax
  int v10; // esi
  unsigned __int64 v11; // rax
  size_t v12; // rcx
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rbx
  WCHAR *v16; // rax
  int v18; // eax
  unsigned __int16 *v19; // rcx
  SIZE_T v20; // rsi
  HGLOBAL v21; // rax
  void *v22; // r14
  void *v23; // rax
  errno_t v24; // eax
  WCHAR *v25; // rcx
  bool v26; // zf
  __int64 v27; // [rsp+0h] [rbp-40h] BYREF
  WCHAR String[4]; // [rsp+40h] [rbp+0h] BYREF
  __int64 v29; // [rsp+48h] [rbp+8h]
  LONG_PTR dwNewLong[3]; // [rsp+50h] [rbp+10h] BYREF

  if ( Msg == 1 )
  {
    OleInitialize(0);
    v10 = GetWindowTextLengthW(hWnd) + 1;
    v11 = 2LL * v10;
    v12 = v11 + 16;
    if ( v11 + 16 < v11 )
    {
      v15 = 0;
    }
    else
    {
      if ( v12 > 0x400 )
      {
        v16 = (WCHAR *)malloc(v12);
        v15 = v16;
        if ( !v16 )
          goto LABEL_20;
        *(_DWORD *)v16 = 56797;
        goto LABEL_18;
      }
      v13 = v11 + 31;
      if ( v12 + 15 < v12 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
      v15 = String;
      if ( &v27 != (__int64 *)-64LL )
      {
        wcscpy(String, L"쳌");
LABEL_18:
        v15 += 8;
      }
    }
LABEL_20:
    dwNewLong[1] = (LONG_PTR)v15;
    if ( !v15 )
      return -1;
    GetWindowTextW(hWnd, v15, v10);
    SetWindowTextW(hWnd, &::String);
    dwNewLong[0] = 0;
    v18 = 0;
    if ( lParam && (v19 = *(unsigned __int16 **)lParam) != 0 )
    {
      v18 = *v19;
      v20 = *v19;
    }
    else
    {
      v20 = 0;
    }
    *(_QWORD *)String = 0;
    if ( v18 )
    {
      v21 = GlobalAlloc(0x42u, v20);
      v22 = v21;
      if ( !v21 )
      {
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
        v25 = v15 - 8;
        v26 = *((_DWORD *)v15 - 4) == 56797;
LABEL_49:
        if ( v26 )
          free(v25);
        return -1;
      }
      v23 = GlobalLock(v21);
      v24 = memcpy_s(v23, v20, (const void *const)(*(_QWORD *)lParam + 2LL), v20);
      if ( v24 )
      {
        if ( v24 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v24 == 22 || v24 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v24 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      GlobalUnlock(v22);
      CreateStreamOnHGlobal(v22, 1, (LPSTREAM *)String);
    }
    dwNewLong[2] = 0;
    v29 = 0;
    if ( (int)AtlAxCreateControlLicEx(v15, 0, (__int64)&GUID_NULL, 0, 0) >= 0 )
    {
      if ( (**(int (__fastcall ***)(__int64, GUID *, LONG_PTR *))v29)(
             v29,
             &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e,
             dwNewLong) >= 0 )
      {
        SetWindowLongPtrW(hWnd, -21, dwNewLong[0]);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
        if ( *((_DWORD *)v15 - 4) == 56797 )
          free(v15 - 8);
        return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
      }
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
    }
    else
    {
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
    }
    v25 = v15 - 8;
    v26 = *((_DWORD *)v15 - 4) == 56797;
    goto LABEL_49;
  }
  if ( Msg == 130 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
    if ( WindowLongPtrW )
      (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
    OleUninitialize();
  }
  else if ( Msg == 528 && (_DWORD)wParam == 1 && (GetWindowLongW(lParam, -20) & 0x10000) != 0 )
  {
    WindowLongW = GetWindowLongW(hWnd, -20);
    SetWindowLongW(hWnd, -20, WindowLongW | 0x10000);
  }
  return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x14000e0c0  push    rbp
0x14000e0c2  push    rbx
0x14000e0c3  push    rsi
0x14000e0c4  push    rdi
0x14000e0c5  push    r12
0x14000e0c7  push    r13
0x14000e0c9  push    r14
0x14000e0cb  push    r15
0x14000e0cd  sub     rsp, 78h
0x14000e0d1  lea     rbp, [rsp+40h]
0x14000e0d6  mov     rax, cs:__security_cookie
0x14000e0dd  xor     rax, rbp
0x14000e0e0  mov     [rbp+70h+var_48], rax
0x14000e0e4  mov     r15, r9
0x14000e0e7  mov     r12, r8
0x14000e0ea  mov     r13d, edx
0x14000e0ed  mov     rdi, rcx
0x14000e0f0  mov     eax, edx
0x14000e0f2  sub     eax, 1
0x14000e0f5  jz      loc_14000E19F
0x14000e0fb  sub     eax, 81h
0x14000e100  jz      short loc_14000E166
0x14000e102  cmp     eax, 18Eh
0x14000e107  jnz     loc_14000E498
0x14000e10d  cmp     r12d, 1
0x14000e111  jnz     loc_14000E498
0x14000e117  lea     ebx, [r12-15h]
0x14000e11c  mov     edx, ebx; nIndex
0x14000e11e  mov     rcx, r9; hWnd
0x14000e121  call    cs:__imp_GetWindowLongW
0x14000e128  nop     dword ptr [rax+rax+00h]
0x14000e12d  mov     esi, 10000h
0x14000e132  test    esi, eax
0x14000e134  jz      loc_14000E498
0x14000e13a  mov     edx, ebx; nIndex
0x14000e13c  mov     rcx, rdi; hWnd
0x14000e13f  call    cs:__imp_GetWindowLongW
0x14000e146  nop     dword ptr [rax+rax+00h]
0x14000e14b  or      eax, esi
0x14000e14d  mov     r8d, eax; dwNewLong
0x14000e150  mov     edx, ebx; nIndex
0x14000e152  mov     rcx, rdi; hWnd
0x14000e155  call    cs:__imp_SetWindowLongW
0x14000e15c  nop     dword ptr [rax+rax+00h]
0x14000e161  jmp     loc_14000E498
0x14000e166  mov     edx, 0FFFFFFEBh; nIndex
0x14000e16b  call    cs:__imp_GetWindowLongPtrW
0x14000e172  nop     dword ptr [rax+rax+00h]
0x14000e177  mov     rdx, rax
0x14000e17a  test    rax, rax
0x14000e17d  jz      short loc_14000E18E
0x14000e17f  mov     rcx, [rax]
0x14000e182  mov     rax, [rcx+10h]
0x14000e186  mov     rcx, rdx
0x14000e189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e18e  call    cs:__imp_OleUninitialize
0x14000e195  nop     dword ptr [rax+rax+00h]
0x14000e19a  jmp     loc_14000E498
0x14000e19f  xor     ecx, ecx; pvReserved
0x14000e1a1  call    cs:__imp_OleInitialize
0x14000e1a8  nop     dword ptr [rax+rax+00h]
0x14000e1ad  mov     rcx, rdi; hWnd
0x14000e1b0  call    cs:__imp_GetWindowTextLengthW
0x14000e1b7  nop     dword ptr [rax+rax+00h]
0x14000e1bc  lea     esi, [rax+1]
0x14000e1bf  movsxd  rax, esi
0x14000e1c2  add     rax, rax
0x14000e1c5  lea     rcx, [rax+10h]; Size
0x14000e1c9  mov     r14d, 0DDDDh
0x14000e1cf  cmp     rcx, rax
0x14000e1d2  jbe     short loc_14000E22B
0x14000e1d4  cmp     rcx, 400h
0x14000e1db  ja      short loc_14000E20E
0x14000e1dd  lea     rax, [rcx+0Fh]
0x14000e1e1  cmp     rax, rcx
0x14000e1e4  ja      short loc_14000E1F0
0x14000e1e6  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000e1f0  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000e1f4  call    _alloca_probe
0x14000e1f9  sub     rsp, rax
0x14000e1fc  lea     rbx, [rsp+0B0h+String]
0x14000e201  test    rbx, rbx
0x14000e204  jz      short loc_14000E22D
0x14000e206  mov     dword ptr [rbx], 0CCCCh
0x14000e20c  jmp     short loc_14000E225
0x14000e20e  call    cs:__imp_malloc
0x14000e215  nop     dword ptr [rax+rax+00h]
0x14000e21a  mov     rbx, rax
0x14000e21d  test    rax, rax
0x14000e220  jz      short loc_14000E22D
0x14000e222  mov     [rax], r14d
0x14000e225  add     rbx, 10h
0x14000e229  jmp     short loc_14000E22D
0x14000e22b  xor     ebx, ebx
0x14000e22d  mov     [rbp+70h+var_58], rbx
0x14000e231  test    rbx, rbx
0x14000e234  jnz     short loc_14000E23F
0x14000e236  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e23a  jmp     loc_14000E4B0
0x14000e23f  mov     r8d, esi; nMaxCount
0x14000e242  mov     rdx, rbx; lpString
0x14000e245  mov     rcx, rdi; hWnd
0x14000e248  call    cs:__imp_GetWindowTextW
0x14000e24f  nop     dword ptr [rax+rax+00h]
0x14000e254  lea     rdx, String; lpString
0x14000e25b  mov     rcx, rdi; hWnd
0x14000e25e  call    cs:__imp_SetWindowTextW
0x14000e265  nop     dword ptr [rax+rax+00h]
0x14000e26a  mov     [rbp+70h+dwNewLong], 0
0x14000e272  xor     eax, eax
0x14000e274  test    r15, r15
0x14000e277  jz      short loc_14000E288
0x14000e279  mov     rcx, [r15]
0x14000e27c  test    rcx, rcx
0x14000e27f  jz      short loc_14000E288
0x14000e281  movzx   eax, word ptr [rcx]
0x14000e284  mov     esi, eax
0x14000e286  jmp     short loc_14000E28A
0x14000e288  xor     esi, esi
0x14000e28a  xor     r8d, r8d
0x14000e28d  mov     qword ptr [rbp+70h+String], r8
0x14000e291  test    eax, eax
0x14000e293  jz      loc_14000E33C
0x14000e299  mov     rdx, rsi; dwBytes
0x14000e29c  lea     ecx, [r8+42h]; uFlags
0x14000e2a0  call    cs:__imp_GlobalAlloc
0x14000e2a7  nop     dword ptr [rax+rax+00h]
0x14000e2ac  mov     r14, rax
0x14000e2af  test    rax, rax
0x14000e2b2  jz      loc_14000E3B4
0x14000e2b8  mov     rcx, rax; hMem
0x14000e2bb  call    cs:__imp_GlobalLock
0x14000e2c2  nop     dword ptr [rax+rax+00h]
0x14000e2c7  mov     r8, [r15]
0x14000e2ca  add     r8, 2; Source
0x14000e2ce  mov     r9, rsi; SourceSize
0x14000e2d1  mov     rdx, rsi; DestinationSize
0x14000e2d4  mov     rcx, rax; Destination
0x14000e2d7  call    cs:__imp_memcpy_s
0x14000e2de  nop     dword ptr [rax+rax+00h]
0x14000e2e3  test    eax, eax
0x14000e2e5  jz      short loc_14000E30B
0x14000e2e7  cmp     eax, 0Ch
0x14000e2ea  jz      loc_14000E4CE
0x14000e2f0  cmp     eax, 16h
0x14000e2f3  jz      loc_14000E4E4
0x14000e2f9  cmp     eax, 22h ; '"'
0x14000e2fc  jz      loc_14000E4E4
0x14000e302  cmp     eax, 50h ; 'P'
0x14000e305  jnz     loc_14000E4D9
0x14000e30b  mov     rcx, r14; hMem
0x14000e30e  call    cs:__imp_GlobalUnlock
0x14000e315  nop     dword ptr [rax+rax+00h]
0x14000e31a  lea     r8, [rbp+70h+String]; ppstm
0x14000e31e  mov     edx, 1; fDeleteOnRelease
0x14000e323  mov     rcx, r14; hGlobal
0x14000e326  call    cs:__imp_CreateStreamOnHGlobal
0x14000e32d  nop     dword ptr [rax+rax+00h]
0x14000e332  mov     r8, qword ptr [rbp+70h+String]
0x14000e336  mov     r14d, 0DDDDh
0x14000e33c  mov     [rbp+70h+var_50], 0
0x14000e344  mov     [rbp+70h+var_68], 0
0x14000e34c  mov     [rsp+0B0h+var_78], 0; __int64
0x14000e355  mov     [rsp+0B0h+var_80], 0; __int64
0x14000e35e  lea     rax, GUID_NULL
0x14000e365  mov     [rsp+0B0h+var_88], rax; __int64
0x14000e36a  mov     [rsp+0B0h+var_90], 0; __int64
0x14000e373  lea     r9, [rbp+70h+var_68]
0x14000e377  mov     rdx, rdi
0x14000e37a  mov     rcx, rbx; psz
0x14000e37d  call    AtlAxCreateControlLicEx
0x14000e382  test    eax, eax
0x14000e384  jns     short loc_14000E3D6
0x14000e386  mov     rcx, [rbp+70h+var_68]
0x14000e38a  test    rcx, rcx
0x14000e38d  jz      short loc_14000E39C
0x14000e38f  mov     rax, [rcx]
0x14000e392  mov     rax, [rax+10h]
0x14000e396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e39b  nop
0x14000e39c  mov     rcx, qword ptr [rbp+70h+String]
0x14000e3a0  test    rcx, rcx
0x14000e3a3  jz      short loc_14000E3B2
0x14000e3a5  mov     rax, [rcx]
0x14000e3a8  mov     rax, [rax+10h]
0x14000e3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3b1  nop
0x14000e3b2  jmp     short loc_14000E420
0x14000e3b4  mov     rcx, qword ptr [rbp+70h+String]
0x14000e3b8  test    rcx, rcx
0x14000e3bb  jz      short loc_14000E3CA
0x14000e3bd  mov     rax, [rcx]
0x14000e3c0  mov     rax, [rax+10h]
0x14000e3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3c9  nop
0x14000e3ca  lea     rcx, [rbx-10h]
0x14000e3ce  cmp     dword ptr [rcx], 0DDDDh
0x14000e3d4  jmp     short loc_14000E427
0x14000e3d6  mov     rcx, [rbp+70h+var_68]
0x14000e3da  mov     rax, [rcx]
0x14000e3dd  lea     r8, [rbp+70h+dwNewLong]
0x14000e3e1  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x14000e3e8  mov     rax, [rax]
0x14000e3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3f0  test    eax, eax
0x14000e3f2  jns     short loc_14000E43E
0x14000e3f4  mov     rcx, [rbp+70h+var_68]
0x14000e3f8  test    rcx, rcx
0x14000e3fb  jz      short loc_14000E40A
0x14000e3fd  mov     rax, [rcx]
0x14000e400  mov     rax, [rax+10h]
0x14000e404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e409  nop
0x14000e40a  mov     rcx, qword ptr [rbp+70h+String]
0x14000e40e  test    rcx, rcx
0x14000e411  jz      short loc_14000E420
0x14000e413  mov     rax, [rcx]
0x14000e416  mov     rax, [rax+10h]
0x14000e41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e41f  nop
0x14000e420  lea     rcx, [rbx-10h]; Block
0x14000e424  cmp     [rcx], r14d
0x14000e427  jnz     loc_14000E236
0x14000e42d  call    cs:__imp_free
0x14000e434  nop     dword ptr [rax+rax+00h]
0x14000e439  jmp     loc_14000E236
0x14000e43e  mov     r8, [rbp+70h+dwNewLong]; dwNewLong
0x14000e442  mov     edx, 0FFFFFFEBh; nIndex
0x14000e447  mov     rcx, rdi; hWnd
0x14000e44a  call    cs:__imp_SetWindowLongPtrW
0x14000e451  nop     dword ptr [rax+rax+00h]
0x14000e456  nop
0x14000e457  mov     rcx, [rbp+70h+var_68]
0x14000e45b  test    rcx, rcx
0x14000e45e  jz      short loc_14000E46D
0x14000e460  mov     rax, [rcx]
0x14000e463  mov     rax, [rax+10h]
0x14000e467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e46c  nop
0x14000e46d  mov     rcx, qword ptr [rbp+70h+String]
0x14000e471  test    rcx, rcx
0x14000e474  jz      short loc_14000E483
0x14000e476  mov     rax, [rcx]
0x14000e479  mov     rax, [rax+10h]
0x14000e47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e482  nop
0x14000e483  lea     rcx, [rbx-10h]; Block
0x14000e487  cmp     [rcx], r14d
0x14000e48a  jnz     short loc_14000E498
0x14000e48c  call    cs:__imp_free
0x14000e493  nop     dword ptr [rax+rax+00h]
0x14000e498  mov     r9, r15; lParam
0x14000e49b  mov     r8, r12; wParam
0x14000e49e  mov     edx, r13d; Msg
0x14000e4a1  mov     rcx, rdi; hWnd
0x14000e4a4  call    cs:__imp_DefWindowProcW
0x14000e4ab  nop     dword ptr [rax+rax+00h]
0x14000e4b0  mov     rcx, [rbp+70h+var_48]
0x14000e4b4  xor     rcx, rbp; StackCookie
0x14000e4b7  call    __security_check_cookie
0x14000e4bc  lea     rsp, [rbp+38h]
0x14000e4c0  pop     r15
0x14000e4c2  pop     r14
0x14000e4c4  pop     r13
0x14000e4c6  pop     r12
0x14000e4c8  pop     rdi
0x14000e4c9  pop     rsi
0x14000e4ca  pop     rbx
0x14000e4cb  pop     rbp
0x14000e4cc  retn
0x14000e4ce  mov     ecx, 8007000Eh; int
0x14000e4d3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000e4d9  mov     ecx, 80004005h; int
0x14000e4de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000e4e4  mov     ecx, 80070057h; int
0x14000e4e9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
