# KsecpRemoveRpcConnection(_EPROCESS *)

- ea: `0x18000150c`
- end: `0x1800017bb`
- name: `?KsecpRemoveRpcConnection@@YAPEAXPEAU_EPROCESS@@@Z`
- size: `687`
- prototype: `void *__fastcall(struct _EPROCESS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001478`

## callees

- `0x18000150c`
- `0x180001c00`
- `0x180001cf0`
- `0x180010980`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000154d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800016c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000174b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000154d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800016c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000174b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800016dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000175c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800016dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000175c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000168e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800016f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000168e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800016f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800015ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001705`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000173f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800015ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001705`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000173f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180001565`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180001565`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800015be`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180001733`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800015be`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180001733`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x18000171e`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x18000171e`
- `ntoskrnl!PsGetCurrentProcess` at `0x180001520`
- `ntoskrnl!PsGetCurrentProcess` at `0x180001520`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000166f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000166f`
- `ntoskrnl!ExAllocatePool2` at `0x180001634`
- `ntoskrnl!ExAllocatePool2` at `0x180001634`

## pseudocode

```c
__int64 __fastcall KsecpRemoveRpcConnection(struct _EPROCESS *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rsi
  int v6; // r12d
  unsigned int i; // ebx
  unsigned int v8; // r15d
  __int64 v9; // rbp
  unsigned int v11; // r8d
  unsigned int v12; // r14d
  void *Pool2; // rax
  void *v14; // rbp
  __int64 v15; // rbx
  __int64 v16; // [rsp+78h] [rbp+10h] BYREF

  if ( (PVOID)PsGetCurrentProcess(a1, a2, a3, a4) == WPP_MAIN_CB.DeviceExtension )
  {
    KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
    v15 = v16;
    if ( v16 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(&KsecRpcLock, 0);
      v5 = *(_QWORD *)(v15 + 16);
      *(_QWORD *)(v15 + 16) = 0;
      ExReleasePushLockExclusiveEx(&KsecRpcLock, 0);
      KeLeaveCriticalRegion();
    }
    else
    {
      v5 = 0;
    }
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
    return v5;
  }
  if ( KsecRpcConnectionsCount )
  {
    v5 = 0;
    v6 = 0;
    i = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(&KsecRpcLock, 0);
    v8 = 1;
    while ( 2 )
    {
      if ( v8 <= 2 )
      {
        v5 = 0;
        for ( i = 0; ; ++i )
        {
          if ( i >= KsecRpcConnectionsCount )
            goto LABEL_10;
          if ( a1 == *((struct _EPROCESS **)KsecRpcConnections + 2 * i) )
            break;
        }
        v9 = *((_QWORD *)KsecRpcConnections + 2 * i + 1);
        v5 = v9;
        if ( !v9 )
          goto LABEL_10;
        if ( v8 != 1 )
        {
LABEL_29:
          ++v8;
          v5 = v9;
          continue;
        }
        if ( (unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(&KsecRpcLock, 0) )
        {
          v6 = 1;
        }
        else
        {
          ExReleasePushLockSharedEx(&KsecRpcLock, 0);
          KeLeaveCriticalRegion();
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(&KsecRpcLock, 0);
          v6 = 1;
          if ( i >= KsecRpcConnectionsCount || a1 != *((struct _EPROCESS **)KsecRpcConnections + 2 * i) )
            goto LABEL_29;
        }
      }
      break;
    }
    v11 = KsecRpcConnectionsCount;
    if ( KsecRpcConnectionsCount > 1 )
      *((_OWORD *)KsecRpcConnections + i) = *((_OWORD *)KsecRpcConnections + KsecRpcConnectionsCount - 1);
    KsecRpcConnectionsCount = v11 - 1;
    if ( v11 - 1 + 512 < KsecRpcConnectionsSize )
    {
      v12 = KsecRpcConnectionsSize - 256;
      Pool2 = (void *)ExAllocatePool2(256, 16LL * (KsecRpcConnectionsSize - 256), 1667593035);
      v14 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, KsecRpcConnections, 16LL * KsecRpcConnectionsCount);
        ExFreePoolWithTag(KsecRpcConnections, 0);
        KsecRpcConnections = v14;
        KsecRpcConnectionsSize = v12;
      }
    }
LABEL_10:
    if ( v6 )
      ExReleasePushLockExclusiveEx(&KsecRpcLock, 0);
    else
      ExReleasePushLockSharedEx(&KsecRpcLock, 0);
    KeLeaveCriticalRegion();
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000150c  push    rbx
0x18000150e  push    rbp
0x18000150f  push    rsi
0x180001510  push    rdi
0x180001511  push    r12
0x180001513  push    r13
0x180001515  push    r14
0x180001517  push    r15
0x180001519  sub     rsp, 28h
0x18000151d  mov     r13, rcx
0x180001520  call    cs:__imp_PsGetCurrentProcess
0x180001527  nop     dword ptr [rax+rax+00h]
0x18000152c  cmp     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180001533  jz      loc_18000169F
0x180001539  cmp     cs:?KsecRpcConnectionsCount@@3KA, 0; ulong KsecRpcConnectionsCount
0x180001540  jz      loc_1800015EB
0x180001546  xor     esi, esi
0x180001548  xor     r12d, r12d
0x18000154b  xor     ebx, ebx
0x18000154d  call    cs:__imp_KeEnterCriticalRegion
0x180001554  nop     dword ptr [rax+rax+00h]
0x180001559  lea     rdi, ?KsecRpcLock@@3U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK KsecRpcLock
0x180001560  xor     edx, edx
0x180001562  mov     rcx, rdi
0x180001565  call    cs:__imp_ExAcquirePushLockSharedEx
0x18000156c  nop     dword ptr [rax+rax+00h]
0x180001571  lea     r15d, [rsi+1]
0x180001575  cmp     r15d, 2
0x180001579  ja      short loc_1800015EF
0x18000157b  xor     esi, esi
0x18000157d  xor     ebx, ebx
0x18000157f  cmp     ebx, cs:?KsecRpcConnectionsCount@@3KA; ulong KsecRpcConnectionsCount
0x180001585  jnb     short loc_1800015B0
0x180001587  mov     rbp, cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA; _KSEC_RPC_CONNECTION * KsecRpcConnections
0x18000158e  mov     r14d, ebx
0x180001591  add     r14, r14
0x180001594  cmp     r13, [rbp+r14*8+0]
0x180001599  jz      short loc_18000159F
0x18000159b  inc     ebx
0x18000159d  jmp     short loc_18000157F
0x18000159f  mov     rbp, [rbp+r14*8+8]
0x1800015a4  mov     rsi, rbp
0x1800015a7  test    rbp, rbp
0x1800015aa  jnz     loc_180001713
0x1800015b0  xor     edx, edx
0x1800015b2  mov     rcx, rdi
0x1800015b5  test    r12d, r12d
0x1800015b8  jnz     loc_18000168E
0x1800015be  call    cs:__imp_ExReleasePushLockSharedEx
0x1800015c5  nop     dword ptr [rax+rax+00h]
0x1800015ca  call    cs:__imp_KeLeaveCriticalRegion
0x1800015d1  nop     dword ptr [rax+rax+00h]
0x1800015d6  mov     rax, rsi
0x1800015d9  add     rsp, 28h
0x1800015dd  pop     r15
0x1800015df  pop     r14
0x1800015e1  pop     r13
0x1800015e3  pop     r12
0x1800015e5  pop     rdi
0x1800015e6  pop     rsi
0x1800015e7  pop     rbp
0x1800015e8  pop     rbx
0x1800015e9  retn
0x1800015eb  xor     eax, eax
0x1800015ed  jmp     short loc_1800015D9
0x1800015ef  mov     r8d, cs:?KsecRpcConnectionsCount@@3KA; ulong KsecRpcConnectionsCount
0x1800015f6  cmp     r8d, 1
0x1800015fa  ja      loc_18000179A
0x180001600  mov     ecx, cs:?KsecRpcConnectionsSize@@3KA; ulong KsecRpcConnectionsSize
0x180001606  dec     r8d
0x180001609  mov     cs:?KsecRpcConnectionsCount@@3KA, r8d; ulong KsecRpcConnectionsCount
0x180001610  lea     eax, [r8+200h]
0x180001617  cmp     eax, ecx
0x180001619  jnb     short loc_1800015B0
0x18000161b  lea     r14d, [rcx-100h]
0x180001622  mov     r8d, 6365734Bh
0x180001628  mov     edx, r14d
0x18000162b  mov     ecx, 100h
0x180001630  shl     rdx, 4
0x180001634  call    cs:__imp_ExAllocatePool2
0x18000163b  nop     dword ptr [rax+rax+00h]
0x180001640  mov     rbp, rax
0x180001643  test    rax, rax
0x180001646  jz      loc_1800015B0
0x18000164c  mov     r8d, cs:?KsecRpcConnectionsCount@@3KA; ulong KsecRpcConnectionsCount
0x180001653  mov     rcx, rax; void *
0x180001656  mov     rdx, cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA; Src
0x18000165d  shl     r8, 4; Size
0x180001661  call    memmove
0x180001666  mov     rcx, cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA; P
0x18000166d  xor     edx, edx; Tag
0x18000166f  call    cs:__imp_ExFreePoolWithTag
0x180001676  nop     dword ptr [rax+rax+00h]
0x18000167b  mov     cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA, rbp; _KSEC_RPC_CONNECTION * KsecRpcConnections
0x180001682  mov     cs:?KsecRpcConnectionsSize@@3KA, r14d; ulong KsecRpcConnectionsSize
0x180001689  jmp     loc_1800015B0
0x18000168e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180001695  nop     dword ptr [rax+rax+00h]
0x18000169a  jmp     loc_1800015CA
0x18000169f  lea     rcx, [rsp+68h+arg_8]; this
0x1800016a4  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800016a9  mov     rbx, [rsp+68h+arg_8]
0x1800016ae  test    rbx, rbx
0x1800016b1  jnz     short loc_1800016C4
0x1800016b3  xor     esi, esi
0x1800016b5  lea     rcx, [rsp+68h+arg_8]; this
0x1800016ba  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800016bf  jmp     loc_1800015D6
0x1800016c4  call    cs:__imp_KeEnterCriticalRegion
0x1800016cb  nop     dword ptr [rax+rax+00h]
0x1800016d0  lea     rdi, ?KsecRpcLock@@3U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK KsecRpcLock
0x1800016d7  xor     edx, edx
0x1800016d9  mov     rcx, rdi
0x1800016dc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800016e3  nop     dword ptr [rax+rax+00h]
0x1800016e8  mov     rsi, [rbx+10h]
0x1800016ec  xor     edx, edx
0x1800016ee  mov     rcx, rdi
0x1800016f1  mov     qword ptr [rbx+10h], 0
0x1800016f9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180001700  nop     dword ptr [rax+rax+00h]
0x180001705  call    cs:__imp_KeLeaveCriticalRegion
0x18000170c  nop     dword ptr [rax+rax+00h]
0x180001711  jmp     short loc_1800016B5
0x180001713  cmp     r15d, 1
0x180001717  jnz     short loc_180001784
0x180001719  xor     edx, edx
0x18000171b  mov     rcx, rdi
0x18000171e  call    cs:__imp_ExTryConvertPushLockSharedToExclusiveEx
0x180001725  nop     dword ptr [rax+rax+00h]
0x18000172a  test    al, al
0x18000172c  jnz     short loc_18000178F
0x18000172e  xor     edx, edx
0x180001730  mov     rcx, rdi
0x180001733  call    cs:__imp_ExReleasePushLockSharedEx
0x18000173a  nop     dword ptr [rax+rax+00h]
0x18000173f  call    cs:__imp_KeLeaveCriticalRegion
0x180001746  nop     dword ptr [rax+rax+00h]
0x18000174b  call    cs:__imp_KeEnterCriticalRegion
0x180001752  nop     dword ptr [rax+rax+00h]
0x180001757  xor     edx, edx
0x180001759  mov     rcx, rdi
0x18000175c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180001763  nop     dword ptr [rax+rax+00h]
0x180001768  cmp     ebx, cs:?KsecRpcConnectionsCount@@3KA; ulong KsecRpcConnectionsCount
0x18000176e  mov     r12d, r15d
0x180001771  jnb     short loc_180001784
0x180001773  mov     rax, cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA; _KSEC_RPC_CONNECTION * KsecRpcConnections
0x18000177a  cmp     r13, [rax+r14*8]
0x18000177e  jz      loc_1800015EF
0x180001784  inc     r15d
0x180001787  mov     rsi, rbp
0x18000178a  jmp     loc_180001575
0x18000178f  mov     r12d, 1
0x180001795  jmp     loc_1800015EF
0x18000179a  mov     rax, cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA; _KSEC_RPC_CONNECTION * KsecRpcConnections
0x1800017a1  lea     ecx, [r8-1]
0x1800017a5  add     rcx, rcx
0x1800017a8  mov     edx, ebx
0x1800017aa  add     rdx, rdx
0x1800017ad  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800017b1  movdqu  xmmword ptr [rax+rdx*8], xmm0
0x1800017b6  jmp     loc_180001600
```
