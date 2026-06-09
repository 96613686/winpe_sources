# NbtReadRegistryCleanup

- ea: `0x14004fcf4`
- end: `0x14004fd9c`
- name: `NbtReadRegistryCleanup`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140027200`
- `0x140053828`

## callees

- `0x14004fcf4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd78`

## pseudocode

```c
void __fastcall NbtReadRegistryCleanup(PVOID *a1, PVOID **a2, PVOID *a3)
{
  PVOID *v5; // rcx

  v5 = (PVOID *)*a1;
  if ( v5 )
  {
    ExFreePoolWithTag(*v5, 0);
    ExFreePoolWithTag(*a1, 0);
    *a1 = 0;
  }
  if ( *a2 )
  {
    ExFreePoolWithTag(**a2, 0);
    ExFreePoolWithTag(*a2, 0);
    *a2 = 0;
  }
  if ( *a3 )
  {
    ExFreePoolWithTag(*a3, 0);
    *a3 = 0;
  }
}

```

## disassembly

```asm
0x14004fcf4  mov     [rsp+arg_0], rbx
0x14004fcf9  mov     [rsp+arg_8], rsi
0x14004fcfe  push    rdi
0x14004fcff  sub     rsp, 20h
0x14004fd03  mov     rsi, rcx
0x14004fd06  mov     rdi, r8
0x14004fd09  mov     rcx, [rcx]
0x14004fd0c  mov     rbx, rdx
0x14004fd0f  test    rcx, rcx
0x14004fd12  jz      short loc_14004FD3D
0x14004fd14  mov     rcx, [rcx]; P
0x14004fd17  xor     edx, edx; Tag
0x14004fd19  call    cs:__imp_ExFreePoolWithTag
0x14004fd20  nop     dword ptr [rax+rax+00h]
0x14004fd25  mov     rcx, [rsi]; P
0x14004fd28  xor     edx, edx; Tag
0x14004fd2a  call    cs:__imp_ExFreePoolWithTag
0x14004fd31  nop     dword ptr [rax+rax+00h]
0x14004fd36  mov     qword ptr [rsi], 0
0x14004fd3d  mov     rcx, [rbx]
0x14004fd40  test    rcx, rcx
0x14004fd43  jz      short loc_14004FD6E
0x14004fd45  mov     rcx, [rcx]; P
0x14004fd48  xor     edx, edx; Tag
0x14004fd4a  call    cs:__imp_ExFreePoolWithTag
0x14004fd51  nop     dword ptr [rax+rax+00h]
0x14004fd56  mov     rcx, [rbx]; P
0x14004fd59  xor     edx, edx; Tag
0x14004fd5b  call    cs:__imp_ExFreePoolWithTag
0x14004fd62  nop     dword ptr [rax+rax+00h]
0x14004fd67  mov     qword ptr [rbx], 0
0x14004fd6e  mov     rcx, [rdi]; P
0x14004fd71  test    rcx, rcx
0x14004fd74  jz      short loc_14004FD8B
0x14004fd76  xor     edx, edx; Tag
0x14004fd78  call    cs:__imp_ExFreePoolWithTag
0x14004fd7f  nop     dword ptr [rax+rax+00h]
0x14004fd84  mov     qword ptr [rdi], 0
0x14004fd8b  mov     rbx, [rsp+28h+arg_0]
0x14004fd90  mov     rsi, [rsp+28h+arg_8]
0x14004fd95  add     rsp, 20h
0x14004fd99  pop     rdi
0x14004fd9a  retn
```
