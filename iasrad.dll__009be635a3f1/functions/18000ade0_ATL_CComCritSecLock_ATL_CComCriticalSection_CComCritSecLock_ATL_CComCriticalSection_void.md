# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x18000ade0`
- end: `0x18000ae02`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000af20`
- `0x18000b1d4`
- `0x18000efac`
- `0x180010118`
- `0x18002e829`

## callees

- `0x18000ade0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000adf2`
- `KERNEL32!LeaveCriticalSection` at `0x18000adf2`

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
0x18000ade0  push    rbx
0x18000ade2  sub     rsp, 20h
0x18000ade6  cmp     byte ptr [rcx+8], 0
0x18000adea  mov     rbx, rcx
0x18000aded  jz      short loc_18000ADFC
0x18000adef  mov     rcx, [rcx]; lpCriticalSection
0x18000adf2  call    cs:__imp_LeaveCriticalSection
0x18000adf8  mov     byte ptr [rbx+8], 0
0x18000adfc  add     rsp, 20h
0x18000ae00  pop     rbx
0x18000ae01  retn
```
