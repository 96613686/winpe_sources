# DeleteFromLocalDatabase

- ea: `0x14000b4a0`
- end: `0x14000b510`
- name: `DeleteFromLocalDatabase`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140014fc0`

## callees

- `0x140003280`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000b4f2`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000b4f2`

## string_xrefs

- `0x14000b4e1`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall DeleteFromLocalDatabase(__int64 a1, __int64 a2)
{
  _QWORD v5[15]; // [rsp+30h] [rbp-78h] BYREF

  memset(v5, 0, 0x70u);
  v5[0] = DeleteFromLocalDatabaseRoutine;
  v5[2] = *(_QWORD *)(a1 + 8);
  return RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v5, a2, 0);
}

```

## disassembly

```asm
0x14000b4a0  mov     [rsp+arg_0], rbx
0x14000b4a5  push    rdi
0x14000b4a6  sub     rsp, 0A0h
0x14000b4ad  mov     rdi, rdx
0x14000b4b0  mov     rbx, rcx
0x14000b4b3  xor     edx, edx; Val
0x14000b4b5  lea     rcx, [rsp+0A8h+var_78]; void *
0x14000b4ba  lea     r8d, [rdx+70h]; Size
0x14000b4be  call    memset
0x14000b4c3  lea     rax, DeleteFromLocalDatabaseRoutine
0x14000b4ca  mov     [rsp+0A8h+var_88], 0
0x14000b4d3  mov     [rsp+0A8h+var_78], rax
0x14000b4d8  lea     r8, [rsp+0A8h+var_78]
0x14000b4dd  mov     rax, [rbx+8]
0x14000b4e1  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000b4e8  mov     r9, rdi
0x14000b4eb  mov     [rsp+0A8h+var_68], rax
0x14000b4f0  xor     ecx, ecx
0x14000b4f2  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000b4f9  nop     dword ptr [rax+rax+00h]
0x14000b4fe  mov     rbx, [rsp+0A8h+arg_0]
0x14000b506  add     rsp, 0A0h
0x14000b50d  pop     rdi
0x14000b50e  retn
```
