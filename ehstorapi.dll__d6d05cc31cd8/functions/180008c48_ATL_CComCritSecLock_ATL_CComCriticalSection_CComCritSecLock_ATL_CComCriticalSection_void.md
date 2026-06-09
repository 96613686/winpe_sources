# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180008c48`
- end: `0x180008c6a`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009834`
- `0x18000a21c`

## callees

- `0x180008c48`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008c5a`
- `KERNEL32!LeaveCriticalSection` at `0x180008c5a`

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
0x180008c48  push    rbx
0x180008c4a  sub     rsp, 20h
0x180008c4e  cmp     byte ptr [rcx+8], 0
0x180008c52  mov     rbx, rcx
0x180008c55  jz      short loc_180008C64
0x180008c57  mov     rcx, [rcx]; lpCriticalSection
0x180008c5a  call    cs:__imp_LeaveCriticalSection
0x180008c60  mov     byte ptr [rbx+8], 0
0x180008c64  add     rsp, 20h
0x180008c68  pop     rbx
0x180008c69  retn
```
