# ScPolicyCancelMonitorThread

- ea: `0x18001ae78`
- end: `0x18001aed8`
- name: `ScPolicyCancelMonitorThread`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b278`
- `0x18001b808`

## callees

- `0x18001ae78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aebc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aebc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aea0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aea0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001ae92`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001ae92`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001aec2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001aec2`
- `WinSCard!SCardCancel` at `0x18001aeb2`
- `WinSCard!SCardCancel` at `0x18001aeb2`

## pseudocode

```c
BOOL __fastcall ScPolicyCancelMonitorThread(__int64 a1, int a2)
{
  BOOL result; // eax
  SCARDCONTEXT v5; // rcx

  result = SetThreadToken(0, *(HANDLE *)(a1 + 56));
  if ( result )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    v5 = *(_QWORD *)(a1 + 80);
    *(_DWORD *)(a1 + 72) = a2;
    if ( v5 )
      SCardCancel(v5);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    return RevertToSelf();
  }
  return result;
}

```

## disassembly

```asm
0x18001ae78  mov     [rsp+arg_0], rbx
0x18001ae7d  mov     [rsp+arg_8], rsi
0x18001ae82  push    rdi
0x18001ae83  sub     rsp, 20h
0x18001ae87  mov     esi, edx
0x18001ae89  mov     rbx, rcx
0x18001ae8c  mov     rdx, [rcx+38h]; Token
0x18001ae90  xor     ecx, ecx; Thread
0x18001ae92  call    cs:__imp_SetThreadToken
0x18001ae98  test    eax, eax
0x18001ae9a  jz      short loc_18001AEC8
0x18001ae9c  lea     rcx, [rbx+8]; lpCriticalSection
0x18001aea0  call    cs:__imp_EnterCriticalSection
0x18001aea6  mov     rcx, [rbx+50h]; hContext
0x18001aeaa  mov     [rbx+48h], esi
0x18001aead  test    rcx, rcx
0x18001aeb0  jz      short loc_18001AEB8
0x18001aeb2  call    cs:__imp_SCardCancel
0x18001aeb8  lea     rcx, [rbx+8]; lpCriticalSection
0x18001aebc  call    cs:__imp_LeaveCriticalSection
0x18001aec2  call    cs:__imp_RevertToSelf
0x18001aec8  mov     rbx, [rsp+28h+arg_0]
0x18001aecd  mov     rsi, [rsp+28h+arg_8]
0x18001aed2  add     rsp, 20h
0x18001aed6  pop     rdi
0x18001aed7  retn
```
