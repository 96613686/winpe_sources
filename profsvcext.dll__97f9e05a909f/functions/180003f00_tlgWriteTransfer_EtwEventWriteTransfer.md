# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180003f00`
- end: `0x180003f97`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x1800012bc`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180003f8c`
- `ntdll!EtwEventWriteTransfer` at `0x180003f8c`

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
0x180003f00  sub     rsp, 48h
0x180003f04  movzx   eax, byte ptr [rdx]
0x180003f07  mov     r11, rcx
0x180003f0a  shl     eax, 18h
0x180003f0d  mov     r10, r8
0x180003f10  mov     r8, [rsp+48h+arg_28]
0x180003f15  mov     [rsp+48h+var_18], eax
0x180003f19  movzx   eax, word ptr [rdx+1]
0x180003f1d  mov     [rsp+48h+var_14], eax
0x180003f21  mov     rax, [rdx+3]
0x180003f25  add     rdx, 0Bh
0x180003f29  mov     [rsp+48h+var_10], rax
0x180003f2e  mov     rax, [rcx+8]
0x180003f32  mov     [r8], rax
0x180003f35  mov     rax, [rcx+8]
0x180003f39  mov     [rsp+48h+var_20], r8
0x180003f3e  movzx   ecx, word ptr [rax]
0x180003f41  mov     [r8+8], ecx
0x180003f45  lea     rcx, _TraceLoggingMetadata
0x180003f4c  mov     [r8+10h], rdx
0x180003f50  mov     dword ptr [r8+0Ch], 2
0x180003f58  movzx   eax, word ptr [rdx]
0x180003f5b  lea     rdx, [rsp+48h+var_18]
0x180003f60  mov     [r8+18h], eax
0x180003f64  lea     rax, _TraceLoggingMetadataEnd
0x180003f6b  sub     eax, ecx
0x180003f6d  mov     dword ptr [r8+1Ch], 1
0x180003f75  mov     dword ptr [rsp+48h+arg_28], eax
0x180003f79  mov     r8, r10
0x180003f7c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180003f80  mov     eax, [rsp+48h+arg_20]
0x180003f84  mov     rcx, [r11+20h]
0x180003f88  mov     [rsp+48h+var_28], eax
0x180003f8c  call    cs:__imp_EtwEventWriteTransfer
0x180003f92  add     rsp, 48h
0x180003f96  retn
```
