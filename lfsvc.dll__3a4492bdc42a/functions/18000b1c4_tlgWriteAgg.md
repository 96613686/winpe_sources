# _tlgWriteAgg

- ea: `0x18000b1c4`
- end: `0x18000b249`
- name: `_tlgWriteAgg`
- size: `133`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001158`

## callees

- `0x18000afc8`

## pseudocode

```c
__int64 __fastcall tlgWriteAgg(__int64 a1, unsigned __int8 *a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 v5; // rax
  unsigned __int16 *v6; // rdx
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]

  v8[0] = *a2 << 24;
  v8[1] = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  v9 = v5;
  *(_QWORD *)a5 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a5 + 8) = **(unsigned __int16 **)(a1 + 8);
  *(_QWORD *)(a5 + 16) = v6;
  *(_DWORD *)(a5 + 12) = 2;
  *(_DWORD *)(a5 + 24) = *v6;
  *(_DWORD *)(a5 + 28) = 1;
  return TlgAggregateAbsorbEvent(a1, v8, a4);
}

```

## disassembly

```asm
0x18000b1c4  sub     rsp, 38h
0x18000b1c8  movzx   eax, byte ptr [rdx]
0x18000b1cb  mov     r11, rcx
0x18000b1ce  shl     eax, 18h
0x18000b1d1  mov     r8d, r9d
0x18000b1d4  mov     r9, [rsp+38h+arg_20]
0x18000b1d9  mov     [rsp+38h+var_18], eax
0x18000b1dd  movzx   eax, word ptr [rdx+1]
0x18000b1e1  mov     [rsp+38h+var_14], eax
0x18000b1e5  mov     rax, [rdx+3]
0x18000b1e9  add     rdx, 0Bh
0x18000b1ed  mov     [rsp+38h+var_10], rax
0x18000b1f2  mov     rax, [rcx+8]
0x18000b1f6  mov     [r9], rax
0x18000b1f9  mov     rax, [rcx+8]
0x18000b1fd  movzx   ecx, word ptr [rax]
0x18000b200  mov     [r9+8], ecx
0x18000b204  lea     rcx, _TraceLoggingMetadata
0x18000b20b  mov     [r9+10h], rdx
0x18000b20f  mov     dword ptr [r9+0Ch], 2
0x18000b217  movzx   eax, word ptr [rdx]
0x18000b21a  lea     rdx, [rsp+38h+var_18]
0x18000b21f  mov     [r9+18h], eax
0x18000b223  lea     rax, _TraceLoggingMetadataEnd
0x18000b22a  sub     eax, ecx
0x18000b22c  mov     dword ptr [r9+1Ch], 1
0x18000b234  mov     dword ptr [rsp+38h+arg_20], eax
0x18000b238  mov     rcx, r11
0x18000b23b  mov     eax, dword ptr [rsp+38h+arg_20]
0x18000b23f  call    TlgAggregateAbsorbEvent
0x18000b244  add     rsp, 38h
0x18000b248  retn
```
