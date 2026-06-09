# OdmlSvcSetAutoUpdateEnabled

- ea: `0x180008520`
- end: `0x180008593`
- name: `OdmlSvcSetAutoUpdateEnabled`
- size: `115`
- prototype: `int __fastcall(int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180008520`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000854e`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000854e`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008584`

## string_xrefs

- `0x180008535`: `[MosHost] OdmlSvcSetAutoUpdateEnabled`
- `0x180008542`: `OdmlSvcSetAutoUpdateEnabled`
- `0x180008576`: `OdmlSvcSetAutoUpdateEnabled`

## pseudocode

```c
int __fastcall OdmlSvcSetAutoUpdateEnabled(int a1, unsigned int a2)
{
  int v3; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(3, "OdmlSvcSetAutoUpdateEnabled", 327, "[MosHost] OdmlSvcSetAutoUpdateEnabled");
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800185D0 + 160LL))(qword_1800185D0, a2);
  if ( v3 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v3, "OdmlSvcSetAutoUpdateEnabled", 329);
}

```

## disassembly

```asm
0x180008520  push    rbx
0x180008522  sub     rsp, 20h
0x180008526  mov     eax, cs:dword_1800185C4
0x18000852c  mov     ebx, edx
0x18000852e  nop
0x18000852f  cmp     eax, ecx
0x180008531  jz      short loc_180008535
0x180008533  int     2Ch; Windows NT - assertion failure
0x180008535  lea     r9, aMoshostOdmlsvc_5; "[MosHost] OdmlSvcSetAutoUpdateEnabled"
0x18000853c  mov     r8d, 147h
0x180008542  lea     rdx, aOdmlsvcsetauto; "OdmlSvcSetAutoUpdateEnabled"
0x180008549  mov     ecx, 3
0x18000854e  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008554  mov     rcx, cs:qword_1800185D0
0x18000855b  mov     edx, ebx
0x18000855d  mov     rax, [rcx]
0x180008560  mov     rax, [rax+0A0h]
0x180008567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000856c  test    eax, eax
0x18000856e  jns     short loc_18000858B
0x180008570  mov     r8d, 149h
0x180008576  lea     rdx, aOdmlsvcsetauto; "OdmlSvcSetAutoUpdateEnabled"
0x18000857d  mov     ecx, eax
0x18000857f  add     rsp, 20h
0x180008583  pop     rbx
0x180008584  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000858b  xor     eax, eax
0x18000858d  add     rsp, 20h
0x180008591  pop     rbx
0x180008592  retn
```
