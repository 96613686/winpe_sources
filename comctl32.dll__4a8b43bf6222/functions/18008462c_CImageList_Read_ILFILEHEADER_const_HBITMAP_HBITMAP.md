# CImageList::_Read(_ILFILEHEADER const *,HBITMAP__ *,HBITMAP__ *)

- ea: `0x18008462c`
- end: `0x180084714`
- name: `?_Read@CImageList@@QEAAJPEBU_ILFILEHEADER@@PEAUHBITMAP__@@1@Z`
- size: `232`
- prototype: `__int64 __fastcall(CImageList *__hidden this, const struct _ILFILEHEADER *, HBITMAP, HBITMAP)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180082280`

## callees

- `0x18008212c`
- `0x18008462c`
- `0x180084e38`
- `0x180084ef8`

## import_xrefs

- `GDI32!SelectObject` at `0x180084678`
- `GDI32!SelectObject` at `0x1800846a2`
- `GDI32!SelectObject` at `0x180084678`
- `GDI32!SelectObject` at `0x1800846a2`
- `GDI32!DeleteObject` at `0x180084682`
- `GDI32!DeleteObject` at `0x1800846ac`
- `GDI32!DeleteObject` at `0x1800846f7`
- `GDI32!DeleteObject` at `0x180084700`
- `GDI32!DeleteObject` at `0x180084682`
- `GDI32!DeleteObject` at `0x1800846ac`
- `GDI32!DeleteObject` at `0x1800846f7`
- `GDI32!DeleteObject` at `0x180084700`

## pseudocode

```c
__int64 __fastcall CImageList::_Read(CImageList *this, const struct _ILFILEHEADER *a2, HBITMAP a3, HBITMAP a4)
{
  int v8; // r14d
  HDC v9; // rcx
  __int64 v10; // rax
  int v11; // ebx

  v8 = CImageList::Initialize(
         this,
         *((__int16 *)a2 + 5),
         *((__int16 *)a2 + 6),
         *((__int16 *)a2 + 9),
         1,
         *((__int16 *)a2 + 4));
  if ( v8 < 0 )
  {
    DeleteObject(a3);
    DeleteObject(a4);
  }
  else
  {
    SelectObject(*((HDC *)this + 15), a3);
    DeleteObject(*((HGDIOBJ *)this + 13));
    v9 = (HDC)*((_QWORD *)this + 16);
    *((_QWORD *)this + 13) = a3;
    *((_DWORD *)this + 21) = -1;
    if ( v9 )
    {
      SelectObject(v9, a4);
      DeleteObject(*((HGDIOBJ *)this + 14));
      *((_QWORD *)this + 14) = a4;
    }
    *((_DWORD *)this + 15) = *((__int16 *)a2 + 3);
    *((_DWORD *)this + 14) = 0;
    CImageList::_SetBkColor(this, *(_DWORD *)((char *)a2 + 14));
    *((_DWORD *)this + 14) = *((__int16 *)a2 + 2);
    v10 = 0;
    do
    {
      v11 = v10 + 1;
      CImageList::_SetOverlayImage(this, *((__int16 *)a2 + v10 + 10), v10 + 1);
      v10 = (unsigned int)v11;
    }
    while ( v11 < 15 );
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008462c  push    rbx
0x18008462e  push    rbp
0x18008462f  push    rsi
0x180084630  push    rdi
0x180084631  push    r14
0x180084633  sub     rsp, 30h
0x180084637  movsx   eax, word ptr [rdx+8]
0x18008463b  mov     rbx, r9
0x18008463e  movsx   r9d, word ptr [rdx+12h]; unsigned int
0x180084643  mov     rbp, r8
0x180084646  movsx   r8d, word ptr [rdx+0Ch]; int
0x18008464b  mov     rsi, rdx
0x18008464e  movsx   edx, word ptr [rdx+0Ah]; int
0x180084652  mov     rdi, rcx
0x180084655  mov     [rsp+58h+var_30], eax; int
0x180084659  mov     [rsp+58h+var_38], 1; int
0x180084661  call    ?Initialize@CImageList@@QEAAJHHIHH@Z; CImageList::Initialize(int,int,uint,int,int)
0x180084666  mov     r14d, eax
0x180084669  test    eax, eax
0x18008466b  js      loc_1800846F4
0x180084671  mov     rcx, [rdi+78h]; hdc
0x180084675  mov     rdx, rbp; h
0x180084678  call    cs:__imp_SelectObject
0x18008467e  mov     rcx, [rdi+68h]; ho
0x180084682  call    cs:__imp_DeleteObject
0x180084688  mov     rcx, [rdi+80h]; hdc
0x18008468f  mov     [rdi+68h], rbp
0x180084693  mov     dword ptr [rdi+54h], 0FFFFFFFFh
0x18008469a  test    rcx, rcx
0x18008469d  jz      short loc_1800846B6
0x18008469f  mov     rdx, rbx; h
0x1800846a2  call    cs:__imp_SelectObject
0x1800846a8  mov     rcx, [rdi+70h]; ho
0x1800846ac  call    cs:__imp_DeleteObject
0x1800846b2  mov     [rdi+70h], rbx
0x1800846b6  movsx   eax, word ptr [rsi+6]
0x1800846ba  mov     rcx, rdi; this
0x1800846bd  mov     [rdi+3Ch], eax
0x1800846c0  mov     dword ptr [rdi+38h], 0
0x1800846c7  mov     edx, [rsi+0Eh]; color
0x1800846ca  call    ?_SetBkColor@CImageList@@QEAAKK@Z; CImageList::_SetBkColor(ulong)
0x1800846cf  movsx   eax, word ptr [rsi+4]
0x1800846d3  mov     [rdi+38h], eax
0x1800846d6  xor     eax, eax
0x1800846d8  movsx   edx, word ptr [rsi+rax*2+14h]; int
0x1800846dd  lea     ebx, [rax+1]
0x1800846e0  mov     r8d, ebx; int
0x1800846e3  mov     rcx, rdi; this
0x1800846e6  call    ?_SetOverlayImage@CImageList@@QEAAJHH@Z; CImageList::_SetOverlayImage(int,int)
0x1800846eb  mov     eax, ebx
0x1800846ed  cmp     ebx, 0Fh
0x1800846f0  jl      short loc_1800846D8
0x1800846f2  jmp     short loc_180084706
0x1800846f4  mov     rcx, rbp; ho
0x1800846f7  call    cs:__imp_DeleteObject
0x1800846fd  mov     rcx, rbx; ho
0x180084700  call    cs:__imp_DeleteObject
0x180084706  mov     eax, r14d
0x180084709  add     rsp, 30h
0x18008470d  pop     r14
0x18008470f  pop     rdi
0x180084710  pop     rsi
0x180084711  pop     rbp
0x180084712  pop     rbx
0x180084713  retn
```
