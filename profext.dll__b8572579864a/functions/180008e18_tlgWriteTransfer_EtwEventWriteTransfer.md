# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180008e18`
- end: `0x180008eb6`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800013e4`
- `0x180008cec`
- `0x18001317c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180008ea4`
- `ntdll!EtwEventWriteTransfer` at `0x180008ea4`

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
0x180008e18  sub     rsp, 48h
0x180008e1c  movzx   eax, byte ptr [rdx]
0x180008e1f  mov     r11, rcx
0x180008e22  shl     eax, 18h
0x180008e25  mov     r10, r8
0x180008e28  mov     r8, [rsp+48h+arg_28]
0x180008e2d  mov     [rsp+48h+var_18], eax
0x180008e31  movzx   eax, word ptr [rdx+1]
0x180008e35  mov     [rsp+48h+var_14], eax
0x180008e39  mov     rax, [rdx+3]
0x180008e3d  add     rdx, 0Bh
0x180008e41  mov     [rsp+48h+var_10], rax
0x180008e46  mov     rax, [rcx+8]
0x180008e4a  mov     [r8], rax
0x180008e4d  mov     rax, [rcx+8]
0x180008e51  mov     [rsp+48h+var_20], r8
0x180008e56  movzx   ecx, word ptr [rax]
0x180008e59  mov     [r8+8], ecx
0x180008e5d  lea     rcx, _TraceLoggingMetadata
0x180008e64  mov     [r8+10h], rdx
0x180008e68  mov     dword ptr [r8+0Ch], 2
0x180008e70  movzx   eax, word ptr [rdx]
0x180008e73  lea     rdx, [rsp+48h+var_18]
0x180008e78  mov     [r8+18h], eax
0x180008e7c  lea     rax, _TraceLoggingMetadataEnd
0x180008e83  sub     eax, ecx
0x180008e85  mov     dword ptr [r8+1Ch], 1
0x180008e8d  mov     dword ptr [rsp+48h+arg_28], eax
0x180008e91  mov     r8, r10
0x180008e94  mov     eax, dword ptr [rsp+48h+arg_28]
0x180008e98  mov     eax, [rsp+48h+arg_20]
0x180008e9c  mov     rcx, [r11+20h]
0x180008ea0  mov     [rsp+48h+var_28], eax
0x180008ea4  call    cs:__imp_EtwEventWriteTransfer
0x180008eab  nop     dword ptr [rax+rax+00h]
0x180008eb0  add     rsp, 48h
0x180008eb4  retn
```
