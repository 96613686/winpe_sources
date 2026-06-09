# NdisAllocateNetBufferAndNetBufferList

- ea: `0x1400319e0`
- end: `0x14003210c`
- name: `NdisAllocateNetBufferAndNetBufferList`
- size: `1836`
- prototype: `PNET_BUFFER_LIST __stdcall(NDIS_HANDLE PoolHandle, USHORT ContextSize, USHORT ContextBackFill, PMDL MdlChain, ULONG DataOffset, SIZE_T DataLength)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140030050`
- `0x140030bc0`
- `0x140054890`
- `0x140055980`
- `0x140089630`

## callees

- `0x140009e70`
- `0x1400319e0`
- `0x140032aa0`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140031e27`
- `ntoskrnl!DbgPrint` at `0x14003209b`
- `ntoskrnl!DbgPrint` at `0x140031e27`
- `ntoskrnl!DbgPrint` at `0x14003209b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031fe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031fe9`
- `ntoskrnl!ExAllocatePool2` at `0x140031f1d`
- `ntoskrnl!ExAllocatePool2` at `0x14003202e`
- `ntoskrnl!ExAllocatePool2` at `0x1400320bc`
- `ntoskrnl!ExAllocatePool2` at `0x140031f1d`
- `ntoskrnl!ExAllocatePool2` at `0x14003202e`
- `ntoskrnl!ExAllocatePool2` at `0x1400320bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031b1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031eaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031fad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031b1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031eaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031fad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031aa4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031e7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031f4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031aa4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031e7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031f4a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140031b00`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140031b00`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031b35`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031ec2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031eec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031b35`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031ec2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031eec`
- `ntoskrnl!ExQueryDepthSList` at `0x140032079`
- `ntoskrnl!ExQueryDepthSList` at `0x140032079`

## pseudocode

```c
PNET_BUFFER_LIST __stdcall NdisAllocateNetBufferAndNetBufferList(
        NDIS_HANDLE PoolHandle,
        USHORT ContextSize,
        USHORT ContextBackFill,
        PMDL MdlChain,
        ULONG DataOffset,
        SIZE_T DataLength)
{
  int v6; // r12d
  USHORT v8; // r15
  unsigned int Number; // r15d
  unsigned __int64 v11; // rbx
  char *v12; // rdi
  KIRQL v13; // r14
  PSLIST_ENTRY v14; // rbx
  unsigned int v15; // ebp
  __int16 v16; // di
  _QWORD *p_Next; // rdx
  unsigned int v18; // ecx
  __int64 v19; // rax
  int v20; // eax
  bool v21; // zf
  _SLIST_ENTRY *v22; // rax
  unsigned __int16 v23; // ax
  ULONG v24; // ecx
  ULONG ByteCount; // eax
  _SLIST_ENTRY *i; // rcx
  __int64 v28; // rax
  unsigned int v29; // edx
  struct _SLIST_ENTRY *v30; // rdi
  unsigned int v31; // r14d
  _SLIST_ENTRY *Next; // rcx
  _SLIST_ENTRY *v33; // r8
  int v34; // edx
  PSLIST_ENTRY v35; // rax
  int v36; // edx
  unsigned __int64 v37; // rax
  KIRQL v38; // al
  __int64 v39; // r8
  PSLIST_ENTRY v40; // rax
  unsigned __int64 v41; // rax
  struct _SLIST_ENTRY *v42; // rax
  KIRQL v43; // al
  __int64 v44; // rdx
  _QWORD *v45; // rcx
  KIRQL v46; // r8
  _QWORD *v47; // rax
  unsigned __int16 v48; // bp
  __int64 v49; // rax
  struct _SLIST_ENTRY *Pool2; // rax

  v6 = ContextSize;
  v8 = ContextBackFill;
  if ( PoolHandle )
  {
    if ( (*((_DWORD *)PoolHandle + 11) & 5) == 1 )
    {
      if ( (ContextSize & 7) != 0 || (ContextBackFill & 7) != 0 )
        return 0;
      if ( (*((_DWORD *)PoolHandle + 1) & 1) != 0 )
      {
        v37 = *((unsigned int *)PoolHandle + 8);
        v15 = 0;
        if ( v37 + 32 >= v37 )
        {
          Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(0x100000042LL, v37 + 32, *((unsigned int *)PoolHandle + 9));
          if ( Pool2 )
          {
            Pool2->Next = (_SLIST_ENTRY *)PoolHandle;
            v14 = Pool2 + 2;
          }
          else
          {
            v14 = 0;
          }
        }
        else
        {
          v14 = 0;
        }
LABEL_14:
        if ( v14 )
        {
          v16 = *((_WORD *)&v14[3].Next + 5);
          memset(v14, 0, 8 * (v15 ^ 1LL) + 368);
          v14[2].Next = (_SLIST_ENTRY *)PoolHandle;
          *((_DWORD *)&v14[8].Next + 2) = 256;
          if ( v15 )
            *((_WORD *)&v14[3].Next + 5) = v16;
          if ( Microsoft_Windows_Networking_CorrelationEnabled )
          {
            if ( *((__int64 *)&v14[15].Next + 1) > 0 )
            {
              for ( i = v14->Next; i; i = i->Next )
              {
                v28 = *((_QWORD *)&i[15].Next + 1);
                if ( !v28 || v28 < 0 )
                {
                  v29 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
                  if ( v29 + 1 < v29 )
                    v29 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
                  *((_QWORD *)&i[15].Next + 1) = v29;
                }
              }
            }
            else
            {
              p_Next = &v14->Next;
              v18 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
              if ( v18 + 1 < v18 )
                v18 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
              do
              {
                if ( (__int64)p_Next[31] <= 0 )
                {
                  v19 = v18++;
                  p_Next[31] = v19;
                }
                p_Next = (_QWORD *)*p_Next;
              }
              while ( p_Next );
            }
          }
          *((_BYTE *)&v14[12].Next + 8) = *((_BYTE *)PoolHandle + 40);
          v20 = *((_DWORD *)PoolHandle + 11);
          if ( (v20 & 2) != 0 )
          {
            v21 = (v20 & 1) == 0;
            v22 = v14 + 35;
            if ( v21 )
              v22 = v14 + 24;
            v14[1].Next = v22;
            v22->Next = 0;
            *((_WORD *)&v14[1].Next->Next + 4) = *((_WORD *)PoolHandle + 21);
            *((_WORD *)&v14[1].Next->Next + 5) = *((_WORD *)PoolHandle + 21);
            if ( *((_WORD *)PoolHandle + 21) >= (unsigned __int16)v6 )
            {
              *((_WORD *)&v14[1].Next->Next + 5) -= v6;
LABEL_35:
              memset(&v14[24], 0, 0xB0u);
              v24 = DataOffset;
              *((_DWORD *)&v14[26].Next + 2) = DataOffset;
              *((_DWORD *)&v14[25].Next + 2) = DataLength;
              v14[26].Next = (_SLIST_ENTRY *)MdlChain;
              for ( *((_QWORD *)&v14[27].Next + 1) = PoolHandle; MdlChain; v24 -= ByteCount )
              {
                ByteCount = MdlChain->ByteCount;
                if ( v24 < ByteCount )
                  break;
                MdlChain = MdlChain->Next;
              }
              *((_QWORD *)&v14[24].Next + 1) = MdlChain;
              LODWORD(v14[25].Next) = v24;
              *((_QWORD *)&v14->Next + 1) = v14 + 24;
              if ( *(int *)ndisNblTrackerMode >= 3 )
                ndisNblTrackerRecordEventInternal((struct _NET_BUFFER_LIST *)v14, 0, 3u, 0, 0);
              return (PNET_BUFFER_LIST)v14;
            }
          }
          v30 = v14;
          if ( !(_WORD)v6 )
            goto LABEL_34;
          v31 = *((_DWORD *)PoolHandle + 9);
          Next = v14[1].Next;
          v33 = v14[23].Next;
          v34 = *((_DWORD *)&v14[2].Next[2].Next + 3);
          if ( (v34 & 2) == 0 )
            goto LABEL_53;
          v35 = v14 + 35;
          if ( (v34 & 1) == 0 )
            v35 = v14 + 24;
          if ( Next != v35 || *((_WORD *)&Next->Next + 5) < (unsigned __int16)v6 )
          {
LABEL_53:
            *((_WORD *)&v14[3].Next + 4) += v6;
            v36 = *((unsigned __int16 *)&v14[3].Next + 4);
            if ( v36 <= ndisMaxCachedNblContextSize )
            {
              if ( (unsigned __int16)v36 <= *((_WORD *)&v14[3].Next + 5) )
                LOWORD(v36) = *((_WORD *)&v14[3].Next + 5);
              *((_WORD *)&v14[3].Next + 5) = v36;
            }
          }
          if ( Next && (v23 = *((_WORD *)&Next->Next + 5), v23 >= (unsigned __int16)v6) )
          {
            *((_WORD *)&Next->Next + 5) = v23 - v6;
          }
          else if ( v33 && *((_WORD *)&v33->Next + 4) >= (unsigned __int16)v6 )
          {
            *((_WORD *)&v33->Next + 5) -= v6;
            v33->Next = v14[1].Next;
            v14[1].Next = v33;
            v14[23].Next = 0;
          }
          else
          {
            v48 = v8 + v6;
            if ( *((unsigned __int16 *)&v14[3].Next + 4) <= ndisMaxCachedNblContextSize )
            {
              if ( v33 )
              {
                v14[23].Next = 0;
                ExFreePoolWithTag(v33, 0);
              }
              if ( v48 <= v6 + *((unsigned __int16 *)&v14[3].Next + 5) - *((unsigned __int16 *)&v14[3].Next + 4) )
                v48 = v6 + *((_WORD *)&v14[3].Next + 5) - *((_WORD *)&v14[3].Next + 4);
              if ( v48 > v6 + (unsigned int)v8 )
                v31 = 1668170830;
            }
            v49 = ExAllocatePool2(64, v48 + 16LL, v31);
            if ( !v49 )
            {
              *((_WORD *)&v14[3].Next + 4) -= v6;
              NdisFreeNetBufferList((PNET_BUFFER_LIST)v14);
              v30 = 0;
LABEL_34:
              v14 = v30;
              if ( v30 )
                goto LABEL_35;
              return (PNET_BUFFER_LIST)v14;
            }
            *(_WORD *)(v49 + 8) = v48;
            *(_WORD *)(v49 + 10) = v48 - v6;
            *(_QWORD *)v49 = v14[1].Next;
            v14[1].Next = (_SLIST_ENTRY *)v49;
          }
          *((_DWORD *)&v14[8].Next + 2) |= 0x400u;
          goto LABEL_34;
        }
        return 0;
      }
      Number = KeGetPcr()->Prcb.Number;
      if ( ndisMaxNumberOfProcessors != 1 )
      {
        v11 = (unsigned __int64)Number << 8;
        v12 = (char *)PoolHandle + v11 + 384;
        if ( !v12[216] )
        {
          v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v12 + 26);
          if ( !v12[216] )
          {
            ExInitializeLookasideListEx(
              (PLOOKASIDE_LIST_EX)v12,
              ndisAllocateFromNPagedPool,
              *(PFREE_FUNCTION_EX *)&v12[-v11 - 200],
              NonPagedPoolNx,
              0,
              *(unsigned int *)&v12[-v11 - 212],
              *(_DWORD *)&v12[-v11 - 216],
              0x400u);
            v12[216] = 1;
          }
          KeReleaseSpinLock((PKSPIN_LOCK)v12 + 26, v13);
        }
        _InterlockedIncrement((volatile signed __int32 *)v12 + 5);
        v14 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v12 + 24));
        if ( v14
          || ExQueryDepthSList(*((PSLIST_HEADER *)v12 + 25)) >= 0xAu
          && (v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v12 + 26),
              v39 = *((_QWORD *)v12 + 24),
              *((_QWORD *)v12 + 24) = *((_QWORD *)v12 + 25),
              *((_QWORD *)v12 + 25) = v39,
              KeReleaseSpinLock((PKSPIN_LOCK)v12 + 26, v38),
              (v14 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v12 + 24))) != 0) )
        {
          v15 = 1;
          goto LABEL_13;
        }
        _InterlockedIncrement((volatile signed __int32 *)v12 + 6);
      }
      _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 37);
      v40 = ExpInterlockedPopEntrySList((PSLIST_HEADER)PoolHandle + 8);
      v14 = v40;
      if ( v40 )
      {
        v15 = 1;
        *((_DWORD *)&v40[-1].Next + 2) = Number;
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 38);
        v41 = *((unsigned int *)PoolHandle + 43);
        if ( v41 + 32 >= v41
          && (v42 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v41 + 32, *((unsigned int *)PoolHandle + 42))) != 0 )
        {
          v42->Next = 0;
          v14 = v42 + 2;
          if ( v42 != (struct _SLIST_ENTRY *)-32LL )
          {
            v42->Next = (_SLIST_ENTRY *)PoolHandle;
            v43 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 1);
            v44 = *((_QWORD *)PoolHandle + 2);
            v45 = (char *)PoolHandle + 16;
            v46 = v43;
            if ( *(NDIS_HANDLE *)(v44 + 8) != (char *)PoolHandle + 16 )
              __fastfail(3u);
            v47 = &v14[-2].Next + 1;
            *v47 = v44;
            v47[1] = v45;
            *(_QWORD *)(v44 + 8) = (char *)v14 - 24;
            *v45 = (char *)v14 - 24;
            KeReleaseSpinLock((PKSPIN_LOCK)PoolHandle + 1, v46);
            v15 = 0;
            *((_DWORD *)&v14[-1].Next + 2) = Number;
            goto LABEL_13;
          }
        }
        else
        {
          v14 = 0;
        }
        v15 = 0;
      }
LABEL_13:
      v8 = ContextBackFill;
      goto LABEL_14;
    }
    DbgPrint("NdisAllocateNetBufferAndNetBufferList: Pool %p wrong pool type.\n", PoolHandle);
    return 0;
  }
  else
  {
    DbgPrint("NdisAllocateNetBufferAndNetBufferList: Pool is NULL\n");
    return 0;
  }
}

```

## disassembly

```asm
0x1400319e0  mov     r11, rsp
0x1400319e3  mov     [r11+18h], r8w
0x1400319e8  push    rsi
0x1400319e9  push    r12
0x1400319eb  push    r13
0x1400319ed  push    r15
0x1400319ef  sub     rsp, 58h
0x1400319f3  movzx   r12d, dx
0x1400319f7  mov     r13, r9
0x1400319fa  movzx   r15d, r8w
0x1400319fe  mov     rsi, rcx
0x140031a01  test    rcx, rcx
0x140031a04  jz      loc_140032094
0x140031a0a  mov     eax, [rcx+2Ch]
0x140031a0d  and     al, 5
0x140031a0f  cmp     al, 1
0x140031a11  jnz     loc_140031E1D
0x140031a17  mov     [r11+10h], rbx
0x140031a1b  movzx   eax, r12w
0x140031a1f  mov     [r11-28h], rbp
0x140031a23  and     ax, 7
0x140031a27  mov     [r11-30h], rdi
0x140031a2b  mov     word ptr [rsp+78h+arg_0], ax
0x140031a33  mov     [r11-38h], r14
0x140031a37  jnz     loc_140032105
0x140031a3d  movzx   eax, r8w
0x140031a41  and     ax, 7
0x140031a45  mov     word ptr [rsp+78h+arg_0], ax
0x140031a4d  jnz     loc_140032105
0x140031a53  mov     eax, [rcx+4]
0x140031a56  test    al, 1
0x140031a58  jnz     loc_140031E04
0x140031a5e  mov     r15d, gs:1A4h
0x140031a67  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140031a6e  mov     [rsp+78h+arg_0], 1
0x140031a79  jz      loc_140031EDE
0x140031a7f  mov     ebx, r15d
0x140031a82  lea     rdi, [rcx+180h]
0x140031a89  shl     rbx, 8
0x140031a8d  add     rdi, rbx
0x140031a90  cmp     byte ptr [rdi+0D8h], 0
0x140031a97  jnz     loc_140031B2A
0x140031a9d  lea     rcx, [rdi+0D0h]; SpinLock
0x140031aa4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031aab  nop     dword ptr [rax+rax+00h]
0x140031ab0  cmp     byte ptr [rdi+0D8h], 0
0x140031ab7  movzx   r14d, al
0x140031abb  jnz     short loc_140031B13
0x140031abd  mov     [rsp+78h+Depth], 400h; Depth
0x140031ac4  mov     r8, rdi
0x140031ac7  sub     r8, rbx
0x140031aca  mov     r9d, 200h; PoolType
0x140031ad0  mov     edx, [r8-0D4h]
0x140031ad7  mov     ecx, [r8-0D8h]
0x140031ade  mov     r8, [r8-0C8h]; Free
0x140031ae5  mov     [rsp+78h+Tag], ecx; Tag
0x140031ae9  mov     rcx, rdi; Lookaside
0x140031aec  mov     [rsp+78h+Size], rdx; Size
0x140031af1  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140031af8  mov     [rsp+78h+Flags], 0; Flags
0x140031b00  call    cs:__imp_ExInitializeLookasideListEx
0x140031b07  nop     dword ptr [rax+rax+00h]
0x140031b0c  mov     byte ptr [rdi+0D8h], 1
0x140031b13  movzx   edx, r14b; NewIrql
0x140031b17  lea     rcx, [rdi+0D0h]; SpinLock
0x140031b1e  call    cs:__imp_KeReleaseSpinLock
0x140031b25  nop     dword ptr [rax+rax+00h]
0x140031b2a  lock inc dword ptr [rdi+14h]
0x140031b2e  mov     rcx, [rdi+0C0h]; ListHead
0x140031b35  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031b3c  nop     dword ptr [rax+rax+00h]
0x140031b41  mov     rbx, rax
0x140031b44  test    rax, rax
0x140031b47  jz      loc_140032072
0x140031b4d  mov     ebp, [rsp+78h+arg_0]
0x140031b54  movzx   r15d, [rsp+78h+arg_10]
0x140031b5d  test    rbx, rbx
0x140031b60  jz      loc_140032105
0x140031b66  movzx   edi, word ptr [rbx+3Ah]
0x140031b6a  xor     edx, edx; Val
0x140031b6c  mov     r8d, ebp
0x140031b6f  mov     rcx, rbx; void *
0x140031b72  xor     r8, 1
0x140031b76  lea     r8, ds:170h[r8*8]; Size
0x140031b7e  call    memset
0x140031b83  mov     [rbx+20h], rsi
0x140031b87  mov     dword ptr [rbx+88h], 100h
0x140031b91  test    ebp, ebp
0x140031b93  jz      short loc_140031B99
0x140031b95  mov     [rbx+3Ah], di
0x140031b99  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140031b9f  test    eax, eax
0x140031ba1  jz      short loc_140031BF1
0x140031ba3  mov     rax, [rbx+0F8h]
0x140031baa  test    rax, rax
0x140031bad  jnz     loc_140031D10
0x140031bb3  mov     rdx, rbx
0x140031bb6  mov     ecx, 1
0x140031bbb  lock xadd cs:dword_14011AE28, ecx
0x140031bc3  lea     eax, [rcx+1]
0x140031bc6  cmp     eax, ecx
0x140031bc8  jb      loc_1400320F3
0x140031bce  mov     rax, [rdx+0F8h]
0x140031bd5  test    rax, rax
0x140031bd8  jnz     loc_140031D61
0x140031bde  mov     eax, ecx
0x140031be0  inc     ecx
0x140031be2  mov     [rdx+0F8h], rax
0x140031be9  mov     rdx, [rdx]
0x140031bec  test    rdx, rdx
0x140031bef  jnz     short loc_140031BCE
0x140031bf1  movzx   eax, byte ptr [rsi+28h]
0x140031bf5  mov     [rbx+0C8h], al
0x140031bfb  mov     eax, [rsi+2Ch]
0x140031bfe  test    al, 2
0x140031c00  jz      loc_140031D6C
0x140031c06  test    al, 1
0x140031c08  lea     rax, [rbx+230h]
0x140031c0f  jnz     short loc_140031C18
0x140031c11  lea     rax, [rbx+180h]
0x140031c18  mov     [rbx+10h], rax
0x140031c1c  mov     qword ptr [rax], 0
0x140031c23  mov     rcx, [rbx+10h]
0x140031c27  movzx   eax, word ptr [rsi+2Ah]
0x140031c2b  mov     [rcx+8], ax
0x140031c2f  mov     rcx, [rbx+10h]
0x140031c33  movzx   eax, word ptr [rsi+2Ah]
0x140031c37  mov     [rcx+0Ah], ax
0x140031c3b  cmp     [rsi+2Ah], r12w
0x140031c40  jb      loc_140031D6C
0x140031c46  mov     rax, [rbx+10h]
0x140031c4a  sub     [rax+0Ah], r12w
0x140031c4f  jmp     short loc_140031C8D
0x140031c51  cmp     [rcx+0Ah], r12w
0x140031c56  jb      loc_140031DB0
0x140031c5c  test    rcx, rcx
0x140031c5f  jz      loc_140031E42
0x140031c65  movzx   eax, word ptr [rcx+0Ah]
0x140031c69  cmp     ax, r12w
0x140031c6d  jb      loc_140031E42
0x140031c73  sub     ax, r12w
0x140031c77  mov     [rcx+0Ah], ax
0x140031c7b  or      dword ptr [rbx+88h], 400h
0x140031c85  mov     rbx, rdi
0x140031c88  test    rdi, rdi
0x140031c8b  jz      short loc_140031CE9
0x140031c8d  lea     rdi, [rbx+180h]
0x140031c94  xor     edx, edx; Val
0x140031c96  mov     rcx, rdi; void *
0x140031c99  mov     r8d, 0B0h; Size
0x140031c9f  call    memset
0x140031ca4  mov     ecx, [rsp+78h+DataOffset]
0x140031cab  mov     eax, dword ptr [rsp+78h+DataLength]
0x140031cb2  mov     [rdi+28h], ecx
0x140031cb5  mov     [rdi+18h], eax
0x140031cb8  mov     [rdi+20h], r13
0x140031cbc  mov     [rdi+38h], rsi
0x140031cc0  test    r13, r13
0x140031cc3  jz      short loc_140031CD1
0x140031cc5  mov     eax, [r13+28h]
0x140031cc9  cmp     ecx, eax
0x140031ccb  jnb     loc_140031F7F
0x140031cd1  mov     [rdi+8], r13
0x140031cd5  mov     [rdi+10h], ecx
0x140031cd8  mov     [rbx+8], rdi
0x140031cdc  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140031ce3  jge     loc_140031DE4
0x140031ce9  mov     rdi, [rsp+78h+var_30]
0x140031cee  mov     rax, rbx
0x140031cf1  mov     rbx, [rsp+78h+arg_8]
0x140031cf9  mov     rbp, [rsp+78h+var_28]
0x140031cfe  mov     r14, [rsp+78h+var_38]
0x140031d03  add     rsp, 58h
0x140031d07  pop     r15
0x140031d09  pop     r13
0x140031d0b  pop     r12
0x140031d0d  pop     rsi
0x140031d0e  retn
0x140031d10  js      loc_140031BB3
0x140031d16  mov     rcx, [rbx]
0x140031d19  test    rcx, rcx
0x140031d1c  jz      loc_140031BF1
0x140031d22  mov     rax, [rcx+0F8h]
0x140031d29  test    rax, rax
0x140031d2c  jnz     loc_140031DD9
0x140031d32  mov     edx, 1
0x140031d37  lock xadd cs:dword_14011AE28, edx
0x140031d3f  lea     eax, [rdx+1]
0x140031d42  cmp     eax, edx
0x140031d44  jb      loc_1400320E1
0x140031d4a  mov     eax, edx
0x140031d4c  mov     [rcx+0F8h], rax
0x140031d53  mov     rcx, [rcx]
0x140031d56  test    rcx, rcx
0x140031d59  jz      loc_140031BF1
0x140031d5f  jmp     short loc_140031D22
0x140031d61  js      loc_140031BDE
0x140031d67  jmp     loc_140031BE9
0x140031d6c  mov     rdi, rbx
0x140031d6f  test    r12w, r12w
0x140031d73  jz      loc_140031C85
0x140031d79  mov     rax, [rbx+20h]
0x140031d7d  mov     r14d, [rsi+24h]
0x140031d81  mov     rcx, [rbx+10h]
0x140031d85  mov     r8, [rbx+170h]
0x140031d8c  mov     edx, [rax+2Ch]
0x140031d8f  test    dl, 2
0x140031d92  jz      short loc_140031DB0
0x140031d94  lea     rax, [rbx+230h]
0x140031d9b  test    dl, 1
0x140031d9e  jnz     short loc_140031DA7
0x140031da0  lea     rax, [rbx+180h]
0x140031da7  cmp     rcx, rax
0x140031daa  jz      loc_140031C51
0x140031db0  add     [rbx+38h], r12w
0x140031db5  movzx   edx, word ptr [rbx+38h]
0x140031db9  cmp     edx, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x140031dbf  jg      loc_140031C5C
0x140031dc5  movzx   eax, word ptr [rbx+3Ah]
0x140031dc9  cmp     dx, ax
0x140031dcc  cmovbe  dx, ax
0x140031dd0  mov     [rbx+3Ah], dx
0x140031dd4  jmp     loc_140031C5C
0x140031dd9  jns     loc_140031D53
0x140031ddf  jmp     loc_140031D32
0x140031de4  xor     r9d, r9d; void *
0x140031de7  mov     [rsp+78h+Flags], 0; unsigned int
0x140031def  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140031df1  mov     r8d, 3; unsigned int
0x140031df7  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140031dfa  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140031dff  jmp     loc_140031CE9
0x140031e04  mov     eax, [rcx+20h]
0x140031e07  xor     ebp, ebp
0x140031e09  lea     rdx, [rax+20h]
0x140031e0d  cmp     rdx, rax
0x140031e10  jnb     loc_1400320AE
0x140031e16  xor     ebx, ebx
0x140031e18  jmp     loc_140031B5D
0x140031e1d  mov     rdx, rsi
0x140031e20  lea     rcx, Format; "NdisAllocateNetBufferAndNetBufferList: "...
0x140031e27  call    cs:__imp_DbgPrint
0x140031e2e  nop     dword ptr [rax+rax+00h]
0x140031e33  xor     eax, eax
0x140031e35  add     rsp, 58h
0x140031e39  pop     r15
0x140031e3b  pop     r13
0x140031e3d  pop     r12
0x140031e3f  pop     rsi
0x140031e40  retn
0x140031e42  test    r8, r8
0x140031e45  jz      loc_140031FC4
0x140031e4b  cmp     [r8+8], r12w
0x140031e50  jb      loc_140031FC4
0x140031e56  sub     [r8+0Ah], r12w
0x140031e5b  mov     rax, [rbx+10h]
0x140031e5f  mov     [r8], rax
0x140031e62  mov     [rbx+10h], r8
0x140031e66  mov     qword ptr [rbx+170h], 0
0x140031e71  jmp     loc_140031C7B
0x140031e76  lea     rcx, [rdi+0D0h]; SpinLock
0x140031e7d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031e84  nop     dword ptr [rax+rax+00h]
0x140031e89  mov     rdx, [rdi+0C8h]
0x140031e90  lea     rcx, [rdi+0D0h]; SpinLock
0x140031e97  mov     r8, [rdi+0C0h]
0x140031e9e  mov     [rdi+0C0h], rdx
0x140031ea5  movzx   edx, al; NewIrql
0x140031ea8  mov     [rdi+0C8h], r8
0x140031eaf  call    cs:__imp_KeReleaseSpinLock
0x140031eb6  nop     dword ptr [rax+rax+00h]
0x140031ebb  mov     rcx, [rdi+0C0h]; ListHead
0x140031ec2  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031ec9  nop     dword ptr [rax+rax+00h]
0x140031ece  mov     rbx, rax
0x140031ed1  test    rax, rax
0x140031ed4  jnz     loc_140031B4D
0x140031eda  lock inc dword ptr [rdi+18h]
0x140031ede  lea     rdi, [rsi+80h]
0x140031ee5  lock inc dword ptr [rdi+14h]
0x140031ee9  mov     rcx, rdi; ListHead
0x140031eec  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031ef3  nop     dword ptr [rax+rax+00h]
0x140031ef8  mov     rbx, rax
0x140031efb  test    rax, rax
0x140031efe  jnz     short loc_140031F6F
0x140031f00  lock inc dword ptr [rdi+18h]
0x140031f04  mov     eax, [rdi+2Ch]
0x140031f07  lea     rdx, [rax+20h]
0x140031f0b  cmp     rdx, rax
0x140031f0e  jb      loc_1400320D8
0x140031f14  mov     r8d, [rdi+28h]
0x140031f18  mov     ecx, 42h ; 'B'
0x140031f1d  call    cs:__imp_ExAllocatePool2
0x140031f24  nop     dword ptr [rax+rax+00h]
0x140031f29  test    rax, rax
0x140031f2c  jz      loc_1400320D8
0x140031f32  mov     [rax], rbx
0x140031f35  lea     rbx, [rax+20h]
0x140031f39  test    rbx, rbx
  ... truncated ...
```
