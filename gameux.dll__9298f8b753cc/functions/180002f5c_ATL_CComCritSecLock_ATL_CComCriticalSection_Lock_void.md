# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x180002f5c`
- end: `0x180002f7a`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002db8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002f68`
- `KERNEL32!EnterCriticalSection` at `0x180002f68`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(__int64 a1)
{
  __int64 result; // rax

  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  result = 0;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x180002f5c  push    rbx
0x180002f5e  sub     rsp, 20h
0x180002f62  mov     rbx, rcx
0x180002f65  mov     rcx, [rcx]; lpCriticalSection
0x180002f68  call    cs:__imp_EnterCriticalSection
0x180002f6e  xor     eax, eax
0x180002f70  mov     byte ptr [rbx+8], 1
0x180002f74  add     rsp, 20h
0x180002f78  pop     rbx
0x180002f79  retn
```
