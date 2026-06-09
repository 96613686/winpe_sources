# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180002108`
- end: `0x18000219f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180001118`
- `0x180001300`
- `0x180001524`
- `0x1800015f0`
- `0x1800016dc`
- `0x1800017a4`
- `0x18000186c`
- `0x1800019cc`
- `0x180001c80`
- `0x180023f90`
- `0x18002442c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180002194`
- `ntdll!EtwEventWriteTransfer` at `0x180002194`

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
0x180002108  sub     rsp, 48h
0x18000210c  movzx   eax, byte ptr [rdx]
0x18000210f  mov     r11, rcx
0x180002112  shl     eax, 18h
0x180002115  mov     r10, r8
0x180002118  mov     r8, [rsp+48h+arg_28]
0x18000211d  mov     [rsp+48h+var_18], eax
0x180002121  movzx   eax, word ptr [rdx+1]
0x180002125  mov     [rsp+48h+var_14], eax
0x180002129  mov     rax, [rdx+3]
0x18000212d  add     rdx, 0Bh
0x180002131  mov     [rsp+48h+var_10], rax
0x180002136  mov     rax, [rcx+8]
0x18000213a  mov     [r8], rax
0x18000213d  mov     rax, [rcx+8]
0x180002141  mov     [rsp+48h+var_20], r8
0x180002146  movzx   ecx, word ptr [rax]
0x180002149  mov     [r8+8], ecx
0x18000214d  lea     rcx, _TraceLoggingMetadata
0x180002154  mov     [r8+10h], rdx
0x180002158  mov     dword ptr [r8+0Ch], 2
0x180002160  movzx   eax, word ptr [rdx]
0x180002163  lea     rdx, [rsp+48h+var_18]
0x180002168  mov     [r8+18h], eax
0x18000216c  lea     rax, _TraceLoggingMetadataEnd
0x180002173  sub     eax, ecx
0x180002175  mov     dword ptr [r8+1Ch], 1
0x18000217d  mov     dword ptr [rsp+48h+arg_28], eax
0x180002181  mov     r8, r10
0x180002184  mov     eax, dword ptr [rsp+48h+arg_28]
0x180002188  mov     eax, [rsp+48h+arg_20]
0x18000218c  mov     rcx, [r11+20h]
0x180002190  mov     [rsp+48h+var_28], eax
0x180002194  call    cs:__imp_EtwEventWriteTransfer
0x18000219a  add     rsp, 48h
0x18000219e  retn
```
