# LoadImageList32BitColors(HINSTANCE__ *,ushort const *,int)

- ea: `0x140097c30`
- end: `0x140097cc7`
- name: `?LoadImageList32BitColors@@YAPEAU_IMAGELIST@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `151`
- prototype: `struct _IMAGELIST *(HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020338`
- `0x1400238a0`
- `0x140049b18`
- `0x140049fa0`

## callees

- `0x140097b90`
- `0x140097c30`

## import_xrefs

- `GDI32!GetObjectW` at `0x140097c6d`
- `GDI32!GetObjectW` at `0x140097c6d`
- `GDI32!DeleteObject` at `0x140097cae`
- `GDI32!DeleteObject` at `0x140097cae`
- `COMCTL32!ImageList_Create` at `0x140097c8e`
- `COMCTL32!ImageList_Create` at `0x140097c8e`
- `COMCTL32!ImageList_Add` at `0x140097ca5`
- `COMCTL32!ImageList_Add` at `0x140097ca5`

## pseudocode

```c
struct _IMAGELIST *__fastcall LoadImageList32BitColors(HINSTANCE a1, const unsigned __int16 *a2, int a3)
{
  struct _IMAGELIST *v4; // rdi
  HBITMAP ImageFromResID; // rax
  HBITMAP v6; // rbx
  struct _IMAGELIST *v7; // rax
  _OWORD pv[2]; // [rsp+30h] [rbp-28h] BYREF

  v4 = 0;
  ImageFromResID = LoadImageFromResID(a1, a2);
  v6 = ImageFromResID;
  if ( ImageFromResID )
  {
    memset(pv, 0, sizeof(pv));
    GetObjectW(ImageFromResID, 32, pv);
    v7 = ImageList_Create(a3, SDWORD2(pv[0]), 0x20u, SDWORD1(pv[0]) / a3, 0);
    v4 = v7;
    if ( v7 )
      ImageList_Add(v7, v6, 0);
    DeleteObject(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x140097c30  mov     [rsp+arg_0], rbx
0x140097c35  mov     [rsp+arg_8], rsi
0x140097c3a  push    rdi
0x140097c3b  sub     rsp, 50h
0x140097c3f  mov     esi, r8d
0x140097c42  xor     edi, edi
0x140097c44  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x140097c49  mov     rbx, rax
0x140097c4c  test    rax, rax
0x140097c4f  jz      short loc_140097CB4
0x140097c51  xorps   xmm0, xmm0
0x140097c54  lea     r8, [rsp+58h+pv]; pv
0x140097c59  mov     edi, 20h ; ' '
0x140097c5e  mov     rcx, rax; h
0x140097c61  mov     edx, edi; c
0x140097c63  movups  [rsp+58h+pv], xmm0
0x140097c68  movups  [rsp+58h+var_18], xmm0
0x140097c6d  call    cs:__imp_GetObjectW
0x140097c73  mov     eax, dword ptr [rsp+58h+pv+4]
0x140097c77  mov     r8d, edi; flags
0x140097c7a  cdq
0x140097c7b  mov     [rsp+58h+cGrow], 0; cGrow
0x140097c83  idiv    esi
0x140097c85  mov     edx, dword ptr [rsp+58h+pv+8]; cy
0x140097c89  mov     ecx, esi; cx
0x140097c8b  mov     r9d, eax; cInitial
0x140097c8e  call    cs:__imp_ImageList_Create
0x140097c94  mov     rdi, rax
0x140097c97  test    rax, rax
0x140097c9a  jz      short loc_140097CAB
0x140097c9c  xor     r8d, r8d; hbmMask
0x140097c9f  mov     rdx, rbx; hbmImage
0x140097ca2  mov     rcx, rax; himl
0x140097ca5  call    cs:__imp_ImageList_Add
0x140097cab  mov     rcx, rbx; ho
0x140097cae  call    cs:__imp_DeleteObject
0x140097cb4  mov     rbx, [rsp+58h+arg_0]
0x140097cb9  mov     rax, rdi
0x140097cbc  mov     rsi, [rsp+58h+arg_8]
0x140097cc1  add     rsp, 50h
0x140097cc5  pop     rdi
0x140097cc6  retn
```
