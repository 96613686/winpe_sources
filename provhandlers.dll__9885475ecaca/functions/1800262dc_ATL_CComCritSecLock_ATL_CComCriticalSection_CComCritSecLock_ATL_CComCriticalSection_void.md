# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800262dc`
- end: `0x1800262fe`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003cdcb`
- `0x18003cf3b`
- `0x18003cfc4`
- `0x18003cfd6`

## callees

- `0x1800262dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800262ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800262ee`

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
0x1800262dc  push    rbx
0x1800262de  sub     rsp, 20h
0x1800262e2  cmp     byte ptr [rcx+8], 0
0x1800262e6  mov     rbx, rcx
0x1800262e9  jz      short loc_1800262F8
0x1800262eb  mov     rcx, [rcx]; lpCriticalSection
0x1800262ee  call    cs:__imp_LeaveCriticalSection
0x1800262f4  mov     byte ptr [rbx+8], 0
0x1800262f8  add     rsp, 20h
0x1800262fc  pop     rbx
0x1800262fd  retn
```
