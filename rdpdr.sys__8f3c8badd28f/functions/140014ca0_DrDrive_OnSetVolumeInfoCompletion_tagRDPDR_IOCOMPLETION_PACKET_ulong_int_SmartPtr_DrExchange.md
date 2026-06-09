# DrDrive::OnSetVolumeInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140014ca0`
- end: `0x140014d49`
- name: `?OnSetVolumeInfoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140003704`
- `0x1400117e0`
- `0x140014ca0`
- `0x140024020`

## string_xrefs

- `0x140014cf6`: `IRP_MJ_CREATE                  `

## pseudocode

```c
__int64 __fastcall DrDrive::OnSetVolumeInfoCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rax

  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 32LL) + 48LL);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_sL(
        WPP_GLOBAL_Control->AttachedDevice,
        116,
        (unsigned int)WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
        (unsigned int)&(&IrpNames)[5 * *(unsigned __int8 *)(v7 + 32)],
        *(_DWORD *)(a2 + 12));
    DrDevice::CompleteBusyExchange(a1, a5, *(_DWORD *)(a2 + 12), 0);
  }
  else
  {
    DrDevice::DiscardBusyExchange(a1, a5);
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return 0;
}

```

## disassembly

```asm
0x140014ca0  mov     [rsp+arg_0], rbx
0x140014ca5  mov     [rsp+arg_8], rsi
0x140014caa  push    rdi
0x140014cab  sub     rsp, 30h
0x140014caf  mov     rbx, [rsp+38h+arg_20]
0x140014cb4  mov     rsi, rdx
0x140014cb7  mov     rdi, rcx
0x140014cba  mov     rax, [rbx]
0x140014cbd  mov     r8, [rax+20h]
0x140014cc1  mov     rax, [r8+30h]
0x140014cc5  test    rax, rax
0x140014cc8  jz      short loc_140014D26
0x140014cca  mov     rcx, cs:WPP_GLOBAL_Control
0x140014cd1  lea     rdx, WPP_GLOBAL_Control
0x140014cd8  cmp     rcx, rdx
0x140014cdb  jz      short loc_140014D12
0x140014cdd  cmp     byte ptr [rcx+29h], 5
0x140014ce1  jb      short loc_140014D12
0x140014ce3  movzx   eax, byte ptr [rax+20h]
0x140014ce7  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014cee  mov     rcx, [rcx+18h]
0x140014cf2  lea     rdx, [rax+rax*4]
0x140014cf6  lea     rax, ?IrpNames@@3PAY0CI@DA; "IRP_MJ_CREATE                  "
0x140014cfd  lea     r9, [rax+rdx*8]
0x140014d01  mov     eax, [rsi+0Ch]
0x140014d04  mov     edx, 74h ; 't'
0x140014d09  mov     [rsp+38h+var_18], eax
0x140014d0d  call    WPP_SF_sL
0x140014d12  mov     r8d, [rsi+0Ch]
0x140014d16  xor     r9d, r9d
0x140014d19  mov     rdx, rbx
0x140014d1c  mov     rcx, rdi
0x140014d1f  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140014d24  jmp     short loc_140014D2E
0x140014d26  mov     rdx, rbx
0x140014d29  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140014d2e  mov     rcx, rbx
0x140014d31  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014d36  mov     rbx, [rsp+38h+arg_0]
0x140014d3b  xor     eax, eax
0x140014d3d  mov     rsi, [rsp+38h+arg_8]
0x140014d42  add     rsp, 30h
0x140014d46  pop     rdi
0x140014d47  retn
```
