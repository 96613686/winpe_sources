# ndisMIsLoopbackPacket

- ea: `0x1400df03c`
- end: `0x1400df41b`
- name: `ndisMIsLoopbackPacket`
- size: `991`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_PACKET *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400df424`

## callees

- `0x14002f450`
- `0x14002fe60`
- `0x14005b5b0`
- `0x140060c40`
- `0x140066030`
- `0x1400689b0`
- `0x140069360`
- `0x14006a3d0`
- `0x140088a2c`
- `0x1400df03c`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400df0a9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400df0a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400df3c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400df3c6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400df2d9`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400df2d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400df26e`
- `ntoskrnl!ExAllocatePool2` at `0x1400df26e`
- `ntoskrnl!IoFreeMdl` at `0x1400df3de`
- `ntoskrnl!IoFreeMdl` at `0x1400df3de`

## pseudocode

```c
bool __fastcall ndisMIsLoopbackPacket(struct _NDIS_MINIPORT_BLOCK *a1, struct _NDIS_PACKET *a2, _QWORD *a3)
{
  _MDL *Head; // rcx
  _QWORD *v5; // r13
  struct _NDIS_PACKET *v6; // rdi
  char *MappedSystemVa; // rbx
  unsigned int *v9; // rdx
  char v10; // r8
  _X_FILTER *EthDB; // rcx
  char v12; // bl
  char v13; // si
  _X_FILTER *v14; // r14
  char v15; // cl
  unsigned int MiniportPacketFilter; // r15d
  bool v17; // zf
  char v18; // al
  unsigned __int8 Multicast; // al
  char v20; // dl
  UINT TotalLength; // r12d
  UINT v22; // eax
  __int64 v23; // rbx
  _BYTE *Pool2; // rax
  _BYTE *v25; // r14
  __int64 v26; // r15
  char *v27; // rbx
  char *v28; // rax
  unsigned int v29; // edi
  PVOID v30; // r9
  __int64 v31; // rdx
  PNDIS_BUFFER v32; // rax
  unsigned __int8 *v33; // r9
  unsigned int TotalPacketLength; // [rsp+30h] [rbp-30h] BYREF
  int Status; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v36; // [rsp+38h] [rbp-28h] BYREF
  PNDIS_BUFFER Buffer; // [rsp+40h] [rbp-20h] BYREF
  struct _NDIS_STACK_RESERVED *v38; // [rsp+48h] [rbp-18h] BYREF
  PVOID VirtualAddress; // [rsp+50h] [rbp-10h]
  unsigned int LockState; // [rsp+B8h] [rbp+58h] BYREF

  TotalPacketLength = 0;
  Head = a2->Private.Head;
  v5 = a3;
  v6 = a2;
  Status = 0;
  Buffer = 0;
  v36 = 0;
  v17 = (Head->MdlFlags & 5) == 0;
  LOWORD(LockState) = 0;
  BYTE2(LockState) = 0;
  if ( v17 )
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(Head, 0, MmCached, 0, 0, 0x40000020u);
  else
    MappedSystemVa = (char *)Head->MappedSystemVa;
  if ( MappedSystemVa )
  {
    if ( a1->MediaType )
      return (v6->Private.Flags & 0x200) != 0;
    if ( MINIPORT_TEST_FLAG(a1, 0x800000u) )
    {
      if ( ((unsigned __int8)v10 & (unsigned __int8)*MappedSystemVa) == 0
        && (EthDB = a1->EthDB, *(_DWORD *)(MappedSystemVa + 2) == *(_DWORD *)&EthDB->AdapterAddress[2])
        && *(_WORD *)MappedSystemVa == *(_WORD *)EthDB->AdapterAddress )
      {
        v12 = v10;
        v13 = v10;
      }
      else
      {
        v13 = 0;
        v12 = v10;
      }
      goto LABEL_36;
    }
    NdisAcquireRWLockRead(a1->EthDB->BindListLock, (PLOCK_STATE_EX)&LockState, 0);
    v14 = a1->EthDB;
    v15 = 1;
    v13 = 0;
    MiniportPacketFilter = v14->MiniportPacketFilter;
    if ( (*MappedSystemVa & 1) == 0 )
    {
      if ( *(_DWORD *)(MappedSystemVa + 2) == *(_DWORD *)&v14->AdapterAddress[2]
        && *(_WORD *)MappedSystemVa == *(_WORD *)v14->AdapterAddress )
      {
        v18 = 1;
        v13 = 1;
        goto LABEL_32;
      }
      goto LABEL_31;
    }
    if ( *MappedSystemVa == -1
      && MappedSystemVa[1] == -1
      && MappedSystemVa[2] == -1
      && MappedSystemVa[3] == -1
      && MappedSystemVa[4] == -1
      && MappedSystemVa[5] == -1 )
    {
      v17 = (MiniportPacketFilter & 8) == 0;
    }
    else
    {
      if ( (MiniportPacketFilter & 4) != 0 )
        goto LABEL_24;
      if ( (MiniportPacketFilter & 2) == 0 )
      {
LABEL_31:
        v18 = 0;
        goto LABEL_32;
      }
      Multicast = ethFindMulticast(
                    v14->NextNumAddresses,
                    0,
                    v14->NextMCastAddressBuf,
                    (unsigned __int8 *const)MappedSystemVa);
      v15 = v20 + 1;
      v17 = Multicast == 0;
    }
    if ( !v17 )
    {
LABEL_24:
      v18 = v15;
LABEL_32:
      v12 = v18;
      if ( (MiniportPacketFilter & 0xA0) != 0 )
        v12 = v15;
      NdisReleaseRWLock(v14->BindListLock, (PLOCK_STATE_EX)&LockState);
      if ( !v12 )
        goto LABEL_38;
      v10 = 1;
LABEL_36:
      if ( (v6->Private.Flags & 0x200) != 0 )
      {
        v13 = v10;
LABEL_39:
        v6->Private.NdisPacketFlags |= 4u;
LABEL_40:
        if ( v12 )
        {
          v38 = 0;
          if ( v6->Private.ValidCounts )
          {
            TotalLength = v6->Private.TotalLength;
          }
          else
          {
            NdisQueryPacket(v6, v9, 0, 0, &TotalPacketLength);
            TotalLength = TotalPacketLength;
          }
          v22 = NdisPacketSize(0x20u);
          v23 = v22;
          TotalPacketLength = v22;
          if ( v22 + TotalLength >= TotalLength )
          {
            Pool2 = (_BYTE *)ExAllocatePool2(66, v22 + TotalLength, 1886143566);
            v25 = Pool2;
            if ( Pool2 )
            {
              memset(Pool2, 0, (unsigned int)v23);
              VirtualAddress = &v25[v23];
              LockState = 0;
              v26 = 48LL * ndisPacketStackSize;
              v27 = &v25[v26 + 16];
              v28 = v27 - 4;
              if ( ndisPacketStackSize )
              {
                v29 = LockState;
                do
                {
                  *((_DWORD *)v27 - 1) = v29;
                  NDIS_STACK_RESERVED_FROM_PACKET((struct _NDIS_PACKET *)&v25[v26 + 16], &v38);
                  KeInitializeSpinLock((PKSPIN_LOCK)v38 + 3);
                  ++v29;
                }
                while ( v29 < ndisPacketStackSize );
                v6 = a2;
                v28 = v27 - 4;
                v5 = a3;
              }
              v30 = VirtualAddress;
              *(_DWORD *)v28 = -1;
              NdisAllocateBuffer(&Status, &Buffer, 0, v30, TotalLength);
              if ( !Status )
              {
                v32 = Buffer;
                v33 = (unsigned __int8 *)VirtualAddress;
                *((_QWORD *)v27 + 1) = Buffer;
                *(_QWORD *)&v25[v26 + 32] = v32;
                *(_QWORD *)&v25[v26 + 40] = 1886351180;
                LOWORD(v32) = TotalPacketLength - 48 * ndisPacketStackSize - 152;
                *(_WORD *)&v25[v26 + 58] = (_WORD)v32;
                *(_QWORD *)&v27[(unsigned __int16)v32 + 96] = v27;
                ndisMCopyFromPacketToBuffer(v6, v31, TotalLength, v33, &v36);
                if ( v36 == TotalLength )
                {
                  if ( v5 )
                  {
                    *v5 = v27;
                    v25[v26 + 57] |= 2u;
                    *(_DWORD *)&v25[v26 + 52] = v6->Private.Flags & 0x80 | 0x100;
                  }
                  return v13;
                }
              }
              if ( v27 )
                ExFreePoolWithTag(&v25[v26 + -48 * ndisPacketStackSize], 0);
              if ( Buffer )
                IoFreeMdl(Buffer);
            }
          }
          *v5 = 0;
          return 0;
        }
        return (v6->Private.Flags & 0x200) != 0;
      }
LABEL_38:
      if ( !v13 )
        goto LABEL_40;
      goto LABEL_39;
    }
    goto LABEL_31;
  }
  if ( v5 )
    *v5 = 0;
  return 0;
}

```

## disassembly

```asm
0x1400df03c  mov     [rsp-38h+arg_0], rbx
0x1400df041  mov     [rsp-38h+arg_10], r8
0x1400df046  mov     [rsp-38h+arg_8], rdx
0x1400df04b  push    rbp
0x1400df04c  push    rsi
0x1400df04d  push    rdi
0x1400df04e  push    r12
0x1400df050  push    r13
0x1400df052  push    r14
0x1400df054  push    r15
0x1400df056  mov     rbp, rsp
0x1400df059  sub     rsp, 60h
0x1400df05d  xor     r12d, r12d
0x1400df060  xor     eax, eax
0x1400df062  mov     rsi, rcx
0x1400df065  mov     [rbp+TotalPacketLength], r12d
0x1400df069  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400df06d  mov     r13, r8
0x1400df070  mov     rdi, rdx
0x1400df073  mov     [rbp+Status], r12d
0x1400df077  mov     [rbp+Buffer], r12
0x1400df07b  lea     r8d, [r12+1]; CacheType
0x1400df080  mov     [rbp+var_28], r12d
0x1400df084  test    byte ptr [rcx+0Ah], 5
0x1400df088  mov     word ptr [rbp+LockState], ax
0x1400df08c  mov     byte ptr [rbp+LockState+2], al
0x1400df08f  jz      short loc_1400DF097
0x1400df091  mov     rbx, [rcx+18h]
0x1400df095  jmp     short loc_1400DF0BE
0x1400df097  mov     [rsp+60h+Priority], 40000020h; Priority
0x1400df09f  xor     r9d, r9d; RequestedAddress
0x1400df0a2  xor     edx, edx; AccessMode
0x1400df0a4  mov     [rsp+60h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x1400df0a9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400df0b0  nop     dword ptr [rax+rax+00h]
0x1400df0b5  mov     rbx, rax
0x1400df0b8  mov     r8d, 1
0x1400df0be  test    rbx, rbx
0x1400df0c1  jnz     short loc_1400DF0D3
0x1400df0c3  test    r13, r13
0x1400df0c6  jz      short loc_1400DF0CC
0x1400df0c8  mov     [r13+0], r12
0x1400df0cc  xor     al, al
0x1400df0ce  jmp     loc_1400DF402
0x1400df0d3  cmp     [rsi+1D0h], r12d
0x1400df0da  jnz     loc_1400DF3FA
0x1400df0e0  mov     edx, 800000h; unsigned int
0x1400df0e5  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400df0e8  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400df0ed  test    al, al
0x1400df0ef  jz      short loc_1400DF12A
0x1400df0f1  test    [rbx], r8b
0x1400df0f4  jnz     short loc_1400DF11F
0x1400df0f6  mov     rcx, [rsi+190h]
0x1400df0fd  mov     eax, [rcx+152h]
0x1400df103  cmp     [rbx+2], eax
0x1400df106  jnz     short loc_1400DF11F
0x1400df108  movzx   eax, word ptr [rcx+150h]
0x1400df10f  cmp     [rbx], ax
0x1400df112  jnz     short loc_1400DF11F
0x1400df114  mov     bl, r8b
0x1400df117  mov     sil, r8b
0x1400df11a  jmp     loc_1400DF1FB
0x1400df11f  mov     sil, r12b
0x1400df122  mov     bl, r8b
0x1400df125  jmp     loc_1400DF1FB
0x1400df12a  mov     rcx, [rsi+190h]
0x1400df131  lea     rdx, [rbp+LockState]; LockState
0x1400df135  xor     r8d, r8d; Flags
0x1400df138  mov     rcx, [rcx+120h]; Lock
0x1400df13f  call    NdisAcquireRWLockRead
0x1400df144  mov     r14, [rsi+190h]
0x1400df14b  mov     ecx, 1
0x1400df150  mov     al, [rbx]
0x1400df152  mov     sil, r12b
0x1400df155  mov     r15d, [r14+138h]
0x1400df15c  test    cl, al
0x1400df15e  jz      short loc_1400DF1B4
0x1400df160  mov     dl, 0FFh
0x1400df162  cmp     al, dl
0x1400df164  jnz     short loc_1400DF189
0x1400df166  cmp     [rbx+1], dl
0x1400df169  jnz     short loc_1400DF189
0x1400df16b  cmp     [rbx+2], dl
0x1400df16e  jnz     short loc_1400DF189
0x1400df170  cmp     [rbx+3], dl
0x1400df173  jnz     short loc_1400DF189
0x1400df175  cmp     [rbx+4], dl
0x1400df178  jnz     short loc_1400DF189
0x1400df17a  cmp     [rbx+5], dl
0x1400df17d  jnz     short loc_1400DF189
0x1400df17f  test    r15b, 8
0x1400df183  jz      short loc_1400DF1D4
0x1400df185  mov     al, cl
0x1400df187  jmp     short loc_1400DF1D7
0x1400df189  test    r15b, 4
0x1400df18d  jnz     short loc_1400DF185
0x1400df18f  test    r15b, 2
0x1400df193  jz      short loc_1400DF1D4
0x1400df195  mov     r8, [r14+160h]; unsigned __int8 (*)[6]
0x1400df19c  mov     r9, rbx; unsigned __int8 *
0x1400df19f  mov     ecx, [r14+170h]; unsigned int
0x1400df1a6  xor     edx, edx; struct _ETH_MULTICAST_WRAPPER *
0x1400df1a8  call    ?ethFindMulticast@@YAEIPEAU_ETH_MULTICAST_WRAPPER@@PEAY05EQEAE@Z; ethFindMulticast(uint,_ETH_MULTICAST_WRAPPER *,uchar (*)[6],uchar * const)
0x1400df1ad  lea     ecx, [rdx+1]
0x1400df1b0  test    al, al
0x1400df1b2  jmp     short loc_1400DF183
0x1400df1b4  mov     eax, [r14+152h]
0x1400df1bb  cmp     [rbx+2], eax
0x1400df1be  jnz     short loc_1400DF1D4
0x1400df1c0  movzx   eax, word ptr [r14+150h]
0x1400df1c8  cmp     [rbx], ax
0x1400df1cb  jnz     short loc_1400DF1D4
0x1400df1cd  mov     al, cl
0x1400df1cf  mov     sil, cl
0x1400df1d2  jmp     short loc_1400DF1D7
0x1400df1d4  mov     al, r12b
0x1400df1d7  movzx   ebx, al
0x1400df1da  lea     rdx, [rbp+LockState]; LockState
0x1400df1de  test    r15b, 0A0h
0x1400df1e2  cmovnz  ebx, ecx
0x1400df1e5  mov     rcx, [r14+120h]; Lock
0x1400df1ec  call    NdisReleaseRWLock
0x1400df1f1  test    bl, bl
0x1400df1f3  jz      short loc_1400DF209
0x1400df1f5  mov     r8d, 1
0x1400df1fb  test    dword ptr [rdi+24h], 200h
0x1400df202  jz      short loc_1400DF209
0x1400df204  mov     sil, r8b
0x1400df207  jmp     short loc_1400DF20E
0x1400df209  test    sil, sil
0x1400df20c  jz      short loc_1400DF212
0x1400df20e  or      byte ptr [rdi+29h], 4
0x1400df212  test    bl, bl
0x1400df214  jz      loc_1400DF3FA
0x1400df21a  mov     [rbp+var_18], r12
0x1400df21e  cmp     [rdi+28h], r12b
0x1400df222  jnz     short loc_1400DF241
0x1400df224  lea     rax, [rbp+TotalPacketLength]
0x1400df228  xor     r9d, r9d; FirstBuffer
0x1400df22b  xor     r8d, r8d; BufferCount
0x1400df22e  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax; TotalPacketLength
0x1400df233  mov     rcx, rdi; Packet
0x1400df236  call    NdisQueryPacket
0x1400df23b  mov     r12d, [rbp+TotalPacketLength]
0x1400df23f  jmp     short loc_1400DF245
0x1400df241  mov     r12d, [rdi+4]
0x1400df245  mov     ecx, 20h ; ' '; ProtocolReservedSize
0x1400df24a  call    NdisPacketSize
0x1400df24f  mov     ebx, eax
0x1400df251  mov     [rbp+TotalPacketLength], ebx
0x1400df254  lea     ecx, [rbx+r12]
0x1400df258  cmp     ecx, r12d
0x1400df25b  jb      loc_1400DF3EA
0x1400df261  mov     edx, ecx
0x1400df263  mov     r8d, 706C444Eh
0x1400df269  mov     ecx, 42h ; 'B'
0x1400df26e  call    cs:__imp_ExAllocatePool2
0x1400df275  nop     dword ptr [rax+rax+00h]
0x1400df27a  mov     r14, rax
0x1400df27d  test    rax, rax
0x1400df280  jz      loc_1400DF3EA
0x1400df286  mov     r8d, ebx; Size
0x1400df289  xor     edx, edx; Val
0x1400df28b  mov     rcx, rax; void *
0x1400df28e  call    memset
0x1400df293  mov     edx, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400df299  lea     rax, [rbx+r14]
0x1400df29d  mov     [rbp+VirtualAddress], rax
0x1400df2a1  mov     [rbp+LockState], 0
0x1400df2a8  lea     r15, [rdx+rdx*2]
0x1400df2ac  shl     r15, 4
0x1400df2b0  lea     rbx, [r15+10h]
0x1400df2b4  add     rbx, r14
0x1400df2b7  lea     rax, [rbx-4]
0x1400df2bb  test    edx, edx
0x1400df2bd  jz      short loc_1400DF2FB
0x1400df2bf  mov     edi, [rbp+LockState]
0x1400df2c2  lea     rdx, [rbp+var_18]; struct _NDIS_STACK_RESERVED **
0x1400df2c6  mov     [rbx-4], edi
0x1400df2c9  mov     rcx, rbx; struct _NDIS_PACKET *
0x1400df2cc  call    ?NDIS_STACK_RESERVED_FROM_PACKET@@YAXPEAU_NDIS_PACKET@@PEAPEAU_NDIS_STACK_RESERVED@@@Z; NDIS_STACK_RESERVED_FROM_PACKET(_NDIS_PACKET *,_NDIS_STACK_RESERVED * *)
0x1400df2d1  mov     rcx, [rbp+var_18]
0x1400df2d5  add     rcx, 18h; SpinLock
0x1400df2d9  call    cs:__imp_KeInitializeSpinLock
0x1400df2e0  nop     dword ptr [rax+rax+00h]
0x1400df2e5  inc     edi
0x1400df2e7  cmp     edi, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400df2ed  jb      short loc_1400DF2C2
0x1400df2ef  mov     rdi, [rbp+arg_8]
0x1400df2f3  lea     rax, [rbx-4]
0x1400df2f7  mov     r13, [rbp+arg_10]
0x1400df2fb  mov     r9, [rbp+VirtualAddress]; VirtualAddress
0x1400df2ff  lea     rdx, [rbp+Buffer]; Buffer
0x1400df303  xor     r8d, r8d; PoolHandle
0x1400df306  mov     dword ptr [rax], 0FFFFFFFFh
0x1400df30c  lea     rcx, [rbp+Status]; Status
0x1400df310  mov     [rsp+60h+BugCheckOnFailure], r12d; Length
0x1400df315  call    NdisAllocateBuffer
0x1400df31a  cmp     [rbp+Status], 0
0x1400df31e  jnz     loc_1400DF3AA
0x1400df324  mov     rax, [rbp+Buffer]
0x1400df328  mov     r8d, r12d; unsigned int
0x1400df32b  mov     r9, [rbp+VirtualAddress]; unsigned __int8 *
0x1400df32f  mov     [rbx+8], rax
0x1400df333  mov     [r15+r14+20h], rax
0x1400df338  mov     qword ptr [r15+r14+28h], 706F6F4Ch
0x1400df341  movzx   ecx, word ptr cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400df348  movzx   eax, cx
0x1400df34b  add     ax, ax
0x1400df34e  add     cx, ax
0x1400df351  mov     eax, [rbp+TotalPacketLength]
0x1400df354  shl     cx, 4
0x1400df358  sub     ax, cx
0x1400df35b  mov     ecx, 98h
0x1400df360  sub     ax, cx
0x1400df363  mov     rcx, rdi; struct _NDIS_PACKET *
0x1400df366  movzx   eax, ax
0x1400df369  mov     [r15+r14+3Ah], ax
0x1400df36f  mov     [rax+rbx+60h], rbx
0x1400df374  lea     rax, [rbp+var_28]
0x1400df378  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax; unsigned int *
0x1400df37d  call    ?ndisMCopyFromPacketToBuffer@@YAXPEAU_NDIS_PACKET@@IIPEAEPEAI@Z; ndisMCopyFromPacketToBuffer(_NDIS_PACKET *,uint,uint,uchar *,uint *)
0x1400df382  cmp     [rbp+var_28], r12d
0x1400df386  jnz     short loc_1400DF3AA
0x1400df388  test    r13, r13
0x1400df38b  jz      short loc_1400DF3F5
0x1400df38d  mov     [r13+0], rbx
0x1400df391  or      byte ptr [r15+r14+39h], 2
0x1400df397  mov     eax, [rdi+24h]
0x1400df39a  and     eax, 80h
0x1400df39f  bts     eax, 8
0x1400df3a3  mov     [r15+r14+34h], eax
0x1400df3a8  jmp     short loc_1400DF3F5
0x1400df3aa  test    rbx, rbx
0x1400df3ad  jz      short loc_1400DF3D2
0x1400df3af  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400df3b5  lea     rdx, [rax+rax*2]
0x1400df3b9  shl     rdx, 4
0x1400df3bd  sub     rbx, rdx
0x1400df3c0  xor     edx, edx; Tag
0x1400df3c2  lea     rcx, [rbx-10h]; P
0x1400df3c6  call    cs:__imp_ExFreePoolWithTag
0x1400df3cd  nop     dword ptr [rax+rax+00h]
0x1400df3d2  mov     rax, [rbp+Buffer]
0x1400df3d6  test    rax, rax
0x1400df3d9  jz      short loc_1400DF3EA
0x1400df3db  mov     rcx, rax; Mdl
0x1400df3de  call    cs:__imp_IoFreeMdl
0x1400df3e5  nop     dword ptr [rax+rax+00h]
0x1400df3ea  mov     qword ptr [r13+0], 0
0x1400df3f2  xor     sil, sil
0x1400df3f5  mov     al, sil
0x1400df3f8  jmp     short loc_1400DF402
0x1400df3fa  mov     eax, [rdi+24h]
0x1400df3fd  shr     eax, 9
0x1400df400  and     al, 1
0x1400df402  mov     rbx, [rsp+60h+arg_0]
0x1400df40a  add     rsp, 60h
0x1400df40e  pop     r15
0x1400df410  pop     r14
0x1400df412  pop     r13
0x1400df414  pop     r12
0x1400df416  pop     rdi
0x1400df417  pop     rsi
0x1400df418  pop     rbp
0x1400df419  retn
```
