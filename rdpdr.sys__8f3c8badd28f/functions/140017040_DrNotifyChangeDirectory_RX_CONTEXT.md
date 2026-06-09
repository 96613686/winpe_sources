# DrNotifyChangeDirectory(_RX_CONTEXT *)

- ea: `0x140017040`
- end: `0x1400170c4`
- name: `?DrNotifyChangeDirectory@@YAJPEAU_RX_CONTEXT@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001050`
- `0x1400016a0`
- `0x14000324c`
- `0x140006560`
- `0x140017040`

## pseudocode

```c
__int64 __fastcall DrNotifyChangeDirectory(struct _RX_CONTEXT *a1)
{
  unsigned int v2; // ebx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  if ( (unsigned int)GetDeviceFromRxContext(a1, &v4) )
    v2 = (*(__int64 (__fastcall **)(__int64, struct _RX_CONTEXT *))(*(_QWORD *)v4 + 160LL))(v4, a1);
  else
    v2 = -1073741823;
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v4);
  return v2;
}

```

## disassembly

```asm
0x140017040  push    rbx
0x140017042  sub     rsp, 20h
0x140017046  mov     rbx, rcx
0x140017049  mov     [rsp+28h+arg_8], 0
0x140017052  mov     rcx, cs:WPP_GLOBAL_Control
0x140017059  lea     rax, WPP_GLOBAL_Control
0x140017060  cmp     rcx, rax
0x140017063  jz      short loc_140017080
0x140017065  cmp     byte ptr [rcx+29h], 4
0x140017069  jb      short loc_140017080
0x14001706b  mov     rcx, [rcx+18h]
0x14001706f  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140017076  mov     edx, 40h ; '@'
0x14001707b  call    WPP_SF_
0x140017080  lea     rdx, [rsp+28h+arg_8]
0x140017085  mov     rcx, rbx
0x140017088  call    ?GetDeviceFromRxContext@@YAHPEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z; GetDeviceFromRxContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)
0x14001708d  test    eax, eax
0x14001708f  jz      short loc_1400170AC
0x140017091  mov     rcx, [rsp+28h+arg_8]
0x140017096  mov     rdx, rbx
0x140017099  mov     rax, [rcx]
0x14001709c  mov     rax, [rax+0A0h]
0x1400170a3  call    _guard_dispatch_icall
0x1400170a8  mov     ebx, eax
0x1400170aa  jmp     short loc_1400170B1
0x1400170ac  mov     ebx, 0C0000001h
0x1400170b1  lea     rcx, [rsp+28h+arg_8]
0x1400170b6  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400170bb  mov     eax, ebx
0x1400170bd  add     rsp, 20h
0x1400170c1  pop     rbx
0x1400170c2  retn
```
