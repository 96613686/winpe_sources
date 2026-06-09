# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x18000a320`
- end: `0x18000a342`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cc0f`

## callees

- `0x18000a320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a332`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a332`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
    *(_BYTE *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000a320  push    rbx
0x18000a322  sub     rsp, 20h
0x18000a326  cmp     byte ptr [rcx+8], 0
0x18000a32a  mov     rbx, rcx
0x18000a32d  jz      short loc_18000A33C
0x18000a32f  mov     rcx, [rcx]; lpCriticalSection
0x18000a332  call    cs:__imp_LeaveCriticalSection
0x18000a338  mov     byte ptr [rbx+8], 0
0x18000a33c  add     rsp, 20h
0x18000a340  pop     rbx
0x18000a341  retn
```
