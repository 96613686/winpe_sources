# IsDisallowedCertAutoUpdateEnabled

- ea: `0x18000cab4`
- end: `0x18000cb0a`
- name: `IsDisallowedCertAutoUpdateEnabled`
- size: `86`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180004530`
- `0x180005700`

## import_xrefs

- `CRYPT32!I_CertSrvProtectFunction` at `0x18000caf6`
- `CRYPT32!I_CertSrvProtectFunction` at `0x18000caf6`

## pseudocode

```c
_BOOL8 IsDisallowedCertAutoUpdateEnabled()
{
  return (unsigned int)I_CertSrvProtectFunction(0) == 0;
}

```

## disassembly

```asm
0x18000cab4  mov     rax, rsp
0x18000cab7  sub     rsp, 58h
0x18000cabb  mov     qword ptr [rax-10h], 0
0x18000cac3  xor     r9d, r9d
0x18000cac6  mov     qword ptr [rax-18h], 0
0x18000cace  xor     r8d, r8d
0x18000cad1  mov     qword ptr [rax-20h], 0
0x18000cad9  xor     ecx, ecx
0x18000cadb  mov     qword ptr [rax-28h], 0
0x18000cae3  mov     dword ptr [rax-30h], 0
0x18000caea  lea     edx, [r9+0Eh]
0x18000caee  mov     qword ptr [rax-38h], 0
0x18000caf6  call    cs:__imp_I_CertSrvProtectFunction
0x18000cafc  xor     ecx, ecx
0x18000cafe  test    eax, eax
0x18000cb00  setz    cl
0x18000cb03  mov     eax, ecx
0x18000cb05  add     rsp, 58h
0x18000cb09  retn
```
