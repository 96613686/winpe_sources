# NsippEnumerateObjectsAllPersistentParametersWithMask

- ea: `0x140005c3c`
- end: `0x1400060e0`
- name: `NsippEnumerateObjectsAllPersistentParametersWithMask`
- size: `1188`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x1400043d0`
- `0x1400056e8`
- `0x140005c3c`
- `0x140006560`
- `0x140006980`
- `0x14000d08c`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140005cbb`
- `ntoskrnl!IoIs32bitProcess` at `0x140005cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060aa`
- `NETIO!NsiEnumerateObjectsAllPersistentParametersWithMask` at `0x140005f97`
- `NETIO!NsiEnumerateObjectsAllPersistentParametersWithMask` at `0x140005f97`

## pseudocode

```c
__int64 __fastcall NsippEnumerateObjectsAllPersistentParametersWithMask(
        int *Src,
        unsigned int a2,
        unsigned __int8 a3,
        _QWORD *a4)
{
  BOOLEAN v7; // al
  unsigned int v8; // r15d
  int v9; // r12d
  _QWORD *v10; // rdi
  int *v11; // r13
  int v12; // ecx
  int v13; // eax
  int *v14; // rcx
  void *v15; // rdx
  int v16; // eax
  size_t v17; // r8
  void *v18; // rdx
  int v19; // eax
  size_t v20; // r8
  void *v21; // rdx
  int v22; // eax
  size_t v23; // r8
  char v25; // [rsp+D0h] [rbp-118h]
  PVOID P; // [rsp+D8h] [rbp-110h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-108h] BYREF
  char *v28; // [rsp+E8h] [rbp-100h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-F8h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-F0h] BYREF
  char *v31; // [rsp+100h] [rbp-E8h]
  _OWORD v32[3]; // [rsp+108h] [rbp-E0h] BYREF
  void *v33[2]; // [rsp+138h] [rbp-B0h] BYREF
  void *v34[2]; // [rsp+148h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+158h] [rbp-90h]
  _QWORD v36[12]; // [rsp+160h] [rbp-88h] BYREF

  P = 0;
  *(_OWORD *)v33 = 0;
  v30 = 0;
  v29 = 0;
  v27 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v28 = 0;
  memset(v36, 0, 0x58u);
  v7 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v7 )
  {
    if ( a2 >= 0x2C )
    {
      memset(v32, 0, 44);
      v25 = 1;
      v31 = (char *)Src;
      if ( a3 )
        RtlCopyFromUser(v32, Src, 0x2Cu);
      else
        RtlCopyVolatileMemory(v32, Src, 0x2Cu);
      LODWORD(v36[4]) = v32[1];
      v8 = DWORD2(v32[2]);
      LODWORD(v36[10]) = DWORD2(v32[2]);
      v36[5] = DWORD1(v32[1]);
      LODWORD(v36[6]) = DWORD2(v32[1]);
      v36[2] = DWORD2(v32[0]);
      LODWORD(v36[1]) = DWORD1(v32[0]);
      LODWORD(v36[3]) = HIDWORD(v32[0]);
      v36[8] = LODWORD(v32[2]);
      v36[7] = HIDWORD(v32[1]);
      LODWORD(v36[9]) = DWORD1(v32[2]);
      v36[0] = SLODWORD(v32[0]);
      goto LABEL_13;
    }
    return 3221225485LL;
  }
  v31 = 0;
  v25 = 0;
  if ( a2 < 0x58 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(v36, Src, 0x58u);
  else
    RtlCopyVolatileMemory(v36, Src, 0x58u);
  v8 = v36[10];
LABEL_13:
  v9 = NsippProbeAndAllocateParameters(
         v36,
         0x58u,
         (__int64)&v36[1],
         (__m128i *)&v36[5],
         0,
         0,
         0,
         (__m128i *)&v36[7],
         a3,
         v8,
         0,
         (__m128i *)v33,
         &v27,
         0,
         0,
         0,
         0,
         0,
         (__m128i *)v34,
         &v30,
         &v29,
         0,
         0,
         &v28,
         &P);
  v10 = P;
  if ( v9 >= 0 )
  {
    v11 = (int *)((char *)P + 80);
    *((_DWORD *)P + 20) = v8;
    v10[5] = v27;
    *((_DWORD *)v10 + 12) = v8 != 0 ? LODWORD(v33[1]) : 0;
    v10[2] = v28;
    v10[8] = v29;
    v10[7] = v30;
    v12 = v8 != 0 ? v35 : 0;
    *((_DWORD *)v10 + 18) = v12;
    v9 = NsiEnumerateObjectsAllPersistentParametersWithMask(
           *((unsigned int *)v10 + 8),
           v10[2],
           *((unsigned int *)v10 + 6),
           v10[5],
           *((_DWORD *)v10 + 12),
           v10[7],
           v10[8],
           v12,
           v10 + 10);
    v13 = *v11;
    if ( v25 == 1 )
    {
      v14 = (int *)(v31 + 40);
      if ( !a3 )
      {
        *v14 = v13;
        goto LABEL_21;
      }
    }
    else
    {
      if ( !a3 )
      {
        Src[20] = v13;
LABEL_21:
        if ( v9 >= 0 )
        {
          *a4 = 88;
          v15 = (void *)v10[5];
          if ( v15 )
          {
            v16 = *((_DWORD *)v10 + 12);
            if ( v16 )
            {
              v17 = v8 * v16;
              if ( a3 )
                RtlCopyToUser(v33[0], v15, v17);
              else
                RtlCopyVolatileMemory(v33[0], v15, v17);
            }
          }
          v18 = (void *)v10[7];
          if ( v18 )
          {
            v19 = *((_DWORD *)v10 + 18);
            if ( v19 )
            {
              v20 = v8 * v19;
              if ( a3 )
                RtlCopyToUser(v34[0], v18, v20);
              else
                RtlCopyVolatileMemory(v34[0], v18, v20);
            }
          }
          v21 = (void *)v10[8];
          if ( v21 )
          {
            v22 = *((_DWORD *)v10 + 18);
            if ( v22 )
            {
              v23 = v8 * v22;
              if ( a3 )
                RtlCopyToUser(v34[1], v21, v23);
              else
                RtlCopyVolatileMemory(v34[1], v21, v23);
            }
          }
        }
        goto LABEL_37;
      }
      v14 = Src + 20;
    }
    RtlWriteULongToUser(v14, v13);
    goto LABEL_21;
  }
LABEL_37:
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140005c3c  mov     r11, rsp
0x140005c3f  mov     [r11+8], rbx
0x140005c43  mov     [r11+10h], rsi
0x140005c47  mov     [r11+20h], r9
0x140005c4b  push    rdi
0x140005c4c  push    r12
0x140005c4e  push    r13
0x140005c50  push    r14
0x140005c52  push    r15
0x140005c54  sub     rsp, 1C0h
0x140005c5b  mov     r14b, r8b
0x140005c5e  mov     edi, edx
0x140005c60  mov     rsi, rcx
0x140005c63  xor     ebx, ebx
0x140005c65  mov     [r11-110h], rbx
0x140005c6c  xorps   xmm0, xmm0
0x140005c6f  movups  xmmword ptr [rsp+1E8h+var_B0], xmm0
0x140005c77  mov     [r11-0F0h], rbx
0x140005c7e  mov     [r11-0F8h], rbx
0x140005c85  mov     [r11-108h], rbx
0x140005c8c  xor     eax, eax
0x140005c8e  movups  xmmword ptr [rsp+1E8h+var_A0], xmm0
0x140005c96  mov     [r11-90h], rax
0x140005c9d  mov     [r11-100h], rbx
0x140005ca4  lea     r12d, [rbx+58h]
0x140005ca8  mov     r8d, r12d; Size
0x140005cab  xor     edx, edx; Val
0x140005cad  lea     rcx, [r11-88h]; void *
0x140005cb4  call    memset
0x140005cb9  xor     ecx, ecx; Irp
0x140005cbb  call    cs:__imp_IoIs32bitProcess
0x140005cc2  nop     dword ptr [rax+rax+00h]
0x140005cc7  test    rsi, rsi
0x140005cca  jz      loc_1400060BD
0x140005cd0  test    al, al
0x140005cd2  jz      loc_140005DD6
0x140005cd8  lea     r8d, [rbx+2Ch]; Size
0x140005cdc  cmp     edi, r8d
0x140005cdf  jb      loc_1400060BD
0x140005ce5  xorps   xmm0, xmm0
0x140005ce8  movups  [rsp+1E8h+var_E0], xmm0
0x140005cf0  movups  [rsp+1E8h+var_D0], xmm0
0x140005cf8  movups  [rsp+1E8h+var_D0+0Ch], xmm0
0x140005d00  mov     [rsp+1E8h+var_118], 1
0x140005d08  mov     [rsp+1E8h+var_E8], rsi
0x140005d10  mov     rdx, rsi; Src
0x140005d13  lea     rcx, [rsp+1E8h+var_E0]; void *
0x140005d1b  test    r14b, r14b
0x140005d1e  jz      short loc_140005D27
0x140005d20  call    RtlCopyFromUser
0x140005d25  jmp     short loc_140005D2D
0x140005d27  call    RtlCopyVolatileMemory
0x140005d2c  nop
0x140005d2d  mov     eax, dword ptr [rsp+1E8h+var_D0]
0x140005d34  mov     [rsp+1E8h+var_68], eax
0x140005d3b  mov     r15d, [rsp+1E8h+var_B8]
0x140005d43  mov     [rsp+1E8h+var_38], r15d
0x140005d4b  mov     eax, dword ptr [rsp+1E8h+var_D0+4]
0x140005d52  mov     [rsp+1E8h+var_60], rax
0x140005d5a  mov     eax, dword ptr [rsp+1E8h+var_D0+8]
0x140005d61  mov     [rsp+1E8h+var_58], eax
0x140005d68  mov     eax, dword ptr [rsp+1E8h+var_E0+8]
0x140005d6f  mov     [rsp+1E8h+var_78], rax
0x140005d77  mov     eax, dword ptr [rsp+1E8h+var_E0+4]
0x140005d7e  mov     [rsp+1E8h+var_80], eax
0x140005d85  mov     eax, dword ptr [rsp+1E8h+var_E0+0Ch]
0x140005d8c  mov     [rsp+1E8h+var_70], eax
0x140005d93  mov     eax, [rsp+1E8h+var_C0]
0x140005d9a  mov     [rsp+1E8h+var_48], rax
0x140005da2  mov     eax, dword ptr [rsp+1E8h+var_D0+0Ch]
0x140005da9  mov     [rsp+1E8h+var_50], rax
0x140005db1  mov     eax, [rsp+1E8h+var_BC]
0x140005db8  mov     [rsp+1E8h+var_40], eax
0x140005dbf  movsxd  rax, dword ptr [rsp+1E8h+var_E0]
0x140005dc7  mov     [rsp+1E8h+var_88], rax
0x140005dcf  jmp     short loc_140005E16
0x140005dd1  jmp     loc_1400060C2
0x140005dd6  mov     [rsp+1E8h+var_E8], rbx
0x140005dde  mov     [rsp+1E8h+var_118], bl
0x140005de5  cmp     edi, r12d
0x140005de8  jb      loc_1400060BD
0x140005dee  mov     r8, r12; Size
0x140005df1  mov     rdx, rsi; Src
0x140005df4  lea     rcx, [rsp+1E8h+var_88]; void *
0x140005dfc  test    r14b, r14b
0x140005dff  jz      short loc_140005E08
0x140005e01  call    RtlCopyFromUser
0x140005e06  jmp     short loc_140005E0E
0x140005e08  call    RtlCopyVolatileMemory
0x140005e0d  nop
0x140005e0e  mov     r15d, [rsp+1E8h+var_38]
0x140005e16  lea     rax, [rsp+1E8h+P]
0x140005e1e  mov     [rsp+1E8h+var_128], rax
0x140005e26  lea     rax, [rsp+1E8h+var_100]
0x140005e2e  mov     [rsp+1E8h+var_130], rax
0x140005e36  mov     [rsp+1E8h+var_138], rbx
0x140005e3e  mov     [rsp+1E8h+var_140], rbx
0x140005e46  lea     rax, [rsp+1E8h+var_F8]
0x140005e4e  mov     [rsp+1E8h+var_148], rax
0x140005e56  lea     rax, [rsp+1E8h+var_F0]
0x140005e5e  mov     [rsp+1E8h+var_150], rax
0x140005e66  lea     rax, [rsp+1E8h+var_A0]
0x140005e6e  mov     [rsp+1E8h+var_158], rax
0x140005e76  mov     [rsp+1E8h+var_160], rbx
0x140005e7e  mov     [rsp+1E8h+var_168], rbx
0x140005e86  mov     [rsp+1E8h+var_170], rbx
0x140005e8b  mov     [rsp+1E8h+var_178], rbx
0x140005e90  mov     [rsp+1E8h+var_180], rbx
0x140005e95  lea     rax, [rsp+1E8h+var_108]
0x140005e9d  mov     [rsp+1E8h+var_188], rax
0x140005ea2  lea     rax, [rsp+1E8h+var_B0]
0x140005eaa  mov     [rsp+1E8h+var_190], rax
0x140005eaf  mov     [rsp+1E8h+var_198], bl
0x140005eb3  mov     [rsp+1E8h+var_1A0], r15d
0x140005eb8  mov     byte ptr [rsp+1E8h+var_1A8], r14b
0x140005ebd  lea     rax, [rsp+1E8h+var_50]
0x140005ec5  mov     [rsp+1E8h+var_1B0], rax
0x140005eca  mov     [rsp+1E8h+var_1B8], rbx
0x140005ecf  mov     [rsp+1E8h+var_1C0], rbx
0x140005ed4  mov     [rsp+1E8h+var_1C8], rbx
0x140005ed9  lea     r9, [rsp+1E8h+var_60]
0x140005ee1  lea     r8, [rsp+1E8h+var_80]
0x140005ee9  mov     edx, r12d
0x140005eec  lea     rcx, [rsp+1E8h+var_88]
0x140005ef4  call    NsippProbeAndAllocateParameters
0x140005ef9  mov     r12d, eax
0x140005efc  mov     rdi, [rsp+1E8h+P]
0x140005f04  test    eax, eax
0x140005f06  js      loc_1400060A0
0x140005f0c  lea     r13, [rdi+50h]
0x140005f10  mov     [r13+0], r15d
0x140005f14  mov     rax, [rsp+1E8h+var_108]
0x140005f1c  mov     [rdi+28h], rax
0x140005f20  mov     eax, r15d
0x140005f23  neg     eax
0x140005f25  sbb     ecx, ecx
0x140005f27  and     ecx, dword ptr [rsp+1E8h+var_B0+8]
0x140005f2e  mov     [rdi+30h], ecx
0x140005f31  mov     rax, [rsp+1E8h+var_100]
0x140005f39  mov     [rdi+10h], rax
0x140005f3d  mov     rax, [rsp+1E8h+var_F8]
0x140005f45  mov     [rdi+40h], rax
0x140005f49  mov     rax, [rsp+1E8h+var_F0]
0x140005f51  mov     [rdi+38h], rax
0x140005f55  mov     eax, r15d
0x140005f58  neg     eax
0x140005f5a  sbb     ecx, ecx
0x140005f5c  and     ecx, dword ptr [rsp+1E8h+var_90]
0x140005f63  mov     [rdi+48h], ecx
0x140005f66  mov     [rsp+1E8h+var_1A8], r13
0x140005f6b  mov     dword ptr [rsp+1E8h+var_1B0], ecx
0x140005f6f  mov     rax, [rdi+40h]
0x140005f73  mov     [rsp+1E8h+var_1B8], rax
0x140005f78  mov     rax, [rdi+38h]
0x140005f7c  mov     [rsp+1E8h+var_1C0], rax
0x140005f81  mov     eax, [rdi+30h]
0x140005f84  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x140005f88  mov     r9, [rdi+28h]
0x140005f8c  mov     r8d, [rdi+18h]
0x140005f90  mov     rdx, [rdi+10h]
0x140005f94  mov     ecx, [rdi+20h]
0x140005f97  call    cs:__imp_NsiEnumerateObjectsAllPersistentParametersWithMask
0x140005f9e  nop     dword ptr [rax+rax+00h]
0x140005fa3  mov     r12d, eax
0x140005fa6  mov     eax, [r13+0]
0x140005faa  cmp     [rsp+1E8h+var_118], 1
0x140005fb2  jnz     short loc_140005FC9
0x140005fb4  mov     rcx, [rsp+1E8h+var_E8]
0x140005fbc  add     rcx, 28h ; '('
0x140005fc0  test    r14b, r14b
0x140005fc3  jnz     short loc_140005FD2
0x140005fc5  mov     [rcx], eax
0x140005fc7  jmp     short loc_140005FDE
0x140005fc9  test    r14b, r14b
0x140005fcc  jz      short loc_140005FDB
0x140005fce  lea     rcx, [rsi+50h]
0x140005fd2  mov     edx, eax
0x140005fd4  call    RtlWriteULongToUser
0x140005fd9  jmp     short loc_140005FDE
0x140005fdb  mov     [rsi+50h], eax
0x140005fde  test    r12d, r12d
0x140005fe1  js      loc_1400060A0
0x140005fe7  mov     rax, [rsp+1E8h+arg_18]
0x140005fef  mov     qword ptr [rax], 58h ; 'X'
0x140005ff6  mov     rdx, [rdi+28h]; Src
0x140005ffa  test    rdx, rdx
0x140005ffd  jz      short loc_140006026
0x140005fff  mov     eax, [rdi+30h]
0x140006002  test    eax, eax
0x140006004  jz      short loc_140006026
0x140006006  imul    eax, r15d
0x14000600a  mov     r8d, eax; Size
0x14000600d  mov     rcx, [rsp+1E8h+var_B0]; void *
0x140006015  test    r14b, r14b
0x140006018  jz      short loc_140006021
0x14000601a  call    RtlCopyToUser
0x14000601f  jmp     short loc_140006026
0x140006021  call    RtlCopyVolatileMemory
0x140006026  mov     rdx, [rdi+38h]; Src
0x14000602a  test    rdx, rdx
0x14000602d  jz      short loc_140006056
0x14000602f  mov     eax, [rdi+48h]
0x140006032  test    eax, eax
0x140006034  jz      short loc_140006056
0x140006036  imul    eax, r15d
0x14000603a  mov     r8d, eax; Size
0x14000603d  mov     rcx, [rsp+1E8h+var_A0]; void *
0x140006045  test    r14b, r14b
0x140006048  jz      short loc_140006051
0x14000604a  call    RtlCopyToUser
0x14000604f  jmp     short loc_140006056
0x140006051  call    RtlCopyVolatileMemory
0x140006056  mov     rdx, [rdi+40h]; Src
0x14000605a  test    rdx, rdx
0x14000605d  jz      short loc_140006086
0x14000605f  mov     eax, [rdi+48h]
0x140006062  test    eax, eax
0x140006064  jz      short loc_140006086
0x140006066  imul    eax, r15d
0x14000606a  mov     r8d, eax; Size
0x14000606d  mov     rcx, [rsp+1E8h+var_A0+8]; void *
0x140006075  test    r14b, r14b
0x140006078  jz      short loc_140006081
0x14000607a  call    RtlCopyToUser
0x14000607f  jmp     short loc_140006086
0x140006081  call    RtlCopyVolatileMemory
0x140006086  jmp     short loc_1400060A0
0x140006088  mov     r12d, eax
0x14000608b  mov     rdi, [rsp+1E8h+P]
0x140006093  jmp     short loc_1400060A0
0x140006095  mov     r12d, eax
0x140006098  mov     rdi, [rsp+1E8h+P]
0x1400060a0  test    rdi, rdi
0x1400060a3  jz      short loc_1400060B6
0x1400060a5  xor     edx, edx; Tag
0x1400060a7  mov     rcx, rdi; P
0x1400060aa  call    cs:__imp_ExFreePoolWithTag
0x1400060b1  nop     dword ptr [rax+rax+00h]
0x1400060b6  mov     eax, r12d
0x1400060b9  jmp     short loc_1400060C2
0x1400060bb  jmp     short loc_1400060C2
0x1400060bd  mov     eax, 0C000000Dh
0x1400060c2  lea     r11, [rsp+1E8h+var_28]
0x1400060ca  mov     rbx, [r11+30h]
0x1400060ce  mov     rsi, [r11+38h]
0x1400060d2  mov     rsp, r11
0x1400060d5  pop     r15
0x1400060d7  pop     r14
0x1400060d9  pop     r13
0x1400060db  pop     r12
0x1400060dd  pop     rdi
0x1400060de  retn
```
