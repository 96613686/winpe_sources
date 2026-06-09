# DnsShutdownWinsock

- ea: `0x18000edd0`
- end: `0x18000ee55`
- name: `DnsShutdownWinsock`
- size: `133`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d1bc`
- `0x18000dfb8`
- `0x18001e740`
- `0x180039e64`
- `0x180079dd4`
- `0x18007b280`
- `0x18009f000`
- `0x1800a3b74`

## callees

- `0x18000edd0`
- `0x180083954`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eddd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edff`
- `WS2_32!__imp_WSACleanup` at `0x18000ee1d`
- `WS2_32!__imp_WSACleanup` at `0x18000ee1d`

## pseudocode

```c
void DnsShutdownWinsock()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx

  EnterCriticalSection(&g_csWinsock);
  v0 = g_dwWinsockRefCount--;
  LeaveCriticalSection(&g_csWinsock);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 13, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids, v0);
  if ( v0 )
  {
    if ( v0 == 1 )
      WSACleanup();
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v1);
  }
}

```

## disassembly

```asm
0x18000edd0  push    rbx
0x18000edd2  sub     rsp, 20h
0x18000edd6  lea     rcx, g_csWinsock; lpCriticalSection
0x18000eddd  call    cs:__imp_EnterCriticalSection
0x18000ede4  nop     dword ptr [rax+rax+00h]
0x18000ede9  mov     ebx, cs:g_dwWinsockRefCount
0x18000edef  lea     rcx, g_csWinsock; lpCriticalSection
0x18000edf6  lea     eax, [rbx-1]
0x18000edf9  mov     cs:g_dwWinsockRefCount, eax
0x18000edff  call    cs:__imp_LeaveCriticalSection
0x18000ee06  nop     dword ptr [rax+rax+00h]
0x18000ee0b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000ee12  jnz     short loc_18000EE30
0x18000ee14  test    ebx, ebx
0x18000ee16  jz      short loc_18000EE4B
0x18000ee18  cmp     ebx, 1
0x18000ee1b  jnz     short loc_18000EE29
0x18000ee1d  call    cs:__imp_WSACleanup
0x18000ee24  nop     dword ptr [rax+rax+00h]
0x18000ee29  add     rsp, 20h
0x18000ee2d  pop     rbx
0x18000ee2e  retn
0x18000ee30  mov     edx, 0Dh
0x18000ee35  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18000ee3c  mov     ecx, 40Bh
0x18000ee41  mov     r9d, ebx
0x18000ee44  call    WPP_SF_d
0x18000ee49  jmp     short loc_18000EE14
0x18000ee4b  add     rsp, 20h
0x18000ee4f  pop     rbx
0x18000ee50  jmp     MicrosoftTelemetryAssertTriggeredNoArgs
```
