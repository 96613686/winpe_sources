# CdCommonQueryInfo

- ea: `0x140012d24`
- end: `0x14001313a`
- name: `CdCommonQueryInfo`
- size: `1046`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x140003000`
- `0x14000b684`
- `0x140012d24`
- `0x1400135d0`
- `0x1400181a4`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001310c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b953`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001310c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b953`

## pseudocode

```c
__int64 __fastcall CdCommonQueryInfo(__int64 a1, _QWORD *a2)
{
  unsigned int AlternateNameInfo; // r15d
  char v4; // r12
  unsigned int v5; // esi
  int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // r13
  int v9; // ecx
  __int64 v10; // r14
  unsigned __int64 v11; // r13
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // rbx
  unsigned int v22; // esi
  __int64 v23; // rax
  __int64 v24; // r13
  __int64 v25; // r9
  unsigned int v26; // ecx
  unsigned int v27; // esi
  unsigned int v28; // eax
  bool v29; // cf
  void *v30; // rcx
  const void *v31; // rdx
  unsigned int v32; // ebx
  int v33; // eax
  __int64 v34; // rdx
  unsigned int v35; // ecx
  __int64 v36; // rax
  unsigned int v40; // [rsp+90h] [rbp+18h] BYREF
  __int64 v41; // [rsp+98h] [rbp+20h]

  AlternateNameInfo = 0;
  v41 = a2[23];
  v4 = 0;
  v5 = *(_DWORD *)(v41 + 8);
  v40 = v5;
  v6 = *(_DWORD *)(v41 + 16);
  v7 = a2[3];
  v8 = *(_QWORD *)(v41 + 48);
  v9 = *(_DWORD *)(v8 + 32) & 7;
  if ( v9 )
  {
    v10 = *(_QWORD *)(v8 + 24);
    v11 = *(_QWORD *)(v8 + 32) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  if ( (unsigned int)(v9 - 3) >= 2 )
    goto LABEL_5;
  v4 = 1;
  CdAcquireResource(a1, *(_QWORD *)(v10 + 8), 0, 1);
  if ( (*(_DWORD *)(v10 + 172) & 1) == 0 && !*(_QWORD *)(v10 + 472) )
    CdCreateInternalStream(a1, *(_QWORD *)(v10 + 120), v10, v10 + 344);
  CdVerifyFcbOperation(a1, v10);
  v12 = v6 - 4;
  if ( !v12 )
  {
    v36 = *(_QWORD *)(v10 + 464);
    *(_QWORD *)(v7 + 24) = v36;
    *(_QWORD *)v7 = v36;
    *(_QWORD *)(v7 + 16) = v36;
    *(_QWORD *)(v7 + 8) = 0;
    *(_DWORD *)(v7 + 32) = *(_DWORD *)(v10 + 176);
    v5 -= 40;
    goto LABEL_48;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    *(_DWORD *)(v7 + 16) = 1;
    *(_BYTE *)(v7 + 20) = 0;
    if ( (*(_DWORD *)(v10 + 176) & 0x10) != 0 )
    {
      *(_QWORD *)(v7 + 8) = 0;
      *(_QWORD *)v7 = 0;
      *(_BYTE *)(v7 + 21) = 1;
    }
    else
    {
      *(_QWORD *)v7 = *(_QWORD *)(v10 + 24);
      *(_QWORD *)(v7 + 8) = *(_QWORD *)(v10 + 32);
      *(_BYTE *)(v7 + 21) = 0;
    }
    v5 -= 24;
    goto LABEL_48;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    *(_QWORD *)v7 = *(_QWORD *)(v10 + 152);
    v5 -= 8;
    goto LABEL_48;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    *(_DWORD *)v7 = 0;
    v5 -= 4;
    goto LABEL_48;
  }
  v16 = v15 - 2;
  if ( !v16 )
  {
    v33 = *(_DWORD *)(v11 + 4);
    v24 = v41;
    if ( (v33 & 1) != 0 )
    {
      AlternateNameInfo = -1073741811;
      goto LABEL_34;
    }
    v34 = *(_QWORD *)(v41 + 48);
    v35 = *(unsigned __int16 *)(v34 + 88);
    *(_DWORD *)v7 = v35;
    v27 = v5 - 4;
    v40 = v27;
    v28 = v27;
    if ( v35 <= v27 )
      v28 = v35;
    v29 = v27 < v35;
    v30 = (void *)(v7 + 4);
    v31 = *(const void **)(v34 + 96);
    goto LABEL_32;
  }
  v17 = v16 - 5;
  if ( !v17 )
  {
    v24 = v41;
    *(_QWORD *)v7 = *(_QWORD *)(*(_QWORD *)(v41 + 48) + 104LL);
    v5 -= 8;
    goto LABEL_33;
  }
  v18 = v17 - 4;
  if ( v18 )
  {
    v19 = v18 - 3;
    if ( !v19 )
    {
      v21 = a1;
      if ( (*(_DWORD *)(v11 + 4) & 1) != 0 )
      {
        AlternateNameInfo = -1073741811;
      }
      else
      {
        AlternateNameInfo = CdQueryAlternateNameInfo(a1, v10, v11, v7, (__int64)&v40);
        v5 = v40;
      }
      goto LABEL_50;
    }
    if ( v19 != 13 )
      goto LABEL_5;
    v20 = *(_QWORD *)(v10 + 464);
    *(_QWORD *)(v7 + 24) = v20;
    *(_QWORD *)v7 = v20;
    *(_QWORD *)(v7 + 16) = v20;
    *(_QWORD *)(v7 + 8) = 0;
    *(_DWORD *)(v7 + 48) = *(_DWORD *)(v10 + 176);
    if ( (*(_DWORD *)(v10 + 176) & 0x10) != 0 )
    {
      *(_QWORD *)(v7 + 40) = 0;
      *(_QWORD *)(v7 + 32) = 0;
    }
    else
    {
      *(_QWORD *)(v7 + 32) = *(_QWORD *)(v10 + 24);
      *(_QWORD *)(v7 + 40) = *(_QWORD *)(v10 + 32);
    }
    v5 -= 56;
LABEL_48:
    v40 = v5;
    goto LABEL_49;
  }
  if ( (*(_DWORD *)(v11 + 4) & 1) == 0 )
  {
    v22 = v5 - 12;
    v40 = v22;
    v23 = *(_QWORD *)(v10 + 464);
    *(_QWORD *)(v7 + 24) = v23;
    *(_QWORD *)v7 = v23;
    *(_QWORD *)(v7 + 16) = v23;
    *(_QWORD *)(v7 + 8) = 0;
    *(_DWORD *)(v7 + 32) = *(_DWORD *)(v10 + 176);
    v40 = v22 - 40;
    *(_DWORD *)(v7 + 56) = 1;
    *(_BYTE *)(v7 + 60) = 0;
    if ( (*(_DWORD *)(v10 + 176) & 0x10) != 0 )
    {
      *(_QWORD *)(v7 + 48) = 0;
      *(_QWORD *)(v7 + 40) = 0;
      *(_BYTE *)(v7 + 61) = 1;
    }
    else
    {
      *(_QWORD *)(v7 + 40) = *(_QWORD *)(v10 + 24);
      *(_QWORD *)(v7 + 48) = *(_QWORD *)(v10 + 32);
      *(_BYTE *)(v7 + 61) = 0;
    }
    v40 = v22 - 64;
    *(_QWORD *)(v7 + 64) = *(_QWORD *)(v10 + 152);
    *(_DWORD *)(v7 + 72) = 0;
    v40 = v22 - 76;
    v24 = v41;
    *(_QWORD *)(v7 + 80) = *(_QWORD *)(*(_QWORD *)(v41 + 48) + 104LL);
    v40 = v22 - 84;
    v25 = *(_QWORD *)(v24 + 48);
    v26 = *(unsigned __int16 *)(v25 + 88);
    *(_DWORD *)(v7 + 96) = v26;
    v27 = v22 - 88;
    v40 = v27;
    v28 = v27;
    if ( v26 <= v27 )
      v28 = v26;
    v29 = v27 < v26;
    v30 = (void *)(v7 + 100);
    v31 = *(const void **)(v25 + 96);
LABEL_32:
    AlternateNameInfo = v29 ? 0x80000005 : 0;
    v32 = v28;
    memmove(v30, v31, v28);
    v5 = v27 - v32;
LABEL_33:
    v40 = v5;
LABEL_34:
    v21 = a1;
    goto LABEL_51;
  }
LABEL_5:
  AlternateNameInfo = -1073741811;
LABEL_49:
  v21 = a1;
LABEL_50:
  v24 = v41;
LABEL_51:
  a2[7] = *(_DWORD *)(v24 + 8) - v5;
  if ( v4 )
    ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
  CdCompleteRequest(v21, a2, AlternateNameInfo);
  return AlternateNameInfo;
}

```

## disassembly

```asm
0x140012d24  mov     r11, rsp
0x140012d27  mov     [r11+10h], rdx
0x140012d2b  mov     [r11+8], rcx
0x140012d2f  push    rbx
0x140012d30  push    rsi
0x140012d31  push    rdi
0x140012d32  push    r12
0x140012d34  push    r13
0x140012d36  push    r14
0x140012d38  push    r15
0x140012d3a  sub     rsp, 40h
0x140012d3e  mov     r10, rcx
0x140012d41  xor     r15d, r15d
0x140012d44  mov     rax, [rdx+0B8h]
0x140012d4b  mov     [rsp+78h+arg_18], rax
0x140012d53  xor     r12b, r12b
0x140012d56  mov     [r11-48h], r12b
0x140012d5a  mov     esi, [rax+8]
0x140012d5d  mov     [r11+18h], esi
0x140012d61  mov     ebx, [rax+10h]
0x140012d64  mov     rdi, [rdx+18h]
0x140012d68  mov     r13, [rax+30h]
0x140012d6c  mov     ecx, [r13+20h]
0x140012d70  and     ecx, 7
0x140012d73  jnz     short loc_140012D7D
0x140012d75  xor     r14d, r14d
0x140012d78  xor     r13d, r13d
0x140012d7b  jmp     short loc_140012D89
0x140012d7d  mov     r14, [r13+18h]
0x140012d81  mov     r13, [r13+20h]
0x140012d85  and     r13, 0FFFFFFFFFFFFFFF8h
0x140012d89  mov     [rsp+78h+var_40], r14
0x140012d8e  sub     ecx, 3
0x140012d91  jz      short loc_140012DA3
0x140012d93  cmp     ecx, 1
0x140012d96  jz      short loc_140012DA3
0x140012d98  mov     r15d, 0C000000Dh
0x140012d9e  jmp     loc_1400130E1
0x140012da3  mov     r12d, 1
0x140012da9  mov     r9d, r12d
0x140012dac  xor     r8d, r8d
0x140012daf  mov     rdx, [r14+8]
0x140012db3  mov     rcx, r10
0x140012db6  call    CdAcquireResource
0x140012dbb  mov     [rsp+78h+var_48], r12b
0x140012dc0  mov     eax, [r14+0ACh]
0x140012dc7  test    r12b, al
0x140012dca  jnz     short loc_140012DF1
0x140012dcc  cmp     qword ptr [r14+1D8h], 0
0x140012dd4  jnz     short loc_140012DF1
0x140012dd6  lea     r9, [r14+158h]
0x140012ddd  mov     r8, r14
0x140012de0  mov     rdx, [r14+78h]
0x140012de4  mov     rcx, [rsp+78h+arg_0]
0x140012dec  call    CdCreateInternalStream
0x140012df1  mov     rdx, r14
0x140012df4  mov     rcx, [rsp+78h+arg_0]
0x140012dfc  call    CdVerifyFcbOperation
0x140012e01  sub     ebx, 4
0x140012e04  jz      loc_1400130B3
0x140012e0a  sub     ebx, r12d
0x140012e0d  jz      loc_140013073
0x140012e13  sub     ebx, r12d
0x140012e16  jz      loc_140013064
0x140012e1c  sub     ebx, r12d
0x140012e1f  jz      loc_140013059
0x140012e25  sub     ebx, 2
0x140012e28  jz      loc_140013019
0x140012e2e  sub     ebx, 5
0x140012e31  jz      loc_140013001
0x140012e37  sub     ebx, 4
0x140012e3a  jz      loc_140012EF0
0x140012e40  sub     ebx, 3
0x140012e43  jz      short loc_140012EA7
0x140012e45  cmp     ebx, 0Dh
0x140012e48  jnz     loc_140012D98
0x140012e4e  mov     rax, [r14+1D0h]
0x140012e55  mov     [rdi+18h], rax
0x140012e59  mov     [rdi], rax
0x140012e5c  mov     [rdi+10h], rax
0x140012e60  mov     qword ptr [rdi+8], 0
0x140012e68  mov     eax, [r14+0B0h]
0x140012e6f  mov     [rdi+30h], eax
0x140012e72  mov     eax, [r14+0B0h]
0x140012e79  test    al, 10h
0x140012e7b  jz      short loc_140012E8F
0x140012e7d  mov     qword ptr [rdi+28h], 0
0x140012e85  mov     qword ptr [rdi+20h], 0
0x140012e8d  jmp     short loc_140012E9F
0x140012e8f  mov     rax, [r14+18h]
0x140012e93  mov     [rdi+20h], rax
0x140012e97  mov     rax, [r14+20h]
0x140012e9b  mov     [rdi+28h], rax
0x140012e9f  add     esi, 0FFFFFFC8h
0x140012ea2  jmp     loc_1400130DA
0x140012ea7  mov     eax, [r13+4]
0x140012eab  mov     rbx, [rsp+78h+arg_0]
0x140012eb3  test    r12b, al
0x140012eb6  jnz     short loc_140012EE5
0x140012eb8  lea     rax, [rsp+78h+arg_10]
0x140012ec0  mov     [rsp+78h+var_58], rax
0x140012ec5  mov     r9, rdi
0x140012ec8  mov     r8, r13
0x140012ecb  mov     rdx, r14
0x140012ece  mov     rcx, rbx
0x140012ed1  call    CdQueryAlternateNameInfo
0x140012ed6  mov     r15d, eax
0x140012ed9  mov     esi, [rsp+78h+arg_10]
0x140012ee0  jmp     loc_1400130E9
0x140012ee5  mov     r15d, 0C000000Dh
0x140012eeb  jmp     loc_1400130E9
0x140012ef0  mov     eax, [r13+4]
0x140012ef4  test    r12b, al
0x140012ef7  jnz     loc_140012D98
0x140012efd  add     esi, 0FFFFFFF4h
0x140012f00  mov     [rsp+78h+arg_10], esi
0x140012f07  mov     rax, [r14+1D0h]
0x140012f0e  mov     [rdi+18h], rax
0x140012f12  mov     [rdi], rax
0x140012f15  mov     [rdi+10h], rax
0x140012f19  xor     edx, edx
0x140012f1b  mov     [rdi+8], rdx
0x140012f1f  mov     eax, [r14+0B0h]
0x140012f26  mov     [rdi+20h], eax
0x140012f29  lea     ecx, [rsi-28h]
0x140012f2c  mov     [rsp+78h+arg_10], ecx
0x140012f33  mov     [rdi+38h], r12d
0x140012f37  mov     [rdi+3Ch], dl
0x140012f3a  mov     eax, [r14+0B0h]
0x140012f41  test    al, 10h
0x140012f43  jz      short loc_140012F53
0x140012f45  mov     [rdi+30h], rdx
0x140012f49  mov     [rdi+28h], rdx
0x140012f4d  mov     [rdi+3Dh], r12b
0x140012f51  jmp     short loc_140012F66
0x140012f53  mov     rax, [r14+18h]
0x140012f57  mov     [rdi+28h], rax
0x140012f5b  mov     rax, [r14+20h]
0x140012f5f  mov     [rdi+30h], rax
0x140012f63  mov     [rdi+3Dh], dl
0x140012f66  add     ecx, 0FFFFFFE8h
0x140012f69  mov     [rsp+78h+arg_10], ecx
0x140012f70  mov     rax, [r14+98h]
0x140012f77  mov     [rdi+40h], rax
0x140012f7b  lea     eax, [rcx-8]
0x140012f7e  mov     [rsp+78h+arg_10], eax
0x140012f85  mov     [rdi+48h], edx
0x140012f88  lea     edx, [rax-4]
0x140012f8b  mov     [rsp+78h+arg_10], edx
0x140012f92  mov     r13, [rsp+78h+arg_18]
0x140012f9a  mov     rax, [r13+30h]
0x140012f9e  mov     rcx, [rax+68h]
0x140012fa2  mov     [rdi+50h], rcx
0x140012fa6  add     edx, 0FFFFFFF8h
0x140012fa9  mov     [rsp+78h+arg_10], edx
0x140012fb0  mov     r9, [r13+30h]
0x140012fb4  movzx   ecx, word ptr [r9+58h]
0x140012fb9  mov     [rdi+60h], ecx
0x140012fbc  lea     esi, [rdx-4]
0x140012fbf  mov     [rsp+78h+arg_10], esi
0x140012fc6  mov     eax, esi
0x140012fc8  cmp     ecx, esi
0x140012fca  cmovbe  eax, ecx
0x140012fcd  cmp     esi, ecx
0x140012fcf  lea     rcx, [rdi+64h]; void *
0x140012fd3  mov     rdx, [r9+60h]; Src
0x140012fd7  sbb     r15d, r15d
0x140012fda  mov     r8d, eax; Size
0x140012fdd  and     r15d, 80000005h
0x140012fe4  mov     ebx, eax
0x140012fe6  call    memmove
0x140012feb  sub     esi, ebx
0x140012fed  mov     [rsp+78h+arg_10], esi
0x140012ff4  mov     rbx, [rsp+78h+arg_0]
0x140012ffc  jmp     loc_1400130F1
0x140013001  mov     r13, [rsp+78h+arg_18]
0x140013009  mov     rax, [r13+30h]
0x14001300d  mov     rcx, [rax+68h]
0x140013011  mov     [rdi], rcx
0x140013014  add     esi, 0FFFFFFF8h
0x140013017  jmp     short loc_140012FED
0x140013019  mov     eax, [r13+4]
0x14001301d  mov     r13, [rsp+78h+arg_18]
0x140013025  test    r12b, al
0x140013028  jnz     short loc_140013051
0x14001302a  mov     rdx, [r13+30h]
0x14001302e  movzx   ecx, word ptr [rdx+58h]
0x140013032  mov     [rdi], ecx
0x140013034  add     esi, 0FFFFFFFCh
0x140013037  mov     [rsp+78h+arg_10], esi
0x14001303e  mov     eax, esi
0x140013040  cmp     ecx, esi
0x140013042  cmovbe  eax, ecx
0x140013045  cmp     esi, ecx
0x140013047  lea     rcx, [rdi+4]
0x14001304b  mov     rdx, [rdx+60h]
0x14001304f  jmp     short loc_140012FD7
0x140013051  mov     r15d, 0C000000Dh
0x140013057  jmp     short loc_140012FF4
0x140013059  mov     dword ptr [rdi], 0
0x14001305f  add     esi, 0FFFFFFFCh
0x140013062  jmp     short loc_1400130DA
0x140013064  mov     rax, [r14+98h]
0x14001306b  mov     [rdi], rax
0x14001306e  add     esi, 0FFFFFFF8h
0x140013071  jmp     short loc_1400130DA
0x140013073  mov     [rdi+10h], r12d
0x140013077  mov     byte ptr [rdi+14h], 0
0x14001307b  mov     eax, [r14+0B0h]
0x140013082  test    al, 10h
0x140013084  jz      short loc_14001309B
0x140013086  mov     qword ptr [rdi+8], 0
0x14001308e  mov     qword ptr [rdi], 0
0x140013095  mov     [rdi+15h], r12b
0x140013099  jmp     short loc_1400130AE
0x14001309b  mov     rax, [r14+18h]
0x14001309f  mov     [rdi], rax
0x1400130a2  mov     rax, [r14+20h]
0x1400130a6  mov     [rdi+8], rax
0x1400130aa  mov     byte ptr [rdi+15h], 0
0x1400130ae  add     esi, 0FFFFFFE8h
0x1400130b1  jmp     short loc_1400130DA
0x1400130b3  mov     rax, [r14+1D0h]
0x1400130ba  mov     [rdi+18h], rax
0x1400130be  mov     [rdi], rax
0x1400130c1  mov     [rdi+10h], rax
0x1400130c5  mov     qword ptr [rdi+8], 0
0x1400130cd  mov     eax, [r14+0B0h]
0x1400130d4  mov     [rdi+20h], eax
0x1400130d7  add     esi, 0FFFFFFD8h
0x1400130da  mov     [rsp+78h+arg_10], esi
0x1400130e1  mov     rbx, [rsp+78h+arg_0]
0x1400130e9  mov     r13, [rsp+78h+arg_18]
0x1400130f1  mov     eax, [r13+8]
0x1400130f5  sub     eax, esi
0x1400130f7  mov     rdi, [rsp+78h+arg_8]
0x1400130ff  mov     [rdi+38h], rax
0x140013103  test    r12b, r12b
0x140013106  jz      short loc_140013118
0x140013108  mov     rcx, [r14+8]; Resource
0x14001310c  call    cs:__imp_ExReleaseResourceLite
0x140013113  nop     dword ptr [rax+rax+00h]
0x140013118  mov     r8d, r15d
0x14001311b  mov     rdx, rdi
0x14001311e  mov     rcx, rbx
0x140013121  call    CdCompleteRequest
0x140013126  mov     eax, r15d
0x140013129  add     rsp, 40h
0x14001312d  pop     r15
0x14001312f  pop     r14
0x140013131  pop     r13
0x140013133  pop     r12
0x140013135  pop     rdi
0x140013136  pop     rsi
0x140013137  pop     rbx
0x140013138  retn
0x14001b93c  push    rbp
0x14001b93e  sub     rsp, 30h
0x14001b942  mov     rbp, rdx
0x14001b945  cmp     byte ptr [rbp+30h], 0
0x14001b949  jz      short loc_14001B960
0x14001b94b  mov     rcx, [rbp+38h]
0x14001b94f  mov     rcx, [rcx+8]; Resource
0x14001b953  call    cs:__imp_ExReleaseResourceLite
0x14001b95a  nop     dword ptr [rax+rax+00h]
0x14001b95f  nop
0x14001b960  add     rsp, 30h
0x14001b964  pop     rbp
0x14001b965  retn
```
