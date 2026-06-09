# InactiveCallCleanUp

- ea: `0x14000f2ec`
- end: `0x14000f692`
- name: `InactiveCallCleanUp`
- size: `934`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400106b4`
- `0x1400109d0`
- `0x14001b830`

## callees

- `0x1400013f0`
- `0x1400021c0`
- `0x140004c00`
- `0x14000f2ec`
- `0x14000f698`
- `0x14000f7c4`
- `0x14001070c`
- `0x140018b24`
- `0x14001ac30`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f587`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f587`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f34a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f405`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f418`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f4d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f5b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f34a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f405`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f418`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f4d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f5b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f4bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f4bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f328`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f37d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f3c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f428`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f466`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f328`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f37d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f3c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f428`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f466`
- `NDIS!NdisFreeNetBufferList` at `0x14000f4a9`
- `NDIS!NdisFreeNetBufferList` at `0x14000f575`
- `NDIS!NdisFreeNetBufferList` at `0x14000f4a9`
- `NDIS!NdisFreeNetBufferList` at `0x14000f575`
- `NDIS!NdisCmCloseCallComplete` at `0x14000f644`
- `NDIS!NdisCmCloseCallComplete` at `0x14000f644`
- `NDIS!NdisMCmDeleteVc` at `0x14000f65d`
- `NDIS!NdisMCmDeleteVc` at `0x14000f65d`

## pseudocode

```c
void __fastcall InactiveCallCleanUp(__int64 *a1)
{
  __int64 v1; // r13
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 v5; // rsi
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 *v9; // rdx
  __int64 **v10; // rax
  KIRQL v11; // al
  __int64 v12; // rdx
  void **v13; // r14
  void *v14; // rbx
  void **v15; // rax
  _QWORD *v16; // r14
  _QWORD *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  _QWORD **v20; // r14
  _QWORD *v21; // rbx
  _QWORD *v22; // rax
  struct _NET_BUFFER_LIST *v23; // rcx
  int v24; // ebx
  int v25; // eax
  int v26; // eax

  v1 = a1[3];
  CallSetupComplete(a1);
  v3 = *((unsigned __int16 *)a1 + 28);
  *((_WORD *)a1 + 28) = 0;
  if ( (_WORD)v3 )
  {
    v4 = a1[3];
    if ( (unsigned __int16)v3 <= *(_WORD *)(v4 + 96) )
    {
      *(_BYTE *)(v4 + 112) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 104));
      *(_QWORD *)(*(_QWORD *)(v4 + 88) + 8 * v3 - 8) = 0;
      ++*(_DWORD *)(v4 + 100);
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 104), *(_BYTE *)(v4 + 112));
    }
  }
  v5 = a1[4];
  if ( v5 && (unsigned int)ClearFlags((char *)a1 + 60, 0x2000000) )
  {
    *(_BYTE *)(v5 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 32));
    v6 = a1 + 12;
    v7 = a1[12];
    if ( *(__int64 **)(v7 + 8) != a1 + 12 )
      goto LABEL_35;
    v8 = (_QWORD *)a1[13];
    if ( (_QWORD *)*v8 != v6
      || (*v8 = v7,
          *(_QWORD *)(v7 + 8) = v8,
          a1[13] = (__int64)(a1 + 12),
          *v6 = v6,
          *(_BYTE *)(v5 + 368) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 360)),
          v9 = (__int64 *)*a1,
          *(__int64 **)(*a1 + 8) != a1)
      || (v10 = (__int64 **)a1[1], *v10 != a1) )
    {
LABEL_35:
      __fastfail(3u);
    }
    *v10 = v9;
    v9[1] = (__int64)v10;
    a1[1] = (__int64)a1;
    *a1 = (__int64)a1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 360), *(_BYTE *)(v5 + 368));
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 32), *(_BYTE *)(v5 + 40));
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 5);
    v12 = a1[34];
    *((_BYTE *)a1 + 48) = v11;
    if ( v12 )
    {
      RemoveTqi(*(_QWORD *)(v5 + 304), v12, 2);
      a1[34] = 0;
    }
    *((_BYTE *)a1 + 472) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 58);
    v13 = (void **)(a1 + 55);
    while ( 1 )
    {
      v14 = *v13;
      if ( *v13 == v13 )
        break;
      if ( *((void ***)v14 + 1) != v13 )
        goto LABEL_35;
      v15 = *(void ***)v14;
      if ( *(void **)(*(_QWORD *)v14 + 8LL) != v14 )
        goto LABEL_35;
      *v13 = v15;
      v15[1] = v13;
      NdisFreeNetBufferList(*((PNET_BUFFER_LIST *)v14 + 9));
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v1 + 1216), v14);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 58, *((_BYTE *)a1 + 472));
    v16 = a1 + 29;
    while ( 1 )
    {
      v17 = (_QWORD *)*v16;
      if ( (_QWORD *)*v16 == v16 )
        break;
      if ( (_QWORD *)v17[1] != v16 )
        goto LABEL_35;
      v18 = *v17;
      if ( *(_QWORD **)(*v17 + 8LL) != v17 )
        goto LABEL_35;
      *v16 = v18;
      *(_QWORD *)(v18 + 8) = v16;
      v19 = v17[5];
      v17[1] = v17;
      *v17 = v17;
      RemoveTqi(*(_QWORD *)(v5 + 304), v19, 2);
      *((_DWORD *)v17 + 18) = -1073741823;
      DereferencePayloadSent(v17);
    }
    v20 = (_QWORD **)(a1 + 36);
    while ( 1 )
    {
      v21 = *v20;
      if ( *v20 == v20 )
        break;
      if ( (_QWORD **)v21[1] != v20 )
        goto LABEL_35;
      v22 = (_QWORD *)*v21;
      if ( *(_QWORD **)(*v21 + 8LL) != v21 )
        goto LABEL_35;
      *v20 = v22;
      v22[1] = v20;
      v23 = (struct _NET_BUFFER_LIST *)v21[3];
      v21[1] = v21;
      *v21 = v21;
      NdisFreeNetBufferList(v23);
      ExFreePoolWithTag(v21 - 2, 0);
    }
    UpdateGlobalCallStats(a1);
    v24 = ClearFlags((char *)a1 + 60, 0xFFFFFFFFLL);
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 5, *((_BYTE *)a1 + 48));
    DereferenceTunnel(v5);
    *((_WORD *)a1 + 29) = 0;
    *((_DWORD *)a1 + 22) = 0;
    a1[25] = 0;
    *((_DWORD *)a1 + 32) = 0;
    *((_WORD *)a1 + 113) = 0;
    *(__int64 *)((char *)a1 + 252) = 0;
    *((_DWORD *)a1 + 66) = 0;
    *((_WORD *)a1 + 140) = 0;
    memset(a1 + 43, 0, 0x60u);
    v25 = *(_DWORD *)(v1 + 28);
    *((_DWORD *)a1 + 65) = v25;
    *((_DWORD *)a1 + 67) = v25;
    v26 = *(_DWORD *)(v1 + 364) >> 1;
    *((_DWORD *)a1 + 62) = v26;
    if ( !v26 )
      *((_DWORD *)a1 + 62) = 1;
    if ( (v24 & 0x20000) != 0 )
      NdisCmCloseCallComplete(0, (NDIS_HANDLE)a1[38], 0);
    if ( (v24 & 0x100) != 0 )
    {
      NdisMCmDeleteVc((NDIS_HANDLE)a1[38]);
      LcmCmDeleteVc(a1);
    }
    DereferenceVc(a1);
  }
}

```

## disassembly

```asm
0x14000f2ec  push    rbx
0x14000f2ee  push    rbp
0x14000f2ef  push    rsi
0x14000f2f0  push    rdi
0x14000f2f1  push    r12
0x14000f2f3  push    r13
0x14000f2f5  push    r14
0x14000f2f7  push    r15
0x14000f2f9  sub     rsp, 28h
0x14000f2fd  mov     r13, [rcx+18h]
0x14000f301  mov     rdi, rcx
0x14000f304  call    CallSetupComplete
0x14000f309  movzx   ebp, word ptr [rdi+38h]
0x14000f30d  xor     r14d, r14d
0x14000f310  mov     [rdi+38h], r14w
0x14000f315  test    bp, bp
0x14000f318  jz      short loc_14000F356
0x14000f31a  mov     rsi, [rdi+18h]
0x14000f31e  cmp     bp, [rsi+60h]
0x14000f322  ja      short loc_14000F356
0x14000f324  lea     rcx, [rsi+68h]; SpinLock
0x14000f328  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f32f  nop     dword ptr [rax+rax+00h]
0x14000f334  mov     [rsi+70h], al
0x14000f337  lea     rcx, [rsi+68h]; SpinLock
0x14000f33b  mov     rax, [rsi+58h]
0x14000f33f  mov     [rax+rbp*8-8], r14
0x14000f344  inc     dword ptr [rsi+64h]
0x14000f347  mov     dl, [rsi+70h]; NewIrql
0x14000f34a  call    cs:__imp_KeReleaseSpinLock
0x14000f351  nop     dword ptr [rax+rax+00h]
0x14000f356  mov     rsi, [rdi+20h]
0x14000f35a  test    rsi, rsi
0x14000f35d  jz      loc_14000F679
0x14000f363  mov     edx, 2000000h
0x14000f368  lea     rcx, [rdi+3Ch]
0x14000f36c  call    ClearFlags
0x14000f371  test    eax, eax
0x14000f373  jz      loc_14000F679
0x14000f379  lea     rcx, [rsi+20h]; SpinLock
0x14000f37d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f384  nop     dword ptr [rax+rax+00h]
0x14000f389  mov     [rsi+28h], al
0x14000f38c  lea     rax, [rdi+60h]
0x14000f390  mov     rdx, [rax]
0x14000f393  cmp     [rdx+8], rax
0x14000f397  jnz     loc_14000F68B
0x14000f39d  mov     rcx, [rax+8]
0x14000f3a1  cmp     [rcx], rax
0x14000f3a4  jnz     loc_14000F68B
0x14000f3aa  mov     [rcx], rdx
0x14000f3ad  lea     rbp, [rsi+168h]
0x14000f3b4  mov     [rdx+8], rcx
0x14000f3b8  mov     rcx, rbp; SpinLock
0x14000f3bb  mov     [rax+8], rax
0x14000f3bf  mov     [rax], rax
0x14000f3c2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f3c9  nop     dword ptr [rax+rax+00h]
0x14000f3ce  mov     [rsi+170h], al
0x14000f3d4  mov     rdx, [rdi]
0x14000f3d7  cmp     [rdx+8], rdi
0x14000f3db  jnz     loc_14000F68B
0x14000f3e1  mov     rax, [rdi+8]
0x14000f3e5  cmp     [rax], rdi
0x14000f3e8  jnz     loc_14000F68B
0x14000f3ee  mov     [rax], rdx
0x14000f3f1  mov     rcx, rbp; SpinLock
0x14000f3f4  mov     [rdx+8], rax
0x14000f3f8  mov     [rdi+8], rdi
0x14000f3fc  mov     [rdi], rdi
0x14000f3ff  mov     dl, [rsi+170h]; NewIrql
0x14000f405  call    cs:__imp_KeReleaseSpinLock
0x14000f40c  nop     dword ptr [rax+rax+00h]
0x14000f411  mov     dl, [rsi+28h]; NewIrql
0x14000f414  lea     rcx, [rsi+20h]; SpinLock
0x14000f418  call    cs:__imp_KeReleaseSpinLock
0x14000f41f  nop     dword ptr [rax+rax+00h]
0x14000f424  lea     rcx, [rdi+28h]; SpinLock
0x14000f428  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f42f  nop     dword ptr [rax+rax+00h]
0x14000f434  mov     rdx, [rdi+110h]
0x14000f43b  mov     [rdi+30h], al
0x14000f43e  test    rdx, rdx
0x14000f441  jz      short loc_14000F45C
0x14000f443  mov     rcx, [rsi+130h]
0x14000f44a  mov     r8d, 2
0x14000f450  call    RemoveTqi
0x14000f455  mov     [rdi+110h], r14
0x14000f45c  lea     rbp, [rdi+1D0h]
0x14000f463  mov     rcx, rbp; SpinLock
0x14000f466  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f46d  nop     dword ptr [rax+rax+00h]
0x14000f472  mov     [rdi+1D8h], al
0x14000f478  lea     r14, [rdi+1B8h]
0x14000f47f  mov     rbx, [r14]
0x14000f482  cmp     rbx, r14
0x14000f485  jz      short loc_14000F4CD
0x14000f487  cmp     [rbx+8], r14
0x14000f48b  jnz     loc_14000F68B
0x14000f491  mov     rax, [rbx]
0x14000f494  cmp     [rax+8], rbx
0x14000f498  jnz     loc_14000F68B
0x14000f49e  mov     [r14], rax
0x14000f4a1  mov     [rax+8], r14
0x14000f4a5  mov     rcx, [rbx+48h]; NetBufferList
0x14000f4a9  call    cs:__imp_NdisFreeNetBufferList
0x14000f4b0  nop     dword ptr [rax+rax+00h]
0x14000f4b5  lea     rcx, [r13+4C0h]; Lookaside
0x14000f4bc  mov     rdx, rbx; Entry
0x14000f4bf  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000f4c6  nop     dword ptr [rax+rax+00h]
0x14000f4cb  jmp     short loc_14000F47F
0x14000f4cd  mov     dl, [rdi+1D8h]; NewIrql
0x14000f4d3  mov     rcx, rbp; SpinLock
0x14000f4d6  call    cs:__imp_KeReleaseSpinLock
0x14000f4dd  nop     dword ptr [rax+rax+00h]
0x14000f4e2  lea     r14, [rdi+0E8h]
0x14000f4e9  mov     rbx, [r14]
0x14000f4ec  cmp     rbx, r14
0x14000f4ef  jz      short loc_14000F53D
0x14000f4f1  cmp     [rbx+8], r14
0x14000f4f5  jnz     loc_14000F68B
0x14000f4fb  mov     rax, [rbx]
0x14000f4fe  cmp     [rax+8], rbx
0x14000f502  jnz     loc_14000F68B
0x14000f508  mov     [r14], rax
0x14000f50b  mov     r8d, 2
0x14000f511  mov     [rax+8], r14
0x14000f515  mov     rdx, [rbx+28h]
0x14000f519  mov     [rbx+8], rbx
0x14000f51d  mov     [rbx], rbx
0x14000f520  mov     rcx, [rsi+130h]
0x14000f527  call    RemoveTqi
0x14000f52c  mov     rcx, rbx
0x14000f52f  mov     dword ptr [rbx+48h], 0C0000001h
0x14000f536  call    DereferencePayloadSent
0x14000f53b  jmp     short loc_14000F4E9
0x14000f53d  lea     r14, [rdi+120h]
0x14000f544  mov     rbx, [r14]
0x14000f547  cmp     rbx, r14
0x14000f54a  jz      short loc_14000F595
0x14000f54c  cmp     [rbx+8], r14
0x14000f550  jnz     loc_14000F68B
0x14000f556  mov     rax, [rbx]
0x14000f559  cmp     [rax+8], rbx
0x14000f55d  jnz     loc_14000F68B
0x14000f563  mov     [r14], rax
0x14000f566  mov     [rax+8], r14
0x14000f56a  mov     rcx, [rbx+18h]; NetBufferList
0x14000f56e  mov     [rbx+8], rbx
0x14000f572  mov     [rbx], rbx
0x14000f575  call    cs:__imp_NdisFreeNetBufferList
0x14000f57c  nop     dword ptr [rax+rax+00h]
0x14000f581  lea     rcx, [rbx-10h]; P
0x14000f585  xor     edx, edx; Tag
0x14000f587  call    cs:__imp_ExFreePoolWithTag
0x14000f58e  nop     dword ptr [rax+rax+00h]
0x14000f593  jmp     short loc_14000F544
0x14000f595  mov     rcx, rdi
0x14000f598  call    UpdateGlobalCallStats
0x14000f59d  or      edx, 0FFFFFFFFh
0x14000f5a0  lea     rcx, [rdi+3Ch]
0x14000f5a4  call    ClearFlags
0x14000f5a9  mov     dl, [rdi+30h]; NewIrql
0x14000f5ac  lea     rcx, [rdi+28h]; SpinLock
0x14000f5b0  mov     ebx, eax
0x14000f5b2  call    cs:__imp_KeReleaseSpinLock
0x14000f5b9  nop     dword ptr [rax+rax+00h]
0x14000f5be  mov     rcx, rsi
0x14000f5c1  call    DereferenceTunnel
0x14000f5c6  xor     edx, edx; Val
0x14000f5c8  lea     rcx, [rdi+158h]; void *
0x14000f5cf  mov     [rdi+3Ah], dx
0x14000f5d3  mov     [rdi+58h], edx
0x14000f5d6  mov     [rdi+0C8h], rdx
0x14000f5dd  lea     r8d, [rdx+60h]; Size
0x14000f5e1  mov     [rdi+80h], edx
0x14000f5e7  mov     [rdi+0E2h], dx
0x14000f5ee  mov     [rdi+0FCh], rdx
0x14000f5f5  mov     [rdi+108h], edx
0x14000f5fb  mov     [rdi+118h], dx
0x14000f602  call    memset
0x14000f607  mov     eax, [r13+1Ch]
0x14000f60b  mov     [rdi+104h], eax
0x14000f611  mov     [rdi+10Ch], eax
0x14000f617  mov     eax, [r13+16Ch]
0x14000f61e  shr     eax, 1
0x14000f620  mov     [rdi+0F8h], eax
0x14000f626  jnz     short loc_14000F632
0x14000f628  mov     dword ptr [rdi+0F8h], 1
0x14000f632  bt      ebx, 11h
0x14000f636  jnb     short loc_14000F650
0x14000f638  mov     rdx, [rdi+130h]; NdisVcHandle
0x14000f63f  xor     r8d, r8d; NdisPartyHandle
0x14000f642  xor     ecx, ecx; Status
0x14000f644  call    cs:__imp_NdisCmCloseCallComplete
0x14000f64b  nop     dword ptr [rax+rax+00h]
0x14000f650  bt      ebx, 8
0x14000f654  jnb     short loc_14000F671
0x14000f656  mov     rcx, [rdi+130h]; NdisVcHandle
0x14000f65d  call    cs:__imp_NdisMCmDeleteVc
0x14000f664  nop     dword ptr [rax+rax+00h]
0x14000f669  mov     rcx, rdi
0x14000f66c  call    LcmCmDeleteVc
0x14000f671  mov     rcx, rdi
0x14000f674  call    DereferenceVc
0x14000f679  add     rsp, 28h
0x14000f67d  pop     r15
0x14000f67f  pop     r14
0x14000f681  pop     r13
0x14000f683  pop     r12
0x14000f685  pop     rdi
0x14000f686  pop     rsi
0x14000f687  pop     rbp
0x14000f688  pop     rbx
0x14000f689  retn
0x14000f68b  mov     ecx, 3
0x14000f690  int     29h; Win8: RtlFailFast(ecx)
```
