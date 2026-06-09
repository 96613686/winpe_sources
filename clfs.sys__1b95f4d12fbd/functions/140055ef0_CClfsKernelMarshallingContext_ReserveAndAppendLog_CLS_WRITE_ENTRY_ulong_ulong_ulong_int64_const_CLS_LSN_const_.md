# CClfsKernelMarshallingContext::ReserveAndAppendLog(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,_CLS_LSN const &,_CLS_LSN const &,ulong,_CLS_LSN &)

- ea: `0x140055ef0`
- end: `0x1400565ee`
- name: `?ReserveAndAppendLog@CClfsKernelMarshallingContext@@QEAAJPEAU_CLS_WRITE_ENTRY@@KKKQEA_JAEBT_CLS_LSN@@2KAEAT3@@Z`
- size: `1790`
- prototype: `__int64 __usercall@<rax>(CClfsKernelMarshallingContext *__hidden this@<rcx>, struct _CLS_WRITE_ENTRY *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, __int64 *const, const union _CLS_LSN *, const union _CLS_LSN *, unsigned int, union _CLS_LSN *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140055aa0`

## callees

- `0x140016cc8`
- `0x140018280`
- `0x140055ef0`
- `0x140056600`
- `0x1400572a0`
- `0x1400577c0`
- `0x140058210`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055f4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005651b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055f4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005651b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140056547`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140056588`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400798de`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140056547`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140056588`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400798de`

## pseudocode

```c
__int64 __fastcall CClfsKernelMarshallingContext::ReserveAndAppendLog(
        CClfsKernelMarshallingContext *this,
        struct _CLS_WRITE_ENTRY *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 *const a6,
        const union _CLS_LSN *a7,
        const union _CLS_LSN *a8,
        unsigned int a9,
        union _CLS_LSN *a10)
{
  int Iocb; // edi
  char v12; // r15
  int v13; // r14d
  unsigned __int64 i; // rdx
  BOOLEAN v15; // bl
  __int64 v16; // r8
  PVOID *v17; // r12
  struct _CLS_WRITE_ENTRY *v18; // r10
  unsigned int v19; // ebx
  unsigned int v20; // ecx
  int appended; // eax
  union _CLS_LSN *v22; // rcx
  int v23; // eax
  unsigned int v24; // eax
  _DWORD *v25; // rax
  unsigned int v26; // r10d
  __int64 v27; // r9
  struct _CLFS_RECORD_HEADER *v28; // rcx
  unsigned int v29; // r8d
  __int64 v30; // rcx
  bool v31; // zf
  unsigned int v32; // eax
  char v33; // al
  _QWORD *v34; // r14
  CLFS_LSN *v35; // rbx
  unsigned __int64 v36; // rax
  unsigned int v37; // ecx
  unsigned int v38; // eax
  unsigned int v39; // r8d
  __int64 v40; // rax
  unsigned int v41; // eax
  char v42; // al
  unsigned int v43; // eax
  PVOID v44; // r14
  CLFS_LSN *v45; // rbx
  unsigned __int64 v46; // rax
  BOOLEAN v48; // [rsp+B8h] [rbp-88h]
  unsigned int v49; // [rsp+C4h] [rbp-7Ch]
  unsigned int v50; // [rsp+CCh] [rbp-74h] BYREF
  unsigned int v51; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-68h]
  struct _CLFS_RECORD_HEADER *v53; // [rsp+E0h] [rbp-60h] BYREF
  unsigned int v54; // [rsp+E8h] [rbp-58h] BYREF
  unsigned int v55; // [rsp+ECh] [rbp-54h]
  int v56; // [rsp+F0h] [rbp-50h]
  struct _CLS_WRITE_ENTRY *v57; // [rsp+100h] [rbp-40h]

  v53 = 0;
  Iocb = 0;
  v12 = 0;
  v50 = 0;
  v51 = 0;
  v54 = 0;
  v13 = 0;
  LODWORD(v52) = 0;
  if ( !*((_DWORD *)this + 16) )
    return 3222929414LL;
  v15 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 17), 1u);
  v48 = v15;
  if ( *((_BYTE *)this + 188) )
  {
    Iocb = -1072037845;
    if ( !*(&CClfsLogFcbCommon::m_infoGlobalError + 2) )
    {
      *(&CClfsLogFcbCommon::m_infoGlobalError + 2) = 20;
      *(&CClfsLogFcbCommon::m_infoGlobalError + 3) = -1072037845;
    }
    goto LABEL_69;
  }
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slqdi(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      16,
      v16,
      (unsigned int)"CClfsKernelMarshallingContext::ReserveAndAppendLog",
      248,
      (char)this,
      *((_DWORD *)this + 15),
      *((_QWORD *)this + 11));
  }
  v17 = (PVOID *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
  {
    Iocb = CClfsKernelMarshallingContext::AllocateIocb((CLFS_LSN)this, 1, (CLFS_LSN **)this + 16);
    if ( Iocb < 0 )
      goto LABEL_69;
    v44 = *v17;
    if ( !*v17 )
      goto LABEL_69;
    v45 = (CLFS_LSN *)*((_QWORD *)v44 + 1);
    memset(v45, 0, 0x70u);
    LOBYTE(v45->offset.idxRecord) = 21;
    v45[3] = CLFS_LSN_INVALID;
    v45[4] = CLFS_LSN_INVALID;
    v45[5].offset.idxRecord = 112;
    v46 = ((unsigned __int64)*((unsigned int *)this + 11) - 40) >> 9;
    HIWORD(v45->ullOffset) = v46;
    WORD2(v45->ullOffset) = v46;
    *((_DWORD *)v44 + 4) = 112;
    v45[5].offset.idxRecord = 0;
    v13 = v52;
  }
  v18 = a2;
  v57 = a2;
  v19 = a3;
  v20 = a3;
  v49 = a3;
  while ( !v12 )
  {
    appended = CClfsKernelMarshallingContext::AppendRecord(this, v18, v20, a4, a5, a6, a9, &v53, &v51, &v54, &v50);
    Iocb = appended;
    if ( appended != -2147483643 )
    {
      if ( appended )
        goto LABEL_20;
      if ( v19 )
      {
        v22 = (union _CLS_LSN *)v53;
        *((_BYTE *)v53 + 36) |= 1u;
        v22[1] = *a7;
        v22[2] = *a8;
        LODWORD(v52) = v50 + v13;
        v56 = v50 + v13;
        v16 = *((_QWORD *)*v17 + 1);
        i = *((unsigned int *)this + 17);
        if ( (_DWORD)i )
        {
          v23 = i + *((_DWORD *)*v17 + 4) - 1;
          i = (unsigned int)-(int)i;
          v24 = i & v23;
        }
        else
        {
          v24 = 0;
        }
        *(_WORD *)(v16 + 4) = v24 >> 9;
        *a10 = *v22;
      }
      v12 = 1;
LABEL_16:
      v20 = v49;
      v18 = a2;
      goto LABEL_17;
    }
    v26 = v50;
    if ( v50 )
    {
      v28 = v53;
    }
    else
    {
      v27 = *((_QWORD *)*v17 + 1);
      v28 = 0;
      v53 = 0;
      if ( *(_DWORD *)(v27 + 40) )
      {
        for ( i = 1; (unsigned __int16)i < 0x10u; LOWORD(i) = i + 1 )
        {
          v29 = *(_DWORD *)(v27 + 4LL * (unsigned __int16)i + 40);
          if ( !v29 )
            break;
          if ( v29 > *(unsigned __int16 *)(v27 + 4) << 9 )
            goto LABEL_30;
        }
        v30 = *(unsigned int *)(v27 + 4LL * (unsigned __int16)i + 36);
        v31 = v27 + v30 == 0;
        v28 = (struct _CLFS_RECORD_HEADER *)(v27 + v30);
        v53 = v28;
        v52 = 0;
        v32 = -1;
        if ( !v31 )
          v32 = *(_DWORD *)v28 & 0x1FF;
        if ( v32 >= 0x1FF
          || (v33 = *((_BYTE *)v28 + 36), (v33 & 0x3F) == 0)
          || (v33 & 0xC0) != 0
          || (v38 = *((unsigned __int16 *)v28 + 17), v38 < 0x28)
          || (i = *((unsigned int *)v28 + 6), v38 > (unsigned int)i)
          || (i = (unsigned __int64)v28 + i - v27, i > *(unsigned __int16 *)(v27 + 4) << 9) )
        {
LABEL_30:
          Iocb = -1072037878;
          goto LABEL_31;
        }
        v39 = 0;
        v55 = 0;
        while ( (*((_BYTE *)v28 + 36) & 0x20) == 0 )
        {
          if ( v39 >= 0x1FF )
            goto LABEL_30;
          i = 4294967288LL;
          v40 = (*((_DWORD *)v28 + 6) + 7) & 0xFFFFFFF8;
          v31 = (struct _CLFS_RECORD_HEADER *)((char *)v28 + v40) == 0;
          v28 = (struct _CLFS_RECORD_HEADER *)((char *)v28 + v40);
          v53 = v28;
          v41 = -1;
          if ( !v31 )
            v41 = *(_DWORD *)v28 & 0x1FF;
          if ( v41 >= 0x1FF )
            goto LABEL_30;
          v42 = *((_BYTE *)v28 + 36);
          if ( (v42 & 0x3F) == 0 )
            goto LABEL_30;
          if ( (v42 & 0xC0) != 0 )
            goto LABEL_30;
          v43 = *((unsigned __int16 *)v28 + 17);
          if ( v43 < 0x28 )
            goto LABEL_30;
          i = *((unsigned int *)v28 + 6);
          if ( v43 > (unsigned int)i )
            goto LABEL_30;
          i = (unsigned __int64)v28 + i - v27;
          if ( i > *(unsigned __int16 *)(v27 + 4) << 9 )
            goto LABEL_30;
          v55 = ++v39;
        }
        Iocb = 0;
      }
      else
      {
        Iocb = -1073741275;
      }
    }
LABEL_31:
    if ( !v28 )
    {
      ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 18), 1u);
      CClfsKernelMarshallingContext::DeallocateIocb(this, *v17);
      *v17 = 0;
      ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 18), (ERESOURCE_THREAD)KeGetCurrentThread());
      goto LABEL_20;
    }
    *((_BYTE *)v28 + 36) |= 1u;
    LODWORD(v52) = v26 + v13;
    v56 = v26 + v13;
    *a10 = *(union _CLS_LSN *)v28;
    *((_DWORD *)*v17 + 32) |= 2u;
    Iocb = CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(this, i, 0);
    if ( Iocb < 0 )
      goto LABEL_20;
    Iocb = CClfsKernelMarshallingContext::AllocateIocb((CLFS_LSN)this, 1, (CLFS_LSN **)this + 16);
    if ( Iocb < 0 )
      goto LABEL_20;
    v34 = *v17;
    if ( !*v17 )
      goto LABEL_20;
    v35 = (CLFS_LSN *)v34[1];
    memset(v35, 0, 0x70u);
    LOBYTE(v35->offset.idxRecord) = 21;
    v35[3] = CLFS_LSN_INVALID;
    v35[4] = CLFS_LSN_INVALID;
    v35[5].offset.idxRecord = 112;
    v36 = ((unsigned __int64)*((unsigned int *)this + 11) - 40) >> 9;
    HIWORD(v35->ullOffset) = v36;
    WORD2(v35->ullOffset) = v36;
    *((_DWORD *)v34 + 4) = 112;
    LODWORD(v16) = 0;
    v35[5].offset.idxRecord = 0;
    v19 = a3;
    if ( !a3 )
      goto LABEL_16;
    i = v51;
    v18 = &a2[v51];
    a2 = v18;
    v57 = v18;
    v37 = v54;
    v18->Buffer = (char *)v18->Buffer + v54;
    v18->ByteLength -= v37;
    v20 = v49 - i;
    v49 -= i;
    v51 = 0;
LABEL_17:
    v13 = v52;
  }
  v25 = *v17;
  if ( *v17 && (a9 & 3) != 0 && (v25[4] || *((_QWORD *)v25 + 4)) )
    Iocb = CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(this, i, a9 & 0xFFFFFFFE);
LABEL_20:
  v15 = v48;
LABEL_69:
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slqdi(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      17,
      v16,
      (unsigned int)"CClfsKernelMarshallingContext::ReserveAndAppendLog",
      5,
      (char)this,
      *((_DWORD *)this + 15),
      *((_QWORD *)this + 11));
  }
  if ( v15 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 17), (ERESOURCE_THREAD)KeGetCurrentThread());
  return (unsigned int)Iocb;
}

```

## disassembly

```asm
0x140055ef0  mov     r11, rsp
0x140055ef3  mov     [r11+20h], r9d
0x140055ef7  mov     [r11+18h], r8d
0x140055efb  mov     [r11+10h], rdx
0x140055eff  mov     [r11+8], rcx
0x140055f03  push    rbx
0x140055f04  push    rsi
0x140055f05  push    rdi
0x140055f06  push    r12
0x140055f08  push    r13
0x140055f0a  push    r14
0x140055f0c  push    r15
0x140055f0e  sub     rsp, 0B0h
0x140055f15  mov     rsi, rcx
0x140055f18  xor     eax, eax
0x140055f1a  mov     [r11-60h], rax
0x140055f1e  mov     edi, eax
0x140055f20  xor     r15b, r15b
0x140055f23  mov     [rsp+0E8h+var_88], al
0x140055f27  mov     [rsp+0E8h+var_74], eax
0x140055f2b  mov     [rsp+0E8h+var_70], eax
0x140055f2f  mov     [r11-58h], eax
0x140055f33  mov     r14d, eax
0x140055f36  mov     [r11-68h], eax
0x140055f3a  cmp     [rcx+40h], eax
0x140055f3d  jz      loc_1400565E7
0x140055f43  mov     dl, 1; Wait
0x140055f45  mov     rcx, [rcx+88h]; Resource
0x140055f4c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140055f53  nop     dword ptr [rax+rax+00h]
0x140055f58  movzx   ebx, al
0x140055f5b  mov     [rsp+0E8h+var_88], al
0x140055f5f  cmp     [rsi+0BCh], r15b
0x140055f66  jnz     loc_14005649C
0x140055f6c  lea     r13, WPP_GLOBAL_Control
0x140055f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140055f7a  cmp     rcx, r13
0x140055f7d  jz      short loc_140055F8C
0x140055f7f  test    dword ptr [rcx+2Ch], 4000000h
0x140055f86  jnz     loc_1400564CE
0x140055f8c  lea     r12, [rsi+80h]
0x140055f93  cmp     qword ptr [r12], 0
0x140055f98  jz      loc_1400563EE
0x140055f9e  mov     r10, [rsp+0E8h+arg_8]
0x140055fa6  mov     [rsp+0E8h+var_40], r10
0x140055fae  mov     ebx, [rsp+0E8h+arg_10]
0x140055fb5  mov     ecx, ebx
0x140055fb7  mov     [rsp+0E8h+var_7C], ebx
0x140055fbb  test    r15b, r15b
0x140055fbe  jnz     loc_1400560DC
0x140055fc4  lea     rax, [rsp+0E8h+var_74]
0x140055fc9  mov     [rsp+0E8h+var_98], rax; unsigned int *
0x140055fce  lea     rax, [rsp+0E8h+var_58]
0x140055fd6  mov     [rsp+0E8h+var_A0], rax; unsigned int *
0x140055fdb  lea     rax, [rsp+0E8h+var_70]
0x140055fe0  mov     [rsp+0E8h+var_A8], rax; unsigned int *
0x140055fe5  lea     rax, [rsp+0E8h+var_60]
0x140055fed  mov     [rsp+0E8h+var_B0], rax; struct _CLFS_RECORD_HEADER **
0x140055ff2  mov     eax, dword ptr [rsp+0E8h+arg_40]
0x140055ff9  mov     dword ptr [rsp+0E8h+var_B8], eax; char
0x140055ffd  mov     rax, [rsp+0E8h+arg_28]
0x140056005  mov     [rsp+0E8h+var_C0], rax; __int64 *
0x14005600a  mov     eax, [rsp+0E8h+arg_20]
0x140056011  mov     [rsp+0E8h+var_C8], eax; unsigned int
0x140056015  mov     r9d, [rsp+0E8h+arg_18]; unsigned int
0x14005601d  mov     r8d, ecx; unsigned int
0x140056020  mov     rdx, r10; struct _CLS_WRITE_ENTRY *
0x140056023  mov     rcx, rsi; this
0x140056026  call    ?AppendRecord@CClfsKernelMarshallingContext@@AEAAJPEAU_CLS_WRITE_ENTRY@@KKKQEA_JKAEAPEAU_CLFS_RECORD_HEADER@@AEAK33@Z; CClfsKernelMarshallingContext::AppendRecord(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,ulong,_CLFS_RECORD_HEADER * &,ulong &,ulong &,ulong &)
0x14005602b  mov     edi, eax
0x14005602d  mov     [rsp+0E8h+var_84], eax
0x140056031  cmp     eax, 80000005h
0x140056036  jz      loc_1400560FF
0x14005603c  test    eax, eax
0x14005603e  jnz     loc_1400560F5
0x140056044  test    ebx, ebx
0x140056046  jz      short loc_1400560BB
0x140056048  mov     rcx, [rsp+0E8h+var_60]
0x140056050  or      byte ptr [rcx+24h], 1
0x140056054  mov     rax, [rsp+0E8h+arg_30]
0x14005605c  mov     rax, [rax]
0x14005605f  mov     [rcx+8], rax
0x140056063  mov     rax, [rsp+0E8h+arg_38]
0x14005606b  mov     rax, [rax]
0x14005606e  mov     [rcx+10h], rax
0x140056072  add     r14d, [rsp+0E8h+var_74]
0x140056077  mov     dword ptr [rsp+0E8h+var_68], r14d
0x14005607f  mov     [rsp+0E8h+var_50], r14d
0x140056087  mov     rax, [r12]
0x14005608b  mov     r8, [rax+8]
0x14005608f  mov     edx, [rsi+44h]
0x140056092  test    edx, edx
0x140056094  jz      loc_140056495
0x14005609a  mov     eax, [rax+10h]
0x14005609d  dec     eax
0x14005609f  add     eax, edx
0x1400560a1  neg     edx
0x1400560a3  and     eax, edx
0x1400560a5  shr     eax, 9
0x1400560a8  mov     [r8+4], ax
0x1400560ad  mov     rax, [rcx]
0x1400560b0  mov     rcx, [rsp+0E8h+arg_48]
0x1400560b8  mov     [rcx], rax
0x1400560bb  mov     r15b, 1
0x1400560be  mov     [rsp+0E8h+var_78], r15b
0x1400560c3  mov     ecx, [rsp+0E8h+var_7C]
0x1400560c7  mov     r10, [rsp+0E8h+arg_8]
0x1400560cf  mov     r14d, dword ptr [rsp+0E8h+var_68]
0x1400560d7  jmp     loc_140055FBB
0x1400560dc  mov     rax, [r12]
0x1400560e0  test    rax, rax
0x1400560e3  jz      short loc_1400560F5
0x1400560e5  mov     ecx, dword ptr [rsp+0E8h+arg_40]
0x1400560ec  test    cl, 3
0x1400560ef  jnz     loc_1400563C1
0x1400560f5  movzx   ebx, [rsp+0E8h+var_88]
0x1400560fa  jmp     loc_140056568
0x1400560ff  mov     r10d, [rsp+0E8h+var_74]
0x140056104  xor     ebx, ebx
0x140056106  test    r10d, r10d
0x140056109  jnz     loc_140056505
0x14005610f  mov     rax, [r12]
0x140056113  mov     r9, [rax+8]
0x140056117  mov     [rsp+0E8h+var_80], bx
0x14005611c  mov     ecx, ebx
0x14005611e  mov     [rsp+0E8h+var_60], rbx
0x140056126  cmp     [r9+28h], ebx
0x14005612a  jz      loc_1400563E4
0x140056130  mov     edx, 1; unsigned __int8
0x140056135  mov     [rsp+0E8h+var_80], dx
0x14005613a  cmp     dx, 10h
0x14005613e  jnb     short loc_140056151
0x140056140  movzx   eax, dx
0x140056143  mov     r8d, [r9+rax*4+28h]
0x140056148  test    r8d, r8d
0x14005614b  jnz     loc_14005647C
0x140056151  movzx   eax, dx
0x140056154  mov     ecx, [r9+rax*4+24h]
0x140056159  add     rcx, r9
0x14005615c  mov     [rsp+0E8h+var_60], rcx
0x140056164  mov     [rsp+0E8h+var_68], rbx
0x14005616c  mov     eax, 0FFFFFFFFh
0x140056171  jz      short loc_14005617A
0x140056173  mov     eax, [rcx]
0x140056175  and     eax, 1FFh
0x14005617a  cmp     eax, 1FFh
0x14005617f  jnb     short loc_14005618D
0x140056181  movzx   eax, byte ptr [rcx+24h]
0x140056185  test    al, 3Fh
0x140056187  jnz     loc_1400562BF
0x14005618d  mov     edi, 0C01A000Ah
0x140056192  mov     [rsp+0E8h+var_84], edi
0x140056196  test    rcx, rcx
0x140056199  jz      loc_140056512
0x14005619f  or      byte ptr [rcx+24h], 1
0x1400561a3  add     r14d, r10d
0x1400561a6  mov     dword ptr [rsp+0E8h+var_68], r14d
0x1400561ae  mov     [rsp+0E8h+var_50], r14d
0x1400561b6  mov     rax, [rcx]
0x1400561b9  mov     rcx, [rsp+0E8h+arg_48]
0x1400561c1  mov     [rcx], rax
0x1400561c4  mov     rax, [r12]
0x1400561c8  or      dword ptr [rax+80h], 2
0x1400561cf  xor     r8d, r8d; unsigned int
0x1400561d2  mov     rcx, rsi; this
0x1400561d5  call    ?AppendWriteBlockToFlushQueue@CClfsKernelMarshallingContext@@AEAAJEK@Z; CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong)
0x1400561da  mov     edi, eax
0x1400561dc  mov     [rsp+0E8h+var_84], eax
0x1400561e0  test    eax, eax
0x1400561e2  js      loc_1400560F5
0x1400561e8  mov     r8, r12
0x1400561eb  mov     edx, 1
0x1400561f0  mov     rcx, rsi
0x1400561f3  call    ?AllocateIocb@CClfsKernelMarshallingContext@@AEAAJW4_LOGIOCB_TYPE@1@AEAPEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::AllocateIocb(CClfsKernelMarshallingContext::_LOGIOCB_TYPE,_LOGIOCB * &)
0x1400561f8  mov     edi, eax
0x1400561fa  mov     [rsp+0E8h+var_84], eax
0x1400561fe  test    eax, eax
0x140056200  js      loc_1400560F5
0x140056206  mov     r14, [r12]
0x14005620a  test    r14, r14
0x14005620d  jz      loc_1400560F5
0x140056213  mov     rbx, [r14+8]
0x140056217  xor     edx, edx; Val
0x140056219  mov     r8d, 70h ; 'p'; Size
0x14005621f  mov     rcx, rbx; void *
0x140056222  call    memset
0x140056227  mov     byte ptr [rbx], 15h
0x14005622a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140056231  mov     [rbx+18h], rax
0x140056235  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14005623c  mov     [rbx+20h], rax
0x140056240  mov     dword ptr [rbx+28h], 70h ; 'p'
0x140056247  mov     eax, [rsi+2Ch]
0x14005624a  sub     rax, 28h ; '('
0x14005624e  shr     rax, 9
0x140056252  mov     [rbx+6], ax
0x140056256  mov     [rbx+4], ax
0x14005625a  mov     dword ptr [r14+10h], 70h ; 'p'
0x140056262  xor     r8d, r8d
0x140056265  mov     [rbx+28h], r8d
0x140056269  mov     ebx, [rsp+0E8h+arg_10]
0x140056270  test    ebx, ebx
0x140056272  jz      loc_1400560C3
0x140056278  mov     edx, [rsp+0E8h+var_70]
0x14005627c  mov     eax, edx
0x14005627e  shl     rax, 4
0x140056282  mov     r10, [rsp+0E8h+arg_8]
0x14005628a  add     r10, rax
0x14005628d  mov     [rsp+0E8h+arg_8], r10
0x140056295  mov     [rsp+0E8h+var_40], r10
0x14005629d  mov     ecx, [rsp+0E8h+var_58]
0x1400562a4  add     [r10], rcx
0x1400562a7  sub     [r10+8], ecx
0x1400562ab  mov     ecx, [rsp+0E8h+var_7C]
0x1400562af  sub     ecx, edx
0x1400562b1  mov     [rsp+0E8h+var_7C], ecx
0x1400562b5  mov     [rsp+0E8h+var_70], r8d
0x1400562ba  jmp     loc_1400560CF
0x1400562bf  test    al, 0C0h
0x1400562c1  jnz     loc_14005618D
0x1400562c7  movzx   eax, word ptr [rcx+22h]
0x1400562cb  cmp     eax, 28h ; '('
0x1400562ce  jb      loc_14005618D
0x1400562d4  mov     edx, [rcx+18h]
0x1400562d7  cmp     eax, edx
0x1400562d9  ja      loc_14005618D
0x1400562df  sub     rdx, r9
0x1400562e2  add     rdx, rcx
0x1400562e5  mov     rax, rdx
0x1400562e8  shr     rax, 20h
0x1400562ec  test    eax, eax
0x1400562ee  jnz     loc_14005618D
0x1400562f4  movzx   eax, word ptr [r9+4]
0x1400562f9  shl     eax, 9
0x1400562fc  cmp     edx, eax
0x1400562fe  ja      loc_14005618D
0x140056304  mov     r8d, ebx
0x140056307  mov     [rsp+0E8h+var_54], ebx
0x14005630e  xchg    ax, ax
0x140056310  test    byte ptr [rcx+24h], 20h
0x140056314  jnz     loc_1400563BA
0x14005631a  cmp     r8d, 1FFh
0x140056321  jnb     loc_14005618D
0x140056327  mov     eax, [rcx+18h]
0x14005632a  add     eax, 7
0x14005632d  mov     edx, 0FFFFFFF8h
0x140056332  and     rax, rdx
0x140056335  add     rcx, rax
0x140056338  mov     [rsp+0E8h+var_60], rcx
0x140056340  mov     eax, 0FFFFFFFFh
0x140056345  jz      short loc_14005634E
0x140056347  mov     eax, [rcx]
0x140056349  and     eax, 1FFh
0x14005634e  cmp     eax, 1FFh
0x140056353  jnb     loc_14005618D
0x140056359  movzx   eax, byte ptr [rcx+24h]
0x14005635d  test    al, 3Fh
0x14005635f  jz      loc_14005618D
0x140056365  test    al, 0C0h
0x140056367  jnz     loc_14005618D
0x14005636d  movzx   eax, word ptr [rcx+22h]
0x140056371  cmp     eax, 28h ; '('
0x140056374  jb      loc_14005618D
0x14005637a  mov     edx, [rcx+18h]
0x14005637d  cmp     eax, edx
0x14005637f  ja      loc_14005618D
0x140056385  sub     rdx, r9
0x140056388  add     rdx, rcx
0x14005638b  mov     rax, rdx
0x14005638e  shr     rax, 20h
0x140056392  test    eax, eax
0x140056394  jnz     loc_14005618D
0x14005639a  movzx   eax, word ptr [r9+4]
0x14005639f  shl     eax, 9
0x1400563a2  cmp     edx, eax
0x1400563a4  ja      loc_14005618D
0x1400563aa  inc     r8d
0x1400563ad  mov     [rsp+0E8h+var_54], r8d
0x1400563b5  jmp     loc_140056310
0x1400563ba  mov     edi, ebx
0x1400563bc  jmp     loc_140056192
0x1400563c1  cmp     dword ptr [rax+10h], 0
0x1400563c5  jbe     loc_140056558
0x1400563cb  and     ecx, 0FFFFFFFEh
0x1400563ce  mov     r8d, ecx; unsigned int
0x1400563d1  mov     rcx, rsi; this
0x1400563d4  call    ?AppendWriteBlockToFlushQueue@CClfsKernelMarshallingContext@@AEAAJEK@Z; CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong)
0x1400563d9  mov     edi, eax
0x1400563db  mov     [rsp+0E8h+var_84], eax
0x1400563df  jmp     loc_1400560F5
0x1400563e4  mov     edi, 0C0000225h
0x1400563e9  jmp     loc_140056192
0x1400563ee  mov     r8, r12
0x1400563f1  mov     edx, 1
0x1400563f6  mov     rcx, rsi
0x1400563f9  call    ?AllocateIocb@CClfsKernelMarshallingContext@@AEAAJW4_LOGIOCB_TYPE@1@AEAPEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::AllocateIocb(CClfsKernelMarshallingContext::_LOGIOCB_TYPE,_LOGIOCB * &)
0x1400563fe  mov     edi, eax
0x140056400  mov     [rsp+0E8h+var_84], eax
0x140056404  test    eax, eax
0x140056406  js      loc_140056568
  ... truncated ...
```
