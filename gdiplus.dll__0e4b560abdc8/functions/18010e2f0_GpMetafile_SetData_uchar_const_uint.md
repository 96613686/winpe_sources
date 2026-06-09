# GpMetafile::SetData(uchar const *,uint)

- ea: `0x18010e2f0`
- end: `0x18010e422`
- name: `?SetData@GpMetafile@@UEAA?AW4Status@@PEBEI@Z`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b83c`
- `0x1800a723c`
- `0x1800a7638`
- `0x18010e2f0`

## import_xrefs

- `GDI32!SetMetaFileBitsEx` at `0x18010e354`
- `GDI32!SetMetaFileBitsEx` at `0x18010e354`
- `GDI32!SetEnhMetaFileBits` at `0x18010e3ae`
- `GDI32!SetEnhMetaFileBits` at `0x18010e3ae`
- `GDI32!DeleteMetaFile` at `0x18010e398`
- `GDI32!DeleteMetaFile` at `0x18010e398`
- `GDI32!DeleteEnhMetaFile` at `0x18010e3f9`
- `GDI32!DeleteEnhMetaFile` at `0x18010e3f9`

## pseudocode

```c
__int64 __fastcall GpMetafile::SetData(__int64 a1, __int64 a2, unsigned int a3)
{
  UINT v6; // ecx
  unsigned int v7; // esi
  HMETAFILE v8; // rax
  HMETAFILE v9; // rsi
  HENHMETAFILE v11; // rax
  HENHMETAFILE v12; // rdi
  int v13; // [rsp+38h] [rbp+10h] BYREF

  GpMetafile::InitDefaults((GpMetafile *)a1);
  if ( a2 && a3 >= 0x10 && (*(_DWORD *)a2 & 0xFFFFF000) == 0xDBC01000 )
  {
    v6 = *(_DWORD *)(a2 + 12);
    v7 = a3 - 16;
    if ( *(_DWORD *)(a2 + 8) == 2 )
    {
      if ( v6 + 24 >= v6 && v7 >= v6 + 24 )
      {
        v8 = SetMetaFileBitsEx(v6, (const BYTE *)(a2 + 40));
        v9 = v8;
        if ( v8 )
        {
          if ( !(unsigned int)GetMetafileHeader(v8, a2 + 16, a1 + 32) )
          {
            *(_QWORD *)(a1 + 184) = v9;
LABEL_10:
            *(_DWORD *)(a1 + 176) = 3;
            return 0;
          }
          DeleteMetaFile(v9);
        }
        return 1;
      }
    }
    else if ( v7 >= v6 )
    {
      v11 = SetEnhMetaFileBits(v6, (const BYTE *)(a2 + 16));
      v12 = v11;
      if ( v11 )
      {
        v13 = 0;
        if ( !(unsigned int)GetMetafileHeader(v11, a1 + 32, &v13) )
        {
          *(_QWORD *)(a1 + 184) = v12;
          goto LABEL_10;
        }
        if ( v13 )
          *(_DWORD *)(a1 + 176) = 1;
        DeleteEnhMetaFile(v12);
      }
      return 1;
    }
  }
  return 2;
}

```

## disassembly

```asm
0x18010e2f0  mov     [rsp+arg_0], rbx
0x18010e2f5  mov     [rsp+arg_10], rsi
0x18010e2fa  push    rdi
0x18010e2fb  sub     rsp, 20h
0x18010e2ff  mov     esi, r8d
0x18010e302  mov     rdi, rdx
0x18010e305  mov     rbx, rcx
0x18010e308  call    ?InitDefaults@GpMetafile@@IEAAXXZ; GpMetafile::InitDefaults(void)
0x18010e30d  test    rdi, rdi
0x18010e310  jz      loc_18010E40C
0x18010e316  cmp     esi, 10h
0x18010e319  jb      loc_18010E40C
0x18010e31f  mov     eax, [rdi]
0x18010e321  and     eax, 0FFFFF000h
0x18010e326  cmp     eax, 0DBC01000h
0x18010e32b  jnz     loc_18010E40C
0x18010e331  mov     ecx, [rdi+0Ch]; nSize
0x18010e334  add     esi, 0FFFFFFF0h
0x18010e337  cmp     dword ptr [rdi+8], 2
0x18010e33b  jnz     short loc_18010E3A6
0x18010e33d  lea     eax, [rcx+18h]
0x18010e340  cmp     eax, ecx
0x18010e342  jb      loc_18010E40C
0x18010e348  cmp     esi, eax
0x18010e34a  jb      loc_18010E40C
0x18010e350  lea     rdx, [rdi+28h]; lpData
0x18010e354  call    cs:__imp_SetMetaFileBitsEx
0x18010e35b  nop     dword ptr [rax+rax+00h]
0x18010e360  mov     rsi, rax
0x18010e363  test    rax, rax
0x18010e366  jz      loc_18010E405
0x18010e36c  lea     r8, [rbx+20h]
0x18010e370  mov     rcx, rax
0x18010e373  lea     rdx, [rdi+10h]
0x18010e377  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@AEAVMetafileHeader@@@Z; GetMetafileHeader(HMETAFILE__ *,WmfPlaceableFileHeader const *,MetafileHeader &)
0x18010e37c  test    eax, eax
0x18010e37e  jnz     short loc_18010E395
0x18010e380  mov     [rbx+0B8h], rsi
0x18010e387  mov     dword ptr [rbx+0B0h], 3
0x18010e391  xor     eax, eax
0x18010e393  jmp     short loc_18010E411
0x18010e395  mov     rcx, rsi; hmf
0x18010e398  call    cs:__imp_DeleteMetaFile
0x18010e39f  nop     dword ptr [rax+rax+00h]
0x18010e3a4  jmp     short loc_18010E405
0x18010e3a6  cmp     esi, ecx
0x18010e3a8  jb      short loc_18010E40C
0x18010e3aa  lea     rdx, [rdi+10h]; pb
0x18010e3ae  call    cs:__imp_SetEnhMetaFileBits
0x18010e3b5  nop     dword ptr [rax+rax+00h]
0x18010e3ba  mov     rdi, rax
0x18010e3bd  test    rax, rax
0x18010e3c0  jz      short loc_18010E405
0x18010e3c2  and     [rsp+28h+arg_8], 0
0x18010e3c7  lea     rdx, [rbx+20h]
0x18010e3cb  lea     r8, [rsp+28h+arg_8]
0x18010e3d0  mov     rcx, rax
0x18010e3d3  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x18010e3d8  test    eax, eax
0x18010e3da  jnz     short loc_18010E3E5
0x18010e3dc  mov     [rbx+0B8h], rdi
0x18010e3e3  jmp     short loc_18010E387
0x18010e3e5  cmp     [rsp+28h+arg_8], 0
0x18010e3ea  jz      short loc_18010E3F6
0x18010e3ec  mov     dword ptr [rbx+0B0h], 1
0x18010e3f6  mov     rcx, rdi; hmf
0x18010e3f9  call    cs:__imp_DeleteEnhMetaFile
0x18010e400  nop     dword ptr [rax+rax+00h]
0x18010e405  mov     eax, 1
0x18010e40a  jmp     short loc_18010E411
0x18010e40c  mov     eax, 2
0x18010e411  mov     rbx, [rsp+28h+arg_0]
0x18010e416  mov     rsi, [rsp+28h+arg_10]
0x18010e41b  add     rsp, 20h
0x18010e41f  pop     rdi
0x18010e420  retn
```
