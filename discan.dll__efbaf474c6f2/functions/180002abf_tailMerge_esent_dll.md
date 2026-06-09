# __tailMerge_esent_dll

- ea: `0x180002abf`
- end: `0x180002b38`
- name: `__tailMerge_esent_dll`
- size: `121`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b3e`
- `0x180002b50`
- `0x180002b62`
- `0x180002b74`
- `0x180002b86`
- `0x180002b98`
- `0x180002baa`
- `0x180002bbc`
- `0x180002bce`
- `0x180002be0`
- `0x180002bf2`
- `0x180002c04`
- `0x180002c16`
- `0x180002c28`
- `0x180002c3a`
- `0x180002c4c`
- `0x180002c5e`
- `0x180002c70`
- `0x180002c82`
- `0x180002c94`
- `0x180002ca6`
- `0x180002cb8`
- `0x180002cca`
- `0x180002cdc`
- `0x180002cee`
- `0x180002d00`
- `0x180002d12`
- `0x180002d24`
- `0x180002d36`
- `0x180002d48`

## callees

- `0x180002abf`
- `0x180036f50`

## pseudocode

```c
__int64 __fastcall _tailMerge_esent_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_esent_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002abf  mov     [rsp+arg_0], rcx
0x180002ac4  mov     [rsp+arg_8], rdx
0x180002ac9  mov     [rsp+arg_10], r8
0x180002ace  mov     [rsp+arg_18], r9
0x180002ad3  sub     rsp, 68h
0x180002ad7  movdqa  [rsp+68h+var_48], xmm0
0x180002add  movdqa  [rsp+68h+var_38], xmm1
0x180002ae3  movdqa  [rsp+68h+var_28], xmm2
0x180002ae9  movdqa  [rsp+68h+var_18], xmm3
0x180002aef  mov     rdx, rax
0x180002af2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_esent_dll
0x180002af9  call    __delayLoadHelper2
0x180002afe  movdqa  xmm0, [rsp+68h+var_48]
0x180002b04  movdqa  xmm1, [rsp+68h+var_38]
0x180002b0a  movdqa  xmm2, [rsp+68h+var_28]
0x180002b10  movdqa  xmm3, [rsp+68h+var_18]
0x180002b16  mov     rcx, [rsp+68h+arg_0]
0x180002b1b  mov     rdx, [rsp+68h+arg_8]
0x180002b20  mov     r8, [rsp+68h+arg_10]
0x180002b28  mov     r9, [rsp+68h+arg_18]
0x180002b30  add     rsp, 68h
0x180002b34  jmp     short $+2
0x180002b36  jmp     rax
```
