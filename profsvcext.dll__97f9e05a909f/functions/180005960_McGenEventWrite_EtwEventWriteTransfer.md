# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180005960`
- end: `0x1800059b2`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003300`
- `0x180003410`
- `0x180004130`
- `0x180004b00`
- `0x18000637c`
- `0x18000671c`
- `0x180006c1c`
- `0x180008258`
- `0x18000f4b0`
- `0x18000f530`
- `0x180011880`
- `0x180012314`
- `0x180015dbc`
- `0x180016a1c`
- `0x180018a3c`
- `0x180018c78`

## callees

- `0x180005960`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800059a7`
- `ntdll!EtwEventWriteTransfer` at `0x1800059a7`

## pseudocode

```c

```

## disassembly

```asm
0x180005960  sub     rsp, 38h
0x180005964  mov     rcx, cs:qword_18002B048
0x18000596b  mov     rax, [rsp+38h+arg_20]
0x180005970  test    rcx, rcx
0x180005973  jnz     short loc_18000597D
0x180005975  mov     [rax], rcx
0x180005978  xor     r8d, r8d
0x18000597b  jmp     short loc_180005989
0x18000597d  mov     [rax], rcx
0x180005980  mov     r8d, 2
0x180005986  movzx   ecx, word ptr [rcx]
0x180005989  mov     [rax+8], ecx
0x18000598c  mov     [rax+0Ch], r8d
0x180005990  xor     r8d, r8d
0x180005993  mov     rcx, cs:S_Microsoft_Windows_Profsvc_Context
0x18000599a  mov     [rsp+38h+var_10], rax
0x18000599f  mov     [rsp+38h+var_18], r9d
0x1800059a4  xor     r9d, r9d
0x1800059a7  call    cs:__imp_EtwEventWriteTransfer
0x1800059ad  add     rsp, 38h
0x1800059b1  retn
```
