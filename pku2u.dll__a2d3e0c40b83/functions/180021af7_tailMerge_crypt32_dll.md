# __tailMerge_crypt32_dll

- ea: `0x180021af7`
- end: `0x180021b70`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021b76`
- `0x180021b9a`
- `0x180021bac`
- `0x180021bbe`
- `0x180021bd0`
- `0x180021c91`
- `0x180021d88`
- `0x180021d9a`
- `0x180021dac`
- `0x180021dbe`
- `0x180021dd0`
- `0x180021de2`
- `0x180021df4`
- `0x180021e06`
- `0x180021e18`
- `0x180021e2a`
- `0x180021e3c`
- `0x180021e4e`
- `0x180021e60`
- `0x180021e72`

## callees

- `0x18001a6d0`
- `0x180021af7`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180021af7  mov     [rsp+arg_0], rcx
0x180021afc  mov     [rsp+arg_8], rdx
0x180021b01  mov     [rsp+arg_10], r8
0x180021b06  mov     [rsp+arg_18], r9
0x180021b0b  sub     rsp, 68h
0x180021b0f  movdqa  [rsp+68h+var_48], xmm0
0x180021b15  movdqa  [rsp+68h+var_38], xmm1
0x180021b1b  movdqa  [rsp+68h+var_28], xmm2
0x180021b21  movdqa  [rsp+68h+var_18], xmm3
0x180021b27  mov     rdx, rax
0x180021b2a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180021b31  call    __delayLoadHelper2
0x180021b36  movdqa  xmm0, [rsp+68h+var_48]
0x180021b3c  movdqa  xmm1, [rsp+68h+var_38]
0x180021b42  movdqa  xmm2, [rsp+68h+var_28]
0x180021b48  movdqa  xmm3, [rsp+68h+var_18]
0x180021b4e  mov     rcx, [rsp+68h+arg_0]
0x180021b53  mov     rdx, [rsp+68h+arg_8]
0x180021b58  mov     r8, [rsp+68h+arg_10]
0x180021b60  mov     r9, [rsp+68h+arg_18]
0x180021b68  add     rsp, 68h
0x180021b6c  jmp     short $+2
0x180021b6e  jmp     rax
```
