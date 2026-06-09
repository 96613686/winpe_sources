# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180008884`
- end: `0x1800088a6`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009594`
- `0x18000a65c`
- `0x1800128b0`
- `0x18001317c`
- `0x180014504`
- `0x18001ad2e`

## callees

- `0x180008884`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008896`
- `KERNEL32!LeaveCriticalSection` at `0x180008896`

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
0x180008884  push    rbx
0x180008886  sub     rsp, 20h
0x18000888a  cmp     byte ptr [rcx+8], 0
0x18000888e  mov     rbx, rcx
0x180008891  jz      short loc_1800088A0
0x180008893  mov     rcx, [rcx]; lpCriticalSection
0x180008896  call    cs:__imp_LeaveCriticalSection
0x18000889c  mov     byte ptr [rbx+8], 0
0x1800088a0  add     rsp, 20h
0x1800088a4  pop     rbx
0x1800088a5  retn
```
