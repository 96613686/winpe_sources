# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180012544`
- end: `0x1800125e2`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800010ac`
- `0x180001184`
- `0x1800011e0`
- `0x180001224`
- `0x18000128c`
- `0x1800012fc`
- `0x18000145c`
- `0x180001550`
- `0x180012420`
- `0x1800124a4`
- `0x18001866c`
- `0x180019f40`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800125d0`
- `ntdll!EtwEventWriteTransfer` at `0x1800125d0`

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
0x180012544  sub     rsp, 48h
0x180012548  movzx   eax, byte ptr [rdx]
0x18001254b  mov     r11, rcx
0x18001254e  shl     eax, 18h
0x180012551  mov     r10, r8
0x180012554  mov     r8, [rsp+48h+arg_28]
0x180012559  mov     [rsp+48h+var_18], eax
0x18001255d  movzx   eax, word ptr [rdx+1]
0x180012561  mov     [rsp+48h+var_14], eax
0x180012565  mov     rax, [rdx+3]
0x180012569  add     rdx, 0Bh
0x18001256d  mov     [rsp+48h+var_10], rax
0x180012572  mov     rax, [rcx+8]
0x180012576  mov     [r8], rax
0x180012579  mov     rax, [rcx+8]
0x18001257d  mov     [rsp+48h+var_20], r8
0x180012582  movzx   ecx, word ptr [rax]
0x180012585  mov     [r8+8], ecx
0x180012589  lea     rcx, _TraceLoggingMetadata
0x180012590  mov     [r8+10h], rdx
0x180012594  mov     dword ptr [r8+0Ch], 2
0x18001259c  movzx   eax, word ptr [rdx]
0x18001259f  lea     rdx, [rsp+48h+var_18]
0x1800125a4  mov     [r8+18h], eax
0x1800125a8  lea     rax, _TraceLoggingMetadataEnd
0x1800125af  sub     eax, ecx
0x1800125b1  mov     dword ptr [r8+1Ch], 1
0x1800125b9  mov     dword ptr [rsp+48h+arg_28], eax
0x1800125bd  mov     r8, r10
0x1800125c0  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800125c4  mov     eax, [rsp+48h+arg_20]
0x1800125c8  mov     rcx, [r11+20h]
0x1800125cc  mov     [rsp+48h+var_28], eax
0x1800125d0  call    cs:__imp_EtwEventWriteTransfer
0x1800125d7  nop     dword ptr [rax+rax+00h]
0x1800125dc  add     rsp, 48h
0x1800125e0  retn
```
