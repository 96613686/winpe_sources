# ServiceHandler

- ea: `0x1800061e0`
- end: `0x18000623a`
- name: `ServiceHandler`
- size: `90`
- prototype: `__int64 __fastcall(__int64 dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800061b0`
- `0x1800061e0`
- `0x1800067a0`

## pseudocode

```c
__int64 __fastcall ServiceHandler(__int64 dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // edi
  int v5; // ebx
  int v6; // ebx

  v4 = 0;
  v5 = dwControl;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McTemplateU0dd_EventWriteTransfer(
      dwControl,
      (const EVENT_DESCRIPTOR *)PushRoutererviceHandlerInvoked,
      (unsigned int)dwControl,
      ServiceStatus.dwCurrentState);
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 == 31 && ServiceStatus.dwCurrentState == 3 )
      return 1115;
  }
  else
  {
    InitiateStop();
  }
  return v4;
}

```

## disassembly

```asm
0x1800061e0  mov     [rsp+arg_0], rbx
0x1800061e5  push    rdi
0x1800061e6  sub     rsp, 20h
0x1800061ea  xor     edi, edi
0x1800061ec  mov     ebx, ecx
0x1800061ee  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x1800061f5  jz      short loc_18000620D
0x1800061f7  mov     r9d, cs:ServiceStatus.dwCurrentState
0x1800061fe  lea     rdx, PushRoutererviceHandlerInvoked
0x180006205  mov     r8d, ecx
0x180006208  call    McTemplateU0dd_EventWriteTransfer
0x18000620d  sub     ebx, 1
0x180006210  jz      short loc_180006228
0x180006212  cmp     ebx, 1Fh
0x180006215  jnz     short loc_18000622D
0x180006217  cmp     cs:ServiceStatus.dwCurrentState, 3
0x18000621e  mov     eax, 45Bh
0x180006223  cmovz   edi, eax
0x180006226  jmp     short loc_18000622D
0x180006228  call    ?InitiateStop@@YAXXZ; InitiateStop(void)
0x18000622d  mov     rbx, [rsp+28h+arg_0]
0x180006232  mov     eax, edi
0x180006234  add     rsp, 20h
0x180006238  pop     rdi
0x180006239  retn
```
