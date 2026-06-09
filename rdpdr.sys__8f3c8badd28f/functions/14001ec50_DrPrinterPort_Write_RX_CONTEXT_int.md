# DrPrinterPort::Write(_RX_CONTEXT *,int)

- ea: `0x14001ec50`
- end: `0x14001ec89`
- name: `?Write@DrPrinterPort@@UEAAJPEAU_RX_CONTEXT@@H@Z`
- size: `57`
- prototype: `__int64 __fastcall(DrPrinterPort *__hidden this, struct _RX_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001ec50`
- `0x14001f900`

## pseudocode

```c
__int64 __fastcall DrPrinterPort::Write(DrPrinterPort *this, struct _RX_CONTEXT *a2)
{
  __int64 result; // rax
  int v5; // ecx

  result = DrDevice::Write(this, a2, 0);
  v5 = *((_DWORD *)this + 23);
  if ( v5 >= 0 )
    *((_DWORD *)this + 23) = v5 + *((_DWORD *)&a2->9 + 42);
  return result;
}

```

## disassembly

```asm
0x14001ec50  mov     [rsp+arg_0], rbx
0x14001ec55  push    rdi
0x14001ec56  sub     rsp, 20h
0x14001ec5a  xor     r8d, r8d; int
0x14001ec5d  mov     rdi, rdx
0x14001ec60  mov     rbx, rcx
0x14001ec63  call    ?Write@DrDevice@@UEAAJPEAU_RX_CONTEXT@@H@Z; DrDevice::Write(_RX_CONTEXT *,int)
0x14001ec68  mov     ecx, [rbx+5Ch]
0x14001ec6b  test    ecx, ecx
0x14001ec6d  js      short loc_14001EC7D
0x14001ec6f  mov     r8d, [rdi+238h]
0x14001ec76  add     r8d, ecx
0x14001ec79  mov     [rbx+5Ch], r8d
0x14001ec7d  mov     rbx, [rsp+28h+arg_0]
0x14001ec82  add     rsp, 20h
0x14001ec86  pop     rdi
0x14001ec87  retn
```
