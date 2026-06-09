# SocketBrokerTable::Initialize(void)

- ea: `0x180003c7c`
- end: `0x180003cf8`
- name: `?Initialize@SocketBrokerTable@@QEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800039a0`
- `0x180003b60`

## callees

- `0x180003c7c`
- `0x18000a0a0`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x180003cc9`
- `ntdll!RtlCreateHashTable` at `0x180003cc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ca3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ca3`

## string_xrefs

- `0x180003ce4`: `SocketBrokerTable: Failed to create Hash Table for socket broker`

## pseudocode

```c
__int64 __fastcall SocketBrokerTable::Initialize(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  LPCRITICAL_SECTION v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  v2 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( !LOBYTE(lpCriticalSection[2].DebugInfo) )
  {
    v6 = lpCriticalSection + 1;
    if ( (unsigned __int8)RtlCreateHashTable(&v6, 0, 0) )
    {
      LOBYTE(lpCriticalSection[2].DebugInfo) = 1;
    }
    else
    {
      v2 = 8;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v5,
          v4,
          L"SocketBrokerTable: Failed to create Hash Table for socket broker",
          8);
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x180003c7c  mov     [rsp+arg_8], rbx
0x180003c81  push    rdi
0x180003c82  sub     rsp, 20h
0x180003c86  mov     rbx, rcx
0x180003c89  mov     [rsp+28h+arg_0], 0
0x180003c92  xor     edi, edi
0x180003c94  call    cs:__imp_EnterCriticalSection
0x180003c9a  cmp     [rbx+50h], dil
0x180003c9e  jz      short loc_180003CB6
0x180003ca0  mov     rcx, rbx; lpCriticalSection
0x180003ca3  call    cs:__imp_LeaveCriticalSection
0x180003ca9  mov     rbx, [rsp+28h+arg_8]
0x180003cae  mov     eax, edi
0x180003cb0  add     rsp, 20h
0x180003cb4  pop     rdi
0x180003cb5  retn
0x180003cb6  lea     rax, [rbx+28h]
0x180003cba  xor     r8d, r8d
0x180003cbd  xor     edx, edx
0x180003cbf  mov     [rsp+28h+arg_0], rax
0x180003cc4  lea     rcx, [rsp+28h+arg_0]
0x180003cc9  call    cs:__imp_RtlCreateHashTable
0x180003ccf  test    al, al
0x180003cd1  jnz     short loc_180003CF2
0x180003cd3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003cda  mov     edi, 8
0x180003cdf  jz      short loc_180003CA0
0x180003ce1  mov     r9d, edi
0x180003ce4  lea     r8, aSocketbrokerta; "SocketBrokerTable: Failed to create Has"...
0x180003ceb  call    McTemplateU0zq_EventWriteTransfer
0x180003cf0  jmp     short loc_180003CA0
0x180003cf2  mov     byte ptr [rbx+50h], 1
0x180003cf6  jmp     short loc_180003CA0
```
