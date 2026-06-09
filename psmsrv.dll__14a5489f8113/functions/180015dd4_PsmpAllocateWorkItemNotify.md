# PsmpAllocateWorkItemNotify

- ea: `0x180015dd4`
- end: `0x180015e66`
- name: `PsmpAllocateWorkItemNotify`
- size: `146`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000191c`
- `0x18000dfc0`

## callees

- `0x180015dd4`
- `0x18001b7e0`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180015e2f`
- `ntdll!NtCreateWnfStateName` at `0x180015e2f`

## pseudocode

```c
__int64 __fastcall PsmpAllocateWorkItemNotify(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  __int64 v6; // [rsp+40h] [rbp-18h] BYREF

  v2 = *(_QWORD *)(a1 + 88);
  v6 = 0;
  if ( !v2 )
  {
    result = NtCreateWnfStateName(&v6, 3, 0);
    if ( (int)result < 0 )
      return result;
    v2 = v6;
    *(_QWORD *)(a1 + 88) = v6;
  }
  if ( a2 )
    *a2 = v2;
  return 0;
}

```

## disassembly

```asm
0x180015dd4  mov     r11, rsp
0x180015dd7  mov     [r11+18h], rbx
0x180015ddb  push    rdi
0x180015ddc  sub     rsp, 50h
0x180015de0  mov     rax, cs:__security_cookie
0x180015de7  xor     rax, rsp
0x180015dea  mov     [rsp+58h+var_10], rax
0x180015def  mov     rax, [rcx+58h]
0x180015df3  mov     rbx, rdx
0x180015df6  mov     qword ptr [r11-18h], 0
0x180015dfe  mov     rdi, rcx
0x180015e01  test    rax, rax
0x180015e04  jnz     short loc_180015E42
0x180015e06  xor     r9d, r9d
0x180015e09  lea     rax, PsmpWorkItemCountDescriptor
0x180015e10  mov     [r11-28h], rax
0x180015e14  lea     rcx, [r11-18h]
0x180015e18  mov     [rsp+58h+var_30], 4
0x180015e20  xor     r8d, r8d
0x180015e23  mov     qword ptr [r11-38h], 0
0x180015e2b  lea     edx, [r9+3]
0x180015e2f  call    cs:__imp_NtCreateWnfStateName
0x180015e35  test    eax, eax
0x180015e37  js      short loc_180015E49
0x180015e39  mov     rax, [rsp+58h+var_18]
0x180015e3e  mov     [rdi+58h], rax
0x180015e42  test    rbx, rbx
0x180015e45  jnz     short loc_180015E61
0x180015e47  xor     eax, eax
0x180015e49  mov     rcx, [rsp+58h+var_10]
0x180015e4e  xor     rcx, rsp; StackCookie
0x180015e51  call    __security_check_cookie
0x180015e56  mov     rbx, [rsp+58h+arg_10]
0x180015e5b  add     rsp, 50h
0x180015e5f  pop     rdi
0x180015e60  retn
0x180015e61  mov     [rbx], rax
0x180015e64  jmp     short loc_180015E47
```
