# OdmlSvcSetUpdateOnlyOnWifi

- ea: `0x1800085a0`
- end: `0x180008613`
- name: `OdmlSvcSetUpdateOnlyOnWifi`
- size: `115`
- prototype: `int __fastcall(int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800085a0`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800085ce`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800085ce`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008604`

## string_xrefs

- `0x1800085b5`: `[MosHost] OdmlSvcSetUpdateOnlyOnWifi`
- `0x1800085c2`: `OdmlSvcSetUpdateOnlyOnWifi`
- `0x1800085f6`: `OdmlSvcSetUpdateOnlyOnWifi`

## pseudocode

```c
int __fastcall OdmlSvcSetUpdateOnlyOnWifi(int a1, unsigned int a2)
{
  int v3; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(3, "OdmlSvcSetUpdateOnlyOnWifi", 359, "[MosHost] OdmlSvcSetUpdateOnlyOnWifi");
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800185D0 + 168LL))(qword_1800185D0, a2);
  if ( v3 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v3, "OdmlSvcSetUpdateOnlyOnWifi", 362);
}

```

## disassembly

```asm
0x1800085a0  push    rbx
0x1800085a2  sub     rsp, 20h
0x1800085a6  mov     eax, cs:dword_1800185C4
0x1800085ac  mov     ebx, edx
0x1800085ae  nop
0x1800085af  cmp     eax, ecx
0x1800085b1  jz      short loc_1800085B5
0x1800085b3  int     2Ch; Windows NT - assertion failure
0x1800085b5  lea     r9, aMoshostOdmlsvc_8; "[MosHost] OdmlSvcSetUpdateOnlyOnWifi"
0x1800085bc  mov     r8d, 167h
0x1800085c2  lea     rdx, aOdmlsvcsetupda; "OdmlSvcSetUpdateOnlyOnWifi"
0x1800085c9  mov     ecx, 3
0x1800085ce  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800085d4  mov     rcx, cs:qword_1800185D0
0x1800085db  mov     edx, ebx
0x1800085dd  mov     rax, [rcx]
0x1800085e0  mov     rax, [rax+0A8h]
0x1800085e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ec  test    eax, eax
0x1800085ee  jns     short loc_18000860B
0x1800085f0  mov     r8d, 16Ah
0x1800085f6  lea     rdx, aOdmlsvcsetupda; "OdmlSvcSetUpdateOnlyOnWifi"
0x1800085fd  mov     ecx, eax
0x1800085ff  add     rsp, 20h
0x180008603  pop     rbx
0x180008604  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000860b  xor     eax, eax
0x18000860d  add     rsp, 20h
0x180008611  pop     rbx
0x180008612  retn
```
