# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001b08`
- end: `0x180001b9f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x18000119c`
- `0x1800012d0`
- `0x1800013cc`
- `0x180001680`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001b94`
- `ntdll!EtwEventWriteTransfer` at `0x180001b94`

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
0x180001b08  sub     rsp, 48h
0x180001b0c  movzx   eax, byte ptr [rdx]
0x180001b0f  mov     r11, rcx
0x180001b12  shl     eax, 18h
0x180001b15  mov     r10, r8
0x180001b18  mov     r8, [rsp+48h+arg_28]
0x180001b1d  mov     [rsp+48h+var_18], eax
0x180001b21  movzx   eax, word ptr [rdx+1]
0x180001b25  mov     [rsp+48h+var_14], eax
0x180001b29  mov     rax, [rdx+3]
0x180001b2d  add     rdx, 0Bh
0x180001b31  mov     [rsp+48h+var_10], rax
0x180001b36  mov     rax, [rcx+8]
0x180001b3a  mov     [r8], rax
0x180001b3d  mov     rax, [rcx+8]
0x180001b41  mov     [rsp+48h+var_20], r8
0x180001b46  movzx   ecx, word ptr [rax]
0x180001b49  mov     [r8+8], ecx
0x180001b4d  lea     rcx, _TraceLoggingMetadata
0x180001b54  mov     [r8+10h], rdx
0x180001b58  mov     dword ptr [r8+0Ch], 2
0x180001b60  movzx   eax, word ptr [rdx]
0x180001b63  lea     rdx, [rsp+48h+var_18]
0x180001b68  mov     [r8+18h], eax
0x180001b6c  lea     rax, _TraceLoggingMetadataEnd
0x180001b73  sub     eax, ecx
0x180001b75  mov     dword ptr [r8+1Ch], 1
0x180001b7d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001b81  mov     r8, r10
0x180001b84  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001b88  mov     eax, [rsp+48h+arg_20]
0x180001b8c  mov     rcx, [r11+20h]
0x180001b90  mov     [rsp+48h+var_28], eax
0x180001b94  call    cs:__imp_EtwEventWriteTransfer
0x180001b9a  add     rsp, 48h
0x180001b9e  retn
```
