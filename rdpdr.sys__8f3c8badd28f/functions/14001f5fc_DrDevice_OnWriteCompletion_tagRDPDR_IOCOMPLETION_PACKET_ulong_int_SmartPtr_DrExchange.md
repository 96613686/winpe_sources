# DrDevice::OnWriteCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x14001f5fc`
- end: `0x14001f707`
- name: `?OnWriteCompletion@DrDevice@@QEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140022ab0`

## callees

- `0x1400016a0`
- `0x14000324c`
- `0x140003704`
- `0x1400117e0`
- `0x14001f5fc`
- `0x140024020`

## string_xrefs

- `0x14001f6b3`: `IRP_MJ_CREATE                  `

## pseudocode

```c
__int64 __fastcall DrDevice::OnWriteCompletion(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, __int64 a5)
{
  __int64 v8; // rbp
  unsigned int v9; // edi

  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 32LL) + 48LL);
  if ( a3 >= 0x15 )
  {
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_sL(
          WPP_GLOBAL_Control->AttachedDevice,
          76,
          (unsigned int)WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
          (unsigned int)&(&IrpNames)[5 * *(unsigned __int8 *)(v8 + 32)],
          *(_DWORD *)(v8 + 176));
      DrDevice::CompleteBusyExchange(a1, a5, *(_DWORD *)(a2 + 12), *(_DWORD *)(a2 + 16));
    }
    else
    {
      DrDevice::DiscardBusyExchange(a1, a5);
    }
    v9 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v9 = -1073741434;
    if ( v8 )
      DrDevice::CompleteBusyExchange(a1, a5, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, a5);
    *a4 = 0;
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return v9;
}

```

## disassembly

```asm
0x14001f5fc  push    rbx
0x14001f5fe  push    rbp
0x14001f5ff  push    rsi
0x14001f600  push    rdi
0x14001f601  push    r14
0x14001f603  sub     rsp, 30h
0x14001f607  mov     rbx, [rsp+58h+arg_20]
0x14001f60f  mov     r14, r9
0x14001f612  mov     rdi, rdx
0x14001f615  mov     rsi, rcx
0x14001f618  mov     rax, [rbx]
0x14001f61b  mov     r10, [rax+20h]
0x14001f61f  mov     rbp, [r10+30h]
0x14001f623  cmp     r8d, 15h
0x14001f627  jnb     short loc_14001F682
0x14001f629  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f630  lea     rax, WPP_GLOBAL_Control
0x14001f637  cmp     rcx, rax
0x14001f63a  jz      short loc_14001F657
0x14001f63c  cmp     byte ptr [rcx+29h], 2
0x14001f640  jb      short loc_14001F657
0x14001f642  mov     rcx, [rcx+18h]
0x14001f646  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f64d  mov     edx, 4Bh ; 'K'
0x14001f652  call    WPP_SF_
0x14001f657  mov     edi, 0C0000186h
0x14001f65c  mov     rdx, rbx
0x14001f65f  mov     rcx, rsi
0x14001f662  test    rbp, rbp
0x14001f665  jz      short loc_14001F674
0x14001f667  xor     r9d, r9d
0x14001f66a  mov     r8d, edi
0x14001f66d  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x14001f672  jmp     short loc_14001F679
0x14001f674  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x14001f679  mov     dword ptr [r14], 0
0x14001f680  jmp     short loc_14001F6F1
0x14001f682  test    rbp, rbp
0x14001f685  jz      short loc_14001F6E7
0x14001f687  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f68e  lea     rax, WPP_GLOBAL_Control
0x14001f695  cmp     rcx, rax
0x14001f698  jz      short loc_14001F6D2
0x14001f69a  cmp     byte ptr [rcx+29h], 5
0x14001f69e  jb      short loc_14001F6D2
0x14001f6a0  movzx   eax, byte ptr [rbp+20h]
0x14001f6a4  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f6ab  mov     rcx, [rcx+18h]
0x14001f6af  lea     rdx, [rax+rax*4]
0x14001f6b3  lea     rax, ?IrpNames@@3PAY0CI@DA; "IRP_MJ_CREATE                  "
0x14001f6ba  lea     r9, [rax+rdx*8]
0x14001f6be  mov     eax, [rbp+0B0h]
0x14001f6c4  mov     edx, 4Ch ; 'L'
0x14001f6c9  mov     [rsp+58h+var_38], eax
0x14001f6cd  call    WPP_SF_sL
0x14001f6d2  mov     r9d, [rdi+10h]
0x14001f6d6  mov     rdx, rbx
0x14001f6d9  mov     r8d, [rdi+0Ch]
0x14001f6dd  mov     rcx, rsi
0x14001f6e0  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x14001f6e5  jmp     short loc_14001F6EF
0x14001f6e7  mov     rdx, rbx
0x14001f6ea  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x14001f6ef  xor     edi, edi
0x14001f6f1  mov     rcx, rbx
0x14001f6f4  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f6f9  mov     eax, edi
0x14001f6fb  add     rsp, 30h
0x14001f6ff  pop     r14
0x14001f701  pop     rdi
0x14001f702  pop     rsi
0x14001f703  pop     rbp
0x14001f704  pop     rbx
0x14001f705  retn
```
