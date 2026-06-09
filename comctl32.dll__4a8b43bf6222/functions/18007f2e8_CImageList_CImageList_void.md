# CImageList::~CImageList(void)

- ea: `0x18007f2e8`
- end: `0x18007f3da`
- name: `??1CImageList@@AEAA@XZ`
- size: `242`
- prototype: `void __fastcall(CImageList *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800826f0`

## callees

- `0x18007f2e8`
- `0x180081650`
- `0x180084018`
- `0x180090020`

## import_xrefs

- `GDI32!SelectObject` at `0x18007f351`
- `GDI32!SelectObject` at `0x18007f374`
- `GDI32!SelectObject` at `0x18007f351`
- `GDI32!SelectObject` at `0x18007f374`
- `GDI32!DeleteObject` at `0x18007f3ac`
- `GDI32!DeleteObject` at `0x18007f3ac`
- `GDI32!DeleteDC` at `0x18007f35b`
- `GDI32!DeleteDC` at `0x18007f381`
- `GDI32!DeleteDC` at `0x18007f35b`
- `GDI32!DeleteDC` at `0x18007f381`
- `KERNEL32!EnterCriticalSection` at `0x18007f33b`
- `KERNEL32!EnterCriticalSection` at `0x18007f33b`
- `KERNEL32!LeaveCriticalSection` at `0x18007f3c7`
- `KERNEL32!LeaveCriticalSection` at `0x18007f3c7`

## pseudocode

```c
void __fastcall CImageList::~CImageList(CImageList *this)
{
  __int64 v2; // rcx
  HDC v3; // rcx
  HDC v4; // rcx
  HBITMAP v5; // rcx
  HBITMAP v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CImageList::`vftable'{for `CImageListBase'};
  *((_QWORD *)this + 2) = &CImageList::`vftable'{for `IImageList'};
  *((_QWORD *)this + 3) = &CImageList::`vftable'{for `IImageListPriv'};
  *((_QWORD *)this + 4) = &CImageList::`vftable'{for `IPersistStream'};
  v2 = *((_QWORD *)this + 62);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  EnterCriticalSection(&g_csDll);
  v3 = (HDC)*((_QWORD *)this + 15);
  if ( v3 )
  {
    SelectObject(v3, g_hbmDcDeselect);
    DeleteDC(*((HDC *)this + 15));
  }
  v4 = (HDC)*((_QWORD *)this + 16);
  if ( v4 )
  {
    SelectObject(v4, g_hbmDcDeselect);
    DeleteDC(*((HDC *)this + 16));
  }
  v5 = (HBITMAP)*((_QWORD *)this + 13);
  if ( v5 )
    CImageList::_DeleteBitmap(v5);
  v6 = (HBITMAP)*((_QWORD *)this + 14);
  if ( v6 )
    CImageList::_DeleteBitmap(v6);
  v7 = (void *)*((_QWORD *)this + 12);
  if ( v7 )
    DeleteObject(v7);
  if ( !--g_iILRefCount )
    CImageList::GlobalUninit();
  LeaveCriticalSection(&g_csDll);
  *((_DWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18007f2e8  push    rbx
0x18007f2ea  sub     rsp, 20h
0x18007f2ee  lea     rax, ??_7CImageList@@6BCImageListBase@@@; const CImageList::`vftable'{for `CImageListBase'}
0x18007f2f5  mov     rbx, rcx
0x18007f2f8  mov     [rcx], rax
0x18007f2fb  lea     rax, ??_7CImageList@@6BIImageList@@@; const CImageList::`vftable'{for `IImageList'}
0x18007f302  mov     [rcx+10h], rax
0x18007f306  lea     rax, ??_7CImageList@@6BIImageListPriv@@@; const CImageList::`vftable'{for `IImageListPriv'}
0x18007f30d  mov     [rcx+18h], rax
0x18007f311  lea     rax, ??_7CImageList@@6BIPersistStream@@@; const CImageList::`vftable'{for `IPersistStream'}
0x18007f318  mov     [rcx+20h], rax
0x18007f31c  mov     rcx, [rcx+1F0h]
0x18007f323  test    rcx, rcx
0x18007f326  jz      short loc_18007F334
0x18007f328  mov     rax, [rcx]
0x18007f32b  mov     rax, [rax+10h]
0x18007f32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f334  lea     rcx, g_csDll; lpCriticalSection
0x18007f33b  call    cs:__imp_EnterCriticalSection
0x18007f341  mov     rcx, [rbx+78h]; hdc
0x18007f345  test    rcx, rcx
0x18007f348  jz      short loc_18007F361
0x18007f34a  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x18007f351  call    cs:__imp_SelectObject
0x18007f357  mov     rcx, [rbx+78h]; hdc
0x18007f35b  call    cs:__imp_DeleteDC
0x18007f361  mov     rcx, [rbx+80h]; hdc
0x18007f368  test    rcx, rcx
0x18007f36b  jz      short loc_18007F387
0x18007f36d  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x18007f374  call    cs:__imp_SelectObject
0x18007f37a  mov     rcx, [rbx+80h]; hdc
0x18007f381  call    cs:__imp_DeleteDC
0x18007f387  mov     rcx, [rbx+68h]; ho
0x18007f38b  test    rcx, rcx
0x18007f38e  jz      short loc_18007F395
0x18007f390  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x18007f395  mov     rcx, [rbx+70h]; ho
0x18007f399  test    rcx, rcx
0x18007f39c  jz      short loc_18007F3A3
0x18007f39e  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x18007f3a3  mov     rcx, [rbx+60h]; ho
0x18007f3a7  test    rcx, rcx
0x18007f3aa  jz      short loc_18007F3B2
0x18007f3ac  call    cs:__imp_DeleteObject
0x18007f3b2  sub     cs:?g_iILRefCount@@3HA, 1; int g_iILRefCount
0x18007f3b9  jnz     short loc_18007F3C0
0x18007f3bb  call    ?GlobalUninit@CImageList@@SAXXZ; CImageList::GlobalUninit(void)
0x18007f3c0  lea     rcx, g_csDll; lpCriticalSection
0x18007f3c7  call    cs:__imp_LeaveCriticalSection
0x18007f3cd  mov     dword ptr [rbx+8], 0
0x18007f3d4  add     rsp, 20h
0x18007f3d8  pop     rbx
0x18007f3d9  retn
```
