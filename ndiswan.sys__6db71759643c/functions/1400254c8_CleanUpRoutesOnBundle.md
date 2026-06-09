# CleanUpRoutesOnBundle

- ea: `0x1400254c8`
- end: `0x140025718`
- name: `CleanUpRoutesOnBundle`
- size: `592`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002e540`

## callees

- `0x1400035f0`
- `0x140005494`
- `0x14000a290`
- `0x14000a648`
- `0x14000b818`
- `0x1400254c8`
- `0x14002c16c`
- `0x14002c200`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140025640`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025640`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400255cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002561a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002568d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400256ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400255cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002561a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002568d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400256ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025520`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400255f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002564f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002569c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025520`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400255f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002564f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002569c`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x1400255e5`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x1400255e5`

## pseudocode

```c
void __fastcall CleanUpRoutesOnBundle(KSPIN_LOCK *Entry)
{
  KIRQL v2; // al
  volatile signed __int32 *v3; // r14
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rax
  volatile signed __int32 **v6; // rdi
  volatile signed __int32 *v7; // r13
  int v8; // eax
  volatile __int32 **v9; // r15
  volatile __int32 *v10; // rsi
  __int64 v11; // rax
  KIRQL v12; // al
  bool v13; // zf

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, Entry);
  }
  v2 = KeAcquireSpinLockRaiseToDpc(Entry + 221);
  ++*((_DWORD *)Entry + 6);
  v3 = (volatile signed __int32 *)(Entry + 35);
  v4 = (volatile signed __int32 *)Entry[35];
  *((_BYTE *)Entry + 1776) = v2;
  while ( v4 != v3 )
  {
    v5 = v4;
    v4 = *(volatile signed __int32 **)v4;
    _InterlockedIncrement(v5 + 6);
  }
  v6 = *(volatile signed __int32 ***)v3;
  if ( *(volatile signed __int32 **)v3 != v3 )
  {
    do
    {
      v7 = *v6;
      DereferenceRefCount(v6 + 3);
      if ( *((_DWORD *)v6 + 5) != 1 )
      {
        v8 = ~*((_DWORD *)v6 + 27);
        *((_DWORD *)v6 + 5) = 1;
        *((_DWORD *)Entry + 78) &= v8;
        FlushProtocolPacketQueue(v6);
        v9 = v6 + 9;
        while ( 1 )
        {
          v10 = *v9;
          if ( *v9 == (volatile __int32 *)v9 )
            break;
          if ( *((volatile __int32 ***)v10 + 1) != v9
            || (v11 = *(_QWORD *)v10, *(volatile __int32 **)(*(_QWORD *)v10 + 8LL) != v10) )
          {
            __fastfail(3u);
          }
          *v9 = (volatile __int32 *)v11;
          *(_QWORD *)(v11 + 8) = v9;
          if ( *((_DWORD *)v10 + 5) == 1 )
          {
            _InterlockedExchange(v10 + 5, 2);
            KeReleaseSpinLock(Entry + 221, *((_BYTE *)Entry + 1776));
            NdisCmDispatchIncomingCloseCall(0, *((NDIS_HANDLE *)v10 + 5), 0, 0);
            *((_BYTE *)Entry + 1776) = KeAcquireSpinLockRaiseToDpc(Entry + 221);
          }
        }
        DereferenceRefCount(v6 + 3);
        KeReleaseSpinLock(Entry + 221, *((_BYTE *)Entry + 1776));
        KeWaitForSingleObject(v6 + 38, UserRequest, 0, 0, 0);
        *((_BYTE *)Entry + 1776) = KeAcquireSpinLockRaiseToDpc(Entry + 221);
        DoLineDownToProtocol(v6);
        NdisWanFreeProtocolCB((PVOID *)v6);
      }
      v6 = (volatile signed __int32 **)v7;
    }
    while ( v7 != v3 );
  }
  KeReleaseSpinLock(Entry + 221, *((_BYTE *)Entry + 1776));
  v12 = KeAcquireSpinLockRaiseToDpc(Entry + 221);
  v13 = (*((_DWORD *)Entry + 6))-- == 1;
  *((_BYTE *)Entry + 1776) = v12;
  if ( v13 )
    DoDerefBundleCBWork(Entry);
  else
    KeReleaseSpinLock(Entry + 221, v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
}

```

## disassembly

```asm
0x1400254c8  push    rbx
0x1400254ca  push    rbp
0x1400254cb  push    rsi
0x1400254cc  push    rdi
0x1400254cd  push    r12
0x1400254cf  push    r13
0x1400254d1  push    r14
0x1400254d3  push    r15
0x1400254d5  sub     rsp, 38h
0x1400254d9  mov     rbx, rcx
0x1400254dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254e3  lea     rsi, WPP_GLOBAL_Control
0x1400254ea  cmp     rcx, rsi
0x1400254ed  jz      short loc_140025516
0x1400254ef  test    dword ptr [rcx+2Ch], 8000h
0x1400254f6  jz      short loc_140025516
0x1400254f8  cmp     byte ptr [rcx+29h], 5
0x1400254fc  jb      short loc_140025516
0x1400254fe  mov     rcx, [rcx+18h]
0x140025502  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140025509  mov     edx, 2Dh ; '-'
0x14002550e  mov     r9, rbx
0x140025511  call    WPP_SF_q
0x140025516  lea     rbp, [rbx+6E8h]
0x14002551d  mov     rcx, rbp; SpinLock
0x140025520  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025527  nop     dword ptr [rax+rax+00h]
0x14002552c  inc     dword ptr [rbx+18h]
0x14002552f  lea     r14, [rbx+118h]
0x140025536  mov     rcx, [r14]
0x140025539  mov     [rbx+6F0h], al
0x14002553f  jmp     short loc_14002554B
0x140025541  lea     rax, [rcx]
0x140025544  mov     rcx, [rcx]
0x140025547  lock inc dword ptr [rax+18h]
0x14002554b  cmp     rcx, r14
0x14002554e  jnz     short loc_140025541
0x140025550  mov     rdi, [r14]
0x140025553  cmp     rdi, r14
0x140025556  jz      loc_140025684
0x14002555c  mov     r13, [rdi]
0x14002555f  lea     rcx, [rdi+18h]
0x140025563  call    DereferenceRefCount
0x140025568  cmp     dword ptr [rdi+14h], 1
0x14002556c  jz      loc_140025671
0x140025572  mov     eax, [rdi+6Ch]
0x140025575  mov     rcx, rdi
0x140025578  not     eax
0x14002557a  mov     dword ptr [rdi+14h], 1
0x140025581  and     [rbx+138h], eax
0x140025587  call    FlushProtocolPacketQueue
0x14002558c  lea     r15, [rdi+48h]
0x140025590  mov     rsi, [r15]
0x140025593  cmp     rsi, r15
0x140025596  jz      short loc_140025608
0x140025598  cmp     [rsi+8], r15
0x14002559c  jnz     loc_1400256BE
0x1400255a2  mov     rax, [rsi]
0x1400255a5  cmp     [rax+8], rsi
0x1400255a9  jnz     loc_1400256BE
0x1400255af  mov     [r15], rax
0x1400255b2  mov     [rax+8], r15
0x1400255b6  cmp     dword ptr [rsi+14h], 1
0x1400255ba  jnz     short loc_140025590
0x1400255bc  mov     eax, 2
0x1400255c1  mov     rcx, rbp; SpinLock
0x1400255c4  xchg    eax, [rsi+14h]
0x1400255c7  mov     dl, [rbx+6F0h]; NewIrql
0x1400255cd  call    cs:__imp_KeReleaseSpinLock
0x1400255d4  nop     dword ptr [rax+rax+00h]
0x1400255d9  mov     rdx, [rsi+28h]; NdisVcHandle
0x1400255dd  xor     r9d, r9d; Size
0x1400255e0  xor     r8d, r8d; Buffer
0x1400255e3  xor     ecx, ecx; CloseStatus
0x1400255e5  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x1400255ec  nop     dword ptr [rax+rax+00h]
0x1400255f1  mov     rcx, rbp; SpinLock
0x1400255f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400255fb  nop     dword ptr [rax+rax+00h]
0x140025600  mov     [rbx+6F0h], al
0x140025606  jmp     short loc_140025590
0x140025608  lea     rcx, [rdi+18h]
0x14002560c  call    DereferenceRefCount
0x140025611  mov     dl, [rbx+6F0h]; NewIrql
0x140025617  mov     rcx, rbp; SpinLock
0x14002561a  call    cs:__imp_KeReleaseSpinLock
0x140025621  nop     dword ptr [rax+rax+00h]
0x140025626  xor     r9d, r9d; Alertable
0x140025629  mov     [rsp+78h+Timeout], 0; Timeout
0x140025632  lea     rcx, [rdi+130h]; Object
0x140025639  xor     r8d, r8d; WaitMode
0x14002563c  lea     edx, [r9+6]; WaitReason
0x140025640  call    cs:__imp_KeWaitForSingleObject
0x140025647  nop     dword ptr [rax+rax+00h]
0x14002564c  mov     rcx, rbp; SpinLock
0x14002564f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025656  nop     dword ptr [rax+rax+00h]
0x14002565b  mov     rcx, rdi
0x14002565e  mov     [rbx+6F0h], al
0x140025664  call    DoLineDownToProtocol
0x140025669  mov     rcx, rdi; Entry
0x14002566c  call    NdisWanFreeProtocolCB
0x140025671  mov     rdi, r13
0x140025674  cmp     r13, r14
0x140025677  jnz     loc_14002555C
0x14002567d  lea     rsi, WPP_GLOBAL_Control
0x140025684  mov     dl, [rbx+6F0h]; NewIrql
0x14002568a  mov     rcx, rbp; SpinLock
0x14002568d  call    cs:__imp_KeReleaseSpinLock
0x140025694  nop     dword ptr [rax+rax+00h]
0x140025699  mov     rcx, rbp; SpinLock
0x14002569c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400256a3  nop     dword ptr [rax+rax+00h]
0x1400256a8  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x1400256ac  mov     [rbx+6F0h], al
0x1400256b2  jnz     short loc_1400256C5
0x1400256b4  mov     rcx, rbx; Entry
0x1400256b7  call    DoDerefBundleCBWork
0x1400256bc  jmp     short loc_1400256D6
0x1400256be  mov     ecx, 3
0x1400256c3  int     29h; Win8: RtlFailFast(ecx)
0x1400256c5  mov     dl, al; NewIrql
0x1400256c7  mov     rcx, rbp; SpinLock
0x1400256ca  call    cs:__imp_KeReleaseSpinLock
0x1400256d1  nop     dword ptr [rax+rax+00h]
0x1400256d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400256dd  cmp     rcx, rsi
0x1400256e0  jz      short loc_140025706
0x1400256e2  test    dword ptr [rcx+2Ch], 8000h
0x1400256e9  jz      short loc_140025706
0x1400256eb  cmp     byte ptr [rcx+29h], 5
0x1400256ef  jb      short loc_140025706
0x1400256f1  mov     rcx, [rcx+18h]
0x1400256f5  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400256fc  mov     edx, 2Eh ; '.'
0x140025701  call    WPP_SF_
0x140025706  add     rsp, 38h
0x14002570a  pop     r15
0x14002570c  pop     r14
0x14002570e  pop     r13
0x140025710  pop     r12
0x140025712  pop     rdi
0x140025713  pop     rsi
0x140025714  pop     rbp
0x140025715  pop     rbx
0x140025716  retn
```
