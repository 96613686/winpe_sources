# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18000a0dc`
- end: `0x18000a173`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000a060`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000a168`
- `ntdll!EtwEventWriteTransfer` at `0x18000a168`

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
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v9, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18000a0dc  sub     rsp, 48h
0x18000a0e0  movzx   eax, byte ptr [rdx]
0x18000a0e3  mov     r11, rcx
0x18000a0e6  shl     eax, 18h
0x18000a0e9  mov     r10, r8
0x18000a0ec  mov     r8, [rsp+48h+arg_28]
0x18000a0f1  mov     [rsp+48h+var_18], eax
0x18000a0f5  movzx   eax, word ptr [rdx+1]
0x18000a0f9  mov     [rsp+48h+var_14], eax
0x18000a0fd  mov     rax, [rdx+3]
0x18000a101  add     rdx, 0Bh
0x18000a105  mov     [rsp+48h+var_10], rax
0x18000a10a  mov     rax, [rcx+8]
0x18000a10e  mov     [r8], rax
0x18000a111  mov     rax, [rcx+8]
0x18000a115  mov     [rsp+48h+var_20], r8
0x18000a11a  movzx   ecx, word ptr [rax]
0x18000a11d  mov     [r8+8], ecx
0x18000a121  lea     rcx, _TraceLoggingMetadata
0x18000a128  mov     [r8+10h], rdx
0x18000a12c  mov     dword ptr [r8+0Ch], 2
0x18000a134  movzx   eax, word ptr [rdx]
0x18000a137  lea     rdx, [rsp+48h+var_18]
0x18000a13c  mov     [r8+18h], eax
0x18000a140  lea     rax, _TraceLoggingMetadataEnd
0x18000a147  sub     eax, ecx
0x18000a149  mov     dword ptr [r8+1Ch], 1
0x18000a151  mov     dword ptr [rsp+48h+arg_28], eax
0x18000a155  mov     r8, r10
0x18000a158  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000a15c  mov     eax, [rsp+48h+arg_20]
0x18000a160  mov     rcx, [r11+20h]
0x18000a164  mov     [rsp+48h+var_28], eax
0x18000a168  call    cs:__imp_EtwEventWriteTransfer
0x18000a16e  add     rsp, 48h
0x18000a172  retn
```
