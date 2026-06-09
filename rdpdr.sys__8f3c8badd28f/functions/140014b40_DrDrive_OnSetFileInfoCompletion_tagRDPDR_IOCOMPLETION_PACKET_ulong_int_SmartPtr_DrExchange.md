# DrDrive::OnSetFileInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140014b40`
- end: `0x140014be9`
- name: `?OnSetFileInfoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400016a0`
- `0x140003704`
- `0x1400117e0`
- `0x140014b40`
- `0x140024020`

## string_xrefs

- `0x140014b96`: `IRP_MJ_CREATE                  `

## pseudocode

```c
__int64 __fastcall DrDrive::OnSetFileInfoCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rax

  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 32LL) + 48LL);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_sL(
        WPP_GLOBAL_Control->AttachedDevice,
        134,
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
0x140014b40  mov     [rsp+arg_0], rbx
0x140014b45  mov     [rsp+arg_8], rsi
0x140014b4a  push    rdi
0x140014b4b  sub     rsp, 30h
0x140014b4f  mov     rbx, [rsp+38h+arg_20]
0x140014b54  mov     rsi, rdx
0x140014b57  mov     rdi, rcx
0x140014b5a  mov     rax, [rbx]
0x140014b5d  mov     r8, [rax+20h]
0x140014b61  mov     rax, [r8+30h]
0x140014b65  test    rax, rax
0x140014b68  jz      short loc_140014BC6
0x140014b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b71  lea     rdx, WPP_GLOBAL_Control
0x140014b78  cmp     rcx, rdx
0x140014b7b  jz      short loc_140014BB2
0x140014b7d  cmp     byte ptr [rcx+29h], 5
0x140014b81  jb      short loc_140014BB2
0x140014b83  movzx   eax, byte ptr [rax+20h]
0x140014b87  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014b8e  mov     rcx, [rcx+18h]
0x140014b92  lea     rdx, [rax+rax*4]
0x140014b96  lea     rax, ?IrpNames@@3PAY0CI@DA; "IRP_MJ_CREATE                  "
0x140014b9d  lea     r9, [rax+rdx*8]
0x140014ba1  mov     eax, [rsi+0Ch]
0x140014ba4  mov     edx, 86h
0x140014ba9  mov     [rsp+38h+var_18], eax
0x140014bad  call    WPP_SF_sL
0x140014bb2  mov     r8d, [rsi+0Ch]
0x140014bb6  xor     r9d, r9d
0x140014bb9  mov     rdx, rbx
0x140014bbc  mov     rcx, rdi
0x140014bbf  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140014bc4  jmp     short loc_140014BCE
0x140014bc6  mov     rdx, rbx
0x140014bc9  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140014bce  mov     rcx, rbx
0x140014bd1  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014bd6  mov     rbx, [rsp+38h+arg_0]
0x140014bdb  xor     eax, eax
0x140014bdd  mov     rsi, [rsp+38h+arg_8]
0x140014be2  add     rsp, 30h
0x140014be6  pop     rdi
0x140014be7  retn
```
