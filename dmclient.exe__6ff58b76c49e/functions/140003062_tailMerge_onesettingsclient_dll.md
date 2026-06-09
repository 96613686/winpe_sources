# __tailMerge_onesettingsclient_dll

- ea: `0x140003062`
- end: `0x1400030db`
- name: `__tailMerge_onesettingsclient_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400030e1`
- `0x1400030f3`
- `0x140003105`
- `0x140003117`
- `0x140003129`
- `0x14000313b`
- `0x14000314d`
- `0x14000315f`
- `0x140003171`
- `0x140003183`

## callees

- `0x140003062`
- `0x140018670`

## pseudocode

```c
__int64 __fastcall _tailMerge_onesettingsclient_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_onesettingsclient_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003062  mov     [rsp+arg_0], rcx
0x140003067  mov     [rsp+arg_8], rdx
0x14000306c  mov     [rsp+arg_10], r8
0x140003071  mov     [rsp+arg_18], r9
0x140003076  sub     rsp, 68h
0x14000307a  movdqa  [rsp+68h+var_48], xmm0
0x140003080  movdqa  [rsp+68h+var_38], xmm1
0x140003086  movdqa  [rsp+68h+var_28], xmm2
0x14000308c  movdqa  [rsp+68h+var_18], xmm3
0x140003092  mov     rdx, rax
0x140003095  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_onesettingsclient_dll
0x14000309c  call    __delayLoadHelper2
0x1400030a1  movdqa  xmm0, [rsp+68h+var_48]
0x1400030a7  movdqa  xmm1, [rsp+68h+var_38]
0x1400030ad  movdqa  xmm2, [rsp+68h+var_28]
0x1400030b3  movdqa  xmm3, [rsp+68h+var_18]
0x1400030b9  mov     rcx, [rsp+68h+arg_0]
0x1400030be  mov     rdx, [rsp+68h+arg_8]
0x1400030c3  mov     r8, [rsp+68h+arg_10]
0x1400030cb  mov     r9, [rsp+68h+arg_18]
0x1400030d3  add     rsp, 68h
0x1400030d7  jmp     short $+2
0x1400030d9  jmp     rax
```
