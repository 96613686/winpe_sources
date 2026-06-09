# NsippEnumerateObjectsAllParameters

- ea: `0x140002850`
- end: `0x140002ea9`
- name: `NsippEnumerateObjectsAllParameters`
- size: `1625`
- prototype: `__int64 __fastcall(char *Src, unsigned int, unsigned __int8, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140002850`
- `0x1400043d0`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`
- `0x14000d08c`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400028dc`
- `ntoskrnl!IoIs32bitProcess` at `0x1400028dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d3b`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x140002abc`
- `NETIO!NsiEnumerateObjectsAllParametersEx` at `0x140002abc`

## pseudocode

```c
__int64 __fastcall NsippEnumerateObjectsAllParameters(char *Src, unsigned int a2, unsigned __int8 a3, _QWORD *a4)
{
  BOOLEAN v7; // al
  char v8; // r12
  char *v9; // r13
  unsigned int v10; // r15d
  int v11; // ebx
  _QWORD *v12; // rdi
  __int32 v13; // eax
  int v14; // eax
  int v15; // eax
  __int32 v16; // eax
  unsigned int v17; // eax
  unsigned int *v18; // rcx
  void *v19; // rdx
  int v20; // eax
  size_t v21; // r8
  void *v22; // rdx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  size_t v26; // r8
  void *v27; // rdx
  size_t v28; // r8
  void *v29; // rdx
  int v30; // eax
  size_t v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int *v34; // rcx
  unsigned int *v35; // rcx
  unsigned int *v36; // rcx
  unsigned int *v37; // rcx
  PVOID P; // [rsp+D0h] [rbp-148h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-140h] BYREF
  char *v41; // [rsp+E0h] [rbp-138h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-130h] BYREF
  __int64 v43; // [rsp+F0h] [rbp-128h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-120h] BYREF
  __m128i v45; // [rsp+100h] [rbp-118h] BYREF
  __int128 v46; // [rsp+110h] [rbp-108h]
  __int128 v47; // [rsp+120h] [rbp-F8h]
  __int128 v48; // [rsp+130h] [rbp-E8h] BYREF
  __int128 v49; // [rsp+140h] [rbp-D8h]
  _OWORD v50[2]; // [rsp+150h] [rbp-C8h] BYREF
  __m128i v51; // [rsp+170h] [rbp-A8h] BYREF
  _QWORD v52[14]; // [rsp+180h] [rbp-98h] BYREF

  v51 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v40 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v41 = 0;
  P = 0;
  memset(v52, 0, sizeof(v52));
  v7 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( !v7 )
  {
    v8 = 0;
    v9 = 0;
    if ( a2 >= 0x70 )
    {
      if ( a3 )
        RtlCopyFromUser(v52, Src, 0x70u);
      else
        RtlCopyVolatileMemory(v52, Src, 0x70u);
      v10 = v52[13];
      goto LABEL_8;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x3C )
    return 3221225485LL;
  v48 = 0;
  v49 = 0;
  memset(v50, 0, 28);
  v8 = 1;
  v9 = Src;
  if ( a3 )
    RtlCopyFromUser(&v48, Src, 0x3Cu);
  else
    RtlCopyVolatileMemory(&v48, Src, 0x3Cu);
  v52[5] = DWORD2(v49);
  LODWORD(v52[6]) = HIDWORD(v49);
  v52[2] = DWORD2(v48);
  LODWORD(v52[1]) = DWORD1(v48);
  LODWORD(v52[3]) = HIDWORD(v48);
  v52[9] = DWORD2(v50[0]);
  LODWORD(v52[10]) = HIDWORD(v50[0]);
  v52[11] = LODWORD(v50[1]);
  LODWORD(v52[12]) = DWORD1(v50[1]);
  v52[7] = LODWORD(v50[0]);
  LODWORD(v52[8]) = DWORD1(v50[0]);
  v52[4] = v49;
  v52[0] = (int)v48;
  v10 = DWORD2(v50[1]);
  LODWORD(v52[13]) = DWORD2(v50[1]);
LABEL_8:
  v11 = NsippProbeAndAllocateParameters(
          v52,
          0x70u,
          (__int64)&v52[1],
          (__m128i *)&v52[5],
          0,
          (__m128i *)&v52[7],
          0,
          0,
          a3,
          v10,
          0,
          &v51,
          &v40,
          0,
          0,
          0,
          &v45,
          &v44,
          0,
          0,
          0,
          &v42,
          &v43,
          &v41,
          &P);
  v12 = P;
  if ( v11 >= 0 )
  {
    *((_DWORD *)P + 26) = v10;
    v12[5] = v40;
    v13 = 0;
    if ( v10 )
      v13 = v51.m128i_i32[2];
    *((_DWORD *)v12 + 12) = v13;
    v12[2] = v41;
    v12[9] = v42;
    v14 = 0;
    if ( v10 )
      v14 = DWORD2(v46);
    *((_DWORD *)v12 + 20) = v14;
    v12[11] = v43;
    v15 = 0;
    if ( v10 )
      v15 = DWORD2(v47);
    *((_DWORD *)v12 + 24) = v15;
    v12[7] = v44;
    v16 = 0;
    if ( v10 )
      v16 = v45.m128i_i32[2];
    *((_DWORD *)v12 + 16) = v16;
    v11 = NsiEnumerateObjectsAllParametersEx(v12);
    v17 = *((_DWORD *)v12 + 26);
    if ( v8 == 1 )
    {
      v18 = (unsigned int *)(v9 + 56);
      if ( a3 )
      {
LABEL_19:
        RtlWriteULongToUser(v18, v17);
        goto LABEL_23;
      }
    }
    else
    {
      v18 = (unsigned int *)(Src + 104);
      if ( a3 )
        goto LABEL_19;
    }
    *v18 = v17;
LABEL_23:
    if ( v11 >= 0 )
    {
      *a4 = 112;
      v19 = (void *)v12[5];
      if ( v19 )
      {
        v20 = *((_DWORD *)v12 + 12);
        if ( v20 )
        {
          v21 = v10 * v20;
          if ( a3 )
            RtlCopyToUser((void *)v51.m128i_i64[0], v19, v21);
          else
            RtlCopyVolatileMemory((void *)v51.m128i_i64[0], v19, v21);
        }
      }
      v22 = (void *)v12[9];
      if ( v22 )
      {
        v30 = *((_DWORD *)v12 + 20);
        if ( v30 )
        {
          v31 = v10 * v30;
          if ( a3 )
            RtlCopyToUser((void *)v46, v22, v31);
          else
            RtlCopyVolatileMemory((void *)v46, v22, v31);
        }
      }
      if ( (_QWORD)v47 && DWORD2(v47) )
      {
        v26 = *((_DWORD *)v12 + 24) * v10;
        v27 = (void *)v12[11];
        if ( a3 )
          RtlCopyToUser((void *)v47, v27, v26);
        else
          RtlCopyVolatileMemory((void *)v47, v27, v26);
      }
      if ( v45.m128i_i64[0] && v45.m128i_i32[2] )
      {
        v28 = *((_DWORD *)v12 + 16) * v10;
        v29 = (void *)v12[7];
        if ( a3 )
          RtlCopyToUser((void *)v45.m128i_i64[0], v29, v28);
        else
          RtlCopyVolatileMemory((void *)v45.m128i_i64[0], v29, v28);
      }
      if ( v10 )
      {
        v23 = *((_DWORD *)v12 + 20);
        if ( v8 == 1 )
        {
          if ( v23 != DWORD2(v46) )
          {
            v34 = (unsigned int *)(v9 + 44);
            if ( a3 )
              RtlWriteULongToUser(v34, v23);
            else
              *v34 = v23;
          }
          v32 = *((_DWORD *)v12 + 24);
          if ( v32 != DWORD2(v47) )
          {
            v35 = (unsigned int *)(v9 + 52);
            if ( a3 )
              RtlWriteULongToUser(v35, v32);
            else
              *v35 = v32;
          }
          v33 = *((_DWORD *)v12 + 16);
          if ( v33 != v45.m128i_i32[2] )
          {
            if ( a3 )
              RtlWriteULongToUser(v9 + 36, v33);
            else
              *((_DWORD *)v9 + 9) = v33;
          }
        }
        else
        {
          if ( v23 != DWORD2(v46) )
          {
            v36 = (unsigned int *)(Src + 80);
            if ( a3 )
              RtlWriteULongToUser(v36, v23);
            else
              *v36 = v23;
          }
          v24 = *((_DWORD *)v12 + 24);
          if ( v24 != DWORD2(v47) )
          {
            v37 = (unsigned int *)(Src + 96);
            if ( a3 )
              RtlWriteULongToUser(v37, v24);
            else
              *v37 = v24;
          }
          v25 = *((_DWORD *)v12 + 16);
          if ( v25 != v45.m128i_i32[2] )
          {
            if ( a3 )
              RtlWriteULongToUser(Src + 64, v25);
            else
              *((_DWORD *)Src + 16) = v25;
          }
        }
      }
    }
  }
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140002850  mov     rax, rsp
0x140002853  mov     [rax+8], rbx
0x140002857  mov     [rax+10h], rsi
0x14000285b  mov     [rax+20h], r9
0x14000285f  push    rdi
0x140002860  push    r12
0x140002862  push    r13
0x140002864  push    r14
0x140002866  push    r15
0x140002868  sub     rsp, 1F0h
0x14000286f  movzx   esi, r8b
0x140002873  mov     ebx, edx
0x140002875  mov     r14, rcx
0x140002878  xorps   xmm0, xmm0
0x14000287b  movups  xmmword ptr [rax-0A8h], xmm0
0x140002882  xorps   xmm1, xmm1
0x140002885  movups  xmmword ptr [rax-118h], xmm1
0x14000288c  movups  xmmword ptr [rax-108h], xmm1
0x140002893  movups  xmmword ptr [rax-0F8h], xmm1
0x14000289a  xor     edi, edi
0x14000289c  mov     [rax-140h], rdi
0x1400028a3  mov     [rax-130h], rdi
0x1400028aa  mov     [rax-128h], rdi
0x1400028b1  mov     [rax-120h], rdi
0x1400028b8  mov     [rax-138h], rdi
0x1400028bf  mov     [rax-148h], rdi
0x1400028c6  xor     edx, edx; Val
0x1400028c8  mov     r8d, 70h ; 'p'; Size
0x1400028ce  lea     rcx, [rax-98h]; void *
0x1400028d5  call    memset
0x1400028da  xor     ecx, ecx; Irp
0x1400028dc  call    cs:__imp_IoIs32bitProcess
0x1400028e3  nop     dword ptr [rax+rax+00h]
0x1400028e8  test    r14, r14
0x1400028eb  jz      loc_140002E9F
0x1400028f1  test    al, al
0x1400028f3  jnz     loc_140002D67
0x1400028f9  xor     r12b, r12b
0x1400028fc  mov     r13d, edi
0x1400028ff  cmp     ebx, 70h ; 'p'
0x140002902  jb      loc_140002E9F
0x140002908  mov     r8d, 70h ; 'p'; Size
0x14000290e  mov     rdx, r14; Src
0x140002911  lea     rcx, [rsp+218h+var_98]; void *
0x140002919  test    sil, sil
0x14000291c  jz      short loc_140002925
0x14000291e  call    RtlCopyFromUser
0x140002923  jmp     short loc_14000292A
0x140002925  call    RtlCopyVolatileMemory
0x14000292a  jmp     short loc_140002931
0x14000292c  jmp     loc_140002D49
0x140002931  mov     r15d, [rsp+218h+var_30]
0x140002939  lea     rax, [rsp+218h+P]
0x140002941  mov     [rsp+218h+var_158], rax
0x140002949  lea     rax, [rsp+218h+var_138]
0x140002951  mov     [rsp+218h+var_160], rax
0x140002959  lea     rax, [rsp+218h+var_128]
0x140002961  mov     [rsp+218h+var_168], rax
0x140002969  lea     rax, [rsp+218h+var_130]
0x140002971  mov     [rsp+218h+var_170], rax
0x140002979  mov     [rsp+218h+var_178], rdi
0x140002981  mov     [rsp+218h+var_180], rdi
0x140002989  mov     [rsp+218h+var_188], rdi
0x140002991  lea     rax, [rsp+218h+var_120]
0x140002999  mov     [rsp+218h+var_190], rax
0x1400029a1  lea     rax, [rsp+218h+var_118]
0x1400029a9  mov     [rsp+218h+var_198], rax
0x1400029b1  mov     [rsp+218h+var_1A0], rdi
0x1400029b6  mov     [rsp+218h+var_1A8], rdi
0x1400029bb  mov     [rsp+218h+var_1B0], rdi
0x1400029c0  lea     rax, [rsp+218h+var_140]
0x1400029c8  mov     [rsp+218h+var_1B8], rax
0x1400029cd  lea     rax, [rsp+218h+var_A8]
0x1400029d5  mov     [rsp+218h+var_1C0], rax
0x1400029da  mov     [rsp+218h+var_1C8], 0
0x1400029df  mov     [rsp+218h+var_1D0], r15d
0x1400029e4  mov     [rsp+218h+var_1D8], sil
0x1400029e9  mov     [rsp+218h+var_1E0], rdi
0x1400029ee  mov     [rsp+218h+var_1E8], rdi
0x1400029f3  lea     rax, [rsp+218h+var_60]
0x1400029fb  mov     [rsp+218h+var_1F0], rax
0x140002a00  mov     [rsp+218h+var_1F8], rdi
0x140002a05  lea     r9, [rsp+218h+var_70]
0x140002a0d  lea     r8, [rsp+218h+var_90]
0x140002a15  mov     edx, 70h ; 'p'
0x140002a1a  lea     rcx, [rsp+218h+var_98]
0x140002a22  call    NsippProbeAndAllocateParameters
0x140002a27  mov     ebx, eax
0x140002a29  mov     rdi, [rsp+218h+P]
0x140002a31  test    eax, eax
0x140002a33  js      loc_140002D31
0x140002a39  mov     [rdi+68h], r15d
0x140002a3d  mov     rax, [rsp+218h+var_140]
0x140002a45  mov     [rdi+28h], rax
0x140002a49  xor     eax, eax
0x140002a4b  test    r15d, r15d
0x140002a4e  cmovnz  eax, [rsp+218h+var_A0]
0x140002a56  mov     [rdi+30h], eax
0x140002a59  mov     rax, [rsp+218h+var_138]
0x140002a61  mov     [rdi+10h], rax
0x140002a65  mov     rax, [rsp+218h+var_130]
0x140002a6d  mov     [rdi+48h], rax
0x140002a71  xor     eax, eax
0x140002a73  test    r15d, r15d
0x140002a76  cmovnz  eax, [rsp+218h+var_100]
0x140002a7e  mov     [rdi+50h], eax
0x140002a81  mov     rax, [rsp+218h+var_128]
0x140002a89  mov     [rdi+58h], rax
0x140002a8d  xor     eax, eax
0x140002a8f  test    r15d, r15d
0x140002a92  cmovnz  eax, [rsp+218h+var_F0]
0x140002a9a  mov     [rdi+60h], eax
0x140002a9d  mov     rax, [rsp+218h+var_120]
0x140002aa5  mov     [rdi+38h], rax
0x140002aa9  xor     eax, eax
0x140002aab  test    r15d, r15d
0x140002aae  cmovnz  eax, [rsp+218h+var_110]
0x140002ab6  mov     [rdi+40h], eax
0x140002ab9  mov     rcx, rdi
0x140002abc  call    cs:__imp_NsiEnumerateObjectsAllParametersEx
0x140002ac3  nop     dword ptr [rax+rax+00h]
0x140002ac8  mov     ebx, eax
0x140002aca  mov     eax, [rdi+68h]
0x140002acd  cmp     r12b, 1
0x140002ad1  jnz     short loc_140002AE9
0x140002ad3  lea     rcx, [r13+38h]
0x140002ad7  test    sil, sil
0x140002ada  jz      short loc_140002AE5
0x140002adc  mov     edx, eax
0x140002ade  call    RtlWriteULongToUser
0x140002ae3  jmp     short loc_140002AF4
0x140002ae5  mov     [rcx], eax
0x140002ae7  jmp     short loc_140002AF4
0x140002ae9  lea     rcx, [r14+68h]
0x140002aed  test    sil, sil
0x140002af0  jz      short loc_140002AE5
0x140002af2  jmp     short loc_140002ADC
0x140002af4  jmp     short loc_140002B05
0x140002af6  mov     ebx, eax
0x140002af8  mov     rdi, [rsp+218h+P]
0x140002b00  jmp     loc_140002D31
0x140002b05  test    ebx, ebx
0x140002b07  js      loc_140002D31
0x140002b0d  mov     rax, [rsp+218h+arg_18]
0x140002b15  mov     qword ptr [rax], 70h ; 'p'
0x140002b1c  mov     rdx, [rdi+28h]; Src
0x140002b20  test    rdx, rdx
0x140002b23  jz      short loc_140002B49
0x140002b25  mov     eax, [rdi+30h]
0x140002b28  test    eax, eax
0x140002b2a  jz      short loc_140002B49
0x140002b2c  imul    eax, r15d
0x140002b30  mov     r8d, eax; Size
0x140002b33  mov     rcx, [rsp+218h+var_A8]; void *
0x140002b3b  test    sil, sil
0x140002b3e  jz      loc_140002CFD
0x140002b44  call    RtlCopyToUser
0x140002b49  mov     rdx, [rdi+48h]; Src
0x140002b4d  test    rdx, rdx
0x140002b50  jnz     loc_140002C26
0x140002b56  mov     rcx, [rsp+218h+var_F8]; void *
0x140002b5e  test    rcx, rcx
0x140002b61  jnz     short loc_140002BD0
0x140002b63  mov     rcx, [rsp+218h+var_118]; void *
0x140002b6b  test    rcx, rcx
0x140002b6e  jnz     loc_140002BF9
0x140002b74  test    r15d, r15d
0x140002b77  jz      loc_140002D25
0x140002b7d  mov     eax, [rdi+50h]
0x140002b80  cmp     r12b, 1
0x140002b84  jz      loc_140002C53
0x140002b8a  cmp     eax, [rsp+218h+var_100]
0x140002b91  jnz     loc_140002CBF
0x140002b97  mov     eax, [rdi+60h]
0x140002b9a  cmp     eax, [rsp+218h+var_F0]
0x140002ba1  jnz     loc_140002CDB
0x140002ba7  mov     eax, [rdi+40h]
0x140002baa  cmp     eax, [rsp+218h+var_110]
0x140002bb1  jz      loc_140002D25
0x140002bb7  test    sil, sil
0x140002bba  jz      loc_140002CF7
0x140002bc0  mov     edx, eax
0x140002bc2  lea     rcx, [r14+40h]
0x140002bc6  call    RtlWriteULongToUser
0x140002bcb  jmp     loc_140002D25
0x140002bd0  cmp     [rsp+218h+var_F0], 0
0x140002bd8  jz      short loc_140002B63
0x140002bda  mov     r8d, r15d
0x140002bdd  imul    r8d, [rdi+60h]; Size
0x140002be2  mov     rdx, [rdi+58h]; Src
0x140002be6  test    sil, sil
0x140002be9  jz      loc_140002D11
0x140002bef  call    RtlCopyToUser
0x140002bf4  jmp     loc_140002B63
0x140002bf9  cmp     [rsp+218h+var_110], 0
0x140002c01  jz      loc_140002B74
0x140002c07  mov     r8d, r15d
0x140002c0a  imul    r8d, [rdi+40h]; Size
0x140002c0f  mov     rdx, [rdi+38h]; Src
0x140002c13  test    sil, sil
0x140002c16  jz      loc_140002D1B
0x140002c1c  call    RtlCopyToUser
0x140002c21  jmp     loc_140002B74
0x140002c26  mov     eax, [rdi+50h]
0x140002c29  test    eax, eax
0x140002c2b  jz      loc_140002B56
0x140002c31  imul    eax, r15d
0x140002c35  mov     r8d, eax; Size
0x140002c38  mov     rcx, [rsp+218h+var_108]; void *
0x140002c40  test    sil, sil
0x140002c43  jz      loc_140002D07
0x140002c49  call    RtlCopyToUser
0x140002c4e  jmp     loc_140002B56
0x140002c53  cmp     eax, [rsp+218h+var_100]
0x140002c5a  jnz     short loc_140002C8D
0x140002c5c  mov     eax, [rdi+60h]
0x140002c5f  cmp     eax, [rsp+218h+var_F0]
0x140002c66  jnz     short loc_140002CA3
0x140002c68  mov     eax, [rdi+40h]
0x140002c6b  cmp     eax, [rsp+218h+var_110]
0x140002c72  jz      loc_140002D25
0x140002c78  test    sil, sil
0x140002c7b  jz      short loc_140002CB9
0x140002c7d  mov     edx, eax
0x140002c7f  lea     rcx, [r13+24h]
0x140002c83  call    RtlWriteULongToUser
0x140002c88  jmp     loc_140002D25
0x140002c8d  lea     rcx, [r13+2Ch]
0x140002c91  test    sil, sil
0x140002c94  jz      short loc_140002C9F
0x140002c96  mov     edx, eax
0x140002c98  call    RtlWriteULongToUser
0x140002c9d  jmp     short loc_140002C5C
0x140002c9f  mov     [rcx], eax
0x140002ca1  jmp     short loc_140002C5C
0x140002ca3  lea     rcx, [r13+34h]
0x140002ca7  test    sil, sil
0x140002caa  jz      short loc_140002CB5
0x140002cac  mov     edx, eax
0x140002cae  call    RtlWriteULongToUser
0x140002cb3  jmp     short loc_140002C68
0x140002cb5  mov     [rcx], eax
0x140002cb7  jmp     short loc_140002C68
0x140002cb9  mov     [r13+24h], eax
0x140002cbd  jmp     short loc_140002D25
0x140002cbf  lea     rcx, [r14+50h]
0x140002cc3  test    sil, sil
0x140002cc6  jz      short loc_140002CD4
0x140002cc8  mov     edx, eax
0x140002cca  call    RtlWriteULongToUser
0x140002ccf  jmp     loc_140002B97
0x140002cd4  mov     [rcx], eax
0x140002cd6  jmp     loc_140002B97
0x140002cdb  lea     rcx, [r14+60h]
0x140002cdf  test    sil, sil
0x140002ce2  jz      short loc_140002CF0
0x140002ce4  mov     edx, eax
0x140002ce6  call    RtlWriteULongToUser
0x140002ceb  jmp     loc_140002BA7
0x140002cf0  mov     [rcx], eax
0x140002cf2  jmp     loc_140002BA7
0x140002cf7  mov     [r14+40h], eax
0x140002cfb  jmp     short loc_140002D25
0x140002cfd  call    RtlCopyVolatileMemory
0x140002d02  jmp     loc_140002B49
0x140002d07  call    RtlCopyVolatileMemory
0x140002d0c  jmp     loc_140002B56
0x140002d11  call    RtlCopyVolatileMemory
0x140002d16  jmp     loc_140002B63
0x140002d1b  call    RtlCopyVolatileMemory
0x140002d20  jmp     loc_140002B74
0x140002d25  jmp     short loc_140002D31
0x140002d27  mov     ebx, eax
0x140002d29  mov     rdi, [rsp+218h+P]
0x140002d31  test    rdi, rdi
0x140002d34  jz      short loc_140002D47
0x140002d36  xor     edx, edx; Tag
0x140002d38  mov     rcx, rdi; P
0x140002d3b  call    cs:__imp_ExFreePoolWithTag
0x140002d42  nop     dword ptr [rax+rax+00h]
0x140002d47  mov     eax, ebx
0x140002d49  lea     r11, [rsp+218h+var_28]
0x140002d51  mov     rbx, [r11+30h]
0x140002d55  mov     rsi, [r11+38h]
0x140002d59  mov     rsp, r11
0x140002d5c  pop     r15
0x140002d5e  pop     r14
0x140002d60  pop     r13
0x140002d62  pop     r12
0x140002d64  pop     rdi
0x140002d65  retn
0x140002d67  cmp     ebx, 3Ch ; '<'
0x140002d6a  jb      loc_140002E9F
0x140002d70  xorps   xmm0, xmm0
0x140002d73  movups  [rsp+218h+var_E8], xmm0
0x140002d7b  movups  [rsp+218h+var_D8], xmm0
0x140002d83  movups  [rsp+218h+var_C8], xmm0
0x140002d8b  movups  [rsp+218h+var_C8+0Ch], xmm0
0x140002d93  mov     r12b, 1
0x140002d96  mov     r13, r14
  ... truncated ...
```
