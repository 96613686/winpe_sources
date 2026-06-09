# ServiceHandler

- ea: `0x180002b30`
- end: `0x180002bb0`
- name: `ServiceHandler`
- size: `128`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800023d0`
- `0x180002b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002ba3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002ba3`
- `LocationFramework!SvcOnConsoleSessionNotification` at `0x180002b7d`
- `LocationFramework!SvcOnConsoleSessionNotification` at `0x180002b7d`
- `LocationFramework!SvcOnUserLogOnStateNotification` at `0x180002b61`
- `LocationFramework!SvcOnUserLogOnStateNotification` at `0x180002b61`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx

  v4 = dwControl - 1;
  if ( v4 )
  {
    v5 = v4 - 13;
    if ( v5 )
    {
      if ( v5 == 19 && dwEventType - 5 <= 1 && lpEventData )
        SvcOnUserLogOnStateNotification(dwEventType, *((_DWORD *)lpEventData + 1), *((_QWORD *)lpEventData + 1));
    }
    else if ( dwEventType - 1 <= 3 && lpEventData )
    {
      SvcOnConsoleSessionNotification(dwEventType, *((_DWORD *)lpEventData + 1));
    }
  }
  else
  {
    SvcEngUpdateServiceStatus(3u, 0, 0x2710u);
    if ( hObject )
      SetEvent(hObject);
  }
  return 0;
}

```

## disassembly

```asm
0x180002b30  sub     rsp, 28h
0x180002b34  mov     r9, r8
0x180002b37  mov     r10d, edx
0x180002b3a  sub     ecx, 1
0x180002b3d  jz      short loc_180002B85
0x180002b3f  sub     ecx, 0Dh
0x180002b42  jz      short loc_180002B69
0x180002b44  cmp     ecx, 13h
0x180002b47  jnz     short loc_180002BA9
0x180002b49  lea     eax, [rdx-5]
0x180002b4c  cmp     eax, 1
0x180002b4f  ja      short loc_180002BA9
0x180002b51  test    r8, r8
0x180002b54  jz      short loc_180002BA9
0x180002b56  mov     r8, [r8+8]
0x180002b5a  mov     ecx, r10d
0x180002b5d  mov     edx, [r9+4]
0x180002b61  call    cs:__imp_?SvcOnUserLogOnStateNotification@@YAJKK_K@Z; SvcOnUserLogOnStateNotification(ulong,ulong,unsigned __int64)
0x180002b67  jmp     short loc_180002BA9
0x180002b69  lea     eax, [rdx-1]
0x180002b6c  cmp     eax, 3
0x180002b6f  ja      short loc_180002BA9
0x180002b71  test    r9, r9
0x180002b74  jz      short loc_180002BA9
0x180002b76  mov     edx, [r8+4]
0x180002b7a  mov     ecx, r10d
0x180002b7d  call    cs:__imp_?SvcOnConsoleSessionNotification@@YAJKK@Z; SvcOnConsoleSessionNotification(ulong,ulong)
0x180002b83  jmp     short loc_180002BA9
0x180002b85  xor     edx, edx; unsigned int
0x180002b87  mov     ecx, 3; unsigned int
0x180002b8c  mov     r8d, 2710h; unsigned int
0x180002b92  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180002b97  mov     rcx, cs:hObject; hEvent
0x180002b9e  test    rcx, rcx
0x180002ba1  jz      short loc_180002BA9
0x180002ba3  call    cs:__imp_SetEvent
0x180002ba9  xor     eax, eax
0x180002bab  add     rsp, 28h
0x180002baf  retn
```
