# FveInit

- ea: `0x140061eb0`
- end: `0x14006249c`
- name: `FveInit`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14006f9a0`

## callees

- `0x140008e44`
- `0x14000b3ac`
- `0x14000b62c`
- `0x140021d00`
- `0x14002d8e8`
- `0x140030690`
- `0x140061eb0`
- `0x1400643ec`
- `0x14007b054`
- `0x140094020`
- `0x1400b5bc0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140062117`
- `ntoskrnl!KeInitializeEvent` at `0x140062117`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006203f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062060`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006208d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400620a8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400620de`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062246`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400623cc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062402`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006203f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062060`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006208d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400620a8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400620de`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062246`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400623cc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140062402`
- `ntoskrnl!KeInitializeMutex` at `0x1400620bd`
- `ntoskrnl!KeInitializeMutex` at `0x1400620bd`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14006226b`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14006226b`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400622e4`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400622e4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400623b5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400623b5`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14006243d`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14006243d`
- `ntoskrnl!ExAllocatePool2` at `0x140062312`
- `ntoskrnl!ExAllocatePool2` at `0x140062377`
- `ntoskrnl!ExAllocatePool2` at `0x140062312`
- `ntoskrnl!ExAllocatePool2` at `0x140062377`

## pseudocode

```c
__int64 __fastcall FveInit(__int64 a1, char a2)
{
  __int64 v2; // rbp
  __int64 i; // rcx
  __int64 v6; // rax
  int v7; // esi
  int v8; // eax
  __int64 v9; // r8
  ULONG MaximumProcessorCount; // eax
  void *Pool2; // rax
  __int64 v12; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v13; // rcx
  _QWORD *v14; // rax
  __int64 SecurityDescriptor_low; // [rsp+90h] [rbp+8h]

  v2 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 1040) = 0;
  *(_BYTE *)(a1 + 4808) = 0;
  *(_QWORD *)(a1 + 844) = 0;
  *(_QWORD *)(a1 + 1016) = 0;
  *(_QWORD *)(a1 + 1008) = 0;
  *(_QWORD *)(a1 + 1308) = 0;
  *(_DWORD *)(a1 + 1320) = 0;
  *(_QWORD *)(a1 + 1048) = 0;
  *(_QWORD *)(a1 + 852) = 0;
  *(_QWORD *)(a1 + 860) = 0;
  *(_DWORD *)(a1 + 868) = 0;
  *(_QWORD *)(a1 + 872) = 0;
  *(_DWORD *)(a1 + 880) = 0;
  *(_QWORD *)(a1 + 888) = 0;
  *(_DWORD *)(a1 + 896) = 0;
  *(_QWORD *)(a1 + 960) = 0;
  *(_DWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 1352) = 0;
  *(_BYTE *)(a1 + 1364) = 0;
  *(_QWORD *)(a1 + 4792) = 0;
  *(_DWORD *)(a1 + 4800) = 0;
  *(_QWORD *)(a1 + 836) = 1;
  *(_DWORD *)(a1 + 1316) = -1;
  *(_DWORD *)(a1 + 808) = 0x8000;
  *(_DWORD *)(a1 + 16) = -1;
  *(_DWORD *)(a1 + 1360) = 3;
  *(_DWORD *)(a1 + 4804) = -1073741802;
  for ( i = 0; i != 3; ++i )
  {
    v6 = 3 * i;
    *(_OWORD *)(a1 + 8 * v6 + 1056) = 0;
    *(_QWORD *)(a1 + 8 * v6 + 1072) = 0;
    *(_QWORD *)(a1 + 8 * i + 1128) = 0;
  }
  *(_QWORD *)(a1 + 1168) = 0;
  *(_QWORD *)(a1 + 1176) = 0;
  *(_QWORD *)(a1 + 1192) = 0;
  *(_DWORD *)(a1 + 1200) = 0;
  *(_QWORD *)(a1 + 4720) = 0;
  *(_QWORD *)(a1 + 4728) = 0;
  *(_QWORD *)(a1 + 4736) = 0;
  *(_QWORD *)(a1 + 4768) = a1 + 4760;
  *(_QWORD *)(a1 + 4760) = a1 + 4760;
  *(_QWORD *)(a1 + 2344) = 0;
  FveLockInitialize(a1 + 1504);
  *(_QWORD *)(a1 + 1392) = 0;
  *(_DWORD *)(a1 + 1492) = 0;
  *(_QWORD *)(a1 + 1032) = 0;
  *(_QWORD *)(a1 + 1024) = 0;
  *(_QWORD *)(a1 + 2248) = a1 + 2240;
  *(_QWORD *)(a1 + 2240) = a1 + 2240;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 2256));
  *(_QWORD *)(a1 + 2272) = a1 + 2264;
  *(_QWORD *)(a1 + 2264) = a1 + 2264;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 2280));
  *(_QWORD *)(a1 + 2232) = a1 + 2224;
  *(_QWORD *)(a1 + 2224) = a1 + 2224;
  *(_QWORD *)(a1 + 760) = FveGetSystemUpTime();
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 128));
  FveWrqInitialize(a1);
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 496));
  KeInitializeMutex((PRKMUTEX)(a1 + 504), 0);
  *(_QWORD *)(a1 + 568) = a1 + 560;
  *(_QWORD *)(a1 + 560) = a1 + 560;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 576));
  *(_QWORD *)(a1 + 592) = 0;
  *(_BYTE *)(a1 + 600) = 0;
  *(_QWORD *)(a1 + 584) = 0;
  *(_DWORD *)(a1 + 604) = 4;
  KeInitializeEvent((PRKEVENT)(a1 + 608), SynchronizationEvent, 1u);
  memset((void *)(a1 + 144), 0, 0x58u);
  memset((void *)(a1 + 232), 0, 0x58u);
  memset((void *)(a1 + 320), 0, 0x58u);
  memset((void *)(a1 + 408), 0, 0x58u);
  v7 = FveFrRangeListInitializeEx(
         (POOL_TYPE)512,
         0x30455646u,
         (char *)(a1 + 144),
         (*(_DWORD *)(v2 + 9676) & 0x20000000) != 0);
  if ( v7 >= 0 )
  {
    v7 = FveFrRangeListInitializeEx(
           (POOL_TYPE)512,
           0x30455646u,
           (char *)(a1 + 232),
           (*(_DWORD *)(v2 + 9676) & 0x20000000) != 0);
    if ( v7 >= 0 )
    {
      v7 = FveFrRangeListInitializeEx(
             (POOL_TYPE)512,
             0x30455646u,
             (char *)(a1 + 320),
             (*(_DWORD *)(v2 + 9676) & 0x20000000) != 0);
      if ( v7 >= 0 )
      {
        v7 = FveFrRangeListInitializeEx(
               (POOL_TYPE)512,
               0x30455646u,
               (char *)(a1 + 408),
               (*(_DWORD *)(v2 + 9676) & 0x20000000) != 0);
        if ( v7 >= 0 )
        {
          *(_QWORD *)(a1 + 4536) = 0;
          *(_DWORD *)(a1 + 4544) = 0;
          *(_DWORD *)(a1 + 4548) = 16;
          *(_QWORD *)(a1 + 4528) = a1 + 4520;
          *(_QWORD *)(a1 + 4520) = a1 + 4520;
          KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 4536));
          v8 = FvePerfDevInit(a1);
          LOBYTE(v9) = 1;
          v7 = v8;
          FveTestDevStateChange(a1, 1, v9);
          if ( MmIsThisAnNtAsSystem() )
          {
            SecurityDescriptor_low = LODWORD(WPP_MAIN_CB.SecurityDescriptor);
            if ( ((__int64)WPP_MAIN_CB.SecurityDescriptor & 0x10) == 0 )
            {
              LODWORD(SecurityDescriptor_low) = LODWORD(WPP_MAIN_CB.SecurityDescriptor) | 1;
              wil_details_FeatureReporting_ReportUsageToService(
                &wil_details_featureDescriptors_a,
                SecurityDescriptor_low,
                3);
              wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                SecurityDescriptor_low,
                3,
                &wil_details_featureDescriptors_a);
            }
            MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
          }
          else
          {
            MaximumProcessorCount = 1;
          }
          *(_DWORD *)(a1 + 2328) = MaximumProcessorCount;
          Pool2 = (void *)ExAllocatePool2(64, 296LL * MaximumProcessorCount, 809850438);
          *(_QWORD *)(a1 + 2336) = Pool2;
          if ( Pool2 )
          {
            memset(Pool2, 0, 296LL * *(unsigned int *)(a1 + 2328));
            *(_QWORD *)(*(_QWORD *)(a1 + 2336) + 8LL) = 0;
            if ( (*(_DWORD *)(v2 + 9676) & 8) != 0 )
            {
              v12 = *(_QWORD *)(a1 + 2336);
              *(_QWORD *)(v12 + 8) = ExAllocatePool2(64, 128, 809850438);
              v13 = *(struct _NPAGED_LOOKASIDE_LIST **)(*(_QWORD *)(a1 + 2336) + 8LL);
              if ( v13 )
                ExInitializeNPagedLookasideList(v13, 0, 0, 0x200u, 0x20u, 0x30455646u, 0);
            }
            KeInitializeSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 2336) + 16LL));
            v14 = (_QWORD *)(*(_QWORD *)(a1 + 2336) + 24LL);
            v14[1] = v14;
            *v14 = v14;
            memset((void *)(a1 + 4416), 0, 0x40u);
            KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 4456));
            if ( a2 )
            {
              if ( v7 >= 0 )
              {
                v7 = ExSubscribeWnfStateChange(a1 + 4448, &WNF_FVE_WIM_HASH_GENERATION_COMPLETION, 1);
                if ( v7 < 0
                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    11,
                    WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
                    (unsigned int)v7);
                }
              }
            }
          }
          else
          {
            return (unsigned int)-1073741670;
          }
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140061eb0  push    rbx
0x140061eb2  push    rbp
0x140061eb3  push    rsi
0x140061eb4  push    rdi
0x140061eb5  push    r12
0x140061eb7  push    r13
0x140061eb9  push    r14
0x140061ebb  push    r15
0x140061ebd  sub     rsp, 48h
0x140061ec1  mov     rbp, [rcx+8]
0x140061ec5  xor     ebx, ebx
0x140061ec7  mov     [rcx+410h], rbx
0x140061ece  mov     rdi, rcx
0x140061ed1  mov     [rcx+12C8h], bl
0x140061ed7  mov     r14b, dl
0x140061eda  mov     [rcx+34Ch], rbx
0x140061ee1  mov     [rcx+3F8h], rbx
0x140061ee8  mov     [rcx+3F0h], rbx
0x140061eef  mov     [rcx+51Ch], rbx
0x140061ef6  mov     [rcx+528h], ebx
0x140061efc  mov     [rcx+418h], rbx
0x140061f03  mov     [rcx+354h], rbx
0x140061f0a  mov     [rcx+35Ch], rbx
0x140061f11  mov     [rcx+364h], ebx
0x140061f17  mov     [rcx+368h], rbx
0x140061f1e  mov     [rcx+370h], ebx
0x140061f24  mov     [rcx+378h], rbx
0x140061f2b  mov     [rcx+380h], ebx
0x140061f31  mov     [rcx+3C0h], rbx
0x140061f38  mov     [rcx+88h], ebx
0x140061f3e  mov     [rcx+548h], rbx
0x140061f45  mov     [rcx+554h], bl
0x140061f4b  mov     [rcx+12B8h], rbx
0x140061f52  mov     [rcx+12C0h], ebx
0x140061f58  mov     qword ptr [rcx+344h], 1
0x140061f63  mov     dword ptr [rcx+524h], 0FFFFFFFFh
0x140061f6d  mov     dword ptr [rcx+328h], 8000h
0x140061f77  mov     dword ptr [rcx+10h], 0FFFFFFFFh
0x140061f7e  mov     dword ptr [rcx+550h], 3
0x140061f88  mov     dword ptr [rcx+12C4h], 0C0000016h
0x140061f92  mov     ecx, ebx
0x140061f94  lea     rax, [rcx+rcx*2]
0x140061f98  xor     edx, edx
0x140061f9a  xorps   xmm0, xmm0
0x140061f9d  movups  xmmword ptr [rdi+rax*8+420h], xmm0
0x140061fa5  mov     [rdi+rax*8+430h], rdx
0x140061fad  mov     [rdi+rcx*8+468h], rbx
0x140061fb5  inc     rcx
0x140061fb8  cmp     rcx, 3
0x140061fbc  jnz     short loc_140061F94
0x140061fbe  lea     rax, [rdi+1298h]
0x140061fc5  mov     [rdi+490h], rbx
0x140061fcc  mov     [rdi+498h], rbx
0x140061fd3  lea     rcx, [rdi+5E0h]
0x140061fda  mov     [rdi+4A8h], rbx
0x140061fe1  mov     [rdi+4B0h], ebx
0x140061fe7  mov     [rdi+1270h], rbx
0x140061fee  mov     [rdi+1278h], rbx
0x140061ff5  mov     [rdi+1280h], rbx
0x140061ffc  mov     [rax+8], rax
0x140062000  mov     [rax], rax
0x140062003  mov     [rdi+928h], rbx
0x14006200a  call    FveLockInitialize
0x14006200f  lea     rax, [rdi+8C0h]
0x140062016  mov     [rdi+570h], rbx
0x14006201d  mov     [rdi+5D4h], ebx
0x140062023  lea     rcx, [rdi+8D0h]; SpinLock
0x14006202a  mov     [rdi+408h], rbx
0x140062031  mov     [rdi+400h], rbx
0x140062038  mov     [rax+8], rax
0x14006203c  mov     [rax], rax
0x14006203f  call    cs:__imp_KeInitializeSpinLock
0x140062046  nop     dword ptr [rax+rax+00h]
0x14006204b  lea     rax, [rdi+8D8h]
0x140062052  lea     rcx, [rdi+8E8h]; SpinLock
0x140062059  mov     [rax+8], rax
0x14006205d  mov     [rax], rax
0x140062060  call    cs:__imp_KeInitializeSpinLock
0x140062067  nop     dword ptr [rax+rax+00h]
0x14006206c  lea     rax, [rdi+8B0h]
0x140062073  mov     [rax+8], rax
0x140062077  mov     [rax], rax
0x14006207a  call    FveGetSystemUpTime
0x14006207f  lea     rcx, [rdi+80h]; SpinLock
0x140062086  mov     [rdi+2F8h], rax
0x14006208d  call    cs:__imp_KeInitializeSpinLock
0x140062094  nop     dword ptr [rax+rax+00h]
0x140062099  mov     rcx, rdi
0x14006209c  call    FveWrqInitialize
0x1400620a1  lea     rcx, [rdi+1F0h]; SpinLock
0x1400620a8  call    cs:__imp_KeInitializeSpinLock
0x1400620af  nop     dword ptr [rax+rax+00h]
0x1400620b4  lea     rcx, [rdi+1F8h]; Mutex
0x1400620bb  xor     edx, edx; Level
0x1400620bd  call    cs:__imp_KeInitializeMutex
0x1400620c4  nop     dword ptr [rax+rax+00h]
0x1400620c9  lea     rax, [rdi+230h]
0x1400620d0  lea     rcx, [rdi+240h]; SpinLock
0x1400620d7  mov     [rax+8], rax
0x1400620db  mov     [rax], rax
0x1400620de  call    cs:__imp_KeInitializeSpinLock
0x1400620e5  nop     dword ptr [rax+rax+00h]
0x1400620ea  lea     rcx, [rdi+260h]; Event
0x1400620f1  mov     [rdi+250h], rbx
0x1400620f8  mov     r8b, 1; State
0x1400620fb  mov     [rdi+258h], bl
0x140062101  mov     edx, 1; Type
0x140062106  mov     [rdi+248h], rbx
0x14006210d  mov     dword ptr [rdi+25Ch], 4
0x140062117  call    cs:__imp_KeInitializeEvent
0x14006211e  nop     dword ptr [rax+rax+00h]
0x140062123  lea     rbx, [rdi+90h]
0x14006212a  mov     esi, 58h ; 'X'
0x14006212f  mov     r8d, esi; Size
0x140062132  mov     rcx, rbx; void *
0x140062135  xor     edx, edx; Val
0x140062137  call    memset
0x14006213c  lea     r15, [rdi+0E8h]
0x140062143  mov     r8d, esi; Size
0x140062146  mov     rcx, r15; void *
0x140062149  xor     edx, edx; Val
0x14006214b  call    memset
0x140062150  lea     r12, [rdi+140h]
0x140062157  mov     r8d, esi; Size
0x14006215a  mov     rcx, r12; void *
0x14006215d  xor     edx, edx; Val
0x14006215f  call    memset
0x140062164  lea     r13, [rdi+198h]
0x14006216b  mov     r8d, esi; Size
0x14006216e  mov     rcx, r13; void *
0x140062171  xor     edx, edx; Val
0x140062173  call    memset
0x140062178  mov     r9d, [rbp+25CCh]
0x14006217f  mov     r8, rbx; void *
0x140062182  shr     r9d, 1Dh
0x140062186  mov     ebx, 30455646h
0x14006218b  and     r9b, 1
0x14006218f  mov     edx, ebx; Tag
0x140062191  mov     ecx, 200h; PoolType
0x140062196  call    FveFrRangeListInitializeEx
0x14006219b  mov     esi, eax
0x14006219d  test    eax, eax
0x14006219f  js      loc_140062488
0x1400621a5  mov     r9d, [rbp+25CCh]
0x1400621ac  mov     r8, r15; void *
0x1400621af  shr     r9d, 1Dh
0x1400621b3  mov     edx, ebx; Tag
0x1400621b5  and     r9b, 1
0x1400621b9  mov     ecx, 200h; PoolType
0x1400621be  call    FveFrRangeListInitializeEx
0x1400621c3  xor     r15d, r15d
0x1400621c6  mov     esi, eax
0x1400621c8  test    eax, eax
0x1400621ca  js      loc_140062488
0x1400621d0  mov     r9d, [rbp+25CCh]
0x1400621d7  mov     r8, r12; void *
0x1400621da  shr     r9d, 1Dh
0x1400621de  mov     r12d, 200h
0x1400621e4  and     r9b, 1
0x1400621e8  mov     edx, ebx; Tag
0x1400621ea  mov     ecx, r12d; PoolType
0x1400621ed  call    FveFrRangeListInitializeEx
0x1400621f2  mov     esi, eax
0x1400621f4  test    eax, eax
0x1400621f6  js      loc_140062488
0x1400621fc  mov     r9d, [rbp+25CCh]
0x140062203  mov     r8, r13; void *
0x140062206  shr     r9d, 1Dh
0x14006220a  mov     edx, ebx; Tag
0x14006220c  and     r9b, 1
0x140062210  mov     ecx, r12d; PoolType
0x140062213  call    FveFrRangeListInitializeEx
0x140062218  mov     esi, eax
0x14006221a  test    eax, eax
0x14006221c  js      loc_140062488
0x140062222  lea     rcx, [rdi+11A8h]
0x140062229  mov     [rdi+11B8h], r15
0x140062230  mov     [rcx+18h], r15d
0x140062234  mov     dword ptr [rcx+1Ch], 10h
0x14006223b  mov     [rcx+8], rcx
0x14006223f  mov     [rcx], rcx
0x140062242  add     rcx, 10h; SpinLock
0x140062246  call    cs:__imp_KeInitializeSpinLock
0x14006224d  nop     dword ptr [rax+rax+00h]
0x140062252  mov     rcx, rdi
0x140062255  call    FvePerfDevInit
0x14006225a  mov     r8b, 1
0x14006225d  lea     edx, [r15+1]
0x140062261  mov     rcx, rdi
0x140062264  mov     esi, eax
0x140062266  call    FveTestDevStateChange
0x14006226b  call    cs:__imp_MmIsThisAnNtAsSystem
0x140062272  nop     dword ptr [rax+rax+00h]
0x140062277  test    al, al
0x140062279  jz      short loc_1400622F2
0x14006227b  mov     ecx, dword ptr cs:WPP_MAIN_CB.SecurityDescriptor
0x140062281  mov     [rsp+88h+arg_0], r15
0x140062289  mov     dword ptr [rsp+88h+arg_0], ecx
0x140062290  test    cl, 10h
0x140062293  jnz     short loc_1400622DF
0x140062295  mov     rax, [rsp+88h+arg_0]
0x14006229d  lea     r8d, [r15+3]
0x1400622a1  or      ecx, 1
0x1400622a4  mov     [rsp+88h+arg_0], rax
0x1400622ac  mov     dword ptr [rsp+88h+arg_0], ecx
0x1400622b3  lea     rcx, wil_details_featureDescriptors_a
0x1400622ba  mov     rdx, [rsp+88h+arg_0]
0x1400622c2  call    wil_details_FeatureReporting_ReportUsageToService
0x1400622c7  mov     rcx, [rsp+88h+arg_0]
0x1400622cf  lea     r8, wil_details_featureDescriptors_a
0x1400622d6  lea     edx, [r15+3]
0x1400622da  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400622df  mov     ecx, 0FFFFh; GroupNumber
0x1400622e4  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400622eb  nop     dword ptr [rax+rax+00h]
0x1400622f0  jmp     short loc_1400622F7
0x1400622f2  mov     eax, 1
0x1400622f7  mov     [rdi+918h], eax
0x1400622fd  mov     r12d, 40h ; '@'
0x140062303  mov     eax, eax
0x140062305  mov     r8d, ebx
0x140062308  imul    rdx, rax, 128h
0x14006230f  mov     ecx, r12d
0x140062312  call    cs:__imp_ExAllocatePool2
0x140062319  nop     dword ptr [rax+rax+00h]
0x14006231e  mov     [rdi+920h], rax
0x140062325  mov     rcx, rax; void *
0x140062328  test    rax, rax
0x14006232b  jnz     short loc_140062337
0x14006232d  mov     esi, 0C000009Ah
0x140062332  jmp     loc_140062488
0x140062337  mov     eax, [rdi+918h]
0x14006233d  xor     edx, edx; Val
0x14006233f  imul    r8, rax, 128h; Size
0x140062346  call    memset
0x14006234b  mov     rax, [rdi+920h]
0x140062352  mov     [rax+8], r15
0x140062356  mov     eax, [rbp+25CCh]
0x14006235c  test    al, 8
0x14006235e  jz      short loc_1400623C1
0x140062360  mov     rbx, [rdi+920h]
0x140062367  mov     ebp, 30455646h
0x14006236c  mov     r8d, ebp
0x14006236f  mov     edx, 80h
0x140062374  mov     rcx, r12
0x140062377  call    cs:__imp_ExAllocatePool2
0x14006237e  nop     dword ptr [rax+rax+00h]
0x140062383  mov     [rbx+8], rax
0x140062387  mov     rax, [rdi+920h]
0x14006238e  mov     rcx, [rax+8]; Lookaside
0x140062392  test    rcx, rcx
0x140062395  jz      short loc_1400623C1
0x140062397  mov     [rsp+88h+Depth], r15w; Depth
0x14006239d  mov     r9d, 200h; Flags
0x1400623a3  mov     [rsp+88h+Tag], ebp; Tag
0x1400623a7  xor     r8d, r8d; Free
0x1400623aa  xor     edx, edx; Allocate
0x1400623ac  mov     [rsp+88h+Size], 20h ; ' '; Size
0x1400623b5  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400623bc  nop     dword ptr [rax+rax+00h]
0x1400623c1  mov     rcx, [rdi+920h]
0x1400623c8  add     rcx, 10h; SpinLock
0x1400623cc  call    cs:__imp_KeInitializeSpinLock
0x1400623d3  nop     dword ptr [rax+rax+00h]
0x1400623d8  mov     rax, [rdi+920h]
0x1400623df  lea     rcx, [rdi+1140h]; void *
0x1400623e6  add     rax, 18h
0x1400623ea  mov     r8, r12; Size
0x1400623ed  xor     edx, edx; Val
0x1400623ef  mov     [rax+8], rax
0x1400623f3  mov     [rax], rax
0x1400623f6  call    memset
0x1400623fb  lea     rcx, [rdi+1168h]; SpinLock
0x140062402  call    cs:__imp_KeInitializeSpinLock
0x140062409  nop     dword ptr [rax+rax+00h]
0x14006240e  test    r14b, r14b
0x140062411  jz      short loc_140062488
0x140062413  test    esi, esi
0x140062415  js      short loc_140062488
0x140062417  xor     r9d, r9d
0x14006241a  mov     qword ptr [rsp+88h+Tag], rdi
0x14006241f  lea     rax, FveWnfWimHashingCompletionCallback
0x140062426  lea     rcx, [rdi+1160h]
0x14006242d  mov     [rsp+88h+Size], rax
0x140062432  lea     rdx, WNF_FVE_WIM_HASH_GENERATION_COMPLETION
0x140062439  lea     r8d, [r9+1]
0x14006243d  call    cs:__imp_ExSubscribeWnfStateChange
0x140062444  nop     dword ptr [rax+rax+00h]
0x140062449  mov     esi, eax
0x14006244b  test    eax, eax
0x14006244d  jns     short loc_140062488
0x14006244f  mov     rcx, cs:WPP_GLOBAL_Control
0x140062456  lea     rax, WPP_GLOBAL_Control
0x14006245d  cmp     rcx, rax
0x140062460  jz      short loc_140062488
0x140062462  mov     eax, [rcx+2Ch]
0x140062465  test    r12b, al
0x140062468  jz      short loc_140062488
0x14006246a  cmp     byte ptr [rcx+29h], 2
0x14006246e  jb      short loc_140062488
  ... truncated ...
```
