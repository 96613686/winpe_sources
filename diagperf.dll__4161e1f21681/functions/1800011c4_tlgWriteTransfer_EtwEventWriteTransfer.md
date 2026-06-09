# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x1800011c4`
- end: `0x18000125b`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001034`
- `0x1800010e0`
- `0x180001264`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001250`
- `ntdll!EtwEventWriteTransfer` at `0x180001250`

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
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v9, a3);
}

```

## disassembly

```asm
0x1800011c4  sub     rsp, 48h
0x1800011c8  movzx   eax, byte ptr [rdx]
0x1800011cb  mov     r11, rcx
0x1800011ce  shl     eax, 18h
0x1800011d1  mov     r10, r8
0x1800011d4  mov     r8, [rsp+48h+arg_28]
0x1800011d9  mov     [rsp+48h+var_18], eax
0x1800011dd  movzx   eax, word ptr [rdx+1]
0x1800011e1  mov     [rsp+48h+var_14], eax
0x1800011e5  mov     rax, [rdx+3]
0x1800011e9  add     rdx, 0Bh
0x1800011ed  mov     [rsp+48h+var_10], rax
0x1800011f2  mov     rax, [rcx+8]
0x1800011f6  mov     [r8], rax
0x1800011f9  mov     rax, [rcx+8]
0x1800011fd  mov     [rsp+48h+var_20], r8
0x180001202  movzx   ecx, word ptr [rax]
0x180001205  mov     [r8+8], ecx
0x180001209  lea     rcx, _TraceLoggingMetadata
0x180001210  mov     [r8+10h], rdx
0x180001214  mov     dword ptr [r8+0Ch], 2
0x18000121c  movzx   eax, word ptr [rdx]
0x18000121f  lea     rdx, [rsp+48h+var_18]
0x180001224  mov     [r8+18h], eax
0x180001228  lea     rax, _TraceLoggingMetadataEnd
0x18000122f  sub     eax, ecx
0x180001231  mov     dword ptr [r8+1Ch], 1
0x180001239  mov     dword ptr [rsp+48h+arg_28], eax
0x18000123d  mov     r8, r10
0x180001240  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001244  mov     eax, [rsp+48h+arg_20]
0x180001248  mov     rcx, [r11+20h]
0x18000124c  mov     [rsp+48h+var_28], eax
0x180001250  call    cs:__imp_EtwEventWriteTransfer
0x180001256  add     rsp, 48h
0x18000125a  retn
```
