# PnpCleanDriversNotifyCallback

- ea: `0x180007370`
- end: `0x1800073db`
- name: `PnpCleanDriversNotifyCallback`
- size: `107`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005bd0`
- `0x180006dc4`
- `0x180007680`

## callees

- `0x180007370`
- `0x180008e30`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall PnpCleanDriversNotifyCallback(__int64 a1)
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
    v4[0] = *(_DWORD *)(a1 + 68);
    v4[2] = *(_DWORD *)(a1 + 72);
    v5 = *(_QWORD *)(a1 + 80);
    return v1(v4, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007370  sub     rsp, 48h
0x180007374  mov     rax, cs:__security_cookie
0x18000737b  xor     rax, rsp
0x18000737e  mov     [rsp+48h+var_10], rax
0x180007383  mov     r8, [rcx+18h]
0x180007387  mov     eax, 1
0x18000738c  mov     [rsp+48h+var_24], 0
0x180007394  mov     [rsp+48h+var_1C], 0
0x18000739c  test    r8, r8
0x18000739f  jz      short loc_1800073C9
0x1800073a1  mov     eax, [rcx+44h]
0x1800073a4  mov     rdx, [rcx+20h]
0x1800073a8  mov     [rsp+48h+var_28], eax
0x1800073ac  mov     eax, [rcx+48h]
0x1800073af  mov     [rsp+48h+var_20], eax
0x1800073b3  mov     rax, [rcx+50h]
0x1800073b7  lea     rcx, [rsp+48h+var_28]
0x1800073bc  mov     [rsp+48h+var_18], rax
0x1800073c1  mov     rax, r8
0x1800073c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c9  mov     rcx, [rsp+48h+var_10]
0x1800073ce  xor     rcx, rsp; StackCookie
0x1800073d1  call    __security_check_cookie
0x1800073d6  add     rsp, 48h
0x1800073da  retn
```
