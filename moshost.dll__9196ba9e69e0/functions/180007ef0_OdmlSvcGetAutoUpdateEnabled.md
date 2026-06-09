# OdmlSvcGetAutoUpdateEnabled

- ea: `0x180007ef0`
- end: `0x180007f65`
- name: `OdmlSvcGetAutoUpdateEnabled`
- size: `117`
- prototype: `int __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180007ef0`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007f1f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007f1f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007f56`

## string_xrefs

- `0x180007f06`: `[MosHost] OdmlSvcGetAutoUpdateEnabled`
- `0x180007f13`: `OdmlSvcGetAutoUpdateEnabled`
- `0x180007f48`: `OdmlSvcGetAutoUpdateEnabled`

## pseudocode

```c
int __fastcall OdmlSvcGetAutoUpdateEnabled(int a1, __int64 a2)
{
  int v3; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(5, "OdmlSvcGetAutoUpdateEnabled", 343, "[MosHost] OdmlSvcGetAutoUpdateEnabled");
  v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800185D0 + 176LL))(qword_1800185D0, a2);
  if ( v3 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v3, "OdmlSvcGetAutoUpdateEnabled", 345);
}

```

## disassembly

```asm
0x180007ef0  push    rbx
0x180007ef2  sub     rsp, 20h
0x180007ef6  mov     eax, cs:dword_1800185C4
0x180007efc  mov     rbx, rdx
0x180007eff  nop
0x180007f00  cmp     eax, ecx
0x180007f02  jz      short loc_180007F06
0x180007f04  int     2Ch; Windows NT - assertion failure
0x180007f06  lea     r9, aMoshostOdmlsvc_6; "[MosHost] OdmlSvcGetAutoUpdateEnabled"
0x180007f0d  mov     r8d, 157h
0x180007f13  lea     rdx, aOdmlsvcgetauto; "OdmlSvcGetAutoUpdateEnabled"
0x180007f1a  mov     ecx, 5
0x180007f1f  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180007f25  mov     rcx, cs:qword_1800185D0
0x180007f2c  mov     rdx, rbx
0x180007f2f  mov     rax, [rcx]
0x180007f32  mov     rax, [rax+0B0h]
0x180007f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3e  test    eax, eax
0x180007f40  jns     short loc_180007F5D
0x180007f42  mov     r8d, 159h
0x180007f48  lea     rdx, aOdmlsvcgetauto; "OdmlSvcGetAutoUpdateEnabled"
0x180007f4f  mov     ecx, eax
0x180007f51  add     rsp, 20h
0x180007f55  pop     rbx
0x180007f56  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007f5d  xor     eax, eax
0x180007f5f  add     rsp, 20h
0x180007f63  pop     rbx
0x180007f64  retn
```
