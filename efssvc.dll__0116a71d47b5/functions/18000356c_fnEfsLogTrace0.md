# fnEfsLogTrace0

- ea: `0x18000356c`
- end: `0x1800035fb`
- name: `fnEfsLogTrace0`
- size: `143`
- prototype: `__int64 __fastcall(__int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ee0`
- `0x1800065a0`

## callees

- `0x18000356c`
- `0x18000c3c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800035dd`
- `ntdll!EtwEventWrite` at `0x1800035dd`
- `ntdll!EtwEventEnabled` at `0x18000359c`
- `ntdll!EtwEventEnabled` at `0x18000359c`

## pseudocode

```c
__int64 __fastcall fnEfsLogTrace0(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 v4; // rdi
  __int64 result; // rax
  _QWORD v7[4]; // [rsp+20h] [rbp-38h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
  v8 = a3;
  v4 = g_hPublisher;
  result = EtwEventEnabled(g_hPublisher);
  if ( (_BYTE)result )
  {
    v7[1] = 4;
    v7[0] = &v8;
    v7[3] = 4;
    v7[2] = &v9;
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD *))EtwEventWrite)(v4, a2, 2, v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000356c  mov     [rsp+arg_0], rbx
0x180003571  mov     [rsp+arg_18], r9d
0x180003576  mov     [rsp+arg_10], r8d
0x18000357b  push    rdi
0x18000357c  sub     rsp, 50h
0x180003580  mov     rax, cs:__security_cookie
0x180003587  xor     rax, rsp
0x18000358a  mov     [rsp+58h+var_18], rax
0x18000358f  mov     rdi, cs:g_hPublisher
0x180003596  mov     rbx, rdx
0x180003599  mov     rcx, rdi
0x18000359c  call    cs:__imp_EtwEventEnabled
0x1800035a2  test    al, al
0x1800035a4  jz      short loc_1800035E3
0x1800035a6  lea     rax, [rsp+58h+arg_10]
0x1800035ab  mov     [rsp+58h+var_30], 4
0x1800035b4  mov     [rsp+58h+var_38], rax
0x1800035b9  lea     r9, [rsp+58h+var_38]
0x1800035be  lea     rax, [rsp+58h+arg_18]
0x1800035c3  mov     [rsp+58h+var_20], 4
0x1800035cc  mov     r8d, 2
0x1800035d2  mov     [rsp+58h+var_28], rax
0x1800035d7  mov     rdx, rbx
0x1800035da  mov     rcx, rdi
0x1800035dd  call    cs:__imp_EtwEventWrite
0x1800035e3  mov     rcx, [rsp+58h+var_18]
0x1800035e8  xor     rcx, rsp; StackCookie
0x1800035eb  call    __security_check_cookie
0x1800035f0  mov     rbx, [rsp+58h+arg_0]
0x1800035f5  add     rsp, 50h
0x1800035f9  pop     rdi
0x1800035fa  retn
```
