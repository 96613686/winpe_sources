# ATL::CComControlBase::IDataObject_GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1800cb950`
- end: `0x1800cbb2b`
- name: `?IDataObject_GetData@CComControlBase@ATL@@QEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800ca180`

## callees

- `0x180004640`
- `0x1800054bc`
- `0x18008676c`
- `0x1800cb950`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1800cbaba`
- `KERNEL32!GlobalAlloc` at `0x1800cbaba`
- `KERNEL32!GlobalLock` at `0x1800cbadb`
- `KERNEL32!GlobalLock` at `0x1800cbadb`
- `KERNEL32!GlobalUnlock` at `0x1800cbaf7`
- `KERNEL32!GlobalUnlock` at `0x1800cbaf7`
- `GDI32!DeleteMetaFile` at `0x1800cbacb`
- `GDI32!DeleteMetaFile` at `0x1800cbacb`
- `GDI32!SetWindowOrgEx` at `0x1800cba5d`
- `GDI32!SetWindowOrgEx` at `0x1800cba5d`
- `GDI32!SaveDC` at `0x1800cba4b`
- `GDI32!SaveDC` at `0x1800cba4b`
- `GDI32!CloseMetaFile` at `0x1800cba9b`
- `GDI32!CloseMetaFile` at `0x1800cba9b`
- `GDI32!CreateMetaFileW` at `0x1800cba3e`
- `GDI32!CreateMetaFileW` at `0x1800cba3e`
- `GDI32!SetWindowExtEx` at `0x1800cba71`
- `GDI32!SetWindowExtEx` at `0x1800cba71`
- `GDI32!RestoreDC` at `0x1800cba91`
- `GDI32!RestoreDC` at `0x1800cba91`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::IDataObject_GetData(
        struct tagSIZE *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  __int64 result; // rax
  bool v6; // zf
  struct tagSIZE v7; // rbx
  struct tagSIZE v8; // rax
  int v9; // eax
  HMETAFILE v10; // r14
  HBITMAP v11; // rax
  HBITMAP v12; // rsi
  _DWORD *v13; // rax
  struct tagSIZE v14; // [rsp+20h] [rbp-59h] BYREF
  struct tagSIZE v15; // [rsp+28h] [rbp-51h] BYREF
  _DWORD v16[4]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v17; // [rsp+40h] [rbp-39h]
  HDC hdc; // [rsp+50h] [rbp-29h]
  __int64 *v19; // [rsp+58h] [rbp-21h]
  __int64 *v20; // [rsp+60h] [rbp-19h]
  int v21; // [rsp+68h] [rbp-11h]
  int v22; // [rsp+70h] [rbp-9h]
  __int64 v23; // [rsp+90h] [rbp+17h] BYREF
  struct tagSIZE x; // [rsp+98h] [rbp+1Fh]

  if ( !a3 )
    return 2147500035LL;
  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  if ( (a2->tymed & 0x20) == 0 )
    return 2147745892LL;
  v6 = (this[13].cx & 0x1000) == 0;
  v15 = 0;
  if ( v6 )
    v7 = this[8];
  else
    v7 = this[7];
  v6 = (this[13].cx & 0x2000) == 0;
  v14 = v7;
  if ( v6 )
  {
    ATL::AtlHiMetricToPixel(&v14, &v15);
    v8 = v15;
  }
  else
  {
    v8 = v7;
  }
  x = v8;
  v23 = 0;
  memset_0(v16, 0, 0x58u);
  v16[0] = 88;
  v16[1] = 1;
  v19 = &v23;
  v21 = 1;
  v20 = &v23;
  v9 = ((unsigned int)this[13].cx >> 13) & 1;
  v16[2] = -1;
  v22 = v9;
  v17 = 0;
  hdc = CreateMetaFileW(0);
  SaveDC(hdc);
  SetWindowOrgEx(hdc, 0, 0, 0);
  SetWindowExtEx(hdc, x.cx, x.cy, 0);
  (*(void (__fastcall **)(struct tagSIZE *, _DWORD *))(*(_QWORD *)this + 16LL))(this, v16);
  RestoreDC(hdc, -1);
  v10 = CloseMetaFile(hdc);
  if ( !v10 )
    return 2147549183LL;
  v11 = (HBITMAP)GlobalAlloc(0x2002u, 0x18u);
  v12 = v11;
  if ( v11 )
  {
    v13 = GlobalLock(v11);
    v13[2] = v14.cy;
    *((_QWORD *)v13 + 2) = v10;
    *v13 = 8;
    v13[1] = v7.cx;
    GlobalUnlock(v12);
    result = 0;
    a3->tymed = 32;
    a3->hBitmap = v12;
    a3->pUnkForRelease = 0;
  }
  else
  {
    DeleteMetaFile(v10);
    return 2147680368LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800cb950  push    rbp
0x1800cb952  push    rbx
0x1800cb953  push    rsi
0x1800cb954  push    rdi
0x1800cb955  push    r14
0x1800cb957  lea     rbp, [rsp-37h]
0x1800cb95c  sub     rsp, 0B0h
0x1800cb963  mov     rax, cs:__security_cookie
0x1800cb96a  xor     rax, rsp
0x1800cb96d  mov     [rbp+57h+var_30], rax
0x1800cb971  mov     rdi, r8
0x1800cb974  mov     rsi, rcx
0x1800cb977  test    r8, r8
0x1800cb97a  jnz     short loc_1800CB986
0x1800cb97c  mov     eax, 80004003h
0x1800cb981  jmp     loc_1800CBB11
0x1800cb986  xor     eax, eax
0x1800cb988  xorps   xmm0, xmm0
0x1800cb98b  movups  xmmword ptr [r8], xmm0
0x1800cb98f  mov     [r8+10h], rax
0x1800cb993  test    byte ptr [rdx+18h], 20h
0x1800cb997  jnz     short loc_1800CB9A3
0x1800cb999  mov     eax, 80040064h
0x1800cb99e  jmp     loc_1800CBB11
0x1800cb9a3  test    dword ptr [rcx+68h], 1000h
0x1800cb9aa  mov     qword ptr [rbp+57h+var_A8.cx], rax
0x1800cb9ae  jz      short loc_1800CB9B6
0x1800cb9b0  mov     rbx, [rcx+38h]
0x1800cb9b4  jmp     short loc_1800CB9BA
0x1800cb9b6  mov     rbx, [rcx+40h]
0x1800cb9ba  test    dword ptr [rcx+68h], 2000h
0x1800cb9c1  mov     qword ptr [rbp+57h+var_B0.cx], rbx
0x1800cb9c5  jnz     short loc_1800CB9DA
0x1800cb9c7  lea     rdx, [rbp+57h+var_A8]; struct tagSIZE *
0x1800cb9cb  lea     rcx, [rbp+57h+var_B0]; struct tagSIZE *
0x1800cb9cf  call    ?AtlHiMetricToPixel@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlHiMetricToPixel(tagSIZE const *,tagSIZE *)
0x1800cb9d4  mov     rax, qword ptr [rbp+57h+var_A8.cx]
0x1800cb9d8  jmp     short loc_1800CB9DD
0x1800cb9da  mov     rax, rbx
0x1800cb9dd  mov     [rbp+57h+x], eax
0x1800cb9e0  lea     rcx, [rbp+57h+var_A0]; void *
0x1800cb9e4  shr     rax, 20h
0x1800cb9e8  mov     r14d, 58h ; 'X'
0x1800cb9ee  mov     r8d, r14d; Size
0x1800cb9f1  mov     [rbp+57h+y], eax
0x1800cb9f4  xor     edx, edx; Val
0x1800cb9f6  mov     [rbp+57h+var_40], 0
0x1800cb9fe  call    memset_0
0x1800cba03  lea     ecx, [r14-57h]
0x1800cba07  mov     [rbp+57h+var_A0], r14d
0x1800cba0b  lea     rax, [rbp+57h+var_40]
0x1800cba0f  mov     [rbp+57h+var_9C], ecx
0x1800cba12  mov     [rbp+57h+var_78], rax
0x1800cba16  xorps   xmm0, xmm0
0x1800cba19  lea     rax, [rbp+57h+var_40]
0x1800cba1d  mov     [rbp+57h+var_68], ecx
0x1800cba20  mov     [rbp+57h+var_70], rax
0x1800cba24  or      r14d, 0FFFFFFFFh
0x1800cba28  mov     eax, [rsi+68h]
0x1800cba2b  shr     eax, 0Dh
0x1800cba2e  and     eax, ecx
0x1800cba30  mov     [rbp+57h+var_98], r14d
0x1800cba34  xor     ecx, ecx; pszFile
0x1800cba36  mov     [rbp+57h+var_60], eax
0x1800cba39  movdqa  [rbp+57h+var_90], xmm0
0x1800cba3e  call    cs:__imp_CreateMetaFileW
0x1800cba44  mov     rcx, rax; hdc
0x1800cba47  mov     [rbp+57h+hdc], rax
0x1800cba4b  call    cs:__imp_SaveDC
0x1800cba51  mov     rcx, [rbp+57h+hdc]; hdc
0x1800cba55  xor     r9d, r9d; lppt
0x1800cba58  xor     r8d, r8d; y
0x1800cba5b  xor     edx, edx; x
0x1800cba5d  call    cs:__imp_SetWindowOrgEx
0x1800cba63  mov     r8d, [rbp+57h+y]; y
0x1800cba67  xor     r9d, r9d; lpsz
0x1800cba6a  mov     edx, [rbp+57h+x]; x
0x1800cba6d  mov     rcx, [rbp+57h+hdc]; hdc
0x1800cba71  call    cs:__imp_SetWindowExtEx
0x1800cba77  mov     rax, [rsi]
0x1800cba7a  lea     rdx, [rbp+57h+var_A0]
0x1800cba7e  mov     rcx, rsi
0x1800cba81  mov     rax, [rax+10h]
0x1800cba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cba8a  mov     rcx, [rbp+57h+hdc]; hdc
0x1800cba8e  mov     edx, r14d; nSavedDC
0x1800cba91  call    cs:__imp_RestoreDC
0x1800cba97  mov     rcx, [rbp+57h+hdc]; hdc
0x1800cba9b  call    cs:__imp_CloseMetaFile
0x1800cbaa1  mov     r14, rax
0x1800cbaa4  test    rax, rax
0x1800cbaa7  jnz     short loc_1800CBAB0
0x1800cbaa9  mov     eax, 8000FFFFh
0x1800cbaae  jmp     short loc_1800CBB11
0x1800cbab0  mov     edx, 18h; dwBytes
0x1800cbab5  mov     ecx, 2002h; uFlags
0x1800cbaba  call    cs:__imp_GlobalAlloc
0x1800cbac0  mov     rsi, rax
0x1800cbac3  test    rax, rax
0x1800cbac6  jnz     short loc_1800CBAD8
0x1800cbac8  mov     rcx, r14; hmf
0x1800cbacb  call    cs:__imp_DeleteMetaFile
0x1800cbad1  mov     eax, 80030070h
0x1800cbad6  jmp     short loc_1800CBB11
0x1800cbad8  mov     rcx, rsi; hMem
0x1800cbadb  call    cs:__imp_GlobalLock
0x1800cbae1  mov     ecx, [rbp+57h+var_B0.cy]
0x1800cbae4  mov     [rax+8], ecx
0x1800cbae7  mov     rcx, rsi; hMem
0x1800cbaea  mov     [rax+10h], r14
0x1800cbaee  mov     dword ptr [rax], 8
0x1800cbaf4  mov     [rax+4], ebx
0x1800cbaf7  call    cs:__imp_GlobalUnlock
0x1800cbafd  xor     eax, eax
0x1800cbaff  mov     dword ptr [rdi], 20h ; ' '
0x1800cbb05  mov     [rdi+8], rsi
0x1800cbb09  mov     qword ptr [rdi+10h], 0
0x1800cbb11  mov     rcx, [rbp+57h+var_30]
0x1800cbb15  xor     rcx, rsp; StackCookie
0x1800cbb18  call    __security_check_cookie
0x1800cbb1d  add     rsp, 0B0h
0x1800cbb24  pop     r14
0x1800cbb26  pop     rdi
0x1800cbb27  pop     rsi
0x1800cbb28  pop     rbx
0x1800cbb29  pop     rbp
0x1800cbb2a  retn
```
