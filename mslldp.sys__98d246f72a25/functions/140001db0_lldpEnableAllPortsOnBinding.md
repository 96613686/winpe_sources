# lldpEnableAllPortsOnBinding

- ea: `0x140001db0`
- end: `0x140001ef1`
- name: `lldpEnableAllPortsOnBinding`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ae0`
- `0x140010f20`

## callees

- `0x140001db0`
- `0x140002180`
- `0x140005a6c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e7e`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001ee0`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001ee0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001eac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001eac`

## pseudocode

```c
void __fastcall lldpEnableAllPortsOnBinding(__int64 a1, int a2)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  signed __int32 v4; // ebp
  __int64 i; // rax
  __int64 v6; // [rsp+20h] [rbp-18h]

  v2 = *(_QWORD *)(a1 + 120);
  if ( v2 )
  {
    v3 = ~a2;
    do
    {
      _m_prefetchw((const void *)(v2 + 304));
      v4 = _InterlockedAnd((volatile signed __int32 *)(v2 + 304), v3);
      if ( (v4 & v3) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          LODWORD(v6) = (*(_QWORD *)(v2 + 120) >> 24) & 0xFFFFFF;
          WPP_SF_DD(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0xDu,
            (__int64)WPP_0ffa195ed41632c397cfac9730cd0bab_Traceguids,
            HIWORD(*(_QWORD *)(v2 + 120)),
            v6);
        }
        lldpEnableTxFastMode(v2);
      }
      if ( v4 != (v4 & v3) && *(_QWORD *)(v2 + 88) )
      {
        *(_BYTE *)(v2 + 80) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 72));
        for ( i = *(_QWORD *)(v2 + 88); i; i = *(_QWORD *)(i + 8) )
          _InterlockedOr((volatile signed __int32 *)(i + 32), 8u);
        KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 72), *(_BYTE *)(v2 + 80));
        if ( !_InterlockedExchange((volatile __int32 *)(v2 + 96), 1) )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v2 + 48));
          IoQueueWorkItemEx(*(PIO_WORKITEM *)(v2 + 104), lldpDeliverChangeNotifications, DelayedWorkQueue, (PVOID)v2);
        }
      }
      v2 = *(_QWORD *)(v2 + 40);
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x140001db0  mov     [rsp+arg_18], rbx
0x140001db5  push    rsi
0x140001db6  sub     rsp, 30h
0x140001dba  mov     rbx, [rcx+78h]
0x140001dbe  mov     esi, edx
0x140001dc0  test    rbx, rbx
0x140001dc3  jz      short loc_140001E23
0x140001dc5  mov     [rsp+38h+arg_0], rbp
0x140001dca  not     esi
0x140001dcc  mov     [rsp+38h+arg_8], rdi
0x140001dd1  mov     [rsp+38h+arg_10], r14
0x140001dd6  lea     r14, WPP_GLOBAL_Control
0x140001ddd  prefetchw byte ptr [rbx+130h]
0x140001de4  mov     eax, [rbx+130h]
0x140001dea  mov     ecx, eax
0x140001dec  and     ecx, esi
0x140001dee  lock cmpxchg [rbx+130h], ecx
0x140001df6  jnz     short loc_140001DEA
0x140001df8  mov     edi, esi
0x140001dfa  mov     ebp, eax
0x140001dfc  and     edi, eax
0x140001dfe  jz      short loc_140001E2F
0x140001e00  cmp     ebp, edi
0x140001e02  jz      short loc_140001E0B
0x140001e04  cmp     qword ptr [rbx+58h], 0
0x140001e09  jnz     short loc_140001E7A
0x140001e0b  mov     rbx, [rbx+28h]
0x140001e0f  test    rbx, rbx
0x140001e12  jnz     short loc_140001DDD
0x140001e14  mov     r14, [rsp+38h+arg_10]
0x140001e19  mov     rdi, [rsp+38h+arg_8]
0x140001e1e  mov     rbp, [rsp+38h+arg_0]
0x140001e23  mov     rbx, [rsp+38h+arg_18]
0x140001e28  add     rsp, 30h
0x140001e2c  pop     rsi
0x140001e2d  retn
0x140001e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e36  cmp     rcx, r14
0x140001e39  jz      short loc_140001E41
0x140001e3b  cmp     byte ptr [rcx+29h], 4
0x140001e3f  jnb     short loc_140001E4B
0x140001e41  mov     rcx, rbx
0x140001e44  call    lldpEnableTxFastMode
0x140001e49  jmp     short loc_140001E00
0x140001e4b  mov     r9, [rbx+78h]
0x140001e4f  lea     r8, WPP_0ffa195ed41632c397cfac9730cd0bab_Traceguids
0x140001e56  mov     rcx, [rcx+18h]
0x140001e5a  mov     rax, r9
0x140001e5d  shr     rax, 18h
0x140001e61  mov     edx, 0Dh
0x140001e66  and     eax, 0FFFFFFh
0x140001e6b  shr     r9, 30h
0x140001e6f  mov     dword ptr [rsp+38h+var_18], eax
0x140001e73  call    WPP_SF_DD
0x140001e78  jmp     short loc_140001E41
0x140001e7a  lea     rcx, [rbx+48h]; SpinLock
0x140001e7e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001e85  nop     dword ptr [rax+rax+00h]
0x140001e8a  mov     [rbx+50h], al
0x140001e8d  mov     rax, [rbx+58h]
0x140001e91  test    rax, rax
0x140001e94  jz      short loc_140001EA4
0x140001e96  lock or dword ptr [rax+20h], 8
0x140001e9b  mov     rax, [rax+8]
0x140001e9f  test    rax, rax
0x140001ea2  jnz     short loc_140001E96
0x140001ea4  movzx   edx, byte ptr [rbx+50h]; NewIrql
0x140001ea8  lea     rcx, [rbx+48h]; SpinLock
0x140001eac  call    cs:__imp_KeReleaseSpinLock
0x140001eb3  nop     dword ptr [rax+rax+00h]
0x140001eb8  mov     eax, 1
0x140001ebd  xchg    eax, [rbx+60h]
0x140001ec0  test    eax, eax
0x140001ec2  jnz     loc_140001E0B
0x140001ec8  lock inc dword ptr [rbx+30h]
0x140001ecc  mov     rcx, [rbx+68h]; IoWorkItem
0x140001ed0  lea     rdx, lldpDeliverChangeNotifications; WorkerRoutine
0x140001ed7  mov     r9, rbx; Context
0x140001eda  mov     r8d, 1; QueueType
0x140001ee0  call    cs:__imp_IoQueueWorkItemEx
0x140001ee7  nop     dword ptr [rax+rax+00h]
0x140001eec  jmp     loc_140001E0B
```
