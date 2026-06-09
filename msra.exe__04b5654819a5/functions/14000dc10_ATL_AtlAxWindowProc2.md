# ATL::AtlAxWindowProc2

- ea: `0x14000dc10`
- end: `0x14000e0ba`
- name: `ATL::AtlAxWindowProc2`
- size: `1194`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400044f8`
- `0x14000dc10`
- `0x1400138f8`
- `0x140019004`
- `0x14004ad80`
- `0x14004ae40`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000ddf3`
- `KERNEL32!GlobalAlloc` at `0x14000ddf3`
- `KERNEL32!GlobalUnlock` at `0x14000de61`
- `KERNEL32!GlobalUnlock` at `0x14000de61`
- `KERNEL32!GlobalLock` at `0x14000de0e`
- `KERNEL32!GlobalLock` at `0x14000de0e`
- `USER32!DefWindowProcW` at `0x14000e06f`
- `USER32!DefWindowProcW` at `0x14000e06f`
- `USER32!SetWindowLongW` at `0x14000dca8`
- `USER32!SetWindowLongW` at `0x14000dca8`
- `USER32!GetWindowLongW` at `0x14000dc74`
- `USER32!GetWindowLongW` at `0x14000dc92`
- `USER32!GetWindowLongW` at `0x14000dc74`
- `USER32!GetWindowLongW` at `0x14000dc92`
- `USER32!GetWindowLongPtrW` at `0x14000dcbe`
- `USER32!GetWindowLongPtrW` at `0x14000dcbe`
- `USER32!SetWindowLongPtrW` at `0x14000e005`
- `USER32!SetWindowLongPtrW` at `0x14000e005`
- `USER32!GetWindowTextLengthW` at `0x14000dd03`
- `USER32!GetWindowTextLengthW` at `0x14000dd03`
- `USER32!GetWindowTextW` at `0x14000dd9b`
- `USER32!GetWindowTextW` at `0x14000dd9b`
- `USER32!SetWindowTextW` at `0x14000ddb1`
- `USER32!SetWindowTextW` at `0x14000ddb1`
- `msvcrt!malloc` at `0x14000dd61`
- `msvcrt!malloc` at `0x14000dd61`
- `msvcrt!free` at `0x14000dfe8`
- `msvcrt!free` at `0x14000e057`
- `msvcrt!free` at `0x14000dfe8`
- `msvcrt!free` at `0x14000e057`
- `msvcrt!memcpy_s` at `0x14000de2a`
- `msvcrt!memcpy_s` at `0x14000de2a`
- `ole32!CreateStreamOnHGlobal` at `0x14000de79`
- `ole32!CreateStreamOnHGlobal` at `0x14000de79`
- `ole32!OleUninitialize` at `0x14000dce1`
- `ole32!OleUninitialize` at `0x14000dce1`
- `ole32!OleInitialize` at `0x14000dcf4`
- `ole32!OleInitialize` at `0x14000dcf4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dea8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000df5c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dfb8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e02b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dea8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000df5c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000dfb8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e02b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LRESULT __fastcall ATL::AtlAxWindowProc2(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  LONG WindowLongW; // eax
  LONG_PTR WindowLongPtrW; // rax
  int v10; // ebx
  unsigned __int64 v11; // rax
  size_t v12; // rcx
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rdi
  WCHAR *v16; // rax
  int v18; // eax
  unsigned __int16 *v19; // rcx
  SIZE_T v20; // rbx
  struct IStream *v21; // rcx
  HGLOBAL v22; // rax
  void *v23; // r14
  void *v24; // rax
  errno_t v25; // eax
  WCHAR *v26; // rcx
  bool v27; // zf
  OLECHAR *v28; // rbx
  __int64 v29; // [rsp+0h] [rbp-40h] BYREF
  WCHAR String[4]; // [rsp+40h] [rbp+0h] BYREF
  __int64 v31; // [rsp+48h] [rbp+8h]
  BSTR bstrString; // [rsp+50h] [rbp+10h] BYREF
  LONG_PTR dwNewLong[3]; // [rsp+58h] [rbp+18h] BYREF

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
      if ( &v29 != (__int64 *)-64LL )
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
    v21 = 0;
    *(_QWORD *)String = 0;
    if ( v18 )
    {
      v22 = GlobalAlloc(0x42u, v20);
      v23 = v22;
      if ( !v22 )
      {
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
        v26 = v15 - 8;
        v27 = *((_DWORD *)v15 - 4) == 56797;
LABEL_53:
        if ( v27 )
          free(v26);
        return -1;
      }
      v24 = GlobalLock(v22);
      v25 = memcpy_s(v24, v20, (const void *const)(*(_QWORD *)lParam + 2LL), v20);
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
      CreateStreamOnHGlobal(v23, 1, (LPSTREAM *)String);
      v21 = *(struct IStream **)String;
    }
    bstrString = 0;
    if ( (int)ATL::_DialogSplitHelper::ParseInitData(v21, &bstrString) >= 0 )
    {
      dwNewLong[2] = 0;
      v31 = 0;
      v28 = bstrString;
      if ( (int)AtlAxCreateControlLicEx(v15, 0, (__int64)&GUID_NULL, 0, (__int64)bstrString) >= 0 )
      {
        if ( (**(int (__fastcall ***)(__int64, GUID *, LONG_PTR *))v31)(
               v31,
               &GUID_3935bda8_4ed9_495c_8650_e01fc1e38a4b,
               dwNewLong) >= 0 )
        {
          SetWindowLongPtrW(hWnd, -21, dwNewLong[0]);
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          SysFreeString(v28);
          if ( *(_QWORD *)String )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
          if ( *((_DWORD *)v15 - 4) == 56797 )
            free(v15 - 8);
          return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
        }
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        SysFreeString(v28);
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
      }
      else
      {
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        SysFreeString(v28);
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
      }
    }
    else
    {
      SysFreeString(bstrString);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
    }
    v26 = v15 - 8;
    v27 = *((_DWORD *)v15 - 4) == 56797;
    goto LABEL_53;
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
0x14000dc10  push    rbp
0x14000dc12  push    rbx
0x14000dc13  push    rsi
0x14000dc14  push    rdi
0x14000dc15  push    r12
0x14000dc17  push    r13
0x14000dc19  push    r14
0x14000dc1b  push    r15
0x14000dc1d  sub     rsp, 88h
0x14000dc24  lea     rbp, [rsp+40h]
0x14000dc29  mov     rax, cs:__security_cookie
0x14000dc30  xor     rax, rbp
0x14000dc33  mov     [rbp+80h+var_50], rax
0x14000dc37  mov     r15, r9
0x14000dc3a  mov     r12, r8
0x14000dc3d  mov     r13d, edx
0x14000dc40  mov     rsi, rcx
0x14000dc43  mov     eax, edx
0x14000dc45  sub     eax, 1
0x14000dc48  jz      loc_14000DCF2
0x14000dc4e  sub     eax, 81h
0x14000dc53  jz      short loc_14000DCB9
0x14000dc55  cmp     eax, 18Eh
0x14000dc5a  jnz     loc_14000E063
0x14000dc60  cmp     r12d, 1
0x14000dc64  jnz     loc_14000E063
0x14000dc6a  lea     ebx, [r12-15h]
0x14000dc6f  mov     edx, ebx; nIndex
0x14000dc71  mov     rcx, r9; hWnd
0x14000dc74  call    cs:__imp_GetWindowLongW
0x14000dc7b  nop     dword ptr [rax+rax+00h]
0x14000dc80  mov     edi, 10000h
0x14000dc85  test    edi, eax
0x14000dc87  jz      loc_14000E063
0x14000dc8d  mov     edx, ebx; nIndex
0x14000dc8f  mov     rcx, rsi; hWnd
0x14000dc92  call    cs:__imp_GetWindowLongW
0x14000dc99  nop     dword ptr [rax+rax+00h]
0x14000dc9e  or      eax, edi
0x14000dca0  mov     r8d, eax; dwNewLong
0x14000dca3  mov     edx, ebx; nIndex
0x14000dca5  mov     rcx, rsi; hWnd
0x14000dca8  call    cs:__imp_SetWindowLongW
0x14000dcaf  nop     dword ptr [rax+rax+00h]
0x14000dcb4  jmp     loc_14000E063
0x14000dcb9  mov     edx, 0FFFFFFEBh; nIndex
0x14000dcbe  call    cs:__imp_GetWindowLongPtrW
0x14000dcc5  nop     dword ptr [rax+rax+00h]
0x14000dcca  mov     rdx, rax
0x14000dccd  test    rax, rax
0x14000dcd0  jz      short loc_14000DCE1
0x14000dcd2  mov     rcx, [rax]
0x14000dcd5  mov     rax, [rcx+10h]
0x14000dcd9  mov     rcx, rdx
0x14000dcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dce1  call    cs:__imp_OleUninitialize
0x14000dce8  nop     dword ptr [rax+rax+00h]
0x14000dced  jmp     loc_14000E063
0x14000dcf2  xor     ecx, ecx; pvReserved
0x14000dcf4  call    cs:__imp_OleInitialize
0x14000dcfb  nop     dword ptr [rax+rax+00h]
0x14000dd00  mov     rcx, rsi; hWnd
0x14000dd03  call    cs:__imp_GetWindowTextLengthW
0x14000dd0a  nop     dword ptr [rax+rax+00h]
0x14000dd0f  lea     ebx, [rax+1]
0x14000dd12  movsxd  rax, ebx
0x14000dd15  add     rax, rax
0x14000dd18  lea     rcx, [rax+10h]; Size
0x14000dd1c  mov     r14d, 0DDDDh
0x14000dd22  cmp     rcx, rax
0x14000dd25  jbe     short loc_14000DD7E
0x14000dd27  cmp     rcx, 400h
0x14000dd2e  ja      short loc_14000DD61
0x14000dd30  lea     rax, [rcx+0Fh]
0x14000dd34  cmp     rax, rcx
0x14000dd37  ja      short loc_14000DD43
0x14000dd39  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000dd43  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000dd47  call    _alloca_probe
0x14000dd4c  sub     rsp, rax
0x14000dd4f  lea     rdi, [rsp+0C0h+String]
0x14000dd54  test    rdi, rdi
0x14000dd57  jz      short loc_14000DD80
0x14000dd59  mov     dword ptr [rdi], 0CCCCh
0x14000dd5f  jmp     short loc_14000DD78
0x14000dd61  call    cs:__imp_malloc
0x14000dd68  nop     dword ptr [rax+rax+00h]
0x14000dd6d  mov     rdi, rax
0x14000dd70  test    rax, rax
0x14000dd73  jz      short loc_14000DD80
0x14000dd75  mov     [rax], r14d
0x14000dd78  add     rdi, 10h
0x14000dd7c  jmp     short loc_14000DD80
0x14000dd7e  xor     edi, edi
0x14000dd80  mov     [rbp+80h+var_60], rdi
0x14000dd84  test    rdi, rdi
0x14000dd87  jnz     short loc_14000DD92
0x14000dd89  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000dd8d  jmp     loc_14000E07B
0x14000dd92  mov     r8d, ebx; nMaxCount
0x14000dd95  mov     rdx, rdi; lpString
0x14000dd98  mov     rcx, rsi; hWnd
0x14000dd9b  call    cs:__imp_GetWindowTextW
0x14000dda2  nop     dword ptr [rax+rax+00h]
0x14000dda7  lea     rdx, String; lpString
0x14000ddae  mov     rcx, rsi; hWnd
0x14000ddb1  call    cs:__imp_SetWindowTextW
0x14000ddb8  nop     dword ptr [rax+rax+00h]
0x14000ddbd  mov     [rbp+80h+dwNewLong], 0
0x14000ddc5  xor     eax, eax
0x14000ddc7  test    r15, r15
0x14000ddca  jz      short loc_14000DDDB
0x14000ddcc  mov     rcx, [r15]
0x14000ddcf  test    rcx, rcx
0x14000ddd2  jz      short loc_14000DDDB
0x14000ddd4  movzx   eax, word ptr [rcx]
0x14000ddd7  mov     ebx, eax
0x14000ddd9  jmp     short loc_14000DDDD
0x14000dddb  xor     ebx, ebx
0x14000dddd  xor     ecx, ecx
0x14000dddf  mov     qword ptr [rbp+80h+String], rcx
0x14000dde3  test    eax, eax
0x14000dde5  jz      loc_14000DE8F
0x14000ddeb  mov     rdx, rbx; dwBytes
0x14000ddee  mov     ecx, 42h ; 'B'; uFlags
0x14000ddf3  call    cs:__imp_GlobalAlloc
0x14000ddfa  nop     dword ptr [rax+rax+00h]
0x14000ddff  mov     r14, rax
0x14000de02  test    rax, rax
0x14000de05  jz      loc_14000DED0
0x14000de0b  mov     rcx, rax; hMem
0x14000de0e  call    cs:__imp_GlobalLock
0x14000de15  nop     dword ptr [rax+rax+00h]
0x14000de1a  mov     r8, [r15]
0x14000de1d  add     r8, 2; Source
0x14000de21  mov     r9, rbx; SourceSize
0x14000de24  mov     rdx, rbx; DestinationSize
0x14000de27  mov     rcx, rax; Destination
0x14000de2a  call    cs:__imp_memcpy_s
0x14000de31  nop     dword ptr [rax+rax+00h]
0x14000de36  test    eax, eax
0x14000de38  jz      short loc_14000DE5E
0x14000de3a  cmp     eax, 0Ch
0x14000de3d  jz      loc_14000E099
0x14000de43  cmp     eax, 16h
0x14000de46  jz      loc_14000E0AF
0x14000de4c  cmp     eax, 22h ; '"'
0x14000de4f  jz      loc_14000E0AF
0x14000de55  cmp     eax, 50h ; 'P'
0x14000de58  jnz     loc_14000E0A4
0x14000de5e  mov     rcx, r14; hMem
0x14000de61  call    cs:__imp_GlobalUnlock
0x14000de68  nop     dword ptr [rax+rax+00h]
0x14000de6d  lea     r8, [rbp+80h+String]; ppstm
0x14000de71  mov     edx, 1; fDeleteOnRelease
0x14000de76  mov     rcx, r14; hGlobal
0x14000de79  call    cs:__imp_CreateStreamOnHGlobal
0x14000de80  nop     dword ptr [rax+rax+00h]
0x14000de85  mov     rcx, qword ptr [rbp+80h+String]; struct IStream *
0x14000de89  mov     r14d, 0DDDDh
0x14000de8f  mov     [rbp+80h+bstrString], 0
0x14000de97  lea     rdx, [rbp+80h+bstrString]; unsigned __int16 **
0x14000de9b  call    ?ParseInitData@_DialogSplitHelper@ATL@@SAJPEAUIStream@@PEAPEAG@Z; ATL::_DialogSplitHelper::ParseInitData(IStream *,ushort * *)
0x14000dea0  test    eax, eax
0x14000dea2  jns     short loc_14000DEF5
0x14000dea4  mov     rcx, [rbp+80h+bstrString]; bstrString
0x14000dea8  call    cs:__imp_SysFreeString
0x14000deaf  nop     dword ptr [rax+rax+00h]
0x14000deb4  nop
0x14000deb5  mov     rcx, qword ptr [rbp+80h+String]
0x14000deb9  test    rcx, rcx
0x14000debc  jz      short loc_14000DECB
0x14000debe  mov     rax, [rcx]
0x14000dec1  mov     rax, [rax+10h]
0x14000dec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000deca  nop
0x14000decb  jmp     loc_14000DFDB
0x14000ded0  mov     rcx, qword ptr [rbp+80h+String]
0x14000ded4  test    rcx, rcx
0x14000ded7  jz      short loc_14000DEE6
0x14000ded9  mov     rax, [rcx]
0x14000dedc  mov     rax, [rax+10h]
0x14000dee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dee5  nop
0x14000dee6  lea     rcx, [rdi-10h]
0x14000deea  cmp     dword ptr [rcx], 0DDDDh
0x14000def0  jmp     loc_14000DFE2
0x14000def5  mov     [rbp+80h+var_58], 0
0x14000defd  mov     [rbp+80h+var_78], 0
0x14000df05  mov     rbx, [rbp+80h+bstrString]
0x14000df09  mov     [rsp+0C0h+var_88], rbx; __int64
0x14000df0e  mov     [rsp+0C0h+var_90], 0; __int64
0x14000df17  lea     rax, GUID_NULL
0x14000df1e  mov     [rsp+0C0h+var_98], rax; __int64
0x14000df23  mov     [rsp+0C0h+var_A0], 0; __int64
0x14000df2c  lea     r9, [rbp+80h+var_78]
0x14000df30  mov     r8, qword ptr [rbp+80h+String]
0x14000df34  mov     rdx, rsi
0x14000df37  mov     rcx, rdi; psz
0x14000df3a  call    AtlAxCreateControlLicEx
0x14000df3f  test    eax, eax
0x14000df41  jns     short loc_14000DF81
0x14000df43  mov     rcx, [rbp+80h+var_78]
0x14000df47  test    rcx, rcx
0x14000df4a  jz      short loc_14000DF59
0x14000df4c  mov     rax, [rcx]
0x14000df4f  mov     rax, [rax+10h]
0x14000df53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df58  nop
0x14000df59  mov     rcx, rbx; bstrString
0x14000df5c  call    cs:__imp_SysFreeString
0x14000df63  nop     dword ptr [rax+rax+00h]
0x14000df68  nop
0x14000df69  mov     rcx, qword ptr [rbp+80h+String]
0x14000df6d  test    rcx, rcx
0x14000df70  jz      short loc_14000DF7F
0x14000df72  mov     rax, [rcx]
0x14000df75  mov     rax, [rax+10h]
0x14000df79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df7e  nop
0x14000df7f  jmp     short loc_14000DFDB
0x14000df81  mov     rcx, [rbp+80h+var_78]
0x14000df85  mov     rax, [rcx]
0x14000df88  lea     r8, [rbp+80h+dwNewLong]
0x14000df8c  lea     rdx, _GUID_3935bda8_4ed9_495c_8650_e01fc1e38a4b
0x14000df93  mov     rax, [rax]
0x14000df96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df9b  test    eax, eax
0x14000df9d  jns     short loc_14000DFF9
0x14000df9f  mov     rcx, [rbp+80h+var_78]
0x14000dfa3  test    rcx, rcx
0x14000dfa6  jz      short loc_14000DFB5
0x14000dfa8  mov     rax, [rcx]
0x14000dfab  mov     rax, [rax+10h]
0x14000dfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfb4  nop
0x14000dfb5  mov     rcx, rbx; bstrString
0x14000dfb8  call    cs:__imp_SysFreeString
0x14000dfbf  nop     dword ptr [rax+rax+00h]
0x14000dfc4  nop
0x14000dfc5  mov     rcx, qword ptr [rbp+80h+String]
0x14000dfc9  test    rcx, rcx
0x14000dfcc  jz      short loc_14000DFDB
0x14000dfce  mov     rax, [rcx]
0x14000dfd1  mov     rax, [rax+10h]
0x14000dfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfda  nop
0x14000dfdb  lea     rcx, [rdi-10h]; Block
0x14000dfdf  cmp     [rcx], r14d
0x14000dfe2  jnz     loc_14000DD89
0x14000dfe8  call    cs:__imp_free
0x14000dfef  nop     dword ptr [rax+rax+00h]
0x14000dff4  jmp     loc_14000DD89
0x14000dff9  mov     r8, [rbp+80h+dwNewLong]; dwNewLong
0x14000dffd  mov     edx, 0FFFFFFEBh; nIndex
0x14000e002  mov     rcx, rsi; hWnd
0x14000e005  call    cs:__imp_SetWindowLongPtrW
0x14000e00c  nop     dword ptr [rax+rax+00h]
0x14000e011  nop
0x14000e012  mov     rcx, [rbp+80h+var_78]
0x14000e016  test    rcx, rcx
0x14000e019  jz      short loc_14000E028
0x14000e01b  mov     rax, [rcx]
0x14000e01e  mov     rax, [rax+10h]
0x14000e022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e027  nop
0x14000e028  mov     rcx, rbx; bstrString
0x14000e02b  call    cs:__imp_SysFreeString
0x14000e032  nop     dword ptr [rax+rax+00h]
0x14000e037  nop
0x14000e038  mov     rcx, qword ptr [rbp+80h+String]
0x14000e03c  test    rcx, rcx
0x14000e03f  jz      short loc_14000E04E
0x14000e041  mov     rax, [rcx]
0x14000e044  mov     rax, [rax+10h]
0x14000e048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e04d  nop
0x14000e04e  lea     rcx, [rdi-10h]; Block
0x14000e052  cmp     [rcx], r14d
0x14000e055  jnz     short loc_14000E063
0x14000e057  call    cs:__imp_free
0x14000e05e  nop     dword ptr [rax+rax+00h]
0x14000e063  mov     r9, r15; lParam
0x14000e066  mov     r8, r12; wParam
0x14000e069  mov     edx, r13d; Msg
0x14000e06c  mov     rcx, rsi; hWnd
0x14000e06f  call    cs:__imp_DefWindowProcW
0x14000e076  nop     dword ptr [rax+rax+00h]
0x14000e07b  mov     rcx, [rbp+80h+var_50]
0x14000e07f  xor     rcx, rbp; StackCookie
0x14000e082  call    __security_check_cookie
0x14000e087  lea     rsp, [rbp+48h]
0x14000e08b  pop     r15
0x14000e08d  pop     r14
0x14000e08f  pop     r13
0x14000e091  pop     r12
0x14000e093  pop     rdi
0x14000e094  pop     rsi
0x14000e095  pop     rbx
0x14000e096  pop     rbp
  ... truncated ...
```
