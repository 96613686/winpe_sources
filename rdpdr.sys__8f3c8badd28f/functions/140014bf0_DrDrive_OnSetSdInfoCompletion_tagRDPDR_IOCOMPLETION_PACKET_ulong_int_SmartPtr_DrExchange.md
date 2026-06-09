# DrDrive::OnSetSdInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140014bf0`
- end: `0x140014c99`
- name: `?OnSetSdInfoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140003704`
- `0x1400117e0`
- `0x140014bf0`
- `0x140024020`

## string_xrefs

- `0x140014c46`: `IRP_MJ_CREATE                  `

## pseudocode

```c
__int64 __fastcall DrDrive::OnSetSdInfoCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rax

  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 32LL) + 48LL);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_sL(
        WPP_GLOBAL_Control->AttachedDevice,
        144,
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
0x140014bf0  mov     [rsp+arg_0], rbx
0x140014bf5  mov     [rsp+arg_8], rsi
0x140014bfa  push    rdi
0x140014bfb  sub     rsp, 30h
0x140014bff  mov     rbx, [rsp+38h+arg_20]
0x140014c04  mov     rsi, rdx
0x140014c07  mov     rdi, rcx
0x140014c0a  mov     rax, [rbx]
0x140014c0d  mov     r8, [rax+20h]
0x140014c11  mov     rax, [r8+30h]
0x140014c15  test    rax, rax
0x140014c18  jz      short loc_140014C76
0x140014c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c21  lea     rdx, WPP_GLOBAL_Control
0x140014c28  cmp     rcx, rdx
0x140014c2b  jz      short loc_140014C62
0x140014c2d  cmp     byte ptr [rcx+29h], 5
0x140014c31  jb      short loc_140014C62
0x140014c33  movzx   eax, byte ptr [rax+20h]
0x140014c37  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014c3e  mov     rcx, [rcx+18h]
0x140014c42  lea     rdx, [rax+rax*4]
0x140014c46  lea     rax, ?IrpNames@@3PAY0CI@DA; "IRP_MJ_CREATE                  "
0x140014c4d  lea     r9, [rax+rdx*8]
0x140014c51  mov     eax, [rsi+0Ch]
0x140014c54  mov     edx, 90h
0x140014c59  mov     [rsp+38h+var_18], eax
0x140014c5d  call    WPP_SF_sL
0x140014c62  mov     r8d, [rsi+0Ch]
0x140014c66  xor     r9d, r9d
0x140014c69  mov     rdx, rbx
0x140014c6c  mov     rcx, rdi
0x140014c6f  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140014c74  jmp     short loc_140014C7E
0x140014c76  mov     rdx, rbx
0x140014c79  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140014c7e  mov     rcx, rbx
0x140014c81  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014c86  mov     rbx, [rsp+38h+arg_0]
0x140014c8b  xor     eax, eax
0x140014c8d  mov     rsi, [rsp+38h+arg_8]
0x140014c92  add     rsp, 30h
0x140014c96  pop     rdi
0x140014c97  retn
```
