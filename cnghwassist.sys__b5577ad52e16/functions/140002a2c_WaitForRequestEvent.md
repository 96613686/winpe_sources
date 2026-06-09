# WaitForRequestEvent

- ea: `0x140002a2c`
- end: `0x140002c42`
- name: `WaitForRequestEvent`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001430`

## callees

- `0x14000292c`
- `0x140002a2c`
- `0x140003aa8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002a5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002c0e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002a5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002c0e`
- `ntoskrnl!KeSetEvent` at `0x140002b66`
- `ntoskrnl!KeSetEvent` at `0x140002b66`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140002bd7`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140002bd7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002acb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002acb`
- `ntoskrnl!KeQueryPriorityThread` at `0x140002ab6`
- `ntoskrnl!KeQueryPriorityThread` at `0x140002ab6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002bed`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002bed`
- `ntoskrnl!KeClearEvent` at `0x140002c28`
- `ntoskrnl!KeClearEvent` at `0x140002c28`

## pseudocode

```c
void __fastcall WaitForRequestEvent(__int64 a1)
{
  struct _KEVENT *v1; // rsi
  unsigned int PriorityThread; // edi
  KIRQL v4; // al
  int v5; // ecx
  KIRQL v6; // bp
  __int64 v7; // rax
  unsigned int v8; // edx
  unsigned int v9; // ecx
  __int64 v10; // r8
  __int64 v11; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+8h] BYREF

  v1 = (struct _KEVENT *)(a1 + 104);
  Timeout.QuadPart = -50000000;
  while ( KeWaitForSingleObject(v1, Executive, 0, 0, &Timeout) == 258 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_390e2dc370203258022970013e7d63eb_Traceguids,
        *(unsigned int *)(a1 + 156));
    PriorityThread = KeQueryPriorityThread(*(PKTHREAD *)(a1 + 96));
    v4 = KeAcquireSpinLockRaiseToDpc(&g_spinlock);
    v5 = *(_DWORD *)(a1 + 152);
    v6 = v4;
    if ( v5 == 6 )
    {
      if ( *(_DWORD *)(a1 + 128) != PriorityThread )
      {
        removeRequestFromPriorityQueue(a1);
        *(_DWORD *)(a1 + 128) = PriorityThread;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
            *(unsigned int *)(a1 + 156));
        v7 = *(unsigned int *)(a1 + 128);
        *(_DWORD *)(a1 + 152) = 1;
        ++g_SwThreadsRunning[v7];
        if ( g_maxPrioritySoftware <= (unsigned int)v7 )
          g_maxPrioritySoftware = v7;
        ++g_nSwThreadsRunning;
        KeSetEvent(v1, 0, 0);
      }
    }
    else if ( v5 == 5 && *(_DWORD *)(a1 + 128) != PriorityThread )
    {
      v8 = g_actualHardwareThreads;
      v9 = 0;
      *(_DWORD *)(a1 + 128) = PriorityThread;
      if ( v8 )
      {
        while ( 1 )
        {
          v10 = 7LL * v9;
          if ( g_hwEngineState[v10] == a1 )
            break;
          if ( ++v9 >= v8 )
            goto LABEL_24;
        }
        if ( dword_1400077F4[0] )
        {
          if ( PriorityThread < 0xE )
            ++PriorityThread;
          if ( LODWORD(g_hwEngineState[v10 + 3]) < PriorityThread )
          {
            v11 = g_hwEngineState[v10 + 2];
            LODWORD(g_hwEngineState[v10 + 3]) = PriorityThread;
            KeSetActualBasePriorityThread(v11, PriorityThread);
          }
        }
      }
    }
LABEL_24:
    KeReleaseSpinLock(&g_spinlock, v6);
  }
  KeClearEvent(v1);
}

```

## disassembly

```asm
0x140002a2c  push    rbx
0x140002a2e  push    rbp
0x140002a2f  push    rsi
0x140002a30  push    rdi
0x140002a31  push    r12
0x140002a33  push    r14
0x140002a35  sub     rsp, 38h
0x140002a39  lea     rsi, [rcx+68h]
0x140002a3d  mov     qword ptr [rsp+68h+arg_0], 0FFFFFFFFFD050F80h
0x140002a46  mov     rbx, rcx
0x140002a49  lea     rax, [rsp+68h+arg_0]
0x140002a4e  mov     rcx, rsi; Object
0x140002a51  mov     [rsp+68h+Timeout], rax; Timeout
0x140002a56  xor     r9d, r9d; Alertable
0x140002a59  xor     r8d, r8d; WaitMode
0x140002a5c  xor     edx, edx; WaitReason
0x140002a5e  call    cs:__imp_KeWaitForSingleObject
0x140002a65  nop     dword ptr [rax+rax+00h]
0x140002a6a  cmp     eax, 102h
0x140002a6f  jnz     loc_140002C25
0x140002a75  lea     r12, WPP_GLOBAL_Control
0x140002a7c  lea     r14, cs:140000000h
0x140002a83  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a8a  cmp     rcx, r12
0x140002a8d  jz      short loc_140002AB2
0x140002a8f  mov     eax, [rcx+2Ch]
0x140002a92  test    al, 4
0x140002a94  jz      short loc_140002AB2
0x140002a96  mov     r9d, [rbx+9Ch]
0x140002a9d  lea     r8, WPP_390e2dc370203258022970013e7d63eb_Traceguids
0x140002aa4  mov     rcx, [rcx+18h]
0x140002aa8  mov     edx, 0Ch
0x140002aad  call    WPP_SF_D
0x140002ab2  mov     rcx, [rbx+60h]; Thread
0x140002ab6  call    cs:__imp_KeQueryPriorityThread
0x140002abd  nop     dword ptr [rax+rax+00h]
0x140002ac2  lea     rcx, g_spinlock; SpinLock
0x140002ac9  mov     edi, eax
0x140002acb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002ad2  nop     dword ptr [rax+rax+00h]
0x140002ad7  mov     ecx, [rbx+98h]
0x140002add  mov     bpl, al
0x140002ae0  cmp     ecx, 6
0x140002ae3  jnz     loc_140002B74
0x140002ae9  cmp     [rbx+80h], edi
0x140002aef  jz      loc_140002BE3
0x140002af5  mov     rcx, rbx
0x140002af8  call    removeRequestFromPriorityQueue
0x140002afd  mov     [rbx+80h], edi
0x140002b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b0a  cmp     rcx, r12
0x140002b0d  jz      short loc_140002B32
0x140002b0f  mov     eax, [rcx+2Ch]
0x140002b12  test    al, 4
0x140002b14  jz      short loc_140002B32
0x140002b16  mov     r9d, [rbx+9Ch]
0x140002b1d  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x140002b24  mov     rcx, [rcx+18h]
0x140002b28  mov     edx, 16h
0x140002b2d  call    WPP_SF_D
0x140002b32  mov     eax, [rbx+80h]
0x140002b38  mov     dword ptr [rbx+98h], 1
0x140002b42  inc     rva g_SwThreadsRunning[r14+rax*4]
0x140002b4a  cmp     cs:g_maxPrioritySoftware, eax
0x140002b50  ja      short loc_140002B58
0x140002b52  mov     cs:g_maxPrioritySoftware, eax
0x140002b58  inc     cs:g_nSwThreadsRunning
0x140002b5e  xor     r8d, r8d; Wait
0x140002b61  xor     edx, edx; Increment
0x140002b63  mov     rcx, rsi; Event
0x140002b66  call    cs:__imp_KeSetEvent
0x140002b6d  nop     dword ptr [rax+rax+00h]
0x140002b72  jmp     short loc_140002BE3
0x140002b74  cmp     ecx, 5
0x140002b77  jnz     short loc_140002BE3
0x140002b79  cmp     [rbx+80h], edi
0x140002b7f  jz      short loc_140002BE3
0x140002b81  mov     edx, cs:g_actualHardwareThreads
0x140002b87  xor     ecx, ecx
0x140002b89  mov     [rbx+80h], edi
0x140002b8f  test    edx, edx
0x140002b91  jz      short loc_140002BE3
0x140002b93  mov     eax, ecx
0x140002b95  imul    r8, rax, 38h ; '8'
0x140002b99  cmp     [r8+r14+7660h], rbx
0x140002ba1  jz      short loc_140002BAB
0x140002ba3  inc     ecx
0x140002ba5  cmp     ecx, edx
0x140002ba7  jb      short loc_140002B93
0x140002ba9  jmp     short loc_140002BE3
0x140002bab  cmp     cs:dword_1400077F4, 0
0x140002bb2  jz      short loc_140002BE3
0x140002bb4  cmp     edi, 0Eh
0x140002bb7  jnb     short loc_140002BBB
0x140002bb9  inc     edi
0x140002bbb  cmp     [r8+r14+7678h], edi
0x140002bc3  jnb     short loc_140002BE3
0x140002bc5  mov     rcx, [r8+r14+7670h]
0x140002bcd  mov     edx, edi
0x140002bcf  mov     [r8+r14+7678h], edi
0x140002bd7  call    cs:__imp_KeSetActualBasePriorityThread
0x140002bde  nop     dword ptr [rax+rax+00h]
0x140002be3  mov     dl, bpl; NewIrql
0x140002be6  lea     rcx, g_spinlock; SpinLock
0x140002bed  call    cs:__imp_KeReleaseSpinLock
0x140002bf4  nop     dword ptr [rax+rax+00h]
0x140002bf9  lea     rax, [rsp+68h+arg_0]
0x140002bfe  xor     r9d, r9d; Alertable
0x140002c01  xor     r8d, r8d; WaitMode
0x140002c04  mov     [rsp+68h+Timeout], rax; Timeout
0x140002c09  xor     edx, edx; WaitReason
0x140002c0b  mov     rcx, rsi; Object
0x140002c0e  call    cs:__imp_KeWaitForSingleObject
0x140002c15  nop     dword ptr [rax+rax+00h]
0x140002c1a  cmp     eax, 102h
0x140002c1f  jz      loc_140002A83
0x140002c25  mov     rcx, rsi; Event
0x140002c28  call    cs:__imp_KeClearEvent
0x140002c2f  nop     dword ptr [rax+rax+00h]
0x140002c34  add     rsp, 38h
0x140002c38  pop     r14
0x140002c3a  pop     r12
0x140002c3c  pop     rdi
0x140002c3d  pop     rsi
0x140002c3e  pop     rbp
0x140002c3f  pop     rbx
0x140002c40  retn
```
