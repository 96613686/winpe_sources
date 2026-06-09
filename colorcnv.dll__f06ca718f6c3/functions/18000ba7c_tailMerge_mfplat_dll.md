# __tailMerge_mfplat_dll

- ea: `0x18000ba7c`
- end: `0x18000baf5`
- name: `__tailMerge_mfplat_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bafb`

## callees

- `0x1800089e0`
- `0x18000ba7c`

## pseudocode

```c
__int64 __fastcall _tailMerge_mfplat_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_mfplat_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ba7c  mov     [rsp+arg_0], rcx
0x18000ba81  mov     [rsp+arg_8], rdx
0x18000ba86  mov     [rsp+arg_10], r8
0x18000ba8b  mov     [rsp+arg_18], r9
0x18000ba90  sub     rsp, 68h
0x18000ba94  movdqa  [rsp+68h+var_48], xmm0
0x18000ba9a  movdqa  [rsp+68h+var_38], xmm1
0x18000baa0  movdqa  [rsp+68h+var_28], xmm2
0x18000baa6  movdqa  [rsp+68h+var_18], xmm3
0x18000baac  mov     rdx, rax
0x18000baaf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mfplat_dll
0x18000bab6  call    __delayLoadHelper2
0x18000babb  movdqa  xmm0, [rsp+68h+var_48]
0x18000bac1  movdqa  xmm1, [rsp+68h+var_38]
0x18000bac7  movdqa  xmm2, [rsp+68h+var_28]
0x18000bacd  movdqa  xmm3, [rsp+68h+var_18]
0x18000bad3  mov     rcx, [rsp+68h+arg_0]
0x18000bad8  mov     rdx, [rsp+68h+arg_8]
0x18000badd  mov     r8, [rsp+68h+arg_10]
0x18000bae5  mov     r9, [rsp+68h+arg_18]
0x18000baed  add     rsp, 68h
0x18000baf1  jmp     short $+2
0x18000baf3  jmp     rax
```
