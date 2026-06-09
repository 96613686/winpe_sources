# MupFastIoQueryNetworkOpenInfo

- ea: `0x14001edb0`
- end: `0x14001ee18`
- name: `MupFastIoQueryNetworkOpenInfo`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400023a0`
- `0x1400054e0`
- `0x14001edb0`

## pseudocode

```c
char __fastcall MupFastIoQueryNetworkOpenInfo(__int64 a1, char a2, __int64 a3, _DWORD *a4)
{
  __int64 UncProviderDeviceObjectFromFileObject; // rax
  __int64 v9; // rdx
  __int64 v10; // r11
  __int64 (__fastcall *v11)(__int64, __int64, __int64, _DWORD *, __int64); // r10
  char result; // al

  UncProviderDeviceObjectFromFileObject = MupGetUncProviderDeviceObjectFromFileObject();
  if ( UncProviderDeviceObjectFromFileObject
    && (v10 = *(_QWORD *)(*(_QWORD *)(UncProviderDeviceObjectFromFileObject + 8) + 80LL)) != 0
    && *(_DWORD *)v10 >= 0x78u
    && (v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _DWORD *, __int64))(v10 + 112)) != 0 )
  {
    LOBYTE(v9) = a2;
    return v11(a1, v9, a3, a4, UncProviderDeviceObjectFromFileObject);
  }
  else
  {
    result = 0;
    *a4 = -1073741637;
  }
  return result;
}

```

## disassembly

```asm
0x14001edb0  push    rbx
0x14001edb2  push    rbp
0x14001edb3  push    rsi
0x14001edb4  push    rdi
0x14001edb5  sub     rsp, 38h
0x14001edb9  mov     rbx, r9
0x14001edbc  mov     rsi, r8
0x14001edbf  mov     bpl, dl
0x14001edc2  mov     rdi, rcx
0x14001edc5  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001edca  test    rax, rax
0x14001edcd  jz      short loc_14001EE06
0x14001edcf  mov     r10, [rax+8]
0x14001edd3  mov     r11, [r10+50h]
0x14001edd7  test    r11, r11
0x14001edda  jz      short loc_14001EE06
0x14001eddc  cmp     dword ptr [r11], 78h ; 'x'
0x14001ede0  jb      short loc_14001EE06
0x14001ede2  mov     r10, [r11+70h]
0x14001ede6  test    r10, r10
0x14001ede9  jz      short loc_14001EE06
0x14001edeb  mov     [rsp+58h+var_38], rax
0x14001edf0  mov     r9, rbx
0x14001edf3  mov     rax, r10
0x14001edf6  mov     r8, rsi
0x14001edf9  mov     dl, bpl
0x14001edfc  mov     rcx, rdi
0x14001edff  call    _guard_dispatch_icall
0x14001ee04  jmp     short loc_14001EE0E
0x14001ee06  xor     al, al
0x14001ee08  mov     dword ptr [rbx], 0C00000BBh
0x14001ee0e  add     rsp, 38h
0x14001ee12  pop     rdi
0x14001ee13  pop     rsi
0x14001ee14  pop     rbp
0x14001ee15  pop     rbx
0x14001ee16  retn
```
