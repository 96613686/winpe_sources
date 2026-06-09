# DrDeviceManager::ProcessDeviceRemove(tagRDPDR_DEVICE_REMOVE *)

- ea: `0x140020788`
- end: `0x140020877`
- name: `?ProcessDeviceRemove@DrDeviceManager@@AEAAXPEAUtagRDPDR_DEVICE_REMOVE@@@Z`
- size: `239`
- prototype: `void __fastcall(DrDeviceManager *__hidden this, struct tagRDPDR_DEVICE_REMOVE *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14001ff80`
- `0x1400205a8`

## callees

- `0x140001310`
- `0x1400016a0`
- `0x140001890`
- `0x14000324c`
- `0x14000327c`
- `0x140006560`
- `0x140011b3c`
- `0x140020788`
- `0x14002be98`

## pseudocode

```c
void __fastcall DrDeviceManager::ProcessDeviceRemove(DrDeviceManager *this, struct tagRDPDR_DEVICE_REMOVE *a2)
{
  RefCount *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  RefCount *v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  v3 = (RefCount *)*((_QWORD *)this + 24);
  v6 = v3;
  if ( v3 )
    RefCount::AddRef(v3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids,
      *(unsigned int *)a2);
  if ( (unsigned int)DrDeviceManager::FindDeviceById(this, *(unsigned int *)a2, &v5) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
    DrDeviceManager::RemoveDevice(this, &v5);
    SmartPtr<DrDevice>::operator=(&v5, 0);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v6);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v5);
}

```

## disassembly

```asm
0x140020788  mov     rax, rsp
0x14002078b  mov     [rax+18h], rbx
0x14002078f  mov     [rax+20h], rsi
0x140020793  push    rdi
0x140020794  sub     rsp, 20h
0x140020798  mov     rbx, rcx
0x14002079b  mov     qword ptr [rax+8], 0
0x1400207a3  mov     rcx, [rcx+0C0h]; this
0x1400207aa  mov     rdi, rdx
0x1400207ad  mov     [rax+10h], rcx
0x1400207b1  test    rcx, rcx
0x1400207b4  jz      short loc_1400207BB
0x1400207b6  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400207bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207c2  lea     rsi, WPP_GLOBAL_Control
0x1400207c9  cmp     rcx, rsi
0x1400207cc  jz      short loc_1400207EC
0x1400207ce  cmp     byte ptr [rcx+29h], 4
0x1400207d2  jb      short loc_1400207EC
0x1400207d4  mov     r9d, [rdi]
0x1400207d7  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x1400207de  mov     rcx, [rcx+18h]
0x1400207e2  mov     edx, 29h ; ')'
0x1400207e7  call    WPP_SF_d
0x1400207ec  mov     edx, [rdi]
0x1400207ee  lea     r8, [rsp+28h+arg_0]
0x1400207f3  mov     rcx, rbx
0x1400207f6  call    ?FindDeviceById@DrDeviceManager@@QEAAHKAEAV?$SmartPtr@VDrDevice@@@@H@Z; DrDeviceManager::FindDeviceById(ulong,SmartPtr<DrDevice> &,int)
0x1400207fb  test    eax, eax
0x1400207fd  jz      short loc_14002082B
0x1400207ff  mov     rcx, [rsp+28h+arg_0]
0x140020804  mov     rax, [rcx]
0x140020807  mov     rax, [rax+40h]
0x14002080b  call    _guard_dispatch_icall
0x140020810  lea     rdx, [rsp+28h+arg_0]
0x140020815  mov     rcx, rbx
0x140020818  call    ?RemoveDevice@DrDeviceManager@@QEAAXAEAV?$SmartPtr@VDrDevice@@@@@Z; DrDeviceManager::RemoveDevice(SmartPtr<DrDevice> &)
0x14002081d  xor     edx, edx
0x14002081f  lea     rcx, [rsp+28h+arg_0]
0x140020824  call    ??4?$SmartPtr@VDrDevice@@@@QEAAAEAV0@PEAVDrDevice@@@Z; SmartPtr<DrDevice>::operator=(DrDevice *)
0x140020829  jmp     short loc_140020852
0x14002082b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020832  cmp     rcx, rsi
0x140020835  jz      short loc_140020852
0x140020837  cmp     byte ptr [rcx+29h], 5
0x14002083b  jb      short loc_140020852
0x14002083d  mov     rcx, [rcx+18h]
0x140020841  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x140020848  mov     edx, 2Ah ; '*'
0x14002084d  call    WPP_SF_
0x140020852  lea     rcx, [rsp+28h+arg_8]
0x140020857  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14002085c  lea     rcx, [rsp+28h+arg_0]
0x140020861  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140020866  mov     rbx, [rsp+28h+arg_10]
0x14002086b  mov     rsi, [rsp+28h+arg_18]
0x140020870  add     rsp, 20h
0x140020874  pop     rdi
0x140020875  retn
```
