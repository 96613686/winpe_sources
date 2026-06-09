# ValidateWritePointer

- ea: `0x180003e80`
- end: `0x180003eaf`
- name: `ValidateWritePointer`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x180002470`
- `0x180002540`
- `0x180002b00`
- `0x180002e70`
- `0x180003560`
- `0x1800037b0`
- `0x1800039a0`
- `0x180003b40`
- `0x180005990`
- `0x180007790`
- `0x180007ef0`
- `0x180008160`
- `0x180008c00`
- `0x18000b140`
- `0x18000b2c0`
- `0x18000b360`
- `0x18000b7d0`
- `0x18000b8d0`
- `0x18000bba0`
- `0x18000bca0`
- `0x18000c040`
- `0x18000c130`
- `0x18000c350`
- `0x18000cdf0`
- `0x18000cef0`
- `0x18000cfe0`
- `0x18000d6c0`
- `0x18000d7b0`
- `0x18000da50`
- `0x1800116d0`
- `0x1800119c0`
- `0x180011d40`

## callees

- `0x180003e80`

## pseudocode

```c
__int64 __fastcall ValidateWritePointer(_BYTE *a1, int a2)
{
  *a1 = *a1;
  a1[a2 - 1] = a1[a2 - 1];
  return 1;
}

```

## disassembly

```asm
0x180003e80  movzx   eax, byte ptr [rcx]
0x180003e83  mov     [rsp+arg_10], al
0x180003e87  movzx   eax, [rsp+arg_10]
0x180003e8c  mov     [rcx], al
0x180003e8e  lea     eax, [rdx-1]
0x180003e91  mov     edx, eax
0x180003e93  movzx   eax, byte ptr [rax+rcx]
0x180003e97  mov     [rsp+arg_10], al
0x180003e9b  movzx   eax, [rsp+arg_10]
0x180003ea0  mov     [rdx+rcx], al
0x180003ea3  jmp     short loc_180003EA9
0x180003ea5  xor     eax, eax
0x180003ea7  jmp     short locret_180003EAE
0x180003ea9  mov     eax, 1
0x180003eae  retn
```
