# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180002cb0`
- end: `0x180002cd2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002db8`

## callees

- `0x180002cb0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002cc2`
- `KERNEL32!LeaveCriticalSection` at `0x180002cc2`

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
0x180002cb0  push    rbx
0x180002cb2  sub     rsp, 20h
0x180002cb6  cmp     byte ptr [rcx+8], 0
0x180002cba  mov     rbx, rcx
0x180002cbd  jz      short loc_180002CCC
0x180002cbf  mov     rcx, [rcx]; lpCriticalSection
0x180002cc2  call    cs:__imp_LeaveCriticalSection
0x180002cc8  mov     byte ptr [rbx+8], 0
0x180002ccc  add     rsp, 20h
0x180002cd0  pop     rbx
0x180002cd1  retn
```
