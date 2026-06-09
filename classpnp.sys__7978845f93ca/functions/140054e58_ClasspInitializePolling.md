# ClasspInitializePolling

- ea: `0x140054e58`
- end: `0x140055090`
- name: `ClasspInitializePolling`
- size: `568`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140021a00`
- `0x1400543e0`

## callees

- `0x14001fc38`
- `0x14001feac`
- `0x14005479c`
- `0x140054e58`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x140054f51`
- `ntoskrnl!KeInitializeMutex` at `0x140054f51`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14005504d`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14005504d`
- `ntoskrnl!IoFreeIrp` at `0x14005506c`
- `ntoskrnl!IoFreeIrp` at `0x14005506c`
- `ntoskrnl!ExAllocatePool2` at `0x140054e90`
- `ntoskrnl!ExAllocatePool2` at `0x140054eef`
- `ntoskrnl!ExAllocatePool2` at `0x140054e90`
- `ntoskrnl!ExAllocatePool2` at `0x140054eef`
- `ntoskrnl!IoAllocateIrp` at `0x140054ecc`
- `ntoskrnl!IoAllocateIrp` at `0x140054ecc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005507d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005507d`

## pseudocode

```c
__int64 __fastcall ClasspInitializePolling(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, char a2)
{
  _DEVICE_OBJECT *DeviceObject; // rbp
  __int64 Pool2; // rdi
  IRP *Irp; // rsi
  __int64 v7; // rax
  int v8; // eax
  _DEVICE_OBJECT *v9; // rax

  if ( FdoExtension->MediaChangeDetectionInfo )
    return 0;
  DeviceObject = FdoExtension->DeviceObject;
  Pool2 = ExAllocatePool2(64, 328, 1296851795);
  if ( Pool2 )
  {
    *(_QWORD *)&FdoExtension->KernelModeMcnContext.LockCount = 0;
    FdoExtension->KernelModeMcnContext.FileObject = (_FILE_OBJECT *)-1LL;
    FdoExtension->KernelModeMcnContext.DeviceObject = (_DEVICE_OBJECT *)-1LL;
    Irp = IoAllocateIrp(DeviceObject->StackSize + 1, 0);
    if ( Irp )
    {
      v7 = ExAllocatePool2(72, 18, 1296851795);
      if ( v7 )
      {
        *(_QWORD *)(Pool2 + 304) = v7;
        v8 = 0;
        *(_QWORD *)(Pool2 + 112) = Irp;
        *(_WORD *)(Pool2 + 320) = 4608;
        *(_DWORD *)(Pool2 + 64) = 1;
        if ( a2 )
          v8 = 0x100000;
        *(_QWORD *)(Pool2 + 56) = 0;
        *(_DWORD *)(Pool2 + 316) = 0;
        *(_DWORD *)(Pool2 + 312) = v8 | 0x10000108;
        KeInitializeMutex((PRKMUTEX)Pool2, 0x100u);
        v9 = FdoExtension->DeviceObject;
        FdoExtension->MediaChangeDetectionInfo = (_MEDIA_CHANGE_DETECTION_INFO *)Pool2;
        if ( v9->DeviceType == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
          }
          if ( (int)ClasspInitializeGesn(FdoExtension, Pool2) >= 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                55,
                WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
                FdoExtension->DeviceObject);
            }
            goto LABEL_22;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              56,
              WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
              FdoExtension->DeviceObject);
          }
        }
        *(_BYTE *)(Pool2 + 72) = 0;
LABEL_22:
        if ( !WPP_MAIN_CB.Queue.Wcb.DeviceObject )
          PoRegisterPowerSettingCallback(
            DeviceObject,
            &GUID_CONSOLE_DISPLAY_STATE,
            ClasspPowerSettingCallback,
            0,
            &WPP_MAIN_CB.Queue.Wcb.DeviceObject);
        return 0;
      }
      IoFreeIrp(Irp);
    }
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140054e58  push    rbx
0x140054e5a  push    rbp
0x140054e5b  push    rsi
0x140054e5c  push    rdi
0x140054e5d  push    r12
0x140054e5f  push    r14
0x140054e61  sub     rsp, 38h
0x140054e65  cmp     qword ptr [rcx+288h], 0
0x140054e6d  mov     r14b, dl
0x140054e70  mov     rbx, rcx
0x140054e73  jnz     loc_140055059
0x140054e79  mov     rbp, [rcx+8]
0x140054e7d  mov     r12d, 4D4C6353h
0x140054e83  mov     r8d, r12d
0x140054e86  mov     edx, 148h
0x140054e8b  mov     ecx, 40h ; '@'
0x140054e90  call    cs:__imp_ExAllocatePool2
0x140054e97  nop     dword ptr [rax+rax+00h]
0x140054e9c  mov     rdi, rax
0x140054e9f  test    rax, rax
0x140054ea2  jz      loc_140055089
0x140054ea8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140054eac  mov     qword ptr [rbx+2B0h], 0
0x140054eb7  mov     [rbx+2A0h], rax
0x140054ebe  xor     edx, edx; ChargeQuota
0x140054ec0  mov     [rbx+2A8h], rax
0x140054ec7  mov     cl, [rbp+4Ch]
0x140054eca  inc     cl; StackSize
0x140054ecc  call    cs:__imp_IoAllocateIrp
0x140054ed3  nop     dword ptr [rax+rax+00h]
0x140054ed8  mov     rsi, rax
0x140054edb  test    rax, rax
0x140054ede  jz      loc_140055078
0x140054ee4  mov     edx, 12h
0x140054ee9  mov     r8d, r12d
0x140054eec  lea     ecx, [rdx+36h]
0x140054eef  call    cs:__imp_ExAllocatePool2
0x140054ef6  nop     dword ptr [rax+rax+00h]
0x140054efb  test    rax, rax
0x140054efe  jz      loc_140055069
0x140054f04  mov     [rdi+130h], rax
0x140054f0b  mov     ecx, 100000h
0x140054f10  xor     eax, eax
0x140054f12  mov     [rdi+70h], rsi
0x140054f16  test    r14b, r14b
0x140054f19  mov     word ptr [rdi+140h], 1200h
0x140054f22  mov     edx, 100h; Level
0x140054f27  mov     dword ptr [rdi+40h], 1
0x140054f2e  cmovnz  eax, ecx
0x140054f31  mov     qword ptr [rdi+38h], 0
0x140054f39  or      eax, 10000108h
0x140054f3e  mov     dword ptr [rdi+13Ch], 0
0x140054f48  mov     rcx, rdi; Mutex
0x140054f4b  mov     [rdi+138h], eax
0x140054f51  call    cs:__imp_KeInitializeMutex
0x140054f58  nop     dword ptr [rax+rax+00h]
0x140054f5d  mov     rax, [rbx+8]
0x140054f61  mov     [rbx+288h], rdi
0x140054f68  cmp     dword ptr [rax+48h], 2
0x140054f6c  jnz     loc_14005501F
0x140054f72  mov     rcx, cs:WPP_GLOBAL_Control
0x140054f79  lea     r12, WPP_GLOBAL_Control
0x140054f80  mov     sil, 4
0x140054f83  cmp     rcx, r12
0x140054f86  jz      short loc_140054FAA
0x140054f88  bt      dword ptr [rcx+2Ch], 0Ch
0x140054f8d  jnb     short loc_140054FAA
0x140054f8f  cmp     [rcx+29h], sil
0x140054f93  jb      short loc_140054FAA
0x140054f95  mov     rcx, [rcx+18h]
0x140054f99  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054fa0  mov     edx, 36h ; '6'
0x140054fa5  call    WPP_SF_
0x140054faa  mov     rdx, rdi
0x140054fad  mov     rcx, rbx; FdoExtension
0x140054fb0  call    ClasspInitializeGesn
0x140054fb5  test    eax, eax
0x140054fb7  js      short loc_140054FED
0x140054fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140054fc0  cmp     rcx, r12
0x140054fc3  jz      short loc_140055023
0x140054fc5  bt      dword ptr [rcx+2Ch], 0Ch
0x140054fca  jnb     short loc_140055023
0x140054fcc  cmp     [rcx+29h], sil
0x140054fd0  jb      short loc_140055023
0x140054fd2  mov     r9, [rbx+8]
0x140054fd6  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054fdd  mov     rcx, [rcx+18h]
0x140054fe1  mov     edx, 37h ; '7'
0x140054fe6  call    WPP_SF_q
0x140054feb  jmp     short loc_140055023
0x140054fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140054ff4  cmp     rcx, r12
0x140054ff7  jz      short loc_14005501F
0x140054ff9  bt      dword ptr [rcx+2Ch], 0Ch
0x140054ffe  jnb     short loc_14005501F
0x140055000  cmp     [rcx+29h], sil
0x140055004  jb      short loc_14005501F
0x140055006  mov     r9, [rbx+8]
0x14005500a  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140055011  mov     rcx, [rcx+18h]
0x140055015  mov     edx, 38h ; '8'
0x14005501a  call    WPP_SF_q
0x14005501f  mov     byte ptr [rdi+48h], 0
0x140055023  cmp     qword ptr cs:WPP_MAIN_CB.Queue+30h, 0
0x14005502b  jnz     short loc_140055059
0x14005502d  lea     rax, WPP_MAIN_CB.Queue+30h
0x140055034  xor     r9d, r9d; Context
0x140055037  lea     r8, ClasspPowerSettingCallback; Callback
0x14005503e  mov     [rsp+68h+Handle], rax; Handle
0x140055043  lea     rdx, GUID_CONSOLE_DISPLAY_STATE; SettingGuid
0x14005504a  mov     rcx, rbp; DeviceObject
0x14005504d  call    cs:__imp_PoRegisterPowerSettingCallback
0x140055054  nop     dword ptr [rax+rax+00h]
0x140055059  xor     eax, eax
0x14005505b  add     rsp, 38h
0x14005505f  pop     r14
0x140055061  pop     r12
0x140055063  pop     rdi
0x140055064  pop     rsi
0x140055065  pop     rbp
0x140055066  pop     rbx
0x140055067  retn
0x140055069  mov     rcx, rsi; Irp
0x14005506c  call    cs:__imp_IoFreeIrp
0x140055073  nop     dword ptr [rax+rax+00h]
0x140055078  xor     edx, edx; Tag
0x14005507a  mov     rcx, rdi; P
0x14005507d  call    cs:__imp_ExFreePoolWithTag
0x140055084  nop     dword ptr [rax+rax+00h]
0x140055089  mov     eax, 0C000009Ah
0x14005508e  jmp     short loc_14005505B
```
