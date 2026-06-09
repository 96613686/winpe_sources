# MupFastIoRead

- ea: `0x14001e7f0`
- end: `0x14001e879`
- name: `MupFastIoRead`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400023a0`
- `0x1400054e0`
- `0x14001e7f0`

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
0x14001e7f0  push    rbx
0x14001e7f2  push    rbp
0x14001e7f3  push    rsi
0x14001e7f4  push    rdi
0x14001e7f5  sub     rsp, 58h
0x14001e7f9  movzx   edi, r9b
0x14001e7fd  mov     esi, r8d
0x14001e800  mov     rbp, rdx
0x14001e803  mov     rbx, rcx
0x14001e806  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001e80b  test    rax, rax
0x14001e80e  jz      short loc_14001E875
0x14001e810  mov     r10, [rax+8]
0x14001e814  mov     r10, [r10+50h]
0x14001e818  test    r10, r10
0x14001e81b  jz      short loc_14001E875
0x14001e81d  cmp     dword ptr [r10], 18h
0x14001e821  jb      short loc_14001E875
0x14001e823  mov     r11, [r10+10h]
0x14001e827  test    r11, r11
0x14001e82a  jz      short loc_14001E875
0x14001e82c  mov     rcx, [rsp+78h+arg_30]
0x14001e834  movzx   r9d, dil
0x14001e838  mov     [rsp+78h+var_40], rax
0x14001e83d  mov     r8d, esi
0x14001e840  mov     [rsp+78h+var_48], rcx
0x14001e845  mov     rdx, rbp
0x14001e848  mov     rcx, [rsp+78h+arg_28]
0x14001e850  mov     rax, r11
0x14001e853  mov     [rsp+78h+var_50], rcx
0x14001e858  mov     ecx, [rsp+78h+arg_20]
0x14001e85f  mov     [rsp+78h+var_58], ecx
0x14001e863  mov     rcx, rbx
0x14001e866  call    _guard_dispatch_icall
0x14001e86b  add     rsp, 58h
0x14001e86f  pop     rdi
0x14001e870  pop     rsi
0x14001e871  pop     rbp
0x14001e872  pop     rbx
0x14001e873  retn
0x14001e875  xor     al, al
0x14001e877  jmp     short loc_14001E86B
```
