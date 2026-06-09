# LsaDbpLookupDispatchWorkerThreads(_LSAP_DB_LOOKUP_WORK_LIST *)

- ea: `0x180032e3c`
- end: `0x180032f67`
- name: `?LsaDbpLookupDispatchWorkerThreads@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct _LSAP_DB_LOOKUP_WORK_LIST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b8dc`

## callees

- `0x18000fd40`
- `0x18000fee8`
- `0x180032e3c`
- `0x180033abc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032ef8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032f06`
- `ntdll!RtlLeaveCriticalSection` at `0x180032e89`
- `ntdll!RtlLeaveCriticalSection` at `0x180032f4e`
- `ntdll!RtlLeaveCriticalSection` at `0x180032e89`
- `ntdll!RtlLeaveCriticalSection` at `0x180032f4e`
- `ntdll!RtlEnterCriticalSection` at `0x180032e5a`
- `ntdll!RtlEnterCriticalSection` at `0x180032e5a`
- `ntdll!NtSetEvent` at `0x180032e98`
- `ntdll!NtSetEvent` at `0x180032e98`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupDispatchWorkerThreads(struct _LSAP_DB_LOOKUP_WORK_LIST *a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // edi
  NTSTATUS v4; // eax
  int v5; // esi
  HANDLE v6; // rax
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+68h] [rbp+10h] BYREF

  ThreadId = 0;
  v2 = RtlEnterCriticalSection(&LookupWorkQueue);
  if ( (v2 & 0x80000000) != 0 )
    return v2;
  v3 = *((_DWORD *)a1 + 24);
  if ( !v3 )
  {
    RtlLeaveCriticalSection(&LookupWorkQueue);
LABEL_15:
    LsaDbpLookupWorkerThread(a1);
    return v2;
  }
  if ( v3 > dword_180048254 - dword_180048250 )
    v3 = dword_180048254 - dword_180048250;
  RtlLeaveCriticalSection(&LookupWorkQueue);
  v4 = NtSetEvent(LsaDbpLookupStartedEvent, 0);
  v2 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    if ( v3 )
    {
      while ( 1 )
      {
        v6 = CreateThread(0, 0, LsaDbpLookupWorkerThreadStart, 0, 0, &ThreadId);
        if ( !v6 )
          break;
        CloseHandle(v6);
        if ( ++v5 >= v3 )
          goto LABEL_15;
      }
      LastError = GetLastError();
      v2 = -1073741670;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids,
          LastError,
          -1073741670);
    }
    goto LABEL_15;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids,
      (unsigned int)v4);
  return v2;
}

```

## disassembly

```asm
0x180032e3c  push    rbx
0x180032e3e  push    rbp
0x180032e3f  push    rsi
0x180032e40  push    rdi
0x180032e41  sub     rsp, 38h
0x180032e45  mov     rbp, rcx
0x180032e48  mov     [rsp+58h+ThreadId], 0
0x180032e50  lea     rsi, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; _LSAP_DB_LOOKUP_WORK_QUEUE LookupWorkQueue
0x180032e57  mov     rcx, rsi; CriticalSection
0x180032e5a  call    cs:__imp_RtlEnterCriticalSection
0x180032e60  mov     ebx, eax
0x180032e62  test    eax, eax
0x180032e64  js      loc_180032F5C
0x180032e6a  mov     edi, [rbp+60h]
0x180032e6d  mov     rcx, rsi; CriticalSection
0x180032e70  test    edi, edi
0x180032e72  jz      loc_180032F4E
0x180032e78  mov     eax, cs:dword_180048254
0x180032e7e  sub     eax, cs:dword_180048250
0x180032e84  cmp     edi, eax
0x180032e86  cmova   edi, eax
0x180032e89  call    cs:__imp_RtlLeaveCriticalSection
0x180032e8f  mov     rcx, cs:?LsaDbpLookupStartedEvent@@3PEAXEA; EventHandle
0x180032e96  xor     edx, edx; PreviousState
0x180032e98  call    cs:__imp_NtSetEvent
0x180032e9e  mov     ebx, eax
0x180032ea0  test    eax, eax
0x180032ea2  jns     short loc_180032ED2
0x180032ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180032eab  test    byte ptr [rcx+1Ch], 20h
0x180032eaf  jz      loc_180032F5C
0x180032eb5  mov     rcx, [rcx+10h]
0x180032eb9  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x180032ec0  mov     edx, 0Ah
0x180032ec5  mov     r9d, eax
0x180032ec8  call    WPP_SF_d
0x180032ecd  jmp     loc_180032F5C
0x180032ed2  xor     esi, esi
0x180032ed4  test    edi, edi
0x180032ed6  jz      short loc_180032F54
0x180032ed8  lea     rax, [rsp+58h+ThreadId]
0x180032edd  xor     r9d, r9d; lpParameter
0x180032ee0  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180032ee5  lea     r8, ?LsaDbpLookupWorkerThreadStart@@YAXXZ; lpStartAddress
0x180032eec  xor     edx, edx; dwStackSize
0x180032eee  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180032ef6  xor     ecx, ecx; lpThreadAttributes
0x180032ef8  call    cs:__imp_CreateThread
0x180032efe  test    rax, rax
0x180032f01  jz      short loc_180032F14
0x180032f03  mov     rcx, rax; hObject
0x180032f06  call    cs:__imp_CloseHandle
0x180032f0c  inc     esi
0x180032f0e  cmp     esi, edi
0x180032f10  jb      short loc_180032ED8
0x180032f12  jmp     short loc_180032F54
0x180032f14  call    cs:__imp_GetLastError
0x180032f1a  mov     ebx, 0C000009Ah
0x180032f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f26  test    byte ptr [rcx+1Ch], 20h
0x180032f2a  jz      short loc_180032F54
0x180032f2c  mov     rcx, [rcx+10h]
0x180032f30  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x180032f37  mov     edx, 0Bh
0x180032f3c  mov     [rsp+58h+dwCreationFlags], 0C000009Ah
0x180032f44  mov     r9d, eax
0x180032f47  call    WPP_SF_dd
0x180032f4c  jmp     short loc_180032F54
0x180032f4e  call    cs:__imp_RtlLeaveCriticalSection
0x180032f54  mov     rcx, rbp; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x180032f57  call    ?LsaDbpLookupWorkerThread@@YAXPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupWorkerThread(_LSAP_DB_LOOKUP_WORK_LIST *)
0x180032f5c  mov     eax, ebx
0x180032f5e  add     rsp, 38h
0x180032f62  pop     rdi
0x180032f63  pop     rsi
0x180032f64  pop     rbp
0x180032f65  pop     rbx
0x180032f66  retn
```
