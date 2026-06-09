# DusmSvc::~DusmSvc(void)

- ea: `0x180016830`
- end: `0x18001685f`
- name: `??1DusmSvc@@AEAA@XZ`
- size: `47`
- prototype: `void __fastcall(DusmSvc *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016dc8`

## callees

- `0x180016830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016858`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016842`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016842`

## pseudocode

```c
void __fastcall DusmSvc::~DusmSvc(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
  {
    FreeSid(DebugInfo);
    this[1].DebugInfo = 0;
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180016830  push    rbx
0x180016832  sub     rsp, 20h
0x180016836  mov     rbx, rcx
0x180016839  mov     rcx, [rcx+28h]; pSid
0x18001683d  test    rcx, rcx
0x180016840  jz      short loc_180016850
0x180016842  call    cs:__imp_FreeSid
0x180016848  mov     qword ptr [rbx+28h], 0
0x180016850  mov     rcx, rbx
0x180016853  add     rsp, 20h
0x180016857  pop     rbx
0x180016858  jmp     cs:__imp_DeleteCriticalSection
```
