# CmOpenKey(RegEntry const &,ulong)

- ea: `0x14000ef84`
- end: `0x14000efe8`
- name: `?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `100`
- prototype: `HKEY __fastcall(const struct RegEntry *, REGSAM samDesired)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f444`
- `0x14000f4e4`
- `0x14000f64c`
- `0x1400115c8`
- `0x140011f54`
- `0x140015dc8`

## callees

- `0x14000ef84`
- `0x14000f61c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000efbb`
- `ADVAPI32!RegOpenKeyExW` at `0x14000efbb`

## pseudocode

```c
HKEY __fastcall CmOpenKey(const struct RegEntry *a1, REGSAM samDesired)
{
  HKEY v3; // rcx
  int v4; // eax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  v3 = (HKEY)qword_14002AF40;
  if ( *((_QWORD *)a1 + 4) )
    v3 = (HKEY)*((_QWORD *)a1 + 4);
  v4 = RegOpenKeyExW(v3, *((LPCWSTR *)a1 + 1), 0, samDesired, &phkResult);
  if ( !v4 )
    return phkResult;
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  ThrowMissingValue(a1, v4);
  return 0;
}

```

## disassembly

```asm
0x14000ef84  push    rbx
0x14000ef86  sub     rsp, 30h
0x14000ef8a  mov     rbx, rcx
0x14000ef8d  mov     [rsp+38h+arg_0], 0
0x14000ef96  mov     rcx, cs:qword_14002AF40
0x14000ef9d  lea     rax, [rsp+38h+arg_0]
0x14000efa2  mov     r9d, edx; samDesired
0x14000efa5  mov     [rsp+38h+phkResult], rax; phkResult
0x14000efaa  cmp     qword ptr [rbx+20h], 0
0x14000efaf  mov     rdx, [rbx+8]; lpSubKey
0x14000efb3  cmovnz  rcx, [rbx+20h]; hKey
0x14000efb8  xor     r8d, r8d; ulOptions
0x14000efbb  call    cs:__imp_RegOpenKeyExW
0x14000efc1  test    eax, eax
0x14000efc3  jz      short loc_14000EFDD
0x14000efc5  jle     short loc_14000EFCF
0x14000efc7  movzx   eax, ax
0x14000efca  or      eax, 80070000h
0x14000efcf  mov     edx, eax; int
0x14000efd1  mov     rcx, rbx; struct RegEntry *
0x14000efd4  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x14000efd9  xor     eax, eax
0x14000efdb  jmp     short loc_14000EFE2
0x14000efdd  mov     rax, [rsp+38h+arg_0]
0x14000efe2  add     rsp, 30h
0x14000efe6  pop     rbx
0x14000efe7  retn
```
