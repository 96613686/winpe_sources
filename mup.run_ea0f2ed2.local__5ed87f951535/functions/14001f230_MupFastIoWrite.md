# MupFastIoWrite

- ea: `0x14001f230`
- end: `0x14001f2b7`
- name: `MupFastIoWrite`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400023a0`
- `0x1400054e0`
- `0x14001f230`

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
0x14001f230  push    rbx
0x14001f232  push    rbp
0x14001f233  push    rsi
0x14001f234  push    rdi
0x14001f235  sub     rsp, 58h
0x14001f239  mov     dil, r9b
0x14001f23c  mov     esi, r8d
0x14001f23f  mov     rbp, rdx
0x14001f242  mov     rbx, rcx
0x14001f245  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001f24a  test    rax, rax
0x14001f24d  jz      short loc_14001F2AB
0x14001f24f  mov     r10, [rax+8]
0x14001f253  mov     r11, [r10+50h]
0x14001f257  test    r11, r11
0x14001f25a  jz      short loc_14001F2AB
0x14001f25c  cmp     dword ptr [r11], 20h ; ' '
0x14001f260  jb      short loc_14001F2AB
0x14001f262  mov     r10, [r11+18h]
0x14001f266  test    r10, r10
0x14001f269  jz      short loc_14001F2AB
0x14001f26b  mov     rcx, [rsp+78h+arg_30]
0x14001f273  mov     r9b, dil
0x14001f276  mov     [rsp+78h+var_40], rax
0x14001f27b  mov     r8d, esi
0x14001f27e  mov     [rsp+78h+var_48], rcx
0x14001f283  mov     rdx, rbp
0x14001f286  mov     rcx, [rsp+78h+arg_28]
0x14001f28e  mov     rax, r10
0x14001f291  mov     [rsp+78h+var_50], rcx
0x14001f296  mov     ecx, [rsp+78h+arg_20]
0x14001f29d  mov     [rsp+78h+var_58], ecx
0x14001f2a1  mov     rcx, rbx
0x14001f2a4  call    _guard_dispatch_icall
0x14001f2a9  jmp     short loc_14001F2AD
0x14001f2ab  xor     al, al
0x14001f2ad  add     rsp, 58h
0x14001f2b1  pop     rdi
0x14001f2b2  pop     rsi
0x14001f2b3  pop     rbp
0x14001f2b4  pop     rbx
0x14001f2b5  retn
```
