# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x1800853a8`
- end: `0x180085443`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `155`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bdd0`
- `0x1800334c8`
- `0x180071890`
- `0x1800bb614`
- `0x1800e38b8`
- `0x180117254`
- `0x180119960`
- `0x18011a668`
- `0x18011a7d0`
- `0x18011a90c`
- `0x18012558c`
- `0x18014f828`
- `0x1801565dc`
- `0x180156938`
- `0x18015c320`
- `0x18015cbe0`
- `0x18015ccf4`
- `0x18015cff0`

## callees

- `0x180085fe0`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_EtwEventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
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
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), (__int64)v9, 0, 0, a5, a6);
}

```

## disassembly

```asm
0x1800853a8  mov     r11, rsp
0x1800853ab  mov     [r11+20h], r9
0x1800853af  sub     rsp, 48h
0x1800853b3  movzx   eax, byte ptr [rdx]
0x1800853b6  mov     r10, rcx
0x1800853b9  mov     r8, [rsp+48h+arg_28]
0x1800853be  xor     r9d, r9d
0x1800853c1  shl     eax, 18h
0x1800853c4  mov     [rsp+48h+var_18], eax
0x1800853c8  movzx   eax, word ptr [rdx+1]
0x1800853cc  mov     [rsp+48h+var_14], eax
0x1800853d0  mov     rax, [rdx+3]
0x1800853d4  add     rdx, 0Bh
0x1800853d8  mov     [r11-10h], rax
0x1800853dc  mov     rax, [rcx+8]
0x1800853e0  mov     [r8], rax
0x1800853e3  mov     rax, [rcx+8]
0x1800853e7  mov     [r11-20h], r8
0x1800853eb  movzx   ecx, word ptr [rax]
0x1800853ee  mov     [r8+8], ecx
0x1800853f2  lea     rcx, _TraceLoggingMetadata
0x1800853f9  mov     [r8+10h], rdx
0x1800853fd  mov     dword ptr [r8+0Ch], 2
0x180085405  movzx   eax, word ptr [rdx]
0x180085408  lea     rdx, [r11-18h]
0x18008540c  mov     [r8+18h], eax
0x180085410  lea     rax, _TraceLoggingMetadataEnd
0x180085417  sub     eax, ecx
0x180085419  mov     dword ptr [r8+1Ch], 1
0x180085421  mov     [rsp+48h+arg_18], eax
0x180085425  xor     r8d, r8d
0x180085428  mov     eax, [rsp+48h+arg_18]
0x18008542c  mov     eax, [rsp+48h+arg_20]
0x180085430  mov     rcx, [r10+20h]
0x180085434  mov     [rsp+48h+var_28], eax
0x180085438  call    EtwEventWriteTransfer
0x18008543d  add     rsp, 48h
0x180085441  retn
```
