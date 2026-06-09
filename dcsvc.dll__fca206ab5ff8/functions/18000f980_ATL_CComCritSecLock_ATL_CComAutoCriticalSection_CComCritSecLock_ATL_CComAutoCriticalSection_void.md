# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x18000f980`
- end: `0x18000f9a2`
- name: `??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011efb`
- `0x180011f33`

## callees

- `0x18000f980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f992`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f992`

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
0x18000f980  push    rbx
0x18000f982  sub     rsp, 20h
0x18000f986  cmp     byte ptr [rcx+8], 0
0x18000f98a  mov     rbx, rcx
0x18000f98d  jz      short loc_18000F99C
0x18000f98f  mov     rcx, [rcx]; lpCriticalSection
0x18000f992  call    cs:__imp_LeaveCriticalSection
0x18000f998  mov     byte ptr [rbx+8], 0
0x18000f99c  add     rsp, 20h
0x18000f9a0  pop     rbx
0x18000f9a1  retn
```
