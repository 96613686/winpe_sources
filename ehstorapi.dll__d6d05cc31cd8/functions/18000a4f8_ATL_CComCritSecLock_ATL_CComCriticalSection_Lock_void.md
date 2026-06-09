# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x18000a4f8`
- end: `0x18000a516`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009834`
- `0x18000a21c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a504`
- `KERNEL32!EnterCriticalSection` at `0x18000a504`

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
0x18000a4f8  push    rbx
0x18000a4fa  sub     rsp, 20h
0x18000a4fe  mov     rbx, rcx
0x18000a501  mov     rcx, [rcx]; lpCriticalSection
0x18000a504  call    cs:__imp_EnterCriticalSection
0x18000a50a  xor     eax, eax
0x18000a50c  mov     byte ptr [rbx+8], 1
0x18000a510  add     rsp, 20h
0x18000a514  pop     rbx
0x18000a515  retn
```
