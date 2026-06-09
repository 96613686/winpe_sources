# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18000113c`
- end: `0x1800011dd`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800028c0`
- `0x180002974`
- `0x180002e50`
- `0x1800032c0`
- `0x1800039b0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800011d2`
- `ntdll!EtwEventWriteTransfer` at `0x1800011d2`

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
  *(_QWORD *)a6 = off_1800091B0;
  *(_DWORD *)(a6 + 8) = *(unsigned __int16 *)off_1800091B0;
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return ((__int64 (__fastcall *)(__int64, _DWORD *, _QWORD, _QWORD, int, __int64))EtwEventWriteTransfer)(
           qword_1800091C8,
           v9,
           0,
           0,
           a5,
           a6);
}

```

## disassembly

```asm
0x18000113c  mov     r11, rsp
0x18000113f  mov     [r11+20h], r9
0x180001143  sub     rsp, 48h
0x180001147  movzx   eax, byte ptr [rdx]
0x18000114a  xor     r9d, r9d
0x18000114d  mov     r8, [rsp+48h+arg_28]
0x180001152  shl     eax, 18h
0x180001155  mov     [rsp+48h+var_18], eax
0x180001159  movzx   eax, word ptr [rdx+1]
0x18000115d  mov     [rsp+48h+var_14], eax
0x180001161  mov     rax, [rdx+3]
0x180001165  add     rdx, 0Bh
0x180001169  mov     [r11-10h], rax
0x18000116d  mov     rax, cs:off_1800091B0
0x180001174  mov     [r8], rax
0x180001177  mov     rax, cs:off_1800091B0
0x18000117e  mov     [r11-20h], r8
0x180001182  movzx   ecx, word ptr [rax]
0x180001185  mov     [r8+8], ecx
0x180001189  lea     rcx, _TraceLoggingMetadata
0x180001190  mov     [r8+10h], rdx
0x180001194  mov     dword ptr [r8+0Ch], 2
0x18000119c  movzx   eax, word ptr [rdx]
0x18000119f  lea     rdx, [r11-18h]
0x1800011a3  mov     [r8+18h], eax
0x1800011a7  lea     rax, _TraceLoggingMetadataEnd
0x1800011ae  sub     eax, ecx
0x1800011b0  mov     dword ptr [r8+1Ch], 1
0x1800011b8  mov     [rsp+48h+arg_18], eax
0x1800011bc  xor     r8d, r8d
0x1800011bf  mov     eax, [rsp+48h+arg_18]
0x1800011c3  mov     eax, [rsp+48h+arg_20]
0x1800011c7  mov     rcx, cs:qword_1800091C8
0x1800011ce  mov     [rsp+48h+var_28], eax
0x1800011d2  call    cs:__imp_EtwEventWriteTransfer
0x1800011d8  add     rsp, 48h
0x1800011dc  retn
```
