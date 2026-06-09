# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800117f0`
- end: `0x180011812`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011850`

## callees

- `0x1800117f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180011802`
- `KERNEL32!LeaveCriticalSection` at `0x180011802`

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
0x1800117f0  push    rbx
0x1800117f2  sub     rsp, 20h
0x1800117f6  cmp     byte ptr [rcx+8], 0
0x1800117fa  mov     rbx, rcx
0x1800117fd  jz      short loc_18001180C
0x1800117ff  mov     rcx, [rcx]; lpCriticalSection
0x180011802  call    cs:__imp_LeaveCriticalSection
0x180011808  mov     byte ptr [rbx+8], 0
0x18001180c  add     rsp, 20h
0x180011810  pop     rbx
0x180011811  retn
```
