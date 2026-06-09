# UpdateStatus

- ea: `0x18000a0b0`
- end: `0x18000a124`
- name: `UpdateStatus`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180003fb0`
- `0x180009cc0`
- `0x180009cf0`
- `0x180009ee0`
- `0x1800165a0`

## callees

- `0x18000a0b0`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a10f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a10f`

## string_xrefs

- `0x18000a0c5`: `Updating service status to %d\n`

## pseudocode

```c
bool __fastcall UpdateStatus(DWORD a1)
{
  if ( !hService )
    return 0;
  DsRolepLogPrintRoutine(4, "Updating service status to %d\n", a1);
  DsRoleServiceStatus.dwCurrentState = a1;
  if ( a1 - 2 <= 1 )
  {
    ++DsRoleServiceStatus.dwCheckPoint;
    DsRoleServiceStatus.dwWaitHint = 10000;
  }
  else
  {
    *(_QWORD *)&DsRoleServiceStatus.dwCheckPoint = 0;
  }
  return SetServiceStatus(hService, &DsRoleServiceStatus);
}

```

## disassembly

```asm
0x18000a0b0  push    rbx
0x18000a0b2  sub     rsp, 20h
0x18000a0b6  cmp     cs:hService, 0
0x18000a0be  mov     ebx, ecx
0x18000a0c0  jz      short loc_18000A11C
0x18000a0c2  mov     r8d, ecx
0x18000a0c5  lea     rdx, aUpdatingServic; "Updating service status to %d\n"
0x18000a0cc  mov     ecx, 4
0x18000a0d1  call    DsRolepLogPrintRoutine
0x18000a0d6  lea     eax, [rbx-2]
0x18000a0d9  mov     cs:DsRoleServiceStatus.dwCurrentState, ebx
0x18000a0df  cmp     eax, 1
0x18000a0e2  jbe     short loc_18000A0F1
0x18000a0e4  mov     qword ptr cs:DsRoleServiceStatus.dwCheckPoint, 0
0x18000a0ef  jmp     short loc_18000A101
0x18000a0f1  inc     cs:DsRoleServiceStatus.dwCheckPoint
0x18000a0f7  mov     cs:DsRoleServiceStatus.dwWaitHint, 2710h
0x18000a101  mov     rcx, cs:hService; hServiceStatus
0x18000a108  lea     rdx, DsRoleServiceStatus; lpServiceStatus
0x18000a10f  call    cs:__imp_SetServiceStatus
0x18000a115  test    eax, eax
0x18000a117  setnz   al
0x18000a11a  jmp     short loc_18000A11E
0x18000a11c  xor     al, al
0x18000a11e  add     rsp, 20h
0x18000a122  pop     rbx
0x18000a123  retn
```
