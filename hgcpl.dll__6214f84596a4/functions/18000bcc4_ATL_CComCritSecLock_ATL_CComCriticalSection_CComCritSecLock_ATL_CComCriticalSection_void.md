# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x18000bcc4`
- end: `0x18000bce6`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c678`
- `0x18000cc54`

## callees

- `0x18000bcc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bcd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bcd6`

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
0x18000bcc4  push    rbx
0x18000bcc6  sub     rsp, 20h
0x18000bcca  cmp     byte ptr [rcx+8], 0
0x18000bcce  mov     rbx, rcx
0x18000bcd1  jz      short loc_18000BCE0
0x18000bcd3  mov     rcx, [rcx]; lpCriticalSection
0x18000bcd6  call    cs:__imp_LeaveCriticalSection
0x18000bcdc  mov     byte ptr [rbx+8], 0
0x18000bce0  add     rsp, 20h
0x18000bce4  pop     rbx
0x18000bce5  retn
```
