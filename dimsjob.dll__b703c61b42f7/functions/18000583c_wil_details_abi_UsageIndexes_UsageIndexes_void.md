# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x18000583c`
- end: `0x1800058aa`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800076cc`
- `0x180007fa8`
- `0x180008370`

## callees

- `0x1800056b0`

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
0x18000583c  mov     [rsp+arg_0], rbx
0x180005841  push    rdi
0x180005842  sub     rsp, 30h
0x180005846  mov     edi, 4
0x18000584b  xor     r11d, r11d
0x18000584e  mov     r8d, edi
0x180005851  mov     byte ptr [rsp+38h+var_10], r11b
0x180005856  xor     edx, edx
0x180005858  mov     [rsp+38h+var_18], di
0x18000585d  mov     r9b, 1
0x180005860  mov     rbx, rcx
0x180005863  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x180005868  mov     r8d, edi
0x18000586b  mov     byte ptr [rsp+38h+var_10], 2
0x180005870  xor     edx, edx
0x180005872  mov     [rsp+38h+var_18], di
0x180005877  lea     rcx, [rbx+40h]
0x18000587b  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x180005880  mov     r8d, edi
0x180005883  mov     byte ptr [rsp+38h+var_10], r9b
0x180005888  xor     edx, edx
0x18000588a  mov     [rsp+38h+var_18], r11w
0x180005890  lea     rcx, [rbx+80h]
0x180005897  call    ??0RawUsageIndex@details_abi@wil@@QEAA@GGW4CountSize@12@G0@Z; wil::details_abi::RawUsageIndex::RawUsageIndex(ushort,ushort,wil::details_abi::CountSize,ushort,wil::details_abi::CountSize)
0x18000589c  mov     rax, rbx
0x18000589f  mov     rbx, [rsp+38h+arg_0]
0x1800058a4  add     rsp, 30h
0x1800058a8  pop     rdi
0x1800058a9  retn
```
