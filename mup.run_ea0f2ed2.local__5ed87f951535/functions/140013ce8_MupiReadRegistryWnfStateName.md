# MupiReadRegistryWnfStateName

- ea: `0x140013ce8`
- end: `0x140013d3b`
- name: `MupiReadRegistryWnfStateName`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140013884`

## callees

- `0x140013c04`
- `0x140013ce8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013d21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d21`

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
0x140013ce8  mov     [rsp+arg_0], rbx
0x140013ced  push    rdi
0x140013cee  sub     rsp, 20h
0x140013cf2  mov     rdi, r8
0x140013cf5  xor     bl, bl
0x140013cf7  call    MupiReadRegistryValue
0x140013cfc  mov     r9, rax
0x140013cff  test    rax, rax
0x140013d02  jz      short loc_140013D2D
0x140013d04  cmp     dword ptr [rax+4], 3
0x140013d08  jnz     short loc_140013D1C
0x140013d0a  cmp     dword ptr [rax+0Ch], 8
0x140013d0e  jnz     short loc_140013D1C
0x140013d10  mov     eax, [rax+8]
0x140013d13  mov     bl, 1
0x140013d15  mov     rcx, [rax+r9]
0x140013d19  mov     [rdi], rcx
0x140013d1c  xor     edx, edx; Tag
0x140013d1e  mov     rcx, r9; P
0x140013d21  call    cs:__imp_ExFreePoolWithTag
0x140013d28  nop     dword ptr [rax+rax+00h]
0x140013d2d  mov     al, bl
0x140013d2f  mov     rbx, [rsp+28h+arg_0]
0x140013d34  add     rsp, 20h
0x140013d38  pop     rdi
0x140013d39  retn
```
