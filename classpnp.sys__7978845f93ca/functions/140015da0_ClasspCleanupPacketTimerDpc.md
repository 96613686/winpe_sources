# ClasspCleanupPacketTimerDpc

- ea: `0x140015da0`
- end: `0x140016067`
- name: `ClasspCleanupPacketTimerDpc`
- size: `711`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140015da0`
- `0x140016070`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016013`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016013`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140015de1`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140015de1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016031`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016031`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140015e52`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140015e52`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140015f74`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140015f74`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140015e93`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140015e93`
- `ntoskrnl!ExQueryDepthSList` at `0x140015e30`
- `ntoskrnl!ExQueryDepthSList` at `0x140015ed6`
- `ntoskrnl!ExQueryDepthSList` at `0x140015f57`
- `ntoskrnl!ExQueryDepthSList` at `0x140015e30`
- `ntoskrnl!ExQueryDepthSList` at `0x140015ed6`
- `ntoskrnl!ExQueryDepthSList` at `0x140015f57`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140015df0`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140015df0`
- `ntoskrnl!KeCancelTimer` at `0x140016000`
- `ntoskrnl!KeCancelTimer` at `0x140016000`

## pseudocode

```c
void __fastcall ClasspCleanupPacketTimerDpc(
        struct _KDPC *Dpc,
        _QWORD *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // rbx
  ULONG MaximumProcessorCount; // r14d
  ULONG v6; // esi
  unsigned int v7; // r13d
  char i; // r12
  unsigned __int64 v9; // rdi
  USHORT DepthSList; // ax
  unsigned __int64 v11; // rcx
  PSLIST_ENTRY v12; // rax
  unsigned __int64 v13; // rbp
  struct _SLIST_ENTRY *Next; // rdi
  unsigned __int64 v15; // rcx
  unsigned int v16; // ebp
  __int64 v17; // r14
  __int64 v18; // rsi
  USHORT v19; // ax
  __int64 v20; // rcx
  unsigned int v21; // r10d
  unsigned int v22; // r9d
  unsigned int v23; // r15d
  unsigned int v24; // edx
  unsigned int v25; // edi
  PSLIST_ENTRY v26; // rax
  char v27; // dl
  KIRQL v28; // al

  if ( DeferredContext )
  {
    v4 = DeferredContext[143];
    if ( v4 )
    {
      MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
      v6 = 0;
      v7 = KeQueryHighestNodeNumber() + 1;
      for ( i = 1; v6 < MaximumProcessorCount; ++v6 )
      {
        v9 = (unsigned __int64)v6 << 6;
        DepthSList = ExQueryDepthSList((PSLIST_HEADER)(v9 + *(_QWORD *)(v4 + 680)));
        v11 = v9 + *(_QWORD *)(v4 + 680);
        if ( *(_DWORD *)(v11 + 16) == DepthSList )
        {
          v12 = ExpInterlockedFlushSList((PSLIST_HEADER)v11);
          if ( v12 )
          {
            v13 = v9 + 16;
            do
            {
              Next = v12->Next;
              _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v4 + 680) + v13));
              v15 = (unsigned __int64)*((unsigned int *)&v12[22].Next + 3) << 6;
              LODWORD(v12[23].Next) = -1;
              ExpInterlockedPushEntrySList((PSLIST_HEADER)(*(_QWORD *)(v4 + 1536) + v15), v12);
              v12 = Next;
            }
            while ( Next );
          }
        }
        else
        {
          i = 0;
        }
      }
      v16 = 0;
      if ( v7 )
      {
        v17 = 0;
        while ( 1 )
        {
          v18 = v17 << 6;
          v19 = ExQueryDepthSList((PSLIST_HEADER)((v17 << 6) + *(_QWORD *)(v4 + 1536)));
          v20 = *(_QWORD *)(v4 + 1536);
          v21 = *(_DWORD *)(v20 + (v17 << 6) + 16);
          if ( v19 >= v21 )
          {
            v22 = *(_DWORD *)(v4 + 1280);
            if ( v19 > v22 )
              break;
          }
          i = 0;
LABEL_27:
          ++v16;
          ++v17;
          if ( v16 >= v7 )
            goto LABEL_28;
        }
        v23 = *(_DWORD *)(v4 + 1284);
        if ( v19 <= v23 )
        {
          if ( v19 - v22 < 0xAA )
            v24 = 16;
          else
            v24 = (v19 - v22) / 0xA;
          if ( v22 + v24 >= v19 )
          {
            v23 = *(_DWORD *)(v4 + 1280);
            goto LABEL_20;
          }
          v23 = v19 - v24;
        }
        i = 0;
LABEL_20:
        if ( v23 < v21 )
        {
          do
          {
            v25 = *(_DWORD *)(v18 + v20 + 16);
            if ( ExQueryDepthSList((PSLIST_HEADER)(v18 + v20)) < v25 )
              break;
            v26 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v18 + *(_QWORD *)(v4 + 1536)));
            if ( !v26 )
              break;
            v26->Next = 0;
            _InterlockedDecrement((volatile signed __int32 *)(v18 + *(_QWORD *)(v4 + 1536) + 16));
            DestroyTransferPacket(&v26[-1]);
            v20 = *(_QWORD *)(v4 + 1536);
          }
          while ( v23 < *(_DWORD *)(v20 + v18 + 16) );
        }
        v27 = 0;
        if ( v23 == *(_DWORD *)(v18 + *(_QWORD *)(v4 + 1536) + 16) )
          v27 = i;
        i = v27;
        goto LABEL_27;
      }
LABEL_28:
      if ( i )
      {
        KeCancelTimer((PKTIMER)(v4 + 496));
        v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 1560));
        _InterlockedAnd((volatile signed __int32 *)(v4 + 664), 0xFFFFFFF7);
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 1560), v28);
      }
    }
  }
}

```

## disassembly

```asm
0x140015da0  mov     rax, rsp
0x140015da3  sub     rsp, 48h
0x140015da7  test    rdx, rdx
0x140015daa  jz      loc_140016047
0x140015db0  mov     [rax+8], rbx
0x140015db4  mov     rbx, [rdx+478h]
0x140015dbb  test    rbx, rbx
0x140015dbe  jz      loc_140016042
0x140015dc4  mov     [rax+10h], rbp
0x140015dc8  mov     ecx, 0FFFFh; GroupNumber
0x140015dcd  mov     [rax+18h], rsi
0x140015dd1  mov     [rax-10h], r12
0x140015dd5  mov     [rax-18h], r13
0x140015dd9  mov     [rax-20h], r14
0x140015ddd  mov     [rax-8], rdi
0x140015de1  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140015de8  nop     dword ptr [rax+rax+00h]
0x140015ded  mov     r14d, eax
0x140015df0  call    cs:__imp_KeQueryHighestNodeNumber
0x140015df7  nop     dword ptr [rax+rax+00h]
0x140015dfc  movzx   r13d, ax
0x140015e00  xor     esi, esi
0x140015e02  inc     r13d
0x140015e05  mov     r12b, 1
0x140015e08  test    r14d, r14d
0x140015e0b  jz      loc_140015EB2
0x140015e11  nop     dword ptr [rax+00h]
0x140015e15  nop     word ptr [rax+rax+00000000h]
0x140015e20  mov     rcx, [rbx+2A8h]
0x140015e27  mov     edi, esi
0x140015e29  shl     rdi, 6
0x140015e2d  add     rcx, rdi; SListHead
0x140015e30  call    cs:__imp_ExQueryDepthSList
0x140015e37  nop     dword ptr [rax+rax+00h]
0x140015e3c  mov     rcx, [rbx+2A8h]
0x140015e43  add     rcx, rdi; ListHead
0x140015e46  movzx   edx, ax
0x140015e49  cmp     [rcx+10h], edx
0x140015e4c  jnz     loc_14001604D
0x140015e52  call    cs:__imp_ExpInterlockedFlushSList
0x140015e59  nop     dword ptr [rax+rax+00h]
0x140015e5e  test    rax, rax
0x140015e61  jz      short loc_140015EA7
0x140015e63  lea     rbp, [rdi+10h]
0x140015e67  mov     rcx, [rbx+2A8h]
0x140015e6e  mov     rdx, rax; ListEntry
0x140015e71  mov     rdi, [rax]
0x140015e74  lock dec dword ptr [rcx+rbp]
0x140015e78  mov     ecx, [rax+16Ch]
0x140015e7e  shl     rcx, 6
0x140015e82  mov     dword ptr [rax+170h], 0FFFFFFFFh
0x140015e8c  add     rcx, [rbx+600h]; ListHead
0x140015e93  call    cs:__imp_ExpInterlockedPushEntrySList
0x140015e9a  nop     dword ptr [rax+rax+00h]
0x140015e9f  mov     rax, rdi
0x140015ea2  test    rdi, rdi
0x140015ea5  jnz     short loc_140015E67
0x140015ea7  inc     esi
0x140015ea9  cmp     esi, r14d
0x140015eac  jb      loc_140015E20
0x140015eb2  xor     ebp, ebp
0x140015eb4  test    r13d, r13d
0x140015eb7  jz      loc_140015FDB
0x140015ebd  mov     [rsp+48h+var_28], r15
0x140015ec2  xor     r14d, r14d
0x140015ec5  mov     rcx, [rbx+600h]
0x140015ecc  mov     rsi, r14
0x140015ecf  shl     rsi, 6
0x140015ed3  add     rcx, rsi; SListHead
0x140015ed6  call    cs:__imp_ExQueryDepthSList
0x140015edd  nop     dword ptr [rax+rax+00h]
0x140015ee2  mov     rcx, [rbx+600h]
0x140015ee9  movzx   r8d, ax
0x140015eed  mov     r10d, [rcx+rsi+10h]
0x140015ef2  cmp     r8d, r10d
0x140015ef5  jb      short loc_140015F03
0x140015ef7  mov     r9d, [rbx+500h]
0x140015efe  cmp     r8d, r9d
0x140015f01  ja      short loc_140015F0B
0x140015f03  xor     r12b, r12b
0x140015f06  jmp     loc_140015FC8
0x140015f0b  mov     r15d, [rbx+504h]
0x140015f12  cmp     r8d, r15d
0x140015f15  ja      short loc_140015F46
0x140015f17  mov     edx, r8d
0x140015f1a  sub     edx, r9d
0x140015f1d  cmp     edx, 0AAh
0x140015f23  jb      loc_14001605D
0x140015f29  mov     eax, 0CCCCCCCDh
0x140015f2e  mul     edx
0x140015f30  shr     edx, 3
0x140015f33  lea     eax, [r9+rdx]
0x140015f37  cmp     eax, r8d
0x140015f3a  jnb     loc_140016055
0x140015f40  mov     r15d, r8d
0x140015f43  sub     r15d, edx
0x140015f46  xor     r12b, r12b
0x140015f49  cmp     r15d, r10d
0x140015f4c  jnb     short loc_140015FAF
0x140015f4e  xchg    ax, ax
0x140015f50  mov     edi, [rsi+rcx+10h]
0x140015f54  add     rcx, rsi; SListHead
0x140015f57  call    cs:__imp_ExQueryDepthSList
0x140015f5e  nop     dword ptr [rax+rax+00h]
0x140015f63  movzx   eax, ax
0x140015f66  cmp     eax, edi
0x140015f68  jb      short loc_140015FAF
0x140015f6a  mov     rcx, [rbx+600h]
0x140015f71  add     rcx, rsi; ListHead
0x140015f74  call    cs:__imp_ExpInterlockedPopEntrySList
0x140015f7b  nop     dword ptr [rax+rax+00h]
0x140015f80  test    rax, rax
0x140015f83  jz      short loc_140015FAF
0x140015f85  mov     qword ptr [rax], 0
0x140015f8c  mov     rcx, [rbx+600h]
0x140015f93  lock dec dword ptr [rsi+rcx+10h]
0x140015f98  lea     rcx, [rax-10h]; P
0x140015f9c  call    DestroyTransferPacket
0x140015fa1  mov     rcx, [rbx+600h]
0x140015fa8  cmp     r15d, [rcx+rsi+10h]
0x140015fad  jb      short loc_140015F50
0x140015faf  mov     rcx, [rbx+600h]
0x140015fb6  xor     edx, edx
0x140015fb8  movzx   eax, r12b
0x140015fbc  cmp     r15d, [rsi+rcx+10h]
0x140015fc1  cmovz   edx, eax
0x140015fc4  movzx   r12d, dl
0x140015fc8  inc     ebp
0x140015fca  inc     r14
0x140015fcd  cmp     ebp, r13d
0x140015fd0  jb      loc_140015EC5
0x140015fd6  mov     r15, [rsp+48h+var_28]
0x140015fdb  mov     r14, [rsp+48h+var_20]
0x140015fe0  test    r12b, r12b
0x140015fe3  mov     r12, [rsp+48h+var_10]
0x140015fe8  mov     r13, [rsp+48h+var_18]
0x140015fed  mov     rsi, [rsp+48h+arg_10]
0x140015ff2  mov     rbp, [rsp+48h+arg_8]
0x140015ff7  jz      short loc_14001603D
0x140015ff9  lea     rcx, [rbx+1F0h]; PKTIMER
0x140016000  call    cs:__imp_KeCancelTimer
0x140016007  nop     dword ptr [rax+rax+00h]
0x14001600c  lea     rcx, [rbx+618h]; SpinLock
0x140016013  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001601a  nop     dword ptr [rax+rax+00h]
0x14001601f  lock and dword ptr [rbx+298h], 0FFFFFFF7h
0x140016027  movzx   edx, al; NewIrql
0x14001602a  lea     rcx, [rbx+618h]; SpinLock
0x140016031  call    cs:__imp_KeReleaseSpinLock
0x140016038  nop     dword ptr [rax+rax+00h]
0x14001603d  mov     rdi, [rsp+48h+var_8]
0x140016042  mov     rbx, [rsp+48h+arg_0]
0x140016047  add     rsp, 48h
0x14001604b  retn
0x14001604d  xor     r12b, r12b
0x140016050  jmp     loc_140015EA7
0x140016055  mov     r15d, r9d
0x140016058  jmp     loc_140015F49
0x14001605d  mov     edx, 10h
0x140016062  jmp     loc_140015F33
```
