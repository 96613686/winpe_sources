# OdmlSvcDeleteAllMaps

- ea: `0x180007db0`
- end: `0x180007e18`
- name: `OdmlSvcDeleteAllMaps`
- size: `104`
- prototype: `int __fastcall(int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007db0`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007dda`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007dda`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007e0a`

## string_xrefs

- `0x180007dc1`: `[MosHost] OdmlSvcDeleteAllMaps`
- `0x180007dce`: `OdmlSvcDeleteAllMaps`
- `0x180007dfd`: `OdmlSvcDeleteAllMaps`

## pseudocode

```c
int __fastcall OdmlSvcDeleteAllMaps(int a1)
{
  int v1; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(3, "OdmlSvcDeleteAllMaps", 283, "[MosHost] OdmlSvcDeleteAllMaps");
  v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800185D0 + 96LL))(qword_1800185D0);
  if ( v1 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v1, "OdmlSvcDeleteAllMaps", 287);
}

```

## disassembly

```asm
0x180007db0  sub     rsp, 28h
0x180007db4  mov     eax, cs:dword_1800185C4
0x180007dba  nop
0x180007dbb  cmp     eax, ecx
0x180007dbd  jz      short loc_180007DC1
0x180007dbf  int     2Ch; Windows NT - assertion failure
0x180007dc1  lea     r9, aMoshostOdmlsvc_0; "[MosHost] OdmlSvcDeleteAllMaps"
0x180007dc8  mov     r8d, 11Bh
0x180007dce  lea     rdx, aOdmlsvcdeletea; "OdmlSvcDeleteAllMaps"
0x180007dd5  mov     ecx, 3
0x180007dda  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180007de0  mov     rcx, cs:qword_1800185D0
0x180007de7  mov     rax, [rcx]
0x180007dea  mov     rax, [rax+60h]
0x180007dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df3  test    eax, eax
0x180007df5  jns     short loc_180007E11
0x180007df7  mov     r8d, 11Fh
0x180007dfd  lea     rdx, aOdmlsvcdeletea; "OdmlSvcDeleteAllMaps"
0x180007e04  mov     ecx, eax
0x180007e06  add     rsp, 28h
0x180007e0a  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007e11  xor     eax, eax
0x180007e13  add     rsp, 28h
0x180007e17  retn
```
