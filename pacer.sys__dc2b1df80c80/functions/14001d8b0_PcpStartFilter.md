# PcpStartFilter

- ea: `0x14001d8b0`
- end: `0x14001db57`
- name: `PcpStartFilter`
- size: `679`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000eb54`
- `0x140011fa8`
- `0x1400120c8`
- `0x140013600`
- `0x14001d8b0`
- `0x14001fee0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001da5e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001da5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d8fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d916`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d92e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d8fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d916`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d92e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001db2f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001db2f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d9f8`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d9f8`
- `NDIS!NdisFRegisterFilterDriver` at `0x14001dac6`
- `NDIS!NdisFRegisterFilterDriver` at `0x14001dac6`

## pseudocode

```c
unsigned int PcpStartFilter()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  unsigned int result; // eax
  int v4; // ebx
  struct _UNICODE_STRING v5; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v6; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE FilterDriverCharacteristics[240]; // [rsp+70h] [rbp-90h] BYREF
  int v9; // [rsp+170h] [rbp+70h] BYREF

  DestinationString = 0;
  v6 = 0;
  v5 = 0;
  memset(FilterDriverCharacteristics, 0, sizeof(FilterDriverCharacteristics));
  v9 = 0;
  RtlInitUnicodeString(&DestinationString, L"Psched");
  RtlInitUnicodeString(&v5, L"QoS Packet Scheduler");
  RtlInitUnicodeString(&v6, L"{b5f4d659-7daa-4565-8e41-be220ed60542}");
  memset(FilterDriverCharacteristics, 0, sizeof(FilterDriverCharacteristics));
  *(_DWORD *)FilterDriverCharacteristics = 15729547;
  *(_QWORD *)&FilterDriverCharacteristics[80] = PcFilterAttach;
  *(_QWORD *)&FilterDriverCharacteristics[4] = 88326;
  *(_QWORD *)&FilterDriverCharacteristics[88] = PcFilterDetach;
  *(_QWORD *)&FilterDriverCharacteristics[96] = PcFilterRestart;
  *(_QWORD *)&FilterDriverCharacteristics[104] = PcFilterPause;
  *(_QWORD *)&FilterDriverCharacteristics[72] = PcFilterSetModuleOptions;
  *(_QWORD *)&FilterDriverCharacteristics[152] = PcFilterRequest;
  *(_QWORD *)&FilterDriverCharacteristics[160] = &PcFilterRequestComplete;
  *(_QWORD *)&FilterDriverCharacteristics[176] = PcFilterPnPEventNotify;
  *(_QWORD *)&FilterDriverCharacteristics[184] = PcFilterPnPEvent;
  *(struct _UNICODE_STRING *)&FilterDriverCharacteristics[16] = v5;
  *(_QWORD *)&FilterDriverCharacteristics[192] = &PcFilterStatus;
  *(_QWORD *)&FilterDriverCharacteristics[64] = PcFilterSetOptions;
  *(struct _UNICODE_STRING *)&FilterDriverCharacteristics[32] = v6;
  *(struct _UNICODE_STRING *)&FilterDriverCharacteristics[48] = DestinationString;
  KeInitializeSpinLock(&PcgLineTableLock);
  PcgLineTable = 0;
  PcgLineTableLen = 0;
  PcgLineTableNextId = 0;
  qword_140018628 = (__int64)&PcgLineList;
  PcgLineList = &PcgLineList;
  ExInitializeNPagedLookasideList(&PcgNblCadLookasideList, 0, 0, 0x200u, 0x38u, 0x706F6350u, 0);
  PcpReadSettings(0, (__int64)&WPP_MAIN_CB.Reserved);
  *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock = 0;
  QosInit(v1, v0, v2, &v9);
  LOWORD(WPP_MAIN_CB.SecurityDescriptor) = v9;
  qword_140018830 = (__int64)&qword_140018828;
  qword_140018828 = (__int64)&qword_140018828;
  result = NdisFRegisterFilterDriver(
             *(PDRIVER_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels,
             &PcgFilterDriverContext,
             (PNDIS_FILTER_DRIVER_CHARACTERISTICS)FilterDriverCharacteristics,
             (PNDIS_HANDLE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink);
  v4 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids, result);
    }
    QosTerminate();
    ExDeleteNPagedLookasideList(&PcgNblCadLookasideList);
    result = -1073741823;
    if ( v4 < 0 )
      return v4;
  }
  else
  {
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 |= 2uLL;
    _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.DeviceQueue.Lock);
  }
  return result;
}

```

## disassembly

```asm
0x14001d8b0  mov     [rsp-8+arg_8], rbx
0x14001d8b5  push    rbp
0x14001d8b6  lea     rbp, [rsp-60h]
0x14001d8bb  sub     rsp, 160h
0x14001d8c2  xorps   xmm0, xmm0
0x14001d8c5  lea     rcx, [rsp+160h+FilterDriverCharacteristics]; void *
0x14001d8ca  xorps   xmm1, xmm1
0x14001d8cd  mov     ebx, 0F0h
0x14001d8d2  mov     r8d, ebx; Size
0x14001d8d5  xor     edx, edx; Val
0x14001d8d7  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x14001d8dc  movups  xmmword ptr [rsp+160h+var_110.Length], xmm1
0x14001d8e1  movups  xmmword ptr [rsp+160h+var_120.Length], xmm0
0x14001d8e6  call    memset
0x14001d8eb  lea     rdx, aPsched; "Psched"
0x14001d8f2  mov     [rbp+60h+arg_0], 0
0x14001d8f9  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x14001d8fe  call    cs:__imp_RtlInitUnicodeString
0x14001d905  nop     dword ptr [rax+rax+00h]
0x14001d90a  lea     rdx, aQosPacketSched; "QoS Packet Scheduler"
0x14001d911  lea     rcx, [rsp+160h+var_120]; DestinationString
0x14001d916  call    cs:__imp_RtlInitUnicodeString
0x14001d91d  nop     dword ptr [rax+rax+00h]
0x14001d922  lea     rdx, aB5f4d6597daa45; "{b5f4d659-7daa-4565-8e41-be220ed60542}"
0x14001d929  lea     rcx, [rsp+160h+var_110]; DestinationString
0x14001d92e  call    cs:__imp_RtlInitUnicodeString
0x14001d935  nop     dword ptr [rax+rax+00h]
0x14001d93a  mov     r8d, ebx; Size
0x14001d93d  lea     rcx, [rsp+160h+FilterDriverCharacteristics]; void *
0x14001d942  xor     edx, edx; Val
0x14001d944  call    memset
0x14001d949  movups  xmm0, xmmword ptr [rsp+160h+var_120.Length]
0x14001d94e  lea     rax, PcFilterAttach
0x14001d955  mov     dword ptr [rsp+160h+FilterDriverCharacteristics], 0F0038Bh
0x14001d95d  movups  xmm1, xmmword ptr [rsp+160h+var_110.Length]
0x14001d962  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+50h], rax
0x14001d966  lea     rcx, PcgLineTableLock; SpinLock
0x14001d96d  lea     rax, PcFilterDetach
0x14001d974  mov     qword ptr [rsp+160h+FilterDriverCharacteristics+4], 15906h
0x14001d97d  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+58h], rax
0x14001d981  lea     rax, PcFilterRestart
0x14001d988  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+60h], rax
0x14001d98c  lea     rax, PcFilterPause
0x14001d993  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+68h], rax
0x14001d997  lea     rax, PcFilterSetModuleOptions
0x14001d99e  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+48h], rax
0x14001d9a2  lea     rax, PcFilterRequest
0x14001d9a9  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+98h], rax
0x14001d9ad  lea     rax, PcFilterRequestComplete
0x14001d9b4  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+0A0h], rax
0x14001d9b8  lea     rax, PcFilterPnPEventNotify
0x14001d9bf  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+0B0h], rax
0x14001d9c3  lea     rax, PcFilterPnPEvent
0x14001d9ca  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+0B8h], rax
0x14001d9ce  lea     rax, PcFilterStatus
0x14001d9d5  movdqu  xmmword ptr [rbp+60h+FilterDriverCharacteristics+10h], xmm0
0x14001d9da  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+0C0h], rax
0x14001d9de  lea     rax, PcFilterSetOptions
0x14001d9e5  movups  xmm0, xmmword ptr [rsp+160h+DestinationString.Length]
0x14001d9ea  mov     qword ptr [rbp+60h+FilterDriverCharacteristics+40h], rax
0x14001d9ee  movdqu  xmmword ptr [rbp+60h+FilterDriverCharacteristics+20h], xmm1
0x14001d9f3  movdqu  xmmword ptr [rbp+60h+FilterDriverCharacteristics+30h], xmm0
0x14001d9f8  call    cs:__imp_KeInitializeSpinLock
0x14001d9ff  nop     dword ptr [rax+rax+00h]
0x14001da04  xor     eax, eax
0x14001da06  mov     cs:PcgLineTable, 0
0x14001da11  mov     cs:PcgLineTableLen, ax
0x14001da18  lea     rcx, PcgNblCadLookasideList; Lookaside
0x14001da1f  mov     cs:PcgLineTableNextId, ax
0x14001da26  mov     r9d, 200h; Flags
0x14001da2c  lea     rax, PcgLineList
0x14001da33  xor     r8d, r8d; Free
0x14001da36  mov     cs:qword_140018628, rax
0x14001da3d  xor     edx, edx; Allocate
0x14001da3f  mov     cs:PcgLineList, rax
0x14001da46  xor     eax, eax
0x14001da48  mov     [rsp+160h+Depth], ax; Depth
0x14001da4d  mov     [rsp+160h+Tag], 706F6350h; Tag
0x14001da55  mov     [rsp+160h+Size], 38h ; '8'; Size
0x14001da5e  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001da65  nop     dword ptr [rax+rax+00h]
0x14001da6a  lea     rdx, WPP_MAIN_CB.Reserved
0x14001da71  xor     ecx, ecx
0x14001da73  call    PcpReadSettings
0x14001da78  lea     r9, [rbp+60h+arg_0]
0x14001da7c  mov     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header, 0
0x14001da87  call    QosInit
0x14001da8c  movzx   eax, word ptr [rbp+60h+arg_0]
0x14001da90  mov     word ptr cs:WPP_MAIN_CB.SecurityDescriptor, ax
0x14001da97  lea     rax, qword_140018828
0x14001da9e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; DriverObject
0x14001daa5  lea     r9, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; NdisFilterDriverHandle
0x14001daac  lea     r8, [rsp+160h+FilterDriverCharacteristics]; FilterDriverCharacteristics
0x14001dab1  mov     cs:qword_140018830, rax
0x14001dab8  lea     rdx, PcgFilterDriverContext; FilterDriverContext
0x14001dabf  mov     cs:qword_140018828, rax
0x14001dac6  call    cs:__imp_NdisFRegisterFilterDriver
0x14001dacd  nop     dword ptr [rax+rax+00h]
0x14001dad2  mov     ebx, eax
0x14001dad4  test    eax, eax
0x14001dad6  jnz     short loc_14001DAE9
0x14001dad8  or      qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 2
0x14001dae0  lock inc dword ptr cs:WPP_MAIN_CB.DeviceQueue.Lock
0x14001dae7  jmp     short loc_14001DB45
0x14001dae9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001daf0  lea     rax, WPP_GLOBAL_Control
0x14001daf7  cmp     rcx, rax
0x14001dafa  jz      short loc_14001DB23
0x14001dafc  cmp     byte ptr [rcx+29h], 2
0x14001db00  jb      short loc_14001DB23
0x14001db02  test    dword ptr [rcx+2Ch], 800h
0x14001db09  jz      short loc_14001DB23
0x14001db0b  mov     rcx, [rcx+18h]
0x14001db0f  lea     r8, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids
0x14001db16  mov     edx, 15h
0x14001db1b  mov     r9d, ebx
0x14001db1e  call    WPP_SF_D
0x14001db23  call    QosTerminate
0x14001db28  lea     rcx, PcgNblCadLookasideList; Lookaside
0x14001db2f  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001db36  nop     dword ptr [rax+rax+00h]
0x14001db3b  test    ebx, ebx
0x14001db3d  mov     eax, 0C0000001h
0x14001db42  cmovs   eax, ebx
0x14001db45  mov     rbx, [rsp+160h+arg_8]
0x14001db4d  add     rsp, 160h
0x14001db54  pop     rbp
0x14001db55  retn
```
