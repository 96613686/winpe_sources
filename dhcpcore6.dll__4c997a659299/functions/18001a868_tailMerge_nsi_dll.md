# __tailMerge_nsi_dll

- ea: `0x18001a868`
- end: `0x18001a8e1`
- name: `__tailMerge_nsi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a8e7`
- `0x18001a8f9`
- `0x18001a90b`
- `0x18001acab`
- `0x18001acbd`

## callees

- `0x18000f880`
- `0x18001a868`

## pseudocode

```c
__int64 __fastcall _tailMerge_nsi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_nsi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a868  mov     [rsp+arg_0], rcx
0x18001a86d  mov     [rsp+arg_8], rdx
0x18001a872  mov     [rsp+arg_10], r8
0x18001a877  mov     [rsp+arg_18], r9
0x18001a87c  sub     rsp, 68h
0x18001a880  movdqa  [rsp+68h+var_48], xmm0
0x18001a886  movdqa  [rsp+68h+var_38], xmm1
0x18001a88c  movdqa  [rsp+68h+var_28], xmm2
0x18001a892  movdqa  [rsp+68h+var_18], xmm3
0x18001a898  mov     rdx, rax
0x18001a89b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_nsi_dll
0x18001a8a2  call    __delayLoadHelper2
0x18001a8a7  movdqa  xmm0, [rsp+68h+var_48]
0x18001a8ad  movdqa  xmm1, [rsp+68h+var_38]
0x18001a8b3  movdqa  xmm2, [rsp+68h+var_28]
0x18001a8b9  movdqa  xmm3, [rsp+68h+var_18]
0x18001a8bf  mov     rcx, [rsp+68h+arg_0]
0x18001a8c4  mov     rdx, [rsp+68h+arg_8]
0x18001a8c9  mov     r8, [rsp+68h+arg_10]
0x18001a8d1  mov     r9, [rsp+68h+arg_18]
0x18001a8d9  add     rsp, 68h
0x18001a8dd  jmp     short $+2
0x18001a8df  jmp     rax
```
