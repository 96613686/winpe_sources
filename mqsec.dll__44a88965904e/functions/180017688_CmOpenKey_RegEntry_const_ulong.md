# CmOpenKey(RegEntry const &,ulong)

- ea: `0x180017688`
- end: `0x1800176ec`
- name: `?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `100`
- prototype: `HKEY __fastcall(const struct RegEntry *, REGSAM samDesired)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001786c`
- `0x1800178f4`
- `0x1800179e0`
- `0x18002dfd8`

## callees

- `0x180017688`
- `0x1800179b0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800176bf`
- `ADVAPI32!RegOpenKeyExW` at `0x1800176bf`

## pseudocode

```c
HKEY __fastcall CmOpenKey(const struct RegEntry *a1, REGSAM samDesired)
{
  HKEY v3; // rcx
  int v4; // eax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  v3 = (HKEY)qword_180042D30;
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
0x180017688  push    rbx
0x18001768a  sub     rsp, 30h
0x18001768e  mov     rbx, rcx
0x180017691  mov     [rsp+38h+arg_0], 0
0x18001769a  mov     rcx, cs:qword_180042D30
0x1800176a1  lea     rax, [rsp+38h+arg_0]
0x1800176a6  mov     r9d, edx; samDesired
0x1800176a9  mov     [rsp+38h+phkResult], rax; phkResult
0x1800176ae  cmp     qword ptr [rbx+20h], 0
0x1800176b3  mov     rdx, [rbx+8]; lpSubKey
0x1800176b7  cmovnz  rcx, [rbx+20h]; hKey
0x1800176bc  xor     r8d, r8d; ulOptions
0x1800176bf  call    cs:__imp_RegOpenKeyExW
0x1800176c5  test    eax, eax
0x1800176c7  jz      short loc_1800176E1
0x1800176c9  jle     short loc_1800176D3
0x1800176cb  movzx   eax, ax
0x1800176ce  or      eax, 80070000h
0x1800176d3  mov     edx, eax; int
0x1800176d5  mov     rcx, rbx; struct RegEntry *
0x1800176d8  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x1800176dd  xor     eax, eax
0x1800176df  jmp     short loc_1800176E6
0x1800176e1  mov     rax, [rsp+38h+arg_0]
0x1800176e6  add     rsp, 30h
0x1800176ea  pop     rbx
0x1800176eb  retn
```
