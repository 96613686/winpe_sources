# DrSmartCard::CompleteIo(void)

- ea: `0x14001fd20`
- end: `0x14001fe25`
- name: `?CompleteIo@DrSmartCard@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(DrSmartCard *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14001dcb4`
- `0x14001fb94`
- `0x14001fe30`
- `0x140020100`

## callees

- `0x1400016a0`
- `0x140001c50`
- `0x140001e60`
- `0x140002260`
- `0x140002564`
- `0x14000324c`
- `0x1400117e0`
- `0x14001fd20`
- `0x140024020`
- `0x140028ec0`
- `0x140029e50`

## pseudocode

```c
void __fastcall DrSmartCard::CompleteIo(DrSmartCard *this)
{
  DoubleList *v1; // rbx
  struct ListEntry *v3; // rsi
  __int64 v4; // rcx
  DoubleList *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (DrSmartCard *)((char *)this + 80);
  DoubleList::LockExclusive((DrSmartCard *)((char *)this + 80));
  v3 = DoubleList::First(v1);
  while ( v3 )
  {
    v4 = *((_QWORD *)this + 4);
    v6 = 0;
    if ( (unsigned int)DrExchangeManager::Find(v4 + 688, *((unsigned __int16 *)v3 + 8), &v6)
      && (unsigned int)DrDevice::MarkBusy(v5, &v6) )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v6 + 32) + 48LL) )
      {
        DrDevice::CompleteBusyExchange((__int64)this, (__int64)&v6, 0, 0);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids);
        DrDevice::DiscardBusyExchange(this, &v6);
      }
    }
    DoubleList::RemoveEntry(v5, v3);
    v3 = DoubleList::First(v1);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v6);
  }
  DoubleList::Unlock(v1);
}

```

## disassembly

```asm
0x14001fd20  mov     [rsp+arg_8], rbx
0x14001fd25  mov     [rsp+arg_10], rsi
0x14001fd2a  push    rdi
0x14001fd2b  sub     rsp, 20h
0x14001fd2f  lea     rbx, [rcx+50h]
0x14001fd33  mov     rdi, rcx
0x14001fd36  mov     rcx, rbx; this
0x14001fd39  call    ?LockExclusive@DoubleList@@QEAAXXZ; DoubleList::LockExclusive(void)
0x14001fd3e  mov     rcx, rbx; this
0x14001fd41  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14001fd46  mov     rsi, rax
0x14001fd49  test    rax, rax
0x14001fd4c  jz      loc_14001FE0C
0x14001fd52  mov     rcx, [rdi+20h]
0x14001fd56  lea     r8, [rsp+28h+arg_0]
0x14001fd5b  mov     [rsp+28h+arg_0], 0
0x14001fd64  add     rcx, 2B0h
0x14001fd6b  movzx   edx, word ptr [rsi+10h]
0x14001fd6f  call    ?Find@DrExchangeManager@@QEAAHGAEAV?$SmartPtr@VDrExchange@@@@@Z; DrExchangeManager::Find(ushort,SmartPtr<DrExchange> &)
0x14001fd74  test    eax, eax
0x14001fd76  jz      short loc_14001FDE6
0x14001fd78  lea     rdx, [rsp+28h+arg_0]
0x14001fd7d  call    ?MarkBusy@DrDevice@@IEAAHAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::MarkBusy(SmartPtr<DrExchange> &)
0x14001fd82  test    eax, eax
0x14001fd84  jz      short loc_14001FDE6
0x14001fd86  mov     rax, [rsp+28h+arg_0]
0x14001fd8b  mov     rcx, [rax+20h]
0x14001fd8f  cmp     qword ptr [rcx+30h], 0
0x14001fd94  jz      short loc_14001FDAB
0x14001fd96  xor     r9d, r9d
0x14001fd99  lea     rdx, [rsp+28h+arg_0]
0x14001fd9e  xor     r8d, r8d
0x14001fda1  mov     rcx, rdi
0x14001fda4  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x14001fda9  jmp     short loc_14001FDE6
0x14001fdab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fdb2  lea     rax, WPP_GLOBAL_Control
0x14001fdb9  cmp     rcx, rax
0x14001fdbc  jz      short loc_14001FDD9
0x14001fdbe  cmp     byte ptr [rcx+29h], 4
0x14001fdc2  jb      short loc_14001FDD9
0x14001fdc4  mov     rcx, [rcx+18h]
0x14001fdc8  lea     r8, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids
0x14001fdcf  mov     edx, 1Bh
0x14001fdd4  call    WPP_SF_
0x14001fdd9  lea     rdx, [rsp+28h+arg_0]
0x14001fdde  mov     rcx, rdi
0x14001fde1  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x14001fde6  mov     rdx, rsi; struct ListEntry *
0x14001fde9  call    ?RemoveEntry@DoubleList@@QEAAXPEAVListEntry@@@Z; DoubleList::RemoveEntry(ListEntry *)
0x14001fdee  mov     rcx, rbx; this
0x14001fdf1  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14001fdf6  lea     rcx, [rsp+28h+arg_0]
0x14001fdfb  mov     rsi, rax
0x14001fdfe  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001fe03  test    rsi, rsi
0x14001fe06  jnz     loc_14001FD52
0x14001fe0c  mov     rcx, rbx; this
0x14001fe0f  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x14001fe14  mov     rbx, [rsp+28h+arg_8]
0x14001fe19  mov     rsi, [rsp+28h+arg_10]
0x14001fe1e  add     rsp, 20h
0x14001fe22  pop     rdi
0x14001fe23  retn
```
