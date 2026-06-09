# DrDrive::OnLocksCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140012f40`
- end: `0x140012fe9`
- name: `?OnLocksCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140003704`
- `0x1400117e0`
- `0x140012f40`
- `0x140024020`

## string_xrefs

- `0x140012f96`: `IRP_MJ_CREATE                  `

## pseudocode

```c
__int64 __fastcall DrDrive::OnLocksCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rax

  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 32LL) + 48LL);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_sL(
        WPP_GLOBAL_Control->AttachedDevice,
        145,
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
0x140012f40  mov     [rsp+arg_0], rbx
0x140012f45  mov     [rsp+arg_8], rsi
0x140012f4a  push    rdi
0x140012f4b  sub     rsp, 30h
0x140012f4f  mov     rbx, [rsp+38h+arg_20]
0x140012f54  mov     rsi, rdx
0x140012f57  mov     rdi, rcx
0x140012f5a  mov     rax, [rbx]
0x140012f5d  mov     r8, [rax+20h]
0x140012f61  mov     rax, [r8+30h]
0x140012f65  test    rax, rax
0x140012f68  jz      short loc_140012FC6
0x140012f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f71  lea     rdx, WPP_GLOBAL_Control
0x140012f78  cmp     rcx, rdx
0x140012f7b  jz      short loc_140012FB2
0x140012f7d  cmp     byte ptr [rcx+29h], 5
0x140012f81  jb      short loc_140012FB2
0x140012f83  movzx   eax, byte ptr [rax+20h]
0x140012f87  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140012f8e  mov     rcx, [rcx+18h]
0x140012f92  lea     rdx, [rax+rax*4]
0x140012f96  lea     rax, ?IrpNames@@3PAY0CI@DA; "IRP_MJ_CREATE                  "
0x140012f9d  lea     r9, [rax+rdx*8]
0x140012fa1  mov     eax, [rsi+0Ch]
0x140012fa4  mov     edx, 91h
0x140012fa9  mov     [rsp+38h+var_18], eax
0x140012fad  call    WPP_SF_sL
0x140012fb2  mov     r8d, [rsi+0Ch]
0x140012fb6  xor     r9d, r9d
0x140012fb9  mov     rdx, rbx
0x140012fbc  mov     rcx, rdi
0x140012fbf  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140012fc4  jmp     short loc_140012FCE
0x140012fc6  mov     rdx, rbx
0x140012fc9  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140012fce  mov     rcx, rbx
0x140012fd1  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140012fd6  mov     rbx, [rsp+38h+arg_0]
0x140012fdb  xor     eax, eax
0x140012fdd  mov     rsi, [rsp+38h+arg_8]
0x140012fe2  add     rsp, 30h
0x140012fe6  pop     rdi
0x140012fe7  retn
```
