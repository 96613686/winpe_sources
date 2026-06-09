# GpMetafile::InitWmf(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)

- ea: `0x180085d9c`
- end: `0x180085f49`
- name: `?InitWmf@GpMetafile@@IEAAXPEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z`
- size: `429`
- prototype: `void(GpMetafile *__hidden this, HMETAFILE, const struct WmfPlaceableFileHeader *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180087780`
- `0x18008d884`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x180085464`
- `0x180085578`
- `0x180085d9c`
- `0x180085f50`
- `0x180086d80`

## import_xrefs

- `GDI32!GetMetaFileBitsEx` at `0x180085dd1`
- `GDI32!GetMetaFileBitsEx` at `0x180085e07`
- `GDI32!GetMetaFileBitsEx` at `0x180085dd1`
- `GDI32!GetMetaFileBitsEx` at `0x180085e07`
- `GDI32!DeleteMetaFile` at `0x180085f38`
- `GDI32!DeleteMetaFile` at `0x180085f38`
- `GDI32!DeleteEnhMetaFile` at `0x180085f24`
- `GDI32!DeleteEnhMetaFile` at `0x180085f24`

## pseudocode

```c
void __fastcall GpMetafile::InitWmf(
        GpMetafile *this,
        HMETAFILE a2,
        const struct WmfPlaceableFileHeader *a3,
        int a4,
        int a5)
{
  const struct WmfPlaceableFileHeader *v6; // r10
  __int16 *v9; // rsi
  UINT MetaFileBits; // eax
  unsigned int v11; // r14d
  void *v12; // rax
  __int64 v13; // rbp
  HENHMETAFILE EmfFromWmfData; // rax
  HENHMETAFILE v15; // rsi
  __int16 *v16; // r10
  int v17; // [rsp+80h] [rbp+18h] BYREF

  v6 = a3;
  if ( a3 && (unsigned int)WmfPlaceableHeaderIsValid(a3) && !a5 )
  {
    if ( !(unsigned int)GetMetafileHeader(a2, v6, (char *)this + 32) )
    {
      *((_QWORD *)this + 23) = a2;
      *((_DWORD *)this + 44) = 3;
      *((_DWORD *)this + 57) = a4 != 0;
      return;
    }
    *((_DWORD *)this + 44) = 1;
  }
  else
  {
    v9 = 0;
    if ( v6 && (unsigned int)WmfPlaceableHeaderIsValid(v6) )
      v9 = v16;
    MetaFileBits = GetMetaFileBitsEx(a2, 0, 0);
    v11 = MetaFileBits;
    if ( MetaFileBits )
    {
      v12 = (void *)GpMallocEx(MetaFileBits, 0);
      v13 = (__int64)v12;
      if ( v12 )
      {
        if ( (int)GetMetaFileBitsEx(a2, v11, v12) > 0 )
        {
          EmfFromWmfData = GetEmfFromWmfData(a2, v9, v13, v11, *((_DWORD *)this + 61));
          v15 = EmfFromWmfData;
          if ( EmfFromWmfData )
          {
            v17 = 0;
            if ( (unsigned int)GetMetafileHeader(EmfFromWmfData, (char *)this + 32, &v17) )
            {
              if ( v17 )
                *((_DWORD *)this + 44) = 1;
              DeleteEnhMetaFile(v15);
            }
            else
            {
              *((_DWORD *)this + 57) = 1;
              *((_QWORD *)this + 23) = v15;
              *((_DWORD *)this + 44) = 3;
            }
          }
        }
        GpFree(v13);
      }
    }
  }
  if ( a4 )
    DeleteMetaFile(a2);
}

```

## disassembly

```asm
0x180085d9c  push    rbx
0x180085d9e  push    rbp
0x180085d9f  push    rsi
0x180085da0  push    rdi
0x180085da1  push    r14
0x180085da3  push    r15
0x180085da5  sub     rsp, 38h
0x180085da9  mov     r15d, r9d
0x180085dac  mov     r10, r8
0x180085daf  mov     rdi, rdx
0x180085db2  mov     rbx, rcx
0x180085db5  test    r8, r8
0x180085db8  jnz     loc_180085E9B
0x180085dbe  xor     esi, esi
0x180085dc0  test    r10, r10
0x180085dc3  jnz     loc_180085EEB
0x180085dc9  xor     r8d, r8d; lpData
0x180085dcc  xor     edx, edx; cbBuffer
0x180085dce  mov     rcx, rdi; hMF
0x180085dd1  call    cs:__imp_GetMetaFileBitsEx
0x180085dd8  nop     dword ptr [rax+rax+00h]
0x180085ddd  mov     r14d, eax
0x180085de0  test    eax, eax
0x180085de2  jz      loc_180085E84
0x180085de8  mov     ecx, r14d
0x180085deb  xor     edx, edx
0x180085ded  call    GpMallocEx
0x180085df2  mov     rbp, rax
0x180085df5  test    rax, rax
0x180085df8  jz      loc_180085E84
0x180085dfe  mov     r8, rax; lpData
0x180085e01  mov     edx, r14d; cbBuffer
0x180085e04  mov     rcx, rdi; hMF
0x180085e07  call    cs:__imp_GetMetaFileBitsEx
0x180085e0e  nop     dword ptr [rax+rax+00h]
0x180085e13  test    eax, eax
0x180085e15  jle     short loc_180085E7C
0x180085e17  mov     ecx, [rbx+0F4h]
0x180085e1d  mov     r9d, r14d
0x180085e20  mov     [rsp+68h+var_48], ecx
0x180085e24  mov     r8, rbp
0x180085e27  mov     rcx, rdi
0x180085e2a  mov     rdx, rsi
0x180085e2d  call    ?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z; GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)
0x180085e32  mov     rsi, rax
0x180085e35  test    rax, rax
0x180085e38  jz      short loc_180085E7C
0x180085e3a  lea     rdx, [rbx+20h]
0x180085e3e  mov     [rsp+68h+arg_10], 0
0x180085e49  lea     r8, [rsp+68h+arg_10]
0x180085e51  mov     rcx, rax
0x180085e54  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x180085e59  test    eax, eax
0x180085e5b  jnz     loc_180085F0D
0x180085e61  mov     dword ptr [rbx+0E4h], 1
0x180085e6b  mov     [rbx+0B8h], rsi
0x180085e72  mov     dword ptr [rbx+0B0h], 3
0x180085e7c  mov     rcx, rbp
0x180085e7f  call    GpFree
0x180085e84  test    r15d, r15d
0x180085e87  jnz     loc_180085F35
0x180085e8d  add     rsp, 38h
0x180085e91  pop     r15
0x180085e93  pop     r14
0x180085e95  pop     rdi
0x180085e96  pop     rsi
0x180085e97  pop     rbp
0x180085e98  pop     rbx
0x180085e99  retn
0x180085e9b  mov     rcx, r10; struct WmfPlaceableFileHeader *
0x180085e9e  call    ?WmfPlaceableHeaderIsValid@@YAHPEBUWmfPlaceableFileHeader@@@Z; WmfPlaceableHeaderIsValid(WmfPlaceableFileHeader const *)
0x180085ea3  test    eax, eax
0x180085ea5  jz      loc_180085DBE
0x180085eab  cmp     [rsp+68h+arg_20], 0
0x180085eb3  jnz     loc_180085DBE
0x180085eb9  lea     r8, [rbx+20h]
0x180085ebd  mov     rdx, r10
0x180085ec0  mov     rcx, rdi
0x180085ec3  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@AEAVMetafileHeader@@@Z; GetMetafileHeader(HMETAFILE__ *,WmfPlaceableFileHeader const *,MetafileHeader &)
0x180085ec8  test    eax, eax
0x180085eca  jnz     short loc_180085EFE
0x180085ecc  test    r15d, r15d
0x180085ecf  mov     [rbx+0B8h], rdi
0x180085ed6  mov     dword ptr [rbx+0B0h], 3
0x180085ee0  setnz   al
0x180085ee3  mov     [rbx+0E4h], eax
0x180085ee9  jmp     short loc_180085E8D
0x180085eeb  mov     rcx, r10; struct WmfPlaceableFileHeader *
0x180085eee  call    ?WmfPlaceableHeaderIsValid@@YAHPEBUWmfPlaceableFileHeader@@@Z; WmfPlaceableHeaderIsValid(WmfPlaceableFileHeader const *)
0x180085ef3  test    eax, eax
0x180085ef5  cmovnz  rsi, r10
0x180085ef9  jmp     loc_180085DC9
0x180085efe  mov     dword ptr [rbx+0B0h], 1
0x180085f08  jmp     loc_180085E84
0x180085f0d  cmp     [rsp+68h+arg_10], 0
0x180085f15  jz      short loc_180085F21
0x180085f17  mov     dword ptr [rbx+0B0h], 1
0x180085f21  mov     rcx, rsi; hmf
0x180085f24  call    cs:__imp_DeleteEnhMetaFile
0x180085f2b  nop     dword ptr [rax+rax+00h]
0x180085f30  jmp     loc_180085E7C
0x180085f35  mov     rcx, rdi; hmf
0x180085f38  call    cs:__imp_DeleteMetaFile
0x180085f3f  nop     dword ptr [rax+rax+00h]
0x180085f44  jmp     loc_180085E8D
```
