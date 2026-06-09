# NsippSetAllPersistentParametersWithMask

- ea: `0x1400060e8`
- end: `0x140006428`
- name: `NsippSetAllPersistentParametersWithMask`
- size: `832`
- prototype: `__int64 __fastcall(void *Src, unsigned int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x1400043d0`
- `0x1400056e8`
- `0x1400060e8`
- `0x140006560`
- `0x140006980`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140006153`
- `ntoskrnl!IoIs32bitProcess` at `0x140006153`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063f7`
- `NETIO!NsiSetAllPersistentParametersWithMask` at `0x1400063df`
- `NETIO!NsiSetAllPersistentParametersWithMask` at `0x1400063df`

## pseudocode

```c
__int64 __fastcall NsippSetAllPersistentParametersWithMask(void *Src, unsigned int a2, char a3)
{
  BOOLEAN v6; // al
  int Parameters; // edi
  _DWORD *v8; // rbx
  int v9; // eax
  __int64 v11; // [rsp+D0h] [rbp-E8h] BYREF
  __int64 v12; // [rsp+D8h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+E8h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+100h] [rbp-B8h]
  __int64 v17; // [rsp+110h] [rbp-A8h]
  _QWORD v18[10]; // [rsp+120h] [rbp-98h] BYREF
  __int128 v19; // [rsp+170h] [rbp-48h] BYREF
  _BYTE v20[16]; // [rsp+180h] [rbp-38h] BYREF
  __int64 v21; // [rsp+190h] [rbp-28h]
  PVOID P; // [rsp+1D8h] [rbp+20h] BYREF

  P = 0;
  v19 = 0;
  v14 = 0;
  v13 = 0;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  memset(v18, 0, sizeof(v18));
  v6 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v6 )
  {
    if ( a2 >= 0x28 )
    {
      v15 = 0;
      v16 = 0;
      v17 = 0;
      if ( a3 )
        RtlCopyFromUser(&v15, Src, 0x28u);
      else
        RtlCopyVolatileMemory(&v15, Src, 0x28u);
      LODWORD(v18[4]) = v16;
      v18[5] = DWORD1(v16);
      LODWORD(v18[6]) = DWORD2(v16);
      v18[2] = DWORD2(v15);
      LODWORD(v18[1]) = DWORD1(v15);
      LODWORD(v18[3]) = HIDWORD(v15);
      v18[8] = (unsigned int)v17;
      v18[7] = HIDWORD(v16);
      LODWORD(v18[9]) = HIDWORD(v17);
      v18[0] = (int)v15;
      goto LABEL_12;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x50 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(v18, Src, 0x50u);
  else
    RtlCopyVolatileMemory(v18, Src, 0x50u);
LABEL_12:
  Parameters = NsippProbeAndAllocateParameters(
                 (unsigned int)v18,
                 80,
                 (unsigned int)&v18[1],
                 (unsigned int)&v18[5],
                 0,
                 0,
                 0,
                 (__int64)&v18[7],
                 a3,
                 1,
                 1,
                 (__int64)&v19,
                 (__int64)&v11,
                 0,
                 0,
                 0,
                 0,
                 0,
                 (__int64)v20,
                 (__int64)&v14,
                 (__int64)&v13,
                 0,
                 0,
                 (__int64)&v12,
                 (__int64)&P);
  v8 = P;
  if ( Parameters >= 0 )
  {
    *((_QWORD *)P + 5) = v11;
    v8[12] = DWORD2(v19);
    *((_QWORD *)v8 + 2) = v12;
    *((_QWORD *)v8 + 8) = v13;
    *((_QWORD *)v8 + 7) = v14;
    v9 = v21;
    v8[18] = v21;
    Parameters = NsiSetAllPersistentParametersWithMask(
                   (unsigned int)v8[8],
                   *((_QWORD *)v8 + 2),
                   (unsigned int)v8[6],
                   *((_QWORD *)v8 + 5),
                   v8[12],
                   *((_QWORD *)v8 + 7),
                   *((_QWORD *)v8 + 8),
                   v9);
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x1400060e8  mov     r11, rsp
0x1400060eb  mov     [r11+8], rbx
0x1400060ef  mov     [r11+10h], rsi
0x1400060f3  mov     [r11+20h], r9
0x1400060f7  push    rdi
0x1400060f8  push    r14
0x1400060fa  push    r15
0x1400060fc  sub     rsp, 1A0h
0x140006103  mov     sil, r8b
0x140006106  mov     edi, edx
0x140006108  mov     rbx, rcx
0x14000610b  xor     r14d, r14d
0x14000610e  mov     [r11+20h], r14
0x140006112  xorps   xmm0, xmm0
0x140006115  movups  xmmword ptr [r11-48h], xmm0
0x14000611a  mov     [r11-0D0h], r14
0x140006121  mov     [r11-0D8h], r14
0x140006128  mov     [r11-0E8h], r14
0x14000612f  xor     eax, eax
0x140006131  mov     [r11-28h], rax
0x140006135  mov     [r11-0E0h], r14
0x14000613c  lea     r15d, [r14+50h]
0x140006140  mov     r8d, r15d; Size
0x140006143  xor     edx, edx; Val
0x140006145  lea     rcx, [r11-98h]; void *
0x14000614c  call    memset
0x140006151  xor     ecx, ecx; Irp
0x140006153  call    cs:__imp_IoIs32bitProcess
0x14000615a  nop     dword ptr [rax+rax+00h]
0x14000615f  test    rbx, rbx
0x140006162  jz      loc_140006409
0x140006168  test    al, al
0x14000616a  jz      loc_140006250
0x140006170  lea     r8d, [r14+28h]; Size
0x140006174  cmp     edi, r8d
0x140006177  jb      loc_140006409
0x14000617d  xorps   xmm0, xmm0
0x140006180  xor     eax, eax
0x140006182  movups  [rsp+1B8h+var_C8], xmm0
0x14000618a  movups  [rsp+1B8h+var_B8], xmm0
0x140006192  mov     [rsp+1B8h+var_A8], rax
0x14000619a  mov     rdx, rbx; Src
0x14000619d  lea     rcx, [rsp+1B8h+var_C8]; void *
0x1400061a5  test    sil, sil
0x1400061a8  jz      short loc_1400061B1
0x1400061aa  call    RtlCopyFromUser
0x1400061af  jmp     short loc_1400061B7
0x1400061b1  call    RtlCopyVolatileMemory
0x1400061b6  nop
0x1400061b7  mov     eax, dword ptr [rsp+1B8h+var_B8]
0x1400061be  mov     [rsp+1B8h+var_78], eax
0x1400061c5  mov     eax, dword ptr [rsp+1B8h+var_B8+4]
0x1400061cc  mov     [rsp+1B8h+var_70], rax
0x1400061d4  mov     eax, dword ptr [rsp+1B8h+var_B8+8]
0x1400061db  mov     [rsp+1B8h+var_68], eax
0x1400061e2  mov     eax, dword ptr [rsp+1B8h+var_C8+8]
0x1400061e9  mov     [rsp+1B8h+var_88], rax
0x1400061f1  mov     eax, dword ptr [rsp+1B8h+var_C8+4]
0x1400061f8  mov     [rsp+1B8h+var_90], eax
0x1400061ff  mov     eax, dword ptr [rsp+1B8h+var_C8+0Ch]
0x140006206  mov     [rsp+1B8h+var_80], eax
0x14000620d  mov     eax, dword ptr [rsp+1B8h+var_A8]
0x140006214  mov     [rsp+1B8h+var_58], rax
0x14000621c  mov     eax, dword ptr [rsp+1B8h+var_B8+0Ch]
0x140006223  mov     [rsp+1B8h+var_60], rax
0x14000622b  mov     eax, dword ptr [rsp+1B8h+var_A8+4]
0x140006232  mov     [rsp+1B8h+var_50], eax
0x140006239  movsxd  rax, dword ptr [rsp+1B8h+var_C8]
0x140006241  mov     [rsp+1B8h+var_98], rax
0x140006249  jmp     short loc_140006279
0x14000624b  jmp     loc_14000640E
0x140006250  cmp     edi, r15d
0x140006253  jb      loc_140006409
0x140006259  mov     r8, r15; Size
0x14000625c  mov     rdx, rbx; Src
0x14000625f  lea     rcx, [rsp+1B8h+var_98]; void *
0x140006267  test    sil, sil
0x14000626a  jz      short loc_140006273
0x14000626c  call    RtlCopyFromUser
0x140006271  jmp     short loc_140006279
0x140006273  call    RtlCopyVolatileMemory
0x140006278  nop
0x140006279  lea     rax, [rsp+1B8h+P]
0x140006281  mov     [rsp+1B8h+var_F8], rax
0x140006289  lea     rax, [rsp+1B8h+var_E0]
0x140006291  mov     [rsp+1B8h+var_100], rax
0x140006299  mov     [rsp+1B8h+var_108], r14
0x1400062a1  mov     [rsp+1B8h+var_110], r14
0x1400062a9  lea     rax, [rsp+1B8h+var_D8]
0x1400062b1  mov     [rsp+1B8h+var_118], rax
0x1400062b9  lea     rax, [rsp+1B8h+var_D0]
0x1400062c1  mov     [rsp+1B8h+var_120], rax
0x1400062c9  lea     rax, [rsp+1B8h+var_38]
0x1400062d1  mov     [rsp+1B8h+var_128], rax
0x1400062d9  mov     [rsp+1B8h+var_130], r14
0x1400062e1  mov     [rsp+1B8h+var_138], r14
0x1400062e9  mov     [rsp+1B8h+var_140], r14
0x1400062ee  mov     [rsp+1B8h+var_148], r14
0x1400062f3  mov     [rsp+1B8h+var_150], r14
0x1400062f8  lea     rax, [rsp+1B8h+var_E8]
0x140006300  mov     [rsp+1B8h+var_158], rax
0x140006305  lea     rax, [rsp+1B8h+var_48]
0x14000630d  mov     [rsp+1B8h+var_160], rax
0x140006312  mov     [rsp+1B8h+var_168], 1
0x140006317  mov     [rsp+1B8h+var_170], 1
0x14000631f  mov     [rsp+1B8h+var_178], sil
0x140006324  lea     rax, [rsp+1B8h+var_60]
0x14000632c  mov     [rsp+1B8h+var_180], rax
0x140006331  mov     [rsp+1B8h+var_188], r14
0x140006336  mov     [rsp+1B8h+var_190], r14
0x14000633b  mov     [rsp+1B8h+var_198], r14
0x140006340  lea     r9, [rsp+1B8h+var_70]
0x140006348  lea     r8, [rsp+1B8h+var_90]
0x140006350  mov     edx, r15d
0x140006353  lea     rcx, [rsp+1B8h+var_98]
0x14000635b  call    NsippProbeAndAllocateParameters
0x140006360  mov     edi, eax
0x140006362  mov     rbx, [rsp+1B8h+P]
0x14000636a  test    eax, eax
0x14000636c  js      short loc_1400063ED
0x14000636e  mov     rax, [rsp+1B8h+var_E8]
0x140006376  mov     [rbx+28h], rax
0x14000637a  mov     eax, [rsp+1B8h+var_40]
0x140006381  mov     [rbx+30h], eax
0x140006384  mov     rax, [rsp+1B8h+var_E0]
0x14000638c  mov     [rbx+10h], rax
0x140006390  mov     rax, [rsp+1B8h+var_D8]
0x140006398  mov     [rbx+40h], rax
0x14000639c  mov     rax, [rsp+1B8h+var_D0]
0x1400063a4  mov     [rbx+38h], rax
0x1400063a8  mov     rax, [rsp+1B8h+var_28]
0x1400063b0  mov     [rbx+48h], eax
0x1400063b3  mov     dword ptr [rsp+1B8h+var_180], eax
0x1400063b7  mov     rax, [rbx+40h]
0x1400063bb  mov     [rsp+1B8h+var_188], rax
0x1400063c0  mov     rax, [rbx+38h]
0x1400063c4  mov     [rsp+1B8h+var_190], rax
0x1400063c9  mov     eax, [rbx+30h]
0x1400063cc  mov     dword ptr [rsp+1B8h+var_198], eax
0x1400063d0  mov     r9, [rbx+28h]
0x1400063d4  mov     r8d, [rbx+18h]
0x1400063d8  mov     rdx, [rbx+10h]
0x1400063dc  mov     ecx, [rbx+20h]
0x1400063df  call    cs:__imp_NsiSetAllPersistentParametersWithMask
0x1400063e6  nop     dword ptr [rax+rax+00h]
0x1400063eb  mov     edi, eax
0x1400063ed  test    rbx, rbx
0x1400063f0  jz      short loc_140006403
0x1400063f2  xor     edx, edx; Tag
0x1400063f4  mov     rcx, rbx; P
0x1400063f7  call    cs:__imp_ExFreePoolWithTag
0x1400063fe  nop     dword ptr [rax+rax+00h]
0x140006403  mov     eax, edi
0x140006405  jmp     short loc_14000640E
0x140006407  jmp     short loc_14000640E
0x140006409  mov     eax, 0C000000Dh
0x14000640e  lea     r11, [rsp+1B8h+var_18]
0x140006416  mov     rbx, [r11+20h]
0x14000641a  mov     rsi, [r11+28h]
0x14000641e  mov     rsp, r11
0x140006421  pop     r15
0x140006423  pop     r14
0x140006425  pop     rdi
0x140006426  retn
```
