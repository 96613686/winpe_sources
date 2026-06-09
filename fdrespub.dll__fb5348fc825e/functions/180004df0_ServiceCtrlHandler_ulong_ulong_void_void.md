# ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180004df0`
- end: `0x180004f1b`
- name: `?ServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `299`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180004770`
- `0x180004df0`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004edc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004edc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004eaa`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004eca`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004eaa`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004eca`

## pseudocode

```c
__int64 __fastcall ServiceCtrlHandler(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  int v4; // ebx
  DWORD v6; // edi
  DWORD v7; // edi
  DWORD v8; // edi
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx

  v4 = dwEventType;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
  v6 = dwControl - 1;
  if ( !v6 )
    goto LABEL_19;
  v7 = v6 - 3;
  if ( !v7 )
  {
    SetServiceStatus(hServiceStatus, &ServiceStatus);
    goto LABEL_21;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( v8 != 8 )
      goto LABEL_21;
    if ( v4 )
    {
      v9 = v4 - 2;
      if ( !v9 )
      {
LABEL_14:
        if ( g_pPublisher )
          (*(void (__fastcall **)(CResourcePublisher *, _QWORD, LPVOID, LPVOID))(*(_QWORD *)g_pPublisher + 8LL))(
            g_pPublisher,
            0,
            lpEventData,
            lpContext);
        goto LABEL_21;
      }
      v10 = v9 - 2;
      if ( v10 )
      {
        v11 = v10 - 2;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( v12 != 11 )
              goto LABEL_21;
          }
        }
        goto LABEL_14;
      }
    }
    if ( g_pPublisher )
      (*(void (__fastcall **)(CResourcePublisher *, __int64, LPVOID, LPVOID))(*(_QWORD *)g_pPublisher + 24LL))(
        g_pPublisher,
        dwEventType,
        lpEventData,
        lpContext);
  }
  else
  {
LABEL_19:
    ServiceStatus.dwCurrentState = 3;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
    if ( g_hShutdownEvent )
      SetEvent(g_hShutdownEvent);
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180004df0  mov     [rsp+arg_0], rbx
0x180004df5  mov     [rsp+arg_8], rsi
0x180004dfa  push    rdi
0x180004dfb  sub     rsp, 20h
0x180004dff  mov     ebx, edx
0x180004e01  mov     edi, ecx
0x180004e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e0a  lea     rsi, WPP_GLOBAL_Control
0x180004e11  cmp     rcx, rsi
0x180004e14  jz      short loc_180004E31
0x180004e16  cmp     byte ptr [rcx+19h], 4
0x180004e1a  jb      short loc_180004E31
0x180004e1c  mov     rcx, [rcx+10h]
0x180004e20  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180004e27  mov     edx, 0Ch
0x180004e2c  call    WPP_SF_s
0x180004e31  sub     edi, 1
0x180004e34  jz      short loc_180004EB2
0x180004e36  sub     edi, 3
0x180004e39  jz      short loc_180004E9C
0x180004e3b  sub     edi, 1
0x180004e3e  jz      short loc_180004EB2
0x180004e40  cmp     edi, 8
0x180004e43  jnz     loc_180004EE2
0x180004e49  test    ebx, ebx
0x180004e4b  jz      short loc_180004E82
0x180004e4d  sub     ebx, 2
0x180004e50  jz      short loc_180004E66
0x180004e52  sub     ebx, 2
0x180004e55  jz      short loc_180004E82
0x180004e57  sub     ebx, 2
0x180004e5a  jz      short loc_180004E66
0x180004e5c  sub     ebx, 1
0x180004e5f  jz      short loc_180004E66
0x180004e61  cmp     ebx, 0Bh
0x180004e64  jnz     short loc_180004EE2
0x180004e66  mov     rcx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004e6d  test    rcx, rcx
0x180004e70  jz      short loc_180004EE2
0x180004e72  mov     rax, [rcx]
0x180004e75  xor     edx, edx
0x180004e77  mov     rax, [rax+8]
0x180004e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e80  jmp     short loc_180004EE2
0x180004e82  mov     rcx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004e89  test    rcx, rcx
0x180004e8c  jz      short loc_180004EE2
0x180004e8e  mov     rax, [rcx]
0x180004e91  mov     rax, [rax+18h]
0x180004e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e9a  jmp     short loc_180004EE2
0x180004e9c  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180004ea3  lea     rdx, ServiceStatus; lpServiceStatus
0x180004eaa  call    cs:__imp_SetServiceStatus
0x180004eb0  jmp     short loc_180004EE2
0x180004eb2  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180004eb9  lea     rdx, ServiceStatus; lpServiceStatus
0x180004ec0  mov     cs:ServiceStatus.dwCurrentState, 3
0x180004eca  call    cs:__imp_SetServiceStatus
0x180004ed0  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hEvent
0x180004ed7  test    rcx, rcx
0x180004eda  jz      short loc_180004EE2
0x180004edc  call    cs:__imp_SetEvent
0x180004ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ee9  cmp     rcx, rsi
0x180004eec  jz      short loc_180004F09
0x180004eee  cmp     byte ptr [rcx+19h], 4
0x180004ef2  jb      short loc_180004F09
0x180004ef4  mov     rcx, [rcx+10h]
0x180004ef8  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180004eff  mov     edx, 0Dh
0x180004f04  call    WPP_SF_s
0x180004f09  mov     rbx, [rsp+28h+arg_0]
0x180004f0e  xor     eax, eax
0x180004f10  mov     rsi, [rsp+28h+arg_8]
0x180004f15  add     rsp, 20h
0x180004f19  pop     rdi
0x180004f1a  retn
```
