# _CLogStorage::_NewLogFile_::_1_::catch$0

- ea: `0x180014144`
- end: `0x1800141a2`
- name: `_CLogStorage::_NewLogFile_::_1_::catch$0`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ad90`

## string_xrefs

- `0x18001417c`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
__int64 __fastcall CLogStorage::_NewLogFile_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a2 + 108);
  *(_DWORD *)(a2 + 192) = v2;
  TraceStringInline(
    12,
    1u,
    (__int64)L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
    2197,
    (__int64)L"CLogStorage::_NewLogFile",
    v2,
    L"_InitLogPages failed");
  return 0;
}

```

## disassembly

```asm
0x180014144  mov     [rsp+arg_8], rdx
0x180014149  push    rbp
0x18001414a  sub     rsp, 50h
0x18001414e  mov     rbp, rdx
0x180014151  mov     eax, [rbp+6Ch]
0x180014154  mov     [rbp+0C0h], eax
0x18001415a  lea     rcx, aInitlogpagesFa; "_InitLogPages failed"
0x180014161  mov     [rsp+58h+var_28], rcx
0x180014166  mov     [rsp+58h+var_30], eax
0x18001416a  lea     rax, aClogstorageNew; "CLogStorage::_NewLogFile"
0x180014171  mov     [rsp+58h+var_38], rax
0x180014176  mov     r9d, 895h
0x18001417c  lea     r8, aComComplusDtcD_4; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180014183  mov     edx, 1
0x180014188  lea     ecx, [rdx+0Bh]
0x18001418b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014190  nop
0x180014191  mov     rax, 0
0x18001419b  add     rsp, 50h
0x18001419f  pop     rbp
0x1800141a0  retn
```
