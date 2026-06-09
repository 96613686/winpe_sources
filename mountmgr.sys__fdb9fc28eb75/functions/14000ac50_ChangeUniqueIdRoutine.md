# ChangeUniqueIdRoutine

- ea: `0x14000ac50`
- end: `0x14000acd1`
- name: `ChangeUniqueIdRoutine`
- size: `129`
- prototype: `__int64 __usercall@<rax>(PCWSTR ValueName@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000ac50`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x14000acb7`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000acb7`
- `ntoskrnl!RtlCompareMemory` at `0x14000ac7f`
- `ntoskrnl!RtlCompareMemory` at `0x14000ac7f`

## string_xrefs

- `0x14000ac95`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall ChangeUniqueIdRoutine(
        PCWSTR ValueName,
        int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  if ( a2 == 3 && *a5 == a4 && RtlCompareMemory(a5 + 1, a3, a4) == a4 )
    RtlWriteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName, 3u, a6 + 1, *a6);
  return 0;
}

```

## disassembly

```asm
0x14000ac50  mov     [rsp+arg_0], rbx
0x14000ac55  push    rdi
0x14000ac56  sub     rsp, 30h
0x14000ac5a  mov     r10, r8
0x14000ac5d  mov     rdi, rcx
0x14000ac60  cmp     edx, 3
0x14000ac63  jnz     short loc_14000ACC3
0x14000ac65  mov     rcx, [rsp+38h+arg_20]
0x14000ac6a  movzx   eax, word ptr [rcx]
0x14000ac6d  cmp     eax, r9d
0x14000ac70  jnz     short loc_14000ACC3
0x14000ac72  add     rcx, 2; Source1
0x14000ac76  mov     r8d, r9d; Length
0x14000ac79  mov     rdx, r10; Source2
0x14000ac7c  mov     ebx, r9d
0x14000ac7f  call    cs:__imp_RtlCompareMemory
0x14000ac86  nop     dword ptr [rax+rax+00h]
0x14000ac8b  cmp     rax, rbx
0x14000ac8e  jnz     short loc_14000ACC3
0x14000ac90  mov     rax, [rsp+38h+arg_28]
0x14000ac95  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000ac9c  mov     r9d, 3; ValueType
0x14000aca2  mov     r8, rdi; ValueName
0x14000aca5  movzx   ecx, word ptr [rax]
0x14000aca8  add     rax, 2
0x14000acac  mov     [rsp+38h+ValueLength], ecx; ValueLength
0x14000acb0  xor     ecx, ecx; RelativeTo
0x14000acb2  mov     [rsp+38h+ValueData], rax; ValueData
0x14000acb7  call    cs:__imp_RtlWriteRegistryValue
0x14000acbe  nop     dword ptr [rax+rax+00h]
0x14000acc3  mov     rbx, [rsp+38h+arg_0]
0x14000acc8  xor     eax, eax
0x14000acca  add     rsp, 30h
0x14000acce  pop     rdi
0x14000accf  retn
```
