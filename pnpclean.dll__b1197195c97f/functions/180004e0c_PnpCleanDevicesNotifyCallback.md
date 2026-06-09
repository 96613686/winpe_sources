# PnpCleanDevicesNotifyCallback

- ea: `0x180004e0c`
- end: `0x180004e6d`
- name: `PnpCleanDevicesNotifyCallback`
- size: `97`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003d70`
- `0x180004c14`
- `0x180004e74`

## callees

- `0x180004e0c`
- `0x180008e30`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall PnpCleanDevicesNotifyCallback(__int64 a1)
{
  __int64 (__fastcall *v1)(__int128 *, __int64); // r8
  __int64 result; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  v1 = *(__int64 (__fastcall **)(__int128 *, __int64))(a1 + 32);
  v5 = 0;
  result = 1;
  v4 = 0;
  if ( v1 )
  {
    v3 = *(_QWORD *)(a1 + 40);
    LODWORD(v4) = *(_DWORD *)(a1 + 68);
    DWORD2(v4) = *(_DWORD *)(a1 + 72);
    return v1(&v4, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180004e0c  sub     rsp, 48h
0x180004e10  mov     rax, cs:__security_cookie
0x180004e17  xor     rax, rsp
0x180004e1a  mov     [rsp+48h+var_10], rax
0x180004e1f  mov     r8, [rcx+20h]
0x180004e23  xor     edx, edx
0x180004e25  mov     [rsp+48h+var_18], rdx
0x180004e2a  xorps   xmm0, xmm0
0x180004e2d  mov     eax, 1
0x180004e32  movups  [rsp+48h+var_28], xmm0
0x180004e37  test    r8, r8
0x180004e3a  jz      short loc_180004E5B
0x180004e3c  mov     eax, [rcx+44h]
0x180004e3f  mov     rdx, [rcx+28h]
0x180004e43  mov     dword ptr [rsp+48h+var_28], eax
0x180004e47  mov     eax, [rcx+48h]
0x180004e4a  lea     rcx, [rsp+48h+var_28]
0x180004e4f  mov     dword ptr [rsp+48h+var_28+8], eax
0x180004e53  mov     rax, r8
0x180004e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5b  mov     rcx, [rsp+48h+var_10]
0x180004e60  xor     rcx, rsp; StackCookie
0x180004e63  call    __security_check_cookie
0x180004e68  add     rsp, 48h
0x180004e6c  retn
```
