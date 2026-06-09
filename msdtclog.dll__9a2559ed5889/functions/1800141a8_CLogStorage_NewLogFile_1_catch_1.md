# _CLogStorage::_NewLogFile_::_1_::catch$1

- ea: `0x1800141a8`
- end: `0x180014206`
- name: `_CLogStorage::_NewLogFile_::_1_::catch$1`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ad90`

## string_xrefs

- `0x1800141e0`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
__int64 __fastcall CLogStorage::_NewLogFile_::_1_::catch_1(__int64 a1, __int64 a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a2 + 112);
  *(_DWORD *)(a2 + 192) = v2;
  TraceStringInline(
    12,
    1u,
    (__int64)L"com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
    2203,
    (__int64)L"CLogStorage::_NewLogFile",
    v2,
    L"_InitLogPages failed");
  return 0;
}

```

## disassembly

```asm
0x1800141a8  mov     [rsp+arg_8], rdx
0x1800141ad  push    rbp
0x1800141ae  sub     rsp, 50h
0x1800141b2  mov     rbp, rdx
0x1800141b5  mov     eax, [rbp+70h]
0x1800141b8  mov     [rbp+0C0h], eax
0x1800141be  lea     rcx, aInitlogpagesFa; "_InitLogPages failed"
0x1800141c5  mov     [rsp+58h+var_28], rcx
0x1800141ca  mov     [rsp+58h+var_30], eax
0x1800141ce  lea     rax, aClogstorageNew; "CLogStorage::_NewLogFile"
0x1800141d5  mov     [rsp+58h+var_38], rax
0x1800141da  mov     r9d, 89Bh
0x1800141e0  lea     r8, aComComplusDtcD_4; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x1800141e7  mov     edx, 1
0x1800141ec  lea     ecx, [rdx+0Bh]
0x1800141ef  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800141f4  nop
0x1800141f5  mov     rax, 0
0x1800141ff  add     rsp, 50h
0x180014203  pop     rbp
0x180014204  retn
```
