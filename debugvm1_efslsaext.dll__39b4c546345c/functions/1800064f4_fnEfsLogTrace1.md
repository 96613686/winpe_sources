# fnEfsLogTrace1

- ea: `0x1800064f4`
- end: `0x18000658a`
- name: `fnEfsLogTrace1`
- size: `150`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006708`
- `0x1800068c8`
- `0x180006c1c`
- `0x180006e60`
- `0x180006f60`
- `0x180008368`
- `0x180008544`
- `0x180008aec`
- `0x180008bd0`
- `0x180008e54`
- `0x1800090f4`
- `0x180009200`
- `0x180009b2c`

## callees

- `0x1800064f4`
- `0x180012040`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180006523`
- `ntdll!EtwEventEnabled` at `0x180006523`
- `ntdll!EtwEventWrite` at `0x18000656d`
- `ntdll!EtwEventWrite` at `0x18000656d`

## pseudocode

```c
__int64 __fastcall fnEfsLogTrace1(__int64 a1, __int64 a2, unsigned int a3, int a4, char a5)
{
  __int64 v5; // rdi
  _QWORD v8[6]; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v9; // [rsp+90h] [rbp+30h] BYREF
  int v10; // [rsp+98h] [rbp+38h] BYREF

  v10 = a4;
  v9 = a3;
  v5 = g_hPublisher;
  if ( (unsigned __int8)EtwEventEnabled(g_hPublisher) )
  {
    v8[1] = 4;
    v8[0] = &v10;
    v8[3] = 4;
    v8[2] = &a5;
    v8[5] = 4;
    v8[4] = &v9;
    ((void (__fastcall *)(__int64, __int64, __int64, _QWORD *))EtwEventWrite)(v5, a2, 3, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x1800064f4  mov     [rsp-18h+arg_18], r9d
0x1800064f9  mov     [rsp-18h+arg_10], r8d
0x1800064fe  push    rbp
0x1800064ff  push    rbx
0x180006500  push    rdi
0x180006501  mov     rbp, rsp
0x180006504  sub     rsp, 60h
0x180006508  mov     rax, cs:__security_cookie
0x18000650f  xor     rax, rsp
0x180006512  mov     [rbp+var_10], rax
0x180006516  mov     rdi, cs:g_hPublisher
0x18000651d  mov     rbx, rdx
0x180006520  mov     rcx, rdi
0x180006523  call    cs:__imp_EtwEventEnabled
0x180006529  test    al, al
0x18000652b  jz      short loc_180006573
0x18000652d  lea     rax, [rbp+arg_18]
0x180006531  mov     [rbp+var_38], 4
0x180006539  mov     [rbp+var_40], rax
0x18000653d  lea     r9, [rbp+var_40]
0x180006541  lea     rax, [rbp+arg_20]
0x180006545  mov     [rbp+var_28], 4
0x18000654d  mov     [rbp+var_30], rax
0x180006551  mov     r8d, 3
0x180006557  lea     rax, [rbp+arg_10]
0x18000655b  mov     [rbp+var_18], 4
0x180006563  mov     rdx, rbx
0x180006566  mov     [rbp+var_20], rax
0x18000656a  mov     rcx, rdi
0x18000656d  call    cs:__imp_EtwEventWrite
0x180006573  mov     eax, [rbp+arg_10]
0x180006576  mov     rcx, [rbp+var_10]
0x18000657a  xor     rcx, rsp; StackCookie
0x18000657d  call    __security_check_cookie
0x180006582  add     rsp, 60h
0x180006586  pop     rdi
0x180006587  pop     rbx
0x180006588  pop     rbp
0x180006589  retn
```
