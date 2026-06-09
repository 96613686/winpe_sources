# fnEfsLogTrace1

- ea: `0x1800037b8`
- end: `0x18000385b`
- name: `fnEfsLogTrace1`
- size: `163`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, char)`
- caller_count: `49`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e10`
- `0x180002fb0`
- `0x180003864`
- `0x180003dd0`
- `0x180003e90`
- `0x180003fe0`
- `0x1800040c0`
- `0x1800041a0`
- `0x180004290`
- `0x180004380`
- `0x180004470`
- `0x180004540`
- `0x180004630`
- `0x1800047c0`
- `0x180004900`
- `0x180004ad0`
- `0x180004b90`
- `0x180004c70`
- `0x180004d30`
- `0x180004e00`
- `0x180004ec0`
- `0x180005180`
- `0x1800052b0`
- `0x1800053b0`
- `0x180005480`
- `0x180005550`
- `0x180005640`
- `0x1800058a0`
- `0x1800059a0`
- `0x180005d00`
- `0x1800060c0`
- `0x180006460`
- `0x1800069d0`
- `0x180006bf0`
- `0x180006d80`
- `0x180006f40`
- `0x1800070d0`
- `0x1800072b0`
- `0x1800074a0`
- `0x180007530`
- `0x1800077c0`
- `0x1800078e0`
- `0x180007a70`
- `0x180007b30`
- `0x180007d10`
- `0x1800080c4`
- `0x1800084f0`
- `0x18000bf0c`
- `0x18000c264`

## callees

- `0x1800037b8`
- `0x18000d1c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180003837`
- `ntdll!EtwEventWrite` at `0x180003837`
- `ntdll!EtwEventEnabled` at `0x1800037e7`
- `ntdll!EtwEventEnabled` at `0x1800037e7`

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
0x1800037b8  mov     [rsp-18h+arg_18], r9d
0x1800037bd  mov     [rsp-18h+arg_10], r8d
0x1800037c2  push    rbp
0x1800037c3  push    rbx
0x1800037c4  push    rdi
0x1800037c5  mov     rbp, rsp
0x1800037c8  sub     rsp, 60h
0x1800037cc  mov     rax, cs:__security_cookie
0x1800037d3  xor     rax, rsp
0x1800037d6  mov     [rbp+var_10], rax
0x1800037da  mov     rdi, cs:g_hPublisher
0x1800037e1  mov     rbx, rdx
0x1800037e4  mov     rcx, rdi
0x1800037e7  call    cs:__imp_EtwEventEnabled
0x1800037ee  nop     dword ptr [rax+rax+00h]
0x1800037f3  test    al, al
0x1800037f5  jz      short loc_180003843
0x1800037f7  lea     rax, [rbp+arg_18]
0x1800037fb  mov     [rbp+var_38], 4
0x180003803  mov     [rbp+var_40], rax
0x180003807  lea     r9, [rbp+var_40]
0x18000380b  lea     rax, [rbp+arg_20]
0x18000380f  mov     [rbp+var_28], 4
0x180003817  mov     [rbp+var_30], rax
0x18000381b  mov     r8d, 3
0x180003821  lea     rax, [rbp+arg_10]
0x180003825  mov     [rbp+var_18], 4
0x18000382d  mov     rdx, rbx
0x180003830  mov     [rbp+var_20], rax
0x180003834  mov     rcx, rdi
0x180003837  call    cs:__imp_EtwEventWrite
0x18000383e  nop     dword ptr [rax+rax+00h]
0x180003843  mov     eax, [rbp+arg_10]
0x180003846  mov     rcx, [rbp+var_10]
0x18000384a  xor     rcx, rsp; StackCookie
0x18000384d  call    __security_check_cookie
0x180003852  add     rsp, 60h
0x180003856  pop     rdi
0x180003857  pop     rbx
0x180003858  pop     rbp
0x180003859  retn
```
