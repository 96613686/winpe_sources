# KsecpGetRpcConnection

- ea: `0x180001ae4`
- end: `0x180001beb`
- name: `KsecpGetRpcConnection`
- size: `263`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800018b0`
- `0x180001a98`
- `0x180004074`

## callees

- `0x180001ae4`
- `0x180001c00`
- `0x180001cf0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180001b35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180001b7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180001b35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180001b7f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001b6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001bda`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001b6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180001bda`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180001b4a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180001b94`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180001b4a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180001b94`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180001b63`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180001bce`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180001b63`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180001bce`
- `ntoskrnl!PsGetCurrentProcess` at `0x180001aee`
- `ntoskrnl!PsGetCurrentProcess` at `0x180001aee`

## pseudocode

```c
__int64 __fastcall KsecpGetRpcConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID CurrentProcess; // rbx
  __int64 v5; // rbx
  __int64 v6; // rdi
  unsigned int i; // eax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  CurrentProcess = (PVOID)PsGetCurrentProcess(a1, a2, a3, a4);
  if ( CurrentProcess == WPP_MAIN_CB.DeviceExtension )
  {
    KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v9);
    v5 = v9;
    v6 = 0;
    if ( v9 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(&KsecRpcLock, 0);
      v6 = *(_QWORD *)(v5 + 16);
      ExReleasePushLockSharedEx(&KsecRpcLock, 0);
      KeLeaveCriticalRegion();
    }
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v9);
  }
  else
  {
    v6 = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(&KsecRpcLock, 0);
    for ( i = 0; i < KsecRpcConnectionsCount; ++i )
    {
      if ( *((PVOID *)KsecRpcConnections + 2 * i) == CurrentProcess )
      {
        v6 = *((_QWORD *)KsecRpcConnections + 2 * i + 1);
        break;
      }
    }
    ExReleasePushLockSharedEx(&KsecRpcLock, 0);
    KeLeaveCriticalRegion();
  }
  return v6;
}

```

## disassembly

```asm
0x180001ae4  mov     [rsp+arg_8], rbx
0x180001ae9  push    rdi
0x180001aea  sub     rsp, 20h
0x180001aee  call    cs:__imp_PsGetCurrentProcess
0x180001af5  nop     dword ptr [rax+rax+00h]
0x180001afa  cmp     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180001b01  mov     rbx, rax
0x180001b04  jnz     short loc_180001B7D
0x180001b06  lea     rcx, [rsp+28h+arg_0]; this
0x180001b0b  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180001b10  mov     rbx, [rsp+28h+arg_0]
0x180001b15  xor     edi, edi
0x180001b17  test    rbx, rbx
0x180001b1a  jnz     short loc_180001B35
0x180001b1c  lea     rcx, [rsp+28h+arg_0]; this
0x180001b21  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180001b26  mov     rbx, [rsp+28h+arg_8]
0x180001b2b  mov     rax, rdi
0x180001b2e  add     rsp, 20h
0x180001b32  pop     rdi
0x180001b33  retn
0x180001b35  call    cs:__imp_KeEnterCriticalRegion
0x180001b3c  nop     dword ptr [rax+rax+00h]
0x180001b41  xor     edx, edx
0x180001b43  lea     rcx, ?KsecRpcLock@@3U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK KsecRpcLock
0x180001b4a  call    cs:__imp_ExAcquirePushLockSharedEx
0x180001b51  nop     dword ptr [rax+rax+00h]
0x180001b56  mov     rdi, [rbx+10h]
0x180001b5a  lea     rcx, ?KsecRpcLock@@3U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK KsecRpcLock
0x180001b61  xor     edx, edx
0x180001b63  call    cs:__imp_ExReleasePushLockSharedEx
0x180001b6a  nop     dword ptr [rax+rax+00h]
0x180001b6f  call    cs:__imp_KeLeaveCriticalRegion
0x180001b76  nop     dword ptr [rax+rax+00h]
0x180001b7b  jmp     short loc_180001B1C
0x180001b7d  xor     edi, edi
0x180001b7f  call    cs:__imp_KeEnterCriticalRegion
0x180001b86  nop     dword ptr [rax+rax+00h]
0x180001b8b  xor     edx, edx
0x180001b8d  lea     rcx, ?KsecRpcLock@@3U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK KsecRpcLock
0x180001b94  call    cs:__imp_ExAcquirePushLockSharedEx
0x180001b9b  nop     dword ptr [rax+rax+00h]
0x180001ba0  mov     eax, edi
0x180001ba2  cmp     eax, cs:?KsecRpcConnectionsCount@@3KA; ulong KsecRpcConnectionsCount
0x180001ba8  jnb     short loc_180001BC5
0x180001baa  mov     rdx, cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA; _KSEC_RPC_CONNECTION * KsecRpcConnections
0x180001bb1  mov     ecx, eax
0x180001bb3  add     rcx, rcx
0x180001bb6  cmp     [rdx+rcx*8], rbx
0x180001bba  jz      short loc_180001BC0
0x180001bbc  inc     eax
0x180001bbe  jmp     short loc_180001BA2
0x180001bc0  mov     rdi, [rdx+rcx*8+8]
0x180001bc5  xor     edx, edx
0x180001bc7  lea     rcx, ?KsecRpcLock@@3U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK KsecRpcLock
0x180001bce  call    cs:__imp_ExReleasePushLockSharedEx
0x180001bd5  nop     dword ptr [rax+rax+00h]
0x180001bda  call    cs:__imp_KeLeaveCriticalRegion
0x180001be1  nop     dword ptr [rax+rax+00h]
0x180001be6  jmp     loc_180001B26
```
