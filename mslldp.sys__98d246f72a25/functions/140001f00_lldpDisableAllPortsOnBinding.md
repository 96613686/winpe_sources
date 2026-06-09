# lldpDisableAllPortsOnBinding

- ea: `0x140001f00`
- end: `0x140002045`
- name: `lldpDisableAllPortsOnBinding`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ae0`
- `0x140010f20`

## callees

- `0x140001f00`
- `0x140002500`
- `0x140005ac0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001fd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001fd2`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140002034`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140002034`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002000`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002000`

## pseudocode

```c
void __fastcall lldpDisableAllPortsOnBinding(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  unsigned int i; // ebp
  signed __int32 v6; // edi
  __int64 j; // rax

  v4 = *(_QWORD *)(a1 + 120);
  for ( i = a2; v4; v4 = *(_QWORD *)(v4 + 40) )
  {
    _m_prefetchw((const void *)(v4 + 304));
    v6 = _InterlockedOr((volatile signed __int32 *)(v4 + 304), i);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DDD(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_0ffa195ed41632c397cfac9730cd0bab_Traceguids,
          HIWORD(*(_QWORD *)(v4 + 120)),
          (*(_QWORD *)(v4 + 120) >> 24) & 0xFFFFFF,
          i);
      LOBYTE(a2) = 1;
      lldpRecalculateTxTimer(v4, a2, a3, a4);
    }
    if ( v6 != (i | v6) && *(_QWORD *)(v4 + 88) )
    {
      *(_BYTE *)(v4 + 80) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 72));
      for ( j = *(_QWORD *)(v4 + 88); j; j = *(_QWORD *)(j + 8) )
        _InterlockedOr((volatile signed __int32 *)(j + 32), 8u);
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 72), *(_BYTE *)(v4 + 80));
      if ( !_InterlockedExchange((volatile __int32 *)(v4 + 96), 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 48));
        IoQueueWorkItemEx(*(PIO_WORKITEM *)(v4 + 104), lldpDeliverChangeNotifications, DelayedWorkQueue, (PVOID)v4);
      }
    }
  }
}

```

## disassembly

```asm
0x140001f00  mov     [rsp+arg_18], rbx
0x140001f05  push    rbp
0x140001f06  sub     rsp, 30h
0x140001f0a  mov     rbx, [rcx+78h]
0x140001f0e  mov     ebp, edx
0x140001f10  test    rbx, rbx
0x140001f13  jz      short loc_140001F73
0x140001f15  mov     [rsp+38h+arg_0], rsi
0x140001f1a  mov     [rsp+38h+arg_8], rdi
0x140001f1f  mov     [rsp+38h+arg_10], r14
0x140001f24  lea     r14, WPP_GLOBAL_Control
0x140001f2b  prefetchw byte ptr [rbx+130h]
0x140001f32  mov     eax, [rbx+130h]
0x140001f38  mov     ecx, eax
0x140001f3a  or      ecx, ebp
0x140001f3c  lock cmpxchg [rbx+130h], ecx
0x140001f44  jnz     short loc_140001F38
0x140001f46  mov     esi, eax
0x140001f48  mov     edi, eax
0x140001f4a  or      esi, ebp
0x140001f4c  test    eax, eax
0x140001f4e  jz      short loc_140001F7F
0x140001f50  cmp     edi, esi
0x140001f52  jz      short loc_140001F5B
0x140001f54  cmp     qword ptr [rbx+58h], 0
0x140001f59  jnz     short loc_140001FCE
0x140001f5b  mov     rbx, [rbx+28h]
0x140001f5f  test    rbx, rbx
0x140001f62  jnz     short loc_140001F2B
0x140001f64  mov     r14, [rsp+38h+arg_10]
0x140001f69  mov     rdi, [rsp+38h+arg_8]
0x140001f6e  mov     rsi, [rsp+38h+arg_0]
0x140001f73  mov     rbx, [rsp+38h+arg_18]
0x140001f78  add     rsp, 30h
0x140001f7c  pop     rbp
0x140001f7d  retn
0x140001f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f86  cmp     rcx, r14
0x140001f89  jz      short loc_140001FC2
0x140001f8b  cmp     byte ptr [rcx+29h], 4
0x140001f8f  jb      short loc_140001FC2
0x140001f91  mov     r9, [rbx+78h]
0x140001f95  lea     r8, WPP_0ffa195ed41632c397cfac9730cd0bab_Traceguids
0x140001f9c  mov     rcx, [rcx+18h]
0x140001fa0  mov     rax, r9
0x140001fa3  shr     rax, 18h
0x140001fa7  mov     edx, 0Eh
0x140001fac  and     eax, 0FFFFFFh
0x140001fb1  shr     r9, 30h
0x140001fb5  mov     [rsp+38h+var_10], ebp
0x140001fb9  mov     [rsp+38h+var_18], eax
0x140001fbd  call    WPP_SF_DDD
0x140001fc2  mov     dl, 1
0x140001fc4  mov     rcx, rbx
0x140001fc7  call    lldpRecalculateTxTimer
0x140001fcc  jmp     short loc_140001F50
0x140001fce  lea     rcx, [rbx+48h]; SpinLock
0x140001fd2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001fd9  nop     dword ptr [rax+rax+00h]
0x140001fde  mov     [rbx+50h], al
0x140001fe1  mov     rax, [rbx+58h]
0x140001fe5  test    rax, rax
0x140001fe8  jz      short loc_140001FF8
0x140001fea  lock or dword ptr [rax+20h], 8
0x140001fef  mov     rax, [rax+8]
0x140001ff3  test    rax, rax
0x140001ff6  jnz     short loc_140001FEA
0x140001ff8  movzx   edx, byte ptr [rbx+50h]; NewIrql
0x140001ffc  lea     rcx, [rbx+48h]; SpinLock
0x140002000  call    cs:__imp_KeReleaseSpinLock
0x140002007  nop     dword ptr [rax+rax+00h]
0x14000200c  mov     eax, 1
0x140002011  xchg    eax, [rbx+60h]
0x140002014  test    eax, eax
0x140002016  jnz     loc_140001F5B
0x14000201c  lock inc dword ptr [rbx+30h]
0x140002020  mov     rcx, [rbx+68h]; IoWorkItem
0x140002024  lea     rdx, lldpDeliverChangeNotifications; WorkerRoutine
0x14000202b  mov     r9, rbx; Context
0x14000202e  mov     r8d, 1; QueueType
0x140002034  call    cs:__imp_IoQueueWorkItemEx
0x14000203b  nop     dword ptr [rax+rax+00h]
0x140002040  jmp     loc_140001F5B
```
