# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18000f98c`
- end: `0x18000fa2d`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `161`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, int, __int64)`
- caller_count: `15`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000b82c`
- `0x1800165a4`
- `0x180016a30`
- `0x180016d60`
- `0x180017fe8`
- `0x18001f5f0`
- `0x18001f8e0`
- `0x1800218a4`
- `0x1800227ac`
- `0x1800234ac`
- `0x180024de8`
- `0x180030e74`
- `0x180033480`
- `0x18003592c`
- `0x18004304c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000fa22`
- `ntdll!EtwEventWriteTransfer` at `0x18000fa22`

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
  *(_QWORD *)a6 = off_1800610E0;
  *(_DWORD *)(a6 + 8) = *(unsigned __int16 *)off_1800610E0;
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return ((__int64 (__fastcall *)(REGHANDLE, _DWORD *, _QWORD, _QWORD, int, __int64))EtwEventWriteTransfer)(
           RegHandle,
           v9,
           0,
           0,
           a5,
           a6);
}

```

## disassembly

```asm
0x18000f98c  mov     r11, rsp
0x18000f98f  mov     [r11+20h], r9
0x18000f993  sub     rsp, 48h
0x18000f997  movzx   eax, byte ptr [rdx]
0x18000f99a  xor     r9d, r9d
0x18000f99d  mov     r8, [rsp+48h+arg_28]
0x18000f9a2  shl     eax, 18h
0x18000f9a5  mov     [rsp+48h+var_18], eax
0x18000f9a9  movzx   eax, word ptr [rdx+1]
0x18000f9ad  mov     [rsp+48h+var_14], eax
0x18000f9b1  mov     rax, [rdx+3]
0x18000f9b5  add     rdx, 0Bh
0x18000f9b9  mov     [r11-10h], rax
0x18000f9bd  mov     rax, cs:off_1800610E0
0x18000f9c4  mov     [r8], rax
0x18000f9c7  mov     rax, cs:off_1800610E0
0x18000f9ce  mov     [r11-20h], r8
0x18000f9d2  movzx   ecx, word ptr [rax]
0x18000f9d5  mov     [r8+8], ecx
0x18000f9d9  lea     rcx, _TraceLoggingMetadata
0x18000f9e0  mov     [r8+10h], rdx
0x18000f9e4  mov     dword ptr [r8+0Ch], 2
0x18000f9ec  movzx   eax, word ptr [rdx]
0x18000f9ef  lea     rdx, [r11-18h]
0x18000f9f3  mov     [r8+18h], eax
0x18000f9f7  lea     rax, _TraceLoggingMetadataEnd
0x18000f9fe  sub     eax, ecx
0x18000fa00  mov     dword ptr [r8+1Ch], 1
0x18000fa08  mov     [rsp+48h+arg_18], eax
0x18000fa0c  xor     r8d, r8d
0x18000fa0f  mov     eax, [rsp+48h+arg_18]
0x18000fa13  mov     eax, [rsp+48h+arg_20]
0x18000fa17  mov     rcx, cs:RegHandle
0x18000fa1e  mov     [rsp+48h+var_28], eax
0x18000fa22  call    cs:__imp_EtwEventWriteTransfer
0x18000fa28  add     rsp, 48h
0x18000fa2c  retn
```
