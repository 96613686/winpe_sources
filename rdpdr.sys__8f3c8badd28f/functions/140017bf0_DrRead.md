# DrRead

- ea: `0x140017bf0`
- end: `0x140017c6a`
- name: `DrRead`
- size: `122`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001050`
- `0x1400016a0`
- `0x14000324c`
- `0x140017bf0`
- `0x14001f710`

## pseudocode

```c
__int64 __fastcall DrRead(struct _RX_CONTEXT *a1)
{
  unsigned int v2; // ebx
  DrDevice *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  if ( (unsigned int)GetDeviceFromRxContext(a1, &v4) )
    v2 = DrDevice::Read(v4, a1);
  else
    v2 = -1073741823;
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v4);
  return v2;
}

```

## disassembly

```asm
0x140017bf0  push    rbx
0x140017bf2  sub     rsp, 20h
0x140017bf6  mov     rbx, rcx
0x140017bf9  mov     [rsp+28h+arg_8], 0
0x140017c02  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c09  lea     rax, WPP_GLOBAL_Control
0x140017c10  cmp     rcx, rax
0x140017c13  jz      short loc_140017C30
0x140017c15  cmp     byte ptr [rcx+29h], 4
0x140017c19  jb      short loc_140017C30
0x140017c1b  mov     rcx, [rcx+18h]
0x140017c1f  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140017c26  mov     edx, 21h ; '!'
0x140017c2b  call    WPP_SF_
0x140017c30  lea     rdx, [rsp+28h+arg_8]
0x140017c35  mov     rcx, rbx
0x140017c38  call    ?GetDeviceFromRxContext@@YAHPEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z; GetDeviceFromRxContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)
0x140017c3d  test    eax, eax
0x140017c3f  jz      short loc_140017C52
0x140017c41  mov     rcx, [rsp+28h+arg_8]; this
0x140017c46  mov     rdx, rbx; struct _RX_CONTEXT *
0x140017c49  call    ?Read@DrDevice@@QEAAJPEAU_RX_CONTEXT@@@Z; DrDevice::Read(_RX_CONTEXT *)
0x140017c4e  mov     ebx, eax
0x140017c50  jmp     short loc_140017C57
0x140017c52  mov     ebx, 0C0000001h
0x140017c57  lea     rcx, [rsp+28h+arg_8]
0x140017c5c  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140017c61  mov     eax, ebx
0x140017c63  add     rsp, 20h
0x140017c67  pop     rbx
0x140017c68  retn
```
