# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x18000a9f0`
- end: `0x18000aa0e`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009594`
- `0x18000a65c`
- `0x1800128b0`
- `0x18001317c`
- `0x180014504`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a9fc`
- `KERNEL32!EnterCriticalSection` at `0x18000a9fc`

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
0x18000a9f0  push    rbx
0x18000a9f2  sub     rsp, 20h
0x18000a9f6  mov     rbx, rcx
0x18000a9f9  mov     rcx, [rcx]; lpCriticalSection
0x18000a9fc  call    cs:__imp_EnterCriticalSection
0x18000aa02  xor     eax, eax
0x18000aa04  mov     byte ptr [rbx+8], 1
0x18000aa08  add     rsp, 20h
0x18000aa0c  pop     rbx
0x18000aa0d  retn
```
