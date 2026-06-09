# PsmpAllocateTcNotify

- ea: `0x1800238b0`
- end: `0x180023940`
- name: `PsmpAllocateTcNotify`
- size: `144`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000191c`
- `0x180023ae8`

## callees

- `0x18001b7e0`
- `0x1800238b0`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x18002390b`
- `ntdll!NtCreateWnfStateName` at `0x18002390b`

## pseudocode

```c
__int64 __fastcall PsmpAllocateTcNotify(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  __int64 v6; // [rsp+40h] [rbp-18h] BYREF

  v2 = *(_QWORD *)(a1 + 80);
  v6 = 0;
  if ( !v2 )
  {
    result = NtCreateWnfStateName(&v6, 3, 0);
    if ( (int)result < 0 )
      return result;
    v2 = v6;
    *(_QWORD *)(a1 + 80) = v6;
  }
  if ( a2 )
    *a2 = v2;
  return 0;
}

```

## disassembly

```asm
0x1800238b0  mov     r11, rsp
0x1800238b3  mov     [r11+18h], rbx
0x1800238b7  push    rdi
0x1800238b8  sub     rsp, 50h
0x1800238bc  mov     rax, cs:__security_cookie
0x1800238c3  xor     rax, rsp
0x1800238c6  mov     [rsp+58h+var_10], rax
0x1800238cb  mov     rax, [rcx+50h]
0x1800238cf  mov     rbx, rdx
0x1800238d2  mov     qword ptr [r11-18h], 0
0x1800238da  mov     rdi, rcx
0x1800238dd  test    rax, rax
0x1800238e0  jnz     short loc_18002391E
0x1800238e2  xor     r9d, r9d
0x1800238e5  lea     rax, PsmpTcDescriptor
0x1800238ec  mov     [r11-28h], rax
0x1800238f0  lea     rcx, [r11-18h]
0x1800238f4  mov     [rsp+58h+var_30], 4
0x1800238fc  xor     r8d, r8d
0x1800238ff  mov     qword ptr [r11-38h], 0
0x180023907  lea     edx, [r9+3]
0x18002390b  call    cs:__imp_NtCreateWnfStateName
0x180023911  test    eax, eax
0x180023913  js      short loc_180023928
0x180023915  mov     rax, [rsp+58h+var_18]
0x18002391a  mov     [rdi+50h], rax
0x18002391e  test    rbx, rbx
0x180023921  jz      short loc_180023926
0x180023923  mov     [rbx], rax
0x180023926  xor     eax, eax
0x180023928  mov     rcx, [rsp+58h+var_10]
0x18002392d  xor     rcx, rsp; StackCookie
0x180023930  call    __security_check_cookie
0x180023935  mov     rbx, [rsp+58h+arg_10]
0x18002393a  add     rsp, 50h
0x18002393e  pop     rdi
0x18002393f  retn
```
