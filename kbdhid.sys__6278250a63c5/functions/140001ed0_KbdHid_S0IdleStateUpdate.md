# KbdHid_S0IdleStateUpdate

- ea: `0x140001ed0`
- end: `0x140002127`
- name: `KbdHid_S0IdleStateUpdate`
- size: `599`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1400010c0`
- `0x140001300`
- `0x140001d30`
- `0x140001db0`

## callees

- `0x140001ed0`
- `0x140002130`
- `0x1400052a0`
- `0x140005a0c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002031`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002031`
- `ntoskrnl!IoQueueWorkItem` at `0x140001fd4`
- `ntoskrnl!IoQueueWorkItem` at `0x140001fd4`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140002060`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140002060`

## pseudocode

```c
void __fastcall KbdHid_S0IdleStateUpdate(char *Context, int a2, char a3)
{
  int v4; // ebp
  char v6; // si
  KIRQL v7; // al
  int v8; // edx
  int v9; // r8d
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  bool v13; // zf
  PDEVICE_OBJECT v14; // rcx
  int v15; // r9d
  int RemlockSize; // [rsp+20h] [rbp-58h]
  int RemlockSizea; // [rsp+20h] [rbp-58h]

  v4 = a2;
  v6 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      2,
      29,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 97);
  if ( *((_DWORD *)Context + 196) != v4 )
  {
    v13 = Context[788] == 0;
    v6 = 1;
    *((_DWORD *)Context + 196) = v4;
    if ( v13 )
    {
      Context[788] = 1;
      KeReleaseSpinLock((PKSPIN_LOCK)Context + 97, v7);
      v10 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), KbdHid_S0IdleStateChangeWorkItem, File, 1u, 0x20u);
      if ( v10 >= 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 4;
          WPP_RECORDER_SF_qLL(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v12,
            33,
            RemlockSizea,
            *(_QWORD *)Context,
            v4,
            a3);
        }
        IoQueueWorkItem(*((PIO_WORKITEM *)Context + 95), KbdHid_S0IdleStateChangeWorkItem, DelayedWorkQueue, Context);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          2,
          32,
          (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
          *(_QWORD *)Context,
          v10);
      }
      goto LABEL_11;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 97, v7);
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v14 = WPP_GLOBAL_Control;
    v15 = 31;
    LOBYTE(v8) = 4;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v14 = WPP_GLOBAL_Control;
    if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_11;
    v15 = 30;
    LOBYTE(v8) = 5;
  }
  WPP_RECORDER_SF_qLL(v14->DeviceExtension, v8, v9, v15, RemlockSize, *(_QWORD *)Context, v4, a3);
LABEL_11:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        2,
        34,
        (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x140001ed0  push    rbx
0x140001ed2  push    rbp
0x140001ed3  push    rsi
0x140001ed4  push    rdi
0x140001ed5  push    r12
0x140001ed7  push    r14
0x140001ed9  push    r15
0x140001edb  sub     rsp, 40h
0x140001edf  mov     r14d, r8d
0x140001ee2  mov     ebp, edx
0x140001ee4  mov     rdi, rcx
0x140001ee7  xor     sil, sil
0x140001eea  lea     r15, WPP_RECORDER_INITIALIZED
0x140001ef1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140001ef8  lea     r12, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140001eff  jnz     short loc_140001F5C
0x140001f01  lea     rcx, [rdi+308h]; SpinLock
0x140001f08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001f0f  nop     dword ptr [rax+rax+00h]
0x140001f14  cmp     [rdi+310h], ebp
0x140001f1a  jnz     loc_1400020B5
0x140001f20  movzx   edx, al; NewIrql
0x140001f23  lea     rcx, [rdi+308h]; SpinLock
0x140001f2a  call    cs:__imp_KeReleaseSpinLock
0x140001f31  nop     dword ptr [rax+rax+00h]
0x140001f36  test    sil, sil
0x140001f39  jnz     loc_1400020EC
0x140001f3f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140001f46  jnz     loc_1400020D0
0x140001f4c  add     rsp, 40h
0x140001f50  pop     r15
0x140001f52  pop     r14
0x140001f54  pop     r12
0x140001f56  pop     rdi
0x140001f57  pop     rsi
0x140001f58  pop     rbp
0x140001f59  pop     rbx
0x140001f5a  retn
0x140001f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f63  cmp     word ptr [rcx+48h], 0
0x140001f68  jz      short loc_140001F01
0x140001f6a  mov     rcx, [rcx+40h]
0x140001f6e  mov     r9d, 1Dh
0x140001f74  mov     r8d, 2
0x140001f7a  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140001f7f  mov     dl, 5
0x140001f81  call    WPP_RECORDER_SF_
0x140001f86  jmp     loc_140001F01
0x140001f8b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140001f92  jz      short loc_140001FBD
0x140001f94  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f9b  mov     r9d, 21h ; '!'
0x140001fa1  mov     rax, [rdi]
0x140001fa4  mov     dl, 4
0x140001fa6  mov     [rsp+78h+var_40], r14d
0x140001fab  mov     [rsp+78h+var_48], ebp
0x140001faf  mov     rcx, [rcx+40h]
0x140001fb3  mov     [rsp+78h+var_50], rax
0x140001fb8  call    WPP_RECORDER_SF_qLL
0x140001fbd  mov     rcx, [rdi+2F8h]; IoWorkItem
0x140001fc4  lea     rdx, KbdHid_S0IdleStateChangeWorkItem; WorkerRoutine
0x140001fcb  mov     r9, rdi; Context
0x140001fce  mov     r8d, 1; QueueType
0x140001fd4  call    cs:__imp_IoQueueWorkItem
0x140001fdb  nop     dword ptr [rax+rax+00h]
0x140001fe0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140001fe7  jz      loc_140001F4C
0x140001fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ff4  cmp     word ptr [rcx+48h], 0
0x140001ff9  jz      loc_140001F4C
0x140001fff  mov     rcx, [rcx+40h]
0x140002003  mov     r9d, 22h ; '"'
0x140002009  mov     r8d, 2
0x14000200f  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140002014  mov     dl, 5
0x140002016  call    WPP_RECORDER_SF_
0x14000201b  jmp     loc_140001F4C
0x140002020  movzx   edx, al; NewIrql
0x140002023  mov     [rdi+314h], sil
0x14000202a  lea     rcx, [rdi+308h]; SpinLock
0x140002031  call    cs:__imp_KeReleaseSpinLock
0x140002038  nop     dword ptr [rax+rax+00h]
0x14000203d  lea     rcx, [rdi+98h]; RemoveLock
0x140002044  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x14000204c  mov     r9d, 1; Line
0x140002052  lea     r8, File; File
0x140002059  lea     rdx, KbdHid_S0IdleStateChangeWorkItem; Tag
0x140002060  call    cs:__imp_IoAcquireRemoveLockEx
0x140002067  nop     dword ptr [rax+rax+00h]
0x14000206c  test    eax, eax
0x14000206e  jns     loc_140001F8B
0x140002074  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000207b  jz      loc_140001F4C
0x140002081  mov     rcx, cs:WPP_GLOBAL_Control
0x140002088  mov     r9d, 20h ; ' '
0x14000208e  mov     [rsp+78h+var_48], eax
0x140002092  mov     r8d, 2
0x140002098  mov     rax, [rdi]
0x14000209b  mov     dl, 4
0x14000209d  mov     [rsp+78h+var_50], rax
0x1400020a2  mov     rcx, [rcx+40h]
0x1400020a6  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400020ab  call    WPP_RECORDER_SF_qd
0x1400020b0  jmp     loc_140001FE0
0x1400020b5  cmp     byte ptr [rdi+314h], 0
0x1400020bc  mov     sil, 1
0x1400020bf  mov     [rdi+310h], ebp
0x1400020c5  jnz     loc_140001F20
0x1400020cb  jmp     loc_140002020
0x1400020d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020d7  cmp     word ptr [rcx+48h], 0
0x1400020dc  jz      loc_140001FE0
0x1400020e2  mov     r9d, 1Eh
0x1400020e8  mov     dl, 5
0x1400020ea  jmp     short loc_140002108
0x1400020ec  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400020f3  jz      loc_140001F4C
0x1400020f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002100  mov     r9d, 1Fh
0x140002106  mov     dl, 4
0x140002108  mov     rax, [rdi]
0x14000210b  mov     rcx, [rcx+40h]
0x14000210f  mov     [rsp+78h+var_40], r14d
0x140002114  mov     [rsp+78h+var_48], ebp
0x140002118  mov     [rsp+78h+var_50], rax
0x14000211d  call    WPP_RECORDER_SF_qLL
0x140002122  jmp     loc_140001FE0
```
