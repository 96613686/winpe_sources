# IPSecSPDControlHandler

- ea: `0x180007430`
- end: `0x1800074e5`
- name: `IPSecSPDControlHandler`
- size: `181`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180007430`
- `0x180007550`
- `0x18000f638`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800074a8`
- `ntdll!EtwEventWrite` at `0x1800074a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800074d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800074d8`

## pseudocode

```c
__int64 __fastcall IPSecSPDControlHandler(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx
  HANDLE v7; // rcx
  __int64 v8; // rcx

  v4 = dwControl - 1;
  if ( v4 && (v5 = v4 - 4) != 0 )
  {
    v6 = v5 - 124;
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_a32c2c4e5faf34c58819a7bd7d93bf0d_Traceguids);
      v7 = ghNewLocalPolicyEvent;
      goto LABEL_14;
    }
    if ( v6 == 1 )
    {
      v7 = ghForcedPolicyReloadEvent;
LABEL_14:
      SetEvent(v7);
    }
  }
  else
  {
    v8 = g_Provider;
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_SVC_Stop_Begin, 0, 0);
    if ( IPSecSPDStatus.dwCurrentState != 3 )
    {
      IPSecSPDStatus.dwCurrentState = 3;
      *(_QWORD *)&IPSecSPDStatus.dwCheckPoint = 1;
      IPSecSPDUpdateStatus(v8, dwEventType, lpEventData, lpContext);
      v7 = ghServiceStopEvent;
      goto LABEL_14;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007430  sub     rsp, 28h
0x180007434  sub     ecx, 1
0x180007437  jz      short loc_18000748F
0x180007439  sub     ecx, 4
0x18000743c  jz      short loc_18000748F
0x18000743e  sub     ecx, 7Ch ; '|'
0x180007441  jz      short loc_180007458
0x180007443  cmp     ecx, 1
0x180007446  jnz     loc_1800074DE
0x18000744c  mov     rcx, cs:ghForcedPolicyReloadEvent
0x180007453  jmp     loc_1800074D8
0x180007458  mov     rcx, cs:WPP_GLOBAL_Control
0x18000745f  lea     rax, WPP_GLOBAL_Control
0x180007466  cmp     rcx, rax
0x180007469  jz      short loc_180007486
0x18000746b  test    byte ptr [rcx+1Ch], 4
0x18000746f  jz      short loc_180007486
0x180007471  mov     rcx, [rcx+10h]
0x180007475  lea     r8, WPP_a32c2c4e5faf34c58819a7bd7d93bf0d_Traceguids
0x18000747c  mov     edx, 13h
0x180007481  call    WPP_SF_
0x180007486  mov     rcx, cs:ghNewLocalPolicyEvent
0x18000748d  jmp     short loc_1800074D8
0x18000748f  mov     rcx, cs:g_Provider
0x180007496  test    rcx, rcx
0x180007499  jz      short loc_1800074AE
0x18000749b  xor     r9d, r9d
0x18000749e  lea     rdx, IPSEC_SVC_Stop_Begin
0x1800074a5  xor     r8d, r8d
0x1800074a8  call    cs:__imp_EtwEventWrite
0x1800074ae  cmp     cs:IPSecSPDStatus.dwCurrentState, 3
0x1800074b5  jz      short loc_1800074DE
0x1800074b7  mov     cs:IPSecSPDStatus.dwCurrentState, 3
0x1800074c1  mov     qword ptr cs:IPSecSPDStatus.dwCheckPoint, 1
0x1800074cc  call    IPSecSPDUpdateStatus
0x1800074d1  mov     rcx, cs:ghServiceStopEvent; hEvent
0x1800074d8  call    cs:__imp_SetEvent
0x1800074de  xor     eax, eax
0x1800074e0  add     rsp, 28h
0x1800074e4  retn
```
