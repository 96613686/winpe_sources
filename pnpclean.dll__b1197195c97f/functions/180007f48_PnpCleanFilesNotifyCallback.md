# PnpCleanFilesNotifyCallback

- ea: `0x180007f48`
- end: `0x180007fb3`
- name: `PnpCleanFilesNotifyCallback`
- size: `107`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007dec`
- `0x180007fbc`
- `0x18000829c`

## callees

- `0x180007f48`
- `0x180008e30`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall PnpCleanFilesNotifyCallback(__int64 a1)
{
  __int64 (__fastcall *v1)(_DWORD *, __int64); // r8
  __int64 result; // rax
  __int64 v3; // rdx
  _DWORD v4[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  v1 = *(__int64 (__fastcall **)(_DWORD *, __int64))(a1 + 24);
  result = 1;
  v4[1] = 0;
  v4[3] = 0;
  if ( v1 )
  {
    v3 = *(_QWORD *)(a1 + 32);
    v4[0] = *(_DWORD *)(a1 + 60);
    v4[2] = *(_DWORD *)(a1 + 64);
    v5 = *(_QWORD *)(a1 + 72);
    return v1(v4, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007f48  sub     rsp, 48h
0x180007f4c  mov     rax, cs:__security_cookie
0x180007f53  xor     rax, rsp
0x180007f56  mov     [rsp+48h+var_10], rax
0x180007f5b  mov     r8, [rcx+18h]
0x180007f5f  mov     eax, 1
0x180007f64  mov     [rsp+48h+var_24], 0
0x180007f6c  mov     [rsp+48h+var_1C], 0
0x180007f74  test    r8, r8
0x180007f77  jz      short loc_180007FA1
0x180007f79  mov     eax, [rcx+3Ch]
0x180007f7c  mov     rdx, [rcx+20h]
0x180007f80  mov     [rsp+48h+var_28], eax
0x180007f84  mov     eax, [rcx+40h]
0x180007f87  mov     [rsp+48h+var_20], eax
0x180007f8b  mov     rax, [rcx+48h]
0x180007f8f  lea     rcx, [rsp+48h+var_28]
0x180007f94  mov     [rsp+48h+var_18], rax
0x180007f99  mov     rax, r8
0x180007f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa1  mov     rcx, [rsp+48h+var_10]
0x180007fa6  xor     rcx, rsp; StackCookie
0x180007fa9  call    __security_check_cookie
0x180007fae  add     rsp, 48h
0x180007fb2  retn
```
