# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180002b9c`
- end: `0x180002bbe`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000431c`
- `0x1800047a0`
- `0x18000652c`
- `0x18000680c`
- `0x18002ba12`

## callees

- `0x180002b9c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002bae`
- `KERNEL32!LeaveCriticalSection` at `0x180002bae`

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
0x180002b9c  push    rbx
0x180002b9e  sub     rsp, 20h
0x180002ba2  cmp     byte ptr [rcx+8], 0
0x180002ba6  mov     rbx, rcx
0x180002ba9  jz      short loc_180002BB8
0x180002bab  mov     rcx, [rcx]; lpCriticalSection
0x180002bae  call    cs:__imp_LeaveCriticalSection
0x180002bb4  mov     byte ptr [rbx+8], 0
0x180002bb8  add     rsp, 20h
0x180002bbc  pop     rbx
0x180002bbd  retn
```
