# CImageList::Clone(_GUID const &,void * *)

- ea: `0x18007f860`
- end: `0x18007fa01`
- name: `?Clone@CImageList@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `417`
- prototype: `__int64 __fastcall(CImageList *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18007f860`
- `0x18007fe80`
- `0x180081454`
- `0x180083a90`
- `0x180084018`
- `0x180090020`

## import_xrefs

- `GDI32!SelectObject` at `0x18007f8f5`
- `GDI32!SelectObject` at `0x18007f913`
- `GDI32!SelectObject` at `0x18007f8f5`
- `GDI32!SelectObject` at `0x18007f913`
- `GDI32!DeleteObject` at `0x18007f951`
- `GDI32!DeleteObject` at `0x18007f951`
- `GDI32!GetStockObject` at `0x18007f964`
- `GDI32!GetStockObject` at `0x18007f964`
- `GDI32!CreateSolidBrush` at `0x18007f977`
- `GDI32!CreateSolidBrush` at `0x18007f977`
- `KERNEL32!EnterCriticalSection` at `0x18007f888`
- `KERNEL32!EnterCriticalSection` at `0x18007f888`
- `KERNEL32!LeaveCriticalSection` at `0x18007f9a0`
- `KERNEL32!LeaveCriticalSection` at `0x18007f9a0`

## pseudocode

```c
__int64 __fastcall CImageList::Clone(CImageList *this, const struct _GUID *a2, void **a3)
{
  struct CImageList *v4; // rdi
  HBITMAP v7; // rbp
  CImageList *v8; // rcx
  CImageList *v9; // rcx
  HBITMAP v10; // r14
  HDC v11; // r8
  int v12; // esi
  struct CImageList *v13; // rax
  HDC v14; // rcx
  void *v15; // rcx
  COLORREF v16; // ecx
  HBRUSH SolidBrush; // rax
  COLORREF v18; // ebx
  HDC v19; // rcx

  v4 = 0;
  *a3 = 0;
  v7 = 0;
  EnterCriticalSection(&g_csDll);
  v10 = CImageList::_CopyBitmap(v8, *((HBITMAP *)this + 11), *((HDC *)this + 13));
  if ( v10
    && ((v11 = (HDC)*((_QWORD *)this + 14)) == 0 || (v7 = CImageList::_CopyBitmap(v9, *((HBITMAP *)this + 12), v11)) != 0) )
  {
    v12 = 0;
    v13 = CImageList::Create(
            *((_DWORD *)this + 13),
            *((_DWORD *)this + 14),
            *((_DWORD *)this + 16),
            0,
            *((_DWORD *)this + 12));
    v4 = v13;
    if ( v13 )
    {
      SelectObject(*((HDC *)v13 + 15), v10);
      CImageList::_DeleteBitmap(*((HBITMAP *)v4 + 13));
      v14 = (HDC)*((_QWORD *)v4 + 16);
      if ( v14 )
      {
        SelectObject(v14, v7);
        CImageList::_DeleteBitmap(*((HBITMAP *)v4 + 14));
      }
      v15 = (void *)*((_QWORD *)v4 + 12);
      *((_QWORD *)v4 + 13) = v10;
      *((_QWORD *)v4 + 14) = v7;
      *((_DWORD *)v4 + 14) = *((_DWORD *)this + 10);
      *((_DWORD *)v4 + 15) = *((_DWORD *)this + 11);
      *((_DWORD *)v4 + 19) = *((_DWORD *)this + 15);
      *((_DWORD *)v4 + 21) = *((_DWORD *)this + 17);
      *((_DWORD *)v4 + 22) = *((_DWORD *)this + 18);
      if ( v15 )
        DeleteObject(v15);
      v16 = *((_DWORD *)v4 + 22);
      if ( v16 == -1 )
      {
        *((_QWORD *)v4 + 12) = GetStockObject(4);
        *((_DWORD *)v4 + 12) = 1;
      }
      else
      {
        SolidBrush = CreateSolidBrush(v16);
        v18 = *((_DWORD *)v4 + 22);
        v19 = (HDC)*((_QWORD *)v4 + 15);
        *((_QWORD *)v4 + 12) = SolidBrush;
        *((_DWORD *)v4 + 12) = GetNearestColor32(v19, v18) == v18;
      }
    }
  }
  else
  {
    v12 = -2147024882;
  }
  LeaveCriticalSection(&g_csDll);
  if ( v12 < 0 )
  {
    if ( v10 )
      CImageList::_DeleteBitmap(v10);
    if ( v7 )
      CImageList::_DeleteBitmap(v7);
  }
  if ( v4 )
  {
    v12 = (**(__int64 (__fastcall ***)(struct CImageList *, const struct _GUID *, void **))v4)(v4, a2, a3);
    (*(void (__fastcall **)(struct CImageList *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18007f860  push    rbx
0x18007f862  push    rbp
0x18007f863  push    rsi
0x18007f864  push    rdi
0x18007f865  push    r12
0x18007f867  push    r13
0x18007f869  push    r14
0x18007f86b  push    r15
0x18007f86d  sub     rsp, 38h
0x18007f871  mov     rbx, rcx
0x18007f874  xor     edi, edi
0x18007f876  lea     rcx, g_csDll; lpCriticalSection
0x18007f87d  mov     [r8], rdi
0x18007f880  mov     r12, r8
0x18007f883  mov     r13, rdx
0x18007f886  xor     ebp, ebp
0x18007f888  call    cs:__imp_EnterCriticalSection
0x18007f88e  mov     r8, [rbx+68h]; HDC
0x18007f892  mov     rdx, [rbx+58h]; HBITMAP
0x18007f896  call    ?_CopyBitmap@CImageList@@QEAAPEAUHBITMAP__@@PEAU2@PEAUHDC__@@@Z; CImageList::_CopyBitmap(HBITMAP__ *,HDC__ *)
0x18007f89b  mov     r14, rax
0x18007f89e  test    rax, rax
0x18007f8a1  jz      short loc_18007F8BD
0x18007f8a3  mov     r8, [rbx+70h]; HDC
0x18007f8a7  test    r8, r8
0x18007f8aa  jz      short loc_18007F8C7
0x18007f8ac  mov     rdx, [rbx+60h]; HBITMAP
0x18007f8b0  call    ?_CopyBitmap@CImageList@@QEAAPEAUHBITMAP__@@PEAU2@PEAUHDC__@@@Z; CImageList::_CopyBitmap(HBITMAP__ *,HDC__ *)
0x18007f8b5  mov     rbp, rax
0x18007f8b8  test    rax, rax
0x18007f8bb  jnz     short loc_18007F8C7
0x18007f8bd  mov     esi, 8007000Eh
0x18007f8c2  jmp     loc_18007F999
0x18007f8c7  mov     eax, [rbx+30h]
0x18007f8ca  xor     r9d, r9d; int
0x18007f8cd  mov     r8d, [rbx+40h]; unsigned int
0x18007f8d1  xor     esi, esi
0x18007f8d3  mov     edx, [rbx+38h]; int
0x18007f8d6  mov     ecx, [rbx+34h]; int
0x18007f8d9  mov     [rsp+78h+var_58], eax; int
0x18007f8dd  call    ?Create@CImageList@@SAPEAV1@HHIHH@Z; CImageList::Create(int,int,uint,int,int)
0x18007f8e2  mov     rdi, rax
0x18007f8e5  test    rax, rax
0x18007f8e8  jz      loc_18007F999
0x18007f8ee  mov     rcx, [rax+78h]; hdc
0x18007f8f2  mov     rdx, r14; h
0x18007f8f5  call    cs:__imp_SelectObject
0x18007f8fb  mov     rcx, [rdi+68h]; ho
0x18007f8ff  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x18007f904  mov     rcx, [rdi+80h]; hdc
0x18007f90b  test    rcx, rcx
0x18007f90e  jz      short loc_18007F922
0x18007f910  mov     rdx, rbp; h
0x18007f913  call    cs:__imp_SelectObject
0x18007f919  mov     rcx, [rdi+70h]; ho
0x18007f91d  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x18007f922  mov     rcx, [rdi+60h]; ho
0x18007f926  mov     [rdi+68h], r14
0x18007f92a  mov     [rdi+70h], rbp
0x18007f92e  mov     eax, [rbx+28h]
0x18007f931  mov     [rdi+38h], eax
0x18007f934  mov     eax, [rbx+2Ch]
0x18007f937  mov     [rdi+3Ch], eax
0x18007f93a  mov     eax, [rbx+3Ch]
0x18007f93d  mov     [rdi+4Ch], eax
0x18007f940  mov     eax, [rbx+44h]
0x18007f943  mov     [rdi+54h], eax
0x18007f946  mov     eax, [rbx+48h]
0x18007f949  mov     [rdi+58h], eax
0x18007f94c  test    rcx, rcx
0x18007f94f  jz      short loc_18007F957
0x18007f951  call    cs:__imp_DeleteObject
0x18007f957  mov     ecx, [rdi+58h]; color
0x18007f95a  cmp     ecx, 0FFFFFFFFh
0x18007f95d  jnz     short loc_18007F977
0x18007f95f  mov     ecx, 4; i
0x18007f964  call    cs:__imp_GetStockObject
0x18007f96a  mov     [rdi+60h], rax
0x18007f96e  mov     dword ptr [rdi+30h], 1
0x18007f975  jmp     short loc_18007F999
0x18007f977  call    cs:__imp_CreateSolidBrush
0x18007f97d  mov     ebx, [rdi+58h]
0x18007f980  mov     edx, ebx; color
0x18007f982  mov     rcx, [rdi+78h]; hdc
0x18007f986  mov     [rdi+60h], rax
0x18007f98a  call    ?GetNearestColor32@@YAKPEAUHDC__@@K@Z; GetNearestColor32(HDC__ *,ulong)
0x18007f98f  xor     edx, edx
0x18007f991  cmp     eax, ebx
0x18007f993  setz    dl
0x18007f996  mov     [rdi+30h], edx
0x18007f999  lea     rcx, g_csDll; lpCriticalSection
0x18007f9a0  call    cs:__imp_LeaveCriticalSection
0x18007f9a6  test    esi, esi
0x18007f9a8  jns     short loc_18007F9C4
0x18007f9aa  test    r14, r14
0x18007f9ad  jz      short loc_18007F9B7
0x18007f9af  mov     rcx, r14; ho
0x18007f9b2  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x18007f9b7  test    rbp, rbp
0x18007f9ba  jz      short loc_18007F9C4
0x18007f9bc  mov     rcx, rbp; ho
0x18007f9bf  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x18007f9c4  test    rdi, rdi
0x18007f9c7  jz      short loc_18007F9EE
0x18007f9c9  mov     rax, [rdi]
0x18007f9cc  mov     r8, r12
0x18007f9cf  mov     rdx, r13
0x18007f9d2  mov     rcx, rdi
0x18007f9d5  mov     rax, [rax]
0x18007f9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f9dd  mov     rcx, [rdi]
0x18007f9e0  mov     esi, eax
0x18007f9e2  mov     rax, [rcx+10h]
0x18007f9e6  mov     rcx, rdi
0x18007f9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f9ee  mov     eax, esi
0x18007f9f0  add     rsp, 38h
0x18007f9f4  pop     r15
0x18007f9f6  pop     r14
0x18007f9f8  pop     r13
0x18007f9fa  pop     r12
0x18007f9fc  pop     rdi
0x18007f9fd  pop     rsi
0x18007f9fe  pop     rbp
0x18007f9ff  pop     rbx
0x18007fa00  retn
```
