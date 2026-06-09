# McTemplateU0qxx_EventWriteTransfer

- ea: `0x180012614`
- end: `0x180012698`
- name: `McTemplateU0qxx_EventWriteTransfer`
- size: `132`
- prototype: `ULONG(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fd0`

## callees

- `0x180004c2c`
- `0x18001cc70`

## pseudocode

```c
ULONG McTemplateU0qxx_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  int v4; // [rsp+30h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-1h] BYREF
  int *v6; // [rsp+50h] [rbp+Fh]
  __int64 v7; // [rsp+58h] [rbp+17h]
  va_list v8; // [rsp+60h] [rbp+1Fh]
  __int64 v9; // [rsp+68h] [rbp+27h]
  va_list v10; // [rsp+70h] [rbp+2Fh]
  __int64 v11; // [rsp+78h] [rbp+37h]
  __int64 v12; // [rsp+B8h] [rbp+77h] BYREF
  va_list va; // [rsp+B8h] [rbp+77h]
  va_list va1; // [rsp+C0h] [rbp+7Fh] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, _QWORD);
  v4 = 3;
  v6 = &v4;
  v9 = 8;
  va_copy(v8, va);
  v7 = 4;
  va_copy(v10, va1);
  v11 = 8;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)ProbeCallback, a3, 4u, &v5);
}

```

## disassembly

```asm
0x180012614  mov     [rsp-8+arg_18], r9
0x180012619  push    rbp
0x18001261a  lea     rbp, [rsp-4Fh]
0x18001261f  sub     rsp, 90h
0x180012626  mov     rax, cs:__security_cookie
0x18001262d  xor     rax, rsp
0x180012630  mov     [rbp+4Fh+var_10], rax
0x180012634  lea     rax, [rbp+4Fh+var_60]
0x180012638  mov     [rbp+4Fh+var_60], 3
0x18001263f  mov     [rbp+4Fh+var_40], rax
0x180012643  lea     rdx, ProbeCallback
0x18001264a  lea     rax, [rbp+4Fh+arg_18]
0x18001264e  mov     [rbp+4Fh+var_28], 8
0x180012656  mov     [rbp+4Fh+var_30], rax
0x18001265a  mov     r9d, 4
0x180012660  lea     rax, [rbp+4Fh+arg_20]
0x180012664  mov     [rbp+4Fh+var_38], r9
0x180012668  mov     [rbp+4Fh+var_20], rax
0x18001266c  lea     rax, [rbp+4Fh+var_50]
0x180012670  mov     [rsp+90h+var_70], rax
0x180012675  mov     [rbp+4Fh+var_18], 8
0x18001267d  call    McGenEventWrite_EventWriteTransfer
0x180012682  mov     rcx, [rbp+4Fh+var_10]
0x180012686  xor     rcx, rsp; StackCookie
0x180012689  call    __security_check_cookie
0x18001268e  add     rsp, 90h
0x180012695  pop     rbp
0x180012696  retn
```
