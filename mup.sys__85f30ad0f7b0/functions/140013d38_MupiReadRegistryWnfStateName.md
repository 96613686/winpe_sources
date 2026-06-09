# MupiReadRegistryWnfStateName

- ea: `0x140013d38`
- end: `0x140013d8b`
- name: `MupiReadRegistryWnfStateName`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400138d4`

## callees

- `0x140013c54`
- `0x140013d38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013d71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d71`

## pseudocode

```c
char __fastcall MupiReadRegistryWnfStateName(void *a1, const WCHAR *a2, _QWORD *a3)
{
  char v4; // bl
  _DWORD *RegistryValue; // rax

  v4 = 0;
  RegistryValue = MupiReadRegistryValue(a1, a2);
  if ( RegistryValue )
  {
    if ( RegistryValue[1] == 3 && RegistryValue[3] == 8 )
    {
      v4 = 1;
      *a3 = *(_QWORD *)((char *)RegistryValue + (unsigned int)RegistryValue[2]);
    }
    ExFreePoolWithTag(RegistryValue, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x140013d38  mov     [rsp+arg_0], rbx
0x140013d3d  push    rdi
0x140013d3e  sub     rsp, 20h
0x140013d42  mov     rdi, r8
0x140013d45  xor     bl, bl
0x140013d47  call    MupiReadRegistryValue
0x140013d4c  mov     r9, rax
0x140013d4f  test    rax, rax
0x140013d52  jz      short loc_140013D7D
0x140013d54  cmp     dword ptr [rax+4], 3
0x140013d58  jnz     short loc_140013D6C
0x140013d5a  cmp     dword ptr [rax+0Ch], 8
0x140013d5e  jnz     short loc_140013D6C
0x140013d60  mov     eax, [rax+8]
0x140013d63  mov     bl, 1
0x140013d65  mov     rcx, [rax+r9]
0x140013d69  mov     [rdi], rcx
0x140013d6c  xor     edx, edx; Tag
0x140013d6e  mov     rcx, r9; P
0x140013d71  call    cs:__imp_ExFreePoolWithTag
0x140013d78  nop     dword ptr [rax+rax+00h]
0x140013d7d  mov     al, bl
0x140013d7f  mov     rbx, [rsp+28h+arg_0]
0x140013d84  add     rsp, 20h
0x140013d88  pop     rdi
0x140013d89  retn
```
