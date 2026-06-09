# IASInitialize

- ea: `0x18000c070`
- end: `0x18000c19e`
- name: `IASInitialize`
- size: `302`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000c070`
- `0x1800175cc`
- `0x1800181a2`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c0b8`
- `KERNEL32!SetLastError` at `0x18000c10c`
- `KERNEL32!SetLastError` at `0x18000c12a`
- `KERNEL32!SetLastError` at `0x18000c0b8`
- `KERNEL32!SetLastError` at `0x18000c10c`
- `KERNEL32!SetLastError` at `0x18000c12a`
- `KERNEL32!EnterCriticalSection` at `0x18000c0a4`
- `KERNEL32!EnterCriticalSection` at `0x18000c0a4`
- `KERNEL32!LeaveCriticalSection` at `0x18000c166`
- `KERNEL32!LeaveCriticalSection` at `0x18000c17d`
- `KERNEL32!LeaveCriticalSection` at `0x18000c166`
- `KERNEL32!LeaveCriticalSection` at `0x18000c17d`
- `WS2_32!__imp_WSAStartup` at `0x18000c11e`
- `WS2_32!__imp_WSAStartup` at `0x18000c11e`
- `WS2_32!__imp_WSACleanup` at `0x18000c13b`
- `WS2_32!__imp_WSACleanup` at `0x18000c13b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c100`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c100`

## pseudocode

```c
__int64 IASInitialize()
{
  unsigned int v0; // ebx
  HRESULT Instance; // eax
  DWORD v2; // eax
  Dispatcher *v3; // rcx
  WSAData WSAData; // [rsp+30h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  EnterCriticalSection(&theGlobalLock);
  if ( shutdownInProgress )
  {
    SetLastError(0x45Bu);
    v0 = 0;
  }
  else
  {
    v0 = 1;
    if ( refCount <= 0 )
    {
      Instance = CoCreateInstance(
                   &GUID_6bc0969d_0ce6_11d1_baae_00c04fc2e20d,
                   0,
                   1u,
                   &GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d,
                   &pAuditChannel);
      if ( Instance >= 0 )
      {
        v2 = WSAStartup(2u, &WSAData);
        if ( v2 )
        {
          SetLastError(v2);
        }
        else
        {
          if ( (unsigned int)Dispatcher::initialize(v3) )
          {
            ++refCount;
            goto LABEL_14;
          }
          WSACleanup();
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pAuditChannel + 16LL))(pAuditChannel);
        pAuditChannel = 0;
      }
      else
      {
        SetLastError(Instance);
      }
      LeaveCriticalSection(&theGlobalLock);
      return 0;
    }
    ++refCount;
  }
LABEL_14:
  LeaveCriticalSection(&theGlobalLock);
  return v0;
}

```

## disassembly

```asm
0x18000c070  push    rbx
0x18000c072  sub     rsp, 1E0h
0x18000c079  mov     rax, cs:__security_cookie
0x18000c080  xor     rax, rsp
0x18000c083  mov     [rsp+1E8h+var_18], rax
0x18000c08b  xor     edx, edx; Val
0x18000c08d  lea     rcx, [rsp+1E8h+WSAData]; void *
0x18000c092  mov     r8d, 198h; Size
0x18000c098  call    memset_0
0x18000c09d  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c0a4  call    cs:__imp_EnterCriticalSection
0x18000c0aa  cmp     cs:?shutdownInProgress@@3HA, 0; int shutdownInProgress
0x18000c0b1  jz      short loc_18000C0C5
0x18000c0b3  mov     ecx, 45Bh; dwErrCode
0x18000c0b8  call    cs:__imp_SetLastError
0x18000c0be  xor     ebx, ebx
0x18000c0c0  jmp     loc_18000C176
0x18000c0c5  mov     eax, cs:?refCount@@3JA; long refCount
0x18000c0cb  mov     ebx, 1
0x18000c0d0  test    eax, eax
0x18000c0d2  jle     short loc_18000C0E1
0x18000c0d4  add     eax, ebx
0x18000c0d6  mov     cs:?refCount@@3JA, eax; long refCount
0x18000c0dc  jmp     loc_18000C176
0x18000c0e1  lea     rax, ?pAuditChannel@@3PEAUIAuditSink@@EA; IAuditSink * pAuditChannel
0x18000c0e8  mov     r8d, ebx; dwClsContext
0x18000c0eb  lea     r9, _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d; riid
0x18000c0f2  mov     [rsp+1E8h+ppv], rax; ppv
0x18000c0f7  xor     edx, edx; pUnkOuter
0x18000c0f9  lea     rcx, _GUID_6bc0969d_0ce6_11d1_baae_00c04fc2e20d; rclsid
0x18000c100  call    cs:__imp_CoCreateInstance
0x18000c106  test    eax, eax
0x18000c108  jns     short loc_18000C114
0x18000c10a  mov     ecx, eax; dwErrCode
0x18000c10c  call    cs:__imp_SetLastError
0x18000c112  jmp     short loc_18000C15F
0x18000c114  mov     ecx, 2; wVersionRequested
0x18000c119  lea     rdx, [rsp+1E8h+WSAData]; lpWSAData
0x18000c11e  call    cs:__imp_WSAStartup
0x18000c124  test    eax, eax
0x18000c126  jz      short loc_18000C132
0x18000c128  mov     ecx, eax; dwErrCode
0x18000c12a  call    cs:__imp_SetLastError
0x18000c130  jmp     short loc_18000C141
0x18000c132  call    ?initialize@Dispatcher@@QEAAHKK@Z; Dispatcher::initialize(ulong,ulong)
0x18000c137  test    eax, eax
0x18000c139  jnz     short loc_18000C170
0x18000c13b  call    cs:__imp_WSACleanup
0x18000c141  mov     rcx, cs:?pAuditChannel@@3PEAUIAuditSink@@EA; IAuditSink * pAuditChannel
0x18000c148  mov     rax, [rcx]
0x18000c14b  mov     rax, [rax+10h]
0x18000c14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c154  mov     cs:?pAuditChannel@@3PEAUIAuditSink@@EA, 0; IAuditSink * pAuditChannel
0x18000c15f  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c166  call    cs:__imp_LeaveCriticalSection
0x18000c16c  xor     eax, eax
0x18000c16e  jmp     short loc_18000C185
0x18000c170  add     cs:?refCount@@3JA, ebx; long refCount
0x18000c176  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c17d  call    cs:__imp_LeaveCriticalSection
0x18000c183  mov     eax, ebx
0x18000c185  mov     rcx, [rsp+1E8h+var_18]
0x18000c18d  xor     rcx, rsp; StackCookie
0x18000c190  call    __security_check_cookie
0x18000c195  add     rsp, 1E0h
0x18000c19c  pop     rbx
0x18000c19d  retn
```
