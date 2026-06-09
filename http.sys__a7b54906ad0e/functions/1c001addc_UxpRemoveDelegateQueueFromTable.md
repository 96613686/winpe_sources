# UxpRemoveDelegateQueueFromTable

- ea: `0x1c001addc`
- end: `0x1c001aec7`
- name: `UxpRemoveDelegateQueueFromTable`
- size: `235`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1c0109cb4`

## callees

- `0x1c001addc`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c00a93f4`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1c001ae5a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1c001ae5a`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1c001ae3a`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1c001ae3a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c001ae80`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c001ae80`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c001ae26`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c001ae26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c001ae8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c001ae8c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c001ae14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c001ae14`

## pseudocode

```c
__int64 __fastcall UxpRemoveDelegateQueueFromTable(PRTL_AVL_TABLE Table, PSECURITY_DESCRIPTOR *P)
{
  PVOID v4; // rax
  unsigned int v5; // ebx
  PSECURITY_DESCRIPTOR *Buffer; // [rsp+48h] [rbp+10h] BYREF

  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qq(25, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, Table, P);
  Buffer = P;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&Table[1], 0);
  v4 = RtlLookupElementGenericTableAvl(Table, &Buffer);
  v5 = 0;
  if ( v4 )
  {
    RtlDeleteElementGenericTableAvl(Table, v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 1 )
      UlFreeRequestQueue(P);
  }
  else
  {
    v5 = -1073741275;
  }
  ExReleasePushLockExclusiveEx(&Table[1], 0);
  KeLeaveCriticalRegion();
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_D(26, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x1c001addc  mov     [rsp+arg_10], rbx
0x1c001ade1  push    rbp
0x1c001ade2  push    rsi
0x1c001ade3  push    rdi
0x1c001ade4  sub     rsp, 20h
0x1c001ade8  mov     rdi, rdx
0x1c001adeb  mov     rsi, rcx
0x1c001adee  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c001adf4  test    al, 8
0x1c001adf6  jz      short loc_1C001AE0F
0x1c001adf8  mov     r9, rdx
0x1c001adfb  mov     ecx, 19h
0x1c001ae00  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c001ae07  mov     r8, rsi
0x1c001ae0a  call    WPP_SF_qq
0x1c001ae0f  mov     [rsp+38h+Buffer], rdi
0x1c001ae14  call    cs:__imp_KeEnterCriticalRegion
0x1c001ae1b  nop     dword ptr [rax+rax+00h]
0x1c001ae20  xor     edx, edx
0x1c001ae22  lea     rcx, [rsi+68h]
0x1c001ae26  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c001ae2d  nop     dword ptr [rax+rax+00h]
0x1c001ae32  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1c001ae37  mov     rcx, rsi; Table
0x1c001ae3a  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1c001ae41  nop     dword ptr [rax+rax+00h]
0x1c001ae46  xor     ebx, ebx
0x1c001ae48  test    rax, rax
0x1c001ae4b  jnz     short loc_1C001AE54
0x1c001ae4d  mov     ebx, 0C0000225h
0x1c001ae52  jmp     short loc_1C001AE7A
0x1c001ae54  mov     rdx, rax; Buffer
0x1c001ae57  mov     rcx, rsi; Table
0x1c001ae5a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1c001ae61  nop     dword ptr [rax+rax+00h]
0x1c001ae66  or      eax, 0FFFFFFFFh
0x1c001ae69  lock xadd [rdi], eax
0x1c001ae6d  cmp     eax, 1
0x1c001ae70  jnz     short loc_1C001AE7A
0x1c001ae72  mov     rcx, rdi; P
0x1c001ae75  call    UlFreeRequestQueue
0x1c001ae7a  xor     edx, edx
0x1c001ae7c  lea     rcx, [rsi+68h]
0x1c001ae80  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c001ae87  nop     dword ptr [rax+rax+00h]
0x1c001ae8c  call    cs:__imp_KeLeaveCriticalRegion
0x1c001ae93  nop     dword ptr [rax+rax+00h]
0x1c001ae98  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue
0x1c001ae9e  test    cl, 8
0x1c001aea1  jz      short loc_1C001AEB7
0x1c001aea3  mov     ecx, 1Ah
0x1c001aea8  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c001aeaf  mov     r8d, ebx
0x1c001aeb2  call    WPP_SF_D
0x1c001aeb7  mov     eax, ebx
0x1c001aeb9  mov     rbx, [rsp+38h+arg_10]
0x1c001aebe  add     rsp, 20h
0x1c001aec2  pop     rdi
0x1c001aec3  pop     rsi
0x1c001aec4  pop     rbp
0x1c001aec5  retn
```
