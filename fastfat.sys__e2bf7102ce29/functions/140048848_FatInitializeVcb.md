# FatInitializeVcb

- ea: `0x140048848`
- end: `0x140048e26`
- name: `FatInitializeVcb`
- size: `1502`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140040674`

## callees

- `0x140001858`
- `0x140002b30`
- `0x1400076d8`
- `0x14000c230`
- `0x14000c680`
- `0x1400247f4`
- `0x14002e4b0`
- `0x14003db44`
- `0x140048848`
- `0x140048e6c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140048b04`
- `ntoskrnl!KeInitializeEvent` at `0x140048c60`
- `ntoskrnl!KeInitializeEvent` at `0x140048dac`
- `ntoskrnl!KeInitializeEvent` at `0x140048b04`
- `ntoskrnl!KeInitializeEvent` at `0x140048c60`
- `ntoskrnl!KeInitializeEvent` at `0x140048dac`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140048b26`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140048b26`
- `ntoskrnl!ObfReferenceObject` at `0x14004896a`
- `ntoskrnl!ObfReferenceObject` at `0x14004896a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140048ab0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140048ace`
- `ntoskrnl!ExInitializeResourceLite` at `0x140048ab0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140048ace`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005fc88`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005fca1`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005fc88`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005fca1`
- `ntoskrnl!FsRtlInitializeTunnelCache` at `0x1400488f5`
- `ntoskrnl!FsRtlInitializeTunnelCache` at `0x1400488f5`
- `ntoskrnl!FsRtlNotifyInitializeSync` at `0x140048ba4`
- `ntoskrnl!FsRtlNotifyInitializeSync` at `0x140048ba4`
- `ntoskrnl!KeInitializeTimer` at `0x140048c73`
- `ntoskrnl!KeInitializeTimer` at `0x140048c73`
- `ntoskrnl!KeInitializeDpc` at `0x140048c90`
- `ntoskrnl!KeInitializeDpc` at `0x140048c90`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005fd83`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005fd83`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048911`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fd0c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048911`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fd0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048953`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fd38`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048953`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fd38`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fcbf`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fcdd`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fcbf`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fcdd`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140048c0c`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140048c27`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140048c0c`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140048c27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fd5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fd94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fd5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fd94`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140048cb5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140048d43`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140048cb5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140048d43`
- `ntoskrnl!ObfDereferenceObject` at `0x14005fc6f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005fc6f`

## pseudocode

```c
__int64 __fastcall FatInitializeVcb(__int64 a1, _DWORD *a2, void *a3, __int64 a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ecx
  struct _DEVICE_OBJECT *v13; // rbx
  __int64 v14; // rdx
  int v15; // r8d
  SIZE_T v16; // r14
  PVOID PoolWithTag; // rax
  PVOID v18; // rbx
  unsigned int i; // edx
  unsigned __int64 v20; // rcx
  PVOID v21; // rax
  PVOID v22; // rbx
  __int64 result; // rax
  PFILE_OBJECT StreamFileObject; // [rsp+78h] [rbp-A0h]
  __int128 v25; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-50h]

  v25 = 0;
  v26 = 0;
  memset(a2, 0, 0x548u);
  *a2 = 88605953;
  FsRtlInitializeTunnelCache((TUNNEL *)(a2 + 258));
  ExAcquireResourceExclusiveLite(&Resource, (*(_DWORD *)(a1 + 68) & 2) != 0);
  v8 = (_QWORD *)qword_140017CB8;
  if ( *(__int64 **)qword_140017CB8 != &qword_140017CB0 )
    __fastfail(3u);
  *((_QWORD *)a2 + 15) = &qword_140017CB0;
  *((_QWORD *)a2 + 16) = v8;
  *v8 = a2 + 30;
  qword_140017CB8 = (__int64)(a2 + 30);
  ExReleaseResourceLite(&Resource);
  ObfReferenceObject(a3);
  *((_QWORD *)a2 + 17) = a3;
  *((_QWORD *)a2 + 24) = a4;
  *((_QWORD *)a2 + 96) = *(_QWORD *)(a4 + 16);
  FatPerformDevIoCtrl(v9, 2952212, a3);
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 16) + 52LL) & 1) != 0 )
    _InterlockedOr(a2 + 50, 2u);
  v10 = *(unsigned int *)(*(_QWORD *)(a4 + 16) + 52LL);
  if ( (v10 & 4) != 0 )
    _InterlockedOr(a2 + 50, 0x1000u);
  v11 = FatPerformDevIoCtrl(v10, 2953344, a3);
  v12 = -1;
  if ( v11 >= 0 )
    v12 = 0;
  a2[281] = v12;
  a2[51] = 1;
  ExInitializeResourceLite((PERESOURCE)a2 + 5);
  ExInitializeResourceLite((PERESOURCE)a2 + 6);
  a2[116] = 1;
  *((_QWORD *)a2 + 59) = 0;
  a2[120] = 0;
  KeInitializeEvent((PRKEVENT)(a2 + 122), SynchronizationEvent, 0);
  v13 = (struct _DEVICE_OBJECT *)*((_QWORD *)a2 + 96);
  FatPreallocateCloseContext();
  StreamFileObject = IoCreateStreamFileObject(0, v13);
  *((_QWORD *)a2 + 91) = StreamFileObject;
  FatSetFileObject(StreamFileObject, v14, a2, 0);
  _InterlockedAdd(a2 + 70, 1u);
  _InterlockedAdd(a2 + 71, 1u);
  *(_QWORD *)(*((_QWORD *)a2 + 91) + 40LL) = a2 + 184;
  *(_BYTE *)(*((_QWORD *)a2 + 91) + 74LL) = 1;
  *(_BYTE *)(*((_QWORD *)a2 + 91) + 75LL) = 1;
  *(_BYTE *)(*((_QWORD *)a2 + 91) + 76LL) = 1;
  *((_QWORD *)a2 + 101) = a2 + 200;
  *((_QWORD *)a2 + 100) = a2 + 200;
  FsRtlNotifyInitializeSync((PNOTIFY_SYNC *)a2 + 102);
  *((_QWORD *)&v25 + 1) = 62;
  *(_QWORD *)&v25 = 62;
  v26 = FatMaxLarge;
  LOBYTE(v15) = 1;
  FatInitializeCacheMap(*((_QWORD *)a2 + 91), (int)&v25, v15, (int)&qword_140017DB0, a2);
  FsRtlInitializeLargeMcb((PLARGE_MCB)a2 + 12, PagedPool);
  FsRtlInitializeLargeMcb((PLARGE_MCB)a2 + 13, PagedPool);
  a2[190] = 2;
  a2[206] = 1;
  *((_QWORD *)a2 + 104) = 0;
  a2[210] = 0;
  KeInitializeEvent((PRKEVENT)(a2 + 212), SynchronizationEvent, 0);
  KeInitializeTimer((PKTIMER)(a2 + 238));
  KeInitializeDpc((PRKDPC)(a2 + 222), FatCleanVolumeDpc, a2);
  v16 = (unsigned __int64)(unsigned int)dword_140017D48 << 7;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, v16, 0x56746146u);
  v18 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v16);
  *((_QWORD *)a2 + 128) = v18;
  for ( i = 0; i < dword_140017D48; ++i )
  {
    v20 = (unsigned __int64)i << 7;
    *(_WORD *)(v20 + *((_QWORD *)a2 + 128)) = 2;
    *(_WORD *)(v20 + *((_QWORD *)a2 + 128) + 2) = 1;
    *(_DWORD *)(v20 + *((_QWORD *)a2 + 128) + 4) = 128;
  }
  v21 = ExAllocatePoolWithTag((POOL_TYPE)1552, 0x60u, 0x76746146u);
  v22 = v21;
  if ( !ExPoolZeroingNativelySupported && v21 )
    memset(v21, 0, 0x60u);
  *((_QWORD *)a2 + 141) = v22;
  *((_QWORD *)a2 + 143) = a2 + 284;
  *((_QWORD *)a2 + 142) = a2 + 284;
  *((_QWORD *)a2 + 145) = a2 + 288;
  *((_QWORD *)a2 + 144) = a2 + 288;
  a2[292] = 1;
  *((_QWORD *)a2 + 147) = 0;
  a2[296] = 0;
  KeInitializeEvent((PRKEVENT)(a2 + 298), SynchronizationEvent, 0);
  *((_BYTE *)a2 + 4) |= 0x40u;
  *((_BYTE *)a2 + 6) |= 2u;
  *((_BYTE *)a2 + 7) = *((_BYTE *)a2 + 7) & 0xF | 0x50;
  *((_QWORD *)a2 + 8) = a2 + 14;
  *((_QWORD *)a2 + 7) = a2 + 14;
  if ( a2 != (_DWORD *)-1168LL )
    *((_QWORD *)a2 + 6) = a2 + 292;
  *((_QWORD *)a2 + 9) = 0;
  *((_QWORD *)a2 + 10) = 0;
  *((_QWORD *)a2 + 11) = 0;
  *((_QWORD *)a2 + 12) = 0;
  a2[26] = 0;
  *((_QWORD *)a2 + 14) = 0;
  result = FatInitializePerVolumeTelemetry(a2);
  *(_QWORD *)(a1 + 56) = a2;
  return result;
}

```

## disassembly

```asm
0x140048848  mov     r11, rsp
0x14004884b  push    rbx
0x14004884c  push    rsi
0x14004884d  push    rdi
0x14004884e  push    r12
0x140048850  push    r13
0x140048852  push    r14
0x140048854  push    r15
0x140048856  sub     rsp, 0E0h
0x14004885d  mov     rax, cs:__security_cookie
0x140048864  xor     rax, rsp
0x140048867  mov     [rsp+118h+var_48], rax
0x14004886f  mov     r14, r9
0x140048872  mov     r15, r8
0x140048875  mov     rdi, rdx
0x140048878  mov     r13, rcx
0x14004887b  mov     [rsp+118h+var_78], rcx
0x140048883  mov     [rsp+118h+var_B0], rdx
0x140048888  xorps   xmm0, xmm0
0x14004888b  xor     eax, eax
0x14004888d  movups  xmmword ptr [r11-60h], xmm0
0x140048892  mov     [r11-50h], rax
0x140048896  xor     r12d, r12d
0x140048899  mov     [rsp+118h+var_C0], r12
0x14004889e  mov     [r11-70h], rax
0x1400488a2  mov     [r11-68h], eax
0x1400488a6  mov     [r11-88h], r12
0x1400488ad  mov     [r11-98h], r12
0x1400488b4  mov     [r11-90h], r12
0x1400488bb  mov     [rsp+118h+var_A0], r12
0x1400488c0  mov     [rsp+118h+var_A8], r12
0x1400488c5  mov     [rsp+118h+var_C7], r12b
0x1400488ca  mov     [r11-80h], r12
0x1400488ce  mov     [rsp+118h+var_C6], r12b
0x1400488d3  mov     [rsp+118h+var_C8], r12b
0x1400488d8  xor     edx, edx; Val
0x1400488da  mov     r8d, 548h; Size
0x1400488e0  mov     rcx, rdi; void *
0x1400488e3  call    memset
0x1400488e8  mov     dword ptr [rdi], 5480501h
0x1400488ee  lea     rcx, [rdi+408h]; Cache
0x1400488f5  call    cs:__imp_FsRtlInitializeTunnelCache
0x1400488fc  nop     dword ptr [rax+rax+00h]
0x140048901  mov     edx, [r13+44h]
0x140048905  shr     edx, 1
0x140048907  and     dl, 1; Wait
0x14004890a  lea     rcx, Resource; Resource
0x140048911  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140048918  nop     dword ptr [rax+rax+00h]
0x14004891d  mov     rax, cs:qword_140017CB8
0x140048924  lea     rcx, qword_140017CB0
0x14004892b  cmp     [rax], rcx
0x14004892e  jz      short loc_140048937
0x140048930  lea     ecx, [r12+3]
0x140048935  int     29h; Win8: RtlFailFast(ecx)
0x140048937  lea     rbx, [rdi+78h]
0x14004893b  mov     [rbx], rcx
0x14004893e  mov     [rbx+8], rax
0x140048942  mov     [rax], rbx
0x140048945  mov     cs:qword_140017CB8, rbx
0x14004894c  lea     rcx, Resource; Resource
0x140048953  call    cs:__imp_ExReleaseResourceLite
0x14004895a  nop     dword ptr [rax+rax+00h]
0x14004895f  mov     [rsp+118h+var_88], rbx
0x140048967  mov     rcx, r15; Object
0x14004896a  call    cs:__imp_ObfReferenceObject
0x140048971  nop     dword ptr [rax+rax+00h]
0x140048976  mov     [rdi+88h], r15
0x14004897d  mov     [rdi+0C0h], r14
0x140048984  mov     rax, [r14+10h]
0x140048988  mov     [rdi+300h], rax
0x14004898f  mov     [rsp+118h+var_D0], r12
0x140048994  mov     [rsp+118h+var_E8], 8
0x14004899c  lea     rax, [rsp+118h+var_C0]
0x1400489a1  mov     [rsp+118h+var_F0], rax
0x1400489a6  mov     r8, r15
0x1400489a9  mov     edx, 2D0C14h
0x1400489ae  call    FatPerformDevIoCtrl
0x1400489b3  mov     esi, 2
0x1400489b8  test    eax, eax
0x1400489ba  js      short loc_140048A35
0x1400489bc  cmp     byte ptr [rsp+118h+var_C0+4], r12b
0x1400489c1  jz      short loc_1400489CA
0x1400489c3  lock or [rdi+0C8h], esi
0x1400489ca  mov     al, byte ptr [rsp+118h+var_C0+5]
0x1400489ce  test    al, al
0x1400489d0  jnz     short loc_1400489DA
0x1400489d2  mov     cl, byte ptr [rsp+118h+var_C0+6]
0x1400489d6  test    cl, cl
0x1400489d8  jz      short loc_1400489ED
0x1400489da  lock or dword ptr [rdi+0C8h], 200000h
0x1400489e5  mov     cl, byte ptr [rsp+118h+var_C0+6]
0x1400489e9  mov     al, byte ptr [rsp+118h+var_C0+5]
0x1400489ed  cmp     byte ptr [rsp+118h+var_C0+7], r12b
0x1400489f2  jnz     short loc_140048A35
0x1400489f4  test    al, al
0x1400489f6  jnz     short loc_140048A2A
0x1400489f8  test    cl, cl
0x1400489fa  jnz     short loc_140048A2A
0x1400489fc  cmp     byte ptr [rsp+118h+var_C0+4], r12b
0x140048a01  jz      short loc_140048A35
0x140048a03  mov     r8b, 1
0x140048a06  mov     rdx, rdi
0x140048a09  call    FatToggleMediaEjectDisable
0x140048a0e  test    eax, eax
0x140048a10  jns     short loc_140048A1D
0x140048a12  lock or dword ptr [rdi+0C8h], 1000h
0x140048a1d  xor     r8d, r8d
0x140048a20  mov     rdx, rdi
0x140048a23  call    FatToggleMediaEjectDisable
0x140048a28  jmp     short loc_140048A35
0x140048a2a  lock or dword ptr [rdi+0C8h], 1000h
0x140048a35  mov     rax, [r14+10h]
0x140048a39  mov     ecx, [rax+34h]
0x140048a3c  test    cl, 1
0x140048a3f  jz      short loc_140048A48
0x140048a41  lock or [rdi+0C8h], esi
0x140048a48  mov     rax, [r14+10h]
0x140048a4c  mov     ecx, [rax+34h]
0x140048a4f  test    cl, 4
0x140048a52  jz      short loc_140048A5F
0x140048a54  lock or dword ptr [rdi+0C8h], 1000h
0x140048a5f  mov     [rsp+118h+var_D0], r12
0x140048a64  mov     [rsp+118h+var_E8], 0Ch
0x140048a6c  lea     rax, [rsp+118h+var_70]
0x140048a74  mov     [rsp+118h+var_F0], rax
0x140048a79  mov     r8, r15
0x140048a7c  mov     edx, 2D1080h
0x140048a81  call    FatPerformDevIoCtrl
0x140048a86  or      ecx, 0FFFFFFFFh
0x140048a89  test    eax, eax
0x140048a8b  cmovns  ecx, [rsp+118h+var_6C]
0x140048a93  mov     [rdi+464h], ecx
0x140048a99  mov     r15d, 1
0x140048a9f  mov     [rdi+0CCh], r15d
0x140048aa6  lea     rbx, [rdi+208h]
0x140048aad  mov     rcx, rbx; Resource
0x140048ab0  call    cs:__imp_ExInitializeResourceLite
0x140048ab7  nop     dword ptr [rax+rax+00h]
0x140048abc  mov     [rsp+118h+var_98], rbx
0x140048ac4  lea     rbx, [rdi+270h]
0x140048acb  mov     rcx, rbx; Resource
0x140048ace  call    cs:__imp_ExInitializeResourceLite
0x140048ad5  nop     dword ptr [rax+rax+00h]
0x140048ada  mov     [rsp+118h+var_90], rbx
0x140048ae2  mov     [rdi+1D0h], r15d
0x140048ae9  mov     [rdi+1D8h], r12
0x140048af0  mov     [rdi+1E0h], r12d
0x140048af7  lea     rcx, [rdi+1E8h]; Event
0x140048afe  xor     r8d, r8d; State
0x140048b01  mov     edx, r15d; Type
0x140048b04  call    cs:__imp_KeInitializeEvent
0x140048b0b  nop     dword ptr [rax+rax+00h]
0x140048b10  mov     rbx, [rdi+300h]
0x140048b17  call    FatPreallocateCloseContext
0x140048b1c  mov     [rsp+118h+var_C8], r15b
0x140048b21  mov     rdx, rbx; DeviceObject
0x140048b24  xor     ecx, ecx; FileObject
0x140048b26  call    cs:__imp_IoCreateStreamFileObject
0x140048b2d  nop     dword ptr [rax+rax+00h]
0x140048b32  mov     [rsp+118h+var_A0], rax
0x140048b37  mov     [rdi+2D8h], rax
0x140048b3e  xor     r9d, r9d
0x140048b41  mov     r8, rdi
0x140048b44  mov     rcx, rax
0x140048b47  call    FatSetFileObject
0x140048b4c  lock add [rdi+118h], r15d
0x140048b54  lock add [rdi+11Ch], r15d
0x140048b5c  lea     rcx, [rdi+2E0h]
0x140048b63  mov     rax, [rdi+2D8h]
0x140048b6a  mov     [rax+28h], rcx
0x140048b6e  mov     rax, [rdi+2D8h]
0x140048b75  mov     [rax+4Ah], r15b
0x140048b79  mov     rax, [rdi+2D8h]
0x140048b80  mov     [rax+4Bh], r15b
0x140048b84  mov     rax, [rdi+2D8h]
0x140048b8b  mov     [rax+4Ch], r15b
0x140048b8f  lea     rax, [rdi+320h]
0x140048b96  mov     [rax+8], rax
0x140048b9a  mov     [rax], rax
0x140048b9d  lea     rcx, [rdi+330h]; NotifySync
0x140048ba4  call    cs:__imp_FsRtlNotifyInitializeSync
0x140048bab  nop     dword ptr [rax+rax+00h]
0x140048bb0  lea     eax, [r15+3Dh]
0x140048bb4  mov     [rsp+118h+var_58], rax
0x140048bbc  mov     qword ptr [rsp+118h+var_60], rax
0x140048bc4  mov     rax, cs:FatMaxLarge
0x140048bcb  mov     [rsp+118h+var_50], rax
0x140048bd3  mov     [rsp+118h+var_F8], rdi; PVOID
0x140048bd8  lea     r9, qword_140017DB0; int
0x140048bdf  mov     r8b, r15b; int
0x140048be2  lea     rdx, [rsp+118h+var_60]; int
0x140048bea  mov     rcx, [rdi+2D8h]; int
0x140048bf1  call    FatInitializeCacheMap
0x140048bf6  mov     rax, [rdi+2D8h]
0x140048bfd  mov     [rsp+118h+var_A8], rax
0x140048c02  lea     rcx, [rdi+180h]; Mcb
0x140048c09  mov     edx, r15d; PoolType
0x140048c0c  call    cs:__imp_FsRtlInitializeLargeMcb
0x140048c13  nop     dword ptr [rax+rax+00h]
0x140048c18  mov     [rsp+118h+var_C7], r15b
0x140048c1d  lea     rcx, [rdi+1A0h]; Mcb
0x140048c24  mov     edx, r15d; PoolType
0x140048c27  call    cs:__imp_FsRtlInitializeLargeMcb
0x140048c2e  nop     dword ptr [rax+rax+00h]
0x140048c33  mov     [rsp+118h+var_C6], r15b
0x140048c38  mov     [rdi+2F8h], esi
0x140048c3e  mov     [rdi+338h], r15d
0x140048c45  mov     [rdi+340h], r12
0x140048c4c  mov     [rdi+348h], r12d
0x140048c53  lea     rcx, [rdi+350h]; Event
0x140048c5a  xor     r8d, r8d; State
0x140048c5d  mov     edx, r15d; Type
0x140048c60  call    cs:__imp_KeInitializeEvent
0x140048c67  nop     dword ptr [rax+rax+00h]
0x140048c6c  lea     rcx, [rdi+3B8h]; Timer
0x140048c73  call    cs:__imp_KeInitializeTimer
0x140048c7a  nop     dword ptr [rax+rax+00h]
0x140048c7f  lea     rcx, [rdi+378h]; Dpc
0x140048c86  mov     r8, rdi; DeferredContext
0x140048c89  lea     rdx, FatCleanVolumeDpc; DeferredRoutine
0x140048c90  call    cs:__imp_KeInitializeDpc
0x140048c97  nop     dword ptr [rax+rax+00h]
0x140048c9c  mov     r14d, cs:dword_140017D48
0x140048ca3  shl     r14, 7
0x140048ca7  mov     r8d, 56746146h; Tag
0x140048cad  mov     rdx, r14; NumberOfBytes
0x140048cb0  mov     ecx, 610h; PoolType
0x140048cb5  call    cs:__imp_ExAllocatePoolWithTag
0x140048cbc  nop     dword ptr [rax+rax+00h]
0x140048cc1  mov     rbx, rax
0x140048cc4  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140048ccb  jnz     short loc_140048CDF
0x140048ccd  test    rax, rax
0x140048cd0  jz      short loc_140048CDF
0x140048cd2  mov     r8, r14; Size
0x140048cd5  xor     edx, edx; Val
0x140048cd7  mov     rcx, rax; void *
0x140048cda  call    memset
0x140048cdf  mov     [rdi+400h], rbx
0x140048ce6  mov     [rsp+118h+var_80], rbx
0x140048cee  mov     edx, r12d
0x140048cf1  mov     [rsp+118h+var_B8], edx
0x140048cf5  cmp     edx, cs:dword_140017D48
0x140048cfb  jnb     short loc_140048D2F
0x140048cfd  mov     ecx, edx
0x140048cff  shl     rcx, 7
0x140048d03  mov     rax, [rdi+400h]
0x140048d0a  mov     [rcx+rax], si
0x140048d0e  mov     rax, [rdi+400h]
0x140048d15  mov     [rcx+rax+2], r15w
0x140048d1b  mov     rax, [rdi+400h]
0x140048d22  mov     dword ptr [rcx+rax+4], 80h
0x140048d2a  add     edx, r15d
0x140048d2d  jmp     short loc_140048CF1
0x140048d2f  mov     r8d, 76746146h; Tag
0x140048d35  mov     r14d, 60h ; '`'
0x140048d3b  mov     edx, r14d; NumberOfBytes
0x140048d3e  mov     ecx, 610h; PoolType
0x140048d43  call    cs:__imp_ExAllocatePoolWithTag
0x140048d4a  nop     dword ptr [rax+rax+00h]
0x140048d4f  mov     rbx, rax
0x140048d52  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140048d59  jnz     short loc_140048D6D
0x140048d5b  test    rax, rax
0x140048d5e  jz      short loc_140048D6D
0x140048d60  mov     r8d, r14d; Size
0x140048d63  xor     edx, edx; Val
0x140048d65  mov     rcx, rax; void *
0x140048d68  call    memset
0x140048d6d  mov     [rdi+468h], rbx
0x140048d74  lea     rax, [rdi+470h]
0x140048d7b  mov     [rax+8], rax
0x140048d7f  mov     [rax], rax
0x140048d82  lea     rax, [rdi+480h]
0x140048d89  mov     [rax+8], rax
0x140048d8d  mov     [rax], rax
0x140048d90  lea     rbx, [rdi+490h]
0x140048d97  mov     [rbx], r15d
0x140048d9a  mov     [rbx+8], r12
0x140048d9e  mov     [rbx+10h], r12d
0x140048da2  lea     rcx, [rbx+18h]; Event
0x140048da6  xor     r8d, r8d; State
0x140048da9  mov     edx, r15d; Type
0x140048dac  call    cs:__imp_KeInitializeEvent
0x140048db3  nop     dword ptr [rax+rax+00h]
0x140048db8  or      byte ptr [rdi+4], 40h
0x140048dbc  or      [rdi+6], sil
0x140048dc0  mov     al, [rdi+7]
0x140048dc3  and     al, 0Fh
0x140048dc5  or      al, 50h
0x140048dc7  mov     [rdi+7], al
0x140048dca  lea     rax, [rdi+38h]
0x140048dce  mov     [rax+8], rax
0x140048dd2  mov     [rax], rax
0x140048dd5  test    rbx, rbx
0x140048dd8  jz      short loc_140048DDE
0x140048dda  mov     [rdi+30h], rbx
0x140048dde  mov     [rdi+48h], r12
0x140048de2  mov     [rdi+50h], r12
  ... truncated ...
```
