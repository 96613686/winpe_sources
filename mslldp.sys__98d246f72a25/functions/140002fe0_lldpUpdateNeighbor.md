# lldpUpdateNeighbor

- ea: `0x140002fe0`
- end: `0x1400033e0`
- name: `lldpUpdateNeighbor`
- size: `1024`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, size_t Size, size_t, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400029b0`

## callees

- `0x140002180`
- `0x140002fe0`
- `0x1400033e0`
- `0x1400034c0`
- `0x140003d80`
- `0x140004a90`
- `0x140005a6c`
- `0x140005d78`
- `0x140005dd0`
- `0x140005e4c`
- `0x140005ef8`
- `0x140005fe4`
- `0x140006720`
- `0x140006840`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000316c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000316c`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400031ca`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400031ca`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400030a2`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400030a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000319a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000319a`

## pseudocode

```c
__int64 __fastcall lldpUpdateNeighbor(
        unsigned int *Context,
        __int64 a2,
        void *a3,
        const void *a4,
        size_t Size,
        size_t a6,
        int a7)
{
  size_t v7; // rbp
  __int64 result; // rax
  int v13; // ecx
  PDEVICE_OBJECT *v14; // rdx
  int v15; // edx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdi
  int v19; // r14d
  int v20; // ecx
  int v21; // r8d
  char v22; // bp
  __int64 i; // rax
  int v24; // ecx
  int v25; // r8d
  _WORD *v26; // r14
  __int64 v27; // [rsp+80h] [rbp+8h] BYREF
  void *Buf2; // [rsp+90h] [rbp+18h]

  Buf2 = a3;
  v7 = (unsigned int)a6;
  result = Context[35];
  v27 = 0;
  if ( (unsigned int)a6 > (unsigned int)result )
  {
    v13 = (int)WPP_GLOBAL_Control;
    v14 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      result = WPP_SF_DD(
                 WPP_GLOBAL_Control->AttachedDevice,
                 22,
                 WPP_dc65fd90403c30e5e64868c1e34e4ed6_Traceguids,
                 (unsigned int)a6,
                 result);
    if ( SLOBYTE(WPP_MAIN_CB.SecurityDescriptor) < 0 )
      result = McTemplateK0qqq_EtwWriteTransfer(v13, (_DWORD)v14, (_DWORD)a3, Context[32], *(_DWORD *)(a2 + 88), 1);
    _InterlockedIncrement64((volatile signed __int64 *)Context + 111);
    return result;
  }
  KeQuerySystemTimePrecise(&v27);
  v18 = *((_QWORD *)Context + 121);
  if ( !v18 )
  {
    if ( !(unsigned __int8)lldpAllocateNewNeighbor(Context, a3, a4, (unsigned int)Size, v7) )
      return lldpDrop(Context, a2, 1);
    lldpQueueChangeNotificationEx(Context);
    lldpSetTimer((PKTIMER)(Context + 78));
    lldpEnableTxFastMode(Context);
    goto LABEL_41;
  }
  v19 = Size;
  if ( *(_DWORD *)(v18 + 12) != (_DWORD)Size || memcmp((const void *)(v18 + 24), a4, (unsigned int)Size) )
  {
    if ( a7 )
    {
      if ( !*((_BYTE *)Context + 216) )
      {
        *((_BYTE *)Context + 216) = 1;
        lldpQueueChangeNotificationEx(Context);
        lldpSetTimer((PKTIMER)Context + 7);
        if ( (BYTE1(WPP_MAIN_CB.SecurityDescriptor) & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v16, TooManyNeighborsBegin, v17, Context[32]);
      }
      if ( ((__int64)WPP_MAIN_CB.SecurityDescriptor & 8) != 0 )
        McTemplateK0qqbr1qbr3_EtwWriteTransfer(
          *((_QWORD *)Context + 121),
          v15,
          v17,
          Context[32],
          *(_DWORD *)(*((_QWORD *)Context + 121) + 12LL),
          *((_QWORD *)Context + 121) + 24LL,
          v19,
          (__int64)a4);
    }
    if ( SLOBYTE(WPP_MAIN_CB.SecurityDescriptor) < 0 )
      McTemplateK0qqq_EtwWriteTransfer(v16, v15, v17, Context[32], *(_DWORD *)(a2 + 88), 9);
    _InterlockedIncrement64((volatile signed __int64 *)Context + 111);
LABEL_41:
    result = v27;
    *((_QWORD *)Context + 28) = v27;
LABEL_42:
    *((_QWORD *)Context + 29) = result;
    return result;
  }
  if ( a7 )
  {
    if ( *(_DWORD *)(v18 + 16) == (_DWORD)v7 && !memcmp((const void *)(v18 + 24), a4, v7) )
    {
      v22 = 0;
    }
    else
    {
      memmove((void *)(v18 + 24), a4, v7);
      *(_DWORD *)(v18 + 16) = v7;
      v22 = 1;
      lldpQueueChangeNotificationEx(Context);
      if ( ((__int64)WPP_MAIN_CB.SecurityDescriptor & 4) != 0 )
        McTemplateK0qqbr1_EtwWriteTransfer(v24, (unsigned int)RemoteMibChanged, v25, Context[32], v19, (__int64)a4);
    }
    v26 = Buf2;
    if ( memcmp((const void *)(v18 + 4), Buf2, 6u) )
    {
      *(_DWORD *)(v18 + 4) = *(_DWORD *)v26;
      *(_WORD *)(v18 + 8) = v26[2];
      v22 = 1;
      lldpQueueChangeNotificationEx(Context);
    }
    lldpSetTimer((PKTIMER)(Context + 78));
  }
  else
  {
    lldpDeleteNeighborOnPort(Context);
    v22 = 1;
    if ( *((_QWORD *)Context + 11) )
    {
      *((_BYTE *)Context + 80) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 9);
      for ( i = *((_QWORD *)Context + 11); i; i = *(_QWORD *)(i + 8) )
        _InterlockedOr((volatile signed __int32 *)(i + 32), 0x40u);
      KeReleaseSpinLock((PKSPIN_LOCK)Context + 9, *((_BYTE *)Context + 80));
      if ( !_InterlockedExchange((volatile __int32 *)Context + 24, 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)Context + 12);
        IoQueueWorkItemEx(*((PIO_WORKITEM *)Context + 13), lldpDeliverChangeNotifications, DelayedWorkQueue, Context);
      }
    }
    if ( ((__int64)WPP_MAIN_CB.SecurityDescriptor & 2) != 0 )
      McTemplateK0qqbr1_EtwWriteTransfer(v20, (unsigned int)RemoteMibShutdown, v21, Context[32], v19, (__int64)a4);
  }
  result = v27;
  *((_QWORD *)Context + 28) = v27;
  if ( v22 )
    goto LABEL_42;
  return result;
}

```

## disassembly

```asm
0x140002fe0  mov     [rsp+Buf2], r8
0x140002fe5  push    rbx
0x140002fe6  push    rbp
0x140002fe7  push    rsi
0x140002fe8  push    r13
0x140002fea  push    r15
0x140002fec  sub     rsp, 50h
0x140002ff0  mov     ebp, dword ptr [rsp+78h+arg_28]
0x140002ff7  mov     r15, r9
0x140002ffa  mov     eax, [rcx+8Ch]
0x140003000  mov     rsi, r8
0x140003003  mov     [rsp+78h+arg_0], 0
0x14000300f  mov     r13, rdx
0x140003012  mov     rbx, rcx
0x140003015  cmp     ebp, eax
0x140003017  jbe     short loc_140003088
0x140003019  mov     rcx, cs:WPP_GLOBAL_Control
0x140003020  lea     rdx, WPP_GLOBAL_Control
0x140003027  cmp     rcx, rdx
0x14000302a  jz      short loc_14000304E
0x14000302c  cmp     byte ptr [rcx+29h], 2
0x140003030  jb      short loc_14000304E
0x140003032  mov     rcx, [rcx+18h]
0x140003036  lea     r8, WPP_dc65fd90403c30e5e64868c1e34e4ed6_Traceguids
0x14000303d  mov     edx, 16h
0x140003042  mov     [rsp+78h+var_58], eax
0x140003046  mov     r9d, ebp
0x140003049  call    WPP_SF_DD
0x14000304e  cmp     byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 0
0x140003055  jge     short loc_140003073
0x140003057  mov     eax, [r13+58h]
0x14000305b  mov     r9d, [rbx+80h]
0x140003062  mov     dword ptr [rsp+78h+var_50], 1
0x14000306a  mov     [rsp+78h+var_58], eax
0x14000306e  call    McTemplateK0qqq_EtwWriteTransfer
0x140003073  lock inc qword ptr [rbx+378h]
0x14000307b  add     rsp, 50h
0x14000307f  pop     r15
0x140003081  pop     r13
0x140003083  pop     rsi
0x140003084  pop     rbp
0x140003085  pop     rbx
0x140003086  retn
0x140003088  mov     [rsp+78h+arg_8], rdi
0x140003090  lea     rcx, [rsp+78h+arg_0]
0x140003098  mov     [rsp+78h+var_30], r12
0x14000309d  mov     [rsp+78h+var_38], r14
0x1400030a2  call    cs:__imp_KeQuerySystemTimePrecise
0x1400030a9  nop     dword ptr [rax+rax+00h]
0x1400030ae  mov     rdi, [rbx+3C8h]
0x1400030b5  test    rdi, rdi
0x1400030b8  jnz     short loc_14000311E
0x1400030ba  mov     r9d, dword ptr [rsp+78h+Size]
0x1400030c2  mov     r8, r15
0x1400030c5  mov     rdx, rsi
0x1400030c8  mov     [rsp+78h+var_58], ebp
0x1400030cc  mov     rcx, rbx
0x1400030cf  call    lldpAllocateNewNeighbor
0x1400030d4  mov     rcx, rbx; Context
0x1400030d7  test    al, al
0x1400030d9  jnz     short loc_1400030EE
0x1400030db  mov     r8d, 1
0x1400030e1  mov     rdx, r13
0x1400030e4  call    lldpDrop
0x1400030e9  jmp     loc_1400033B0
0x1400030ee  xor     edx, edx
0x1400030f0  mov     r8d, 10h
0x1400030f6  call    lldpQueueChangeNotificationEx
0x1400030fb  mov     edx, [rsp+78h+arg_30]
0x140003102  lea     rcx, [rbx+138h]; Timer
0x140003109  mov     r8b, 1
0x14000310c  call    lldpSetTimer
0x140003111  mov     rcx, rbx
0x140003114  call    lldpEnableTxFastMode
0x140003119  jmp     loc_14000339A
0x14000311e  mov     r14d, dword ptr [rsp+78h+Size]
0x140003126  cmp     [rdi+0Ch], r14d
0x14000312a  jnz     loc_1400032DB
0x140003130  mov     r8d, r14d; Size
0x140003133  lea     rcx, [rdi+18h]; Buf1
0x140003137  mov     rdx, r15; Buf2
0x14000313a  call    memcmp
0x14000313f  test    eax, eax
0x140003141  jnz     loc_1400032DB
0x140003147  mov     esi, [rsp+78h+arg_30]
0x14000314e  test    esi, esi
0x140003150  jnz     loc_140003205
0x140003156  mov     rcx, rbx
0x140003159  call    lldpDeleteNeighborOnPort
0x14000315e  cmp     qword ptr [rbx+58h], 0
0x140003163  mov     bpl, 1
0x140003166  jz      short loc_1400031D6
0x140003168  lea     rcx, [rbx+48h]; SpinLock
0x14000316c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003173  nop     dword ptr [rax+rax+00h]
0x140003178  mov     [rbx+50h], al
0x14000317b  mov     rax, [rbx+58h]
0x14000317f  test    rax, rax
0x140003182  jz      short loc_140003192
0x140003184  lock or dword ptr [rax+20h], 40h
0x140003189  mov     rax, [rax+8]
0x14000318d  test    rax, rax
0x140003190  jnz     short loc_140003184
0x140003192  movzx   edx, byte ptr [rbx+50h]; NewIrql
0x140003196  lea     rcx, [rbx+48h]; SpinLock
0x14000319a  call    cs:__imp_KeReleaseSpinLock
0x1400031a1  nop     dword ptr [rax+rax+00h]
0x1400031a6  mov     eax, 1
0x1400031ab  xchg    eax, [rbx+60h]
0x1400031ae  test    eax, eax
0x1400031b0  jnz     short loc_1400031D6
0x1400031b2  lock inc dword ptr [rbx+30h]
0x1400031b6  mov     rcx, [rbx+68h]; IoWorkItem
0x1400031ba  lea     rdx, lldpDeliverChangeNotifications; WorkerRoutine
0x1400031c1  mov     r9, rbx; Context
0x1400031c4  mov     r8d, 1; QueueType
0x1400031ca  call    cs:__imp_IoQueueWorkItemEx
0x1400031d1  nop     dword ptr [rax+rax+00h]
0x1400031d6  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 2
0x1400031dd  jz      loc_1400032BE
0x1400031e3  mov     r9d, [rbx+80h]
0x1400031ea  lea     rdx, RemoteMibShutdown
0x1400031f1  mov     [rsp+78h+var_50], r15
0x1400031f6  mov     [rsp+78h+var_58], r14d
0x1400031fb  call    McTemplateK0qqbr1_EtwWriteTransfer
0x140003200  jmp     loc_1400032BE
0x140003205  cmp     [rdi+10h], ebp
0x140003208  jnz     short loc_140003222
0x14000320a  mov     r8, rbp; Size
0x14000320d  lea     rcx, [rdi+18h]; Buf1
0x140003211  mov     rdx, r15; Buf2
0x140003214  call    memcmp
0x140003219  test    eax, eax
0x14000321b  jnz     short loc_140003222
0x14000321d  xor     bpl, bpl
0x140003220  jmp     short loc_14000326D
0x140003222  mov     r8, rbp; Size
0x140003225  lea     rcx, [rdi+18h]; void *
0x140003229  mov     rdx, r15; Src
0x14000322c  call    memmove
0x140003231  mov     [rdi+10h], ebp
0x140003234  xor     edx, edx
0x140003236  mov     r8d, 2
0x14000323c  mov     rcx, rbx; Context
0x14000323f  mov     bpl, 1
0x140003242  call    lldpQueueChangeNotificationEx
0x140003247  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 4
0x14000324e  jz      short loc_14000326D
0x140003250  mov     r9d, [rbx+80h]
0x140003257  lea     rdx, RemoteMibChanged
0x14000325e  mov     [rsp+78h+var_50], r15
0x140003263  mov     [rsp+78h+var_58], r14d
0x140003268  call    McTemplateK0qqbr1_EtwWriteTransfer
0x14000326d  mov     r14, [rsp+78h+Buf2]
0x140003275  lea     rcx, [rdi+4]; Buf1
0x140003279  mov     rdx, r14; Buf2
0x14000327c  mov     r8d, 6; Size
0x140003282  call    memcmp
0x140003287  test    eax, eax
0x140003289  jz      short loc_1400032AD
0x14000328b  mov     eax, [r14]
0x14000328e  xor     edx, edx
0x140003290  mov     [rdi+4], eax
0x140003293  mov     r8d, 8
0x140003299  movzx   eax, word ptr [r14+4]
0x14000329e  mov     rcx, rbx; Context
0x1400032a1  mov     [rdi+8], ax
0x1400032a5  mov     bpl, 1
0x1400032a8  call    lldpQueueChangeNotificationEx
0x1400032ad  lea     rcx, [rbx+138h]; Timer
0x1400032b4  mov     r8b, 1
0x1400032b7  mov     edx, esi
0x1400032b9  call    lldpSetTimer
0x1400032be  mov     rax, [rsp+78h+arg_0]
0x1400032c6  mov     [rbx+0E0h], rax
0x1400032cd  test    bpl, bpl
0x1400032d0  jnz     loc_1400033A9
0x1400032d6  jmp     loc_1400033B0
0x1400032db  mov     edi, [rsp+78h+arg_30]
0x1400032e2  test    edi, edi
0x1400032e4  jz      loc_14000336D
0x1400032ea  cmp     byte ptr [rbx+0D8h], 0
0x1400032f1  jnz     short loc_140003337
0x1400032f3  xor     edx, edx
0x1400032f5  mov     byte ptr [rbx+0D8h], 1
0x1400032fc  mov     r8d, 8
0x140003302  mov     rcx, rbx; Context
0x140003305  call    lldpQueueChangeNotificationEx
0x14000330a  lea     rcx, [rbx+1C0h]; Timer
0x140003311  xor     r8d, r8d
0x140003314  mov     edx, edi
0x140003316  call    lldpSetTimer
0x14000331b  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor+1, 1
0x140003322  jz      short loc_140003337
0x140003324  mov     r9d, [rbx+80h]
0x14000332b  lea     rdx, TooManyNeighborsBegin
0x140003332  call    McTemplateK0q_EtwWriteTransfer
0x140003337  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 8
0x14000333e  jz      short loc_14000336D
0x140003340  mov     rcx, [rbx+3C8h]
0x140003347  mov     r9d, [rbx+80h]
0x14000334e  mov     [rsp+78h+var_40], r15
0x140003353  mov     [rsp+78h+var_48], r14d
0x140003358  lea     rax, [rcx+18h]
0x14000335c  mov     [rsp+78h+var_50], rax
0x140003361  mov     eax, [rcx+0Ch]
0x140003364  mov     [rsp+78h+var_58], eax
0x140003368  call    McTemplateK0qqbr1qbr3_EtwWriteTransfer
0x14000336d  cmp     byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 0
0x140003374  jge     short loc_140003392
0x140003376  mov     eax, [r13+58h]
0x14000337a  mov     r9d, [rbx+80h]
0x140003381  mov     dword ptr [rsp+78h+var_50], 9
0x140003389  mov     [rsp+78h+var_58], eax
0x14000338d  call    McTemplateK0qqq_EtwWriteTransfer
0x140003392  lock inc qword ptr [rbx+378h]
0x14000339a  mov     rax, [rsp+78h+arg_0]
0x1400033a2  mov     [rbx+0E0h], rax
0x1400033a9  mov     [rbx+0E8h], rax
0x1400033b0  mov     r12, [rsp+78h+var_30]
0x1400033b5  mov     rdi, [rsp+78h+arg_8]
0x1400033bd  mov     r14, [rsp+78h+var_38]
0x1400033c2  add     rsp, 50h
0x1400033c6  pop     r15
0x1400033c8  pop     r13
0x1400033ca  pop     rsi
0x1400033cb  pop     rbp
0x1400033cc  pop     rbx
0x1400033cd  retn
```
