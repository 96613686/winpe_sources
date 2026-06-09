# OdmlSvcStartCheckForUpdates

- ea: `0x180008620`
- end: `0x180008687`
- name: `OdmlSvcStartCheckForUpdates`
- size: `103`
- prototype: `int __fastcall(int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180008620`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008649`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008649`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008679`

## string_xrefs

- `0x180008637`: `[MosHost] OdmlSvcStartCheckForUpdates`
- `0x18000863e`: `OdmlSvcStartCheckForUpdates`
- `0x18000866c`: `OdmlSvcStartCheckForUpdates`

## pseudocode

```c
int __fastcall OdmlSvcStartCheckForUpdates(int a1)
{
  int v1; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(3, "OdmlSvcStartCheckForUpdates", 108, "[MosHost] OdmlSvcStartCheckForUpdates");
  v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800185D0 + 16LL))(qword_1800185D0);
  if ( v1 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v1, "OdmlSvcStartCheckForUpdates", 112);
}

```

## disassembly

```asm
0x180008620  sub     rsp, 28h
0x180008624  mov     eax, cs:dword_1800185C4
0x18000862a  nop
0x18000862b  cmp     eax, ecx
0x18000862d  jz      short loc_180008631
0x18000862f  int     2Ch; Windows NT - assertion failure
0x180008631  mov     r8d, 6Ch ; 'l'
0x180008637  lea     r9, aMoshostOdmlsvc_9; "[MosHost] OdmlSvcStartCheckForUpdates"
0x18000863e  lea     rdx, aOdmlsvcstartch; "OdmlSvcStartCheckForUpdates"
0x180008645  lea     ecx, [r8-69h]
0x180008649  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000864f  mov     rcx, cs:qword_1800185D0
0x180008656  mov     rax, [rcx]
0x180008659  mov     rax, [rax+10h]
0x18000865d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008662  test    eax, eax
0x180008664  jns     short loc_180008680
0x180008666  mov     r8d, 70h ; 'p'
0x18000866c  lea     rdx, aOdmlsvcstartch; "OdmlSvcStartCheckForUpdates"
0x180008673  mov     ecx, eax
0x180008675  add     rsp, 28h
0x180008679  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008680  xor     eax, eax
0x180008682  add     rsp, 28h
0x180008686  retn
```
