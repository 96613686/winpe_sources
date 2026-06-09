# GpMetafile::SetData(uchar const *,uint)

- ea: `0x180085100`
- end: `0x180085221`
- name: `?SetData@GpMetafile@@UEAA?AW4Status@@PEBEI@Z`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180085100`
- `0x180085464`
- `0x180086d80`
- `0x1800894b8`

## import_xrefs

- `GDI32!SetMetaFileBitsEx` at `0x180085162`
- `GDI32!SetMetaFileBitsEx` at `0x180085162`
- `GDI32!SetEnhMetaFileBits` at `0x1800851ba`
- `GDI32!SetEnhMetaFileBits` at `0x1800851ba`
- `GDI32!DeleteMetaFile` at `0x1800851a5`
- `GDI32!DeleteMetaFile` at `0x1800851a5`
- `GDI32!DeleteEnhMetaFile` at `0x1800851ff`
- `GDI32!DeleteEnhMetaFile` at `0x1800851ff`

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
0x180085100  push    rbx
0x180085102  push    rbp
0x180085103  push    rsi
0x180085104  push    rdi
0x180085105  sub     rsp, 28h
0x180085109  mov     esi, r8d
0x18008510c  mov     rdi, rdx
0x18008510f  mov     rbx, rcx
0x180085112  call    ?InitDefaults@GpMetafile@@IEAAXXZ; GpMetafile::InitDefaults(void)
0x180085117  test    rdi, rdi
0x18008511a  jz      loc_180085212
0x180085120  cmp     esi, 10h
0x180085123  jb      loc_180085212
0x180085129  mov     eax, [rdi]
0x18008512b  and     eax, 0FFFFF000h
0x180085130  cmp     eax, 0DBC01000h
0x180085135  jnz     loc_180085212
0x18008513b  mov     ecx, [rdi+0Ch]; nSize
0x18008513e  lea     rbp, [rdi+10h]
0x180085142  add     esi, 0FFFFFFF0h
0x180085145  cmp     dword ptr [rdi+8], 2
0x180085149  jnz     short loc_1800851B3
0x18008514b  lea     eax, [rcx+18h]
0x18008514e  cmp     eax, ecx
0x180085150  jb      loc_180085212
0x180085156  cmp     esi, eax
0x180085158  jb      loc_180085212
0x18008515e  lea     rdx, [rbp+18h]; lpData
0x180085162  call    cs:__imp_SetMetaFileBitsEx
0x180085169  nop     dword ptr [rax+rax+00h]
0x18008516e  mov     rdi, rax
0x180085171  test    rax, rax
0x180085174  jz      loc_18008520B
0x18008517a  lea     r8, [rbx+20h]
0x18008517e  mov     rdx, rbp
0x180085181  mov     rcx, rax
0x180085184  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@AEAVMetafileHeader@@@Z; GetMetafileHeader(HMETAFILE__ *,WmfPlaceableFileHeader const *,MetafileHeader &)
0x180085189  test    eax, eax
0x18008518b  jnz     short loc_1800851A2
0x18008518d  mov     [rbx+0B8h], rdi
0x180085194  xor     eax, eax
0x180085196  mov     dword ptr [rbx+0B0h], 3
0x1800851a0  jmp     short loc_180085217
0x1800851a2  mov     rcx, rdi; hmf
0x1800851a5  call    cs:__imp_DeleteMetaFile
0x1800851ac  nop     dword ptr [rax+rax+00h]
0x1800851b1  jmp     short loc_18008520B
0x1800851b3  cmp     esi, ecx
0x1800851b5  jb      short loc_180085212
0x1800851b7  mov     rdx, rbp; pb
0x1800851ba  call    cs:__imp_SetEnhMetaFileBits
0x1800851c1  nop     dword ptr [rax+rax+00h]
0x1800851c6  mov     rdi, rax
0x1800851c9  test    rax, rax
0x1800851cc  jz      short loc_18008520B
0x1800851ce  lea     rdx, [rbx+20h]
0x1800851d2  mov     [rsp+48h+arg_8], 0
0x1800851da  lea     r8, [rsp+48h+arg_8]
0x1800851df  mov     rcx, rax
0x1800851e2  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x1800851e7  test    eax, eax
0x1800851e9  jz      short loc_18008518D
0x1800851eb  cmp     [rsp+48h+arg_8], 0
0x1800851f0  jz      short loc_1800851FC
0x1800851f2  mov     dword ptr [rbx+0B0h], 1
0x1800851fc  mov     rcx, rdi; hmf
0x1800851ff  call    cs:__imp_DeleteEnhMetaFile
0x180085206  nop     dword ptr [rax+rax+00h]
0x18008520b  mov     eax, 1
0x180085210  jmp     short loc_180085217
0x180085212  mov     eax, 2
0x180085217  add     rsp, 28h
0x18008521b  pop     rdi
0x18008521c  pop     rsi
0x18008521d  pop     rbp
0x18008521e  pop     rbx
0x18008521f  retn
```
