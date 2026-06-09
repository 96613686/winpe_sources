# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x18000d678`
- end: `0x18000d69a`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800188ea`

## callees

- `0x18000d678`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d68a`
- `KERNEL32!LeaveCriticalSection` at `0x18000d68a`

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
0x18000d678  push    rbx
0x18000d67a  sub     rsp, 20h
0x18000d67e  cmp     byte ptr [rcx+8], 0
0x18000d682  mov     rbx, rcx
0x18000d685  jz      short loc_18000D694
0x18000d687  mov     rcx, [rcx]; lpCriticalSection
0x18000d68a  call    cs:__imp_LeaveCriticalSection
0x18000d690  mov     byte ptr [rbx+8], 0
0x18000d694  add     rsp, 20h
0x18000d698  pop     rbx
0x18000d699  retn
```
