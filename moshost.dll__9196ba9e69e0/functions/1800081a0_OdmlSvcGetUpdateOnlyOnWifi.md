# OdmlSvcGetUpdateOnlyOnWifi

- ea: `0x1800081a0`
- end: `0x180008215`
- name: `OdmlSvcGetUpdateOnlyOnWifi`
- size: `117`
- prototype: `int __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800081a0`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800081cf`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800081cf`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008206`

## string_xrefs

- `0x1800081b6`: `[MosHost] OdmlSvcGetUpdateOnlyOnWifi`
- `0x1800081c3`: `OdmlSvcGetUpdateOnlyOnWifi`
- `0x1800081f8`: `OdmlSvcGetUpdateOnlyOnWifi`

## pseudocode

```c
int __fastcall OdmlSvcGetUpdateOnlyOnWifi(int a1, __int64 a2)
{
  int v3; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(5, "OdmlSvcGetUpdateOnlyOnWifi", 376, "[MosHost] OdmlSvcGetUpdateOnlyOnWifi");
  v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800185D0 + 184LL))(qword_1800185D0, a2);
  if ( v3 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v3, "OdmlSvcGetUpdateOnlyOnWifi", 379);
}

```

## disassembly

```asm
0x1800081a0  push    rbx
0x1800081a2  sub     rsp, 20h
0x1800081a6  mov     eax, cs:dword_1800185C4
0x1800081ac  mov     rbx, rdx
0x1800081af  nop
0x1800081b0  cmp     eax, ecx
0x1800081b2  jz      short loc_1800081B6
0x1800081b4  int     2Ch; Windows NT - assertion failure
0x1800081b6  lea     r9, aMoshostOdmlsvc_3; "[MosHost] OdmlSvcGetUpdateOnlyOnWifi"
0x1800081bd  mov     r8d, 178h
0x1800081c3  lea     rdx, aOdmlsvcgetupda; "OdmlSvcGetUpdateOnlyOnWifi"
0x1800081ca  mov     ecx, 5
0x1800081cf  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800081d5  mov     rcx, cs:qword_1800185D0
0x1800081dc  mov     rdx, rbx
0x1800081df  mov     rax, [rcx]
0x1800081e2  mov     rax, [rax+0B8h]
0x1800081e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ee  test    eax, eax
0x1800081f0  jns     short loc_18000820D
0x1800081f2  mov     r8d, 17Bh
0x1800081f8  lea     rdx, aOdmlsvcgetupda; "OdmlSvcGetUpdateOnlyOnWifi"
0x1800081ff  mov     ecx, eax
0x180008201  add     rsp, 20h
0x180008205  pop     rbx
0x180008206  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000820d  xor     eax, eax
0x18000820f  add     rsp, 20h
0x180008213  pop     rbx
0x180008214  retn
```
