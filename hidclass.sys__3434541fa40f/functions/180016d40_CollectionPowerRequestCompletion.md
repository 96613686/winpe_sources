# CollectionPowerRequestCompletion

- ea: `0x180016d40`
- end: `0x180016de3`
- name: `CollectionPowerRequestCompletion`
- size: `163`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016d40`
- `0x180018220`
- `0x180038090`

## import_xrefs

- `ntoskrnl!PoStartNextPowerIrp` at `0x180016d6e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180016d6e`
- `ntoskrnl!IofCompleteRequest` at `0x180016d7f`
- `ntoskrnl!IofCompleteRequest` at `0x180016d7f`

## pseudocode

```c
void __fastcall CollectionPowerRequestCompletion(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        _QWORD *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  char *DeviceExtension; // rsi
  int v7; // ebx
  __int64 v8; // rax

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v7 = *(_DWORD *)(Context[23] + 24LL);
  *((_DWORD *)Context + 12) = IoStatus->Status;
  PoStartNextPowerIrp((PIRP)Context);
  IofCompleteRequest((PIRP)Context, 0);
  if ( v7 == 1 && !DeviceExtension[288] )
  {
    v8 = *((_QWORD *)DeviceExtension + 12);
    if ( *(int *)(v8 + 376) > 1
      && *(int *)(v8 + 372) > 1
      && !_InterlockedCompareExchange64((volatile signed __int64 *)DeviceExtension + 16, 0, 0) )
    {
      if ( (unsigned __int8)HidpCheckRemoteWakeEnabled(DeviceExtension + 32) )
        HidpCreateRemoteWakeIrp(DeviceExtension + 32);
    }
  }
}

```

## disassembly

```asm
0x180016d40  mov     [rsp+arg_0], rbx
0x180016d45  mov     [rsp+arg_8], rsi
0x180016d4a  push    rdi
0x180016d4b  sub     rsp, 20h
0x180016d4f  mov     rsi, [rcx+40h]
0x180016d53  mov     rdi, r9
0x180016d56  mov     rax, [r9+0B8h]
0x180016d5d  mov     ebx, [rax+18h]
0x180016d60  mov     rax, [rsp+28h+IoStatus]
0x180016d65  mov     ecx, [rax]
0x180016d67  mov     [r9+30h], ecx
0x180016d6b  mov     rcx, r9; Irp
0x180016d6e  call    cs:__imp_PoStartNextPowerIrp
0x180016d75  nop     dword ptr [rax+rax+00h]
0x180016d7a  xor     edx, edx; PriorityBoost
0x180016d7c  mov     rcx, rdi; Irp
0x180016d7f  call    cs:__imp_IofCompleteRequest
0x180016d86  nop     dword ptr [rax+rax+00h]
0x180016d8b  cmp     ebx, 1
0x180016d8e  jnz     short loc_180016DD2
0x180016d90  cmp     byte ptr [rsi+120h], 0
0x180016d97  jnz     short loc_180016DD2
0x180016d99  mov     rax, [rsi+60h]
0x180016d9d  cmp     [rax+178h], ebx
0x180016da3  jle     short loc_180016DD2
0x180016da5  cmp     [rax+174h], ebx
0x180016dab  jle     short loc_180016DD2
0x180016dad  xor     edx, edx
0x180016daf  xor     eax, eax
0x180016db1  lock cmpxchg [rsi+80h], rdx
0x180016dba  jnz     short loc_180016DD2
0x180016dbc  lea     rcx, [rsi+20h]
0x180016dc0  call    HidpCheckRemoteWakeEnabled
0x180016dc5  test    al, al
0x180016dc7  jz      short loc_180016DD2
0x180016dc9  lea     rcx, [rsi+20h]; Context
0x180016dcd  call    HidpCreateRemoteWakeIrp
0x180016dd2  mov     rbx, [rsp+28h+arg_0]
0x180016dd7  mov     rsi, [rsp+28h+arg_8]
0x180016ddc  add     rsp, 20h
0x180016de0  pop     rdi
0x180016de1  retn
```
