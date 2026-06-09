# CIISGlobalModule::Terminate(void)

- ea: `0x180002c00`
- end: `0x180002c36`
- name: `?Terminate@CIISGlobalModule@@UEAAXXZ`
- size: `54`
- prototype: `void __fastcall(CIISGlobalModule *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180002c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c19`

## pseudocode

```c
void __fastcall CIISGlobalModule::Terminate(CIISGlobalModule *this)
{
  if ( IIS_REQMON_CONTEXT::sm_fInitializedcsRequestList )
  {
    DeleteCriticalSection(&IIS_REQMON_CONTEXT::sm_csRequestList);
    IIS_REQMON_CONTEXT::sm_fInitializedcsRequestList = 0;
  }
  operator delete(this);
}

```

## disassembly

```asm
0x180002c00  push    rbx
0x180002c02  sub     rsp, 20h
0x180002c06  cmp     cs:?sm_fInitializedcsRequestList@IIS_REQMON_CONTEXT@@0HA, 0; int IIS_REQMON_CONTEXT::sm_fInitializedcsRequestList
0x180002c0d  mov     rbx, rcx
0x180002c10  jz      short loc_180002C29
0x180002c12  lea     rcx, ?sm_csRequestList@IIS_REQMON_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002c19  call    cs:__imp_DeleteCriticalSection
0x180002c1f  mov     cs:?sm_fInitializedcsRequestList@IIS_REQMON_CONTEXT@@0HA, 0; int IIS_REQMON_CONTEXT::sm_fInitializedcsRequestList
0x180002c29  mov     rcx, rbx; Block
0x180002c2c  add     rsp, 20h
0x180002c30  pop     rbx
0x180002c31  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
