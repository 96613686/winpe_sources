# fnEfsLogTrace1

- ea: `0x180003604`
- end: `0x18000369a`
- name: `fnEfsLogTrace1`
- size: `150`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, char)`
- caller_count: `49`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d6c`
- `0x180002ee0`
- `0x1800036a0`
- `0x180003b80`
- `0x180003c30`
- `0x180003d70`
- `0x180003e50`
- `0x180003f20`
- `0x180004000`
- `0x1800040f0`
- `0x1800041d0`
- `0x180004290`
- `0x180004370`
- `0x1800044f0`
- `0x180004630`
- `0x180004800`
- `0x1800048b0`
- `0x180004980`
- `0x180004a30`
- `0x180004af0`
- `0x180004bb0`
- `0x180004e20`
- `0x180004f30`
- `0x180005030`
- `0x1800050f0`
- `0x1800051c0`
- `0x1800052a0`
- `0x1800054b0`
- `0x1800055b0`
- `0x1800058a0`
- `0x180005bc0`
- `0x180005ef0`
- `0x1800063c0`
- `0x1800065a0`
- `0x180006710`
- `0x1800068a0`
- `0x180006a00`
- `0x180006bb0`
- `0x180006d70`
- `0x180006df0`
- `0x180007030`
- `0x180007140`
- `0x180007290`
- `0x180007330`
- `0x1800074d0`
- `0x180007810`
- `0x180007bb0`
- `0x18000b308`
- `0x18000b614`

## callees

- `0x180003604`
- `0x18000c3c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000367d`
- `ntdll!EtwEventWrite` at `0x18000367d`
- `ntdll!EtwEventEnabled` at `0x180003633`
- `ntdll!EtwEventEnabled` at `0x180003633`

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
0x180003604  mov     [rsp-18h+arg_18], r9d
0x180003609  mov     [rsp-18h+arg_10], r8d
0x18000360e  push    rbp
0x18000360f  push    rbx
0x180003610  push    rdi
0x180003611  mov     rbp, rsp
0x180003614  sub     rsp, 60h
0x180003618  mov     rax, cs:__security_cookie
0x18000361f  xor     rax, rsp
0x180003622  mov     [rbp+var_10], rax
0x180003626  mov     rdi, cs:g_hPublisher
0x18000362d  mov     rbx, rdx
0x180003630  mov     rcx, rdi
0x180003633  call    cs:__imp_EtwEventEnabled
0x180003639  test    al, al
0x18000363b  jz      short loc_180003683
0x18000363d  lea     rax, [rbp+arg_18]
0x180003641  mov     [rbp+var_38], 4
0x180003649  mov     [rbp+var_40], rax
0x18000364d  lea     r9, [rbp+var_40]
0x180003651  lea     rax, [rbp+arg_20]
0x180003655  mov     [rbp+var_28], 4
0x18000365d  mov     [rbp+var_30], rax
0x180003661  mov     r8d, 3
0x180003667  lea     rax, [rbp+arg_10]
0x18000366b  mov     [rbp+var_18], 4
0x180003673  mov     rdx, rbx
0x180003676  mov     [rbp+var_20], rax
0x18000367a  mov     rcx, rdi
0x18000367d  call    cs:__imp_EtwEventWrite
0x180003683  mov     eax, [rbp+arg_10]
0x180003686  mov     rcx, [rbp+var_10]
0x18000368a  xor     rcx, rsp; StackCookie
0x18000368d  call    __security_check_cookie
0x180003692  add     rsp, 60h
0x180003696  pop     rdi
0x180003697  pop     rbx
0x180003698  pop     rbp
0x180003699  retn
```
