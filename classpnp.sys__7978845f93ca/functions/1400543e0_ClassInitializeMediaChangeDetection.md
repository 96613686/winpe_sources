# ClassInitializeMediaChangeDetection

- ea: `0x1400543e0`
- end: `0x1400545b1`
- name: `ClassInitializeMediaChangeDetection`
- size: `465`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PUCHAR EventPrefix)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x14001feac`
- `0x140022748`
- `0x140022fe0`
- `0x1400543e0`
- `0x140054e58`
- `0x140055098`
- `0x1400554c0`
- `0x14005f9f0`

## pseudocode

```c
void __stdcall ClassInitializeMediaChangeDetection(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PUCHAR EventPrefix)
{
  PCLASS_DRIVER_EXTENSION DriverExtension; // rax
  struct _UNICODE_STRING *p_RegistryPath; // rbx
  bool v5; // al
  bool v6; // r15
  const char *v7; // r12
  const char *v8; // r9
  char v9; // r15
  const char *v10; // r9
  char v11; // [rsp+50h] [rbp+8h] BYREF

  DriverExtension = ClassGetDriverExtension(FdoExtension->DeviceObject->DriverObject);
  v11 = 0;
  p_RegistryPath = &DriverExtension->RegistryPath;
  if ( ClasspIsMediaChangeDisabledDueToHardwareLimitation((__int64)FdoExtension, &DriverExtension->RegistryPath) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
    }
    return;
  }
  v5 = ClasspIsMediaChangeDisabledForClass((__int64)FdoExtension, p_RegistryPath);
  v6 = v5;
  v7 = "disabled";
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v8 = "disabled";
    if ( !v5 )
      v8 = "enabled";
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v8);
  }
  if ( (int)ClasspMediaChangeDeviceInstanceOverride((__int64)FdoExtension, &v11) >= 0 )
  {
    v9 = v11;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v10 = "Enabling";
      if ( !v11 )
        v10 = "Disabling";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v10);
    }
    v6 = v9 == 0;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
    }
LABEL_24:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      if ( !v6 )
        v7 = "enabled";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v7);
    }
  }
  if ( !v6 )
    ClasspInitializePolling(FdoExtension);
}

```

## disassembly

```asm
0x1400543e0  mov     [rsp+arg_8], rbx
0x1400543e5  mov     [rsp+arg_10], rsi
0x1400543ea  push    rdi
0x1400543eb  push    r12
0x1400543ed  push    r13
0x1400543ef  push    r14
0x1400543f1  push    r15
0x1400543f3  sub     rsp, 20h
0x1400543f7  mov     r14, rcx
0x1400543fa  mov     rcx, [rcx+8]
0x1400543fe  mov     rcx, [rcx+8]; DriverObject
0x140054402  call    ClassGetDriverExtension
0x140054407  mov     rdx, rax
0x14005440a  mov     [rsp+48h+arg_0], 0
0x14005440f  mov     rcx, r14
0x140054412  mov     rbx, rax
0x140054415  call    ClasspIsMediaChangeDisabledDueToHardwareLimitation
0x14005441a  test    al, al
0x14005441c  jz      short loc_140054465
0x14005441e  mov     rcx, cs:WPP_GLOBAL_Control
0x140054425  lea     rsi, WPP_GLOBAL_Control
0x14005442c  cmp     rcx, rsi
0x14005442f  jz      loc_140054598
0x140054435  bt      dword ptr [rcx+2Ch], 0Ch
0x14005443a  jnb     loc_140054598
0x140054440  mov     bl, 4
0x140054442  cmp     [rcx+29h], bl
0x140054445  jb      loc_140054598
0x14005444b  mov     rcx, [rcx+18h]
0x14005444f  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054456  mov     edx, 46h ; 'F'
0x14005445b  call    WPP_SF_
0x140054460  jmp     loc_140054598
0x140054465  mov     rdx, rbx
0x140054468  mov     rcx, r14
0x14005446b  call    ClasspIsMediaChangeDisabledForClass
0x140054470  mov     r15b, al
0x140054473  mov     rcx, cs:WPP_GLOBAL_Control
0x14005447a  lea     rsi, WPP_GLOBAL_Control
0x140054481  lea     r13, aEnabled; "enabled"
0x140054488  mov     bl, 4
0x14005448a  lea     r12, aDisabled_0; "disabled"
0x140054491  cmp     rcx, rsi
0x140054494  jz      short loc_1400544C0
0x140054496  bt      dword ptr [rcx+2Ch], 0Ch
0x14005449b  jnb     short loc_1400544C0
0x14005449d  cmp     [rcx+29h], bl
0x1400544a0  jb      short loc_1400544C0
0x1400544a2  mov     rcx, [rcx+18h]
0x1400544a6  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400544ad  test    al, al
0x1400544af  mov     r9, r12
0x1400544b2  mov     edx, 47h ; 'G'
0x1400544b7  cmovz   r9, r13
0x1400544bb  call    WPP_SF_s
0x1400544c0  lea     rdx, [rsp+48h+arg_0]
0x1400544c5  mov     rcx, r14
0x1400544c8  call    ClasspMediaChangeDeviceInstanceOverride
0x1400544cd  test    eax, eax
0x1400544cf  jns     short loc_140054504
0x1400544d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400544d8  cmp     rcx, rsi
0x1400544db  jz      loc_140054589
0x1400544e1  bt      dword ptr [rcx+2Ch], 0Ch
0x1400544e6  jnb     short loc_140054552
0x1400544e8  cmp     [rcx+29h], bl
0x1400544eb  jb      short loc_140054552
0x1400544ed  mov     rcx, [rcx+18h]
0x1400544f1  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400544f8  mov     edx, 48h ; 'H'
0x1400544fd  call    WPP_SF_
0x140054502  jmp     short loc_140054552
0x140054504  mov     rcx, cs:WPP_GLOBAL_Control
0x14005450b  mov     r15b, [rsp+48h+arg_0]
0x140054510  cmp     rcx, rsi
0x140054513  jz      short loc_14005454B
0x140054515  bt      dword ptr [rcx+2Ch], 0Ch
0x14005451a  jnb     short loc_14005454B
0x14005451c  cmp     [rcx+29h], bl
0x14005451f  jb      short loc_14005454B
0x140054521  mov     rcx, [rcx+18h]
0x140054525  lea     rax, aDisabling; "Disabling"
0x14005452c  test    r15b, r15b
0x14005452f  lea     r9, aEnabling; "Enabling"
0x140054536  mov     edx, 49h ; 'I'
0x14005453b  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054542  cmovz   r9, rax
0x140054546  call    WPP_SF_s
0x14005454b  test    r15b, r15b
0x14005454e  setz    r15b
0x140054552  mov     rcx, cs:WPP_GLOBAL_Control
0x140054559  cmp     rcx, rsi
0x14005455c  jz      short loc_140054589
0x14005455e  bt      dword ptr [rcx+2Ch], 0Ch
0x140054563  jnb     short loc_140054589
0x140054565  cmp     [rcx+29h], bl
0x140054568  jb      short loc_140054589
0x14005456a  mov     rcx, [rcx+18h]
0x14005456e  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054575  test    r15b, r15b
0x140054578  mov     edx, 4Ah ; 'J'
0x14005457d  cmovz   r12, r13
0x140054581  mov     r9, r12
0x140054584  call    WPP_SF_s
0x140054589  test    r15b, r15b
0x14005458c  jnz     short loc_140054598
0x14005458e  xor     edx, edx
0x140054590  mov     rcx, r14; FdoExtension
0x140054593  call    ClasspInitializePolling
0x140054598  mov     rbx, [rsp+48h+arg_8]
0x14005459d  mov     rsi, [rsp+48h+arg_10]
0x1400545a2  add     rsp, 20h
0x1400545a6  pop     r15
0x1400545a8  pop     r14
0x1400545aa  pop     r13
0x1400545ac  pop     r12
0x1400545ae  pop     rdi
0x1400545af  retn
```
