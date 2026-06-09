# DrDrive::ShouldCreateDevice(void)

- ea: `0x1400163f0`
- end: `0x140016419`
- name: `?ShouldCreateDevice@DrDrive@@UEAAHXZ`
- size: `41`
- prototype: `__int64 __fastcall(DrDrive *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006560`
- `0x1400163f0`

## pseudocode

```c
__int64 __fastcall DrDrive::ShouldCreateDevice(DrDrive *this)
{
  if ( (*(_DWORD *)(*((_QWORD *)this + 4) + 592LL) & 0x10) != 0 )
    return 0;
  else
    return (*(__int64 (__fastcall **)(DrDrive *))(*(_QWORD *)this + 40LL))(this);
}

```

## disassembly

```asm
0x1400163f0  sub     rsp, 28h
0x1400163f4  mov     rax, [rcx+20h]
0x1400163f8  mov     edx, [rax+250h]
0x1400163fe  test    dl, 10h
0x140016401  jnz     short loc_140016411
0x140016403  mov     rax, [rcx]
0x140016406  mov     rax, [rax+28h]
0x14001640a  call    _guard_dispatch_icall
0x14001640f  jmp     short loc_140016413
0x140016411  xor     eax, eax
0x140016413  add     rsp, 28h
0x140016417  retn
```
