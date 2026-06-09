# MupFastIoWrite

- ea: `0x14001f280`
- end: `0x14001f307`
- name: `MupFastIoWrite`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400023a0`
- `0x1400054e0`
- `0x14001f280`

## pseudocode

```c
char __fastcall MupFastIoWrite(__int64 a1, __int64 a2, unsigned int a3, char a4, int a5, __int64 a6, __int64 a7)
{
  __int64 UncProviderDeviceObjectFromFileObject; // rax
  __int64 v12; // r9
  __int64 v13; // r11
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, __int64, int, __int64, __int64, __int64); // r10

  UncProviderDeviceObjectFromFileObject = MupGetUncProviderDeviceObjectFromFileObject();
  if ( !UncProviderDeviceObjectFromFileObject )
    return 0;
  v13 = *(_QWORD *)(*(_QWORD *)(UncProviderDeviceObjectFromFileObject + 8) + 80LL);
  if ( !v13 )
    return 0;
  if ( *(_DWORD *)v13 < 0x20u )
    return 0;
  v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, int, __int64, __int64, __int64))(v13 + 24);
  if ( !v14 )
    return 0;
  LOBYTE(v12) = a4;
  return v14(a1, a2, a3, v12, a5, a6, a7, UncProviderDeviceObjectFromFileObject);
}

```

## disassembly

```asm
0x14001f280  push    rbx
0x14001f282  push    rbp
0x14001f283  push    rsi
0x14001f284  push    rdi
0x14001f285  sub     rsp, 58h
0x14001f289  mov     dil, r9b
0x14001f28c  mov     esi, r8d
0x14001f28f  mov     rbp, rdx
0x14001f292  mov     rbx, rcx
0x14001f295  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001f29a  test    rax, rax
0x14001f29d  jz      short loc_14001F2FB
0x14001f29f  mov     r10, [rax+8]
0x14001f2a3  mov     r11, [r10+50h]
0x14001f2a7  test    r11, r11
0x14001f2aa  jz      short loc_14001F2FB
0x14001f2ac  cmp     dword ptr [r11], 20h ; ' '
0x14001f2b0  jb      short loc_14001F2FB
0x14001f2b2  mov     r10, [r11+18h]
0x14001f2b6  test    r10, r10
0x14001f2b9  jz      short loc_14001F2FB
0x14001f2bb  mov     rcx, [rsp+78h+arg_30]
0x14001f2c3  mov     r9b, dil
0x14001f2c6  mov     [rsp+78h+var_40], rax
0x14001f2cb  mov     r8d, esi
0x14001f2ce  mov     [rsp+78h+var_48], rcx
0x14001f2d3  mov     rdx, rbp
0x14001f2d6  mov     rcx, [rsp+78h+arg_28]
0x14001f2de  mov     rax, r10
0x14001f2e1  mov     [rsp+78h+var_50], rcx
0x14001f2e6  mov     ecx, [rsp+78h+arg_20]
0x14001f2ed  mov     [rsp+78h+var_58], ecx
0x14001f2f1  mov     rcx, rbx
0x14001f2f4  call    _guard_dispatch_icall
0x14001f2f9  jmp     short loc_14001F2FD
0x14001f2fb  xor     al, al
0x14001f2fd  add     rsp, 58h
0x14001f301  pop     rdi
0x14001f302  pop     rsi
0x14001f303  pop     rbp
0x14001f304  pop     rbx
0x14001f305  retn
```
