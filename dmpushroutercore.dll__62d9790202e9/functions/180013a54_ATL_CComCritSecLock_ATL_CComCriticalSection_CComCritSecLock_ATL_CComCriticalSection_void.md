# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180013a54`
- end: `0x180013a76`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038f06`
- `0x180038fc1`
- `0x1800390a3`
- `0x1800390b5`
- `0x1800390c7`
- `0x1800390d9`
- `0x1800390eb`
- `0x1800390fd`
- `0x18003910f`
- `0x180039121`
- `0x180039bcb`

## callees

- `0x180013a54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a66`

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
0x180013a54  push    rbx
0x180013a56  sub     rsp, 20h
0x180013a5a  cmp     byte ptr [rcx+8], 0
0x180013a5e  mov     rbx, rcx
0x180013a61  jz      short loc_180013A70
0x180013a63  mov     rcx, [rcx]; lpCriticalSection
0x180013a66  call    cs:__imp_LeaveCriticalSection
0x180013a6c  mov     byte ptr [rbx+8], 0
0x180013a70  add     rsp, 20h
0x180013a74  pop     rbx
0x180013a75  retn
```
