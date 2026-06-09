# ASN1open_cmp

- ea: `0x18000a530`
- end: `0x18000a56f`
- name: `ASN1open_cmp`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a4f0`

## pseudocode

```c
__int64 __fastcall ASN1open_cmp(__int64 a1, __int64 a2)
{
  _DWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v4; // [rsp+28h] [rbp-20h]
  _DWORD v5[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v6; // [rsp+38h] [rbp-10h]

  v5[1] = 0;
  v3[1] = 0;
  v5[0] = *(_DWORD *)a1;
  v6 = *(_QWORD *)(a1 + 8);
  v3[0] = *(_DWORD *)a2;
  v4 = *(_QWORD *)(a2 + 8);
  return ASN1octetstring_cmp(v5, v3);
}

```

## disassembly

```asm
0x18000a530  mov     r11, rsp
0x18000a533  sub     rsp, 48h
0x18000a537  xor     eax, eax
0x18000a539  mov     [rsp+48h+var_14], eax
0x18000a53d  mov     [rsp+48h+var_24], eax
0x18000a541  mov     eax, [rcx]
0x18000a543  mov     [rsp+48h+var_18], eax
0x18000a547  mov     rax, [rcx+8]
0x18000a54b  lea     rcx, [r11-18h]
0x18000a54f  mov     [r11-10h], rax
0x18000a553  mov     eax, [rdx]
0x18000a555  mov     [rsp+48h+var_28], eax
0x18000a559  mov     rax, [rdx+8]
0x18000a55d  lea     rdx, [r11-28h]
0x18000a561  mov     [r11-20h], rax
0x18000a565  call    ASN1octetstring_cmp
0x18000a56a  add     rsp, 48h
0x18000a56e  retn
```
