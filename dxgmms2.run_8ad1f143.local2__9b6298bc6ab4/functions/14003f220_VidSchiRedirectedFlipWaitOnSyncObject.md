# VidSchiRedirectedFlipWaitOnSyncObject

- ea: `0x14003f220`
- end: `0x14003f59b`
- name: `VidSchiRedirectedFlipWaitOnSyncObject`
- size: `891`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, void *Src)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14003fe60`

## callees

- `0x1400045ec`
- `0x1400074a0`
- `0x14001ca80`
- `0x14001f7fc`
- `0x140020aa0`
- `0x140021c90`
- `0x140032d84`
- `0x14003f220`
- `0x140058760`
- `0x1400587c0`
- `0x1400f8aa0`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003f42f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003f42f`
- `watchdog!WdLogSingleEntry3` at `0x14003f528`
- `watchdog!WdLogSingleEntry3` at `0x14003f528`
- `watchdog!WdLogSingleEntry0` at `0x14003f3e1`
- `watchdog!WdLogSingleEntry0` at `0x14003f446`
- `watchdog!WdLogSingleEntry0` at `0x14003f3e1`
- `watchdog!WdLogSingleEntry0` at `0x14003f446`

## string_xrefs

- `0x14003f3f2`: `Synchronization object already has LONG_MAX reference pending, can't reference more.\n`

## pseudocode

```c
__int64 __fastcall VidSchiRedirectedFlipWaitOnSyncObject(struct _VIDSCH_GLOBAL *a1, char *Src, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // r13d
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // r14
  __int64 v12; // rdx
  void (__fastcall *v13)(_QWORD, __int64, __int64); // rax
  unsigned int v14; // edx
  struct _VIDSCH_GLOBAL *v15; // rcx
  unsigned __int64 v16; // r8
  bool v17; // cf
  _DWORD *v18; // rax
  __int64 v19; // r8
  int v20; // ecx
  int v21; // r8d
  _QWORD *v22; // rax
  _QWORD *v23; // r14
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // r10
  char *v27; // rdi
  char **v28; // rcx
  unsigned int *v29; // rax
  __int64 v30; // r10
  struct _VIDSCH_GLOBAL *v32; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v33[2]; // [rsp+58h] [rbp-31h] BYREF
  char v34; // [rsp+68h] [rbp-21h]
  int v35; // [rsp+6Ch] [rbp-1Dh]
  _QWORD v36[4]; // [rsp+70h] [rbp-19h] BYREF
  __int16 v37; // [rsp+90h] [rbp+7h]

  v5 = 0;
  v9 = *(_QWORD *)&Src[8 * *((_DWORD *)Src + 151) * (*((_DWORD *)Src + 152) + 28) + 656];
  if ( v9 )
    v10 = *(_QWORD *)(*(_QWORD *)(v9 + 8) + 32LL);
  else
    v10 = 0;
  v11 = *((unsigned int *)Src + 29);
  if ( (*(_DWORD *)Src & 0x1000000) != 0 && (_DWORD)v11 != -1 )
  {
    v12 = *(unsigned int *)(*((_QWORD *)a1 + v11 + 441) + 44488LL);
    if ( (_DWORD)v12 != -1 )
    {
      v13 = (void (__fastcall *)(_QWORD, __int64, __int64))*((_QWORD *)a1 + 423);
      if ( v13 )
        v13(*((_QWORD *)a1 + 431), v12, 0xFFFFFFFFLL);
    }
  }
  if ( (*a4 & 0x1000) != 0 && (*a4 & 0xC00) != 0x400 && (_DWORD)v11 != -1 && (*(_DWORD *)Src & 0x1040000) == 0x1040000 )
  {
    _InterlockedAdd((volatile signed __int32 *)a1 + 220, 1u);
    IncrementNumberOfQueuedFlipPerSource(a1, v11);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 1836), 1u);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 4 * v11 + 1772), 1u);
    if ( (*(_DWORD *)(v10 + 56) & 2) != 0 || *((int *)Src + 30) >= 4 || *((_BYTE *)a1 + 164) )
      VidSchIsVSyncEnabled(v15, v14);
  }
  v36[0] = (char *)a1 + 2096;
  v37 = 0;
  AcquireSpinLock::Acquire((AcquireSpinLock *)v36);
  v33[1] = v33;
  v33[0] = v33;
  v32 = a1;
  v34 = 0;
  v35 = 1;
  if ( *(_BYTE *)(a3 + 29) )
    goto LABEL_23;
  v16 = *((_QWORD *)Src + 59);
  if ( *(_DWORD *)(a3 + 48) == 6 )
  {
    v17 = *(_QWORD *)(*(unsigned int *)(a3 + 80) + *(_QWORD *)(*(_QWORD *)(a3 + 64) + 184LL)) < v16;
  }
  else
  {
    v18 = *(_DWORD **)(a3 + 72);
    if ( !*(_BYTE *)(a3 + 30) )
    {
      if ( *v18 - (int)v16 >= 0 )
        goto LABEL_23;
      goto LABEL_26;
    }
    v17 = *(_QWORD *)v18 < v16;
  }
  if ( !v17 )
  {
LABEL_23:
    if ( *(_DWORD *)(a3 + 48) == 6 )
    {
      v19 = *(_QWORD *)(*(unsigned int *)(a3 + 80) + *(_QWORD *)(*(_QWORD *)(a3 + 64) + 184LL));
    }
    else
    {
      v29 = *(unsigned int **)(a3 + 72);
      if ( *(_BYTE *)(a3 + 30) )
        v19 = *(_QWORD *)v29;
      else
        v19 = *v29;
    }
    WdLogSingleEntry3(4, a3, v19, *((_QWORD *)Src + 59));
    WdLogGlobalForLineNumber = 13770;
    VidSchiAcquirePrivateDataReference(a1, (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(Src + 600));
    v30 = *((_QWORD *)Src + 4);
    if ( v30 )
      _InterlockedAdd((volatile signed __int32 *)(v30 + 12), 1u);
    VidSchiSubmitPresentHistoryToken((struct HwQueueStagingList *)&v32, 0, Src, 0, (__int64)a1);
    goto LABEL_41;
  }
LABEL_26:
  if ( *(_DWORD *)(a3 + 36) == 0x7FFFFFFF )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 13808;
    DxgkLogInternalTriageEvent(
      v20,
      0x40000,
      v21,
      (unsigned int)L"Synchronization object already has LONG_MAX reference pending, can't reference more.\n",
      13808,
      0,
      0,
      0);
    v5 = -1073741823;
  }
  else
  {
    v22 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)a1 + 1024));
    v23 = v22;
    if ( v22 )
    {
      v22[1] = a3;
      v22[2] = *((_QWORD *)Src + 59);
      memmove(v22 + 5, Src, *((unsigned int *)Src + 139));
      *((_DWORD *)Src + 84) = 0;
      *((_DWORD *)Src + 154) = 0;
      VidSchiAcquirePrivateDataReference(a1, (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(v23 + 80));
      v26 = v23[9];
      if ( v26 )
        _InterlockedAdd((volatile signed __int32 *)(v26 + 12), 1u);
      v27 = (char *)a1 + 1000;
      v28 = (char **)*((_QWORD *)v27 + 1);
      if ( *v28 != v27 )
        __fastfail(3u);
      v23[3] = v27;
      v23[4] = v28;
      *v28 = (char *)(v23 + 3);
      *((_QWORD *)v27 + 1) = v23 + 3;
      ++*(_DWORD *)(a3 + 44);
      _InterlockedAdd((volatile signed __int32 *)(a3 + 36), 1u);
    }
    else
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 13820;
      DxgkLogInternalTriageEvent(
        v24,
        0x40000,
        v25,
        (unsigned int)L"Failed to allocate VIDSCH_SYNCOBJ_PHT_DATA",
        13820,
        0,
        0,
        0);
      v5 = -1073741801;
    }
  }
LABEL_41:
  HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v32);
  AcquireSpinLock::Release((AcquireSpinLock *)v36);
  return v5;
}

```

## disassembly

```asm
0x14003f220  push    rbp
0x14003f222  push    rbx
0x14003f223  push    rsi
0x14003f224  push    rdi
0x14003f225  push    r12
0x14003f227  push    r13
0x14003f229  push    r14
0x14003f22b  push    r15
0x14003f22d  lea     rbp, [rsp-1Fh]
0x14003f232  sub     rsp, 0A8h
0x14003f239  mov     rdi, rcx
0x14003f23c  xor     r13d, r13d
0x14003f23f  lea     rcx, [rdx+258h]
0x14003f246  mov     r12, r9
0x14003f249  mov     eax, [rcx+8]
0x14003f24c  mov     rbx, r8
0x14003f24f  add     eax, 1Ch
0x14003f252  mov     rsi, rdx
0x14003f255  imul    eax, [rcx+4]
0x14003f259  shl     eax, 3
0x14003f25c  mov     rax, [rax+rcx+38h]
0x14003f261  test    rax, rax
0x14003f264  jnz     short loc_14003F26B
0x14003f266  xor     r15d, r15d
0x14003f269  jmp     short loc_14003F273
0x14003f26b  mov     rax, [rax+8]
0x14003f26f  mov     r15, [rax+20h]
0x14003f273  mov     r14d, [rdx+74h]
0x14003f277  or      r8d, 0FFFFFFFFh
0x14003f27b  test    dword ptr [rdx], 1000000h
0x14003f281  jz      short loc_14003F2B7
0x14003f283  cmp     r14d, r8d
0x14003f286  jz      short loc_14003F2B7
0x14003f288  mov     rcx, [rdi+r14*8+0DC8h]
0x14003f290  mov     edx, [rcx+0ADC8h]
0x14003f296  cmp     edx, r8d
0x14003f299  jz      short loc_14003F2B7
0x14003f29b  mov     rax, [rdi+0D38h]
0x14003f2a2  test    rax, rax
0x14003f2a5  jz      short loc_14003F2B7
0x14003f2a7  mov     rcx, [rdi+0D78h]
0x14003f2ae  call    _guard_dispatch_icall
0x14003f2b3  or      r8d, 0FFFFFFFFh
0x14003f2b7  mov     eax, [r12]
0x14003f2bb  mov     r12d, 1
0x14003f2c1  bt      eax, 0Ch
0x14003f2c5  jnb     short loc_14003F325
0x14003f2c7  and     eax, 0C00h
0x14003f2cc  cmp     eax, 400h
0x14003f2d1  jz      short loc_14003F325
0x14003f2d3  cmp     r14d, r8d
0x14003f2d6  jz      short loc_14003F325
0x14003f2d8  mov     eax, [rsi]
0x14003f2da  mov     ecx, 1040000h
0x14003f2df  and     eax, ecx
0x14003f2e1  cmp     eax, ecx
0x14003f2e3  jnz     short loc_14003F325
0x14003f2e5  lock add [rdi+370h], r12d
0x14003f2ed  mov     edx, r14d; unsigned int
0x14003f2f0  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x14003f2f3  call    ?IncrementNumberOfQueuedFlipPerSource@@YAXPEAU_VIDSCH_GLOBAL@@I@Z; IncrementNumberOfQueuedFlipPerSource(_VIDSCH_GLOBAL *,uint)
0x14003f2f8  lock add [r15+72Ch], r12d
0x14003f300  lock add [r15+r14*4+6ECh], r12d
0x14003f309  mov     eax, [r15+38h]
0x14003f30d  test    al, 2
0x14003f30f  jnz     short loc_14003F320
0x14003f311  cmp     dword ptr [rsi+78h], 4
0x14003f315  jge     short loc_14003F320
0x14003f317  cmp     [rdi+0A4h], r13b
0x14003f31e  jz      short loc_14003F325
0x14003f320  call    VidSchIsVSyncEnabled
0x14003f325  lea     rax, [rdi+830h]
0x14003f32c  xor     r15d, r15d
0x14003f32f  lea     rcx, [rbp+57h+var_70]; this
0x14003f333  mov     [rbp+57h+var_70], rax
0x14003f337  mov     [rbp+57h+var_50], r15w
0x14003f33c  call    ?Acquire@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Acquire(void)
0x14003f341  lea     rax, [rbp+57h+var_88]
0x14003f345  xorps   xmm0, xmm0
0x14003f348  movups  [rbp+57h+var_88], xmm0
0x14003f34c  mov     qword ptr [rbp+57h+var_88+8], rax
0x14003f350  lea     rax, [rbp+57h+var_88]
0x14003f354  mov     qword ptr [rbp+57h+var_88], rax
0x14003f358  mov     [rbp+57h+var_90], rdi
0x14003f35c  mov     [rbp+57h+var_78], r15b
0x14003f360  mov     [rbp+57h+var_74], r12d
0x14003f364  cmp     [rbx+1Dh], r15b
0x14003f368  jnz     short loc_14003F3A5
0x14003f36a  cmp     dword ptr [rbx+30h], 6
0x14003f36e  mov     r8, [rsi+1D8h]
0x14003f375  jnz     short loc_14003F38E
0x14003f377  mov     rax, [rbx+40h]
0x14003f37b  mov     edx, [rbx+50h]
0x14003f37e  mov     rcx, [rax+0B8h]
0x14003f385  mov     rax, [rdx+rcx]
0x14003f389  cmp     rax, r8
0x14003f38c  jmp     short loc_14003F39E
0x14003f38e  mov     rax, [rbx+48h]
0x14003f392  cmp     [rbx+1Eh], r15b
0x14003f396  jz      short loc_14003F3CD
0x14003f398  mov     rcx, [rax]
0x14003f39b  cmp     rcx, r8
0x14003f39e  setnb   al
0x14003f3a1  test    al, al
0x14003f3a3  jz      short loc_14003F3D4
0x14003f3a5  cmp     dword ptr [rbx+30h], 6
0x14003f3a9  mov     r9, [rsi+1D8h]
0x14003f3b0  jnz     loc_14003F50E
0x14003f3b6  mov     rax, [rbx+40h]
0x14003f3ba  mov     edx, [rbx+50h]
0x14003f3bd  mov     rcx, [rax+0B8h]
0x14003f3c4  mov     r8, [rdx+rcx]
0x14003f3c8  jmp     loc_14003F520
0x14003f3cd  mov     edx, [rax]
0x14003f3cf  cmp     edx, r8d
0x14003f3d2  jns     short loc_14003F3A5
0x14003f3d4  mov     eax, [rbx+24h]
0x14003f3d7  cmp     eax, 7FFFFFFFh
0x14003f3dc  jnz     short loc_14003F428
0x14003f3de  mov     ecx, r12d
0x14003f3e1  call    cs:__imp_WdLogSingleEntry0
0x14003f3e8  nop     dword ptr [rax+rax+00h]
0x14003f3ed  mov     [rsp+0E0h+var_A8], r15
0x14003f3f2  lea     r9, aSynchronizatio; "Synchronization object already has LONG"...
0x14003f3f9  mov     eax, 35F0h
0x14003f3fe  mov     [rsp+0E0h+var_B0], r15
0x14003f403  mov     [rsp+0E0h+var_B8], r15
0x14003f408  mov     edx, 40000h
0x14003f40d  mov     cs:WdLogGlobalForLineNumber, eax
0x14003f413  mov     [rsp+0E0h+var_C0], rax
0x14003f418  call    DxgkLogInternalTriageEvent
0x14003f41d  mov     r13d, 0C0000001h
0x14003f423  jmp     loc_14003F571
0x14003f428  lea     rcx, [rdi+400h]; Lookaside
0x14003f42f  call    cs:__imp_ExAllocateFromLookasideListEx
0x14003f436  nop     dword ptr [rax+rax+00h]
0x14003f43b  mov     r14, rax
0x14003f43e  test    rax, rax
0x14003f441  jnz     short loc_14003F48D
0x14003f443  mov     ecx, r12d
0x14003f446  call    cs:__imp_WdLogSingleEntry0
0x14003f44d  nop     dword ptr [rax+rax+00h]
0x14003f452  mov     [rsp+0E0h+var_A8], r15
0x14003f457  lea     r9, aFailedToAlloca_100; "Failed to allocate VIDSCH_SYNCOBJ_PHT_D"...
0x14003f45e  mov     eax, 35FCh
0x14003f463  mov     [rsp+0E0h+var_B0], r15
0x14003f468  mov     [rsp+0E0h+var_B8], r15
0x14003f46d  mov     edx, 40000h
0x14003f472  mov     cs:WdLogGlobalForLineNumber, eax
0x14003f478  mov     [rsp+0E0h+var_C0], rax
0x14003f47d  call    DxgkLogInternalTriageEvent
0x14003f482  mov     r13d, 0C0000017h
0x14003f488  jmp     loc_14003F571
0x14003f48d  mov     [rax+8], rbx
0x14003f491  lea     rcx, [r14+28h]; void *
0x14003f495  mov     rax, [rsi+1D8h]
0x14003f49c  mov     rdx, rsi; Src
0x14003f49f  mov     [r14+10h], rax
0x14003f4a3  mov     r8d, [rsi+22Ch]; Size
0x14003f4aa  call    memmove
0x14003f4af  lea     rdx, [r14+280h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x14003f4b6  mov     [rsi+150h], r15d
0x14003f4bd  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x14003f4c0  mov     [rsi+268h], r15d
0x14003f4c7  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x14003f4cc  mov     r10, [r14+48h]
0x14003f4d0  test    r10, r10
0x14003f4d3  jz      short loc_14003F4DA
0x14003f4d5  lock add [r10+0Ch], r12d
0x14003f4da  add     rdi, 3E8h
0x14003f4e1  mov     rcx, [rdi+8]
0x14003f4e5  cmp     [rcx], rdi
0x14003f4e8  jz      short loc_14003F4F1
0x14003f4ea  mov     ecx, 3
0x14003f4ef  int     29h; Win8: RtlFailFast(ecx)
0x14003f4f1  lea     rax, [r14+18h]
0x14003f4f5  mov     [rax], rdi
0x14003f4f8  mov     [rax+8], rcx
0x14003f4fc  mov     [rcx], rax
0x14003f4ff  mov     [rdi+8], rax
0x14003f503  add     [rbx+2Ch], r12d
0x14003f507  lock add [rbx+24h], r12d
0x14003f50c  jmp     short loc_14003F571
0x14003f50e  mov     rax, [rbx+48h]
0x14003f512  cmp     [rbx+1Eh], r15b
0x14003f516  jz      short loc_14003F51D
0x14003f518  mov     r8, [rax]
0x14003f51b  jmp     short loc_14003F520
0x14003f51d  mov     r8d, [rax]
0x14003f520  mov     rdx, rbx
0x14003f523  mov     ecx, 4
0x14003f528  call    cs:__imp_WdLogSingleEntry3
0x14003f52f  nop     dword ptr [rax+rax+00h]
0x14003f534  lea     rdx, [rsi+258h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x14003f53b  mov     cs:WdLogGlobalForLineNumber, 35CAh
0x14003f545  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x14003f548  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x14003f54d  mov     r10, [rsi+20h]
0x14003f551  test    r10, r10
0x14003f554  jz      short loc_14003F55B
0x14003f556  lock add [r10+0Ch], r12d
0x14003f55b  mov     r9, r15
0x14003f55e  mov     [rsp+0E0h+var_C0], rdi
0x14003f563  mov     r8, rsi
0x14003f566  lea     rcx, [rbp+57h+var_90]
0x14003f56a  xor     edx, edx
0x14003f56c  call    VidSchiSubmitPresentHistoryToken
0x14003f571  lea     rcx, [rbp+57h+var_90]; this
0x14003f575  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x14003f57a  lea     rcx, [rbp+57h+var_70]; this
0x14003f57e  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x14003f583  mov     eax, r13d
0x14003f586  add     rsp, 0A8h
0x14003f58d  pop     r15
0x14003f58f  pop     r14
0x14003f591  pop     r13
0x14003f593  pop     r12
0x14003f595  pop     rdi
0x14003f596  pop     rsi
0x14003f597  pop     rbx
0x14003f598  pop     rbp
0x14003f599  retn
```
