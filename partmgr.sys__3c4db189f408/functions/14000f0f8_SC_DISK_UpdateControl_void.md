# SC_DISK::UpdateControl(void)

- ea: `0x14000f0f8`
- end: `0x14000f12a`
- name: `?UpdateControl@SC_DISK@@QEAAJXZ`
- size: `50`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14002208c`
- `0x1400221e4`

## callees

- `0x140010f60`

## pseudocode

```c
__int64 __fastcall SC_DISK::UpdateControl(SC_DISK *this)
{
  return (*(__int64 (__fastcall **)(SC_DISK *, __int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 16LL))(
           this,
           459072,
           0,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x14000f0f8  sub     rsp, 48h
0x14000f0fc  mov     rax, [rcx]
0x14000f0ff  xor     r9d, r9d
0x14000f102  mov     [rsp+48h+var_20], 0
0x14000f10a  xor     r8d, r8d
0x14000f10d  mov     edx, 70140h
0x14000f112  mov     [rsp+48h+var_28], 0
0x14000f11b  mov     rax, [rax+10h]
0x14000f11f  call    _guard_dispatch_icall
0x14000f124  add     rsp, 48h
0x14000f128  retn
```
