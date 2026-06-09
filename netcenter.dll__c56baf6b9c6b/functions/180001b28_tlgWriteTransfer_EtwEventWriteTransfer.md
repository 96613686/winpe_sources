# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001b28`
- end: `0x180001bbf`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001d698`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001bb4`
- `ntdll!EtwEventWriteTransfer` at `0x180001bb4`

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
0x180001b28  sub     rsp, 48h
0x180001b2c  movzx   eax, byte ptr [rdx]
0x180001b2f  mov     r11, rcx
0x180001b32  shl     eax, 18h
0x180001b35  mov     r10, r8
0x180001b38  mov     r8, [rsp+48h+arg_28]
0x180001b3d  mov     [rsp+48h+var_18], eax
0x180001b41  movzx   eax, word ptr [rdx+1]
0x180001b45  mov     [rsp+48h+var_14], eax
0x180001b49  mov     rax, [rdx+3]
0x180001b4d  add     rdx, 0Bh
0x180001b51  mov     [rsp+48h+var_10], rax
0x180001b56  mov     rax, [rcx+8]
0x180001b5a  mov     [r8], rax
0x180001b5d  mov     rax, [rcx+8]
0x180001b61  mov     [rsp+48h+var_20], r8
0x180001b66  movzx   ecx, word ptr [rax]
0x180001b69  mov     [r8+8], ecx
0x180001b6d  lea     rcx, _TraceLoggingMetadata
0x180001b74  mov     [r8+10h], rdx
0x180001b78  mov     dword ptr [r8+0Ch], 2
0x180001b80  movzx   eax, word ptr [rdx]
0x180001b83  lea     rdx, [rsp+48h+var_18]
0x180001b88  mov     [r8+18h], eax
0x180001b8c  lea     rax, _TraceLoggingMetadataEnd
0x180001b93  sub     eax, ecx
0x180001b95  mov     dword ptr [r8+1Ch], 1
0x180001b9d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001ba1  mov     r8, r10
0x180001ba4  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001ba8  mov     eax, [rsp+48h+arg_20]
0x180001bac  mov     rcx, [r11+20h]
0x180001bb0  mov     [rsp+48h+var_28], eax
0x180001bb4  call    cs:__imp_EtwEventWriteTransfer
0x180001bba  add     rsp, 48h
0x180001bbe  retn
```
