# InitializeService(ulong,ushort * * const)

- ea: `0x180006124`
- end: `0x1800061aa`
- name: `?InitializeService@@YAJKQEAPEAG@Z`
- size: `134`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006240`

## callees

- `0x1800049c0`
- `0x180004ab4`
- `0x180004bec`
- `0x180006124`

## import_xrefs

- `dmpushroutercore!RegisterRPCInterface` at `0x18000615f`
- `dmpushroutercore!RegisterRPCInterface` at `0x18000615f`

## pseudocode

```c
__int64 __fastcall InitializeService(unsigned int a1, unsigned __int16 **const a2)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  __int64 *v5; // rdx

  v2 = SvcEngInitialize(a1, a2);
  v4 = v2;
  if ( v2 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(v3, PushRouterSvcEngInitializeSucceeded, (unsigned int)v2);
    v2 = RegisterRPCInterface();
    v4 = v2;
    if ( v2 >= 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      {
        v5 = PushRouterSvcEngRegisterRPCInterfaceSucceeded;
        goto LABEL_12;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
        McTemplateU0d_EventWriteTransfer(v3, PushRouterSvcEngRegisterRPCInterfaceFailed, (unsigned int)v2);
      SvcEngUninitialize(v3);
    }
  }
  else if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
  {
    v5 = PushRouterSvcEngInitializeFailed;
LABEL_12:
    McTemplateU0d_EventWriteTransfer(v3, v5, (unsigned int)v2);
  }
  return v4;
}

```

## disassembly

```asm
0x180006124  push    rbx
0x180006126  sub     rsp, 20h
0x18000612a  call    ?SvcEngInitialize@@YAJKQEAPEAG@Z; SvcEngInitialize(ulong,ushort * * const)
0x18000612f  mov     ebx, eax
0x180006131  test    eax, eax
0x180006133  jns     short loc_180006147
0x180006135  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000613c  jz      short loc_1800061A2
0x18000613e  lea     rdx, PushRouterSvcEngInitializeFailed
0x180006145  jmp     short loc_18000619A
0x180006147  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x18000614e  jz      short loc_18000615F
0x180006150  mov     r8d, eax
0x180006153  lea     rdx, PushRouterSvcEngInitializeSucceeded
0x18000615a  call    McTemplateU0d_EventWriteTransfer
0x18000615f  call    cs:__imp_RegisterRPCInterface
0x180006165  mov     ebx, eax
0x180006167  test    eax, eax
0x180006169  jns     short loc_18000618A
0x18000616b  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x180006172  jz      short loc_180006183
0x180006174  mov     r8d, eax
0x180006177  lea     rdx, PushRouterSvcEngRegisterRPCInterfaceFailed
0x18000617e  call    McTemplateU0d_EventWriteTransfer
0x180006183  call    ?SvcEngUninitialize@@YAJJ@Z; SvcEngUninitialize(long)
0x180006188  jmp     short loc_1800061A2
0x18000618a  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180006191  jz      short loc_1800061A2
0x180006193  lea     rdx, PushRouterSvcEngRegisterRPCInterfaceSucceeded
0x18000619a  mov     r8d, eax
0x18000619d  call    McTemplateU0d_EventWriteTransfer
0x1800061a2  mov     eax, ebx
0x1800061a4  add     rsp, 20h
0x1800061a8  pop     rbx
0x1800061a9  retn
```
