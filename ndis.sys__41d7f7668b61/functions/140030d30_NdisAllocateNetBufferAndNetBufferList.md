# NdisAllocateNetBufferAndNetBufferList

- ea: `0x140030d30`
- end: `0x14003145c`
- name: `NdisAllocateNetBufferAndNetBufferList`
- size: `1836`
- prototype: `PNET_BUFFER_LIST __stdcall(NDIS_HANDLE PoolHandle, USHORT ContextSize, USHORT ContextBackFill, PMDL MdlChain, ULONG DataOffset, SIZE_T DataLength)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400300b0`
- `0x140030860`
- `0x140039510`
- `0x140059990`
- `0x14008e920`

## callees

- `0x1400231d0`
- `0x1400260b0`
- `0x140030d30`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140031177`
- `ntoskrnl!DbgPrint` at `0x1400313eb`
- `ntoskrnl!DbgPrint` at `0x140031177`
- `ntoskrnl!DbgPrint` at `0x1400313eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031339`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031339`
- `ntoskrnl!ExAllocatePool2` at `0x14003126d`
- `ntoskrnl!ExAllocatePool2` at `0x14003137e`
- `ntoskrnl!ExAllocatePool2` at `0x14003140c`
- `ntoskrnl!ExAllocatePool2` at `0x14003126d`
- `ntoskrnl!ExAllocatePool2` at `0x14003137e`
- `ntoskrnl!ExAllocatePool2` at `0x14003140c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030e6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400311ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400312fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030e6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400311ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400312fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030df4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400311cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003129a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030df4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400311cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003129a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140030e50`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140030e50`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030e85`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031212`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003123c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030e85`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031212`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003123c`
- `ntoskrnl!ExQueryDepthSList` at `0x1400313c9`
- `ntoskrnl!ExQueryDepthSList` at `0x1400313c9`

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
                  v29 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
                  if ( v29 + 1 < v29 )
                    v29 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
                  *((_QWORD *)&i[15].Next + 1) = v29;
                }
              }
            }
            else
            {
              p_Next = &v14->Next;
              v18 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
              if ( v18 + 1 < v18 )
                v18 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
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
0x140030d30  mov     r11, rsp
0x140030d33  mov     [r11+18h], r8w
0x140030d38  push    rsi
0x140030d39  push    r12
0x140030d3b  push    r13
0x140030d3d  push    r15
0x140030d3f  sub     rsp, 58h
0x140030d43  movzx   r12d, dx
0x140030d47  mov     r13, r9
0x140030d4a  movzx   r15d, r8w
0x140030d4e  mov     rsi, rcx
0x140030d51  test    rcx, rcx
0x140030d54  jz      loc_1400313E4
0x140030d5a  mov     eax, [rcx+2Ch]
0x140030d5d  and     al, 5
0x140030d5f  cmp     al, 1
0x140030d61  jnz     loc_14003116D
0x140030d67  mov     [r11+10h], rbx
0x140030d6b  movzx   eax, r12w
0x140030d6f  mov     [r11-28h], rbp
0x140030d73  and     ax, 7
0x140030d77  mov     [r11-30h], rdi
0x140030d7b  mov     word ptr [rsp+78h+arg_0], ax
0x140030d83  mov     [r11-38h], r14
0x140030d87  jnz     loc_140031455
0x140030d8d  movzx   eax, r8w
0x140030d91  and     ax, 7
0x140030d95  mov     word ptr [rsp+78h+arg_0], ax
0x140030d9d  jnz     loc_140031455
0x140030da3  mov     eax, [rcx+4]
0x140030da6  test    al, 1
0x140030da8  jnz     loc_140031154
0x140030dae  mov     r15d, gs:1A4h
0x140030db7  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140030dbe  mov     [rsp+78h+arg_0], 1
0x140030dc9  jz      loc_14003122E
0x140030dcf  mov     ebx, r15d
0x140030dd2  lea     rdi, [rcx+180h]
0x140030dd9  shl     rbx, 8
0x140030ddd  add     rdi, rbx
0x140030de0  cmp     byte ptr [rdi+0D8h], 0
0x140030de7  jnz     loc_140030E7A
0x140030ded  lea     rcx, [rdi+0D0h]; SpinLock
0x140030df4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030dfb  nop     dword ptr [rax+rax+00h]
0x140030e00  cmp     byte ptr [rdi+0D8h], 0
0x140030e07  movzx   r14d, al
0x140030e0b  jnz     short loc_140030E63
0x140030e0d  mov     [rsp+78h+Depth], 400h; Depth
0x140030e14  mov     r8, rdi
0x140030e17  sub     r8, rbx
0x140030e1a  mov     r9d, 200h; PoolType
0x140030e20  mov     edx, [r8-0D4h]
0x140030e27  mov     ecx, [r8-0D8h]
0x140030e2e  mov     r8, [r8-0C8h]; Free
0x140030e35  mov     [rsp+78h+Tag], ecx; Tag
0x140030e39  mov     rcx, rdi; Lookaside
0x140030e3c  mov     [rsp+78h+Size], rdx; Size
0x140030e41  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140030e48  mov     [rsp+78h+Flags], 0; Flags
0x140030e50  call    cs:__imp_ExInitializeLookasideListEx
0x140030e57  nop     dword ptr [rax+rax+00h]
0x140030e5c  mov     byte ptr [rdi+0D8h], 1
0x140030e63  movzx   edx, r14b; NewIrql
0x140030e67  lea     rcx, [rdi+0D0h]; SpinLock
0x140030e6e  call    cs:__imp_KeReleaseSpinLock
0x140030e75  nop     dword ptr [rax+rax+00h]
0x140030e7a  lock inc dword ptr [rdi+14h]
0x140030e7e  mov     rcx, [rdi+0C0h]; ListHead
0x140030e85  call    cs:__imp_ExpInterlockedPopEntrySList
0x140030e8c  nop     dword ptr [rax+rax+00h]
0x140030e91  mov     rbx, rax
0x140030e94  test    rax, rax
0x140030e97  jz      loc_1400313C2
0x140030e9d  mov     ebp, [rsp+78h+arg_0]
0x140030ea4  movzx   r15d, [rsp+78h+arg_10]
0x140030ead  test    rbx, rbx
0x140030eb0  jz      loc_140031455
0x140030eb6  movzx   edi, word ptr [rbx+3Ah]
0x140030eba  xor     edx, edx; Val
0x140030ebc  mov     r8d, ebp
0x140030ebf  mov     rcx, rbx; void *
0x140030ec2  xor     r8, 1
0x140030ec6  lea     r8, ds:170h[r8*8]; Size
0x140030ece  call    memset
0x140030ed3  mov     [rbx+20h], rsi
0x140030ed7  mov     dword ptr [rbx+88h], 100h
0x140030ee1  test    ebp, ebp
0x140030ee3  jz      short loc_140030EE9
0x140030ee5  mov     [rbx+3Ah], di
0x140030ee9  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140030eef  test    eax, eax
0x140030ef1  jz      short loc_140030F41
0x140030ef3  mov     rax, [rbx+0F8h]
0x140030efa  test    rax, rax
0x140030efd  jnz     loc_140031060
0x140030f03  mov     rdx, rbx
0x140030f06  mov     ecx, 1
0x140030f0b  lock xadd cs:dword_140120E28, ecx
0x140030f13  lea     eax, [rcx+1]
0x140030f16  cmp     eax, ecx
0x140030f18  jb      loc_140031443
0x140030f1e  mov     rax, [rdx+0F8h]
0x140030f25  test    rax, rax
0x140030f28  jnz     loc_1400310B1
0x140030f2e  mov     eax, ecx
0x140030f30  inc     ecx
0x140030f32  mov     [rdx+0F8h], rax
0x140030f39  mov     rdx, [rdx]
0x140030f3c  test    rdx, rdx
0x140030f3f  jnz     short loc_140030F1E
0x140030f41  movzx   eax, byte ptr [rsi+28h]
0x140030f45  mov     [rbx+0C8h], al
0x140030f4b  mov     eax, [rsi+2Ch]
0x140030f4e  test    al, 2
0x140030f50  jz      loc_1400310BC
0x140030f56  test    al, 1
0x140030f58  lea     rax, [rbx+230h]
0x140030f5f  jnz     short loc_140030F68
0x140030f61  lea     rax, [rbx+180h]
0x140030f68  mov     [rbx+10h], rax
0x140030f6c  mov     qword ptr [rax], 0
0x140030f73  mov     rcx, [rbx+10h]
0x140030f77  movzx   eax, word ptr [rsi+2Ah]
0x140030f7b  mov     [rcx+8], ax
0x140030f7f  mov     rcx, [rbx+10h]
0x140030f83  movzx   eax, word ptr [rsi+2Ah]
0x140030f87  mov     [rcx+0Ah], ax
0x140030f8b  cmp     [rsi+2Ah], r12w
0x140030f90  jb      loc_1400310BC
0x140030f96  mov     rax, [rbx+10h]
0x140030f9a  sub     [rax+0Ah], r12w
0x140030f9f  jmp     short loc_140030FDD
0x140030fa1  cmp     [rcx+0Ah], r12w
0x140030fa6  jb      loc_140031100
0x140030fac  test    rcx, rcx
0x140030faf  jz      loc_140031192
0x140030fb5  movzx   eax, word ptr [rcx+0Ah]
0x140030fb9  cmp     ax, r12w
0x140030fbd  jb      loc_140031192
0x140030fc3  sub     ax, r12w
0x140030fc7  mov     [rcx+0Ah], ax
0x140030fcb  or      dword ptr [rbx+88h], 400h
0x140030fd5  mov     rbx, rdi
0x140030fd8  test    rdi, rdi
0x140030fdb  jz      short loc_140031039
0x140030fdd  lea     rdi, [rbx+180h]
0x140030fe4  xor     edx, edx; Val
0x140030fe6  mov     rcx, rdi; void *
0x140030fe9  mov     r8d, 0B0h; Size
0x140030fef  call    memset
0x140030ff4  mov     ecx, [rsp+78h+DataOffset]
0x140030ffb  mov     eax, dword ptr [rsp+78h+DataLength]
0x140031002  mov     [rdi+28h], ecx
0x140031005  mov     [rdi+18h], eax
0x140031008  mov     [rdi+20h], r13
0x14003100c  mov     [rdi+38h], rsi
0x140031010  test    r13, r13
0x140031013  jz      short loc_140031021
0x140031015  mov     eax, [r13+28h]
0x140031019  cmp     ecx, eax
0x14003101b  jnb     loc_1400312CF
0x140031021  mov     [rdi+8], r13
0x140031025  mov     [rdi+10h], ecx
0x140031028  mov     [rbx+8], rdi
0x14003102c  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140031033  jge     loc_140031134
0x140031039  mov     rdi, [rsp+78h+var_30]
0x14003103e  mov     rax, rbx
0x140031041  mov     rbx, [rsp+78h+arg_8]
0x140031049  mov     rbp, [rsp+78h+var_28]
0x14003104e  mov     r14, [rsp+78h+var_38]
0x140031053  add     rsp, 58h
0x140031057  pop     r15
0x140031059  pop     r13
0x14003105b  pop     r12
0x14003105d  pop     rsi
0x14003105e  retn
0x140031060  js      loc_140030F03
0x140031066  mov     rcx, [rbx]
0x140031069  test    rcx, rcx
0x14003106c  jz      loc_140030F41
0x140031072  mov     rax, [rcx+0F8h]
0x140031079  test    rax, rax
0x14003107c  jnz     loc_140031129
0x140031082  mov     edx, 1
0x140031087  lock xadd cs:dword_140120E28, edx
0x14003108f  lea     eax, [rdx+1]
0x140031092  cmp     eax, edx
0x140031094  jb      loc_140031431
0x14003109a  mov     eax, edx
0x14003109c  mov     [rcx+0F8h], rax
0x1400310a3  mov     rcx, [rcx]
0x1400310a6  test    rcx, rcx
0x1400310a9  jz      loc_140030F41
0x1400310af  jmp     short loc_140031072
0x1400310b1  js      loc_140030F2E
0x1400310b7  jmp     loc_140030F39
0x1400310bc  mov     rdi, rbx
0x1400310bf  test    r12w, r12w
0x1400310c3  jz      loc_140030FD5
0x1400310c9  mov     rax, [rbx+20h]
0x1400310cd  mov     r14d, [rsi+24h]
0x1400310d1  mov     rcx, [rbx+10h]
0x1400310d5  mov     r8, [rbx+170h]
0x1400310dc  mov     edx, [rax+2Ch]
0x1400310df  test    dl, 2
0x1400310e2  jz      short loc_140031100
0x1400310e4  lea     rax, [rbx+230h]
0x1400310eb  test    dl, 1
0x1400310ee  jnz     short loc_1400310F7
0x1400310f0  lea     rax, [rbx+180h]
0x1400310f7  cmp     rcx, rax
0x1400310fa  jz      loc_140030FA1
0x140031100  add     [rbx+38h], r12w
0x140031105  movzx   edx, word ptr [rbx+38h]
0x140031109  cmp     edx, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x14003110f  jg      loc_140030FAC
0x140031115  movzx   eax, word ptr [rbx+3Ah]
0x140031119  cmp     dx, ax
0x14003111c  cmovbe  dx, ax
0x140031120  mov     [rbx+3Ah], dx
0x140031124  jmp     loc_140030FAC
0x140031129  jns     loc_1400310A3
0x14003112f  jmp     loc_140031082
0x140031134  xor     r9d, r9d; void *
0x140031137  mov     [rsp+78h+Flags], 0; unsigned int
0x14003113f  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140031141  mov     r8d, 3; unsigned int
0x140031147  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x14003114a  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14003114f  jmp     loc_140031039
0x140031154  mov     eax, [rcx+20h]
0x140031157  xor     ebp, ebp
0x140031159  lea     rdx, [rax+20h]
0x14003115d  cmp     rdx, rax
0x140031160  jnb     loc_1400313FE
0x140031166  xor     ebx, ebx
0x140031168  jmp     loc_140030EAD
0x14003116d  mov     rdx, rsi
0x140031170  lea     rcx, aNdisallocatene_0; "NdisAllocateNetBufferAndNetBufferList: "...
0x140031177  call    cs:__imp_DbgPrint
0x14003117e  nop     dword ptr [rax+rax+00h]
0x140031183  xor     eax, eax
0x140031185  add     rsp, 58h
0x140031189  pop     r15
0x14003118b  pop     r13
0x14003118d  pop     r12
0x14003118f  pop     rsi
0x140031190  retn
0x140031192  test    r8, r8
0x140031195  jz      loc_140031314
0x14003119b  cmp     [r8+8], r12w
0x1400311a0  jb      loc_140031314
0x1400311a6  sub     [r8+0Ah], r12w
0x1400311ab  mov     rax, [rbx+10h]
0x1400311af  mov     [r8], rax
0x1400311b2  mov     [rbx+10h], r8
0x1400311b6  mov     qword ptr [rbx+170h], 0
0x1400311c1  jmp     loc_140030FCB
0x1400311c6  lea     rcx, [rdi+0D0h]; SpinLock
0x1400311cd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400311d4  nop     dword ptr [rax+rax+00h]
0x1400311d9  mov     rdx, [rdi+0C8h]
0x1400311e0  lea     rcx, [rdi+0D0h]; SpinLock
0x1400311e7  mov     r8, [rdi+0C0h]
0x1400311ee  mov     [rdi+0C0h], rdx
0x1400311f5  movzx   edx, al; NewIrql
0x1400311f8  mov     [rdi+0C8h], r8
0x1400311ff  call    cs:__imp_KeReleaseSpinLock
0x140031206  nop     dword ptr [rax+rax+00h]
0x14003120b  mov     rcx, [rdi+0C0h]; ListHead
0x140031212  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031219  nop     dword ptr [rax+rax+00h]
0x14003121e  mov     rbx, rax
0x140031221  test    rax, rax
0x140031224  jnz     loc_140030E9D
0x14003122a  lock inc dword ptr [rdi+18h]
0x14003122e  lea     rdi, [rsi+80h]
0x140031235  lock inc dword ptr [rdi+14h]
0x140031239  mov     rcx, rdi; ListHead
0x14003123c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140031243  nop     dword ptr [rax+rax+00h]
0x140031248  mov     rbx, rax
0x14003124b  test    rax, rax
0x14003124e  jnz     short loc_1400312BF
0x140031250  lock inc dword ptr [rdi+18h]
0x140031254  mov     eax, [rdi+2Ch]
0x140031257  lea     rdx, [rax+20h]
0x14003125b  cmp     rdx, rax
0x14003125e  jb      loc_140031428
0x140031264  mov     r8d, [rdi+28h]
0x140031268  mov     ecx, 42h ; 'B'
0x14003126d  call    cs:__imp_ExAllocatePool2
0x140031274  nop     dword ptr [rax+rax+00h]
0x140031279  test    rax, rax
0x14003127c  jz      loc_140031428
0x140031282  mov     [rax], rbx
0x140031285  lea     rbx, [rax+20h]
0x140031289  test    rbx, rbx
  ... truncated ...
```
