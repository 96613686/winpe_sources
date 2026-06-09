# ConvertNV11toNV12(tagRECT const &,ParameterBase const *)

- ea: `0x180096e70`
- end: `0x180097027`
- name: `?ConvertNV11toNV12@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180096e70`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180096f00`
- `MFPlat!MFCopyImage` at `0x180096f00`

## pseudocode

```c
__int64 __fastcall ConvertNV11toNV12(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  signed int v2; // ebx
  LONG v3; // r12d
  signed int v4; // r15d
  signed int v5; // edi
  __int64 v6; // rsi
  signed int v7; // r14d
  LONG v8; // edx
  int v9; // ebp
  int v10; // r13d
  int v11; // edi
  int v12; // r11d
  int v13; // r8d
  __int64 v14; // r10
  __int64 v15; // r9
  __int64 v16; // r12
  __int64 v17; // r14
  __int64 v18; // r15
  int v19; // eax
  __int64 v20; // rsi
  int v21; // r11d
  int v22; // ebx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // r8d
  int v28; // [rsp+80h] [rbp+8h]
  int v29; // [rsp+88h] [rbp+10h]
  __int64 v30; // [rsp+90h] [rbp+18h]
  __int64 v31; // [rsp+98h] [rbp+20h]

  v2 = a1->top & 0xFFFFFFFE;
  v3 = *((_DWORD *)a2 + 6);
  v4 = a1->bottom & 0xFFFFFFFE;
  v5 = a1->left & 0xFFFFFFFC;
  v7 = a1->right & 0xFFFFFFFC;
  v29 = *((_DWORD *)a2 + 3);
  v30 = *((_QWORD *)a2 + 2);
  v31 = *(_QWORD *)a2;
  v8 = *((_DWORD *)a2 + 2);
  v6 = v8;
  if ( !MFCopyImage(
          (BYTE *)(v31 + v5 + (__int64)(v8 * v2)),
          v8,
          (const BYTE *)(v30 + v5 + (__int64)(v3 * v2)),
          v3,
          v7 - v5,
          v4 - v2) )
  {
    v9 = v5 / 4;
    v10 = v7 / 4;
    v11 = v2 / 2;
    v12 = v4 / 2;
    v28 = v4 / 2;
    v13 = v3 / 2;
    v14 = v2 * (v3 / 2) + v30 + v3 * v29;
    v15 = (int)v6 * (v2 / 2) + v31 + (int)v6 * v29;
    if ( v2 / 2 < v4 / 2 )
    {
      v16 = v3 / 2;
      v17 = 2 * v13;
      v18 = v6;
      v19 = v12;
      do
      {
        v20 = v16 + v14;
        v21 = v9;
        if ( v9 < v10 )
        {
          v22 = 4 * v9;
          do
          {
            v23 = 2 * v21++;
            v24 = v23;
            v25 = v22;
            v22 += 4;
            v26 = (*(unsigned __int8 *)(v24 + v20 + 1) + 1 + (unsigned int)*(unsigned __int8 *)(v24 + v14 + 1)) >> 1;
            LODWORD(v24) = *(unsigned __int8 *)(v24 + v20) + *(unsigned __int8 *)(v24 + v14) + 1;
            *(_BYTE *)(v25 + v15 + 1) = v26;
            LODWORD(v24) = (unsigned int)v24 >> 1;
            *(_BYTE *)(v25 + v15) = v24;
            *(_BYTE *)(v25 + v15 + 2) = v24;
            *(_BYTE *)(v25 + v15 + 3) = v26;
          }
          while ( v21 < v10 );
          v19 = v28;
        }
        v14 += v17;
        v15 += v18;
        ++v11;
      }
      while ( v11 < v19 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180096e70  push    rbx
0x180096e72  push    rbp
0x180096e73  push    rsi
0x180096e74  push    rdi
0x180096e75  push    r12
0x180096e77  push    r13
0x180096e79  push    r14
0x180096e7b  push    r15
0x180096e7d  sub     rsp, 38h
0x180096e81  mov     ebx, [rcx+4]
0x180096e84  mov     eax, [rdx+0Ch]
0x180096e87  and     ebx, 0FFFFFFFEh
0x180096e8a  mov     r12d, [rdx+18h]
0x180096e8e  mov     r15d, [rcx+0Ch]
0x180096e92  mov     r14d, [rcx+8]
0x180096e96  and     r15d, 0FFFFFFFEh
0x180096e9a  mov     edi, [rcx]
0x180096e9c  mov     r10d, r15d
0x180096e9f  mov     r11, [rdx+10h]
0x180096ea3  and     edi, 0FFFFFFFCh
0x180096ea6  mov     rbp, [rdx]
0x180096ea9  sub     r10d, ebx
0x180096eac  movsxd  rsi, dword ptr [rdx+8]
0x180096eb0  and     r14d, 0FFFFFFFCh
0x180096eb4  mov     [rsp+78h+arg_8], eax
0x180096ebb  mov     r9d, r14d
0x180096ebe  movsxd  rdx, edi
0x180096ec1  sub     r9d, edi
0x180096ec4  mov     eax, ebx
0x180096ec6  mov     [rsp+78h+dwLines], r10d; dwLines
0x180096ecb  imul    eax, r12d
0x180096ecf  mov     [rsp+78h+dwWidthInBytes], r9d; dwWidthInBytes
0x180096ed4  mov     r9d, r12d; lSrcStride
0x180096ed7  mov     [rsp+78h+arg_10], r11
0x180096edf  mov     [rsp+78h+arg_18], rbp
0x180096ee7  movsxd  r8, eax
0x180096eea  mov     eax, ebx
0x180096eec  add     r8, rdx
0x180096eef  imul    eax, esi
0x180096ef2  add     r8, r11; pSrc
0x180096ef5  movsxd  rcx, eax
0x180096ef8  add     rcx, rdx
0x180096efb  mov     edx, esi; lDestStride
0x180096efd  add     rcx, rbp; pDest
0x180096f00  call    cs:__imp_MFCopyImage
0x180096f06  test    eax, eax
0x180096f08  jnz     loc_180097014
0x180096f0e  mov     ecx, 4
0x180096f13  mov     eax, edi
0x180096f15  cdq
0x180096f16  idiv    ecx
0x180096f18  mov     ebp, eax
0x180096f1a  mov     eax, r14d
0x180096f1d  cdq
0x180096f1e  idiv    ecx
0x180096f20  mov     ecx, 2
0x180096f25  mov     r13d, eax
0x180096f28  mov     eax, ebx
0x180096f2a  cdq
0x180096f2b  idiv    ecx
0x180096f2d  mov     edi, eax
0x180096f2f  mov     eax, r15d
0x180096f32  cdq
0x180096f33  idiv    ecx
0x180096f35  mov     r11d, eax
0x180096f38  mov     [rsp+78h+arg_0], eax
0x180096f3f  mov     eax, r12d
0x180096f42  cdq
0x180096f43  idiv    ecx
0x180096f45  movsxd  r8, eax
0x180096f48  mov     eax, [rsp+78h+arg_8]
0x180096f4f  mov     ecx, r8d
0x180096f52  imul    ecx, ebx
0x180096f55  movsxd  rdx, ecx
0x180096f58  mov     ecx, eax
0x180096f5a  imul    ecx, r12d
0x180096f5e  imul    eax, esi
0x180096f61  movsxd  r10, ecx
0x180096f64  mov     rcx, [rsp+78h+arg_10]
0x180096f6c  add     rcx, rdx
0x180096f6f  movsxd  r9, eax
0x180096f72  mov     rax, [rsp+78h+arg_18]
0x180096f7a  add     r10, rcx
0x180096f7d  mov     ecx, edi
0x180096f7f  imul    ecx, esi
0x180096f82  movsxd  rdx, ecx
0x180096f85  add     rax, rdx
0x180096f88  add     r9, rax
0x180096f8b  cmp     edi, r11d
0x180096f8e  jge     loc_180097014
0x180096f94  lea     eax, [r8+r8]
0x180096f98  mov     r12, r8
0x180096f9b  movsxd  r14, eax
0x180096f9e  mov     r15, rsi
0x180096fa1  mov     eax, r11d
0x180096fa4  lea     rsi, [r12+r10]
0x180096fa8  mov     r11d, ebp
0x180096fab  cmp     ebp, r13d
0x180096fae  jge     short loc_180097008
0x180096fb0  lea     ebx, ds:0[rbp*4]
0x180096fb7  lea     eax, [r11+r11]
0x180096fbb  inc     r11d
0x180096fbe  movsxd  rdx, eax
0x180096fc1  movsxd  rax, ebx
0x180096fc4  add     ebx, 4
0x180096fc7  movzx   ecx, byte ptr [rdx+rsi+1]
0x180096fcc  movzx   r8d, byte ptr [rdx+r10+1]
0x180096fd2  inc     ecx
0x180096fd4  add     r8d, ecx
0x180096fd7  movzx   ecx, byte ptr [rdx+rsi]
0x180096fdb  movzx   edx, byte ptr [rdx+r10]
0x180096fe0  inc     edx
0x180096fe2  shr     r8d, 1
0x180096fe5  add     edx, ecx
0x180096fe7  mov     [rax+r9+1], r8b
0x180096fec  shr     edx, 1
0x180096fee  mov     [rax+r9], dl
0x180096ff2  mov     [rax+r9+2], dl
0x180096ff7  mov     [rax+r9+3], r8b
0x180096ffc  cmp     r11d, r13d
0x180096fff  jl      short loc_180096FB7
0x180097001  mov     eax, [rsp+78h+arg_0]
0x180097008  add     r10, r14
0x18009700b  add     r9, r15
0x18009700e  inc     edi
0x180097010  cmp     edi, eax
0x180097012  jl      short loc_180096FA4
0x180097014  xor     eax, eax
0x180097016  add     rsp, 38h
0x18009701a  pop     r15
0x18009701c  pop     r14
0x18009701e  pop     r13
0x180097020  pop     r12
0x180097022  pop     rdi
0x180097023  pop     rsi
0x180097024  pop     rbp
0x180097025  pop     rbx
0x180097026  retn
```
