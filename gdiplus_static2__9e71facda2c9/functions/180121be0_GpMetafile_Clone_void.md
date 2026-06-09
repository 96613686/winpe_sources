# GpMetafile::Clone(void)

- ea: `0x180121be0`
- end: `0x180121da9`
- name: `?Clone@GpMetafile@@UEBAPEAVGpImage@@XZ`
- size: `457`
- prototype: `struct GpImage *__fastcall(GpMetafile *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180063cd8`
- `0x180085f98`
- `0x180087780`
- `0x180105d40`
- `0x1801066d0`
- `0x180121a60`
- `0x180121be0`
- `0x180172010`

## import_xrefs

- `GDI32!CopyMetaFileA` at `0x180121c93`
- `GDI32!CopyMetaFileA` at `0x180121c93`
- `GDI32!CopyEnhMetaFileA` at `0x180121c20`
- `GDI32!CopyEnhMetaFileA` at `0x180121c20`
- `GDI32!DeleteMetaFile` at `0x180121d68`
- `GDI32!DeleteMetaFile` at `0x180121d68`
- `GDI32!DeleteEnhMetaFile` at `0x180121c82`
- `GDI32!DeleteEnhMetaFile` at `0x180121c82`

## pseudocode

```c
struct GpImage *__fastcall GpMetafile::Clone(GpMetafile *this)
{
  GpMetafile *v1; // rbx
  HENHMETAFILE v3; // rcx
  HENHMETAFILE v4; // rdi
  GpMetafile *v5; // rax
  GpMetafile *v6; // rax
  HMETAFILE v7; // rsi
  __m128 v8; // xmm1
  __int16 v9; // ax
  int v10; // eax
  GpMetafile *v11; // rax
  GpMetafile *v12; // rax
  __int64 v13; // rax
  int v15; // [rsp+30h] [rbp-28h] BYREF
  __int16 v16; // [rsp+34h] [rbp-24h]
  __int16 v17; // [rsp+36h] [rbp-22h]
  __int16 v18; // [rsp+38h] [rbp-20h]
  __int16 v19; // [rsp+3Ah] [rbp-1Eh]
  __int16 v20; // [rsp+3Ch] [rbp-1Ch]
  __int16 v21; // [rsp+3Eh] [rbp-1Ah]
  int v22; // [rsp+40h] [rbp-18h]
  __int16 v23; // [rsp+44h] [rbp-14h]

  v1 = 0;
  if ( (unsigned int)(*((_DWORD *)this + 44) - 3) <= 1 )
  {
    v3 = (HENHMETAFILE)*((_QWORD *)this + 23);
    if ( *((int *)this + 8) < 3 )
    {
      v7 = CopyMetaFileA((HMETAFILE)v3, 0);
      if ( v7 )
      {
        v8 = (__m128)*((unsigned int *)this + 12);
        v8.m128_f32[0] = v8.m128_f32[0] + 0.5;
        v23 = 0;
        v16 = 0;
        v17 = *((_WORD *)this + 28);
        v19 = *((_WORD *)this + 32) + v17;
        v18 = *((_WORD *)this + 30);
        v9 = *((_WORD *)this + 34) + v18;
        v15 = -1698247209;
        v20 = v9;
        v10 = Feature_GdiPlusOptimizations_Misc_IsEnabled
            ? (int)_mm_round_ss(v8, v8, 9).m128_f32[0]
            : (int)floor(v8.m128_f32[0]);
        v21 = v10;
        v22 = 0;
        v23 = GetWmfPlaceableCheckSum((const struct WmfPlaceableFileHeader *)&v15);
        v11 = (GpMetafile *)GpMallocEx(256, 0);
        if ( v11 )
        {
          v12 = GpMetafile::GpMetafile(v11, v7, (const struct WmfPlaceableFileHeader *)&v15, 1, 0);
          v1 = v12;
          if ( v12 )
          {
            if ( !(*(unsigned int (__fastcall **)(GpMetafile *))(*(_QWORD *)v12 + 8LL))(v12) )
            {
              DeleteMetaFile(v7);
              goto LABEL_16;
            }
          }
        }
      }
    }
    else
    {
      v4 = CopyEnhMetaFileA(v3, 0);
      if ( v4 )
      {
        v5 = (GpMetafile *)GpMallocEx(256, 0);
        if ( v5 )
        {
          v6 = GpMetafile::GpMetafile(v5, v4, 1);
          v1 = v6;
          if ( v6 )
          {
            if ( !(*(unsigned int (__fastcall **)(GpMetafile *))(*(_QWORD *)v6 + 8LL))(v6) )
            {
              DeleteEnhMetaFile(v4);
LABEL_16:
              v13 = *(_QWORD *)v1;
              *((_QWORD *)v1 + 23) = 0;
              (*(void (__fastcall **)(GpMetafile *))(v13 + 56))(v1);
              return 0;
            }
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180121be0  push    rbp
0x180121be2  push    rbx
0x180121be3  push    rsi
0x180121be4  push    rdi
0x180121be5  mov     rbp, rsp
0x180121be8  sub     rsp, 58h
0x180121bec  mov     rax, cs:__security_cookie
0x180121bf3  xor     rax, rsp
0x180121bf6  mov     [rbp+var_10], rax
0x180121bfa  mov     eax, [rcx+0B0h]
0x180121c00  xor     ebx, ebx
0x180121c02  sub     eax, 3
0x180121c05  mov     rdi, rcx
0x180121c08  cmp     eax, 1
0x180121c0b  ja      loc_180121D90
0x180121c11  mov     rcx, [rcx+0B8h]; HMETAFILE
0x180121c18  xor     edx, edx; LPCSTR
0x180121c1a  cmp     dword ptr [rdi+20h], 3
0x180121c1e  jl      short loc_180121C93
0x180121c20  call    cs:__imp_CopyEnhMetaFileA
0x180121c27  nop     dword ptr [rax+rax+00h]
0x180121c2c  mov     rdi, rax
0x180121c2f  test    rax, rax
0x180121c32  jz      loc_180121D90
0x180121c38  xor     edx, edx
0x180121c3a  mov     ecx, 100h
0x180121c3f  call    GpMallocEx
0x180121c44  test    rax, rax
0x180121c47  jz      loc_180121D90
0x180121c4d  lea     r8d, [rbx+1]; int
0x180121c51  mov     rdx, rdi; HENHMETAFILE
0x180121c54  mov     rcx, rax; this
0x180121c57  call    ??0GpMetafile@@QEAA@PEAUHENHMETAFILE__@@H@Z; GpMetafile::GpMetafile(HENHMETAFILE__ *,int)
0x180121c5c  mov     rbx, rax
0x180121c5f  test    rax, rax
0x180121c62  jz      loc_180121D90
0x180121c68  mov     rax, [rax]
0x180121c6b  mov     rcx, rbx
0x180121c6e  mov     rax, [rax+8]
0x180121c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121c77  test    eax, eax
0x180121c79  jnz     loc_180121D90
0x180121c7f  mov     rcx, rdi; hmf
0x180121c82  call    cs:__imp_DeleteEnhMetaFile
0x180121c89  nop     dword ptr [rax+rax+00h]
0x180121c8e  jmp     loc_180121D74
0x180121c93  call    cs:__imp_CopyMetaFileA
0x180121c9a  nop     dword ptr [rax+rax+00h]
0x180121c9f  mov     rsi, rax
0x180121ca2  test    rax, rax
0x180121ca5  jz      loc_180121D90
0x180121cab  movss   xmm1, dword ptr [rdi+30h]
0x180121cb0  xor     eax, eax
0x180121cb2  addss   xmm1, cs:__real@3f000000
0x180121cba  mov     [rbp+var_14], ax
0x180121cbe  mov     [rbp+var_24], ax
0x180121cc2  movzx   eax, word ptr [rdi+38h]
0x180121cc6  mov     [rbp+var_22], ax
0x180121cca  add     ax, [rdi+40h]
0x180121cce  mov     [rbp+var_1E], ax
0x180121cd2  movzx   eax, word ptr [rdi+3Ch]
0x180121cd6  mov     [rbp+var_20], ax
0x180121cda  add     ax, [rdi+44h]
0x180121cde  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, bl; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180121ce4  mov     [rbp+var_28], 9AC6CDD7h
0x180121ceb  mov     [rbp+var_1C], ax
0x180121cef  jz      short loc_180121D00
0x180121cf1  movaps  xmm0, xmm1
0x180121cf4  roundss xmm0, xmm0, 9
0x180121cfa  cvttss2si eax, xmm0
0x180121cfe  jmp     short loc_180121D0C
0x180121d00  cvtps2pd xmm0, xmm1; X
0x180121d03  call    floor
0x180121d08  cvttsd2si eax, xmm0
0x180121d0c  lea     rcx, [rbp+var_28]; struct WmfPlaceableFileHeader *
0x180121d10  mov     [rbp+var_1A], ax
0x180121d14  mov     [rbp+var_18], ebx
0x180121d17  call    ?GetWmfPlaceableCheckSum@@YAFPEBUWmfPlaceableFileHeader@@@Z; GetWmfPlaceableCheckSum(WmfPlaceableFileHeader const *)
0x180121d1c  xor     edx, edx
0x180121d1e  mov     [rbp+var_14], ax
0x180121d22  mov     ecx, 100h
0x180121d27  call    GpMallocEx
0x180121d2c  test    rax, rax
0x180121d2f  jz      short loc_180121D90
0x180121d31  mov     r9d, 1; int
0x180121d37  mov     [rsp+58h+var_38], ebx; int
0x180121d3b  lea     r8, [rbp+var_28]; struct WmfPlaceableFileHeader *
0x180121d3f  mov     rdx, rsi; HMETAFILE
0x180121d42  mov     rcx, rax; this
0x180121d45  call    ??0GpMetafile@@QEAA@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z; GpMetafile::GpMetafile(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)
0x180121d4a  mov     rbx, rax
0x180121d4d  test    rax, rax
0x180121d50  jz      short loc_180121D90
0x180121d52  mov     rax, [rax]
0x180121d55  mov     rcx, rbx
0x180121d58  mov     rax, [rax+8]
0x180121d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121d61  test    eax, eax
0x180121d63  jnz     short loc_180121D90
0x180121d65  mov     rcx, rsi; hmf
0x180121d68  call    cs:__imp_DeleteMetaFile
0x180121d6f  nop     dword ptr [rax+rax+00h]
0x180121d74  mov     rax, [rbx]
0x180121d77  mov     rcx, rbx
0x180121d7a  mov     qword ptr [rbx+0B8h], 0
0x180121d85  mov     rax, [rax+38h]
0x180121d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121d8e  xor     ebx, ebx
0x180121d90  mov     rax, rbx
0x180121d93  mov     rcx, [rbp+var_10]
0x180121d97  xor     rcx, rsp; StackCookie
0x180121d9a  call    __security_check_cookie
0x180121d9f  add     rsp, 58h
0x180121da3  pop     rdi
0x180121da4  pop     rsi
0x180121da5  pop     rbx
0x180121da6  pop     rbp
0x180121da7  retn
```
