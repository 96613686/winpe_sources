# OdmlSvcRemoveMapPackages

- ea: `0x180008460`
- end: `0x180008519`
- name: `OdmlSvcRemoveMapPackages`
- size: `185`
- prototype: `int __fastcall(int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008460`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800084b3`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800084b3`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008499`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008499`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800084ff`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800084ff`

## string_xrefs

- `0x180008482`: `OdmlSvcRemoveMapPackages`
- `0x1800084f6`: `OdmlSvcRemoveMapPackages`
- `0x1800084a1`: `[MosHost] OdmlSvcRemoveMapPackages`

## pseudocode

```c
int __fastcall OdmlSvcRemoveMapPackages(int a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  int v8; // eax

  if ( dword_1800185C4 != a1 )
    __int2c();
  if ( !a2 )
    return ZTraceReportOriginationNoThis(-2147467261, "OdmlSvcRemoveMapPackages", 244);
  ZTraceHelperNoThis(3, "OdmlSvcRemoveMapPackages", 246, "[MosHost] OdmlSvcRemoveMapPackages");
  v6 = qword_1800185D0;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800185D0 + 264LL))(qword_1800185D0);
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v6 + 80LL))(v6, a3, a2, v7);
  if ( v8 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v8, "OdmlSvcRemoveMapPackages", 250);
}

```

## disassembly

```asm
0x180008460  mov     [rsp+arg_0], rbx
0x180008465  mov     [rsp+arg_8], rsi
0x18000846a  push    rdi
0x18000846b  sub     rsp, 30h
0x18000846f  mov     eax, cs:dword_1800185C4
0x180008475  mov     esi, r8d
0x180008478  mov     rdi, rdx
0x18000847b  nop
0x18000847c  cmp     eax, ecx
0x18000847e  jz      short loc_180008482
0x180008480  int     2Ch; Windows NT - assertion failure
0x180008482  lea     rdx, aOdmlsvcremovem; "OdmlSvcRemoveMapPackages"
0x180008489  test    rdi, rdi
0x18000848c  jnz     short loc_1800084A1
0x18000848e  mov     r8d, 0F4h
0x180008494  mov     ecx, 80004003h
0x180008499  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000849f  jmp     short loc_180008509
0x1800084a1  lea     r9, aMoshostOdmlsvc; "[MosHost] OdmlSvcRemoveMapPackages"
0x1800084a8  mov     r8d, 0F6h
0x1800084ae  mov     ecx, 3
0x1800084b3  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800084b9  mov     rbx, cs:qword_1800185D0
0x1800084c0  mov     rcx, rbx
0x1800084c3  mov     rax, [rbx]
0x1800084c6  mov     rax, [rax+108h]
0x1800084cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d2  mov     rdx, [rbx]
0x1800084d5  mov     r9d, eax
0x1800084d8  mov     r8, rdi
0x1800084db  mov     rcx, rbx
0x1800084de  mov     r10, [rdx+50h]
0x1800084e2  mov     edx, esi
0x1800084e4  mov     rax, r10
0x1800084e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ec  test    eax, eax
0x1800084ee  jns     short loc_180008507
0x1800084f0  mov     r8d, 0FAh
0x1800084f6  lea     rdx, aOdmlsvcremovem; "OdmlSvcRemoveMapPackages"
0x1800084fd  mov     ecx, eax
0x1800084ff  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008505  jmp     short loc_180008509
0x180008507  xor     eax, eax
0x180008509  mov     rbx, [rsp+38h+arg_0]
0x18000850e  mov     rsi, [rsp+38h+arg_8]
0x180008513  add     rsp, 30h
0x180008517  pop     rdi
0x180008518  retn
```
