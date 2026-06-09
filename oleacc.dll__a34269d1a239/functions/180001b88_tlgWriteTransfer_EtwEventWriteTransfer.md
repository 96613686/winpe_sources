# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001b88`
- end: `0x180001c1f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013b4`
- `0x180001478`
- `0x18000172c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001c14`
- `ntdll!EtwEventWriteTransfer` at `0x180001c14`

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
0x180001b88  sub     rsp, 48h
0x180001b8c  movzx   eax, byte ptr [rdx]
0x180001b8f  mov     r11, rcx
0x180001b92  shl     eax, 18h
0x180001b95  mov     r10, r8
0x180001b98  mov     r8, [rsp+48h+arg_28]
0x180001b9d  mov     [rsp+48h+var_18], eax
0x180001ba1  movzx   eax, word ptr [rdx+1]
0x180001ba5  mov     [rsp+48h+var_14], eax
0x180001ba9  mov     rax, [rdx+3]
0x180001bad  add     rdx, 0Bh
0x180001bb1  mov     [rsp+48h+var_10], rax
0x180001bb6  mov     rax, [rcx+8]
0x180001bba  mov     [r8], rax
0x180001bbd  mov     rax, [rcx+8]
0x180001bc1  mov     [rsp+48h+var_20], r8
0x180001bc6  movzx   ecx, word ptr [rax]
0x180001bc9  mov     [r8+8], ecx
0x180001bcd  lea     rcx, _TraceLoggingMetadata
0x180001bd4  mov     [r8+10h], rdx
0x180001bd8  mov     dword ptr [r8+0Ch], 2
0x180001be0  movzx   eax, word ptr [rdx]
0x180001be3  lea     rdx, [rsp+48h+var_18]
0x180001be8  mov     [r8+18h], eax
0x180001bec  lea     rax, _TraceLoggingMetadataEnd
0x180001bf3  sub     eax, ecx
0x180001bf5  mov     dword ptr [r8+1Ch], 1
0x180001bfd  mov     dword ptr [rsp+48h+arg_28], eax
0x180001c01  mov     r8, r10
0x180001c04  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001c08  mov     eax, [rsp+48h+arg_20]
0x180001c0c  mov     rcx, [r11+20h]
0x180001c10  mov     [rsp+48h+var_28], eax
0x180001c14  call    cs:__imp_EtwEventWriteTransfer
0x180001c1a  add     rsp, 48h
0x180001c1e  retn
```
