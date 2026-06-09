# CmOpenKey(RegEntry const &,ulong)

- ea: `0x1800150b8`
- end: `0x18001511c`
- name: `?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `100`
- prototype: `HKEY __fastcall(const struct RegEntry *, REGSAM samDesired)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b760`
- `0x180012770`
- `0x18001557c`
- `0x18001561c`
- `0x180015778`
- `0x180016b50`
- `0x180016d90`
- `0x180019230`
- `0x180019b4c`
- `0x18001a15c`

## callees

- `0x1800150b8`
- `0x180015748`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800150ef`
- `ADVAPI32!RegOpenKeyExW` at `0x1800150ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall CmOpenKey(const struct RegEntry *a1, REGSAM samDesired)
{
  HKEY v3; // rcx
  int v4; // eax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  v3 = (HKEY)qword_18002D0F0;
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
0x1800150b8  push    rbx
0x1800150ba  sub     rsp, 30h
0x1800150be  mov     rbx, rcx
0x1800150c1  mov     [rsp+38h+arg_0], 0
0x1800150ca  mov     rcx, cs:qword_18002D0F0
0x1800150d1  lea     rax, [rsp+38h+arg_0]
0x1800150d6  mov     r9d, edx; samDesired
0x1800150d9  mov     [rsp+38h+phkResult], rax; phkResult
0x1800150de  cmp     qword ptr [rbx+20h], 0
0x1800150e3  mov     rdx, [rbx+8]; lpSubKey
0x1800150e7  cmovnz  rcx, [rbx+20h]; hKey
0x1800150ec  xor     r8d, r8d; ulOptions
0x1800150ef  call    cs:__imp_RegOpenKeyExW
0x1800150f5  test    eax, eax
0x1800150f7  jz      short loc_180015111
0x1800150f9  jle     short loc_180015103
0x1800150fb  movzx   eax, ax
0x1800150fe  or      eax, 80070000h
0x180015103  mov     edx, eax; int
0x180015105  mov     rcx, rbx; struct RegEntry *
0x180015108  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x18001510d  xor     eax, eax
0x18001510f  jmp     short loc_180015116
0x180015111  mov     rax, [rsp+38h+arg_0]
0x180015116  add     rsp, 30h
0x18001511a  pop     rbx
0x18001511b  retn
```
