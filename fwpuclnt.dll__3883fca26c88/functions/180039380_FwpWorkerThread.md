# FwpWorkerThread

- ea: `0x180039380`
- end: `0x180039477`
- name: `FwpWorkerThread`
- size: `247`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000d7a8`
- `0x180038f04`
- `0x1800392e8`
- `0x180039380`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003946a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003946a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800393dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039454`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800393dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039454`
- `WS2_32!__imp_WSACleanup` at `0x180039433`
- `WS2_32!__imp_WSACleanup` at `0x180039433`

## pseudocode

```c
__int64 __fastcall FwpWorkerThread(PVOID Parameter)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  HMODULE v4; // rbx

  FwpStartWSA(Parameter);
  WfpCriticalSectionEnterBusyWait(&gNameCacheState);
  if ( byte_18007C401 )
  {
LABEL_6:
    LeaveCriticalSection(&gNameCacheState);
  }
  else
  {
    while ( 1 )
    {
      v1 = qword_18007C430;
      if ( (__int64 *)qword_18007C430 == &qword_18007C430 )
        break;
      if ( *(__int64 **)(qword_18007C430 + 8) != &qword_18007C430
        || (v2 = *(_QWORD *)qword_18007C430, *(_QWORD *)(*(_QWORD *)qword_18007C430 + 8LL) != qword_18007C430) )
      {
        __fastfail(3u);
      }
      qword_18007C430 = *(_QWORD *)qword_18007C430;
      *(_QWORD *)(v2 + 8) = &qword_18007C430;
      LeaveCriticalSection(&gNameCacheState);
      FwpProcessWorkEntry(v1);
      WfpCriticalSectionEnterBusyWait(&gNameCacheState);
      if ( byte_18007C401 )
        goto LABEL_6;
    }
    word_18007C402 = 1;
    WSACleanup();
    v4 = hLibModule;
    hLibModule = 0;
    LeaveCriticalSection(&gNameCacheState);
    if ( v4 )
      FreeLibraryAndExitThread(v4, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180039380  mov     [rsp+arg_0], rbx
0x180039385  mov     [rsp+arg_8], rbp
0x18003938a  push    rsi
0x18003938b  sub     rsp, 20h
0x18003938f  call    FwpStartWSA
0x180039394  lea     rsi, gNameCacheState
0x18003939b  mov     rcx, rsi
0x18003939e  call    WfpCriticalSectionEnterBusyWait
0x1800393a3  cmp     cs:byte_18007C401, 0
0x1800393aa  jnz     short loc_180039401
0x1800393ac  lea     rbp, qword_18007C430
0x1800393b3  mov     rbx, cs:qword_18007C430
0x1800393ba  cmp     rbx, rbp
0x1800393bd  jz      short loc_18003942A
0x1800393bf  cmp     [rbx+8], rbp
0x1800393c3  jnz     short loc_180039423
0x1800393c5  mov     rax, [rbx]
0x1800393c8  cmp     [rax+8], rbx
0x1800393cc  jnz     short loc_180039423
0x1800393ce  mov     cs:qword_18007C430, rax
0x1800393d5  mov     rcx, rsi; lpCriticalSection
0x1800393d8  mov     [rax+8], rbp
0x1800393dc  call    cs:__imp_LeaveCriticalSection
0x1800393e3  nop     dword ptr [rax+rax+00h]
0x1800393e8  mov     rcx, rbx
0x1800393eb  call    FwpProcessWorkEntry
0x1800393f0  mov     rcx, rsi
0x1800393f3  call    WfpCriticalSectionEnterBusyWait
0x1800393f8  cmp     cs:byte_18007C401, 0
0x1800393ff  jz      short loc_1800393B3
0x180039401  mov     rcx, rsi; lpCriticalSection
0x180039404  call    cs:__imp_LeaveCriticalSection
0x18003940b  nop     dword ptr [rax+rax+00h]
0x180039410  mov     rbx, [rsp+28h+arg_0]
0x180039415  xor     eax, eax
0x180039417  mov     rbp, [rsp+28h+arg_8]
0x18003941c  add     rsp, 20h
0x180039420  pop     rsi
0x180039421  retn
0x180039423  mov     ecx, 3
0x180039428  int     29h; Win8: RtlFailFast(ecx)
0x18003942a  mov     cs:word_18007C402, 1
0x180039433  call    cs:__imp_WSACleanup
0x18003943a  nop     dword ptr [rax+rax+00h]
0x18003943f  mov     rbx, cs:hLibModule
0x180039446  mov     rcx, rsi; lpCriticalSection
0x180039449  mov     cs:hLibModule, 0
0x180039454  call    cs:__imp_LeaveCriticalSection
0x18003945b  nop     dword ptr [rax+rax+00h]
0x180039460  test    rbx, rbx
0x180039463  jz      short loc_180039410
0x180039465  xor     edx, edx; dwExitCode
0x180039467  mov     rcx, rbx; hLibModule
0x18003946a  call    cs:__imp_FreeLibraryAndExitThread
0x180039471  nop     dword ptr [rax+rax+00h]
0x180039476  int     3; Trap to Debugger
```
