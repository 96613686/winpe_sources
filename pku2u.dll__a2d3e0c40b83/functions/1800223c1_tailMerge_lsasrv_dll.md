# __tailMerge_lsasrv_dll

- ea: `0x1800223c1`
- end: `0x18002243a`
- name: `__tailMerge_lsasrv_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022440`
- `0x180022452`
- `0x180022464`
- `0x180022476`
- `0x180022488`
- `0x18002249a`
- `0x1800224ac`
- `0x1800224be`
- `0x1800224d0`
- `0x1800224e2`

## callees

- `0x18001a6d0`
- `0x1800223c1`

## pseudocode

```c
__int64 __fastcall _tailMerge_lsasrv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_lsasrv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800223c1  mov     [rsp+arg_0], rcx
0x1800223c6  mov     [rsp+arg_8], rdx
0x1800223cb  mov     [rsp+arg_10], r8
0x1800223d0  mov     [rsp+arg_18], r9
0x1800223d5  sub     rsp, 68h
0x1800223d9  movdqa  [rsp+68h+var_48], xmm0
0x1800223df  movdqa  [rsp+68h+var_38], xmm1
0x1800223e5  movdqa  [rsp+68h+var_28], xmm2
0x1800223eb  movdqa  [rsp+68h+var_18], xmm3
0x1800223f1  mov     rdx, rax
0x1800223f4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_lsasrv_dll
0x1800223fb  call    __delayLoadHelper2
0x180022400  movdqa  xmm0, [rsp+68h+var_48]
0x180022406  movdqa  xmm1, [rsp+68h+var_38]
0x18002240c  movdqa  xmm2, [rsp+68h+var_28]
0x180022412  movdqa  xmm3, [rsp+68h+var_18]
0x180022418  mov     rcx, [rsp+68h+arg_0]
0x18002241d  mov     rdx, [rsp+68h+arg_8]
0x180022422  mov     r8, [rsp+68h+arg_10]
0x18002242a  mov     r9, [rsp+68h+arg_18]
0x180022432  add     rsp, 68h
0x180022436  jmp     short $+2
0x180022438  jmp     rax
```
