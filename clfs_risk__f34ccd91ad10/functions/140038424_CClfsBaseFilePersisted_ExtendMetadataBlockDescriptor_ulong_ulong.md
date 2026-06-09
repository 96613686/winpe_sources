# CClfsBaseFilePersisted::ExtendMetadataBlockDescriptor(ulong,ulong)

- ea: `0x140038424`
- end: `0x1400388eb`
- name: `?ExtendMetadataBlockDescriptor@CClfsBaseFilePersisted@@AEAAJKK@Z`
- size: `1223`
- prototype: `__int64 __fastcall(CClfsBaseFilePersisted *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140037f48`
- `0x1400392a8`

## callees

- `0x14000c664`
- `0x14000d084`
- `0x140011d90`
- `0x140017f80`
- `0x140018280`
- `0x1400348f4`
- `0x140038424`
- `0x140062c20`
- `0x14007491c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003858c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003887b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400388b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d47d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d4a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d4fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003858c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003887b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400388b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d47d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d4a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d4fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038660`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038713`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038660`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038713`

## string_xrefs

- `0x1400384ec`: `CClfsBaseFilePersisted::ExtendMetadataBlockDescriptor`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::ExtendMetadataBlockDescriptor(
        CClfsBaseFilePersisted *this,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v3; // rbx
  CClfsBaseFilePersisted *v5; // rcx
  __int64 v6; // r12
  __int64 v7; // r9
  unsigned int v8; // edx
  int v9; // eax
  unsigned int v10; // r15d
  unsigned int *PoolWithTag; // r14
  unsigned int *v13; // r13
  int v14; // edi
  __int128 v15; // xmm6
  __int64 v16; // xmm7_8
  CClfsBaseFilePersisted *v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // r10d
  __int64 v20; // r10
  void *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r12
  __int64 v24; // rax
  int v25; // ebx
  __int64 v26; // r9
  size_t v27; // rbx
  PVOID v28; // rax
  unsigned int v29; // edx
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rax
  void *v33; // [rsp+38h] [rbp-A0h]
  char *Src; // [rsp+50h] [rbp-88h]
  unsigned int v36; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v37; // [rsp+F8h] [rbp+20h]

  v3 = a2;
  v36 = 0;
  if ( (int)RtlULongLongToULong((unsigned __int64)a3 << 9, &v36) < 0 )
    return 3222929421LL;
  v37 = v3;
  v6 = 3 * v3;
  v7 = *((_QWORD *)this + 6);
  v8 = v36 + *(_DWORD *)(v7 + 24 * v3 + 8);
  if ( v8 < v36 )
    return 3222929421LL;
  v9 = *((_DWORD *)this + 36);
  if ( v9 )
    v10 = -v9 & (v8 + v9 - 1);
  else
    v10 = 0;
  if ( v10 < v8 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        37,
        (unsigned int)WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids,
        (unsigned int)"CClfsBaseFilePersisted::ExtendMetadataBlockDescriptor",
        235);
    }
    return 3221225621LL;
  }
  PoolWithTag = 0;
  v13 = 0;
  v33 = 0;
  v14 = 0;
  v36 = v10 >> 9;
  v15 = *(_OWORD *)(v7 + 24 * v3);
  v16 = *(_QWORD *)(v7 + 24 * v3 + 16);
  if ( !CClfsBaseFilePersisted::IsShadowBlock(v5, v3, v3 + 1) && CClfsBaseFilePersisted::IsShadowBlock(v17, v19, v3) )
  {
    v21 = *(void **)(v18 + 24 * v3);
    if ( v21 && v21 != *(void **)(v18 + 24 * v20) )
    {
      ExFreePoolWithTag(v21, 0);
      *(_QWORD *)(*((_QWORD *)this + 6) + 24 * v3) = 0;
      v20 = (unsigned int)(v3 + 1);
    }
    *(_DWORD *)(*((_QWORD *)this + 6) + 24 * v3 + 8) = *(_DWORD *)(*((_QWORD *)this + 6) + 24 * v20 + 8);
    v22 = *((_QWORD *)this + 6);
    *(_QWORD *)(v22 + 24 * v3) = *(_QWORD *)(v22 + 24 * v20);
    if ( (_DWORD)v3 == 2 )
    {
      PoolWithTag = *(unsigned int **)(*((_QWORD *)this + 6) + 48LL);
      v22 = PoolWithTag[10];
      *((_QWORD *)this + 8) = (char *)PoolWithTag + v22 + 24;
      *((_DWORD *)this + 18) = 11;
      *((_QWORD *)this + 10) = this;
      *((_QWORD *)this + 11) = (char *)PoolWithTag + v22 + 112;
      *((_DWORD *)this + 24) = 11;
      *((_QWORD *)this + 13) = this;
      *((_QWORD *)this + 14) = (char *)PoolWithTag + v22 + 200;
      *((_DWORD *)this + 30) = 11;
      *((_QWORD *)this + 16) = this;
    }
    v14 = 0;
    goto LABEL_19;
  }
  v13 = *(unsigned int **)(v18 + 24 * v3);
  if ( (_DWORD)v3 == 3 && !CClfsBaseFile::GetBaseLogRecord(this) )
  {
    v14 = -1072037875;
LABEL_19:
    v23 = v3;
LABEL_40:
    v28 = v33;
    goto LABEL_41;
  }
  Src = (char *)v13 + v13[10];
  PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PagedPoolCacheAligned, v10, 0x73666C43u);
  if ( !PoolWithTag )
  {
    v14 = -1073741670;
    goto LABEL_19;
  }
  if ( (CClfsAuthContainer::GetAlignmentRequirement(*((CClfsAuthContainer **)this + 19)) & (unsigned int)PoolWithTag) != 0 )
  {
    v14 = -1073741280;
    goto LABEL_19;
  }
  v24 = *((_QWORD *)this + 6);
  v25 = *(_DWORD *)(v24 + 24 * v3 + 8);
  memmove(PoolWithTag, v13, *(unsigned int *)(v24 + 8 * v6 + 8));
  memset((char *)PoolWithTag + *(unsigned int *)(*((_QWORD *)this + 6) + 8 * v6 + 8), 0, v10 - v25);
  *((_WORD *)PoolWithTag + 2) = v36;
  PoolWithTag[10] = 112;
  v26 = v13[10];
  v27 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 6) + 8 * v6 + 8) - v26);
  if ( (char *)PoolWithTag + v27 + 112 <= (char *)PoolWithTag + v26 )
  {
    memmove(PoolWithTag + 28, Src, v27);
    memset((char *)PoolWithTag + v13[10], 0, v27);
    goto LABEL_32;
  }
  v28 = ExAllocatePoolWithTag(PagedPoolCacheAligned, (unsigned int)v27, 0x73666C43u);
  v33 = v28;
  if ( v28 )
  {
    memmove(v28, Src, v27);
    memset((char *)PoolWithTag + v13[10], 0, v27);
    memmove(PoolWithTag + 28, v33, v27);
LABEL_32:
    v29 = v10 / 0x1FE;
    v22 = v10 / 0x1FE;
    if ( v10 != 510 * (v10 / 0x1FE) )
      v22 = v10 / 0x1FE + 1;
    if ( ((2 * (_DWORD)v22 + 7) & 0xFFFFFFF8) < v10 )
    {
      if ( v10 % 0x1FE )
        v29 = v10 / 0x1FE + 1;
      ClfsStampLogBlock(
        (struct _CLFS_LOG_BLOCK_HEADER *)PoolWithTag,
        v10 - ((2 * v29 + 7) & 0xFFFFFFF8),
        *((_DWORD *)this + 36),
        0);
      v23 = v37;
      v30 = 3 * v37;
      *(_DWORD *)(*((_QWORD *)this + 6) + 8 * v30 + 8) = v10;
      v22 = v30;
      *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v30) = PoolWithTag;
    }
    else
    {
      v14 = -1072037878;
      v23 = v37;
    }
    LODWORD(v3) = a2;
    goto LABEL_40;
  }
  v14 = -1073741670;
  LODWORD(v3) = a2;
  v23 = v37;
LABEL_41:
  if ( v28 )
    ExFreePoolWithTag(v28, 0);
  if ( v14 >= 0 )
  {
    if ( v13 && !CClfsBaseFilePersisted::IsShadowBlock((CClfsBaseFilePersisted *)v22, v3, v3 - 1) )
      ExFreePoolWithTag(v13, 0);
  }
  else
  {
    if ( PoolWithTag )
      ExFreePoolWithTag(PoolWithTag, 0);
    v31 = 3 * v23;
    v32 = *((_QWORD *)this + 6);
    *(_OWORD *)(v32 + 8 * v31) = v15;
    *(_QWORD *)(v32 + 8 * v31 + 16) = v16;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140038424  mov     [rsp+arg_8], edx
0x140038428  mov     r11, rsp
0x14003842b  mov     [r11+8], rcx
0x14003842f  push    rbx
0x140038430  push    rsi
0x140038431  push    rdi
0x140038432  push    r12
0x140038434  push    r13
0x140038436  push    r14
0x140038438  push    r15
0x14003843a  sub     rsp, 0A0h
0x140038441  movaps  xmmword ptr [r11-48h], xmm6
0x140038446  movaps  xmmword ptr [r11-58h], xmm7
0x14003844b  mov     ebx, edx
0x14003844d  mov     rsi, rcx
0x140038450  xorps   xmm0, xmm0
0x140038453  xor     eax, eax
0x140038455  movups  [rsp+0D8h+var_78], xmm0
0x14003845a  mov     [r11-68h], rax
0x14003845e  mov     [r11+18h], eax
0x140038462  mov     ecx, r8d
0x140038465  shl     rcx, 9; unsigned __int64
0x140038469  lea     rdx, [r11+18h]; unsigned int *
0x14003846d  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x140038472  test    eax, eax
0x140038474  js      loc_1400388C4
0x14003847a  mov     [rsp+0D8h+arg_18], rbx
0x140038482  lea     r12, [rbx+rbx*2]
0x140038486  mov     r9, [rsi+30h]
0x14003848a  mov     edx, [r9+r12*8+8]
0x14003848f  add     edx, [rsp+0D8h+arg_10]
0x140038496  cmp     edx, [rsp+0D8h+arg_10]
0x14003849d  jb      loc_1400388C4
0x1400384a3  mov     eax, [rsi+90h]
0x1400384a9  test    eax, eax
0x1400384ab  jnz     short loc_1400384B2
0x1400384ad  xor     r15d, r15d
0x1400384b0  jmp     short loc_1400384BE
0x1400384b2  lea     r15d, [rax-1]
0x1400384b6  add     r15d, edx
0x1400384b9  neg     eax
0x1400384bb  and     r15d, eax
0x1400384be  cmp     r15d, edx
0x1400384c1  jnb     short loc_14003850D
0x1400384c3  lea     rax, WPP_GLOBAL_Control
0x1400384ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400384d1  cmp     rcx, rax
0x1400384d4  jz      short loc_140038503
0x1400384d6  test    dword ptr [rcx+2Ch], 8000000h
0x1400384dd  jz      short loc_140038503
0x1400384df  mov     edx, 25h ; '%'
0x1400384e4  mov     [rsp+0D8h+var_B8], 24EBh
0x1400384ec  lea     r9, aCclfsbasefilep_0; "CClfsBaseFilePersisted::ExtendMetadataB"...
0x1400384f3  lea     r8, WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids
0x1400384fa  mov     rcx, [rcx+18h]
0x1400384fe  call    WPP_SF_sd
0x140038503  mov     eax, 0C0000095h
0x140038508  jmp     loc_1400388C9
0x14003850d  xor     r14d, r14d
0x140038510  mov     [rsp+0D8h+var_90], r14
0x140038515  xor     r13d, r13d
0x140038518  mov     [rsp+0D8h+var_80], r13
0x14003851d  xor     edx, edx
0x14003851f  mov     [rsp+0D8h+var_A0], rdx
0x140038524  xor     edi, edi
0x140038526  mov     [rsp+0D8h+var_A8], edi
0x14003852a  mov     eax, r15d
0x14003852d  shr     eax, 9
0x140038530  mov     [rsp+0D8h+arg_10], eax
0x140038537  movups  xmm6, xmmword ptr [r9+r12*8]
0x14003853c  movups  [rsp+0D8h+var_78], xmm6
0x140038541  movsd   xmm7, qword ptr [r9+r12*8+10h]
0x140038548  movsd   [rsp+0D8h+var_68], xmm7
0x14003854e  lea     r10d, [rbx+1]
0x140038552  mov     r8d, r10d; unsigned int
0x140038555  mov     edx, ebx; unsigned int
0x140038557  call    ?IsShadowBlock@CClfsBaseFilePersisted@@AEAAEKK@Z; CClfsBaseFilePersisted::IsShadowBlock(ulong,ulong)
0x14003855c  test    al, al
0x14003855e  jnz     loc_140038624
0x140038564  mov     r8d, ebx; unsigned int
0x140038567  mov     edx, r10d; unsigned int
0x14003856a  call    ?IsShadowBlock@CClfsBaseFilePersisted@@AEAAEKK@Z; CClfsBaseFilePersisted::IsShadowBlock(ulong,ulong)
0x14003856f  test    al, al
0x140038571  jz      loc_140038624
0x140038577  mov     rcx, [r9+r12*8]; P
0x14003857b  test    rcx, rcx
0x14003857e  jz      short loc_1400385A4
0x140038580  lea     rdx, [r10+r10*2]
0x140038584  cmp     rcx, [r9+rdx*8]
0x140038588  jz      short loc_1400385A4
0x14003858a  xor     edx, edx; Tag
0x14003858c  call    cs:__imp_ExFreePoolWithTag
0x140038593  nop     dword ptr [rax+rax+00h]
0x140038598  mov     rax, [rsi+30h]
0x14003859c  mov     [rax+r12*8], rdi
0x1400385a0  lea     r10d, [rbx+1]
0x1400385a4  lea     rdx, [r10+r10*2]
0x1400385a8  mov     rcx, [rsi+30h]
0x1400385ac  mov     eax, [rcx+rdx*8+8]
0x1400385b0  mov     [rcx+r12*8+8], eax
0x1400385b5  mov     rcx, [rsi+30h]
0x1400385b9  mov     rax, [rcx+rdx*8]
0x1400385bd  mov     [rcx+r12*8], rax
0x1400385c1  cmp     ebx, 2
0x1400385c4  jnz     short loc_140038616
0x1400385c6  mov     rax, [rsi+30h]
0x1400385ca  mov     r14, [rax+30h]
0x1400385ce  mov     [rsp+0D8h+var_90], r14
0x1400385d3  mov     ecx, [r14+28h]
0x1400385d7  lea     rax, [r14+18h]
0x1400385db  add     rax, rcx
0x1400385de  mov     [rsi+40h], rax
0x1400385e2  lea     edx, [rbx+9]
0x1400385e5  mov     [rsi+48h], edx
0x1400385e8  mov     [rsi+50h], rsi
0x1400385ec  lea     rax, [r14+70h]
0x1400385f0  add     rax, rcx
0x1400385f3  mov     [rsi+58h], rax
0x1400385f7  mov     [rsi+60h], edx
0x1400385fa  mov     [rsi+68h], rsi
0x1400385fe  lea     rax, [r14+0C8h]
0x140038605  add     rax, rcx
0x140038608  mov     [rsi+70h], rax
0x14003860c  mov     [rsi+78h], edx
0x14003860f  mov     [rsi+80h], rsi
0x140038616  xor     edi, edi
0x140038618  mov     [rsp+0D8h+var_A8], edi
0x14003861c  mov     r12, rbx
0x14003861f  jmp     loc_140038852
0x140038624  mov     r13, [r9+r12*8]
0x140038628  mov     [rsp+0D8h+var_80], r13
0x14003862d  cmp     ebx, 3
0x140038630  jnz     short loc_140038646
0x140038632  mov     rcx, rsi; this
0x140038635  call    ?GetBaseLogRecord@CClfsBaseFile@@IEAAPEAU_CLFS_BASE_RECORD_HEADER@@XZ; CClfsBaseFile::GetBaseLogRecord(void)
0x14003863a  test    rax, rax
0x14003863d  jnz     short loc_140038646
0x14003863f  mov     edi, 0C01A000Dh
0x140038644  jmp     short loc_140038618
0x140038646  mov     eax, [r13+28h]
0x14003864a  add     rax, r13
0x14003864d  mov     [rsp+0D8h+Src], rax
0x140038652  mov     edx, r15d; NumberOfBytes
0x140038655  mov     ecx, 5; PoolType
0x14003865a  mov     r8d, 73666C43h; Tag
0x140038660  call    cs:__imp_ExAllocatePoolWithTag
0x140038667  nop     dword ptr [rax+rax+00h]
0x14003866c  mov     r14, rax
0x14003866f  mov     [rsp+0D8h+var_90], rax
0x140038674  test    rax, rax
0x140038677  jnz     short loc_140038680
0x140038679  mov     edi, 0C000009Ah
0x14003867e  jmp     short loc_140038618
0x140038680  mov     rcx, [rsi+98h]; this
0x140038687  call    ?GetAlignmentRequirement@CClfsAuthContainer@@QEAAKXZ; CClfsAuthContainer::GetAlignmentRequirement(void)
0x14003868c  mov     eax, eax
0x14003868e  test    r14, rax
0x140038691  jz      short loc_14003869D
0x140038693  mov     edi, 0C0000220h
0x140038698  jmp     loc_140038618
0x14003869d  mov     rax, [rsi+30h]
0x1400386a1  mov     ebx, [rax+r12*8+8]
0x1400386a6  mov     r8d, ebx; Size
0x1400386a9  mov     rdx, r13; Src
0x1400386ac  mov     rcx, r14; void *
0x1400386af  call    memmove
0x1400386b4  mov     r8d, r15d
0x1400386b7  sub     r8d, ebx; Size
0x1400386ba  mov     rax, [rsi+30h]
0x1400386be  mov     ecx, [rax+r12*8+8]
0x1400386c3  add     rcx, r14; void *
0x1400386c6  xor     edx, edx; Val
0x1400386c8  call    memset
0x1400386cd  mov     eax, [rsp+0D8h+arg_10]
0x1400386d4  mov     [r14+4], ax
0x1400386d9  mov     dword ptr [r14+28h], 70h ; 'p'
0x1400386e1  mov     r9d, [r13+28h]
0x1400386e5  lea     rcx, [r14+70h]; void *
0x1400386e9  mov     rax, [rsi+30h]
0x1400386ed  mov     edx, [rax+r12*8+8]
0x1400386f2  sub     edx, r9d
0x1400386f5  mov     ebx, edx
0x1400386f7  add     r9, r14
0x1400386fa  lea     rax, [rdx+70h]
0x1400386fe  add     rax, r14
0x140038701  cmp     rax, r9
0x140038704  jbe     short loc_14003877A
0x140038706  mov     r8d, 73666C43h; Tag
0x14003870c  mov     edx, ebx; NumberOfBytes
0x14003870e  mov     ecx, 5; PoolType
0x140038713  call    cs:__imp_ExAllocatePoolWithTag
0x14003871a  nop     dword ptr [rax+rax+00h]
0x14003871f  mov     [rsp+0D8h+var_A0], rax
0x140038724  test    rax, rax
0x140038727  jnz     short loc_140038746
0x140038729  mov     edi, 0C000009Ah
0x14003872e  mov     [rsp+0D8h+var_A8], edi
0x140038732  mov     ebx, [rsp+0D8h+arg_8]
0x140038739  mov     r12, [rsp+0D8h+arg_18]
0x140038741  jmp     loc_140038857
0x140038746  mov     r8, rbx; Size
0x140038749  mov     rdx, [rsp+0D8h+Src]; Src
0x14003874e  mov     rcx, rax; void *
0x140038751  call    memmove
0x140038756  mov     ecx, [r13+28h]
0x14003875a  add     rcx, r14; void *
0x14003875d  mov     r8, rbx; Size
0x140038760  xor     edx, edx; Val
0x140038762  call    memset
0x140038767  mov     r8, rbx; Size
0x14003876a  mov     rdx, [rsp+0D8h+var_A0]; Src
0x14003876f  lea     rcx, [r14+70h]; void *
0x140038773  call    memmove
0x140038778  jmp     short loc_140038798
0x14003877a  mov     r8, rbx; Size
0x14003877d  mov     rdx, [rsp+0D8h+Src]; Src
0x140038782  call    memmove
0x140038787  mov     ecx, [r13+28h]
0x14003878b  add     rcx, r14; void *
0x14003878e  mov     r8, rbx; Size
0x140038791  xor     edx, edx; Val
0x140038793  call    memset
0x140038798  mov     [rsp+0D8h+var_98], 0
0x1400387a0  mov     eax, 80808081h
0x1400387a5  mul     r15d
0x1400387a8  shr     edx, 8
0x1400387ab  mov     ecx, edx
0x1400387ad  mov     [rsp+0D8h+var_98], edx
0x1400387b1  imul    eax, edx, 1FEh
0x1400387b7  mov     r10d, r15d
0x1400387ba  sub     r10d, eax
0x1400387bd  lea     r9d, [rdx+1]
0x1400387c1  jz      short loc_1400387CA
0x1400387c3  mov     ecx, r9d
0x1400387c6  mov     [rsp+0D8h+var_98], ecx
0x1400387ca  mov     eax, ecx
0x1400387cc  lea     rax, ds:7[rax*2]
0x1400387d4  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400387d8  cmp     eax, r15d
0x1400387db  jb      short loc_1400387F0
0x1400387dd  mov     edi, 0C01A000Ah
0x1400387e2  mov     [rsp+0D8h+var_A8], edi
0x1400387e6  mov     r12, [rsp+0D8h+arg_18]
0x1400387ee  jmp     short loc_14003884B
0x1400387f0  mov     r8d, [rsi+90h]; unsigned int
0x1400387f7  mov     [rsp+0D8h+var_94], 0
0x1400387ff  mov     [rsp+0D8h+var_94], edx
0x140038803  test    r10d, r10d
0x140038806  cmovnz  edx, r9d
0x14003880a  mov     [rsp+0D8h+var_94], edx
0x14003880e  lea     rax, ds:7[rdx*2]
0x140038816  and     rax, 0FFFFFFFFFFFFFFF8h
0x14003881a  mov     edx, r15d
0x14003881d  sub     edx, eax; unsigned int
0x14003881f  xor     r9d, r9d; struct _CLFS_RECORD_HEADER *
0x140038822  mov     rcx, r14; struct _CLFS_LOG_BLOCK_HEADER *
0x140038825  call    ?ClfsStampLogBlock@@YAXPEAU_CLFS_LOG_BLOCK_HEADER@@KKPEAU_CLFS_RECORD_HEADER@@@Z; ClfsStampLogBlock(_CLFS_LOG_BLOCK_HEADER *,ulong,ulong,_CLFS_RECORD_HEADER *)
0x14003882a  mov     r12, [rsp+0D8h+arg_18]
0x140038832  lea     r9, [r12+r12*2]
0x140038836  mov     rax, [rsi+30h]
0x14003883a  mov     [rax+r9*8+8], r15d
0x14003883f  lea     rcx, [r12+r12*2]
0x140038843  mov     rax, [rsi+30h]
0x140038847  mov     [rax+rcx*8], r14
0x14003884b  mov     ebx, [rsp+0D8h+arg_8]
0x140038852  mov     rax, [rsp+0D8h+var_A0]
0x140038857  test    rax, rax
0x14003885a  jz      short loc_14003886D
0x14003885c  xor     edx, edx; Tag
0x14003885e  mov     rcx, rax; P
0x140038861  call    cs:__imp_ExFreePoolWithTag
0x140038868  nop     dword ptr [rax+rax+00h]
0x14003886d  test    edi, edi
0x14003886f  jns     short loc_14003889B
0x140038871  test    r14, r14
0x140038874  jz      short loc_140038887
0x140038876  xor     edx, edx; Tag
0x140038878  mov     rcx, r14; P
0x14003887b  call    cs:__imp_ExFreePoolWithTag
0x140038882  nop     dword ptr [rax+rax+00h]
0x140038887  lea     rcx, [r12+r12*2]
0x14003888b  mov     rax, [rsi+30h]
0x14003888f  movups  xmmword ptr [rax+rcx*8], xmm6
0x140038893  movsd   qword ptr [rax+rcx*8+10h], xmm7
0x140038899  jmp     short loc_1400388C0
0x14003889b  test    r13, r13
0x14003889e  jz      short loc_1400388C0
0x1400388a0  lea     r8d, [rbx-1]; unsigned int
0x1400388a4  mov     edx, ebx; unsigned int
0x1400388a6  call    ?IsShadowBlock@CClfsBaseFilePersisted@@AEAAEKK@Z; CClfsBaseFilePersisted::IsShadowBlock(ulong,ulong)
0x1400388ab  test    al, al
0x1400388ad  jnz     short loc_1400388C0
0x1400388af  xor     edx, edx; Tag
0x1400388b1  mov     rcx, r13; P
0x1400388b4  call    cs:__imp_ExFreePoolWithTag
0x1400388bb  nop     dword ptr [rax+rax+00h]
0x1400388c0  mov     eax, edi
0x1400388c2  jmp     short loc_1400388C9
0x1400388c4  mov     eax, 0C01A000Dh
0x1400388c9  lea     r11, [rsp+0D8h+var_38]
  ... truncated ...
```
