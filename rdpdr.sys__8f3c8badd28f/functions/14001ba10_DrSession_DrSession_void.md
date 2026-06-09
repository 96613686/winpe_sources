# DrSession::DrSession(void)

- ea: `0x14001ba10`
- end: `0x14001bca9`
- name: `??0DrSession@@QEAA@XZ`
- size: `665`
- prototype: `DrSession *__fastcall(DrSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140026a48`

## callees

- `0x140002bf8`
- `0x140002c60`
- `0x1400036c0`
- `0x14001ba10`
- `0x14002c0d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001babb`
- `ntoskrnl!KeInitializeEvent` at `0x14001babb`

## string_xrefs

- `0x14001bb25`: `QuerDirCacheLock`

## pseudocode

```c
DrSession *__fastcall DrSession::DrSession(DrSession *this)
{
  *((_BYTE *)this + 8) = 1;
  *(_QWORD *)this = &DrSession::`vftable'{for `RefCount'};
  *((_QWORD *)this + 3) = &DrSession::`vftable'{for `ISessionPacketReceiver'};
  *(_QWORD *)((char *)this + 12) = 0;
  *((_QWORD *)this + 4) = &DrSession::`vftable'{for `ISessionPacketSender'};
  *((_QWORD *)this + 5) = 0;
  DoubleList::DoubleList((DrSession *)((char *)this + 48), "PacketReceiversLock");
  KernelResource::KernelResource((DrSession *)((char *)this + 208), "ConnectNotificationLock");
  KernelResource::KernelResource((DrSession *)((char *)this + 336), "ConnectRDPDYNNotificationLock");
  KernelResource::KernelResource((DrSession *)((char *)this + 464), "ChannelLock");
  *((_BYTE *)this + 632) = 1;
  *((_QWORD *)this + 78) = &KernelEvent::`vftable';
  *((_DWORD *)this + 159) = 0;
  KeInitializeEvent((PRKEVENT)((char *)this + 640), NotificationEvent, 0);
  *((_BYTE *)this + 696) = 1;
  *((_QWORD *)this + 86) = &TopObj::`vftable';
  *((_DWORD *)this + 175) = 0;
  *((_QWORD *)this + 88) = &DrExchangeManager::`vftable'{for `ISessionPacketReceiver'};
  *((_QWORD *)this + 89) = &DrExchangeManager::`vftable'{for `ISessionPacketSender'};
  *((_QWORD *)this + 90) = 0;
  *((_DWORD *)this + 182) = 0;
  *((_QWORD *)this + 92) = 0;
  DrDeviceManager::DrDeviceManager((DrSession *)((char *)this + 912));
  KernelResource::KernelResource((DrSession *)((char *)this + 1392), "QuerDirCacheLock");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_5c887063686c325024567ba4647d07cf_Traceguids, this);
  *((_DWORD *)this + 148) &= ~0x400u;
  *((_WORD *)this + 390) = 0;
  *(_QWORD *)((char *)this + 596) = 4;
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 154) = 0;
  *((_DWORD *)this + 186) = 0;
  *((_QWORD *)this + 163) = 0;
  *((_QWORD *)this + 164) = 0;
  *((_DWORD *)this + 330) = 0;
  *((_QWORD *)this + 166) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_QWORD *)this + 170) = 0;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_DWORD *)this + 346) = 1;
  *((_DWORD *)this + 380) = 0;
  *((_DWORD *)this + 381) = 64;
  *((_DWORD *)this + 382) = 100;
  *(_OWORD *)((char *)this + 1220) = xmmword_140009400;
  *(_OWORD *)((char *)this + 1236) = xmmword_140009410;
  *(_OWORD *)((char *)this + 1252) = xmmword_140009420;
  *(_OWORD *)((char *)this + 1268) = xmmword_140009430;
  *(_OWORD *)((char *)this + 1284) = xmmword_140009440;
  *((_DWORD *)this + 325) = 1;
  *((_OWORD *)this + 71) = xmmword_1400093A0;
  *((_OWORD *)this + 72) = xmmword_1400093B0;
  *((_OWORD *)this + 73) = xmmword_1400093C0;
  *((_OWORD *)this + 74) = xmmword_1400093D0;
  *((_OWORD *)this + 75) = xmmword_1400093E0;
  *((_DWORD *)this + 304) = 0;
  return this;
}

```

## disassembly

```asm
0x14001ba10  mov     [rsp+arg_0], rbx
0x14001ba15  push    rdi
0x14001ba16  sub     rsp, 20h
0x14001ba1a  lea     rax, ??_7DrSession@@6BRefCount@@@; const DrSession::`vftable'{for `RefCount'}
0x14001ba21  mov     byte ptr [rcx+8], 1
0x14001ba25  mov     [rcx], rax
0x14001ba28  lea     rdx, aPacketreceiver; "PacketReceiversLock"
0x14001ba2f  lea     rax, ??_7DrSession@@6BISessionPacketReceiver@@@; const DrSession::`vftable'{for `ISessionPacketReceiver'}
0x14001ba36  xor     edi, edi
0x14001ba38  mov     [rcx+18h], rax
0x14001ba3c  mov     rbx, rcx
0x14001ba3f  lea     rax, ??_7DrSession@@6BISessionPacketSender@@@; const DrSession::`vftable'{for `ISessionPacketSender'}
0x14001ba46  mov     [rcx+0Ch], rdi
0x14001ba4a  mov     [rcx+20h], rax
0x14001ba4e  mov     [rcx+28h], rdi
0x14001ba52  add     rcx, 30h ; '0'; this
0x14001ba56  call    ??0DoubleList@@QEAA@PEBD@Z; DoubleList::DoubleList(char const *)
0x14001ba5b  lea     rcx, [rbx+0D0h]; this
0x14001ba62  lea     rdx, aConnectnotific; "ConnectNotificationLock"
0x14001ba69  call    ??0KernelResource@@QEAA@PEBD@Z; KernelResource::KernelResource(char const *)
0x14001ba6e  lea     rcx, [rbx+150h]; this
0x14001ba75  lea     rdx, aConnectrdpdynn; "ConnectRDPDYNNotificationLock"
0x14001ba7c  call    ??0KernelResource@@QEAA@PEBD@Z; KernelResource::KernelResource(char const *)
0x14001ba81  lea     rcx, [rbx+1D0h]; this
0x14001ba88  lea     rdx, aChannellock; "ChannelLock"
0x14001ba8f  call    ??0KernelResource@@QEAA@PEBD@Z; KernelResource::KernelResource(char const *)
0x14001ba94  lea     rax, ??_7KernelEvent@@6B@; const KernelEvent::`vftable'
0x14001ba9b  mov     byte ptr [rbx+278h], 1
0x14001baa2  lea     rcx, [rbx+280h]; Event
0x14001baa9  mov     [rbx+270h], rax
0x14001bab0  xor     r8d, r8d; State
0x14001bab3  mov     [rbx+27Ch], edi
0x14001bab9  xor     edx, edx; Type
0x14001babb  call    cs:__imp_KeInitializeEvent
0x14001bac2  nop     dword ptr [rax+rax+00h]
0x14001bac7  lea     rax, ??_7TopObj@@6B@; const TopObj::`vftable'
0x14001bace  mov     byte ptr [rbx+2B8h], 1
0x14001bad5  mov     [rbx+2B0h], rax
0x14001badc  lea     rcx, [rbx+390h]; this
0x14001bae3  lea     rax, ??_7DrExchangeManager@@6BISessionPacketReceiver@@@; const DrExchangeManager::`vftable'{for `ISessionPacketReceiver'}
0x14001baea  mov     [rbx+2BCh], edi
0x14001baf0  mov     [rbx+2C0h], rax
0x14001baf7  lea     rax, ??_7DrExchangeManager@@6BISessionPacketSender@@@; const DrExchangeManager::`vftable'{for `ISessionPacketSender'}
0x14001bafe  mov     [rbx+2C8h], rax
0x14001bb05  mov     [rbx+2D0h], rdi
0x14001bb0c  mov     [rbx+2D8h], edi
0x14001bb12  mov     [rbx+2E0h], rdi
0x14001bb19  call    ??0DrDeviceManager@@QEAA@XZ; DrDeviceManager::DrDeviceManager(void)
0x14001bb1e  lea     rcx, [rbx+570h]; this
0x14001bb25  lea     rdx, aQuerdircachelo; "QuerDirCacheLock"
0x14001bb2c  call    ??0KernelResource@@QEAA@PEBD@Z; KernelResource::KernelResource(char const *)
0x14001bb31  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb38  lea     rax, WPP_GLOBAL_Control
0x14001bb3f  cmp     rcx, rax
0x14001bb42  jz      short loc_14001BB60
0x14001bb44  cmp     byte ptr [rcx+29h], 4
0x14001bb48  jb      short loc_14001BB60
0x14001bb4a  mov     rcx, [rcx+18h]
0x14001bb4e  lea     edx, [rdi+0Ah]
0x14001bb51  mov     r9, rbx
0x14001bb54  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14001bb5b  call    WPP_SF_q
0x14001bb60  btr     dword ptr [rbx+250h], 0Ah
0x14001bb68  mov     [rbx+30Ch], di
0x14001bb6f  mov     qword ptr [rbx+254h], 4
0x14001bb7a  mov     [rbx+260h], rdi
0x14001bb81  mov     [rbx+268h], edi
0x14001bb87  mov     [rbx+2E8h], edi
0x14001bb8d  mov     [rbx+518h], rdi
0x14001bb94  mov     [rbx+520h], rdi
0x14001bb9b  mov     [rbx+528h], edi
0x14001bba1  mov     [rbx+530h], rdi
0x14001bba8  mov     [rbx+540h], rdi
0x14001bbaf  mov     [rbx+538h], rdi
0x14001bbb6  mov     [rbx+550h], rdi
0x14001bbbd  mov     [rbx+548h], rdi
0x14001bbc4  mov     [rbx+558h], rdi
0x14001bbcb  mov     [rbx+560h], rdi
0x14001bbd2  mov     dword ptr [rbx+568h], 1
0x14001bbdc  mov     [rbx+5F0h], edi
0x14001bbe2  mov     dword ptr [rbx+5F4h], 40h ; '@'
0x14001bbec  mov     dword ptr [rbx+5F8h], 64h ; 'd'
0x14001bbf6  movaps  xmm0, cs:xmmword_140009400
0x14001bbfd  movups  xmmword ptr [rbx+4C4h], xmm0
0x14001bc04  movaps  xmm1, cs:xmmword_140009410
0x14001bc0b  movups  xmmword ptr [rbx+4D4h], xmm1
0x14001bc12  movaps  xmm0, cs:xmmword_140009420
0x14001bc19  movups  xmmword ptr [rbx+4E4h], xmm0
0x14001bc20  movaps  xmm1, cs:xmmword_140009430
0x14001bc27  movups  xmmword ptr [rbx+4F4h], xmm1
0x14001bc2e  movaps  xmm0, cs:xmmword_140009440
0x14001bc35  movups  xmmword ptr [rbx+504h], xmm0
0x14001bc3c  mov     eax, cs:dword_140009450
0x14001bc42  mov     [rbx+514h], eax
0x14001bc48  movaps  xmm0, cs:xmmword_1400093A0
0x14001bc4f  movups  xmmword ptr [rbx+470h], xmm0
0x14001bc56  movaps  xmm1, cs:xmmword_1400093B0
0x14001bc5d  movups  xmmword ptr [rbx+480h], xmm1
0x14001bc64  movaps  xmm0, cs:xmmword_1400093C0
0x14001bc6b  movups  xmmword ptr [rbx+490h], xmm0
0x14001bc72  movaps  xmm1, cs:xmmword_1400093D0
0x14001bc79  movups  xmmword ptr [rbx+4A0h], xmm1
0x14001bc80  movaps  xmm0, cs:xmmword_1400093E0
0x14001bc87  movups  xmmword ptr [rbx+4B0h], xmm0
0x14001bc8e  mov     eax, cs:dword_1400093F0
0x14001bc94  mov     [rbx+4C0h], eax
0x14001bc9a  mov     rax, rbx
0x14001bc9d  mov     rbx, [rsp+28h+arg_0]
0x14001bca2  add     rsp, 20h
0x14001bca6  pop     rdi
0x14001bca7  retn
```
