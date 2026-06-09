# GpMetafile::Clone(void)

- ea: `0x18010afb0`
- end: `0x18010b198`
- name: `?Clone@GpMetafile@@UEBAPEAVGpImage@@XZ`
- size: `488`
- prototype: `struct GpImage *__fastcall(GpMetafile *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180007ddc`
- `0x1800a7794`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea080`
- `0x18010ad94`
- `0x18010afb0`
- `0x180175010`

## import_xrefs

- `GDI32!CopyMetaFileA` at `0x18010b073`
- `GDI32!CopyMetaFileA` at `0x18010b073`
- `GDI32!CopyEnhMetaFileA` at `0x18010affd`
- `GDI32!CopyEnhMetaFileA` at `0x18010affd`
- `GDI32!DeleteMetaFile` at `0x18010b14e`
- `GDI32!DeleteMetaFile` at `0x18010b14e`
- `GDI32!DeleteEnhMetaFile` at `0x18010b062`
- `GDI32!DeleteEnhMetaFile` at `0x18010b062`

## pseudocode

```c
struct GpImage *__fastcall GpMetafile::Clone(GpMetafile *this)
{
  GpMetafile *v2; // rbx
  HENHMETAFILE v3; // rcx
  HENHMETAFILE v4; // rsi
  GpMetafile *v5; // rax
  GpMetafile *v6; // rax
  GpMetafile *v7; // rdi
  HMETAFILE v8; // rsi
  __m128 v9; // xmm0
  __int16 v10; // ax
  int v11; // eax
  GpMetafile *v12; // rax
  GpMetafile *v13; // rax
  __int64 v14; // rax
  int v16; // [rsp+30h] [rbp-20h] BYREF
  __int16 v17; // [rsp+34h] [rbp-1Ch]
  __int16 v18; // [rsp+36h] [rbp-1Ah]
  __int16 v19; // [rsp+38h] [rbp-18h]
  __int16 v20; // [rsp+3Ah] [rbp-16h]
  __int16 v21; // [rsp+3Ch] [rbp-14h]
  __int16 v22; // [rsp+3Eh] [rbp-12h]
  int v23; // [rsp+40h] [rbp-10h]
  __int16 v24; // [rsp+44h] [rbp-Ch]

  v2 = 0;
  if ( (unsigned int)(*((_DWORD *)this + 44) - 3) <= 1 )
  {
    v3 = (HENHMETAFILE)*((_QWORD *)this + 23);
    if ( *((int *)this + 8) < 3 )
    {
      v8 = CopyMetaFileA((HMETAFILE)v3, 0);
      if ( v8 )
      {
        v9 = (__m128)*((unsigned int *)this + 12);
        v9.m128_f32[0] = v9.m128_f32[0] + 0.5;
        v18 = *((_WORD *)this + 28);
        v20 = *((_WORD *)this + 32) + v18;
        v19 = *((_WORD *)this + 30);
        v10 = *((_WORD *)this + 34) + v19;
        v24 = 0;
        v16 = -1698247209;
        v17 = 0;
        v21 = v10;
        v11 = Feature_GdiPlusOptimizations_Misc_IsEnabled
            ? (int)_mm_round_ss(v9, v9, 9).m128_f32[0]
            : (int)floor(v9.m128_f32[0]);
        v22 = v11;
        v23 = 0;
        v24 = GetWmfPlaceableCheckSum((const struct WmfPlaceableFileHeader *)&v16);
        v12 = (GpMetafile *)GpMallocEx(256, 0);
        if ( v12 )
        {
          v13 = GpMetafile::GpMetafile(v12, v8, (const struct WmfPlaceableFileHeader *)&v16, 1, 0);
          v7 = v13;
          v2 = v13;
          if ( v13 )
          {
            if ( !(*(unsigned int (__fastcall **)(GpMetafile *))(*(_QWORD *)v13 + 8LL))(v13) )
            {
              DeleteMetaFile(v8);
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
          v7 = v6;
          v2 = v6;
          if ( v6 )
          {
            if ( !(*(unsigned int (__fastcall **)(GpMetafile *))(*(_QWORD *)v6 + 8LL))(v6) )
            {
              DeleteEnhMetaFile(v4);
LABEL_16:
              v14 = *(_QWORD *)v7;
              *((_QWORD *)v7 + 23) = 0;
              (*(void (__fastcall **)(GpMetafile *))(v14 + 56))(v7);
              return 0;
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18010afb0  mov     [rsp-18h+arg_8], rbx
0x18010afb5  mov     [rsp-18h+arg_10], rsi
0x18010afba  push    rbp
0x18010afbb  push    rdi
0x18010afbc  push    r14
0x18010afbe  mov     rbp, rsp
0x18010afc1  sub     rsp, 50h
0x18010afc5  mov     rax, cs:__security_cookie
0x18010afcc  xor     rax, rsp
0x18010afcf  mov     [rbp+var_8], rax
0x18010afd3  mov     eax, [rcx+0B0h]
0x18010afd9  xor     r14d, r14d
0x18010afdc  sub     eax, 3
0x18010afdf  mov     rdi, rcx
0x18010afe2  mov     ebx, r14d
0x18010afe5  cmp     eax, 1
0x18010afe8  ja      loc_18010B173
0x18010afee  mov     rcx, [rcx+0B8h]; HMETAFILE
0x18010aff5  xor     edx, edx; LPCSTR
0x18010aff7  cmp     dword ptr [rdi+20h], 3
0x18010affb  jl      short loc_18010B073
0x18010affd  call    cs:__imp_CopyEnhMetaFileA
0x18010b004  nop     dword ptr [rax+rax+00h]
0x18010b009  mov     rsi, rax
0x18010b00c  test    rax, rax
0x18010b00f  jz      loc_18010B173
0x18010b015  xor     edx, edx
0x18010b017  mov     ecx, 100h
0x18010b01c  call    GpMallocEx
0x18010b021  test    rax, rax
0x18010b024  jz      loc_18010B173
0x18010b02a  lea     r8d, [r14+1]; int
0x18010b02e  mov     rdx, rsi; HENHMETAFILE
0x18010b031  mov     rcx, rax; this
0x18010b034  call    ??0GpMetafile@@QEAA@PEAUHENHMETAFILE__@@H@Z; GpMetafile::GpMetafile(HENHMETAFILE__ *,int)
0x18010b039  mov     rdi, rax
0x18010b03c  mov     rbx, rax
0x18010b03f  test    rax, rax
0x18010b042  jz      loc_18010B173
0x18010b048  mov     rax, [rax]
0x18010b04b  mov     rcx, rbx
0x18010b04e  mov     rax, [rax+8]
0x18010b052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b057  test    eax, eax
0x18010b059  jnz     loc_18010B173
0x18010b05f  mov     rcx, rsi; hmf
0x18010b062  call    cs:__imp_DeleteEnhMetaFile
0x18010b069  nop     dword ptr [rax+rax+00h]
0x18010b06e  jmp     loc_18010B15A
0x18010b073  call    cs:__imp_CopyMetaFileA
0x18010b07a  nop     dword ptr [rax+rax+00h]
0x18010b07f  mov     rsi, rax
0x18010b082  test    rax, rax
0x18010b085  jz      loc_18010B173
0x18010b08b  movzx   eax, word ptr [rdi+38h]
0x18010b08f  movss   xmm0, dword ptr [rdi+30h]
0x18010b094  addss   xmm0, cs:__real@3f000000
0x18010b09c  mov     [rbp+var_1A], ax
0x18010b0a0  add     ax, [rdi+40h]
0x18010b0a4  mov     [rbp+var_16], ax
0x18010b0a8  movzx   eax, word ptr [rdi+3Ch]
0x18010b0ac  mov     [rbp+var_18], ax
0x18010b0b0  add     ax, [rdi+44h]
0x18010b0b4  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, r14b; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18010b0bb  mov     [rbp+var_C], r14w
0x18010b0c0  mov     [rbp+var_20], 9AC6CDD7h
0x18010b0c7  mov     [rbp+var_1C], r14w
0x18010b0cc  mov     [rbp+var_14], ax
0x18010b0d0  jz      short loc_18010B0E1
0x18010b0d2  movaps  xmm1, xmm0
0x18010b0d5  roundss xmm1, xmm1, 9
0x18010b0db  cvttss2si eax, xmm1
0x18010b0df  jmp     short loc_18010B0ED
0x18010b0e1  cvtps2pd xmm0, xmm0; X
0x18010b0e4  call    floor
0x18010b0e9  cvttsd2si eax, xmm0
0x18010b0ed  lea     rcx, [rbp+var_20]; struct WmfPlaceableFileHeader *
0x18010b0f1  mov     [rbp+var_12], ax
0x18010b0f5  mov     [rbp+var_10], r14d
0x18010b0f9  call    ?GetWmfPlaceableCheckSum@@YAFPEBUWmfPlaceableFileHeader@@@Z; GetWmfPlaceableCheckSum(WmfPlaceableFileHeader const *)
0x18010b0fe  xor     edx, edx
0x18010b100  mov     [rbp+var_C], ax
0x18010b104  mov     ecx, 100h
0x18010b109  call    GpMallocEx
0x18010b10e  test    rax, rax
0x18010b111  jz      short loc_18010B173
0x18010b113  mov     r9d, 1; int
0x18010b119  mov     [rsp+50h+var_30], r14d; int
0x18010b11e  lea     r8, [rbp+var_20]; struct WmfPlaceableFileHeader *
0x18010b122  mov     rdx, rsi; HMETAFILE
0x18010b125  mov     rcx, rax; this
0x18010b128  call    ??0GpMetafile@@QEAA@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z; GpMetafile::GpMetafile(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)
0x18010b12d  mov     rdi, rax
0x18010b130  mov     rbx, rax
0x18010b133  test    rax, rax
0x18010b136  jz      short loc_18010B173
0x18010b138  mov     rax, [rax]
0x18010b13b  mov     rcx, rbx
0x18010b13e  mov     rax, [rax+8]
0x18010b142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b147  test    eax, eax
0x18010b149  jnz     short loc_18010B173
0x18010b14b  mov     rcx, rsi; hmf
0x18010b14e  call    cs:__imp_DeleteMetaFile
0x18010b155  nop     dword ptr [rax+rax+00h]
0x18010b15a  mov     rax, [rdi]
0x18010b15d  mov     rcx, rdi
0x18010b160  mov     [rdi+0B8h], r14
0x18010b167  mov     rax, [rax+38h]
0x18010b16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b170  mov     rbx, r14
0x18010b173  mov     rax, rbx
0x18010b176  mov     rcx, [rbp+var_8]
0x18010b17a  xor     rcx, rsp; StackCookie
0x18010b17d  call    __security_check_cookie
0x18010b182  lea     r11, [rsp+50h+var_s0]
0x18010b187  mov     rbx, [r11+28h]
0x18010b18b  mov     rsi, [r11+30h]
0x18010b18f  mov     rsp, r11
0x18010b192  pop     r14
0x18010b194  pop     rdi
0x18010b195  pop     rbp
0x18010b196  retn
```
