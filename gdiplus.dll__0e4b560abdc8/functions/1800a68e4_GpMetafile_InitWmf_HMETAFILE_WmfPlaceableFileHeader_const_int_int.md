# GpMetafile::InitWmf(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)

- ea: `0x1800a68e4`
- end: `0x1800a6a94`
- name: `?InitWmf@GpMetafile@@IEAAXPEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z`
- size: `432`
- prototype: `void(GpMetafile *__hidden this, HMETAFILE, const struct WmfPlaceableFileHeader *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ddc`
- `0x18000adac`

## callees

- `0x18001f950`
- `0x1800a68e4`
- `0x1800a6a9c`
- `0x1800a723c`
- `0x1800a7638`
- `0x1800a774c`
- `0x1800e5044`

## import_xrefs

- `GDI32!GetMetaFileBitsEx` at `0x1800a6925`
- `GDI32!GetMetaFileBitsEx` at `0x1800a6957`
- `GDI32!GetMetaFileBitsEx` at `0x1800a6925`
- `GDI32!GetMetaFileBitsEx` at `0x1800a6957`
- `GDI32!DeleteMetaFile` at `0x1800a6a83`
- `GDI32!DeleteMetaFile` at `0x1800a6a83`
- `GDI32!DeleteEnhMetaFile` at `0x1800a6a6f`
- `GDI32!DeleteEnhMetaFile` at `0x1800a6a6f`

## pseudocode

```c
void __fastcall GpMetafile::InitWmf(
        GpMetafile *this,
        HMETAFILE a2,
        const struct WmfPlaceableFileHeader *a3,
        int a4,
        int a5)
{
  int v5; // ebx
  const struct WmfPlaceableFileHeader *v7; // r10
  __int16 *v10; // rbp
  UINT MetaFileBits; // eax
  unsigned int v12; // r15d
  void *v13; // rax
  __int64 v14; // r14
  HENHMETAFILE EmfFromWmfData; // rax
  HENHMETAFILE v16; // rbp
  __int16 *v17; // r10
  int v18; // [rsp+70h] [rbp+18h] BYREF

  v5 = 0;
  v7 = a3;
  if ( a3 && (unsigned int)WmfPlaceableHeaderIsValid(a3) && !a5 )
  {
    if ( !(unsigned int)GetMetafileHeader(a2, v7, (char *)this + 32) )
    {
      *((_QWORD *)this + 23) = a2;
      *((_DWORD *)this + 44) = 3;
      LOBYTE(v5) = a4 != 0;
      *((_DWORD *)this + 57) = v5;
      return;
    }
    *((_DWORD *)this + 44) = 1;
  }
  else
  {
    v10 = 0;
    if ( v7 && (unsigned int)WmfPlaceableHeaderIsValid(v7) )
      v10 = v17;
    MetaFileBits = GetMetaFileBitsEx(a2, 0, 0);
    v12 = MetaFileBits;
    if ( MetaFileBits )
    {
      v13 = (void *)GpMallocEx(MetaFileBits, 0);
      v14 = (__int64)v13;
      if ( v13 )
      {
        if ( (int)GetMetaFileBitsEx(a2, v12, v13) > 0 )
        {
          EmfFromWmfData = GetEmfFromWmfData(a2, v10, v14, v12, *((_DWORD *)this + 61));
          v16 = EmfFromWmfData;
          if ( EmfFromWmfData )
          {
            v18 = 0;
            if ( (unsigned int)GetMetafileHeader(EmfFromWmfData, (char *)this + 32, &v18) )
            {
              if ( v18 )
                *((_DWORD *)this + 44) = 1;
              DeleteEnhMetaFile(v16);
            }
            else
            {
              *((_DWORD *)this + 57) = 1;
              *((_QWORD *)this + 23) = v16;
              *((_DWORD *)this + 44) = 3;
            }
          }
        }
        GpFree(v14);
      }
    }
  }
  if ( a4 )
    DeleteMetaFile(a2);
}

```

## disassembly

```asm
0x1800a68e4  mov     [rsp+arg_0], rbx
0x1800a68e9  mov     [rsp+arg_8], rbp
0x1800a68ee  push    rsi
0x1800a68ef  push    rdi
0x1800a68f0  push    r12
0x1800a68f2  push    r14
0x1800a68f4  push    r15
0x1800a68f6  sub     rsp, 30h
0x1800a68fa  xor     ebx, ebx
0x1800a68fc  mov     r12d, r9d
0x1800a68ff  mov     r10, r8
0x1800a6902  mov     rsi, rdx
0x1800a6905  mov     rdi, rcx
0x1800a6908  test    r8, r8
0x1800a690b  jnz     loc_1800A69EB
0x1800a6911  mov     rbp, rbx
0x1800a6914  test    r10, r10
0x1800a6917  jnz     loc_1800A6A3A
0x1800a691d  xor     r8d, r8d; lpData
0x1800a6920  xor     edx, edx; cbBuffer
0x1800a6922  mov     rcx, rsi; hMF
0x1800a6925  call    cs:__imp_GetMetaFileBitsEx
0x1800a692c  nop     dword ptr [rax+rax+00h]
0x1800a6931  mov     r15d, eax
0x1800a6934  test    eax, eax
0x1800a6936  jz      loc_1800A69CA
0x1800a693c  mov     ecx, r15d
0x1800a693f  xor     edx, edx
0x1800a6941  call    GpMallocEx
0x1800a6946  mov     r14, rax
0x1800a6949  test    rax, rax
0x1800a694c  jz      short loc_1800A69CA
0x1800a694e  mov     r8, rax; lpData
0x1800a6951  mov     edx, r15d; cbBuffer
0x1800a6954  mov     rcx, rsi; hMF
0x1800a6957  call    cs:__imp_GetMetaFileBitsEx
0x1800a695e  nop     dword ptr [rax+rax+00h]
0x1800a6963  test    eax, eax
0x1800a6965  jle     short loc_1800A69C2
0x1800a6967  mov     ecx, [rdi+0F4h]
0x1800a696d  mov     r9d, r15d
0x1800a6970  mov     [rsp+58h+var_38], ecx
0x1800a6974  mov     r8, r14
0x1800a6977  mov     rcx, rsi
0x1800a697a  mov     rdx, rbp
0x1800a697d  call    ?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z; GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)
0x1800a6982  mov     rbp, rax
0x1800a6985  test    rax, rax
0x1800a6988  jz      short loc_1800A69C2
0x1800a698a  lea     rdx, [rdi+20h]
0x1800a698e  mov     [rsp+58h+arg_10], ebx
0x1800a6992  lea     r8, [rsp+58h+arg_10]
0x1800a6997  mov     rcx, rax
0x1800a699a  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x1800a699f  test    eax, eax
0x1800a69a1  jnz     loc_1800A6A5C
0x1800a69a7  mov     dword ptr [rdi+0E4h], 1
0x1800a69b1  mov     [rdi+0B8h], rbp
0x1800a69b8  mov     dword ptr [rdi+0B0h], 3
0x1800a69c2  mov     rcx, r14
0x1800a69c5  call    GpFree
0x1800a69ca  test    r12d, r12d
0x1800a69cd  jnz     loc_1800A6A80
0x1800a69d3  mov     rbx, [rsp+58h+arg_0]
0x1800a69d8  mov     rbp, [rsp+58h+arg_8]
0x1800a69dd  add     rsp, 30h
0x1800a69e1  pop     r15
0x1800a69e3  pop     r14
0x1800a69e5  pop     r12
0x1800a69e7  pop     rdi
0x1800a69e8  pop     rsi
0x1800a69e9  retn
0x1800a69eb  mov     rcx, r10; struct WmfPlaceableFileHeader *
0x1800a69ee  call    ?WmfPlaceableHeaderIsValid@@YAHPEBUWmfPlaceableFileHeader@@@Z; WmfPlaceableHeaderIsValid(WmfPlaceableFileHeader const *)
0x1800a69f3  test    eax, eax
0x1800a69f5  jz      loc_1800A6911
0x1800a69fb  cmp     [rsp+58h+arg_20], ebx
0x1800a6a02  jnz     loc_1800A6911
0x1800a6a08  lea     r8, [rdi+20h]
0x1800a6a0c  mov     rdx, r10
0x1800a6a0f  mov     rcx, rsi
0x1800a6a12  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@AEAVMetafileHeader@@@Z; GetMetafileHeader(HMETAFILE__ *,WmfPlaceableFileHeader const *,MetafileHeader &)
0x1800a6a17  test    eax, eax
0x1800a6a19  jnz     short loc_1800A6A4D
0x1800a6a1b  test    r12d, r12d
0x1800a6a1e  mov     [rdi+0B8h], rsi
0x1800a6a25  mov     dword ptr [rdi+0B0h], 3
0x1800a6a2f  setnz   bl
0x1800a6a32  mov     [rdi+0E4h], ebx
0x1800a6a38  jmp     short loc_1800A69D3
0x1800a6a3a  mov     rcx, r10; struct WmfPlaceableFileHeader *
0x1800a6a3d  call    ?WmfPlaceableHeaderIsValid@@YAHPEBUWmfPlaceableFileHeader@@@Z; WmfPlaceableHeaderIsValid(WmfPlaceableFileHeader const *)
0x1800a6a42  test    eax, eax
0x1800a6a44  cmovnz  rbp, r10
0x1800a6a48  jmp     loc_1800A691D
0x1800a6a4d  mov     dword ptr [rdi+0B0h], 1
0x1800a6a57  jmp     loc_1800A69CA
0x1800a6a5c  cmp     [rsp+58h+arg_10], ebx
0x1800a6a60  jz      short loc_1800A6A6C
0x1800a6a62  mov     dword ptr [rdi+0B0h], 1
0x1800a6a6c  mov     rcx, rbp; hmf
0x1800a6a6f  call    cs:__imp_DeleteEnhMetaFile
0x1800a6a76  nop     dword ptr [rax+rax+00h]
0x1800a6a7b  jmp     loc_1800A69C2
0x1800a6a80  mov     rcx, rsi; hmf
0x1800a6a83  call    cs:__imp_DeleteMetaFile
0x1800a6a8a  nop     dword ptr [rax+rax+00h]
0x1800a6a8f  jmp     loc_1800A69D3
```
