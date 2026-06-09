# NGENService::CorServiceControlHandlerEx(ulong,ulong,void *,void *)

- ea: `0x18001a880`
- end: `0x18001a98f`
- name: `?CorServiceControlHandlerEx@NGENService@@YAKKKPEAX0@Z`
- size: `271`
- prototype: `__int64 __fastcall(NGENService *this, __int64, __int64, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18001a790`
- `0x18001a880`
- `0x18002e1d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001a8aa`
- `KERNEL32!EnterCriticalSection` at `0x18001a8c2`
- `KERNEL32!EnterCriticalSection` at `0x18001a8aa`
- `KERNEL32!EnterCriticalSection` at `0x18001a8c2`
- `KERNEL32!LeaveCriticalSection` at `0x18001a8d6`
- `KERNEL32!LeaveCriticalSection` at `0x18001a938`
- `KERNEL32!LeaveCriticalSection` at `0x18001a8d6`
- `KERNEL32!LeaveCriticalSection` at `0x18001a938`
- `KERNEL32!SetEvent` at `0x18001a92e`
- `KERNEL32!SetEvent` at `0x18001a92e`

## string_xrefs

- `0x18001a90a`: `Shutdown notification. Will stop the service.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NGENService::CorServiceControlHandlerEx(NGENService *this, __int64 a2, __int64 a3, void *a4)
{
  int v4; // ebx
  unsigned int v5; // edi
  DWORD dwCurrentState; // esi
  const unsigned __int16 *v7; // rdx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  HANDLE v12; // rcx

  v4 = (int)this;
  v5 = 0;
  EnterCriticalSection(&NGENService::g_UpdateServiceCS);
  EnterCriticalSection(&NGENService::g_UpdateServiceCS);
  dwCurrentState = NGENService::g_ServiceStatus.dwCurrentState;
  LeaveCriticalSection(&NGENService::g_UpdateServiceCS);
  if ( ((dwCurrentState - 1) & 0xFFFFFFFD) != 0 )
  {
    v8 = v4 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( !v9 )
      {
        if ( dwCurrentState != 4 )
          goto LABEL_12;
        NGENService::ServiceUpdateState((NGENService *)6, (unsigned int)v7);
        NGENService::g_bPauseRequested = 1;
        goto LABEL_10;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        if ( dwCurrentState != 7 )
          goto LABEL_12;
        NGENService::ServiceUpdateState((NGENService *)5, (unsigned int)v7);
        v12 = NGENService::g_hRestartEvent;
        goto LABEL_11;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        NGENService::ServiceUpdateState((NGENService *)NGENService::g_ServiceStatus.dwCurrentState, (unsigned int)v7);
        goto LABEL_12;
      }
      if ( v11 != 1 )
      {
        v5 = 120;
        goto LABEL_12;
      }
      NGENService::DebugLog((NGENService *)L"Shutdown notification. Will stop the service.\n", v7);
    }
    NGENService::ServiceUpdateState((NGENService *)3, (unsigned int)v7);
    NGENService::g_bStopRequested = 1;
LABEL_10:
    v12 = NGENService::g_hSCMRequestEvent;
LABEL_11:
    SetEvent(v12);
  }
LABEL_12:
  LeaveCriticalSection(&NGENService::g_UpdateServiceCS);
  return v5;
}

```

## disassembly

```asm
0x18001a880  mov     rax, rsp
0x18001a883  mov     [rax+8], rbx
0x18001a887  mov     [rax+10h], rbp
0x18001a88b  mov     [rax+18h], rsi
0x18001a88f  push    rdi
0x18001a890  sub     rsp, 40h
0x18001a894  mov     ebx, ecx
0x18001a896  lea     rbp, ?g_UpdateServiceCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_UpdateServiceCS
0x18001a89d  mov     [rax-28h], rbp
0x18001a8a1  xor     edi, edi
0x18001a8a3  mov     [rax-20h], dil
0x18001a8a7  mov     rcx, rbp; lpCriticalSection
0x18001a8aa  call    cs:__imp_EnterCriticalSection
0x18001a8b0  mov     [rsp+48h+var_20], 1
0x18001a8b5  mov     [rsp+48h+var_18], rbp
0x18001a8ba  mov     [rsp+48h+var_10], dil
0x18001a8bf  mov     rcx, rbp; lpCriticalSection
0x18001a8c2  call    cs:__imp_EnterCriticalSection
0x18001a8c8  mov     [rsp+48h+var_10], 1
0x18001a8cd  mov     esi, cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001a8d3  mov     rcx, rbp; lpCriticalSection
0x18001a8d6  call    cs:__imp_LeaveCriticalSection
0x18001a8dc  lea     eax, [rsi-1]
0x18001a8df  test    eax, 0FFFFFFFDh
0x18001a8e4  jz      short loc_18001A935
0x18001a8e6  sub     ebx, 1
0x18001a8e9  jz      short loc_18001A916
0x18001a8eb  sub     ebx, 1
0x18001a8ee  jz      loc_18001A978
0x18001a8f4  sub     ebx, 1
0x18001a8f7  jz      short loc_18001A962
0x18001a8f9  sub     ebx, 1
0x18001a8fc  jz      short loc_18001A955
0x18001a8fe  cmp     ebx, 1
0x18001a901  jz      short loc_18001A90A
0x18001a903  mov     edi, 78h ; 'x'
0x18001a908  jmp     short loc_18001A935
0x18001a90a  lea     rcx, aShutdownNotifi; "Shutdown notification. Will stop the se"...
0x18001a911  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001a916  mov     ecx, 3; this
0x18001a91b  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001a920  mov     cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A, 1; Volatile<bool> NGENService::g_bStopRequested
0x18001a927  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hEvent
0x18001a92e  call    cs:__imp_SetEvent
0x18001a934  nop
0x18001a935  mov     rcx, rbp; lpCriticalSection
0x18001a938  call    cs:__imp_LeaveCriticalSection
0x18001a93e  mov     eax, edi
0x18001a940  mov     rbx, [rsp+48h+arg_0]
0x18001a945  mov     rbp, [rsp+48h+arg_8]
0x18001a94a  mov     rsi, [rsp+48h+arg_10]
0x18001a94f  add     rsp, 40h
0x18001a953  pop     rdi
0x18001a954  retn
0x18001a955  mov     ecx, cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwCurrentState; this
0x18001a95b  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001a960  jmp     short loc_18001A935
0x18001a962  cmp     esi, 7
0x18001a965  jnz     short loc_18001A935
0x18001a967  lea     ecx, [rsi-2]; this
0x18001a96a  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001a96f  mov     rcx, cs:?g_hRestartEvent@NGENService@@3PEAXEA; void * NGENService::g_hRestartEvent
0x18001a976  jmp     short loc_18001A92E
0x18001a978  cmp     esi, 4
0x18001a97b  jnz     short loc_18001A935
0x18001a97d  lea     ecx, [rsi+2]; this
0x18001a980  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001a985  mov     cs:?g_bPauseRequested@NGENService@@3V?$Volatile@_N@@A, 1; Volatile<bool> NGENService::g_bPauseRequested
0x18001a98c  jmp     short loc_18001A927
```
