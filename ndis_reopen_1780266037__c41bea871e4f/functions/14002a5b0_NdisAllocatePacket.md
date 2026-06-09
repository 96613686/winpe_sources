# NdisAllocatePacket

- ea: `0x14002a5b0`
- end: `0x14002a992`
- name: `NdisAllocatePacket`
- size: `994`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_PACKET *Packet, NDIS_HANDLE PoolHandle)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002a120`
- `0x14002a490`
- `0x140068690`
- `0x14008a290`

## callees

- `0x14002a5b0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14002a90a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002a90a`
- `ntoskrnl!ExAllocatePool2` at `0x14002a80f`
- `ntoskrnl!ExAllocatePool2` at `0x14002a80f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a70f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a75a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a70f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a75a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a5ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a697`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a5ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a697`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002a62c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002a654`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002a94f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002a62c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002a654`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002a94f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002a897`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002a897`
- `ntoskrnl!ExQueryDepthSList` at `0x14002a67b`
- `ntoskrnl!ExQueryDepthSList` at `0x14002a6c7`
- `ntoskrnl!ExQueryDepthSList` at `0x14002a67b`
- `ntoskrnl!ExQueryDepthSList` at `0x14002a6c7`
- `ntoskrnl!InitializeSListHead` at `0x14002a845`
- `ntoskrnl!InitializeSListHead` at `0x14002a845`

## pseudocode

```c
void __stdcall NdisAllocatePacket(PNDIS_STATUS Status, PNDIS_PACKET *Packet, NDIS_HANDLE PoolHandle)
{
  union _SLIST_HEADER *v3; // r14
  char *v4; // rbp
  PSLIST_ENTRY v5; // rsi
  PNDIS_PACKET *v7; // rbx
  PNDIS_STATUS v8; // r13
  KSPIN_LOCK *v9; // r12
  KIRQL v10; // al
  char *v11; // r14
  char *v12; // r15
  char *v13; // rax
  unsigned __int64 v14; // rax
  KSPIN_LOCK *v15; // r12
  KIRQL v16; // al
  _QWORD *Alignment; // rdx
  void **Region; // rcx
  char **v19; // rax
  char *v20; // rdi
  int v21; // eax
  LONGLONG v22; // rax
  KIRQL v23; // dl
  unsigned __int64 v24; // rax
  union _SLIST_HEADER *Pool2; // rax
  union _SLIST_HEADER *v26; // r14
  union _SLIST_HEADER *v27; // rsi
  int v28; // r15d
  union _SLIST_HEADER *v29; // rbx
  union _SLIST_HEADER *v30; // r13
  union _SLIST_HEADER *v31; // r14
  unsigned int v32; // esi
  __int64 v33; // rax
  __int64 p_Region; // rcx
  unsigned __int64 v35; // rax
  union _SLIST_HEADER *v36; // [rsp+30h] [rbp-58h]
  KIRQL v39; // [rsp+A0h] [rbp+18h]
  KIRQL v40; // [rsp+A0h] [rbp+18h]
  union _SLIST_HEADER *v41; // [rsp+A8h] [rbp+20h]

  v3 = (union _SLIST_HEADER *)*((_QWORD *)PoolHandle + 5);
  v4 = (char *)PoolHandle + 40;
  v5 = 0;
  v7 = Packet;
  v8 = Status;
  if ( v3 != (union _SLIST_HEADER *)((char *)PoolHandle + 40) )
  {
    v5 = ExpInterlockedPopEntrySList(v3 + 2);
    if ( v5 )
    {
      if ( *((_WORD *)PoolHandle + 4) <= 1u || ExQueryDepthSList(v3 + 2) )
        goto LABEL_21;
      v15 = (KSPIN_LOCK *)((char *)PoolHandle + 32);
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 4);
      Alignment = (_QWORD *)v3->Alignment;
      v40 = v16;
      if ( *(union _SLIST_HEADER **)(v3->Alignment + 8) == v3 )
      {
        Region = (void **)v3->Region;
        if ( *Region == v3 )
        {
          *Region = Alignment;
          Alignment[1] = Region;
          if ( ExQueryDepthSList(v3 + 2) )
          {
            v24 = *(_QWORD *)v4;
            if ( *(char **)(*(_QWORD *)v4 + 8LL) == v4 )
            {
              v3->Alignment = v24;
              v3->Region = (unsigned __int64)v4;
              *(_QWORD *)(v24 + 8) = v3;
              v21 = 0;
              *(_QWORD *)v4 = v3;
              goto LABEL_15;
            }
          }
          else
          {
            v19 = (char **)*((_QWORD *)PoolHandle + 8);
            v20 = (char *)PoolHandle + 56;
            if ( *v19 == v20 )
            {
              v3->Region = (unsigned __int64)v19;
              v3->Alignment = (unsigned __int64)v20;
              *v19 = (char *)v3;
              v21 = 1;
              *((_QWORD *)v20 + 1) = v3;
LABEL_15:
              LODWORD(v3[3].Alignment) = v21;
              KeReleaseSpinLock(v15, v40);
LABEL_21:
              *v7 = (PNDIS_PACKET)v5;
              *v8 = 0;
              *(_DWORD *)&(*v7)[-1].ProtocolReserved[4] = -1;
              *(_DWORD *)(*v7)[-1].ProtocolReserved = -1;
              *(_QWORD *)&(*v7)->ProtocolReserved[(*v7)->Private.NdisPacketOobOffset] = *v7;
              (*v7)->Private.Head = 0;
              (*v7)->Private.ValidCounts = 0;
              (*v7)->Private.NdisPacketFlags = 0x80;
              return;
            }
          }
        }
      }
LABEL_6:
      __fastfail(3u);
    }
  }
  v9 = (KSPIN_LOCK *)((char *)PoolHandle + 32);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 4);
  v11 = (char *)*((_QWORD *)PoolHandle + 9);
  v12 = (char *)PoolHandle + 72;
  v39 = v10;
  if ( v11 != (char *)PoolHandle + 72 )
  {
    if ( *((char **)v11 + 1) != v12 )
      goto LABEL_6;
    v13 = *(char **)v11;
    if ( *(char **)(*(_QWORD *)v11 + 8LL) != v11 )
      goto LABEL_6;
    *(_QWORD *)v12 = v13;
    *((_QWORD *)v13 + 1) = v12;
    v5 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v11 + 2);
    v14 = *(_QWORD *)v4;
    if ( *(char **)(*(_QWORD *)v4 + 8LL) != v4 )
      goto LABEL_6;
    *(_QWORD *)v11 = v14;
    *((_QWORD *)v11 + 1) = v4;
    *(_QWORD *)(v14 + 8) = v11;
    *(_QWORD *)v4 = v11;
    *((_DWORD *)v11 + 12) = 0;
    if ( *(char **)v12 == v12 )
      v22 = 0;
    else
      v22 = *(_QWORD *)(*(_QWORD *)v12 + 16LL) + PoolAgingTicks.QuadPart;
    *((_QWORD *)PoolHandle + 13) = v22;
LABEL_19:
    v23 = v39;
    goto LABEL_20;
  }
  if ( *((_DWORD *)PoolHandle + 3) < (int)*((unsigned __int16 *)PoolHandle + 4) )
  {
    Pool2 = (union _SLIST_HEADER *)ExAllocatePool2(64, *((unsigned int *)PoolHandle + 5), *(unsigned int *)PoolHandle);
    v36 = Pool2;
    v26 = Pool2;
    if ( Pool2 )
    {
      ++*((_DWORD *)PoolHandle + 3);
      v27 = Pool2 + 2;
      Pool2->Region = (unsigned __int64)Pool2;
      Pool2->Alignment = (unsigned __int64)Pool2;
      v41 = Pool2 + 2;
      InitializeSListHead(Pool2 + 2);
      v28 = *((unsigned __int16 *)PoolHandle + 3);
      if ( *((_WORD *)PoolHandle + 3) )
      {
        v29 = v26 + 4;
        v30 = v27;
        do
        {
          v31 = &v29[3 * ndisPacketStackSize + 1];
          *((_BYTE *)&v31[2].HeaderX64 + 9) = 0;
          v29 = (union _SLIST_HEADER *)((char *)v29 + *((unsigned __int16 *)PoolHandle + 2));
          ExpInterlockedPushEntrySList(v30, (PSLIST_ENTRY)v31);
          v31[1].Region = (unsigned __int64)PoolHandle;
          v32 = 0;
          *((_DWORD *)&v31[2].HeaderX64 + 1) = *((_DWORD *)PoolHandle + 4);
          v33 = (unsigned __int16)(*((_WORD *)PoolHandle + 2) - 48 * ndisPacketStackSize - 152);
          *((_WORD *)&v31[2].HeaderX64 + 5) = v33;
          for ( *(unsigned __int64 *)((char *)&v31[6].Alignment + v33) = (unsigned __int64)v31;
                v32 < ndisPacketStackSize;
                ++v32 )
          {
            *((_DWORD *)&v31[-1].HeaderX64 + 3) = v32;
            if ( v32 >= ndisPacketStackSize )
              p_Region = 40;
            else
              p_Region = (__int64)&v31[3 * (v32 - (unsigned __int64)ndisPacketStackSize) + 1].Region;
            KeInitializeSpinLock((PKSPIN_LOCK)p_Region);
          }
          --v28;
        }
        while ( v28 );
        v7 = Packet;
        v9 = (KSPIN_LOCK *)((char *)PoolHandle + 32);
        v8 = Status;
        v26 = v36;
        v27 = v41;
      }
      v5 = ExpInterlockedPopEntrySList(v27);
      v35 = *(_QWORD *)v4;
      if ( *(char **)(*(_QWORD *)v4 + 8LL) != v4 )
        goto LABEL_6;
      v26->Alignment = v35;
      v26->Region = (unsigned __int64)v4;
      *(_QWORD *)(v35 + 8) = v26;
      *(_QWORD *)v4 = v26;
      LODWORD(v26[3].Alignment) = 0;
    }
    goto LABEL_19;
  }
  v23 = v10;
LABEL_20:
  KeReleaseSpinLock(v9, v23);
  if ( v5 )
    goto LABEL_21;
  *v7 = 0;
  *v8 = -1073741670;
}

```

## disassembly

```asm
0x14002a5b0  mov     [rsp+arg_8], rdx; NdisAllocatePacket
0x14002a5b5  mov     [rsp+arg_0], rcx
0x14002a5ba  push    rbx
0x14002a5bb  push    rbp
0x14002a5bc  push    rsi
0x14002a5bd  push    rdi
0x14002a5be  push    r12
0x14002a5c0  push    r13
0x14002a5c2  push    r14
0x14002a5c4  push    r15
0x14002a5c6  sub     rsp, 48h
0x14002a5ca  mov     r14, [r8+28h]
0x14002a5ce  lea     rbp, [r8+28h]
0x14002a5d2  xor     esi, esi
0x14002a5d4  mov     rdi, r8
0x14002a5d7  mov     rbx, rdx
0x14002a5da  mov     r13, rcx
0x14002a5dd  cmp     r14, rbp
0x14002a5e0  jnz     short loc_14002A650
0x14002a5e2  lea     r12, [rdi+20h]
0x14002a5e6  mov     rcx, r12; SpinLock
0x14002a5e9  mov     [rsp+88h+var_60], r12
0x14002a5ee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a5f5  nop     dword ptr [rax+rax+00h]
0x14002a5fa  mov     r14, [rdi+48h]
0x14002a5fe  lea     r15, [rdi+48h]
0x14002a602  mov     [rsp+88h+arg_10], al
0x14002a609  cmp     r14, r15
0x14002a60c  jz      loc_14002A7BA
0x14002a612  cmp     [r14+8], r15
0x14002a616  jnz     short loc_14002A649
0x14002a618  mov     rax, [r14]
0x14002a61b  cmp     [rax+8], r14
0x14002a61f  jnz     short loc_14002A649
0x14002a621  mov     [r15], rax
0x14002a624  lea     rcx, [r14+20h]; ListHead
0x14002a628  mov     [rax+8], r15
0x14002a62c  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002a633  nop     dword ptr [rax+rax+00h]
0x14002a638  mov     rsi, rax
0x14002a63b  mov     rax, [rbp+0]
0x14002a63f  cmp     [rax+8], rbp
0x14002a643  jz      loc_14002A71D
0x14002a649  mov     ecx, 3
0x14002a64e  int     29h; Win8: RtlFailFast(ecx)
0x14002a650  lea     rcx, [r14+20h]; ListHead
0x14002a654  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002a65b  nop     dword ptr [rax+rax+00h]
0x14002a660  mov     rsi, rax
0x14002a663  test    rax, rax
0x14002a666  jz      loc_14002A5E2
0x14002a66c  cmp     word ptr [rdi+8], 1
0x14002a671  jbe     loc_14002A76B
0x14002a677  lea     rcx, [r14+20h]; SListHead
0x14002a67b  call    cs:__imp_ExQueryDepthSList
0x14002a682  nop     dword ptr [rax+rax+00h]
0x14002a687  test    ax, ax
0x14002a68a  jnz     loc_14002A76B
0x14002a690  lea     r12, [rdi+20h]
0x14002a694  mov     rcx, r12; SpinLock
0x14002a697  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a69e  nop     dword ptr [rax+rax+00h]
0x14002a6a3  mov     rdx, [r14]
0x14002a6a6  mov     [rsp+88h+arg_10], al
0x14002a6ad  cmp     [rdx+8], r14
0x14002a6b1  jnz     short loc_14002A649
0x14002a6b3  mov     rcx, [r14+8]
0x14002a6b7  cmp     [rcx], r14
0x14002a6ba  jnz     short loc_14002A649
0x14002a6bc  mov     [rcx], rdx
0x14002a6bf  mov     [rdx+8], rcx
0x14002a6c3  lea     rcx, [r14+20h]; SListHead
0x14002a6c7  call    cs:__imp_ExQueryDepthSList
0x14002a6ce  nop     dword ptr [rax+rax+00h]
0x14002a6d3  test    ax, ax
0x14002a6d6  jnz     loc_14002A7E0
0x14002a6dc  mov     rax, [rdi+40h]
0x14002a6e0  add     rdi, 38h ; '8'
0x14002a6e4  cmp     [rax], rdi
0x14002a6e7  jnz     loc_14002A649
0x14002a6ed  mov     [r14+8], rax
0x14002a6f1  mov     [r14], rdi
0x14002a6f4  mov     [rax], r14
0x14002a6f7  mov     eax, 1
0x14002a6fc  mov     [rdi+8], r14
0x14002a700  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x14002a708  mov     rcx, r12; SpinLock
0x14002a70b  mov     [r14+30h], eax
0x14002a70f  call    cs:__imp_KeReleaseSpinLock
0x14002a716  nop     dword ptr [rax+rax+00h]
0x14002a71b  jmp     short loc_14002A76B
0x14002a71d  mov     [r14], rax
0x14002a720  mov     [r14+8], rbp
0x14002a724  mov     [rax+8], r14
0x14002a728  mov     [rbp+0], r14
0x14002a72c  mov     dword ptr [r14+30h], 0
0x14002a734  mov     rcx, [r15]
0x14002a737  cmp     rcx, r15
0x14002a73a  jz      loc_14002A7D9
0x14002a740  mov     rax, cs:?PoolAgingTicks@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER PoolAgingTicks
0x14002a747  add     rax, [rcx+10h]
0x14002a74b  mov     [rdi+68h], rax
0x14002a74f  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x14002a757  mov     rcx, r12; SpinLock
0x14002a75a  call    cs:__imp_KeReleaseSpinLock
0x14002a761  nop     dword ptr [rax+rax+00h]
0x14002a766  test    rsi, rsi
0x14002a769  jz      short loc_14002A7C8
0x14002a76b  mov     [rbx], rsi
0x14002a76e  xor     edx, edx
0x14002a770  mov     [r13+0], edx
0x14002a774  mov     rax, [rbx]
0x14002a777  mov     dword ptr [rax-4], 0FFFFFFFFh
0x14002a77e  mov     rax, [rbx]
0x14002a781  mov     dword ptr [rax-8], 0FFFFFFFFh
0x14002a788  mov     rcx, [rbx]
0x14002a78b  movzx   eax, word ptr [rcx+2Ah]
0x14002a78f  mov     [rax+rcx+60h], rcx
0x14002a794  mov     rax, [rbx]
0x14002a797  mov     [rax+8], rdx
0x14002a79b  mov     rax, [rbx]
0x14002a79e  mov     [rax+28h], dl
0x14002a7a1  mov     rax, [rbx]
0x14002a7a4  mov     byte ptr [rax+29h], 80h
0x14002a7a8  add     rsp, 48h
0x14002a7ac  pop     r15
0x14002a7ae  pop     r14
0x14002a7b0  pop     r13
0x14002a7b2  pop     r12
0x14002a7b4  pop     rdi
0x14002a7b5  pop     rsi
0x14002a7b6  pop     rbp
0x14002a7b7  pop     rbx
0x14002a7b8  retn
0x14002a7ba  movzx   ecx, word ptr [rdi+8]
0x14002a7be  cmp     [rdi+0Ch], ecx
0x14002a7c1  jl      short loc_14002A804
0x14002a7c3  movzx   edx, al
0x14002a7c6  jmp     short loc_14002A757
0x14002a7c8  mov     qword ptr [rbx], 0
0x14002a7cf  mov     dword ptr [r13+0], 0C000009Ah
0x14002a7d7  jmp     short loc_14002A7A8
0x14002a7d9  xor     eax, eax
0x14002a7db  jmp     loc_14002A74B
0x14002a7e0  mov     rax, [rbp+0]
0x14002a7e4  cmp     [rax+8], rbp
0x14002a7e8  jnz     loc_14002A649
0x14002a7ee  mov     [r14], rax
0x14002a7f1  mov     [r14+8], rbp
0x14002a7f5  mov     [rax+8], r14
0x14002a7f9  xor     eax, eax
0x14002a7fb  mov     [rbp+0], r14
0x14002a7ff  jmp     loc_14002A700
0x14002a804  mov     edx, [rdi+14h]
0x14002a807  mov     ecx, 40h ; '@'
0x14002a80c  mov     r8d, [rdi]
0x14002a80f  call    cs:__imp_ExAllocatePool2
0x14002a816  nop     dword ptr [rax+rax+00h]
0x14002a81b  mov     [rsp+88h+var_58], rax
0x14002a820  mov     r14, rax
0x14002a823  test    rax, rax
0x14002a826  jz      loc_14002A74F
0x14002a82c  inc     dword ptr [rdi+0Ch]
0x14002a82f  lea     rsi, [rax+20h]
0x14002a833  mov     rcx, rsi; SListHead
0x14002a836  mov     [rax+8], rax
0x14002a83a  mov     [rax], rax
0x14002a83d  mov     [rsp+88h+arg_18], rsi
0x14002a845  call    cs:__imp_InitializeSListHead
0x14002a84c  nop     dword ptr [rax+rax+00h]
0x14002a851  movzx   r15d, word ptr [rdi+6]
0x14002a856  test    r15d, r15d
0x14002a859  jz      loc_14002A94C
0x14002a85f  mov     r12d, 98h
0x14002a865  lea     rbx, [r14+40h]
0x14002a869  mov     r13, rsi
0x14002a86c  nop     dword ptr [rax+00h]
0x14002a870  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14002a876  mov     rcx, r13; ListHead
0x14002a879  lea     r14, [rax+rax*2]
0x14002a87d  shl     r14, 4
0x14002a881  add     r14, 10h
0x14002a885  add     r14, rbx
0x14002a888  mov     rdx, r14; ListEntry
0x14002a88b  mov     byte ptr [r14+29h], 0
0x14002a890  movzx   eax, word ptr [rdi+4]
0x14002a894  add     rbx, rax
0x14002a897  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002a89e  nop     dword ptr [rax+rax+00h]
0x14002a8a3  mov     [r14+18h], rdi
0x14002a8a7  xor     esi, esi
0x14002a8a9  mov     eax, [rdi+10h]
0x14002a8ac  mov     [r14+24h], eax
0x14002a8b0  movzx   ecx, word ptr cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14002a8b7  movzx   eax, cx
0x14002a8ba  add     ax, ax
0x14002a8bd  add     cx, ax
0x14002a8c0  movzx   eax, word ptr [rdi+4]
0x14002a8c4  shl     cx, 4
0x14002a8c8  sub     ax, cx
0x14002a8cb  sub     ax, r12w
0x14002a8cf  movzx   eax, ax
0x14002a8d2  mov     [r14+2Ah], ax
0x14002a8d7  mov     [rax+r14+60h], r14
0x14002a8dc  cmp     cs:?ndisPacketStackSize@@3IA, esi; uint ndisPacketStackSize
0x14002a8e2  jz      short loc_14002A920
0x14002a8e4  mov     [r14-4], esi
0x14002a8e8  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14002a8ee  cmp     esi, eax
0x14002a8f0  jnb     loc_14002A988
0x14002a8f6  mov     ecx, esi
0x14002a8f8  sub     rcx, rax
0x14002a8fb  lea     rcx, [rcx+rcx*2]
0x14002a8ff  shl     rcx, 4
0x14002a903  add     rcx, 18h
0x14002a907  add     rcx, r14; SpinLock
0x14002a90a  call    cs:__imp_KeInitializeSpinLock
0x14002a911  nop     dword ptr [rax+rax+00h]
0x14002a916  inc     esi
0x14002a918  cmp     esi, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14002a91e  jb      short loc_14002A8E4
0x14002a920  add     r15d, 0FFFFFFFFh
0x14002a924  jnz     loc_14002A870
0x14002a92a  mov     rbx, [rsp+88h+arg_8]
0x14002a932  mov     r12, [rsp+88h+var_60]
0x14002a937  mov     r13, [rsp+88h+arg_0]
0x14002a93f  mov     r14, [rsp+88h+var_58]
0x14002a944  mov     rsi, [rsp+88h+arg_18]
0x14002a94c  mov     rcx, rsi; ListHead
0x14002a94f  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002a956  nop     dword ptr [rax+rax+00h]
0x14002a95b  mov     rsi, rax
0x14002a95e  mov     rax, [rbp+0]
0x14002a962  cmp     [rax+8], rbp
0x14002a966  jnz     loc_14002A649
0x14002a96c  mov     [r14], rax
0x14002a96f  mov     [r14+8], rbp
0x14002a973  mov     [rax+8], r14
0x14002a977  mov     [rbp+0], r14
0x14002a97b  mov     dword ptr [r14+30h], 0
0x14002a983  jmp     loc_14002A74F
0x14002a988  mov     ecx, 28h ; '('
0x14002a98d  jmp     loc_14002A90A
```
