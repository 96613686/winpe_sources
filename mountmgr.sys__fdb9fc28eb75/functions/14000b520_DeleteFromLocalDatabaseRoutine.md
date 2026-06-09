# DeleteFromLocalDatabaseRoutine

- ea: `0x14000b520`
- end: `0x14000b581`
- name: `DeleteFromLocalDatabaseRoutine`
- size: `97`
- prototype: `__int64 __usercall@<rax>(PCWSTR ValueName@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b520`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000b567`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000b567`
- `ntoskrnl!RtlCompareMemory` at `0x14000b54a`
- `ntoskrnl!RtlCompareMemory` at `0x14000b54a`

## string_xrefs

- `0x14000b55e`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall DeleteFromLocalDatabaseRoutine(
        PCWSTR ValueName,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  if ( *a5 == a4 && RtlCompareMemory(a5 + 1, a3, a4) == a4 )
    RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName);
  return 0;
}

```

## disassembly

```asm
0x14000b520  mov     [rsp+arg_0], rbx
0x14000b525  push    rdi
0x14000b526  sub     rsp, 20h
0x14000b52a  mov     rdi, rcx
0x14000b52d  mov     r10, r8
0x14000b530  mov     rcx, [rsp+28h+arg_20]
0x14000b535  movzx   eax, word ptr [rcx]
0x14000b538  cmp     eax, r9d
0x14000b53b  jnz     short loc_14000B573
0x14000b53d  add     rcx, 2; Source1
0x14000b541  mov     r8d, r9d; Length
0x14000b544  mov     rdx, r10; Source2
0x14000b547  mov     ebx, r9d
0x14000b54a  call    cs:__imp_RtlCompareMemory
0x14000b551  nop     dword ptr [rax+rax+00h]
0x14000b556  cmp     rax, rbx
0x14000b559  jnz     short loc_14000B573
0x14000b55b  mov     r8, rdi; ValueName
0x14000b55e  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000b565  xor     ecx, ecx; RelativeTo
0x14000b567  call    cs:__imp_RtlDeleteRegistryValue
0x14000b56e  nop     dword ptr [rax+rax+00h]
0x14000b573  mov     rbx, [rsp+28h+arg_0]
0x14000b578  xor     eax, eax
0x14000b57a  add     rsp, 20h
0x14000b57e  pop     rdi
0x14000b57f  retn
```
