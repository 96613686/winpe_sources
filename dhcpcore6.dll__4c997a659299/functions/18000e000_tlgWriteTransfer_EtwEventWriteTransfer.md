# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18000e000`
- end: `0x18000e0a8`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `168`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003cc0`
- `0x180010340`
- `0x1800108f0`
- `0x180010d18`
- `0x18001189c`
- `0x18001225c`
- `0x18002458c`
- `0x180025094`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000e096`
- `ntdll!EtwEventWriteTransfer` at `0x18000e096`

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
  *(_QWORD *)a6 = off_180042050;
  *(_DWORD *)(a6 + 8) = *(unsigned __int16 *)off_180042050;
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return EtwEventWriteTransfer(RegHandle, v9, 0, 0, a5, a6);
}

```

## disassembly

```asm
0x18000e000  mov     r11, rsp
0x18000e003  mov     [r11+20h], r9
0x18000e007  sub     rsp, 48h
0x18000e00b  movzx   eax, byte ptr [rdx]
0x18000e00e  xor     r9d, r9d
0x18000e011  mov     r8, [rsp+48h+arg_28]
0x18000e016  shl     eax, 18h
0x18000e019  mov     [rsp+48h+var_18], eax
0x18000e01d  movzx   eax, word ptr [rdx+1]
0x18000e021  mov     [rsp+48h+var_14], eax
0x18000e025  mov     rax, [rdx+3]
0x18000e029  add     rdx, 0Bh
0x18000e02d  mov     [r11-10h], rax
0x18000e031  mov     rax, cs:off_180042050
0x18000e038  mov     [r8], rax
0x18000e03b  mov     rax, cs:off_180042050
0x18000e042  mov     [r11-20h], r8
0x18000e046  movzx   ecx, word ptr [rax]
0x18000e049  mov     [r8+8], ecx
0x18000e04d  lea     rcx, _TraceLoggingMetadata
0x18000e054  mov     [r8+10h], rdx
0x18000e058  mov     dword ptr [r8+0Ch], 2
0x18000e060  movzx   eax, word ptr [rdx]
0x18000e063  lea     rdx, [r11-18h]
0x18000e067  mov     [r8+18h], eax
0x18000e06b  lea     rax, _TraceLoggingMetadataEnd
0x18000e072  sub     eax, ecx
0x18000e074  mov     dword ptr [r8+1Ch], 1
0x18000e07c  mov     [rsp+48h+arg_18], eax
0x18000e080  xor     r8d, r8d
0x18000e083  mov     eax, [rsp+48h+arg_18]
0x18000e087  mov     eax, [rsp+48h+arg_20]
0x18000e08b  mov     rcx, cs:RegHandle
0x18000e092  mov     [rsp+48h+var_28], eax
0x18000e096  call    cs:__imp_EtwEventWriteTransfer
0x18000e09d  nop     dword ptr [rax+rax+00h]
0x18000e0a2  add     rsp, 48h
0x18000e0a6  retn
```
