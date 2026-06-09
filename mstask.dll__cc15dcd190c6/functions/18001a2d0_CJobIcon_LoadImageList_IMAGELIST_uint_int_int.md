# CJobIcon::LoadImageList(_IMAGELIST * *,uint,int,int)

- ea: `0x18001a2d0`
- end: `0x18001a39a`
- name: `?LoadImageList@CJobIcon@@AEAA_NPEAPEAU_IMAGELIST@@IHH@Z`
- size: `202`
- prototype: `bool(CJobIcon *__hidden this, struct _IMAGELIST **, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a238`

## callees

- `0x18001a2d0`

## import_xrefs

- `USER32!LoadImageW` at `0x18001a32c`
- `USER32!LoadImageW` at `0x18001a32c`
- `GDI32!DeleteObject` at `0x18001a351`
- `GDI32!DeleteObject` at `0x18001a351`
- `COMCTL32!ImageList_AddMasked` at `0x18001a346`
- `COMCTL32!ImageList_AddMasked` at `0x18001a346`
- `COMCTL32!ImageList_Create` at `0x18001a2fe`
- `COMCTL32!ImageList_Create` at `0x18001a2fe`
- `COMCTL32!ImageList_SetOverlayImage` at `0x18001a365`
- `COMCTL32!ImageList_SetOverlayImage` at `0x18001a37b`
- `COMCTL32!ImageList_SetOverlayImage` at `0x18001a365`
- `COMCTL32!ImageList_SetOverlayImage` at `0x18001a37b`

## pseudocode

```c
bool __fastcall CJobIcon::LoadImageList(CJobIcon *this, struct _IMAGELIST **a2, unsigned __int16 a3, int a4, int cy)
{
  struct _IMAGELIST *v7; // rax
  HBITMAP ImageW; // rax
  HBITMAP v9; // rsi
  int v10; // ebx
  bool result; // al

  v7 = ImageList_Create(a4, cy, 0x21u, 1, 1);
  *a2 = v7;
  result = v7
        && (ImageW = (HBITMAP)LoadImageW(g_hInstance, (LPCWSTR)a3, 0, 0, 0, 0), (v9 = ImageW) != 0)
        && (v10 = ImageList_AddMasked(*a2, ImageW, 0xFF00u), DeleteObject(v9), v10 != -1)
        && ImageList_SetOverlayImage(*a2, 0, 1)
        && ImageList_SetOverlayImage(*a2, 1, 2);
  return result;
}

```

## disassembly

```asm
0x18001a2d0  mov     [rsp+arg_0], rbx
0x18001a2d5  mov     [rsp+arg_8], rsi
0x18001a2da  push    rdi
0x18001a2db  sub     rsp, 30h
0x18001a2df  mov     ecx, r9d; cx
0x18001a2e2  mov     ebx, r8d
0x18001a2e5  mov     r9d, 1; cInitial
0x18001a2eb  mov     [rsp+38h+cGrow], 1; cGrow
0x18001a2f3  mov     rdi, rdx
0x18001a2f6  mov     edx, [rsp+38h+cy]; cy
0x18001a2fa  lea     r8d, [r9+20h]; flags
0x18001a2fe  call    cs:__imp_ImageList_Create
0x18001a304  mov     [rdi], rax
0x18001a307  test    rax, rax
0x18001a30a  jz      short loc_18001A388
0x18001a30c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInst
0x18001a313  xor     r9d, r9d; cx
0x18001a316  movzx   edx, bx; name
0x18001a319  xor     r8d, r8d; type
0x18001a31c  mov     [rsp+38h+fuLoad], 0; fuLoad
0x18001a324  mov     [rsp+38h+cGrow], 0; cy
0x18001a32c  call    cs:__imp_LoadImageW
0x18001a332  mov     rsi, rax
0x18001a335  test    rax, rax
0x18001a338  jz      short loc_18001A388
0x18001a33a  mov     rcx, [rdi]; himl
0x18001a33d  mov     r8d, 0FF00h; crMask
0x18001a343  mov     rdx, rax; hbmImage
0x18001a346  call    cs:__imp_ImageList_AddMasked
0x18001a34c  mov     rcx, rsi; ho
0x18001a34f  mov     ebx, eax
0x18001a351  call    cs:__imp_DeleteObject
0x18001a357  cmp     ebx, 0FFFFFFFFh
0x18001a35a  jz      short loc_18001A388
0x18001a35c  mov     rcx, [rdi]; himl
0x18001a35f  xor     edx, edx; iImage
0x18001a361  lea     r8d, [rdx+1]; iOverlay
0x18001a365  call    cs:__imp_ImageList_SetOverlayImage
0x18001a36b  test    eax, eax
0x18001a36d  jz      short loc_18001A388
0x18001a36f  mov     rcx, [rdi]; himl
0x18001a372  mov     edx, 1; iImage
0x18001a377  lea     r8d, [rdx+1]; iOverlay
0x18001a37b  call    cs:__imp_ImageList_SetOverlayImage
0x18001a381  test    eax, eax
0x18001a383  setnz   al
0x18001a386  jmp     short loc_18001A38A
0x18001a388  xor     al, al
0x18001a38a  mov     rbx, [rsp+38h+arg_0]
0x18001a38f  mov     rsi, [rsp+38h+arg_8]
0x18001a394  add     rsp, 30h
0x18001a398  pop     rdi
0x18001a399  retn
```
