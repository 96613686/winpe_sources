# VmbusTlMapSystemIdToPartitionId

- ea: `0x140006f1c`
- end: `0x140006f8a`
- name: `VmbusTlMapSystemIdToPartitionId`
- size: `110`
- prototype: `char __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14001a790`
- `0x14001a9f0`
- `0x14001d728`
- `0x14001febc`

## callees

- `0x140006f1c`
- `0x14000bfa0`
- `0x140018a88`
- `0x1400190c8`

## pseudocode

```c
char __fastcall VmbusTlMapSystemIdToPartitionId(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int128 v4; // xmm1
  char result; // al
  __int128 v6; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v7[3]; // [rsp+30h] [rbp-48h] BYREF
  int v8; // [rsp+60h] [rbp-18h]

  memset(v7, 0, sizeof(v7));
  v8 = 0;
  if ( (int)HvSocketLookupSystemId(a1, a2, (__int64)v7) < 0 )
    return 0;
  v4 = *HvsocketAddressInfoToPartitionId(&v6, (__int64)v7);
  result = 1;
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x140006f1c  push    rbx
0x140006f1e  sub     rsp, 70h
0x140006f22  mov     rax, cs:__security_cookie
0x140006f29  xor     rax, rsp
0x140006f2c  mov     [rsp+78h+var_10], rax
0x140006f31  xorps   xmm0, xmm0
0x140006f34  mov     rbx, r8
0x140006f37  xor     eax, eax
0x140006f39  lea     r8, [rsp+78h+var_48]
0x140006f3e  movups  [rsp+78h+var_48], xmm0
0x140006f43  mov     [rsp+78h+var_18], eax
0x140006f47  movups  [rsp+78h+var_38], xmm0
0x140006f4c  movups  [rsp+78h+var_28], xmm0
0x140006f51  call    HvSocketLookupSystemId
0x140006f56  test    eax, eax
0x140006f58  js      short loc_140006F74
0x140006f5a  lea     rdx, [rsp+78h+var_48]
0x140006f5f  lea     rcx, [rsp+78h+var_58]
0x140006f64  call    HvsocketAddressInfoToPartitionId
0x140006f69  movups  xmm1, xmmword ptr [rax]
0x140006f6c  mov     al, 1
0x140006f6e  movdqu  xmmword ptr [rbx], xmm1
0x140006f72  jmp     short loc_140006F76
0x140006f74  xor     al, al
0x140006f76  mov     rcx, [rsp+78h+var_10]
0x140006f7b  xor     rcx, rsp; StackCookie
0x140006f7e  call    __security_check_cookie
0x140006f83  add     rsp, 70h
0x140006f87  pop     rbx
0x140006f88  retn
```
