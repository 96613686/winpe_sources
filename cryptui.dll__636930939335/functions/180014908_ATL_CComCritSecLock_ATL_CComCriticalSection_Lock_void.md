# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x180014908`
- end: `0x180014926`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013ce4`
- `0x1800152d0`
- `0x180023ce0`
- `0x180023dd0`
- `0x180023ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014914`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014914`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(__int64 a1)
{
  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  *(_BYTE *)(a1 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180014908  push    rbx
0x18001490a  sub     rsp, 20h
0x18001490e  mov     rbx, rcx
0x180014911  mov     rcx, [rcx]; lpCriticalSection
0x180014914  call    cs:__imp_EnterCriticalSection
0x18001491a  mov     byte ptr [rbx+8], 1
0x18001491e  xor     eax, eax
0x180014920  add     rsp, 20h
0x180014924  pop     rbx
0x180014925  retn
```
