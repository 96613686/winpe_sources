# LoadImageList32BitColors(HINSTANCE__ *,ushort const *,int)

- ea: `0x140095ac0`
- end: `0x140095b57`
- name: `?LoadImageList32BitColors@@YAPEAU_IMAGELIST@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `151`
- prototype: `struct _IMAGELIST *(HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020338`
- `0x1400238a0`
- `0x1400479a8`
- `0x140047e30`

## callees

- `0x140095a20`
- `0x140095ac0`

## import_xrefs

- `GDI32!GetObjectW` at `0x140095afd`
- `GDI32!GetObjectW` at `0x140095afd`
- `GDI32!DeleteObject` at `0x140095b3e`
- `GDI32!DeleteObject` at `0x140095b3e`
- `COMCTL32!ImageList_Create` at `0x140095b1e`
- `COMCTL32!ImageList_Create` at `0x140095b1e`
- `COMCTL32!ImageList_Add` at `0x140095b35`
- `COMCTL32!ImageList_Add` at `0x140095b35`

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
0x140095ac0  mov     [rsp+arg_0], rbx
0x140095ac5  mov     [rsp+arg_8], rsi
0x140095aca  push    rdi
0x140095acb  sub     rsp, 50h
0x140095acf  mov     esi, r8d
0x140095ad2  xor     edi, edi
0x140095ad4  call    ?LoadImageFromResID@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEBG@Z; LoadImageFromResID(HINSTANCE__ *,ushort const *)
0x140095ad9  mov     rbx, rax
0x140095adc  test    rax, rax
0x140095adf  jz      short loc_140095B44
0x140095ae1  xorps   xmm0, xmm0
0x140095ae4  lea     r8, [rsp+58h+pv]; pv
0x140095ae9  mov     edi, 20h ; ' '
0x140095aee  mov     rcx, rax; h
0x140095af1  mov     edx, edi; c
0x140095af3  movups  [rsp+58h+pv], xmm0
0x140095af8  movups  [rsp+58h+var_18], xmm0
0x140095afd  call    cs:__imp_GetObjectW
0x140095b03  mov     eax, dword ptr [rsp+58h+pv+4]
0x140095b07  mov     r8d, edi; flags
0x140095b0a  cdq
0x140095b0b  mov     [rsp+58h+cGrow], 0; cGrow
0x140095b13  idiv    esi
0x140095b15  mov     edx, dword ptr [rsp+58h+pv+8]; cy
0x140095b19  mov     ecx, esi; cx
0x140095b1b  mov     r9d, eax; cInitial
0x140095b1e  call    cs:__imp_ImageList_Create
0x140095b24  mov     rdi, rax
0x140095b27  test    rax, rax
0x140095b2a  jz      short loc_140095B3B
0x140095b2c  xor     r8d, r8d; hbmMask
0x140095b2f  mov     rdx, rbx; hbmImage
0x140095b32  mov     rcx, rax; himl
0x140095b35  call    cs:__imp_ImageList_Add
0x140095b3b  mov     rcx, rbx; ho
0x140095b3e  call    cs:__imp_DeleteObject
0x140095b44  mov     rbx, [rsp+58h+arg_0]
0x140095b49  mov     rax, rdi
0x140095b4c  mov     rsi, [rsp+58h+arg_8]
0x140095b51  add     rsp, 50h
0x140095b55  pop     rdi
0x140095b56  retn
```
