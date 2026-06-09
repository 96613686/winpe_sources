# ImageList_LoadImageAndMirror(HINSTANCE__ *,ushort const *,int,int,ulong,uint,uint)

- ea: `0x180049c3c`
- end: `0x180049cff`
- name: `?ImageList_LoadImageAndMirror@@YAPEAU_IMAGELIST@@PEAUHINSTANCE__@@PEBGHHKII@Z`
- size: `195`
- prototype: `struct _IMAGELIST *__fastcall(HINSTANCE, const unsigned __int16 *, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003133c`

## callees

- `0x180049c3c`
- `0x180060888`
- `0x1800608f8`
- `0x180060960`

## import_xrefs

- `USER32!LoadImageW` at `0x180049c66`
- `USER32!LoadImageW` at `0x180049c66`
- `GDI32!GetObjectW` at `0x180049c7f`
- `GDI32!GetObjectW` at `0x180049c7f`
- `GDI32!DeleteObject` at `0x180049ceb`
- `GDI32!DeleteObject` at `0x180049ceb`

## pseudocode

```c
struct _IMAGELIST *__fastcall ImageList_LoadImageAndMirror(HINSTANCE a1, const unsigned __int16 *a2)
{
  struct _IMAGELIST *v2; // rbx
  HBITMAP ImageW; // rax
  HBITMAP v4; // rdi
  int v5; // r8d
  struct _IMAGELIST *v6; // rax
  __int128 pv; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+40h] [rbp-18h]

  v2 = 0;
  pv = 0;
  v9 = 0;
  ImageW = (HBITMAP)LoadImageW(a1, (LPCWSTR)0x8FF, 0, 0, 0, 0);
  v4 = ImageW;
  if ( ImageW )
  {
    if ( GetObjectW(ImageW, 32, &pv) == 32 )
    {
      v5 = 1;
      if ( *((_QWORD *)&v9 + 1) )
        v5 = BYTE2(v9) & 0xFE | 1;
      v6 = ImageList_Create(16, SDWORD2(pv), v5 | 0x2000u, SDWORD1(pv) / 16, 0);
      v2 = v6;
      if ( v6 && ImageList_AddMasked(v6, v4, 0x1000006u) < 0 )
      {
        ImageList_Destroy(v2);
        v2 = 0;
      }
    }
    DeleteObject(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180049c3c  mov     rax, rsp
0x180049c3f  mov     [rax+8], rbx
0x180049c43  push    rdi
0x180049c44  sub     rsp, 50h
0x180049c48  xor     ebx, ebx
0x180049c4a  xorps   xmm0, xmm0
0x180049c4d  movups  xmmword ptr [rax-28h], xmm0
0x180049c51  movups  xmmword ptr [rax-18h], xmm0
0x180049c55  mov     [rax-30h], ebx
0x180049c58  mov     [rax-38h], ebx
0x180049c5b  xor     r9d, r9d; cx
0x180049c5e  xor     r8d, r8d; type
0x180049c61  mov     edx, 8FFh; name
0x180049c66  call    cs:__imp_LoadImageW
0x180049c6c  mov     rdi, rax
0x180049c6f  test    rax, rax
0x180049c72  jz      short loc_180049CF1
0x180049c74  lea     r8, [rsp+58h+pv]; pv
0x180049c79  lea     edx, [rbx+20h]; c
0x180049c7c  mov     rcx, rax; h
0x180049c7f  call    cs:__imp_GetObjectW
0x180049c85  cmp     eax, 20h ; ' '
0x180049c88  jnz     short loc_180049CE8
0x180049c8a  mov     eax, [rsp+58h+var_24]
0x180049c8e  cdq
0x180049c8f  lea     ecx, [rbx+10h]; cx
0x180049c92  idiv    ecx
0x180049c94  mov     r9d, eax; cInitial
0x180049c97  lea     r8d, [rbx+1]
0x180049c9b  cmp     [rsp+58h+var_10], rbx
0x180049ca0  jz      short loc_180049CAF
0x180049ca2  movzx   eax, [rsp+58h+var_16]
0x180049ca7  and     eax, 0FEh
0x180049cac  or      r8d, eax
0x180049caf  bts     r8d, 0Dh; flags
0x180049cb4  mov     [rsp+58h+cGrow], ebx; cGrow
0x180049cb8  mov     edx, [rsp+58h+cy]; cy
0x180049cbc  call    ImageList_Create
0x180049cc1  mov     rbx, rax
0x180049cc4  test    rax, rax
0x180049cc7  jz      short loc_180049CE8
0x180049cc9  mov     r8d, 1000006h; crMask
0x180049ccf  mov     rdx, rdi; hbmImage
0x180049cd2  mov     rcx, rax; himl
0x180049cd5  call    ImageList_AddMasked
0x180049cda  test    eax, eax
0x180049cdc  jns     short loc_180049CE8
0x180049cde  mov     rcx, rbx; himl
0x180049ce1  call    ImageList_Destroy
0x180049ce6  xor     ebx, ebx
0x180049ce8  mov     rcx, rdi; ho
0x180049ceb  call    cs:__imp_DeleteObject
0x180049cf1  mov     rax, rbx
0x180049cf4  mov     rbx, [rsp+58h+arg_0]
0x180049cf9  add     rsp, 50h
0x180049cfd  pop     rdi
0x180049cfe  retn
```
