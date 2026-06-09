# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800133d4`
- end: `0x1800133f6`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013ce4`
- `0x1800152d0`
- `0x180023ce0`
- `0x180023dd0`
- `0x180023ec0`
- `0x18003efc5`

## callees

- `0x1800133d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133e6`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(__int64 a1)
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
0x1800133d4  push    rbx
0x1800133d6  sub     rsp, 20h
0x1800133da  mov     rbx, rcx
0x1800133dd  cmp     byte ptr [rcx+8], 0
0x1800133e1  jz      short loc_1800133F0
0x1800133e3  mov     rcx, [rcx]; lpCriticalSection
0x1800133e6  call    cs:__imp_LeaveCriticalSection
0x1800133ec  mov     byte ptr [rbx+8], 0
0x1800133f0  add     rsp, 20h
0x1800133f4  pop     rbx
0x1800133f5  retn
```
