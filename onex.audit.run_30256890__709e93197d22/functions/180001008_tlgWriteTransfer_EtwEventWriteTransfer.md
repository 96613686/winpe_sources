# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001008`
- end: `0x1800010a9`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000e888`
- `0x18001bbd8`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000109e`
- `ntdll!EtwEventWriteTransfer` at `0x18000109e`

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
  *(_QWORD *)a6 = off_18003A080;
  *(_DWORD *)(a6 + 8) = *(unsigned __int16 *)off_18003A080;
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return EtwEventWriteTransfer(qword_18003A098, v9, 0, 0, a5, a6);
}

```

## disassembly

```asm
0x180001008  mov     r11, rsp
0x18000100b  mov     [r11+20h], r9
0x18000100f  sub     rsp, 48h
0x180001013  movzx   eax, byte ptr [rdx]
0x180001016  xor     r9d, r9d
0x180001019  mov     r8, [rsp+48h+arg_28]
0x18000101e  shl     eax, 18h
0x180001021  mov     [rsp+48h+var_18], eax
0x180001025  movzx   eax, word ptr [rdx+1]
0x180001029  mov     [rsp+48h+var_14], eax
0x18000102d  mov     rax, [rdx+3]
0x180001031  add     rdx, 0Bh
0x180001035  mov     [r11-10h], rax
0x180001039  mov     rax, cs:off_18003A080
0x180001040  mov     [r8], rax
0x180001043  mov     rax, cs:off_18003A080
0x18000104a  mov     [r11-20h], r8
0x18000104e  movzx   ecx, word ptr [rax]
0x180001051  mov     [r8+8], ecx
0x180001055  lea     rcx, _TraceLoggingMetadata
0x18000105c  mov     [r8+10h], rdx
0x180001060  mov     dword ptr [r8+0Ch], 2
0x180001068  movzx   eax, word ptr [rdx]
0x18000106b  lea     rdx, [r11-18h]
0x18000106f  mov     [r8+18h], eax
0x180001073  lea     rax, _TraceLoggingMetadataEnd
0x18000107a  sub     eax, ecx
0x18000107c  mov     dword ptr [r8+1Ch], 1
0x180001084  mov     [rsp+48h+arg_18], eax
0x180001088  xor     r8d, r8d
0x18000108b  mov     eax, [rsp+48h+arg_18]
0x18000108f  mov     eax, [rsp+48h+arg_20]
0x180001093  mov     rcx, cs:qword_18003A098
0x18000109a  mov     [rsp+48h+var_28], eax
0x18000109e  call    cs:__imp_EtwEventWriteTransfer
0x1800010a4  add     rsp, 48h
0x1800010a8  retn
```
