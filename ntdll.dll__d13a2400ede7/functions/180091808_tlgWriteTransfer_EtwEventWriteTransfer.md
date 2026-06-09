# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180091808`
- end: `0x1800918a3`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `155`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b0d0`
- `0x1800327c8`
- `0x18008e340`
- `0x1800bf8f4`
- `0x1800e3c38`
- `0x180118654`
- `0x18011a450`
- `0x18011b158`
- `0x18011b2c0`
- `0x18011b3fc`
- `0x18012607c`
- `0x180150188`
- `0x180156f3c`
- `0x180157298`
- `0x18015cb30`
- `0x18015d3f0`
- `0x18015d504`
- `0x18015d800`

## callees

- `0x180092440`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_EtwEventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  _DWORD v9[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+38h] [rbp-10h]

  v9[0] = *a2 << 24;
  v9[1] = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v10 = v6;
  *(_QWORD *)a6 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a6 + 8) = **(unsigned __int16 **)(a1 + 8);
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), (unsigned int)v9, 0, 0, a5, a6);
}

```

## disassembly

```asm
0x180091808  mov     r11, rsp
0x18009180b  mov     [r11+20h], r9
0x18009180f  sub     rsp, 48h
0x180091813  movzx   eax, byte ptr [rdx]
0x180091816  mov     r10, rcx
0x180091819  mov     r8, [rsp+48h+arg_28]
0x18009181e  xor     r9d, r9d
0x180091821  shl     eax, 18h
0x180091824  mov     [rsp+48h+var_18], eax
0x180091828  movzx   eax, word ptr [rdx+1]
0x18009182c  mov     [rsp+48h+var_14], eax
0x180091830  mov     rax, [rdx+3]
0x180091834  add     rdx, 0Bh
0x180091838  mov     [r11-10h], rax
0x18009183c  mov     rax, [rcx+8]
0x180091840  mov     [r8], rax
0x180091843  mov     rax, [rcx+8]
0x180091847  mov     [r11-20h], r8
0x18009184b  movzx   ecx, word ptr [rax]
0x18009184e  mov     [r8+8], ecx
0x180091852  lea     rcx, _TraceLoggingMetadata
0x180091859  mov     [r8+10h], rdx
0x18009185d  mov     dword ptr [r8+0Ch], 2
0x180091865  movzx   eax, word ptr [rdx]
0x180091868  lea     rdx, [r11-18h]
0x18009186c  mov     [r8+18h], eax
0x180091870  lea     rax, _TraceLoggingMetadataEnd
0x180091877  sub     eax, ecx
0x180091879  mov     dword ptr [r8+1Ch], 1
0x180091881  mov     [rsp+48h+arg_18], eax
0x180091885  xor     r8d, r8d
0x180091888  mov     eax, [rsp+48h+arg_18]
0x18009188c  mov     eax, [rsp+48h+arg_20]
0x180091890  mov     rcx, [r10+20h]
0x180091894  mov     [rsp+48h+var_28], eax
0x180091898  call    EtwEventWriteTransfer
0x18009189d  add     rsp, 48h
0x1800918a1  retn
```
