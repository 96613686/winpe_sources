# NsippGetAllParameters

- ea: `0x140002280`
- end: `0x14000283d`
- name: `NsippGetAllParameters`
- size: `1469`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140002280`
- `0x1400043d0`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`
- `0x14000d08c`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140002305`
- `ntoskrnl!IoIs32bitProcess` at `0x140002305`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002463`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002463`
- `NETIO!NsiGetAllParametersEx` at `0x1400024ec`
- `NETIO!NsiGetAllParametersEx` at `0x1400024ec`

## pseudocode

```c
__int64 __fastcall NsippGetAllParameters(int *Src, unsigned int a2, unsigned __int8 a3, _QWORD *a4)
{
  BOOLEAN v8; // al
  char v9; // r15
  char *v10; // r13
  int AllParameters; // ebx
  _DWORD *v12; // rdi
  void *v14; // rdx
  unsigned int v15; // eax
  void *v16; // rdx
  void *v17; // rdx
  void *v18; // rdx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  int v26; // eax
  int *v27; // rcx
  int *v28; // rcx
  int *v29; // rcx
  int *v30; // rcx
  PVOID P; // [rsp+D0h] [rbp-158h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-150h] BYREF
  char *v33; // [rsp+E0h] [rbp-148h] BYREF
  __int64 v34; // [rsp+E8h] [rbp-140h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-138h] BYREF
  __int64 v36; // [rsp+F8h] [rbp-130h] BYREF
  __int128 v37; // [rsp+100h] [rbp-128h] BYREF
  __int128 v38; // [rsp+110h] [rbp-118h]
  __int128 v39; // [rsp+120h] [rbp-108h]
  __int64 v40; // [rsp+130h] [rbp-F8h]
  __m128i v41; // [rsp+138h] [rbp-F0h] BYREF
  __int128 v42; // [rsp+148h] [rbp-E0h]
  __int128 v43; // [rsp+158h] [rbp-D0h]
  __m128i v44; // [rsp+168h] [rbp-C0h] BYREF
  _QWORD v45[21]; // [rsp+180h] [rbp-A8h] BYREF

  v44 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  P = 0;
  memset(v45, 0, 0x68u);
  v8 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v8 )
  {
    if ( a2 >= 0x38 )
    {
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v9 = 1;
      v10 = (char *)Src;
      if ( a3 )
        RtlCopyFromUser(&v37, Src, 0x38u);
      else
        RtlCopyVolatileMemory(&v37, Src, 0x38u);
      v45[5] = DWORD2(v38);
      LODWORD(v45[6]) = HIDWORD(v38);
      v45[2] = DWORD2(v37);
      LODWORD(v45[1]) = DWORD1(v37);
      LODWORD(v45[3]) = HIDWORD(v37);
      v45[9] = DWORD2(v39);
      LODWORD(v45[10]) = HIDWORD(v39);
      v45[11] = (unsigned int)v40;
      LODWORD(v45[12]) = HIDWORD(v40);
      v45[7] = (unsigned int)v39;
      LODWORD(v45[8]) = DWORD1(v39);
      v45[4] = v38;
      v45[0] = (int)v37;
      goto LABEL_7;
    }
    return 3221225485LL;
  }
  v9 = 0;
  v10 = 0;
  if ( a2 < 0x68 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(v45, Src, 0x68u);
  else
    RtlCopyVolatileMemory(v45, Src, 0x68u);
LABEL_7:
  AllParameters = NsippProbeAndAllocateParameters(
                    v45,
                    0x68u,
                    (__int64)&v45[1],
                    (__m128i *)&v45[5],
                    0,
                    (__m128i *)&v45[7],
                    0,
                    0,
                    a3,
                    1u,
                    1,
                    &v44,
                    &v32,
                    0,
                    0,
                    0,
                    &v41,
                    &v36,
                    0,
                    0,
                    0,
                    &v34,
                    &v35,
                    &v33,
                    &P);
  v12 = P;
  if ( AllParameters >= 0 )
  {
    *((_QWORD *)P + 5) = v32;
    v12[12] = v44.m128i_i32[2];
    *((_QWORD *)v12 + 2) = v33;
    *((_QWORD *)v12 + 9) = v34;
    v12[20] = DWORD2(v42);
    *((_QWORD *)v12 + 11) = v35;
    v12[24] = DWORD2(v43);
    *((_QWORD *)v12 + 7) = v36;
    v12[16] = v41.m128i_i32[2];
    AllParameters = NsiGetAllParametersEx(v12);
    if ( AllParameters >= 0 )
    {
      *a4 = 104;
      v14 = (void *)*((_QWORD *)v12 + 5);
      if ( v14 )
      {
        v15 = v12[12];
        if ( v15 )
        {
          if ( a3 )
            RtlCopyToUser((void *)v44.m128i_i64[0], v14, v15);
          else
            RtlCopyVolatileMemory((void *)v44.m128i_i64[0], v14, v15);
        }
      }
      v16 = (void *)*((_QWORD *)v12 + 9);
      if ( v16 )
      {
        v23 = v12[20];
        if ( v23 )
        {
          if ( a3 )
            RtlCopyToUser((void *)v42, v16, v23);
          else
            RtlCopyVolatileMemory((void *)v42, v16, v23);
        }
      }
      v17 = (void *)*((_QWORD *)v12 + 11);
      if ( v17 )
      {
        v22 = v12[24];
        if ( v22 )
        {
          if ( a3 )
            RtlCopyToUser((void *)v43, v17, v22);
          else
            RtlCopyVolatileMemory((void *)v43, v17, v22);
        }
      }
      v18 = (void *)*((_QWORD *)v12 + 7);
      if ( v18 )
      {
        v24 = v12[16];
        if ( v24 )
        {
          if ( a3 )
            RtlCopyToUser((void *)v41.m128i_i64[0], v18, v24);
          else
            RtlCopyVolatileMemory((void *)v41.m128i_i64[0], v18, v24);
        }
      }
      v19 = v12[20];
      if ( v9 == 1 )
      {
        if ( v19 != DWORD2(v42) )
        {
          v27 = (int *)(v10 + 44);
          if ( a3 )
            RtlWriteULongToUser(v27, v19);
          else
            *v27 = v19;
        }
        v25 = v12[24];
        if ( v25 != DWORD2(v43) )
        {
          v28 = (int *)(v10 + 52);
          if ( a3 )
            RtlWriteULongToUser(v28, v25);
          else
            *v28 = v25;
        }
        v26 = v12[16];
        if ( v26 != v41.m128i_i32[2] )
        {
          if ( a3 )
            RtlWriteULongToUser((_DWORD *)v10 + 9, v26);
          else
            *((_DWORD *)v10 + 9) = v26;
        }
      }
      else
      {
        if ( v19 != DWORD2(v42) )
        {
          v29 = Src + 20;
          if ( a3 )
            RtlWriteULongToUser(v29, v19);
          else
            *v29 = v19;
        }
        v20 = v12[24];
        if ( v20 != DWORD2(v43) )
        {
          v30 = Src + 24;
          if ( a3 )
            RtlWriteULongToUser(v30, v20);
          else
            *v30 = v20;
        }
        v21 = v12[16];
        if ( v21 != v41.m128i_i32[2] )
        {
          if ( a3 )
            RtlWriteULongToUser(Src + 16, v21);
          else
            Src[16] = v21;
        }
      }
    }
  }
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)AllParameters;
}

```

## disassembly

```asm
0x140002280  mov     rax, rsp
0x140002283  push    rbx
0x140002284  push    rsi
0x140002285  push    rdi
0x140002286  push    r12
0x140002288  push    r13
0x14000228a  push    r14
0x14000228c  push    r15
0x14000228e  sub     rsp, 1F0h
0x140002295  mov     r12, r9
0x140002298  movzx   esi, r8b
0x14000229c  mov     ebx, edx
0x14000229e  mov     r14, rcx
0x1400022a1  xorps   xmm0, xmm0
0x1400022a4  movups  xmmword ptr [rax-0C0h], xmm0
0x1400022ab  xorps   xmm1, xmm1
0x1400022ae  movups  xmmword ptr [rax-0F0h], xmm1
0x1400022b5  movups  xmmword ptr [rax-0E0h], xmm1
0x1400022bc  movups  xmmword ptr [rax-0D0h], xmm1
0x1400022c3  xor     edi, edi
0x1400022c5  mov     [rax-150h], rdi
0x1400022cc  mov     [rax-140h], rdi
0x1400022d3  mov     [rax-138h], rdi
0x1400022da  mov     [rax-130h], rdi
0x1400022e1  mov     [rax-148h], rdi
0x1400022e8  mov     [rax-158h], rdi
0x1400022ef  xor     edx, edx; Val
0x1400022f1  mov     r8d, 68h ; 'h'; Size
0x1400022f7  lea     rcx, [rax-0A8h]; void *
0x1400022fe  call    memset
0x140002303  xor     ecx, ecx; Irp
0x140002305  call    cs:__imp_IoIs32bitProcess
0x14000230c  nop     dword ptr [rax+rax+00h]
0x140002311  test    r14, r14
0x140002314  jz      loc_140002833
0x14000231a  test    al, al
0x14000231c  jnz     loc_140002706
0x140002322  xor     r15b, r15b
0x140002325  mov     r13d, edi
0x140002328  cmp     ebx, 68h ; 'h'
0x14000232b  jb      loc_140002833
0x140002331  mov     r8d, 68h ; 'h'; Size
0x140002337  mov     rdx, r14; Src
0x14000233a  lea     rcx, [rsp+228h+var_A8]; void *
0x140002342  test    sil, sil
0x140002345  jz      short loc_14000234E
0x140002347  call    RtlCopyFromUser
0x14000234c  jmp     short loc_140002353
0x14000234e  call    RtlCopyVolatileMemory
0x140002353  jmp     short loc_14000235A
0x140002355  jmp     loc_140002471
0x14000235a  lea     rax, [rsp+228h+P]
0x140002362  mov     [rsp+228h+var_168], rax
0x14000236a  lea     rax, [rsp+228h+var_148]
0x140002372  mov     [rsp+228h+var_170], rax
0x14000237a  lea     rax, [rsp+228h+var_138]
0x140002382  mov     [rsp+228h+var_178], rax
0x14000238a  lea     rax, [rsp+228h+var_140]
0x140002392  mov     [rsp+228h+var_180], rax
0x14000239a  mov     [rsp+228h+var_188], rdi
0x1400023a2  mov     [rsp+228h+var_190], rdi
0x1400023aa  mov     [rsp+228h+var_198], rdi
0x1400023b2  lea     rax, [rsp+228h+var_130]
0x1400023ba  mov     [rsp+228h+var_1A0], rax
0x1400023c2  lea     rax, [rsp+228h+var_F0]
0x1400023ca  mov     [rsp+228h+var_1A8], rax
0x1400023d2  mov     [rsp+228h+var_1B0], rdi
0x1400023d7  mov     [rsp+228h+var_1B8], rdi
0x1400023dc  mov     [rsp+228h+var_1C0], rdi
0x1400023e1  lea     rax, [rsp+228h+var_150]
0x1400023e9  mov     [rsp+228h+var_1C8], rax
0x1400023ee  lea     rax, [rsp+228h+var_C0]
0x1400023f6  mov     [rsp+228h+var_1D0], rax
0x1400023fb  mov     [rsp+228h+var_1D8], 1
0x140002400  mov     [rsp+228h+var_1E0], 1
0x140002408  mov     [rsp+228h+var_1E8], sil
0x14000240d  mov     [rsp+228h+var_1F0], rdi
0x140002412  mov     [rsp+228h+var_1F8], rdi
0x140002417  lea     rax, [rsp+228h+var_70]
0x14000241f  mov     [rsp+228h+var_200], rax
0x140002424  mov     [rsp+228h+var_208], rdi
0x140002429  lea     r9, [rsp+228h+var_80]
0x140002431  lea     r8, [rsp+228h+var_A0]
0x140002439  mov     edx, 68h ; 'h'
0x14000243e  lea     rcx, [rsp+228h+var_A8]
0x140002446  call    NsippProbeAndAllocateParameters
0x14000244b  mov     ebx, eax
0x14000244d  mov     rdi, [rsp+228h+P]
0x140002455  test    eax, eax
0x140002457  jns     short loc_140002485
0x140002459  test    rdi, rdi
0x14000245c  jz      short loc_14000246F
0x14000245e  xor     edx, edx; Tag
0x140002460  mov     rcx, rdi; P
0x140002463  call    cs:__imp_ExFreePoolWithTag
0x14000246a  nop     dword ptr [rax+rax+00h]
0x14000246f  mov     eax, ebx
0x140002471  add     rsp, 1F0h
0x140002478  pop     r15
0x14000247a  pop     r14
0x14000247c  pop     r13
0x14000247e  pop     r12
0x140002480  pop     rdi
0x140002481  pop     rsi
0x140002482  pop     rbx
0x140002483  retn
0x140002485  mov     rax, [rsp+228h+var_150]
0x14000248d  mov     [rdi+28h], rax
0x140002491  mov     eax, [rsp+228h+var_B8]
0x140002498  mov     [rdi+30h], eax
0x14000249b  mov     rax, [rsp+228h+var_148]
0x1400024a3  mov     [rdi+10h], rax
0x1400024a7  mov     rax, [rsp+228h+var_140]
0x1400024af  mov     [rdi+48h], rax
0x1400024b3  mov     eax, [rsp+228h+var_D8]
0x1400024ba  mov     [rdi+50h], eax
0x1400024bd  mov     rax, [rsp+228h+var_138]
0x1400024c5  mov     [rdi+58h], rax
0x1400024c9  mov     eax, [rsp+228h+var_C8]
0x1400024d0  mov     [rdi+60h], eax
0x1400024d3  mov     rax, [rsp+228h+var_130]
0x1400024db  mov     [rdi+38h], rax
0x1400024df  mov     eax, [rsp+228h+var_E8]
0x1400024e6  mov     [rdi+40h], eax
0x1400024e9  mov     rcx, rdi
0x1400024ec  call    cs:__imp_NsiGetAllParametersEx
0x1400024f3  nop     dword ptr [rax+rax+00h]
0x1400024f8  mov     ebx, eax
0x1400024fa  test    eax, eax
0x1400024fc  js      loc_140002459
0x140002502  mov     qword ptr [r12], 68h ; 'h'
0x14000250a  mov     rdx, [rdi+28h]; Src
0x14000250e  test    rdx, rdx
0x140002511  jz      short loc_140002533
0x140002513  mov     eax, [rdi+30h]
0x140002516  test    eax, eax
0x140002518  jz      short loc_140002533
0x14000251a  mov     rcx, [rsp+228h+var_C0]; void *
0x140002522  mov     r8d, eax; Size
0x140002525  test    sil, sil
0x140002528  jz      loc_1400026CA
0x14000252e  call    RtlCopyToUser
0x140002533  mov     rdx, [rdi+48h]; Src
0x140002537  test    rdx, rdx
0x14000253a  jnz     loc_1400025CE
0x140002540  mov     rdx, [rdi+58h]; Src
0x140002544  test    rdx, rdx
0x140002547  jnz     short loc_1400025A9
0x140002549  mov     rdx, [rdi+38h]; Src
0x14000254d  test    rdx, rdx
0x140002550  jnz     loc_1400025F7
0x140002556  mov     eax, [rdi+50h]
0x140002559  cmp     r15b, 1
0x14000255d  jz      loc_140002620
0x140002563  cmp     eax, [rsp+228h+var_D8]
0x14000256a  jnz     loc_14000268C
0x140002570  mov     eax, [rdi+60h]
0x140002573  cmp     eax, [rsp+228h+var_C8]
0x14000257a  jnz     loc_1400026A8
0x140002580  mov     eax, [rdi+40h]
0x140002583  cmp     eax, [rsp+228h+var_E8]
0x14000258a  jz      loc_1400026F2
0x140002590  test    sil, sil
0x140002593  jz      loc_1400026C4
0x140002599  mov     edx, eax
0x14000259b  lea     rcx, [r14+40h]
0x14000259f  call    RtlWriteULongToUser
0x1400025a4  jmp     loc_1400026F2
0x1400025a9  mov     eax, [rdi+60h]
0x1400025ac  test    eax, eax
0x1400025ae  jz      short loc_140002549
0x1400025b0  mov     rcx, [rsp+228h+var_D0]; void *
0x1400025b8  mov     r8d, eax; Size
0x1400025bb  test    sil, sil
0x1400025be  jz      loc_1400026DE
0x1400025c4  call    RtlCopyToUser
0x1400025c9  jmp     loc_140002549
0x1400025ce  mov     eax, [rdi+50h]
0x1400025d1  test    eax, eax
0x1400025d3  jz      loc_140002540
0x1400025d9  mov     rcx, [rsp+228h+var_E0]; void *
0x1400025e1  mov     r8d, eax; Size
0x1400025e4  test    sil, sil
0x1400025e7  jz      loc_1400026D4
0x1400025ed  call    RtlCopyToUser
0x1400025f2  jmp     loc_140002540
0x1400025f7  mov     eax, [rdi+40h]
0x1400025fa  test    eax, eax
0x1400025fc  jz      loc_140002556
0x140002602  mov     rcx, [rsp+228h+var_F0]; void *
0x14000260a  mov     r8d, eax; Size
0x14000260d  test    sil, sil
0x140002610  jz      loc_1400026E8
0x140002616  call    RtlCopyToUser
0x14000261b  jmp     loc_140002556
0x140002620  cmp     eax, [rsp+228h+var_D8]
0x140002627  jnz     short loc_14000265A
0x140002629  mov     eax, [rdi+60h]
0x14000262c  cmp     eax, [rsp+228h+var_C8]
0x140002633  jnz     short loc_140002670
0x140002635  mov     eax, [rdi+40h]
0x140002638  cmp     eax, [rsp+228h+var_E8]
0x14000263f  jz      loc_1400026F2
0x140002645  test    sil, sil
0x140002648  jz      short loc_140002686
0x14000264a  mov     edx, eax
0x14000264c  lea     rcx, [r13+24h]
0x140002650  call    RtlWriteULongToUser
0x140002655  jmp     loc_1400026F2
0x14000265a  lea     rcx, [r13+2Ch]
0x14000265e  test    sil, sil
0x140002661  jz      short loc_14000266C
0x140002663  mov     edx, eax
0x140002665  call    RtlWriteULongToUser
0x14000266a  jmp     short loc_140002629
0x14000266c  mov     [rcx], eax
0x14000266e  jmp     short loc_140002629
0x140002670  lea     rcx, [r13+34h]
0x140002674  test    sil, sil
0x140002677  jz      short loc_140002682
0x140002679  mov     edx, eax
0x14000267b  call    RtlWriteULongToUser
0x140002680  jmp     short loc_140002635
0x140002682  mov     [rcx], eax
0x140002684  jmp     short loc_140002635
0x140002686  mov     [r13+24h], eax
0x14000268a  jmp     short loc_1400026F2
0x14000268c  lea     rcx, [r14+50h]
0x140002690  test    sil, sil
0x140002693  jz      short loc_1400026A1
0x140002695  mov     edx, eax
0x140002697  call    RtlWriteULongToUser
0x14000269c  jmp     loc_140002570
0x1400026a1  mov     [rcx], eax
0x1400026a3  jmp     loc_140002570
0x1400026a8  lea     rcx, [r14+60h]
0x1400026ac  test    sil, sil
0x1400026af  jz      short loc_1400026BD
0x1400026b1  mov     edx, eax
0x1400026b3  call    RtlWriteULongToUser
0x1400026b8  jmp     loc_140002580
0x1400026bd  mov     [rcx], eax
0x1400026bf  jmp     loc_140002580
0x1400026c4  mov     [r14+40h], eax
0x1400026c8  jmp     short loc_1400026F2
0x1400026ca  call    RtlCopyVolatileMemory
0x1400026cf  jmp     loc_140002533
0x1400026d4  call    RtlCopyVolatileMemory
0x1400026d9  jmp     loc_140002540
0x1400026de  call    RtlCopyVolatileMemory
0x1400026e3  jmp     loc_140002549
0x1400026e8  call    RtlCopyVolatileMemory
0x1400026ed  jmp     loc_140002556
0x1400026f2  jmp     loc_140002459
0x1400026f7  mov     ebx, eax
0x1400026f9  mov     rdi, [rsp+228h+P]
0x140002701  jmp     loc_140002459
0x140002706  cmp     ebx, 38h ; '8'
0x140002709  jb      loc_140002833
0x14000270f  xorps   xmm0, xmm0
0x140002712  xor     eax, eax
0x140002714  movups  [rsp+228h+var_128], xmm0
0x14000271c  movups  [rsp+228h+var_118], xmm0
0x140002724  movups  [rsp+228h+var_108], xmm0
0x14000272c  mov     [rsp+228h+var_F8], rax
0x140002734  mov     r15b, 1
0x140002737  mov     r13, r14
0x14000273a  mov     r8d, 38h ; '8'; Size
0x140002740  mov     rdx, r14; Src
0x140002743  lea     rcx, [rsp+228h+var_128]; void *
0x14000274b  test    sil, sil
0x14000274e  jz      short loc_140002757
0x140002750  call    RtlCopyFromUser
0x140002755  jmp     short loc_14000275C
0x140002757  call    RtlCopyVolatileMemory
0x14000275c  jmp     short loc_140002763
0x14000275e  jmp     loc_140002471
0x140002763  mov     eax, dword ptr [rsp+228h+var_118+4]
0x14000276a  mov     dword ptr [rsp+228h+var_88+4], eax
0x140002771  mov     eax, dword ptr [rsp+228h+var_118+8]
0x140002778  mov     [rsp+228h+var_80], rax
0x140002780  mov     eax, dword ptr [rsp+228h+var_118+0Ch]
0x140002787  mov     [rsp+228h+var_78], eax
0x14000278e  mov     eax, dword ptr [rsp+228h+var_128+8]
0x140002795  mov     [rsp+228h+var_98], rax
0x14000279d  mov     eax, dword ptr [rsp+228h+var_128+4]
0x1400027a4  mov     [rsp+228h+var_A0], eax
0x1400027ab  mov     eax, dword ptr [rsp+228h+var_128+0Ch]
0x1400027b2  mov     [rsp+228h+var_90], eax
0x1400027b9  mov     eax, dword ptr [rsp+228h+var_108+8]
0x1400027c0  mov     [rsp+228h+var_60], rax
0x1400027c8  mov     eax, dword ptr [rsp+228h+var_108+0Ch]
0x1400027cf  mov     [rsp+228h+var_58], eax
0x1400027d6  mov     eax, dword ptr [rsp+228h+var_F8]
0x1400027dd  mov     [rsp+228h+var_50], rax
0x1400027e5  mov     eax, dword ptr [rsp+228h+var_F8+4]
0x1400027ec  mov     [rsp+228h+var_48], eax
0x1400027f3  mov     eax, dword ptr [rsp+228h+var_108]
0x1400027fa  mov     [rsp+228h+var_70], rax
0x140002802  mov     eax, dword ptr [rsp+228h+var_108+4]
  ... truncated ...
```
