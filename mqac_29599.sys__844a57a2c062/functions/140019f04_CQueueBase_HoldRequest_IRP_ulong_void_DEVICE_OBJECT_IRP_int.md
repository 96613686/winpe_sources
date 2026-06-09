# CQueueBase::HoldRequest(_IRP *,ulong,void (*)(_DEVICE_OBJECT *,_IRP *),int)

- ea: `0x140019f04`
- end: `0x14001a083`
- name: `?HoldRequest@CQueueBase@@IEAAJPEAU_IRP@@KP6AXPEAU_DEVICE_OBJECT@@0@ZH@Z`
- size: `383`
- prototype: `int(CQueueBase *__hidden this, struct _IRP *, unsigned int, void (*)(struct _DEVICE_OBJECT *, struct _IRP *), int)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001a220`
- `0x14001b900`
- `0x14001be10`
- `0x14001c000`
- `0x14001c2d0`
- `0x14001f1c4`
- `0x14001f56c`
- `0x14001f714`
- `0x14001fcc8`
- `0x14001fe88`

## callees

- `0x14001268c`
- `0x140012754`
- `0x140019b60`
- `0x140019f04`
- `0x140020658`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a030`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a030`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a058`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a058`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a064`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a064`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140019fd7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140019fd7`

## pseudocode

```c
__int64 __fastcall CQueueBase::HoldRequest(
        CQueueBase *this,
        struct _IRP *a2,
        unsigned int a3,
        void (*a4)(struct _DEVICE_OBJECT *, struct _IRP *),
        int a5)
{
  __int64 v5; // rbp
  CBaseObject *v9; // rcx
  __int64 result; // rax
  struct _LIST_ENTRY *QuadPart; // rsi
  struct _DEVICE_OBJECT **v12; // rdi
  CScheduler *v13; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  struct _FAST_MUTEX *v15; // rcx
  union _LARGE_INTEGER v16; // [rsp+20h] [rbp-48h] BYREF
  KIRQL Irql; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  if ( a3 )
  {
    QuadPart = 0;
    v12 = (struct _DEVICE_OBJECT **)((char *)this + 64);
    v16.QuadPart = 0;
    if ( !a5 )
    {
      result = ACpIrp2Xact(*v12, a2, (struct CTransaction **)&v16);
      if ( (int)result < 0 )
        return result;
      QuadPart = (struct _LIST_ENTRY *)v16.QuadPart;
    }
    a2->IoStatus.Status = -1073741536;
    if ( (_DWORD)v5 == -1
      || (v13 = (CScheduler *)*((_QWORD *)(*v12)->DeviceExtension + 45),
          v16.QuadPart = MEMORY[0xFFFFF78000000014] + 10000 * v5,
          (unsigned int)CScheduler::SchedAt(v13, &v16, a2, 1)) )
    {
      IoAcquireCancelSpinLock(&Irql);
      _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)a4);
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      XList<_IRP,168>::insert((char *)this + 40, a2);
      if ( QuadPart )
      {
        Blink = QuadPart[6].Blink;
        if ( Blink->Flink != &QuadPart[6] )
          __fastfail(3u);
        a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = QuadPart + 6;
        a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = Blink;
        Blink->Flink = &a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry;
        QuadPart[6].Blink = &a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry;
      }
      IoReleaseCancelSpinLock(Irql);
      if ( (_DWORD)v5 != -1 )
      {
        v15 = *(struct _FAST_MUTEX **)(*((_QWORD *)(*v12)->DeviceExtension + 45) + 72LL);
        if ( v15 )
        {
          ExReleaseFastMutexUnsafe(v15);
          KeLeaveCriticalRegion();
        }
      }
      return 259;
    }
    else
    {
      return 3221225626LL;
    }
  }
  else
  {
    if ( (*(_BYTE *)(&a2->Tail.CompletionKey + 3) & 7) != 3 )
    {
      v9 = (CBaseObject *)a2->Tail.Overlay.DriverContext[2];
      if ( v9 )
        CBaseObject::Release(v9);
    }
    return 3222143003LL;
  }
}

```

## disassembly

```asm
0x140019f04  push    rbx
0x140019f06  push    rbp
0x140019f07  push    rsi
0x140019f08  push    rdi
0x140019f09  push    r14
0x140019f0b  push    r15
0x140019f0d  sub     rsp, 38h
0x140019f11  mov     ebp, r8d
0x140019f14  mov     r15, r9
0x140019f17  mov     rbx, rdx
0x140019f1a  mov     r14, rcx
0x140019f1d  test    r8d, r8d
0x140019f20  jnz     short loc_140019F4A
0x140019f22  mov     eax, [rdx+90h]
0x140019f28  and     eax, 7
0x140019f2b  cmp     al, 3
0x140019f2d  jz      short loc_140019F40
0x140019f2f  mov     rcx, [rdx+88h]; this
0x140019f36  test    rcx, rcx
0x140019f39  jz      short loc_140019F40
0x140019f3b  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140019f40  mov     eax, 0C00E001Bh
0x140019f45  jmp     loc_14001A075
0x140019f4a  xor     esi, esi
0x140019f4c  lea     rdi, [rcx+40h]
0x140019f50  mov     qword ptr [rsp+68h+var_48], rsi
0x140019f55  cmp     [rsp+68h+arg_20], esi
0x140019f5c  jnz     short loc_140019F78
0x140019f5e  mov     rcx, [rdi]; struct _DEVICE_OBJECT *
0x140019f61  lea     r8, [rsp+68h+var_48]; struct CTransaction **
0x140019f66  call    ?ACpIrp2Xact@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAPEAVCTransaction@@@Z; ACpIrp2Xact(_DEVICE_OBJECT *,_IRP *,CTransaction * *)
0x140019f6b  test    eax, eax
0x140019f6d  js      loc_14001A075
0x140019f73  mov     rsi, qword ptr [rsp+68h+var_48]
0x140019f78  mov     dword ptr [rbx+30h], 0C0000120h
0x140019f7f  cmp     ebp, 0FFFFFFFFh
0x140019f82  jz      short loc_140019FCF
0x140019f84  mov     rax, [rdi]
0x140019f87  mov     r9d, 1; int
0x140019f8d  imul    rdx, rbp, 2710h
0x140019f94  mov     rcx, [rax+40h]
0x140019f98  mov     r8, rbx; void *
0x140019f9b  mov     rax, 0FFFFF78000000014h
0x140019fa5  mov     rax, [rax]
0x140019fa8  mov     rcx, [rcx+168h]; this
0x140019faf  add     rdx, rax
0x140019fb2  mov     qword ptr [rsp+68h+var_48], rdx
0x140019fb7  lea     rdx, [rsp+68h+var_48]; union _LARGE_INTEGER *
0x140019fbc  call    ?SchedAt@CScheduler@@QEAAHAEBT_LARGE_INTEGER@@PEAXH@Z; CScheduler::SchedAt(_LARGE_INTEGER const &,void *,int)
0x140019fc1  test    eax, eax
0x140019fc3  jnz     short loc_140019FCF
0x140019fc5  mov     eax, 0C000009Ah
0x140019fca  jmp     loc_14001A075
0x140019fcf  lea     rcx, [rsp+68h+Irql]; Irql
0x140019fd7  call    cs:__imp_IoAcquireCancelSpinLock
0x140019fde  nop     dword ptr [rax+rax+00h]
0x140019fe3  xchg    r15, [rbx+68h]
0x140019fe7  mov     rax, [rbx+0B8h]
0x140019fee  lea     rcx, [r14+28h]
0x140019ff2  mov     rdx, rbx
0x140019ff5  or      byte ptr [rax+3], 1
0x140019ff9  call    ?insert@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::insert(_IRP *)
0x140019ffe  test    rsi, rsi
0x14001a001  jz      short loc_14001A029
0x14001a003  lea     rcx, [rsi+60h]
0x14001a007  mov     rdx, [rcx+8]
0x14001a00b  cmp     [rdx], rcx
0x14001a00e  jz      short loc_14001A017
0x14001a010  mov     ecx, 3
0x14001a015  int     29h; Win8: RtlFailFast(ecx)
0x14001a017  lea     rax, [rbx+78h]
0x14001a01b  mov     [rax], rcx
0x14001a01e  mov     [rax+8], rdx
0x14001a022  mov     [rdx], rax
0x14001a025  mov     [rcx+8], rax
0x14001a029  mov     cl, [rsp+68h+Irql]; Irql
0x14001a030  call    cs:__imp_IoReleaseCancelSpinLock
0x14001a037  nop     dword ptr [rax+rax+00h]
0x14001a03c  cmp     ebp, 0FFFFFFFFh
0x14001a03f  jz      short loc_14001A070
0x14001a041  mov     rax, [rdi]
0x14001a044  mov     rcx, [rax+40h]
0x14001a048  mov     rax, [rcx+168h]
0x14001a04f  mov     rcx, [rax+48h]; FastMutex
0x14001a053  test    rcx, rcx
0x14001a056  jz      short loc_14001A070
0x14001a058  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001a05f  nop     dword ptr [rax+rax+00h]
0x14001a064  call    cs:__imp_KeLeaveCriticalRegion
0x14001a06b  nop     dword ptr [rax+rax+00h]
0x14001a070  mov     eax, 103h
0x14001a075  add     rsp, 38h
0x14001a079  pop     r15
0x14001a07b  pop     r14
0x14001a07d  pop     rdi
0x14001a07e  pop     rsi
0x14001a07f  pop     rbp
0x14001a080  pop     rbx
0x14001a081  retn
```
