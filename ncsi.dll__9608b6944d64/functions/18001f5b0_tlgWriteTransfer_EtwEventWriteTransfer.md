# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18001f5b0`
- end: `0x18001f663`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `179`
- prototype: ``
- caller_count: `70`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x18000175c`
- `0x180001874`
- `0x180001a74`
- `0x180002268`
- `0x1800028b4`
- `0x180002994`
- `0x180002a84`
- `0x180002b74`
- `0x180002ce0`
- `0x180002d64`
- `0x1800034bc`
- `0x180003c20`
- `0x180003cf8`
- `0x180003da4`
- `0x180003e78`
- `0x180003f54`
- `0x180004000`
- `0x1800040c4`
- `0x1800041b4`
- `0x1800043bc`
- `0x180004450`
- `0x1800044f0`
- `0x1800045a0`
- `0x180004640`
- `0x180004710`
- `0x180004830`
- `0x180004914`
- `0x180004a0c`
- `0x180004ae8`
- `0x180004b84`
- `0x180004c48`
- `0x180004ca8`
- `0x180004f5c`
- `0x180005254`
- `0x18000531c`
- `0x1800053e0`
- `0x180005460`
- `0x180005cb4`
- `0x180006690`
- `0x180006770`
- `0x180006818`
- `0x180006894`
- `0x180006958`
- `0x180006a2c`
- `0x180006ae4`
- `0x180006bd8`
- `0x180006c9c`
- `0x180006d6c`
- `0x180006e74`

## callees

- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001f64b`
- `ntdll!EtwEventWriteTransfer` at `0x18001f64b`

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
  _DWORD v9[2]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]

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
0x18001f5b0  sub     rsp, 58h
0x18001f5b4  mov     rax, cs:__security_cookie
0x18001f5bb  xor     rax, rsp
0x18001f5be  mov     [rsp+58h+var_10], rax
0x18001f5c3  movzx   eax, byte ptr [rdx]
0x18001f5c6  mov     r11, rcx
0x18001f5c9  mov     r10, [rsp+58h+arg_28]
0x18001f5d1  shl     eax, 18h
0x18001f5d4  mov     [rsp+58h+var_20], eax
0x18001f5d8  movzx   eax, word ptr [rdx+1]
0x18001f5dc  mov     [rsp+58h+var_1C], eax
0x18001f5e0  mov     rax, [rdx+3]
0x18001f5e4  add     rdx, 0Bh
0x18001f5e8  mov     [rsp+58h+var_18], rax
0x18001f5ed  mov     rax, [rcx+8]
0x18001f5f1  mov     [r10], rax
0x18001f5f4  mov     rax, [rcx+8]
0x18001f5f8  mov     [rsp+58h+var_30], r10
0x18001f5fd  movzx   ecx, word ptr [rax]
0x18001f600  mov     [r10+8], ecx
0x18001f604  lea     rcx, _TraceLoggingMetadata
0x18001f60b  mov     [r10+10h], rdx
0x18001f60f  mov     dword ptr [r10+0Ch], 2
0x18001f617  movzx   eax, word ptr [rdx]
0x18001f61a  lea     rdx, [rsp+58h+var_20]
0x18001f61f  mov     [r10+18h], eax
0x18001f623  lea     rax, _TraceLoggingMetadataEnd
0x18001f62a  sub     eax, ecx
0x18001f62c  mov     dword ptr [r10+1Ch], 1
0x18001f634  mov     [rsp+58h+var_28], eax
0x18001f638  mov     eax, [rsp+58h+var_28]
0x18001f63c  mov     eax, [rsp+58h+arg_20]
0x18001f643  mov     rcx, [r11+20h]
0x18001f647  mov     [rsp+58h+var_38], eax
0x18001f64b  call    cs:__imp_EtwEventWriteTransfer
0x18001f651  mov     rcx, [rsp+58h+var_10]
0x18001f656  xor     rcx, rsp; StackCookie
0x18001f659  call    __security_check_cookie
0x18001f65e  add     rsp, 58h
0x18001f662  retn
```
