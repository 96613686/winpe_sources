# PsmpGetHostIdFromProcessToken

- ea: `0x180014cc0`
- end: `0x180014d6c`
- name: `PsmpGetHostIdFromProcessToken`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ec8`

## callees

- `0x180014cc0`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtQuerySecurityAttributesToken` at `0x180014d24`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180014d24`

## pseudocode

```c
__int64 __fastcall PsmpGetHostIdFromProcessToken(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  int v5; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v6[4]; // [rsp+38h] [rbp-70h] BYREF
  int v7; // [rsp+3Ch] [rbp-6Ch]
  __int64 v8; // [rsp+40h] [rbp-68h]

  memset_0(v6, 0, 0x60u);
  v5 = 0;
  result = ((__int64 (__fastcall *)(__int64, __int64 *, __int64, _BYTE *, int, int *))NtQuerySecurityAttributesToken)(
             a1,
             &qword_180030000,
             1,
             v6,
             96,
             &v5);
  if ( (int)result >= 0 )
  {
    if ( v7 )
      *a2 = **(_QWORD **)(v8 + 32);
    else
      return 3221226021LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014cc0  mov     [rsp+arg_10], rbx
0x180014cc5  push    rdi
0x180014cc6  sub     rsp, 0A0h
0x180014ccd  mov     rax, cs:__security_cookie
0x180014cd4  xor     rax, rsp
0x180014cd7  mov     [rsp+0A8h+var_10], rax
0x180014cdf  mov     rdi, rdx
0x180014ce2  mov     rbx, rcx
0x180014ce5  xor     edx, edx; Val
0x180014ce7  lea     rcx, [rsp+0A8h+var_70]; void *
0x180014cec  lea     r8d, [rdx+60h]; Size
0x180014cf0  call    memset_0
0x180014cf5  lea     rax, [rsp+0A8h+var_78]
0x180014cfa  mov     [rsp+0A8h+var_78], 0
0x180014d02  mov     [rsp+0A8h+var_80], rax
0x180014d07  lea     r9, [rsp+0A8h+var_70]
0x180014d0c  mov     r8d, 1
0x180014d12  mov     [rsp+0A8h+var_88], 60h ; '`'
0x180014d1a  lea     rdx, qword_180030000
0x180014d21  mov     rcx, rbx
0x180014d24  call    cs:__imp_NtQuerySecurityAttributesToken
0x180014d2a  test    eax, eax
0x180014d2c  js      short loc_180014D44
0x180014d2e  cmp     [rsp+0A8h+var_6C], 0
0x180014d33  jz      short loc_180014D65
0x180014d35  mov     rcx, [rsp+0A8h+var_68]
0x180014d3a  mov     rdx, [rcx+20h]
0x180014d3e  mov     rcx, [rdx]
0x180014d41  mov     [rdi], rcx
0x180014d44  mov     rcx, [rsp+0A8h+var_10]
0x180014d4c  xor     rcx, rsp; StackCookie
0x180014d4f  call    __security_check_cookie
0x180014d54  mov     rbx, [rsp+0A8h+arg_10]
0x180014d5c  add     rsp, 0A0h
0x180014d63  pop     rdi
0x180014d64  retn
0x180014d65  mov     eax, 0C0000225h
0x180014d6a  jmp     short loc_180014D44
```
