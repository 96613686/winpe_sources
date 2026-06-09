# MupFastIoQueryNetworkOpenInfo

- ea: `0x14001ee00`
- end: `0x14001ee68`
- name: `MupFastIoQueryNetworkOpenInfo`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400023a0`
- `0x1400054e0`
- `0x14001ee00`

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
0x14001ee00  push    rbx
0x14001ee02  push    rbp
0x14001ee03  push    rsi
0x14001ee04  push    rdi
0x14001ee05  sub     rsp, 38h
0x14001ee09  mov     rbx, r9
0x14001ee0c  mov     rsi, r8
0x14001ee0f  mov     bpl, dl
0x14001ee12  mov     rdi, rcx
0x14001ee15  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001ee1a  test    rax, rax
0x14001ee1d  jz      short loc_14001EE56
0x14001ee1f  mov     r10, [rax+8]
0x14001ee23  mov     r11, [r10+50h]
0x14001ee27  test    r11, r11
0x14001ee2a  jz      short loc_14001EE56
0x14001ee2c  cmp     dword ptr [r11], 78h ; 'x'
0x14001ee30  jb      short loc_14001EE56
0x14001ee32  mov     r10, [r11+70h]
0x14001ee36  test    r10, r10
0x14001ee39  jz      short loc_14001EE56
0x14001ee3b  mov     [rsp+58h+var_38], rax
0x14001ee40  mov     r9, rbx
0x14001ee43  mov     rax, r10
0x14001ee46  mov     r8, rsi
0x14001ee49  mov     dl, bpl
0x14001ee4c  mov     rcx, rdi
0x14001ee4f  call    _guard_dispatch_icall
0x14001ee54  jmp     short loc_14001EE5E
0x14001ee56  xor     al, al
0x14001ee58  mov     dword ptr [rbx], 0C00000BBh
0x14001ee5e  add     rsp, 38h
0x14001ee62  pop     rdi
0x14001ee63  pop     rsi
0x14001ee64  pop     rbp
0x14001ee65  pop     rbx
0x14001ee66  retn
```
