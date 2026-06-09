# MupFastIoRead

- ea: `0x14001e7a0`
- end: `0x14001e829`
- name: `MupFastIoRead`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400023a0`
- `0x1400054e0`
- `0x14001e7a0`

## pseudocode

```c
char __fastcall MupFastIoRead(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 UncProviderDeviceObjectFromFileObject; // rax
  __int64 v12; // r10
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD, _QWORD, int, __int64, __int64, __int64); // r11

  UncProviderDeviceObjectFromFileObject = MupGetUncProviderDeviceObjectFromFileObject();
  if ( UncProviderDeviceObjectFromFileObject
    && (v12 = *(_QWORD *)(*(_QWORD *)(UncProviderDeviceObjectFromFileObject + 8) + 80LL)) != 0
    && *(_DWORD *)v12 >= 0x18u
    && (v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64, __int64, __int64))(v12 + 16)) != 0 )
  {
    return v13(a1, a2, a3, a4, a5, a6, a7, UncProviderDeviceObjectFromFileObject);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x14001e7a0  push    rbx
0x14001e7a2  push    rbp
0x14001e7a3  push    rsi
0x14001e7a4  push    rdi
0x14001e7a5  sub     rsp, 58h
0x14001e7a9  movzx   edi, r9b
0x14001e7ad  mov     esi, r8d
0x14001e7b0  mov     rbp, rdx
0x14001e7b3  mov     rbx, rcx
0x14001e7b6  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001e7bb  test    rax, rax
0x14001e7be  jz      short loc_14001E825
0x14001e7c0  mov     r10, [rax+8]
0x14001e7c4  mov     r10, [r10+50h]
0x14001e7c8  test    r10, r10
0x14001e7cb  jz      short loc_14001E825
0x14001e7cd  cmp     dword ptr [r10], 18h
0x14001e7d1  jb      short loc_14001E825
0x14001e7d3  mov     r11, [r10+10h]
0x14001e7d7  test    r11, r11
0x14001e7da  jz      short loc_14001E825
0x14001e7dc  mov     rcx, [rsp+78h+arg_30]
0x14001e7e4  movzx   r9d, dil
0x14001e7e8  mov     [rsp+78h+var_40], rax
0x14001e7ed  mov     r8d, esi
0x14001e7f0  mov     [rsp+78h+var_48], rcx
0x14001e7f5  mov     rdx, rbp
0x14001e7f8  mov     rcx, [rsp+78h+arg_28]
0x14001e800  mov     rax, r11
0x14001e803  mov     [rsp+78h+var_50], rcx
0x14001e808  mov     ecx, [rsp+78h+arg_20]
0x14001e80f  mov     [rsp+78h+var_58], ecx
0x14001e813  mov     rcx, rbx
0x14001e816  call    _guard_dispatch_icall
0x14001e81b  add     rsp, 58h
0x14001e81f  pop     rdi
0x14001e820  pop     rsi
0x14001e821  pop     rbp
0x14001e822  pop     rbx
0x14001e823  retn
0x14001e825  xor     al, al
0x14001e827  jmp     short loc_14001E81B
```
