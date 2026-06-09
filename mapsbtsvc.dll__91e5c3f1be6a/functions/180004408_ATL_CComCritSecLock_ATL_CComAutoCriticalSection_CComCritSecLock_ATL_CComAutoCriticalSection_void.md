# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x180004408`
- end: `0x18000442a`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004940`
- `0x180005000`
- `0x180005070`
- `0x1800051b0`
- `0x180005354`
- `0x1800056d0`
- `0x180005820`
- `0x18000bb70`
- `0x18000c348`
- `0x18000c4dc`
- `0x18000d77c`
- `0x18000f308`
- `0x18000f49c`
- `0x180013cca`
- `0x180013d00`
- `0x180013d36`
- `0x18001440c`

## callees

- `0x180004408`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000441a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000441a`

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
0x180004408  push    rbx
0x18000440a  sub     rsp, 20h
0x18000440e  cmp     byte ptr [rcx+8], 0
0x180004412  mov     rbx, rcx
0x180004415  jz      short loc_180004424
0x180004417  mov     rcx, [rcx]; lpCriticalSection
0x18000441a  call    cs:__imp_LeaveCriticalSection
0x180004420  mov     byte ptr [rbx+8], 0
0x180004424  add     rsp, 20h
0x180004428  pop     rbx
0x180004429  retn
```
