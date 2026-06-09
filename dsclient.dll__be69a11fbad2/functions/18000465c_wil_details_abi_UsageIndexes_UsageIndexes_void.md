# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x18000465c`
- end: `0x1800046ca`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004534`
- `0x180006b68`
- `0x1800071dc`

## callees

- `0x1800045a0`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r9
  __int64 v6; // r9
  __int16 v7; // r11
  __int16 v9; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  char v12; // [rsp+28h] [rbp-10h]
  int v13; // [rsp+28h] [rbp-10h]
  int v14; // [rsp+28h] [rbp-10h]

  v12 = 0;
  v9 = 4;
  LOBYTE(a4) = 1;
  wil::details_abi::RawUsageIndex::RawUsageIndex(this, 0, 4, a4, v9, v12);
  LOBYTE(v13) = 2;
  LOWORD(v10) = 4;
  wil::details_abi::RawUsageIndex::RawUsageIndex((char *)this + 64, 0, 4, v5, v10, v13);
  LOBYTE(v14) = v6;
  LOWORD(v11) = v7;
  wil::details_abi::RawUsageIndex::RawUsageIndex((char *)this + 128, 0, 4, v6, v11, v14);
  return this;
}

```

## disassembly

```asm
0x18000465c  mov     [rsp+arg_0], rbx
0x180004661  push    rdi
0x180004662  sub     rsp, 30h
0x180004666  mov     edi, 4
0x18000466b  xor     r11d, r11d
0x18000466e  mov     r8d, edi
0x180004671  mov     byte ptr [rsp+38h+var_10], r11b
0x180004676  xor     edx, edx
0x180004678  mov     [rsp+38h+var_18], di
0x18000467d  mov     r9b, 1
0x180004680  mov     rbx, rcx
0x180004683  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x180004688  mov     r8d, edi
0x18000468b  mov     byte ptr [rsp+38h+var_10], 2
0x180004690  xor     edx, edx
0x180004692  mov     [rsp+38h+var_18], di
0x180004697  lea     rcx, [rbx+40h]
0x18000469b  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x1800046a0  mov     r8d, edi
0x1800046a3  mov     byte ptr [rsp+38h+var_10], r9b
0x1800046a8  xor     edx, edx
0x1800046aa  mov     [rsp+38h+var_18], r11w
0x1800046b0  lea     rcx, [rbx+80h]
0x1800046b7  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x1800046bc  mov     rax, rbx
0x1800046bf  mov     rbx, [rsp+38h+arg_0]
0x1800046c4  add     rsp, 30h
0x1800046c8  pop     rdi
0x1800046c9  retn
```
