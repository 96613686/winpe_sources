# MadcapInitGlobalData

- ea: `0x180038740`
- end: `0x180038816`
- name: `MadcapInitGlobalData`
- size: `214`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180036d60`

## callees

- `0x18001cef0`
- `0x18001d826`
- `0x180038740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800387d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800387d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800387f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800387f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038774`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038774`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003879a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003879a`
- `WS2_32!__imp_WSAStartup` at `0x1800387c0`
- `WS2_32!__imp_WSAStartup` at `0x1800387c0`

## pseudocode

```c
__int64 MadcapInitGlobalData()
{
  DWORD LastError; // ebx
  struct WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  EnterCriticalSection(&MadcapGlobalScopeListCritSect);
  if ( MadcapGlobalInitialized )
  {
    ++MadcapGlobalInitialized;
LABEL_8:
    LastError = 0;
    goto LABEL_9;
  }
  gMScopeQueryEvent = CreateEventW(0, 1, 0, 0);
  if ( gMScopeQueryEvent )
  {
    LastError = WSAStartup(0x101u, &WSAData);
    if ( !LastError )
    {
      ++MadcapGlobalInitialized;
      goto LABEL_8;
    }
    CloseHandle(gMScopeQueryEvent);
    gMScopeQueryEvent = 0;
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_9:
  LeaveCriticalSection(&MadcapGlobalScopeListCritSect);
  return LastError;
}

```

## disassembly

```asm
0x180038740  push    rbx
0x180038742  sub     rsp, 1D0h
0x180038749  mov     rax, cs:__security_cookie
0x180038750  xor     rax, rsp
0x180038753  mov     [rsp+1D8h+var_18], rax
0x18003875b  xor     edx, edx; Val
0x18003875d  lea     rcx, [rsp+1D8h+WSAData]; void *
0x180038762  mov     r8d, 198h; Size
0x180038768  call    memset_0
0x18003876d  lea     rcx, MadcapGlobalScopeListCritSect; lpCriticalSection
0x180038774  call    cs:__imp_EnterCriticalSection
0x18003877a  mov     eax, cs:MadcapGlobalInitialized
0x180038780  test    eax, eax
0x180038782  jz      short loc_18003878E
0x180038784  inc     eax
0x180038786  mov     cs:MadcapGlobalInitialized, eax
0x18003878c  jmp     short loc_1800387EC
0x18003878e  xor     r9d, r9d; lpName
0x180038791  xor     r8d, r8d; bInitialState
0x180038794  xor     ecx, ecx; lpEventAttributes
0x180038796  lea     edx, [r9+1]; bManualReset
0x18003879a  call    cs:__imp_CreateEventW
0x1800387a0  mov     cs:gMScopeQueryEvent, rax
0x1800387a7  test    rax, rax
0x1800387aa  jnz     short loc_1800387B6
0x1800387ac  call    cs:__imp_GetLastError
0x1800387b2  mov     ebx, eax
0x1800387b4  jmp     short loc_1800387EE
0x1800387b6  mov     ecx, 101h; wVersionRequested
0x1800387bb  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x1800387c0  call    cs:__imp_WSAStartup
0x1800387c6  mov     ebx, eax
0x1800387c8  test    eax, eax
0x1800387ca  jz      short loc_1800387E6
0x1800387cc  mov     rcx, cs:gMScopeQueryEvent; hObject
0x1800387d3  call    cs:__imp_CloseHandle
0x1800387d9  mov     cs:gMScopeQueryEvent, 0
0x1800387e4  jmp     short loc_1800387EE
0x1800387e6  inc     cs:MadcapGlobalInitialized
0x1800387ec  xor     ebx, ebx
0x1800387ee  lea     rcx, MadcapGlobalScopeListCritSect; lpCriticalSection
0x1800387f5  call    cs:__imp_LeaveCriticalSection
0x1800387fb  mov     eax, ebx
0x1800387fd  mov     rcx, [rsp+1D8h+var_18]
0x180038805  xor     rcx, rsp; StackCookie
0x180038808  call    __security_check_cookie
0x18003880d  add     rsp, 1D0h
0x180038814  pop     rbx
0x180038815  retn
```
