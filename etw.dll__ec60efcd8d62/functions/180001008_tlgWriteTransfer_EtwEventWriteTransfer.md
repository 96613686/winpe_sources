# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001008`
- end: `0x18000109f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `44`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002ec4`
- `0x180003944`
- `0x1800039e8`
- `0x180003a8c`
- `0x180003b58`
- `0x180003c24`
- `0x180003cf0`
- `0x180003d94`
- `0x180003e60`
- `0x180003f04`
- `0x180006520`
- `0x180006740`
- `0x180006970`
- `0x180006c60`
- `0x180007060`
- `0x180007500`
- `0x180007cc0`
- `0x1800080f0`
- `0x180008330`
- `0x18000861c`
- `0x1800086c0`
- `0x180008764`
- `0x180008808`
- `0x1800088ac`
- `0x180008988`
- `0x180008a2c`
- `0x180008b10`
- `0x180008bb4`
- `0x180008c58`
- `0x180008d3c`
- `0x1800099c0`
- `0x18000a300`
- `0x18000ad70`
- `0x18000b5f0`
- `0x18000b970`
- `0x18000bbe0`
- `0x18000bf60`
- `0x18000c2a0`
- `0x18000c3a0`
- `0x18000c4a0`
- `0x18000cca0`
- `0x18000d780`
- `0x18000de40`
- `0x180012674`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001094`
- `ntdll!EtwEventWriteTransfer` at `0x180001094`

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
0x180001008  sub     rsp, 48h
0x18000100c  movzx   eax, byte ptr [rdx]
0x18000100f  mov     r11, rcx
0x180001012  shl     eax, 18h
0x180001015  mov     r10, r8
0x180001018  mov     r8, [rsp+48h+arg_28]
0x18000101d  mov     [rsp+48h+var_18], eax
0x180001021  movzx   eax, word ptr [rdx+1]
0x180001025  mov     [rsp+48h+var_14], eax
0x180001029  mov     rax, [rdx+3]
0x18000102d  add     rdx, 0Bh
0x180001031  mov     [rsp+48h+var_10], rax
0x180001036  mov     rax, [rcx+8]
0x18000103a  mov     [r8], rax
0x18000103d  mov     rax, [rcx+8]
0x180001041  mov     [rsp+48h+var_20], r8
0x180001046  movzx   ecx, word ptr [rax]
0x180001049  mov     [r8+8], ecx
0x18000104d  lea     rcx, _TraceLoggingMetadata
0x180001054  mov     [r8+10h], rdx
0x180001058  mov     dword ptr [r8+0Ch], 2
0x180001060  movzx   eax, word ptr [rdx]
0x180001063  lea     rdx, [rsp+48h+var_18]
0x180001068  mov     [r8+18h], eax
0x18000106c  lea     rax, _TraceLoggingMetadataEnd
0x180001073  sub     eax, ecx
0x180001075  mov     dword ptr [r8+1Ch], 1
0x18000107d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001081  mov     r8, r10
0x180001084  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001088  mov     eax, [rsp+48h+arg_20]
0x18000108c  mov     rcx, [r11+20h]
0x180001090  mov     [rsp+48h+var_28], eax
0x180001094  call    cs:__imp_EtwEventWriteTransfer
0x18000109a  add     rsp, 48h
0x18000109e  retn
```
