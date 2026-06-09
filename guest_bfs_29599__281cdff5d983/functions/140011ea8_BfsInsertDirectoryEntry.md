# BfsInsertDirectoryEntry

- ea: `0x140011ea8`
- end: `0x140012321`
- name: `BfsInsertDirectoryEntry`
- size: `1145`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x1400104ec`
- `0x14001093c`
- `0x140012608`

## callees

- `0x140001008`
- `0x140010754`
- `0x1400115f0`
- `0x14001193c`
- `0x140011ea8`
- `0x140012c40`
- `0x140013860`
- `0x140013980`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011efe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012111`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011efe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012111`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400121e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400122a6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400122c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400122e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400121e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400122a6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400122c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400122e4`
- `ntoskrnl!RtlFindClearBits` at `0x140011f6c`
- `ntoskrnl!RtlFindClearBits` at `0x14001209a`
- `ntoskrnl!RtlFindClearBits` at `0x140011f6c`
- `ntoskrnl!RtlFindClearBits` at `0x14001209a`
- `ntoskrnl!RtlSetBits` at `0x140011f9b`
- `ntoskrnl!RtlSetBits` at `0x140011f9b`
- `ntoskrnl!RtlClearBits` at `0x14001227a`
- `ntoskrnl!RtlClearBits` at `0x14001227a`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011f57`
- `ntoskrnl!RtlInitializeBitMap` at `0x140012085`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011f57`
- `ntoskrnl!RtlInitializeBitMap` at `0x140012085`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012179`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012290`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012179`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012290`
- `ntoskrnl!ExAllocatePool2` at `0x140011ff8`
- `ntoskrnl!ExAllocatePool2` at `0x140011ff8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011eed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012100`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011eed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012100`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400121f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400121f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122f0`

## pseudocode

```c
ULONG *__fastcall BfsInsertDirectoryEntry(__int64 a1, ULONG a2, NTSTATUS a3, ULONG a4, __int64 a5)
{
  __int64 **v8; // rax
  __int64 *v9; // r12
  ULONG *v10; // r13
  __int64 *v11; // rax
  ULONG v12; // ecx
  __int64 v13; // rbx
  ULONG *v14; // r15
  const void **v15; // rax
  __int64 v16; // rcx
  _DWORD *Pool2; // rsi
  __int64 v18; // r8
  __int64 v19; // r9
  char v20; // bl
  signed int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  ULONG ClearBits; // eax
  __int64 *v25; // rdi
  __int64 v26; // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  NTSTATUS v31; // eax
  __int64 v32; // rcx
  NTSTATUS v33; // eax
  __int64 v34; // r8
  __int64 v35; // r9
  int v37; // [rsp+20h] [rbp-71h]
  NTSTATUS v38; // [rsp+30h] [rbp-61h] BYREF
  char v39; // [rsp+34h] [rbp-5Dh]
  ULONG StartingIndex; // [rsp+38h] [rbp-59h] BYREF
  unsigned int v41; // [rsp+3Ch] [rbp-55h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+40h] [rbp-51h] BYREF
  int v43[2]; // [rsp+50h] [rbp-41h] BYREF
  ULONG *v44; // [rsp+58h] [rbp-39h] BYREF
  __int64 v45; // [rsp+60h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+68h] [rbp-29h] BYREF
  ULONG *p_StartingIndex; // [rsp+88h] [rbp-9h]
  __int64 v48; // [rsp+90h] [rbp-1h]

  v45 = a5;
  v38 = a3;
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  v8 = *(__int64 ***)(a1 + 16);
  v41 = 0;
  v9 = *v8;
  *(_QWORD *)v43 = v9;
  v10 = (ULONG *)v9[2];
LABEL_4:
  v44 = v10;
  do
  {
    RtlInitializeBitMap(&BitMapHeader, v10 + 3992, 0x1Eu);
    StartingIndex = RtlFindClearBits(&BitMapHeader, 1u, 0);
    v12 = StartingIndex;
    if ( StartingIndex != -1 )
      break;
    v11 = (__int64 *)*v9;
    if ( *v9 != *(_QWORD *)(a1 + 16) )
    {
      v10 = (ULONG *)v11[2];
      v9 = (__int64 *)*v9;
      *(_QWORD *)v43 = v11;
      goto LABEL_4;
    }
    v21 = BfsExpandDirectory(a1, (_DWORD)v10, (_DWORD)v9, (unsigned int)&v44, (__int64)v43);
    if ( v21 < 0 )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        StartingIndex = v21;
        p_StartingIndex = &StartingIndex;
        v48 = 4;
        tlgWriteTransfer_EtwWriteTransfer((unsigned int)v21, (unsigned __int8 *)&byte_140016D91, v22, v23, v37, &v46);
      }
      goto LABEL_34;
    }
    v10 = v44;
    RtlInitializeBitMap(&BitMapHeader, v44 + 3992, 0x1Eu);
    ClearBits = RtlFindClearBits(&BitMapHeader, 1u, 0);
    v9 = *(__int64 **)v43;
    v12 = ClearBits;
    StartingIndex = ClearBits;
  }
  while ( ClearBits == -1 );
  v13 = 133LL * v12;
  v14 = &v10[v13];
  RtlSetBits(&BitMapHeader, v12, 1u);
  memset(&v10[v13 + 4], 0, 0x20Cu);
  v14[3] = v38;
  v15 = (const void **)v45;
  v14[2] = a2;
  memmove(&v10[v13 + 7], v15[1], *(unsigned __int16 *)v15);
  if ( a2 == 2 )
  {
    v14[4] = a4;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 0x4000, 1651729986);
    if ( !Pool2 )
    {
      v20 = 0;
      if ( (unsigned int)dword_140019000 <= 3 )
      {
LABEL_30:
        RtlClearBits(&BitMapHeader, StartingIndex, 1u);
        if ( Pool2 )
          ExFreePoolWithTag(Pool2, 0);
        if ( v20 )
        {
          ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 8), 0);
          KeLeaveCriticalRegion();
        }
LABEL_34:
        ExReleasePushLockExclusiveEx(a1, 0);
        KeLeaveCriticalRegion();
        return 0;
      }
      v38 = -1073741801;
LABEL_10:
      v48 = 4;
      p_StartingIndex = (ULONG *)&v38;
      tlgWriteTransfer_EtwWriteTransfer(v16, (unsigned __int8 *)&byte_140016D91, v18, v19, v37, &v46);
      goto LABEL_30;
    }
    v25 = (__int64 *)(a1 + 8);
    v26 = *(_QWORD *)(a1 + 8);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v26, 0);
    v20 = 1;
    v27 = BfsAllocateBlock(*(_QWORD *)(a1 + 8), &v41);
    if ( v27 < 0 )
    {
      v16 = (unsigned int)dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_30;
      v38 = v27;
      goto LABEL_10;
    }
    memset(Pool2 + 1, 0, 0x3FFCu);
    v28 = v41;
    *Pool2 = 1148413506;
    v14[5] = v28;
    v38 = BfsWriteBlock(*v25, v28, Pool2);
    ExFreePoolWithTag(Pool2, 0);
    v31 = v38;
    Pool2 = 0;
    if ( v38 < 0 || (v31 = BfsWriteBlock(*v25, 0, *(void **)(*v25 + 16)), v31 < 0) )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v38 = v31;
        v48 = 4;
        p_StartingIndex = (ULONG *)&v38;
        tlgWriteTransfer_EtwWriteTransfer(
          (unsigned int)dword_140019000,
          (unsigned __int8 *)&byte_140016D91,
          v29,
          v30,
          v37,
          &v46);
      }
LABEL_29:
      BfsFreeBlock(*v25, v41);
      goto LABEL_30;
    }
    v32 = *v25;
    v39 = 1;
    ExReleasePushLockExclusiveEx(v32, 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    v39 = 0;
    v25 = (__int64 *)(a1 + 8);
    v14[4] = 0;
  }
  v33 = BfsWriteBlock(*v25, *((_DWORD *)v9 + 6), v10);
  if ( v33 < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v38 = v33;
      v48 = 4;
      p_StartingIndex = (ULONG *)&v38;
      tlgWriteTransfer_EtwWriteTransfer(
        (unsigned int)dword_140019000,
        (unsigned __int8 *)&byte_140016D91,
        v34,
        v35,
        v37,
        &v46);
    }
    v20 = 0;
    Pool2 = 0;
    if ( !v39 )
      goto LABEL_30;
    goto LABEL_29;
  }
  ExReleasePushLockExclusiveEx(a1, 0);
  KeLeaveCriticalRegion();
  return v14 + 2;
}

```

## disassembly

```asm
0x140011ea8  push    rbp
0x140011eaa  push    rbx
0x140011eab  push    rsi
0x140011eac  push    rdi
0x140011ead  push    r12
0x140011eaf  push    r13
0x140011eb1  push    r14
0x140011eb3  push    r15
0x140011eb5  lea     rbp, [rsp-17h]
0x140011eba  sub     rsp, 0A8h
0x140011ec1  mov     rax, cs:__security_cookie
0x140011ec8  xor     rax, rsp
0x140011ecb  mov     [rbp+4Fh+var_48], rax
0x140011ecf  mov     rax, [rbp+4Fh+arg_20]
0x140011ed3  mov     edi, r9d
0x140011ed6  mov     [rbp+4Fh+var_80], rax
0x140011eda  mov     esi, edx
0x140011edc  xor     eax, eax
0x140011ede  mov     [rbp+4Fh+var_B0], r8d
0x140011ee2  mov     qword ptr [rbp+4Fh+BitMapHeader+4], rax
0x140011ee6  mov     r14, rcx
0x140011ee9  mov     [rbp-51h], rax
0x140011eed  call    cs:__imp_KeEnterCriticalRegion
0x140011ef4  nop     dword ptr [rax+rax+00h]
0x140011ef9  xor     edx, edx
0x140011efb  mov     rcx, r14
0x140011efe  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011f05  nop     dword ptr [rax+rax+00h]
0x140011f0a  mov     rax, [r14+10h]
0x140011f0e  mov     ebx, 1
0x140011f13  mov     [rbp+4Fh+var_A4], 0
0x140011f1a  mov     r12, [rax]
0x140011f1d  lea     r15d, [rbx+1Dh]
0x140011f21  mov     qword ptr [rbp+4Fh+var_90], r12
0x140011f25  mov     r13, [r12+10h]
0x140011f2a  jmp     short loc_140011F45
0x140011f2c  mov     rax, [r12]
0x140011f30  cmp     rax, [r14+10h]
0x140011f34  jz      loc_140012052
0x140011f3a  mov     r13, [rax+10h]
0x140011f3e  mov     r12, rax
0x140011f41  mov     qword ptr [rbp+4Fh+var_90], rax
0x140011f45  mov     [rbp+4Fh+var_88], r13
0x140011f49  mov     r8d, r15d; SizeOfBitMap
0x140011f4c  lea     rdx, [r13+3E60h]; BitMapBuffer
0x140011f53  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011f57  call    cs:__imp_RtlInitializeBitMap
0x140011f5e  nop     dword ptr [rax+rax+00h]
0x140011f63  xor     r8d, r8d; HintIndex
0x140011f66  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011f6a  mov     edx, ebx; NumberToFind
0x140011f6c  call    cs:__imp_RtlFindClearBits
0x140011f73  nop     dword ptr [rax+rax+00h]
0x140011f78  mov     [rbp+4Fh+StartingIndex], eax
0x140011f7b  mov     ecx, eax
0x140011f7d  cmp     eax, 0FFFFFFFFh
0x140011f80  jz      short loc_140011F2C
0x140011f82  mov     eax, ecx
0x140011f84  mov     edx, ecx; StartingIndex
0x140011f86  imul    rbx, rax, 214h
0x140011f8d  mov     r8d, 1; NumberToSet
0x140011f93  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011f97  lea     r15, [rbx+r13]
0x140011f9b  call    cs:__imp_RtlSetBits
0x140011fa2  nop     dword ptr [rax+rax+00h]
0x140011fa7  lea     rcx, [r13+10h]
0x140011fab  xor     edx, edx; Val
0x140011fad  add     rcx, rbx; void *
0x140011fb0  mov     r8d, 20Ch; Size
0x140011fb6  call    memset
0x140011fbb  mov     eax, [rbp+4Fh+var_B0]
0x140011fbe  lea     rcx, [r15+1Ch]; void *
0x140011fc2  mov     [r15+0Ch], eax
0x140011fc6  mov     rax, [rbp+4Fh+var_80]
0x140011fca  mov     [r15+8], esi
0x140011fce  movzx   r8d, word ptr [rax]; Size
0x140011fd2  mov     rdx, [rax+8]; Src
0x140011fd6  call    memmove
0x140011fdb  cmp     esi, 2
0x140011fde  jnz     loc_1400121FE
0x140011fe4  mov     edx, 4000h
0x140011fe9  mov     [r15+10h], edi
0x140011fed  mov     ecx, 100h
0x140011ff2  mov     r8d, 62736642h
0x140011ff8  call    cs:__imp_ExAllocatePool2
0x140011fff  nop     dword ptr [rax+rax+00h]
0x140012004  mov     rsi, rax
0x140012007  test    rax, rax
0x14001200a  jnz     loc_1400120F9
0x140012010  mov     eax, cs:dword_140019000
0x140012016  xor     bl, bl
0x140012018  cmp     eax, 3
0x14001201b  jbe     loc_14001226D
0x140012021  mov     [rbp+4Fh+var_B0], 0C0000017h
0x140012028  lea     rax, [rbp+4Fh+var_B0]
0x14001202c  mov     [rbp+4Fh+var_50], 4
0x140012034  mov     [rbp+4Fh+var_58], rax
0x140012038  lea     rdx, byte_140016D91; int
0x14001203f  lea     rax, [rbp+4Fh+var_78]
0x140012043  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140012048  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001204d  jmp     loc_14001226D
0x140012052  lea     rax, [rbp+4Fh+var_90]
0x140012056  mov     r8, r12
0x140012059  lea     r9, [rbp+4Fh+var_88]
0x14001205d  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x140012062  mov     rdx, r13
0x140012065  mov     rcx, r14
0x140012068  call    BfsExpandDirectory
0x14001206d  mov     ecx, eax; int
0x14001206f  test    eax, eax
0x140012071  js      short loc_1400120BD
0x140012073  mov     r13, [rbp+4Fh+var_88]
0x140012077  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x14001207b  mov     r8d, r15d; SizeOfBitMap
0x14001207e  lea     rdx, [r13+3E60h]; BitMapBuffer
0x140012085  call    cs:__imp_RtlInitializeBitMap
0x14001208c  nop     dword ptr [rax+rax+00h]
0x140012091  xor     r8d, r8d; HintIndex
0x140012094  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140012098  mov     edx, ebx; NumberToFind
0x14001209a  call    cs:__imp_RtlFindClearBits
0x1400120a1  nop     dword ptr [rax+rax+00h]
0x1400120a6  mov     r12, qword ptr [rbp+4Fh+var_90]
0x1400120aa  mov     ecx, eax
0x1400120ac  mov     [rbp+4Fh+StartingIndex], eax
0x1400120af  cmp     eax, 0FFFFFFFFh
0x1400120b2  jz      loc_140011F49
0x1400120b8  jmp     loc_140011F82
0x1400120bd  mov     eax, cs:dword_140019000
0x1400120c3  cmp     eax, 3
0x1400120c6  jbe     loc_1400122BE
0x1400120cc  lea     rax, [rbp+4Fh+StartingIndex]
0x1400120d0  mov     [rbp+4Fh+StartingIndex], ecx
0x1400120d3  mov     [rbp+4Fh+var_58], rax
0x1400120d7  lea     rdx, byte_140016D91; int
0x1400120de  lea     rax, [rbp+4Fh+var_78]
0x1400120e2  mov     [rbp+4Fh+var_50], 4
0x1400120ea  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1400120ef  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400120f4  jmp     loc_1400122BE
0x1400120f9  lea     rdi, [r14+8]
0x1400120fd  mov     rbx, [rdi]
0x140012100  call    cs:__imp_KeEnterCriticalRegion
0x140012107  nop     dword ptr [rax+rax+00h]
0x14001210c  xor     edx, edx
0x14001210e  mov     rcx, rbx
0x140012111  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012118  nop     dword ptr [rax+rax+00h]
0x14001211d  mov     rcx, [rdi]
0x140012120  lea     rdx, [rbp+4Fh+var_A4]
0x140012124  mov     bl, 1
0x140012126  call    BfsAllocateBlock
0x14001212b  test    eax, eax
0x14001212d  jns     short loc_140012146
0x14001212f  mov     ecx, cs:dword_140019000
0x140012135  cmp     ecx, 3
0x140012138  jbe     loc_14001226D
0x14001213e  mov     [rbp+4Fh+var_B0], eax
0x140012141  jmp     loc_140012028
0x140012146  lea     rcx, [rsi+4]; void *
0x14001214a  xor     edx, edx; Val
0x14001214c  mov     r8d, 3FFCh; Size
0x140012152  call    memset
0x140012157  mov     eax, [rbp+4Fh+var_A4]
0x14001215a  mov     r8, rsi
0x14001215d  mov     dword ptr [rsi], 44736642h
0x140012163  mov     edx, eax
0x140012165  mov     [r15+14h], eax
0x140012169  mov     rcx, [rdi]
0x14001216c  call    BfsWriteBlock
0x140012171  xor     edx, edx; Tag
0x140012173  mov     [rbp+4Fh+var_B0], eax
0x140012176  mov     rcx, rsi; P
0x140012179  call    cs:__imp_ExFreePoolWithTag
0x140012180  nop     dword ptr [rax+rax+00h]
0x140012185  mov     eax, [rbp+4Fh+var_B0]
0x140012188  xor     esi, esi
0x14001218a  test    eax, eax
0x14001218c  jns     short loc_1400121CA
0x14001218e  mov     ecx, cs:dword_140019000; int
0x140012194  cmp     ecx, 3
0x140012197  jbe     loc_140012262
0x14001219d  mov     [rbp+4Fh+var_B0], eax
0x1400121a0  lea     rdx, byte_140016D91; int
0x1400121a7  lea     rax, [rbp+4Fh+var_B0]
0x1400121ab  mov     [rbp+4Fh+var_50], 4
0x1400121b3  mov     [rbp+4Fh+var_58], rax
0x1400121b7  lea     rax, [rbp+4Fh+var_78]
0x1400121bb  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1400121c0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400121c5  jmp     loc_140012262
0x1400121ca  mov     rcx, [rdi]
0x1400121cd  xor     edx, edx
0x1400121cf  mov     r8, [rcx+10h]
0x1400121d3  call    BfsWriteBlock
0x1400121d8  test    eax, eax
0x1400121da  js      short loc_14001218E
0x1400121dc  mov     rcx, [rdi]
0x1400121df  xor     edx, edx
0x1400121e1  mov     [rbp+4Fh+var_AC], bl
0x1400121e4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400121eb  nop     dword ptr [rax+rax+00h]
0x1400121f0  call    cs:__imp_KeLeaveCriticalRegion
0x1400121f7  nop     dword ptr [rax+rax+00h]
0x1400121fc  jmp     short loc_14001220E
0x1400121fe  mov     [rbp+4Fh+var_AC], 0
0x140012202  lea     rdi, [r14+8]
0x140012206  mov     dword ptr [r15+10h], 0
0x14001220e  mov     edx, [r12+18h]
0x140012213  mov     r8, r13
0x140012216  mov     rcx, [rdi]
0x140012219  call    BfsWriteBlock
0x14001221e  test    eax, eax
0x140012220  jns     loc_1400122DF
0x140012226  mov     ecx, cs:dword_140019000; int
0x14001222c  cmp     ecx, 3
0x14001222f  jbe     short loc_140012259
0x140012231  mov     [rbp+4Fh+var_B0], eax
0x140012234  lea     rdx, byte_140016D91; int
0x14001223b  lea     rax, [rbp+4Fh+var_B0]
0x14001223f  mov     [rbp+4Fh+var_50], 4
0x140012247  mov     [rbp+4Fh+var_58], rax
0x14001224b  lea     rax, [rbp+4Fh+var_78]
0x14001224f  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140012254  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012259  xor     bl, bl
0x14001225b  xor     esi, esi
0x14001225d  cmp     [rbp+4Fh+var_AC], bl
0x140012260  jz      short loc_14001226D
0x140012262  mov     edx, [rbp+4Fh+var_A4]
0x140012265  mov     rcx, [rdi]
0x140012268  call    BfsFreeBlock
0x14001226d  mov     edx, [rbp+4Fh+StartingIndex]; StartingIndex
0x140012270  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140012274  mov     r8d, 1; NumberToClear
0x14001227a  call    cs:__imp_RtlClearBits
0x140012281  nop     dword ptr [rax+rax+00h]
0x140012286  test    rsi, rsi
0x140012289  jz      short loc_14001229C
0x14001228b  xor     edx, edx; Tag
0x14001228d  mov     rcx, rsi; P
0x140012290  call    cs:__imp_ExFreePoolWithTag
0x140012297  nop     dword ptr [rax+rax+00h]
0x14001229c  test    bl, bl
0x14001229e  jz      short loc_1400122BE
0x1400122a0  mov     rcx, [r14+8]
0x1400122a4  xor     edx, edx
0x1400122a6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400122ad  nop     dword ptr [rax+rax+00h]
0x1400122b2  call    cs:__imp_KeLeaveCriticalRegion
0x1400122b9  nop     dword ptr [rax+rax+00h]
0x1400122be  xor     edx, edx
0x1400122c0  mov     rcx, r14
0x1400122c3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400122ca  nop     dword ptr [rax+rax+00h]
0x1400122cf  call    cs:__imp_KeLeaveCriticalRegion
0x1400122d6  nop     dword ptr [rax+rax+00h]
0x1400122db  xor     eax, eax
0x1400122dd  jmp     short loc_140012300
0x1400122df  xor     edx, edx
0x1400122e1  mov     rcx, r14
0x1400122e4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400122eb  nop     dword ptr [rax+rax+00h]
0x1400122f0  call    cs:__imp_KeLeaveCriticalRegion
0x1400122f7  nop     dword ptr [rax+rax+00h]
0x1400122fc  lea     rax, [r15+8]
0x140012300  mov     rcx, [rbp+4Fh+var_48]
0x140012304  xor     rcx, rsp; StackCookie
0x140012307  call    __security_check_cookie
0x14001230c  add     rsp, 0A8h
0x140012313  pop     r15
0x140012315  pop     r14
0x140012317  pop     r13
0x140012319  pop     r12
0x14001231b  pop     rdi
0x14001231c  pop     rsi
0x14001231d  pop     rbx
0x14001231e  pop     rbp
0x14001231f  retn
```
