# DrPrinterPort::ShouldCreatePort(void)

- ea: `0x14001eb30`
- end: `0x14001eb59`
- name: `?ShouldCreatePort@DrPrinterPort@@UEAAHXZ`
- size: `41`
- prototype: `__int64 __fastcall(DrPrinterPort *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006560`
- `0x14001eb30`

## pseudocode

```c
__int64 __fastcall DrPrinterPort::ShouldCreatePort(DrPrinterPort *this)
{
  if ( (*(_DWORD *)(*((_QWORD *)this + 4) + 592LL) & 8) != 0 )
    return 0;
  else
    return (*(__int64 (__fastcall **)(DrPrinterPort *))(*(_QWORD *)this + 40LL))(this);
}

```

## disassembly

```asm
0x14001eb30  sub     rsp, 28h
0x14001eb34  mov     rax, [rcx+20h]
0x14001eb38  mov     edx, [rax+250h]
0x14001eb3e  test    dl, 8
0x14001eb41  jnz     short loc_14001EB51
0x14001eb43  mov     rax, [rcx]
0x14001eb46  mov     rax, [rax+28h]
0x14001eb4a  call    _guard_dispatch_icall
0x14001eb4f  jmp     short loc_14001EB53
0x14001eb51  xor     eax, eax
0x14001eb53  add     rsp, 28h
0x14001eb57  retn
```
