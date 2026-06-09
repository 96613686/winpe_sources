# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x1800835f4`
- end: `0x18008368b`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x180001168`
- `0x18000120c`
- `0x1800012a0`
- `0x180062274`
- `0x1800640dc`
- `0x1800834e8`
- `0x18008357c`
- `0x1800946ac`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180083680`
- `ntdll!EtwEventWriteTransfer` at `0x180083680`

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
0x1800835f4  sub     rsp, 48h
0x1800835f8  movzx   eax, byte ptr [rdx]
0x1800835fb  mov     r11, rcx
0x1800835fe  shl     eax, 18h
0x180083601  mov     r10, r8
0x180083604  mov     r8, [rsp+48h+arg_28]
0x180083609  mov     [rsp+48h+var_18], eax
0x18008360d  movzx   eax, word ptr [rdx+1]
0x180083611  mov     [rsp+48h+var_14], eax
0x180083615  mov     rax, [rdx+3]
0x180083619  add     rdx, 0Bh
0x18008361d  mov     [rsp+48h+var_10], rax
0x180083622  mov     rax, [rcx+8]
0x180083626  mov     [r8], rax
0x180083629  mov     rax, [rcx+8]
0x18008362d  mov     [rsp+48h+var_20], r8
0x180083632  movzx   ecx, word ptr [rax]
0x180083635  mov     [r8+8], ecx
0x180083639  lea     rcx, _TraceLoggingMetadata
0x180083640  mov     [r8+10h], rdx
0x180083644  mov     dword ptr [r8+0Ch], 2
0x18008364c  movzx   eax, word ptr [rdx]
0x18008364f  lea     rdx, [rsp+48h+var_18]
0x180083654  mov     [r8+18h], eax
0x180083658  lea     rax, _TraceLoggingMetadataEnd
0x18008365f  sub     eax, ecx
0x180083661  mov     dword ptr [r8+1Ch], 1
0x180083669  mov     dword ptr [rsp+48h+arg_28], eax
0x18008366d  mov     r8, r10
0x180083670  mov     eax, dword ptr [rsp+48h+arg_28]
0x180083674  mov     eax, [rsp+48h+arg_20]
0x180083678  mov     rcx, [r11+20h]
0x18008367c  mov     [rsp+48h+var_28], eax
0x180083680  call    cs:__imp_EtwEventWriteTransfer
0x180083686  add     rsp, 48h
0x18008368a  retn
```
