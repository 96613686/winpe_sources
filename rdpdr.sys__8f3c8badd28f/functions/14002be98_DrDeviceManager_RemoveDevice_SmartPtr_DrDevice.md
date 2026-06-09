# DrDeviceManager::RemoveDevice(SmartPtr<DrDevice> &)

- ea: `0x14002be98`
- end: `0x14002bf6e`
- name: `?RemoveDevice@DrDeviceManager@@QEAAXAEAV?$SmartPtr@VDrDevice@@@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140020788`
- `0x140027fe0`
- `0x14002c190`

## callees

- `0x140001660`
- `0x140001c50`
- `0x140001ef0`
- `0x140002564`
- `0x14000324c`
- `0x140006560`
- `0x14002be98`

## pseudocode

```c
__int64 __fastcall DrDeviceManager::RemoveDevice(__int64 a1, RefCount **a2)
{
  __int64 v2; // r14
  struct ListEntry *i; // rax
  struct ListEntry ***v6; // rbx
  DoubleList *v7; // rcx

  v2 = a1 + 64;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 64) + 24LL))(a1 + 64);
  for ( i = DoubleList::First((DoubleList *)(a1 + 32)); ; i = DoubleList::Next((DoubleList *)(a1 + 32), i) )
  {
    v6 = (struct ListEntry ***)i;
    if ( !i )
      break;
    if ( *((RefCount **)i + 2) == *a2 )
    {
      v7 = (DoubleList *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
      DoubleList::RemoveEntry(v7, v6);
      RefCount::Release(*a2);
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 64) + 32LL))(v2);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 64) + 32LL))(v2);
}

```

## disassembly

```asm
0x14002be98  push    rbx
0x14002be9a  push    rbp
0x14002be9b  push    rsi
0x14002be9c  push    rdi
0x14002be9d  push    r14
0x14002be9f  sub     rsp, 20h
0x14002bea3  lea     r14, [rcx+40h]
0x14002bea7  mov     rbp, rcx
0x14002beaa  mov     rax, [r14]
0x14002bead  mov     rcx, r14
0x14002beb0  mov     rdi, rdx
0x14002beb3  mov     rax, [rax+18h]
0x14002beb7  call    _guard_dispatch_icall
0x14002bebc  lea     rcx, [rbp+20h]; this
0x14002bec0  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14002bec5  mov     rbx, rax
0x14002bec8  test    rax, rax
0x14002becb  jz      short loc_14002BF24
0x14002becd  mov     rcx, [rdi]
0x14002bed0  cmp     [rax+10h], rcx
0x14002bed4  jz      short loc_14002BEE4
0x14002bed6  mov     rdx, rax; struct ListEntry *
0x14002bed9  lea     rcx, [rbp+20h]; this
0x14002bedd  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x14002bee2  jmp     short loc_14002BEC5
0x14002bee4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002beeb  lea     rax, WPP_GLOBAL_Control
0x14002bef2  cmp     rcx, rax
0x14002bef5  jz      short loc_14002BF12
0x14002bef7  cmp     byte ptr [rcx+29h], 5
0x14002befb  jb      short loc_14002BF12
0x14002befd  mov     rcx, [rcx+18h]
0x14002bf01  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x14002bf08  mov     edx, 2Fh ; '/'
0x14002bf0d  call    WPP_SF_
0x14002bf12  mov     rdx, rbx; struct ListEntry *
0x14002bf15  call    ?RemoveEntry@DoubleList@@QEAAXPEAVListEntry@@@Z; DoubleList::RemoveEntry(ListEntry *)
0x14002bf1a  mov     rcx, [rdi]; this
0x14002bf1d  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002bf22  jmp     short loc_14002BF52
0x14002bf24  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf2b  lea     rax, WPP_GLOBAL_Control
0x14002bf32  cmp     rcx, rax
0x14002bf35  jz      short loc_14002BF52
0x14002bf37  cmp     byte ptr [rcx+29h], 5
0x14002bf3b  jb      short loc_14002BF52
0x14002bf3d  mov     rcx, [rcx+18h]
0x14002bf41  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x14002bf48  mov     edx, 30h ; '0'
0x14002bf4d  call    WPP_SF_
0x14002bf52  mov     rax, [rbp+40h]
0x14002bf56  mov     rcx, r14
0x14002bf59  mov     rax, [rax+20h]
0x14002bf5d  call    _guard_dispatch_icall
0x14002bf62  add     rsp, 20h
0x14002bf66  pop     r14
0x14002bf68  pop     rdi
0x14002bf69  pop     rsi
0x14002bf6a  pop     rbp
0x14002bf6b  pop     rbx
0x14002bf6c  retn
```
