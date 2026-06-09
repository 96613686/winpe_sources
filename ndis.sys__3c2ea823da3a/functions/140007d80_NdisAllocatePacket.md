# NdisAllocatePacket

- ea: `0x140007d80`
- end: `0x140008162`
- name: `NdisAllocatePacket`
- size: `994`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_PACKET *Packet, NDIS_HANDLE PoolHandle)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400078f0`
- `0x140007c60`
- `0x1400632c0`
- `0x140085010`

## callees

- `0x140007d80`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400080da`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400080da`
- `ntoskrnl!ExAllocatePool2` at `0x140007fdf`
- `ntoskrnl!ExAllocatePool2` at `0x140007fdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007edf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007edf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007dbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007e67`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007dbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007e67`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140007dfc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140007e24`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000811f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140007dfc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140007e24`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000811f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140008067`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140008067`
- `ntoskrnl!ExQueryDepthSList` at `0x140007e4b`
- `ntoskrnl!ExQueryDepthSList` at `0x140007e97`
- `ntoskrnl!ExQueryDepthSList` at `0x140007e4b`
- `ntoskrnl!ExQueryDepthSList` at `0x140007e97`
- `ntoskrnl!InitializeSListHead` at `0x140008015`
- `ntoskrnl!InitializeSListHead` at `0x140008015`

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
0x140007d80  mov     [rsp+arg_8], rdx; NdisAllocatePacket
0x140007d85  mov     [rsp+arg_0], rcx
0x140007d8a  push    rbx
0x140007d8b  push    rbp
0x140007d8c  push    rsi
0x140007d8d  push    rdi
0x140007d8e  push    r12
0x140007d90  push    r13
0x140007d92  push    r14
0x140007d94  push    r15
0x140007d96  sub     rsp, 48h
0x140007d9a  mov     r14, [r8+28h]
0x140007d9e  lea     rbp, [r8+28h]
0x140007da2  xor     esi, esi
0x140007da4  mov     rdi, r8
0x140007da7  mov     rbx, rdx
0x140007daa  mov     r13, rcx
0x140007dad  cmp     r14, rbp
0x140007db0  jnz     short loc_140007E20
0x140007db2  lea     r12, [rdi+20h]
0x140007db6  mov     rcx, r12; SpinLock
0x140007db9  mov     [rsp+88h+var_60], r12
0x140007dbe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007dc5  nop     dword ptr [rax+rax+00h]
0x140007dca  mov     r14, [rdi+48h]
0x140007dce  lea     r15, [rdi+48h]
0x140007dd2  mov     [rsp+88h+arg_10], al
0x140007dd9  cmp     r14, r15
0x140007ddc  jz      loc_140007F8A
0x140007de2  cmp     [r14+8], r15
0x140007de6  jnz     short loc_140007E19
0x140007de8  mov     rax, [r14]
0x140007deb  cmp     [rax+8], r14
0x140007def  jnz     short loc_140007E19
0x140007df1  mov     [r15], rax
0x140007df4  lea     rcx, [r14+20h]; ListHead
0x140007df8  mov     [rax+8], r15
0x140007dfc  call    cs:__imp_ExpInterlockedPopEntrySList
0x140007e03  nop     dword ptr [rax+rax+00h]
0x140007e08  mov     rsi, rax
0x140007e0b  mov     rax, [rbp+0]
0x140007e0f  cmp     [rax+8], rbp
0x140007e13  jz      loc_140007EED
0x140007e19  mov     ecx, 3
0x140007e1e  int     29h; Win8: RtlFailFast(ecx)
0x140007e20  lea     rcx, [r14+20h]; ListHead
0x140007e24  call    cs:__imp_ExpInterlockedPopEntrySList
0x140007e2b  nop     dword ptr [rax+rax+00h]
0x140007e30  mov     rsi, rax
0x140007e33  test    rax, rax
0x140007e36  jz      loc_140007DB2
0x140007e3c  cmp     word ptr [rdi+8], 1
0x140007e41  jbe     loc_140007F3B
0x140007e47  lea     rcx, [r14+20h]; SListHead
0x140007e4b  call    cs:__imp_ExQueryDepthSList
0x140007e52  nop     dword ptr [rax+rax+00h]
0x140007e57  test    ax, ax
0x140007e5a  jnz     loc_140007F3B
0x140007e60  lea     r12, [rdi+20h]
0x140007e64  mov     rcx, r12; SpinLock
0x140007e67  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007e6e  nop     dword ptr [rax+rax+00h]
0x140007e73  mov     rdx, [r14]
0x140007e76  mov     [rsp+88h+arg_10], al
0x140007e7d  cmp     [rdx+8], r14
0x140007e81  jnz     short loc_140007E19
0x140007e83  mov     rcx, [r14+8]
0x140007e87  cmp     [rcx], r14
0x140007e8a  jnz     short loc_140007E19
0x140007e8c  mov     [rcx], rdx
0x140007e8f  mov     [rdx+8], rcx
0x140007e93  lea     rcx, [r14+20h]; SListHead
0x140007e97  call    cs:__imp_ExQueryDepthSList
0x140007e9e  nop     dword ptr [rax+rax+00h]
0x140007ea3  test    ax, ax
0x140007ea6  jnz     loc_140007FB0
0x140007eac  mov     rax, [rdi+40h]
0x140007eb0  add     rdi, 38h ; '8'
0x140007eb4  cmp     [rax], rdi
0x140007eb7  jnz     loc_140007E19
0x140007ebd  mov     [r14+8], rax
0x140007ec1  mov     [r14], rdi
0x140007ec4  mov     [rax], r14
0x140007ec7  mov     eax, 1
0x140007ecc  mov     [rdi+8], r14
0x140007ed0  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x140007ed8  mov     rcx, r12; SpinLock
0x140007edb  mov     [r14+30h], eax
0x140007edf  call    cs:__imp_KeReleaseSpinLock
0x140007ee6  nop     dword ptr [rax+rax+00h]
0x140007eeb  jmp     short loc_140007F3B
0x140007eed  mov     [r14], rax
0x140007ef0  mov     [r14+8], rbp
0x140007ef4  mov     [rax+8], r14
0x140007ef8  mov     [rbp+0], r14
0x140007efc  mov     dword ptr [r14+30h], 0
0x140007f04  mov     rcx, [r15]
0x140007f07  cmp     rcx, r15
0x140007f0a  jz      loc_140007FA9
0x140007f10  mov     rax, cs:?PoolAgingTicks@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER PoolAgingTicks
0x140007f17  add     rax, [rcx+10h]
0x140007f1b  mov     [rdi+68h], rax
0x140007f1f  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x140007f27  mov     rcx, r12; SpinLock
0x140007f2a  call    cs:__imp_KeReleaseSpinLock
0x140007f31  nop     dword ptr [rax+rax+00h]
0x140007f36  test    rsi, rsi
0x140007f39  jz      short loc_140007F98
0x140007f3b  mov     [rbx], rsi
0x140007f3e  xor     edx, edx
0x140007f40  mov     [r13+0], edx
0x140007f44  mov     rax, [rbx]
0x140007f47  mov     dword ptr [rax-4], 0FFFFFFFFh
0x140007f4e  mov     rax, [rbx]
0x140007f51  mov     dword ptr [rax-8], 0FFFFFFFFh
0x140007f58  mov     rcx, [rbx]
0x140007f5b  movzx   eax, word ptr [rcx+2Ah]
0x140007f5f  mov     [rax+rcx+60h], rcx
0x140007f64  mov     rax, [rbx]
0x140007f67  mov     [rax+8], rdx
0x140007f6b  mov     rax, [rbx]
0x140007f6e  mov     [rax+28h], dl
0x140007f71  mov     rax, [rbx]
0x140007f74  mov     byte ptr [rax+29h], 80h
0x140007f78  add     rsp, 48h
0x140007f7c  pop     r15
0x140007f7e  pop     r14
0x140007f80  pop     r13
0x140007f82  pop     r12
0x140007f84  pop     rdi
0x140007f85  pop     rsi
0x140007f86  pop     rbp
0x140007f87  pop     rbx
0x140007f88  retn
0x140007f8a  movzx   ecx, word ptr [rdi+8]
0x140007f8e  cmp     [rdi+0Ch], ecx
0x140007f91  jl      short loc_140007FD4
0x140007f93  movzx   edx, al
0x140007f96  jmp     short loc_140007F27
0x140007f98  mov     qword ptr [rbx], 0
0x140007f9f  mov     dword ptr [r13+0], 0C000009Ah
0x140007fa7  jmp     short loc_140007F78
0x140007fa9  xor     eax, eax
0x140007fab  jmp     loc_140007F1B
0x140007fb0  mov     rax, [rbp+0]
0x140007fb4  cmp     [rax+8], rbp
0x140007fb8  jnz     loc_140007E19
0x140007fbe  mov     [r14], rax
0x140007fc1  mov     [r14+8], rbp
0x140007fc5  mov     [rax+8], r14
0x140007fc9  xor     eax, eax
0x140007fcb  mov     [rbp+0], r14
0x140007fcf  jmp     loc_140007ED0
0x140007fd4  mov     edx, [rdi+14h]
0x140007fd7  mov     ecx, 40h ; '@'
0x140007fdc  mov     r8d, [rdi]
0x140007fdf  call    cs:__imp_ExAllocatePool2
0x140007fe6  nop     dword ptr [rax+rax+00h]
0x140007feb  mov     [rsp+88h+var_58], rax
0x140007ff0  mov     r14, rax
0x140007ff3  test    rax, rax
0x140007ff6  jz      loc_140007F1F
0x140007ffc  inc     dword ptr [rdi+0Ch]
0x140007fff  lea     rsi, [rax+20h]
0x140008003  mov     rcx, rsi; SListHead
0x140008006  mov     [rax+8], rax
0x14000800a  mov     [rax], rax
0x14000800d  mov     [rsp+88h+arg_18], rsi
0x140008015  call    cs:__imp_InitializeSListHead
0x14000801c  nop     dword ptr [rax+rax+00h]
0x140008021  movzx   r15d, word ptr [rdi+6]
0x140008026  test    r15d, r15d
0x140008029  jz      loc_14000811C
0x14000802f  mov     r12d, 98h
0x140008035  lea     rbx, [r14+40h]
0x140008039  mov     r13, rsi
0x14000803c  nop     dword ptr [rax+00h]
0x140008040  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x140008046  mov     rcx, r13; ListHead
0x140008049  lea     r14, [rax+rax*2]
0x14000804d  shl     r14, 4
0x140008051  add     r14, 10h
0x140008055  add     r14, rbx
0x140008058  mov     rdx, r14; ListEntry
0x14000805b  mov     byte ptr [r14+29h], 0
0x140008060  movzx   eax, word ptr [rdi+4]
0x140008064  add     rbx, rax
0x140008067  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000806e  nop     dword ptr [rax+rax+00h]
0x140008073  mov     [r14+18h], rdi
0x140008077  xor     esi, esi
0x140008079  mov     eax, [rdi+10h]
0x14000807c  mov     [r14+24h], eax
0x140008080  movzx   ecx, word ptr cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x140008087  movzx   eax, cx
0x14000808a  add     ax, ax
0x14000808d  add     cx, ax
0x140008090  movzx   eax, word ptr [rdi+4]
0x140008094  shl     cx, 4
0x140008098  sub     ax, cx
0x14000809b  sub     ax, r12w
0x14000809f  movzx   eax, ax
0x1400080a2  mov     [r14+2Ah], ax
0x1400080a7  mov     [rax+r14+60h], r14
0x1400080ac  cmp     cs:?ndisPacketStackSize@@3IA, esi; uint ndisPacketStackSize
0x1400080b2  jz      short loc_1400080F0
0x1400080b4  mov     [r14-4], esi
0x1400080b8  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400080be  cmp     esi, eax
0x1400080c0  jnb     loc_140008158
0x1400080c6  mov     ecx, esi
0x1400080c8  sub     rcx, rax
0x1400080cb  lea     rcx, [rcx+rcx*2]
0x1400080cf  shl     rcx, 4
0x1400080d3  add     rcx, 18h
0x1400080d7  add     rcx, r14; SpinLock
0x1400080da  call    cs:__imp_KeInitializeSpinLock
0x1400080e1  nop     dword ptr [rax+rax+00h]
0x1400080e6  inc     esi
0x1400080e8  cmp     esi, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400080ee  jb      short loc_1400080B4
0x1400080f0  add     r15d, 0FFFFFFFFh
0x1400080f4  jnz     loc_140008040
0x1400080fa  mov     rbx, [rsp+88h+arg_8]
0x140008102  mov     r12, [rsp+88h+var_60]
0x140008107  mov     r13, [rsp+88h+arg_0]
0x14000810f  mov     r14, [rsp+88h+var_58]
0x140008114  mov     rsi, [rsp+88h+arg_18]
0x14000811c  mov     rcx, rsi; ListHead
0x14000811f  call    cs:__imp_ExpInterlockedPopEntrySList
0x140008126  nop     dword ptr [rax+rax+00h]
0x14000812b  mov     rsi, rax
0x14000812e  mov     rax, [rbp+0]
0x140008132  cmp     [rax+8], rbp
0x140008136  jnz     loc_140007E19
0x14000813c  mov     [r14], rax
0x14000813f  mov     [r14+8], rbp
0x140008143  mov     [rax+8], r14
0x140008147  mov     [rbp+0], r14
0x14000814b  mov     dword ptr [r14+30h], 0
0x140008153  jmp     loc_140007F1F
0x140008158  mov     ecx, 28h ; '('
0x14000815d  jmp     loc_1400080DA
```
