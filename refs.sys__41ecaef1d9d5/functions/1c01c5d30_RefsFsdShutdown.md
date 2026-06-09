# RefsFsdShutdown

- ea: `0x1c01c5d30`
- end: `0x1c01c5fee`
- name: `RefsFsdShutdown`
- size: `702`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1c000444c`
- `0x1c0005650`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003fd04`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00a7818`
- `0x1c01716fc`
- `0x1c01c5d30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01c5e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01c5f40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01c5e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01c5f40`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c01c5e25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c01c5eb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c01c5e25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c01c5eb0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01c5e07`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01c5e07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01c5d95`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01c5d95`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c01c5dae`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c01c5dae`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c01c5f83`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c01c5f83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01c5f8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01c5f8f`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1c01c5f26`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1c01c5f26`

## pseudocode

```c
__int64 __fastcall RefsFsdShutdown(__int64 a1, __int64 a2)
{
  BOOL v3; // esi
  __int64 v4; // rbx
  __int64 v5; // rax
  PDEVICE_OBJECT v6; // rbx
  __int64 v8; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v9[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h]
  __int128 v11; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v12[42]; // [rsp+70h] [rbp-90h] BYREF

  v10 = 0;
  memset(v9, 0, sizeof(v9));
  memset(v12, 0, sizeof(v12));
  v8 = 0;
  v11 = 0;
  KeEnterCriticalRegion();
  v3 = (int)IoPropagateActivityIdToThread(a2, &v11, &v8) >= 0;
  RefsInitializeLocalIrpContext(a2, v12);
  v4 = RefsInitializeTopLevelIrp(v9, 0, 0);
  v5 = *(_QWORD *)(v4 + 32);
  if ( !v5 )
  {
    *(_DWORD *)(v4 + 4) = 1397140410;
    *(_QWORD *)(v4 + 32) = v12;
    LODWORD(v12[1]) |= 0x100000u;
    IoSetTopLevelIrp((PIRP)v4);
    v5 = *(_QWORD *)(v4 + 32);
  }
  v12[13] = v5;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  dword_1C012E0B0 |= 0x1000u;
  ExReleaseResourceLite(&Resource);
  if ( dword_1C012E6B0 )
  {
    RefsForEachVcb((unsigned int)v12, 0, (unsigned int)RefsShutdownVirtualVolumeWorker, 0, 0);
    RefsForEachVcb((unsigned int)v12, 0, (unsigned int)RefsNotifyVirtualDiskOfShutdownWorker, 0, 0);
  }
  RefsForEachVcb((unsigned int)v12, 0, (unsigned int)RefsShutdownVolumeWorker, 0, 0);
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  qword_1C012E1C0 = 0;
  McGenEventUnregister_EtwUnregister();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_45f333a422213e937638509ea7879785_Traceguids);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( WPPTraceSuite == 4 )
      {
        while ( v6 )
        {
          if ( v6->Vpb )
          {
            ((void (*)(void))pfnEtwUnregister)();
            v6->Vpb = 0;
          }
          v6 = v6->NextDevice;
        }
      }
      else if ( WPPTraceSuite == 2 )
      {
        IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
      }
      WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    }
  }
  ExReleaseResourceLite(&Resource);
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(0);
  RefsExtendedCompleteRequestInternal(v12, a2, 0);
  if ( v3 )
    IoClearActivityIdThread(v8);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x1c01c5d30  mov     [rsp-8+arg_0], rbx
0x1c01c5d35  mov     [rsp-8+arg_10], rsi
0x1c01c5d3a  push    rbp
0x1c01c5d3b  push    rdi
0x1c01c5d3c  push    r12
0x1c01c5d3e  lea     rbp, [rsp-0D0h]
0x1c01c5d46  sub     rsp, 1D0h
0x1c01c5d4d  mov     rax, cs:__security_cookie
0x1c01c5d54  xor     rax, rsp
0x1c01c5d57  mov     [rbp+0E0h+var_20], rax
0x1c01c5d5e  xorps   xmm0, xmm0
0x1c01c5d61  lea     rcx, [rsp+1E0h+var_170]; void *
0x1c01c5d66  mov     rdi, rdx
0x1c01c5d69  xor     eax, eax
0x1c01c5d6b  xor     edx, edx; Val
0x1c01c5d6d  mov     [rsp+1E0h+var_188], rax
0x1c01c5d72  mov     r8d, 150h; Size
0x1c01c5d78  movups  [rsp+1E0h+var_1A8], xmm0
0x1c01c5d7d  movups  [rsp+1E0h+var_198], xmm0
0x1c01c5d82  call    memset
0x1c01c5d87  and     [rsp+1E0h+var_1B0], 0
0x1c01c5d8d  xorps   xmm0, xmm0
0x1c01c5d90  movups  [rsp+1E0h+var_180], xmm0
0x1c01c5d95  call    cs:__imp_KeEnterCriticalRegion
0x1c01c5d9c  nop     dword ptr [rax+rax+00h]
0x1c01c5da1  lea     r8, [rsp+1E0h+var_1B0]
0x1c01c5da6  mov     rcx, rdi
0x1c01c5da9  lea     rdx, [rsp+1E0h+var_180]
0x1c01c5dae  call    cs:__imp_IoPropagateActivityIdToThread
0x1c01c5db5  nop     dword ptr [rax+rax+00h]
0x1c01c5dba  xor     esi, esi
0x1c01c5dbc  lea     rdx, [rsp+1E0h+var_170]
0x1c01c5dc1  test    eax, eax
0x1c01c5dc3  mov     rcx, rdi
0x1c01c5dc6  lea     r12d, [rsi+1]
0x1c01c5dca  cmovns  esi, r12d
0x1c01c5dce  call    RefsInitializeLocalIrpContext
0x1c01c5dd3  xor     r8d, r8d
0x1c01c5dd6  lea     rcx, [rsp+1E0h+var_1A8]
0x1c01c5ddb  xor     edx, edx
0x1c01c5ddd  call    RefsInitializeTopLevelIrp
0x1c01c5de2  mov     rbx, rax
0x1c01c5de5  mov     rax, [rax+20h]
0x1c01c5de9  test    rax, rax
0x1c01c5dec  jnz     short loc_1C01C5E17
0x1c01c5dee  lea     rax, [rsp+1E0h+var_170]
0x1c01c5df3  mov     dword ptr [rbx+4], 5346ABBAh
0x1c01c5dfa  mov     [rbx+20h], rax
0x1c01c5dfe  mov     rcx, rbx; Irp
0x1c01c5e01  bts     [rsp+1E0h+var_168], 14h
0x1c01c5e07  call    cs:__imp_IoSetTopLevelIrp
0x1c01c5e0e  nop     dword ptr [rax+rax+00h]
0x1c01c5e13  mov     rax, [rbx+20h]
0x1c01c5e17  mov     dl, r12b; Wait
0x1c01c5e1a  mov     [rbp+0E0h+var_108], rax
0x1c01c5e1e  lea     rcx, Resource; Resource
0x1c01c5e25  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c01c5e2c  nop     dword ptr [rax+rax+00h]
0x1c01c5e31  bts     cs:dword_1C012E0B0, 0Ch
0x1c01c5e39  lea     rcx, Resource; Resource
0x1c01c5e40  call    cs:__imp_ExReleaseResourceLite
0x1c01c5e47  nop     dword ptr [rax+rax+00h]
0x1c01c5e4c  cmp     cs:dword_1C012E6B0, 0
0x1c01c5e53  jbe     short loc_1C01C5E8B
0x1c01c5e55  xor     r9d, r9d
0x1c01c5e58  mov     [rsp+1E0h+var_1C0], 0
0x1c01c5e5d  lea     r8, RefsShutdownVirtualVolumeWorker
0x1c01c5e64  xor     edx, edx
0x1c01c5e66  lea     rcx, [rsp+1E0h+var_170]
0x1c01c5e6b  call    RefsForEachVcb
0x1c01c5e70  xor     r9d, r9d
0x1c01c5e73  mov     [rsp+1E0h+var_1C0], 0
0x1c01c5e78  lea     r8, RefsNotifyVirtualDiskOfShutdownWorker
0x1c01c5e7f  xor     edx, edx
0x1c01c5e81  lea     rcx, [rsp+1E0h+var_170]
0x1c01c5e86  call    RefsForEachVcb
0x1c01c5e8b  xor     r9d, r9d
0x1c01c5e8e  mov     [rsp+1E0h+var_1C0], 0
0x1c01c5e93  lea     r8, RefsShutdownVolumeWorker
0x1c01c5e9a  xor     edx, edx
0x1c01c5e9c  lea     rcx, [rsp+1E0h+var_170]
0x1c01c5ea1  call    RefsForEachVcb
0x1c01c5ea6  mov     dl, r12b; Wait
0x1c01c5ea9  lea     rcx, Resource; Resource
0x1c01c5eb0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c01c5eb7  nop     dword ptr [rax+rax+00h]
0x1c01c5ebc  and     cs:qword_1C012E1C0, 0
0x1c01c5ec4  call    McGenEventUnregister_EtwUnregister
0x1c01c5ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c5ed0  lea     r12, WPP_GLOBAL_Control
0x1c01c5ed7  cmp     rcx, r12
0x1c01c5eda  jz      short loc_1C01C5F39
0x1c01c5edc  mov     eax, [rcx+2Ch]
0x1c01c5edf  test    al, 2
0x1c01c5ee1  jz      short loc_1C01C5EFE
0x1c01c5ee3  cmp     byte ptr [rcx+29h], 2
0x1c01c5ee7  jb      short loc_1C01C5EFE
0x1c01c5ee9  mov     rcx, [rcx+18h]
0x1c01c5eed  lea     r8, WPP_45f333a422213e937638509ea7879785_Traceguids
0x1c01c5ef4  mov     edx, 0Ah
0x1c01c5ef9  call    WPP_SF_
0x1c01c5efe  mov     rbx, cs:WPP_GLOBAL_Control
0x1c01c5f05  cmp     rbx, r12
0x1c01c5f08  jz      short loc_1C01C5F39
0x1c01c5f0a  mov     eax, cs:WPPTraceSuite
0x1c01c5f10  cmp     eax, 4
0x1c01c5f13  jz      loc_1C01C5FE4
0x1c01c5f19  cmp     eax, 2
0x1c01c5f1c  jnz     short loc_1C01C5F32
0x1c01c5f1e  mov     edx, 80000002h; Action
0x1c01c5f23  mov     rcx, rbx; DeviceObject
0x1c01c5f26  call    cs:__imp_IoWMIRegistrationControl
0x1c01c5f2d  nop     dword ptr [rax+rax+00h]
0x1c01c5f32  mov     cs:WPP_GLOBAL_Control, r12
0x1c01c5f39  lea     rcx, Resource; Resource
0x1c01c5f40  call    cs:__imp_ExReleaseResourceLite
0x1c01c5f47  nop     dword ptr [rax+rax+00h]
0x1c01c5f4c  mov     al, cs:RefsStatusDebugEnabled
0x1c01c5f52  test    al, al
0x1c01c5f54  jz      short loc_1C01C5F6A
0x1c01c5f56  mov     r8d, 0D1h
0x1c01c5f5c  lea     rdx, aShutdownC; "Shutdown.c"
0x1c01c5f63  xor     ecx, ecx; Status
0x1c01c5f65  call    RefsStatusDebug
0x1c01c5f6a  xor     r8d, r8d
0x1c01c5f6d  lea     rcx, [rsp+1E0h+var_170]
0x1c01c5f72  mov     rdx, rdi
0x1c01c5f75  call    RefsExtendedCompleteRequestInternal
0x1c01c5f7a  test    esi, esi
0x1c01c5f7c  jz      short loc_1C01C5F8F
0x1c01c5f7e  mov     rcx, [rsp+1E0h+var_1B0]
0x1c01c5f83  call    cs:__imp_IoClearActivityIdThread
0x1c01c5f8a  nop     dword ptr [rax+rax+00h]
0x1c01c5f8f  call    cs:__imp_KeLeaveCriticalRegion
0x1c01c5f96  nop     dword ptr [rax+rax+00h]
0x1c01c5f9b  xor     eax, eax
0x1c01c5f9d  mov     rcx, [rbp+0E0h+var_20]
0x1c01c5fa4  xor     rcx, rsp; StackCookie
0x1c01c5fa7  call    __security_check_cookie
0x1c01c5fac  lea     r11, [rsp+1E0h+var_10]
0x1c01c5fb4  mov     rbx, [r11+20h]
0x1c01c5fb8  mov     rsi, [r11+30h]
0x1c01c5fbc  mov     rsp, r11
0x1c01c5fbf  pop     r12
0x1c01c5fc1  pop     rdi
0x1c01c5fc2  pop     rbp
0x1c01c5fc3  retn
0x1c01c5fc5  mov     rcx, [rbx+38h]
0x1c01c5fc9  test    rcx, rcx
0x1c01c5fcc  jz      short loc_1C01C5FE0
0x1c01c5fce  mov     rax, cs:pfnEtwUnregister
0x1c01c5fd5  call    cs:__guard_dispatch_icall_fptr
0x1c01c5fdb  and     qword ptr [rbx+38h], 0
0x1c01c5fe0  mov     rbx, [rbx+10h]
0x1c01c5fe4  test    rbx, rbx
0x1c01c5fe7  jnz     short loc_1C01C5FC5
0x1c01c5fe9  jmp     loc_1C01C5F32
```
