# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x1800014e0`
- end: `0x180001577`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800013c0`
- `0x180001580`
- `0x18000164c`
- `0x180001ed0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000156c`
- `ntdll!EtwEventWriteTransfer` at `0x18000156c`

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
  return ((__int64 (__fastcall *)(_QWORD, _DWORD *, __int64, __int64, int, __int64))EtwEventWriteTransfer)(
           *(_QWORD *)(a1 + 32),
           v9,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x1800014e0  sub     rsp, 48h
0x1800014e4  movzx   eax, byte ptr [rdx]
0x1800014e7  mov     r11, rcx
0x1800014ea  shl     eax, 18h
0x1800014ed  mov     r10, r8
0x1800014f0  mov     r8, [rsp+48h+arg_28]
0x1800014f5  mov     [rsp+48h+var_18], eax
0x1800014f9  movzx   eax, word ptr [rdx+1]
0x1800014fd  mov     [rsp+48h+var_14], eax
0x180001501  mov     rax, [rdx+3]
0x180001505  add     rdx, 0Bh
0x180001509  mov     [rsp+48h+var_10], rax
0x18000150e  mov     rax, [rcx+8]
0x180001512  mov     [r8], rax
0x180001515  mov     rax, [rcx+8]
0x180001519  mov     [rsp+48h+var_20], r8
0x18000151e  movzx   ecx, word ptr [rax]
0x180001521  mov     [r8+8], ecx
0x180001525  lea     rcx, _TraceLoggingMetadata
0x18000152c  mov     [r8+10h], rdx
0x180001530  mov     dword ptr [r8+0Ch], 2
0x180001538  movzx   eax, word ptr [rdx]
0x18000153b  lea     rdx, [rsp+48h+var_18]
0x180001540  mov     [r8+18h], eax
0x180001544  lea     rax, _TraceLoggingMetadataEnd
0x18000154b  sub     eax, ecx
0x18000154d  mov     dword ptr [r8+1Ch], 1
0x180001555  mov     dword ptr [rsp+48h+arg_28], eax
0x180001559  mov     r8, r10
0x18000155c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001560  mov     eax, [rsp+48h+arg_20]
0x180001564  mov     rcx, [r11+20h]
0x180001568  mov     [rsp+48h+var_28], eax
0x18000156c  call    cs:__imp_EtwEventWriteTransfer
0x180001572  add     rsp, 48h
0x180001576  retn
```
