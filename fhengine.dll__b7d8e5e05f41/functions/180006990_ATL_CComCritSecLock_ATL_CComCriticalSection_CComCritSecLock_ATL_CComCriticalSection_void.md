# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180006990`
- end: `0x1800069b2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006a30`
- `0x180026814`

## callees

- `0x180006990`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800069a2`
- `KERNEL32!LeaveCriticalSection` at `0x1800069a2`

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
0x180006990  push    rbx
0x180006992  sub     rsp, 20h
0x180006996  cmp     byte ptr [rcx+8], 0
0x18000699a  mov     rbx, rcx
0x18000699d  jz      short loc_1800069AC
0x18000699f  mov     rcx, [rcx]; lpCriticalSection
0x1800069a2  call    cs:__imp_LeaveCriticalSection
0x1800069a8  mov     byte ptr [rbx+8], 0
0x1800069ac  add     rsp, 20h
0x1800069b0  pop     rbx
0x1800069b1  retn
```
