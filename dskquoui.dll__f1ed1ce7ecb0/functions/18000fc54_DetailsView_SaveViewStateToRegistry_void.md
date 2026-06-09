# DetailsView::SaveViewStateToRegistry(void)

- ea: `0x18000fc54`
- end: `0x18000ff37`
- name: `?SaveViewStateToRegistry@DetailsView@@AEAAXXZ`
- size: `739`
- prototype: `void __fastcall(DetailsView *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18000e32c`

## callees

- `0x180001510`
- `0x180006fa0`
- `0x180007700`
- `0x180007b58`
- `0x18000fc54`
- `0x18001003c`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x18001a5f0`
- `0x18001a73c`
- `0x18001b878`
- `0x18001b8bc`
- `0x18001ba9c`
- `0x18001bb38`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000fe2d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000fe2d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fdda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fdda`
- `GDI32!GetDeviceCaps` at `0x18000fcc8`
- `GDI32!GetDeviceCaps` at `0x18000fcde`
- `GDI32!GetDeviceCaps` at `0x18000fcc8`
- `GDI32!GetDeviceCaps` at `0x18000fcde`
- `USER32!GetDC` at `0x18000fc85`
- `USER32!GetDC` at `0x18000fc85`
- `USER32!ReleaseDC` at `0x18000fcf4`
- `USER32!ReleaseDC` at `0x18000fcf4`
- `USER32!SendMessageW` at `0x18000fd32`
- `USER32!SendMessageW` at `0x18000fd51`
- `USER32!SendMessageW` at `0x18000fd79`
- `USER32!SendMessageW` at `0x18000fdf2`
- `USER32!SendMessageW` at `0x18000fe66`
- `USER32!SendMessageW` at `0x18000fe9d`
- `USER32!SendMessageW` at `0x18000fd32`
- `USER32!SendMessageW` at `0x18000fd51`
- `USER32!SendMessageW` at `0x18000fd79`
- `USER32!SendMessageW` at `0x18000fdf2`
- `USER32!SendMessageW` at `0x18000fe66`
- `USER32!SendMessageW` at `0x18000fe9d`
- `USER32!GetWindowRect` at `0x18000fd02`
- `USER32!GetWindowRect` at `0x18000fd02`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall DetailsView::SaveViewStateToRegistry(DetailsView *this)
{
  HDC DC; // rbx
  HKEY v3; // rdx
  const unsigned __int16 *v4; // r8
  unsigned int v5; // esi
  unsigned int i; // ebx
  __int16 v7; // cx
  unsigned int v8; // eax
  unsigned int v9; // r14d
  unsigned int v10; // esi
  __int64 v11; // rdx
  int v12; // r15d
  unsigned __int16 *Buffer; // rax
  int v14; // ebx
  __int64 v15; // rax
  _BYTE pExceptionObject[16]; // [rsp+30h] [rbp-79h] BYREF
  void **v17; // [rsp+40h] [rbp-69h] BYREF
  __int64 v18; // [rsp+48h] [rbp-61h]
  int v19; // [rsp+50h] [rbp-59h]
  __int64 v20; // [rsp+58h] [rbp-51h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v22[16]; // [rsp+90h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-9h]
  struct tagRECT Rect; // [rsp+B8h] [rbp+Fh] BYREF

  Rect = 0;
  DC = GetDC(*((HWND *)this + 12));
  RegKey::RegKey((RegKey *)v22, v3, v4);
  if ( RegKey::Open((RegKey *)v22, 0x20006u, 1) >= 0 )
  {
    *((_WORD *)this + 284) = 88;
    *((_DWORD *)this + 143) = (unsigned __int16)GetDeviceCaps(DC, 8);
    *((_DWORD *)this + 144) = (unsigned __int16)GetDeviceCaps(DC, 10);
    ReleaseDC(*((HWND *)this + 12), DC);
    GetWindowRect(*((HWND *)this + 12), &Rect);
    *((_DWORD *)this + 145) = Rect.right - Rect.left;
    *((_DWORD *)this + 146) = Rect.bottom - Rect.top;
    v5 = SendMessageW(*((HWND *)this + 18), 0x1200u, 0, 0);
    for ( i = 0; i < v5; ++i )
      *((_DWORD *)this + i + 148) = SendMessageW(*((HWND *)this + 13), 0x101Du, (int)i, 0);
    SendMessageW(*((HWND *)this + 18), 0x1211u, v5, (LPARAM)this + 624);
    v7 = *((_WORD *)this + 294)
       ^ ((unsigned __int8)*((_WORD *)this + 294)
        ^ (unsigned __int8)(8 * *((_WORD *)this + 260)))
       & 0x78;
    *((_WORD *)this + 294) = v7 ^ (v7 ^ (*((_WORD *)this + 262) << 7)) & 0x80;
    RegSetValueExW(hKey, L"Preferences", 0, 3u, (const BYTE *)this + 568, *((unsigned __int16 *)this + 284));
    v8 = SendMessageW(*((HWND *)this + 16), 0x146u, 0, 0);
    v9 = v8;
    if ( v8 != -1 && v8 )
    {
      v17 = &CArray<CString>::`vftable';
      v18 = 0;
      v19 = 8;
      v20 = 0;
      if ( !InitializeCriticalSectionAndSpinCount(&CriticalSection, 0) )
      {
        CSyncException::CSyncException(pExceptionObject);
        throw (CSyncException *)pExceptionObject;
      }
      CArray<CString>::SetSize(&v17, v9, 0xFFFFFFFFLL);
      HIDWORD(v18) = v9;
      v10 = 0;
      do
      {
        v12 = SendMessageW(*((HWND *)this + 16), 0x149u, v10, 0);
        if ( v12 >= 1 )
        {
          CString::CString((CString *)pExceptionObject);
          Buffer = CString::GetBuffer((CString *)pExceptionObject, v12 + 1);
          v14 = SendMessageW(*((HWND *)this + 16), 0x148u, v10, (LPARAM)Buffer);
          CString::ReleaseBuffer((CString *)pExceptionObject);
          if ( v14 != -1 )
          {
            v15 = CArray<CString>::operator[](&v17, v10);
            CString::operator=(v15, pExceptionObject);
          }
          CString::~CString((CString *)pExceptionObject);
        }
        ++v10;
      }
      while ( v10 < v9 );
      RegKey::SetValue(v22, v11, &v17);
      CArray<COwnerListFile>::~CArray<COwnerListFile>(&v17);
    }
  }
  RegKey::~RegKey((RegKey *)v22);
}

```

## disassembly

```asm
0x18000fc54  push    rbp
0x18000fc56  push    rbx
0x18000fc57  push    rsi
0x18000fc58  push    rdi
0x18000fc59  push    r14
0x18000fc5b  push    r15
0x18000fc5d  lea     rbp, [rsp-2Fh]
0x18000fc62  sub     rsp, 0D8h
0x18000fc69  mov     rax, cs:__security_cookie
0x18000fc70  xor     rax, rsp
0x18000fc73  mov     [rbp+57h+var_38], rax
0x18000fc77  mov     rdi, rcx
0x18000fc7a  xorps   xmm0, xmm0
0x18000fc7d  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18000fc81  mov     rcx, [rcx+60h]; hWnd
0x18000fc85  call    cs:__imp_GetDC
0x18000fc8b  mov     rbx, rax
0x18000fc8e  lea     rcx, [rbp+57h+var_70]; this
0x18000fc92  call    ??0RegKey@@QEAA@PEAUHKEY__@@PEBG@Z; RegKey::RegKey(HKEY__ *,ushort const *)
0x18000fc97  nop
0x18000fc98  mov     r8b, 1; bool
0x18000fc9b  mov     edx, 20006h; unsigned int
0x18000fca0  lea     rcx, [rbp+57h+var_70]; this
0x18000fca4  call    ?Open@RegKey@@QEBAJK_N@Z; RegKey::Open(ulong,bool)
0x18000fca9  xor     r15d, r15d
0x18000fcac  test    eax, eax
0x18000fcae  js      loc_18000FEF8
0x18000fcb4  lea     r14, [rdi+238h]
0x18000fcbb  mov     word ptr [r14], 58h ; 'X'
0x18000fcc1  lea     edx, [r15+8]; index
0x18000fcc5  mov     rcx, rbx; hdc
0x18000fcc8  call    cs:__imp_GetDeviceCaps
0x18000fcce  movzx   ecx, ax
0x18000fcd1  mov     [rdi+23Ch], ecx
0x18000fcd7  lea     edx, [r15+0Ah]; index
0x18000fcdb  mov     rcx, rbx; hdc
0x18000fcde  call    cs:__imp_GetDeviceCaps
0x18000fce4  movzx   ecx, ax
0x18000fce7  mov     [rdi+240h], ecx
0x18000fced  mov     rdx, rbx; hDC
0x18000fcf0  mov     rcx, [rdi+60h]; hWnd
0x18000fcf4  call    cs:__imp_ReleaseDC
0x18000fcfa  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000fcfe  mov     rcx, [rdi+60h]; hWnd
0x18000fd02  call    cs:__imp_GetWindowRect
0x18000fd08  mov     eax, [rbp+57h+Rect.right]
0x18000fd0b  sub     eax, [rbp+57h+Rect.left]
0x18000fd0e  mov     [rdi+244h], eax
0x18000fd14  mov     eax, [rbp+57h+Rect.bottom]
0x18000fd17  sub     eax, [rbp+57h+Rect.top]
0x18000fd1a  mov     [rdi+248h], eax
0x18000fd20  xor     r9d, r9d; lParam
0x18000fd23  xor     r8d, r8d; wParam
0x18000fd26  mov     edx, 1200h; Msg
0x18000fd2b  mov     rcx, [rdi+90h]; hWnd
0x18000fd32  call    cs:__imp_SendMessageW
0x18000fd38  mov     rsi, rax
0x18000fd3b  mov     ebx, r15d
0x18000fd3e  test    eax, eax
0x18000fd40  jz      short loc_18000FD66
0x18000fd42  movsxd  r8, ebx; wParam
0x18000fd45  xor     r9d, r9d; lParam
0x18000fd48  mov     edx, 101Dh; Msg
0x18000fd4d  mov     rcx, [rdi+68h]; hWnd
0x18000fd51  call    cs:__imp_SendMessageW
0x18000fd57  mov     ecx, ebx
0x18000fd59  mov     [rdi+rcx*4+250h], eax
0x18000fd60  inc     ebx
0x18000fd62  cmp     ebx, esi
0x18000fd64  jb      short loc_18000FD42
0x18000fd66  lea     r9, [r14+38h]; lParam
0x18000fd6a  mov     r8d, esi; wParam
0x18000fd6d  mov     edx, 1211h; Msg
0x18000fd72  mov     rcx, [rdi+90h]; hWnd
0x18000fd79  call    cs:__imp_SendMessageW
0x18000fd7f  movzx   eax, word ptr [rdi+24Ch]
0x18000fd86  movzx   ecx, word ptr [rdi+208h]
0x18000fd8d  shl     cx, 3
0x18000fd91  xor     cx, ax
0x18000fd94  and     cx, 78h
0x18000fd98  xor     cx, ax
0x18000fd9b  movzx   eax, word ptr [rdi+20Ch]
0x18000fda2  shl     ax, 7
0x18000fda6  xor     ax, cx
0x18000fda9  mov     edx, 80h
0x18000fdae  and     ax, dx
0x18000fdb1  xor     ax, cx
0x18000fdb4  mov     [rdi+24Ch], ax
0x18000fdbb  movzx   eax, word ptr [r14]
0x18000fdbf  mov     [rsp+100h+cbData], eax; cbData
0x18000fdc3  mov     [rsp+100h+lpData], r14; lpData
0x18000fdc8  lea     r9d, [rdx-7Dh]; dwType
0x18000fdcc  xor     r8d, r8d; Reserved
0x18000fdcf  lea     rdx, ValueName; "Preferences"
0x18000fdd6  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fdda  call    cs:__imp_RegSetValueExW
0x18000fde0  xor     r9d, r9d; lParam
0x18000fde3  xor     r8d, r8d; wParam
0x18000fde6  mov     edx, 146h; Msg
0x18000fdeb  mov     rcx, [rdi+80h]; hWnd
0x18000fdf2  call    cs:__imp_SendMessageW
0x18000fdf8  mov     r14, rax
0x18000fdfb  cmp     eax, 0FFFFFFFFh
0x18000fdfe  jz      loc_18000FEF8
0x18000fe04  test    r14d, r14d
0x18000fe07  jz      loc_18000FEF8
0x18000fe0d  lea     rax, ??_7?$CArray@VCString@@@@6B@; const CArray<CString>::`vftable'
0x18000fe14  mov     [rbp+57h+var_C0], rax
0x18000fe18  mov     [rbp+57h+var_B8], r15
0x18000fe1c  mov     [rbp+57h+var_B0], 8
0x18000fe23  mov     [rbp+57h+var_A8], r15
0x18000fe27  xor     edx, edx; dwSpinCount
0x18000fe29  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18000fe2d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000fe33  test    eax, eax
0x18000fe35  jz      loc_18000FF1D
0x18000fe3b  or      r8d, 0FFFFFFFFh
0x18000fe3f  mov     edx, r14d
0x18000fe42  lea     rcx, [rbp+57h+var_C0]
0x18000fe46  call    ?SetSize@?$CArray@VCString@@@@QEAAXHH@Z; CArray<CString>::SetSize(int,int)
0x18000fe4b  mov     dword ptr [rbp+57h+var_B8+4], r14d
0x18000fe4f  mov     esi, r15d
0x18000fe52  mov     ebx, esi
0x18000fe54  xor     r9d, r9d; lParam
0x18000fe57  mov     r8d, esi; wParam
0x18000fe5a  mov     edx, 149h; Msg
0x18000fe5f  mov     rcx, [rdi+80h]; hWnd
0x18000fe66  call    cs:__imp_SendMessageW
0x18000fe6c  mov     r15, rax
0x18000fe6f  cmp     eax, 1
0x18000fe72  jl      short loc_18000FED5
0x18000fe74  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000fe78  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x18000fe7d  nop
0x18000fe7e  lea     edx, [r15+1]; int
0x18000fe82  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000fe86  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x18000fe8b  mov     r9, rax; lParam
0x18000fe8e  mov     r8d, ebx; wParam
0x18000fe91  mov     edx, 148h; Msg
0x18000fe96  mov     rcx, [rdi+80h]; hWnd
0x18000fe9d  call    cs:__imp_SendMessageW
0x18000fea3  mov     rbx, rax
0x18000fea6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000feaa  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x18000feaf  cmp     ebx, 0FFFFFFFFh
0x18000feb2  jz      short loc_18000FECC
0x18000feb4  mov     edx, esi
0x18000feb6  lea     rcx, [rbp+57h+var_C0]
0x18000feba  call    ??A?$CArray@VCString@@@@QEAAAEAVCString@@H@Z; CArray<CString>::operator[](int)
0x18000febf  mov     rcx, rax
0x18000fec2  lea     rdx, [rbp+57h+pExceptionObject]
0x18000fec6  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000fecb  nop
0x18000fecc  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000fed0  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18000fed5  inc     esi
0x18000fed7  cmp     esi, r14d
0x18000feda  jb      loc_18000FE52
0x18000fee0  lea     r8, [rbp+57h+var_C0]
0x18000fee4  lea     rcx, [rbp+57h+var_70]
0x18000fee8  call    ?SetValue@RegKey@@QEAAJPEBGAEBV?$CArray@VCString@@@@@Z; RegKey::SetValue(ushort const *,CArray<CString> const &)
0x18000feed  nop
0x18000feee  lea     rcx, [rbp+57h+var_C0]
0x18000fef2  call    ??1?$CArray@VCOwnerListFile@@@@UEAA@XZ; CArray<COwnerListFile>::~CArray<COwnerListFile>(void)
0x18000fef7  nop
0x18000fef8  lea     rcx, [rbp+57h+var_70]; this
0x18000fefc  call    ??1RegKey@@UEAA@XZ; RegKey::~RegKey(void)
0x18000ff01  mov     rcx, [rbp+57h+var_38]
0x18000ff05  xor     rcx, rsp; StackCookie
0x18000ff08  call    __security_check_cookie
0x18000ff0d  add     rsp, 0D8h
0x18000ff14  pop     r15
0x18000ff16  pop     r14
0x18000ff18  pop     rdi
0x18000ff19  pop     rsi
0x18000ff1a  pop     rbx
0x18000ff1b  pop     rbp
0x18000ff1c  retn
0x18000ff1d  lea     rcx, [rbp+57h+pExceptionObject]
0x18000ff21  call    ??0CSyncException@@QEAA@W4object@0@W4reason@0@@Z; CSyncException::CSyncException(CSyncException::object,CSyncException::reason)
0x18000ff26  lea     rdx, _TI2?AVCSyncException@@; pThrowInfo
0x18000ff2d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000ff31  call    _CxxThrowException_0
```
