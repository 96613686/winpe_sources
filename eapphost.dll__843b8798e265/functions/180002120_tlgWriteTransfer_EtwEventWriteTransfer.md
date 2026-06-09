# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180002120`
- end: `0x1800021be`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x18000111c`
- `0x180001304`
- `0x180001528`
- `0x1800015f4`
- `0x1800016e0`
- `0x1800017a8`
- `0x180001870`
- `0x1800019d4`
- `0x180001c88`
- `0x180024c64`
- `0x180025104`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800021ac`
- `ntdll!EtwEventWriteTransfer` at `0x1800021ac`

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
0x180002120  sub     rsp, 48h
0x180002124  movzx   eax, byte ptr [rdx]
0x180002127  mov     r11, rcx
0x18000212a  shl     eax, 18h
0x18000212d  mov     r10, r8
0x180002130  mov     r8, [rsp+48h+arg_28]
0x180002135  mov     [rsp+48h+var_18], eax
0x180002139  movzx   eax, word ptr [rdx+1]
0x18000213d  mov     [rsp+48h+var_14], eax
0x180002141  mov     rax, [rdx+3]
0x180002145  add     rdx, 0Bh
0x180002149  mov     [rsp+48h+var_10], rax
0x18000214e  mov     rax, [rcx+8]
0x180002152  mov     [r8], rax
0x180002155  mov     rax, [rcx+8]
0x180002159  mov     [rsp+48h+var_20], r8
0x18000215e  movzx   ecx, word ptr [rax]
0x180002161  mov     [r8+8], ecx
0x180002165  lea     rcx, _TraceLoggingMetadata
0x18000216c  mov     [r8+10h], rdx
0x180002170  mov     dword ptr [r8+0Ch], 2
0x180002178  movzx   eax, word ptr [rdx]
0x18000217b  lea     rdx, [rsp+48h+var_18]
0x180002180  mov     [r8+18h], eax
0x180002184  lea     rax, _TraceLoggingMetadataEnd
0x18000218b  sub     eax, ecx
0x18000218d  mov     dword ptr [r8+1Ch], 1
0x180002195  mov     dword ptr [rsp+48h+arg_28], eax
0x180002199  mov     r8, r10
0x18000219c  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800021a0  mov     eax, [rsp+48h+arg_20]
0x1800021a4  mov     rcx, [r11+20h]
0x1800021a8  mov     [rsp+48h+var_28], eax
0x1800021ac  call    cs:__imp_EtwEventWriteTransfer
0x1800021b3  nop     dword ptr [rax+rax+00h]
0x1800021b8  add     rsp, 48h
0x1800021bc  retn
```
