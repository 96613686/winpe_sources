# ATL::CAxHostWindow::CreateControlLicEx(ushort const *,HWND__ *,IStream *,IUnknown * *,_GUID const &,IUnknown *,ushort *)

- ea: `0x14000f180`
- end: `0x14000f737`
- name: `?CreateControlLicEx@CAxHostWindow@ATL@@UEAAJPEBGPEAUHWND__@@PEAUIStream@@PEAPEAUIUnknown@@AEBU_GUID@@PEAU5@PEAG@Z`
- size: `1463`
- prototype: `int(ATL::CAxHostWindow *__hidden this, const unsigned __int16 *, HWND, struct IStream *, struct IUnknown **, const struct _GUID *, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x1400044f8`
- `0x14000c880`
- `0x14000db40`
- `0x14000f180`
- `0x14000fa80`
- `0x14001665c`
- `0x140016974`
- `0x140017e5c`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000f475`
- `KERNEL32!GlobalAlloc` at `0x14000f475`
- `KERNEL32!GlobalUnlock` at `0x14000f4e9`
- `KERNEL32!GlobalUnlock` at `0x14000f4e9`
- `KERNEL32!GlobalLock` at `0x14000f496`
- `KERNEL32!GlobalLock` at `0x14000f496`
- `KERNEL32!lstrcmpW` at `0x14000f28a`
- `KERNEL32!lstrcmpW` at `0x14000f28a`
- `USER32!SetWindowLongW` at `0x14000f386`
- `USER32!SetWindowLongW` at `0x14000f386`
- `USER32!GetWindowLongW` at `0x14000f342`
- `USER32!GetWindowLongW` at `0x14000f36b`
- `USER32!GetWindowLongW` at `0x14000f342`
- `USER32!GetWindowLongW` at `0x14000f36b`
- `USER32!IsWindow` at `0x14000f21c`
- `USER32!IsWindow` at `0x14000f21c`
- `USER32!GetClassNameW` at `0x14000f26f`
- `USER32!GetClassNameW` at `0x14000f26f`
- `USER32!GetSysColor` at `0x14000f2a3`
- `USER32!GetSysColor` at `0x14000f2a3`
- `USER32!SetWindowPos` at `0x14000f3b0`
- `USER32!SetWindowPos` at `0x14000f3b0`
- `USER32!RedrawWindow` at `0x14000f205`
- `USER32!RedrawWindow` at `0x14000f6bc`
- `USER32!RedrawWindow` at `0x14000f205`
- `USER32!RedrawWindow` at `0x14000f6bc`
- `USER32!GetParent` at `0x14000f258`
- `USER32!GetParent` at `0x14000f258`
- `msvcrt!memcpy_s` at `0x14000f4af`
- `msvcrt!memcpy_s` at `0x14000f4af`
- `ole32!CreateStreamOnHGlobal` at `0x14000f501`
- `ole32!CreateStreamOnHGlobal` at `0x14000f501`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f5e1`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f5e1`
- `OLEAUT32!__imp_VariantInit` at `0x14000f5b8`
- `OLEAUT32!__imp_VariantInit` at `0x14000f5b8`
- `OLEAUT32!__imp_VariantClear` at `0x14000f5cd`
- `OLEAUT32!__imp_VariantClear` at `0x14000f64f`
- `OLEAUT32!__imp_VariantClear` at `0x14000f65f`
- `OLEAUT32!__imp_VariantClear` at `0x14000f5cd`
- `OLEAUT32!__imp_VariantClear` at `0x14000f64f`
- `OLEAUT32!__imp_VariantClear` at `0x14000f65f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAxHostWindow::CreateControlLicEx(
        ATL::CAxHostWindow *this,
        const unsigned __int16 *a2,
        HWND a3,
        struct IStream *a4,
        struct IUnknown **a5,
        const struct _GUID *a6,
        struct IUnknown *a7,
        unsigned __int16 *a8)
{
  int v12; // ebx
  ATL::CAxHostWindow *v13; // r12
  HWND v14; // rcx
  __int64 v15; // rdx
  HWND Parent; // rax
  int v17; // eax
  int v18; // ecx
  LONG WindowLongW; // eax
  LPVOID v20; // rsi
  __int64 v21; // rdx
  unsigned int v22; // r15d
  HGLOBAL v23; // rbx
  void *v24; // rax
  errno_t v25; // eax
  struct IStream *v26; // rcx
  HWND v27; // rcx
  char v28; // [rsp+40h] [rbp-51h] BYREF
  char v29; // [rsp+41h] [rbp-50h]
  struct IStream *v30; // [rsp+48h] [rbp-49h] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-39h] BYREF
  VARIANTARG ClassName; // [rsp+70h] [rbp-21h] BYREF

  v30 = a4;
  ppstm = (LPSTREAM)a8;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  v12 = 1;
  v13 = (ATL::CAxHostWindow *)((char *)this - 72);
  ATL::CAxHostWindow::ReleaseAll((ATL::CAxHostWindow *)((char *)this - 72));
  v14 = (HWND)*((_QWORD *)this - 8);
  if ( v14 && v14 != a3 )
  {
    RedrawWindow(v14, 0, 0, 0x507u);
    ATL::CAxHostWindow::ReleaseWindow(v13);
  }
  if ( IsWindow(a3) )
  {
    v29 = 0;
    if ( *((HWND *)this - 8) != a3 )
    {
      ATL::CAxHostWindow::SubclassWindow((size_t)v13, a3);
      v29 = 1;
    }
    if ( !*((_DWORD *)this + 67) )
    {
      Parent = GetParent(*((HWND *)this - 8));
      if ( !GetClassNameW(Parent, &ClassName.vt, 8) || (v17 = lstrcmpW(&ClassName.vt, L"#32770"), v18 = 15, v17) )
        v18 = 5;
      *((_DWORD *)this + 67) = GetSysColor(v18);
    }
    v28 = 0;
    v12 = ATL::CreateNormalizedObject(a2, v15, (LPVOID *)a5, &v28, (BSTR)ppstm);
    if ( v12 >= 0 )
      v12 = ATL::CAxHostWindow::ActivateAx(v13, *a5, 0, v30);
    *(struct _GUID *)((char *)this + 184) = *a6;
    if ( v12 < 0 )
      goto LABEL_60;
    if ( *a5 && a7 )
      ATL::AtlAdvise(*a5, a7, (const struct _GUID *)((char *)this + 184), (unsigned int *)this + 51);
    if ( v28 && *a5 )
    {
      if ( (GetWindowLongW(*((HWND *)this - 8), -16) & 0x300000) != 0 )
      {
        WindowLongW = GetWindowLongW(*((HWND *)this - 8), -16);
        SetWindowLongW(*((HWND *)this - 8), -16, WindowLongW & 0xFFCFFFFF);
        SetWindowPos(*((HWND *)this - 8), 0, 0, 0, 0, 0, 0x37u);
      }
      else
      {
        *((_DWORD *)this + 74) |= 8u;
      }
      v20 = *a5;
      if ( *a5 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 8LL))(v20);
      if ( ((*a2 - 77) & 0xFFDF) != 0
        || ((a2[1] - 83) & 0xFFDF) != 0
        || ((a2[2] - 72) & 0xFFDF) != 0
        || ((a2[3] - 84) & 0xFFDF) != 0
        || ((a2[4] - 77) & 0xFFDF) != 0
        || ((a2[5] - 76) & 0xFFDF) != 0
        || a2[6] != 58 )
      {
        v30 = 0;
        (**(void (__fastcall ***)(LPVOID, GUID *, struct IStream **))v20)(
          v20,
          &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
          &v30);
        v26 = v30;
        if ( v30 )
        {
          VariantInit(&pvarg);
          ClassName.vt = 0;
          VariantClear(&ClassName);
          ClassName.vt = 8;
          ClassName.llVal = (LONGLONG)SysAllocString(a2);
          if ( !ClassName.llVal )
          {
            ClassName.vt = 10;
            ClassName.lVal = -2147024882;
            ATL::AtlThrowImpl(-2147024882);
          }
          (*(void (__fastcall **)(struct IStream *, __int64))(*(_QWORD *)v30 + 328LL))(v30, -1);
          (*(void (__fastcall **)(struct IStream *, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v30 + 416LL))(
            v30,
            &ClassName,
            &pvarg,
            &pvarg,
            &pvarg,
            &pvarg);
          VariantClear(&ClassName);
          VariantClear(&pvarg);
          v26 = v30;
        }
        if ( v26 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      else
      {
        v21 = -1;
        do
          ++v21;
        while ( a2[v21] );
        v22 = 2 * v21 - 14;
        v23 = GlobalAlloc(0x42u, v22);
        if ( v23 )
        {
          ppstm = 0;
          v24 = GlobalLock(v23);
          v25 = memcpy_s(v24, v22, a2 + 7, v22);
          if ( v25 )
          {
            if ( v25 == 12 )
              ATL::AtlThrowImpl(-2147024882);
            if ( v25 == 22 || v25 == 34 )
              ATL::AtlThrowImpl(-2147024809);
            if ( v25 != 80 )
              ATL::AtlThrowImpl(-2147467259);
          }
          GlobalUnlock(v23);
          v12 = CreateStreamOnHGlobal(v23, 1, &ppstm);
          if ( v12 >= 0 )
          {
            v30 = 0;
            v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IStream **))v20)(
                    v20,
                    &GUID_7fd52380_4e07_101b_ae2d_08002b2ec713,
                    &v30);
            if ( v12 >= 0 )
              v12 = (*(__int64 (__fastcall **)(struct IStream *, LPSTREAM))(*(_QWORD *)v30 + 40LL))(v30, ppstm);
            if ( v30 )
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v30 + 16LL))(v30);
          }
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        }
        else
        {
          v12 = -2147024882;
        }
      }
      if ( v20 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v12 < 0 )
        goto LABEL_60;
    }
    if ( !*((_QWORD *)this + 15) )
    {
LABEL_60:
      ATL::CAxHostWindow::ReleaseAll(v13);
      v27 = (HWND)*((_QWORD *)this - 8);
      if ( v27 )
      {
        RedrawWindow(v27, 0, 0, 0x507u);
        if ( v12 < 0 )
        {
          if ( v29 )
            ATL::CAxHostWindow::ReleaseWindow(v13);
        }
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000f180  push    rbp
0x14000f182  push    rbx
0x14000f183  push    rsi
0x14000f184  push    rdi
0x14000f185  push    r12
0x14000f187  push    r13
0x14000f189  push    r14
0x14000f18b  push    r15
0x14000f18d  lea     rbp, [rsp-7]
0x14000f192  sub     rsp, 98h
0x14000f199  mov     rax, cs:__security_cookie
0x14000f1a0  xor     rax, rsp
0x14000f1a3  mov     [rbp+3Fh+var_48], rax
0x14000f1a7  mov     [rbp+3Fh+var_88], r9
0x14000f1ab  mov     r15, r8
0x14000f1ae  mov     r14, rdx
0x14000f1b1  mov     rdi, rcx
0x14000f1b4  mov     rsi, [rbp+3Fh+arg_20]
0x14000f1b8  mov     r13, [rbp+3Fh+arg_30]
0x14000f1bc  mov     rax, [rbp+3Fh+arg_38]
0x14000f1c3  mov     [rbp+3Fh+ppstm], rax
0x14000f1c7  xor     eax, eax
0x14000f1c9  test    rsi, rsi
0x14000f1cc  jnz     short loc_14000F1D8
0x14000f1ce  mov     eax, 80004003h
0x14000f1d3  jmp     loc_14000F6DC
0x14000f1d8  mov     [rsi], rax
0x14000f1db  mov     ebx, 1
0x14000f1e0  lea     r12, [rcx-48h]
0x14000f1e4  mov     rcx, r12; this
0x14000f1e7  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x14000f1ec  mov     rcx, [rdi-40h]; hWnd
0x14000f1f0  test    rcx, rcx
0x14000f1f3  jz      short loc_14000F219
0x14000f1f5  cmp     rcx, r15
0x14000f1f8  jz      short loc_14000F219
0x14000f1fa  mov     r9d, 507h; flags
0x14000f200  xor     r8d, r8d; hrgnUpdate
0x14000f203  xor     edx, edx; lprcUpdate
0x14000f205  call    cs:__imp_RedrawWindow
0x14000f20c  nop     dword ptr [rax+rax+00h]
0x14000f211  mov     rcx, r12; this
0x14000f214  call    ?ReleaseWindow@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseWindow(void)
0x14000f219  mov     rcx, r15; hWnd
0x14000f21c  call    cs:__imp_IsWindow
0x14000f223  nop     dword ptr [rax+rax+00h]
0x14000f228  test    eax, eax
0x14000f22a  jz      loc_14000F6DA
0x14000f230  mov     [rbp+3Fh+var_8F], 0
0x14000f234  cmp     [rdi-40h], r15
0x14000f238  jz      short loc_14000F248
0x14000f23a  mov     rdx, r15; hWnd
0x14000f23d  mov     rcx, r12; FirstParameter
0x14000f240  call    ?SubclassWindow@CAxHostWindow@ATL@@QEAAXPEAUHWND__@@@Z; ATL::CAxHostWindow::SubclassWindow(HWND__ *)
0x14000f245  mov     [rbp+3Fh+var_8F], bl
0x14000f248  xor     r15d, r15d
0x14000f24b  cmp     [rdi+10Ch], r15d
0x14000f252  jnz     short loc_14000F2B5
0x14000f254  mov     rcx, [rdi-40h]; hWnd
0x14000f258  call    cs:__imp_GetParent
0x14000f25f  nop     dword ptr [rax+rax+00h]
0x14000f264  lea     r8d, [r15+8]; nMaxCount
0x14000f268  lea     rdx, [rbp+3Fh+ClassName]; lpClassName
0x14000f26c  mov     rcx, rax; hWnd
0x14000f26f  call    cs:__imp_GetClassNameW
0x14000f276  nop     dword ptr [rax+rax+00h]
0x14000f27b  test    eax, eax
0x14000f27d  jz      short loc_14000F29E
0x14000f27f  lea     rdx, String2; "#32770"
0x14000f286  lea     rcx, [rbp+3Fh+ClassName]; lpString1
0x14000f28a  call    cs:__imp_lstrcmpW
0x14000f291  nop     dword ptr [rax+rax+00h]
0x14000f296  test    eax, eax
0x14000f298  lea     ecx, [r15+0Fh]
0x14000f29c  jz      short loc_14000F2A3
0x14000f29e  mov     ecx, 5; nIndex
0x14000f2a3  call    cs:__imp_GetSysColor
0x14000f2aa  nop     dword ptr [rax+rax+00h]
0x14000f2af  mov     [rdi+10Ch], eax
0x14000f2b5  mov     [rbp+3Fh+var_90], r15b
0x14000f2b9  mov     rax, [rbp+3Fh+ppstm]
0x14000f2bd  mov     [rsp+0D0h+pbstr], rax; pbstr
0x14000f2c2  lea     r9, [rbp+3Fh+var_90]
0x14000f2c6  mov     r8, rsi
0x14000f2c9  mov     rcx, r14; lpsz
0x14000f2cc  call    ATL__CreateNormalizedObject
0x14000f2d1  mov     ebx, eax
0x14000f2d3  test    eax, eax
0x14000f2d5  js      short loc_14000F2EB
0x14000f2d7  mov     r9, [rbp+3Fh+var_88]; struct IStream *
0x14000f2db  xor     r8d, r8d; bool
0x14000f2de  mov     rdx, [rsi]; struct IUnknown *
0x14000f2e1  mov     rcx, r12; this
0x14000f2e4  call    ?ActivateAx@CAxHostWindow@ATL@@QEAAJPEAUIUnknown@@_NPEAUIStream@@@Z; ATL::CAxHostWindow::ActivateAx(IUnknown *,bool,IStream *)
0x14000f2e9  mov     ebx, eax
0x14000f2eb  lea     r8, [rdi+0B8h]; struct _GUID *
0x14000f2f2  mov     rax, [rbp+3Fh+arg_28]
0x14000f2f6  movups  xmm0, xmmword ptr [rax]
0x14000f2f9  movdqu  xmmword ptr [r8], xmm0
0x14000f2fe  test    ebx, ebx
0x14000f300  js      loc_14000F6A0
0x14000f306  mov     rcx, [rsi]; struct IUnknown *
0x14000f309  test    rcx, rcx
0x14000f30c  jz      short loc_14000F322
0x14000f30e  test    r13, r13
0x14000f311  jz      short loc_14000F322
0x14000f313  lea     r9, [rdi+0CCh]; unsigned int *
0x14000f31a  mov     rdx, r13; struct IUnknown *
0x14000f31d  call    ?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x14000f322  cmp     [rbp+3Fh+var_90], r15b
0x14000f326  jz      loc_14000F69A
0x14000f32c  cmp     [rsi], r15
0x14000f32f  jz      loc_14000F69A
0x14000f335  mov     r13d, 0FFFFFFF0h
0x14000f33b  mov     edx, r13d; nIndex
0x14000f33e  mov     rcx, [rdi-40h]; hWnd
0x14000f342  call    cs:__imp_GetWindowLongW
0x14000f349  nop     dword ptr [rax+rax+00h]
0x14000f34e  test    eax, 300000h
0x14000f353  jnz     short loc_14000F364
0x14000f355  mov     r13d, 8
0x14000f35b  or      [rdi+128h], r13d
0x14000f362  jmp     short loc_14000F3C2
0x14000f364  mov     edx, r13d; nIndex
0x14000f367  mov     rcx, [rdi-40h]; hWnd
0x14000f36b  call    cs:__imp_GetWindowLongW
0x14000f372  nop     dword ptr [rax+rax+00h]
0x14000f377  and     eax, 0FFCFFFFFh
0x14000f37c  mov     r8d, eax; dwNewLong
0x14000f37f  mov     edx, r13d; nIndex
0x14000f382  mov     rcx, [rdi-40h]; hWnd
0x14000f386  call    cs:__imp_SetWindowLongW
0x14000f38d  nop     dword ptr [rax+rax+00h]
0x14000f392  mov     [rsp+0D0h+uFlags], 37h ; '7'; uFlags
0x14000f39a  mov     [rsp+0D0h+cy], r15d; cy
0x14000f39f  mov     dword ptr [rsp+0D0h+pbstr], r15d; cx
0x14000f3a4  xor     r9d, r9d; Y
0x14000f3a7  xor     r8d, r8d; X
0x14000f3aa  xor     edx, edx; hWndInsertAfter
0x14000f3ac  mov     rcx, [rdi-40h]; hWnd
0x14000f3b0  call    cs:__imp_SetWindowPos
0x14000f3b7  nop     dword ptr [rax+rax+00h]
0x14000f3bc  mov     r13d, 8
0x14000f3c2  mov     rsi, [rsi]
0x14000f3c5  test    rsi, rsi
0x14000f3c8  jz      short loc_14000F3DA
0x14000f3ca  mov     rax, [rsi]
0x14000f3cd  mov     rcx, rsi
0x14000f3d0  mov     rax, [rax+8]
0x14000f3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3d9  nop
0x14000f3da  movzx   eax, word ptr [r14]
0x14000f3de  sub     ax, 4Dh ; 'M'
0x14000f3e2  mov     ecx, 0FFDFh
0x14000f3e7  test    cx, ax
0x14000f3ea  jnz     loc_14000F58A
0x14000f3f0  movzx   eax, word ptr [r14+2]
0x14000f3f5  sub     ax, 53h ; 'S'
0x14000f3f9  test    cx, ax
0x14000f3fc  jnz     loc_14000F58A
0x14000f402  movzx   eax, word ptr [r14+4]
0x14000f407  sub     ax, 48h ; 'H'
0x14000f40b  test    cx, ax
0x14000f40e  jnz     loc_14000F58A
0x14000f414  movzx   eax, word ptr [r14+6]
0x14000f419  sub     ax, 54h ; 'T'
0x14000f41d  test    cx, ax
0x14000f420  jnz     loc_14000F58A
0x14000f426  movzx   eax, word ptr [r14+8]
0x14000f42b  sub     ax, 4Dh ; 'M'
0x14000f42f  test    cx, ax
0x14000f432  jnz     loc_14000F58A
0x14000f438  movzx   eax, word ptr [r14+0Ah]
0x14000f43d  sub     ax, 4Ch ; 'L'
0x14000f441  test    cx, ax
0x14000f444  jnz     loc_14000F58A
0x14000f44a  cmp     word ptr [r14+0Ch], 3Ah ; ':'
0x14000f450  jnz     loc_14000F58A
0x14000f456  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000f45a  inc     rdx
0x14000f45d  cmp     [r14+rdx*2], r15w
0x14000f462  jnz     short loc_14000F45A
0x14000f464  lea     eax, ds:0FFFFFFFFFFFFFFF2h[rdx*2]
0x14000f46b  mov     r15d, eax
0x14000f46e  mov     edx, eax; dwBytes
0x14000f470  mov     ecx, 42h ; 'B'; uFlags
0x14000f475  call    cs:__imp_GlobalAlloc
0x14000f47c  nop     dword ptr [rax+rax+00h]
0x14000f481  mov     rbx, rax
0x14000f484  xor     eax, eax
0x14000f486  test    rbx, rbx
0x14000f489  jz      loc_14000F57D
0x14000f48f  mov     [rbp+3Fh+ppstm], rax
0x14000f493  mov     rcx, rbx; hMem
0x14000f496  call    cs:__imp_GlobalLock
0x14000f49d  nop     dword ptr [rax+rax+00h]
0x14000f4a2  lea     r8, [r14+0Eh]; Source
0x14000f4a6  mov     r9d, r15d; SourceSize
0x14000f4a9  mov     edx, r15d; DestinationSize
0x14000f4ac  mov     rcx, rax; Destination
0x14000f4af  call    cs:__imp_memcpy_s
0x14000f4b6  nop     dword ptr [rax+rax+00h]
0x14000f4bb  xor     r15d, r15d
0x14000f4be  test    eax, eax
0x14000f4c0  jz      short loc_14000F4E6
0x14000f4c2  cmp     eax, 0Ch
0x14000f4c5  jz      loc_14000F72C
0x14000f4cb  cmp     eax, 16h
0x14000f4ce  jz      loc_14000F721
0x14000f4d4  cmp     eax, 22h ; '"'
0x14000f4d7  jz      loc_14000F721
0x14000f4dd  cmp     eax, 50h ; 'P'
0x14000f4e0  jnz     loc_14000F716
0x14000f4e6  mov     rcx, rbx; hMem
0x14000f4e9  call    cs:__imp_GlobalUnlock
0x14000f4f0  nop     dword ptr [rax+rax+00h]
0x14000f4f5  lea     r8, [rbp+3Fh+ppstm]; ppstm
0x14000f4f9  mov     edx, 1; fDeleteOnRelease
0x14000f4fe  mov     rcx, rbx; hGlobal
0x14000f501  call    cs:__imp_CreateStreamOnHGlobal
0x14000f508  nop     dword ptr [rax+rax+00h]
0x14000f50d  mov     ebx, eax
0x14000f50f  test    eax, eax
0x14000f511  js      short loc_14000F562
0x14000f513  mov     [rbp+3Fh+var_88], r15
0x14000f517  mov     rax, [rsi]
0x14000f51a  lea     r8, [rbp+3Fh+var_88]
0x14000f51e  lea     rdx, _GUID_7fd52380_4e07_101b_ae2d_08002b2ec713
0x14000f525  mov     rcx, rsi
0x14000f528  mov     rax, [rax]
0x14000f52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f530  mov     ebx, eax
0x14000f532  test    eax, eax
0x14000f534  js      short loc_14000F54C
0x14000f536  mov     rcx, [rbp+3Fh+var_88]
0x14000f53a  mov     rax, [rcx]
0x14000f53d  mov     rdx, [rbp+3Fh+ppstm]
0x14000f541  mov     rax, [rax+28h]
0x14000f545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f54a  mov     ebx, eax
0x14000f54c  mov     rcx, [rbp+3Fh+var_88]
0x14000f550  test    rcx, rcx
0x14000f553  jz      short loc_14000F562
0x14000f555  mov     rax, [rcx]
0x14000f558  mov     rax, [rax+10h]
0x14000f55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f561  nop
0x14000f562  mov     rcx, [rbp+3Fh+ppstm]
0x14000f566  test    rcx, rcx
0x14000f569  jz      short loc_14000F578
0x14000f56b  mov     rax, [rcx]
0x14000f56e  mov     rax, [rax+10h]
0x14000f572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f577  nop
0x14000f578  jmp     loc_14000F681
0x14000f57d  mov     ebx, 8007000Eh
0x14000f582  xor     r15d, r15d
0x14000f585  jmp     loc_14000F681
0x14000f58a  mov     [rbp+3Fh+var_88], r15
0x14000f58e  mov     rax, [rsi]
0x14000f591  lea     r8, [rbp+3Fh+var_88]
0x14000f595  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x14000f59c  mov     rcx, rsi
0x14000f59f  mov     rax, [rax]
0x14000f5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5a7  mov     rcx, [rbp+3Fh+var_88]
0x14000f5ab  test    rcx, rcx
0x14000f5ae  jz      loc_14000F66F
0x14000f5b4  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x14000f5b8  call    cs:__imp_VariantInit
0x14000f5bf  nop     dword ptr [rax+rax+00h]
0x14000f5c4  mov     [rbp+3Fh+ClassName], r15w
0x14000f5c9  lea     rcx, [rbp+3Fh+ClassName]; pvarg
0x14000f5cd  call    cs:__imp_VariantClear
0x14000f5d4  nop     dword ptr [rax+rax+00h]
0x14000f5d9  mov     [rbp+3Fh+ClassName], r13w
0x14000f5de  mov     rcx, r14; psz
0x14000f5e1  call    cs:__imp_SysAllocString
0x14000f5e8  nop     dword ptr [rax+rax+00h]
0x14000f5ed  mov     dword ptr [rbp+3Fh+var_58], eax
0x14000f5f0  mov     rcx, rax
0x14000f5f3  sar     rcx, 20h
0x14000f5f7  mov     dword ptr [rbp+3Fh+var_58+4], ecx
0x14000f5fa  test    rax, rax
0x14000f5fd  jz      loc_14000F6FD
0x14000f603  mov     rcx, [rbp+3Fh+var_88]
0x14000f607  mov     rax, [rcx]
0x14000f60a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000f60e  mov     rax, [rax+148h]
0x14000f615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f61a  mov     rcx, [rbp+3Fh+var_88]
0x14000f61e  mov     rax, [rcx]
0x14000f621  lea     rdx, [rbp+3Fh+pvarg]
0x14000f625  mov     qword ptr [rsp+0D0h+cy], rdx
0x14000f62a  lea     rdx, [rbp+3Fh+pvarg]
0x14000f62e  mov     [rsp+0D0h+pbstr], rdx
0x14000f633  lea     r9, [rbp+3Fh+pvarg]
0x14000f637  lea     r8, [rbp+3Fh+pvarg]
0x14000f63b  lea     rdx, [rbp+3Fh+ClassName]
0x14000f63f  mov     rax, [rax+1A0h]
  ... truncated ...
```
