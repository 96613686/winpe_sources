# ClasspTimerTick

- ea: `0x14000fd00`
- end: `0x14000ffca`
- name: `ClasspTimerTick`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fce0`

## callees

- `0x14000fd00`
- `0x14000ffd0`
- `0x1400157d0`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14000fe44`
- `ntoskrnl!IoQueueWorkItem` at `0x14000fe44`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000fd1f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000fd1f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fd93`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fd93`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000fdfe`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000fdfe`

## pseudocode

```c
void __fastcall ClasspTimerTick(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdi
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64); // rax
  __int64 v7; // r8
  signed __int32 v8; // eax
  PIO_WORKITEM WorkItem; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  signed __int32 v12; // ett

  v2 = *(_QWORD *)(a2 + 8);
  v4 = *(_QWORD *)(v2 + 64);
  if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(*(_QWORD *)(v4 + 440) + 8LL)) )
  {
    _InterlockedIncrement(*(volatile signed __int32 **)(v4 + 440));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_a22cc05f221e30b8049471910da99059_Traceguids,
        **(unsigned int **)(v4 + 440));
    }
  }
  if ( !*(_DWORD *)(v4 + 108) )
  {
    v5 = *(_QWORD *)(a2 + 824);
    if ( *(_QWORD *)(a2 + 648) && !*(_BYTE *)(*(_QWORD *)(a2 + 1152) + 37LL) )
      ClassCheckMediaState((PFUNCTIONAL_DEVICE_EXTENSION)a2);
    if ( !v5 || !*(_DWORD *)v5 )
      goto LABEL_6;
    if ( ClasspScreenOff || *(_DWORD *)(a2 + 536) != 1 || *(_BYTE *)(a2 + 832) )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_6;
      }
      v11 = 101;
    }
    else
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 4), 0xFFFFFFFF) != 1 )
        goto LABEL_6;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v2);
      }
      if ( !*(_QWORD *)(v5 + 16) )
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a2 + 8));
        *(_QWORD *)(v5 + 16) = WorkItem;
        if ( WorkItem )
        {
          ClassAcquireRemoveLockEx(
            *(PDEVICE_OBJECT *)(a2 + 8),
            WorkItem,
            "minkernel\\storage\\classpnp\\autorun.c",
            0xE15u);
          IoQueueWorkItem(*(PIO_WORKITEM *)(v5 + 16), ClasspFailurePredict, DelayedWorkQueue, (PVOID)v5);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
          }
          _InterlockedExchange((volatile __int32 *)(v5 + 4), 60);
        }
        goto LABEL_6;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
LABEL_6:
        v6 = *(void (__fastcall **)(__int64))(*(_QWORD *)(a2 + 32) + 400LL);
        if ( v6 )
          v6(v2);
        goto LABEL_8;
      }
      v11 = 100;
    }
    WPP_SF_q(v10->AttachedDevice, v11, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v2);
    goto LABEL_6;
  }
LABEL_8:
  v7 = *(_QWORD *)(v2 + 64);
  v8 = **(_DWORD **)(v7 + 440);
  if ( v8 )
  {
    while ( 1 )
    {
      v12 = v8;
      v8 = _InterlockedCompareExchange(*(volatile signed __int32 **)(v7 + 440), v8 - 1, v8);
      if ( v12 == v8 )
        break;
      if ( !v8 )
        goto LABEL_9;
    }
  }
  else
  {
LABEL_9:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(*(_QWORD *)(v7 + 440) + 8LL));
  }
}

```

## disassembly

```asm
0x14000fd00  push    rbx
0x14000fd02  push    rbp
0x14000fd03  push    rsi
0x14000fd04  push    rdi
0x14000fd05  sub     rsp, 28h
0x14000fd09  mov     rsi, [rdx+8]
0x14000fd0d  mov     rbx, rdx
0x14000fd10  mov     rdi, [rsi+40h]
0x14000fd14  mov     rcx, [rdi+1B8h]
0x14000fd1b  add     rcx, 8; RunRefCacheAware
0x14000fd1f  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14000fd26  nop     dword ptr [rax+rax+00h]
0x14000fd2b  lea     rbp, WPP_GLOBAL_Control
0x14000fd32  test    al, al
0x14000fd34  jz      loc_14000FEA4
0x14000fd3a  cmp     dword ptr [rdi+6Ch], 0
0x14000fd3e  jnz     short loc_14000FD73
0x14000fd40  cmp     qword ptr [rbx+288h], 0
0x14000fd48  mov     rdi, [rbx+338h]
0x14000fd4f  jnz     loc_14000FE55
0x14000fd55  test    rdi, rdi
0x14000fd58  jz      short loc_14000FD5F
0x14000fd5a  cmp     dword ptr [rdi], 0
0x14000fd5d  jnz     short loc_14000FDA9
0x14000fd5f  mov     rax, [rbx+20h]
0x14000fd63  mov     rax, [rax+190h]
0x14000fd6a  test    rax, rax
0x14000fd6d  jnz     loc_14000FFA0
0x14000fd73  mov     r8, [rsi+40h]
0x14000fd77  mov     rax, [r8+1B8h]
0x14000fd7e  mov     eax, [rax]
0x14000fd80  test    eax, eax
0x14000fd82  jnz     loc_14000FFAD
0x14000fd88  mov     rcx, [r8+1B8h]
0x14000fd8f  add     rcx, 8; RunRefCacheAware
0x14000fd93  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14000fd9a  nop     dword ptr [rax+rax+00h]
0x14000fd9f  add     rsp, 28h
0x14000fda3  pop     rdi
0x14000fda4  pop     rsi
0x14000fda5  pop     rbp
0x14000fda6  pop     rbx
0x14000fda7  retn
0x14000fda9  cmp     cs:ClasspScreenOff, 0
0x14000fdb0  jnz     loc_14000FE73
0x14000fdb6  cmp     dword ptr [rbx+218h], 1
0x14000fdbd  jnz     loc_14000FE73
0x14000fdc3  cmp     byte ptr [rbx+340h], 0
0x14000fdca  jnz     loc_14000FE73
0x14000fdd0  mov     eax, 0FFFFFFFFh
0x14000fdd5  lock xadd [rdi+4], eax
0x14000fdda  cmp     eax, 1
0x14000fddd  jnz     short loc_14000FD5F
0x14000fddf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fde6  cmp     rcx, rbp
0x14000fde9  jnz     loc_14000FF2A
0x14000fdef  cmp     qword ptr [rdi+10h], 0
0x14000fdf4  jnz     loc_14000FEF9
0x14000fdfa  mov     rcx, [rbx+8]; DeviceObject
0x14000fdfe  call    cs:__imp_IoAllocateWorkItem
0x14000fe05  nop     dword ptr [rax+rax+00h]
0x14000fe0a  mov     [rdi+10h], rax
0x14000fe0e  test    rax, rax
0x14000fe11  jz      loc_14000FF5E
0x14000fe17  mov     rcx, [rbx+8]; DeviceObject
0x14000fe1b  lea     r8, aMinkernelStora_1; "minkernel\\storage\\classpnp\\autorun.c"
0x14000fe22  mov     r9d, 0E15h; Line
0x14000fe28  mov     rdx, rax; Tag
0x14000fe2b  call    ClassAcquireRemoveLockEx
0x14000fe30  mov     rcx, [rdi+10h]; IoWorkItem
0x14000fe34  lea     rdx, ClasspFailurePredict; WorkerRoutine
0x14000fe3b  mov     r9, rdi; Context
0x14000fe3e  mov     r8d, 1; QueueType
0x14000fe44  call    cs:__imp_IoQueueWorkItem
0x14000fe4b  nop     dword ptr [rax+rax+00h]
0x14000fe50  jmp     loc_14000FD5F
0x14000fe55  mov     rax, [rbx+480h]
0x14000fe5c  cmp     byte ptr [rax+25h], 0
0x14000fe60  jnz     loc_14000FD55
0x14000fe66  mov     rcx, rbx; FdoExtension
0x14000fe69  call    ClassCheckMediaState
0x14000fe6e  jmp     loc_14000FD55
0x14000fe73  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe7a  cmp     rcx, rbp
0x14000fe7d  jz      loc_14000FD5F
0x14000fe83  test    dword ptr [rcx+2Ch], 1000h
0x14000fe8a  jz      loc_14000FD5F
0x14000fe90  cmp     byte ptr [rcx+29h], 4
0x14000fe94  jb      loc_14000FD5F
0x14000fe9a  mov     edx, 65h ; 'e'
0x14000fe9f  jmp     loc_14003FBC1
0x14000fea4  mov     rax, [rdi+1B8h]
0x14000feab  lock inc dword ptr [rax]
0x14000feae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000feb5  cmp     rcx, rbp
0x14000feb8  jz      loc_14000FD3A
0x14000febe  test    dword ptr [rcx+2Ch], 200h
0x14000fec5  jz      loc_14000FD3A
0x14000fecb  cmp     byte ptr [rcx+29h], 5
0x14000fecf  jb      loc_14000FD3A
0x14000fed5  mov     r9, [rdi+1B8h]
0x14000fedc  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x14000fee3  mov     rcx, [rcx+18h]
0x14000fee7  mov     edx, 0Eh
0x14000feec  mov     r9d, [r9]
0x14000feef  call    WPP_SF_d
0x14000fef4  jmp     loc_14000FD3A
0x14000fef9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff00  cmp     rcx, rbp
0x14000ff03  jz      loc_14000FD5F
0x14000ff09  test    dword ptr [rcx+2Ch], 1000h
0x14000ff10  jz      loc_14000FD5F
0x14000ff16  cmp     byte ptr [rcx+29h], 4
0x14000ff1a  jb      loc_14000FD5F
0x14000ff20  mov     edx, 64h ; 'd'
0x14000ff25  jmp     loc_14003FBC1
0x14000ff2a  test    dword ptr [rcx+2Ch], 1000h
0x14000ff31  jz      loc_14000FDEF
0x14000ff37  cmp     byte ptr [rcx+29h], 4
0x14000ff3b  jb      loc_14000FDEF
0x14000ff41  mov     rcx, [rcx+18h]
0x14000ff45  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14000ff4c  mov     edx, 62h ; 'b'
0x14000ff51  mov     r9, rsi
0x14000ff54  call    WPP_SF_q
0x14000ff59  jmp     loc_14000FDEF
0x14000ff5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff65  cmp     rcx, rbp
0x14000ff68  jz      loc_14003FBB4
0x14000ff6e  test    dword ptr [rcx+2Ch], 1000h
0x14000ff75  jz      loc_14003FBB4
0x14000ff7b  cmp     byte ptr [rcx+29h], 3
0x14000ff7f  jb      loc_14003FBB4
0x14000ff85  mov     rcx, [rcx+18h]
0x14000ff89  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14000ff90  mov     edx, 63h ; 'c'
0x14000ff95  call    WPP_SF_
0x14000ff9a  nop
0x14000ff9b  jmp     loc_14003FBB4
0x14000ffa0  mov     rcx, rsi
0x14000ffa3  call    _guard_dispatch_icall
0x14000ffa8  jmp     loc_14000FD73
0x14000ffad  mov     rcx, [r8+1B8h]
0x14000ffb4  lea     edx, [rax-1]
0x14000ffb7  lock cmpxchg [rcx], edx
0x14000ffbb  jz      loc_14000FD9F
0x14000ffc1  test    eax, eax
0x14000ffc3  jnz     short loc_14000FFAD
0x14000ffc5  jmp     loc_14000FD88
0x14003fbb4  mov     eax, 3Ch ; '<'
0x14003fbb9  xchg    eax, [rdi+4]
0x14003fbbc  jmp     loc_14000FD5F
0x14003fbc1  mov     rcx, [rcx+18h]
0x14003fbc5  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14003fbcc  mov     r9, rsi
0x14003fbcf  call    WPP_SF_q
0x14003fbd4  nop
0x14003fbd5  jmp     loc_14000FD5F
```
