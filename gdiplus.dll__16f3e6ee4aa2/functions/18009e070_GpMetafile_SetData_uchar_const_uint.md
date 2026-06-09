# GpMetafile::SetData(uchar const *,uint)

- ea: `0x18009e070`
- end: `0x18009e174`
- name: `?SetData@GpMetafile@@UEAA?AW4Status@@PEBEI@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180098e7c`
- `0x18009b98c`
- `0x18009ce90`
- `0x18009e070`

## import_xrefs

- `GDI32!SetMetaFileBitsEx` at `0x18009e0d2`
- `GDI32!SetMetaFileBitsEx` at `0x18009e0d2`
- `GDI32!SetEnhMetaFileBits` at `0x18009e11a`
- `GDI32!SetEnhMetaFileBits` at `0x18009e11a`
- `GDI32!DeleteMetaFile` at `0x18009e10b`
- `GDI32!DeleteMetaFile` at `0x18009e10b`
- `GDI32!DeleteEnhMetaFile` at `0x18009e159`
- `GDI32!DeleteEnhMetaFile` at `0x18009e159`

## pseudocode

```c
__int64 __fastcall GpMetafile::SetData(__int64 a1, __int64 a2, unsigned int a3)
{
  UINT v6; // ecx
  __int64 v7; // rbp
  unsigned int v8; // esi
  HMETAFILE v9; // rax
  HENHMETAFILE v10; // rdi
  __int64 result; // rax
  HENHMETAFILE v12; // rax
  int v13; // [rsp+58h] [rbp+10h] BYREF

  GpMetafile::InitDefaults((GpMetafile *)a1);
  if ( a2 && a3 >= 0x10 && (*(_DWORD *)a2 & 0xFFFFF000) == 0xDBC01000 )
  {
    v6 = *(_DWORD *)(a2 + 12);
    v7 = a2 + 16;
    v8 = a3 - 16;
    if ( *(_DWORD *)(a2 + 8) == 2 )
    {
      if ( v6 + 24 >= v6 && v8 >= v6 + 24 )
      {
        v9 = SetMetaFileBitsEx(v6, (const BYTE *)(a2 + 40));
        v10 = (HENHMETAFILE)v9;
        if ( v9 )
        {
          if ( !(unsigned int)GetMetafileHeader(v9, v7, a1 + 32) )
          {
LABEL_9:
            *(_QWORD *)(a1 + 184) = v10;
            result = 0;
            *(_DWORD *)(a1 + 176) = 3;
            return result;
          }
          DeleteMetaFile((HMETAFILE)v10);
        }
        return 1;
      }
    }
    else if ( v8 >= v6 )
    {
      v12 = SetEnhMetaFileBits(v6, (const BYTE *)(a2 + 16));
      v10 = v12;
      if ( v12 )
      {
        v13 = 0;
        if ( !(unsigned int)GetMetafileHeader(v12, a1 + 32, &v13) )
          goto LABEL_9;
        if ( v13 )
          *(_DWORD *)(a1 + 176) = 1;
        DeleteEnhMetaFile(v10);
      }
      return 1;
    }
  }
  return 2;
}

```

## disassembly

```asm
0x18009e070  push    rbx
0x18009e072  push    rbp
0x18009e073  push    rsi
0x18009e074  push    rdi
0x18009e075  sub     rsp, 28h
0x18009e079  mov     esi, r8d
0x18009e07c  mov     rdi, rdx
0x18009e07f  mov     rbx, rcx
0x18009e082  call    ?InitDefaults@GpMetafile@@IEAAXXZ; GpMetafile::InitDefaults(void)
0x18009e087  test    rdi, rdi
0x18009e08a  jz      loc_18009E166
0x18009e090  cmp     esi, 10h
0x18009e093  jb      loc_18009E166
0x18009e099  mov     eax, [rdi]
0x18009e09b  and     eax, 0FFFFF000h
0x18009e0a0  cmp     eax, 0DBC01000h
0x18009e0a5  jnz     loc_18009E166
0x18009e0ab  mov     ecx, [rdi+0Ch]; nSize
0x18009e0ae  lea     rbp, [rdi+10h]
0x18009e0b2  add     esi, 0FFFFFFF0h
0x18009e0b5  cmp     dword ptr [rdi+8], 2
0x18009e0b9  jnz     short loc_18009E113
0x18009e0bb  lea     eax, [rcx+18h]
0x18009e0be  cmp     eax, ecx
0x18009e0c0  jb      loc_18009E166
0x18009e0c6  cmp     esi, eax
0x18009e0c8  jb      loc_18009E166
0x18009e0ce  lea     rdx, [rbp+18h]; lpData
0x18009e0d2  call    cs:__imp_SetMetaFileBitsEx
0x18009e0d8  mov     rdi, rax
0x18009e0db  test    rax, rax
0x18009e0de  jz      short loc_18009E15F
0x18009e0e0  lea     r8, [rbx+20h]
0x18009e0e4  mov     rdx, rbp
0x18009e0e7  mov     rcx, rax
0x18009e0ea  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@AEAVMetafileHeader@@@Z; GetMetafileHeader(HMETAFILE__ *,WmfPlaceableFileHeader const *,MetafileHeader &)
0x18009e0ef  test    eax, eax
0x18009e0f1  jnz     short loc_18009E108
0x18009e0f3  mov     [rbx+0B8h], rdi
0x18009e0fa  xor     eax, eax
0x18009e0fc  mov     dword ptr [rbx+0B0h], 3
0x18009e106  jmp     short loc_18009E16B
0x18009e108  mov     rcx, rdi; hmf
0x18009e10b  call    cs:__imp_DeleteMetaFile
0x18009e111  jmp     short loc_18009E15F
0x18009e113  cmp     esi, ecx
0x18009e115  jb      short loc_18009E166
0x18009e117  mov     rdx, rbp; pb
0x18009e11a  call    cs:__imp_SetEnhMetaFileBits
0x18009e120  mov     rdi, rax
0x18009e123  test    rax, rax
0x18009e126  jz      short loc_18009E15F
0x18009e128  lea     rdx, [rbx+20h]
0x18009e12c  mov     [rsp+48h+arg_8], 0
0x18009e134  lea     r8, [rsp+48h+arg_8]
0x18009e139  mov     rcx, rax
0x18009e13c  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x18009e141  test    eax, eax
0x18009e143  jz      short loc_18009E0F3
0x18009e145  cmp     [rsp+48h+arg_8], 0
0x18009e14a  jz      short loc_18009E156
0x18009e14c  mov     dword ptr [rbx+0B0h], 1
0x18009e156  mov     rcx, rdi; hmf
0x18009e159  call    cs:__imp_DeleteEnhMetaFile
0x18009e15f  mov     eax, 1
0x18009e164  jmp     short loc_18009E16B
0x18009e166  mov     eax, 2
0x18009e16b  add     rsp, 28h
0x18009e16f  pop     rdi
0x18009e170  pop     rsi
0x18009e171  pop     rbp
0x18009e172  pop     rbx
0x18009e173  retn
```
