# IsPinRulesAutoUpdateDisabled

- ea: `0x18000a980`
- end: `0x18000a9d6`
- name: `IsPinRulesAutoUpdateDisabled`
- size: `86`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180004530`

## import_xrefs

- `CRYPT32!I_CertSrvProtectFunction` at `0x18000a9c2`
- `CRYPT32!I_CertSrvProtectFunction` at `0x18000a9c2`

## pseudocode

```c
_BOOL8 IsPinRulesAutoUpdateDisabled()
{
  return (unsigned int)I_CertSrvProtectFunction(0) != 0;
}

```

## disassembly

```asm
0x18000a980  mov     rax, rsp
0x18000a983  sub     rsp, 58h
0x18000a987  mov     qword ptr [rax-10h], 0
0x18000a98f  xor     r9d, r9d
0x18000a992  mov     qword ptr [rax-18h], 0
0x18000a99a  xor     r8d, r8d
0x18000a99d  mov     qword ptr [rax-20h], 0
0x18000a9a5  xor     ecx, ecx
0x18000a9a7  mov     qword ptr [rax-28h], 0
0x18000a9af  mov     dword ptr [rax-30h], 0
0x18000a9b6  lea     edx, [r9+0Fh]
0x18000a9ba  mov     qword ptr [rax-38h], 0
0x18000a9c2  call    cs:__imp_I_CertSrvProtectFunction
0x18000a9c8  xor     ecx, ecx
0x18000a9ca  test    eax, eax
0x18000a9cc  setnz   cl
0x18000a9cf  mov     eax, ecx
0x18000a9d1  add     rsp, 58h
0x18000a9d5  retn
```
