# CmOpenKey(RegEntry const &,ulong)

- ea: `0x180023350`
- end: `0x1800233b4`
- name: `?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `100`
- prototype: `HKEY __fastcall(const struct RegEntry *, REGSAM samDesired)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800237d4`
- `0x180023874`
- `0x18002395c`

## callees

- `0x180023350`
- `0x18002392c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180023387`
- `ADVAPI32!RegOpenKeyExW` at `0x180023387`

## pseudocode

```c
HKEY __fastcall CmOpenKey(const struct RegEntry *a1, REGSAM samDesired)
{
  HKEY v3; // rcx
  int v4; // eax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  v3 = (HKEY)qword_18003D930;
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
0x180023350  push    rbx
0x180023352  sub     rsp, 30h
0x180023356  mov     rbx, rcx
0x180023359  mov     [rsp+38h+arg_0], 0
0x180023362  mov     rcx, cs:qword_18003D930
0x180023369  lea     rax, [rsp+38h+arg_0]
0x18002336e  mov     r9d, edx; samDesired
0x180023371  mov     [rsp+38h+phkResult], rax; phkResult
0x180023376  cmp     qword ptr [rbx+20h], 0
0x18002337b  mov     rdx, [rbx+8]; lpSubKey
0x18002337f  cmovnz  rcx, [rbx+20h]; hKey
0x180023384  xor     r8d, r8d; ulOptions
0x180023387  call    cs:__imp_RegOpenKeyExW
0x18002338d  test    eax, eax
0x18002338f  jz      short loc_1800233A9
0x180023391  jle     short loc_18002339B
0x180023393  movzx   eax, ax
0x180023396  or      eax, 80070000h
0x18002339b  mov     edx, eax; int
0x18002339d  mov     rcx, rbx; struct RegEntry *
0x1800233a0  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x1800233a5  xor     eax, eax
0x1800233a7  jmp     short loc_1800233AE
0x1800233a9  mov     rax, [rsp+38h+arg_0]
0x1800233ae  add     rsp, 30h
0x1800233b2  pop     rbx
0x1800233b3  retn
```
