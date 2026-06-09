# _CHtmlIFilterCF::CreateInstance_::_1_::catch$1

- ea: `0x18002363d`
- end: `0x180023699`
- name: `_CHtmlIFilterCF::CreateInstance_::_1_::catch$1`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000fab0`
- `0x18001cee0`
- `0x18001e3a0`

## string_xrefs

- `0x180023665`: `[HTML] Exception 0x%x caught in CHtmlIFilterCF::CreateInstance`

## pseudocode

```c
void __fastcall __noreturn CHtmlIFilterCF::CreateInstance_::_1_::catch_1(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 40),
    333,
    "onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\htmliflt.cxx");
}

```

## disassembly

```asm
0x18002363d  mov     [rsp+arg_8], rdx
0x180023642  push    rbx
0x180023643  push    rbp
0x180023644  sub     rsp, 28h
0x180023648  mov     rbp, rdx
0x18002364b  mov     rcx, [rbp+28h]
0x18002364f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180023656  mov     edx, 14Dh
0x18002365b  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180023660  mov     ebx, eax
0x180023662  mov     r9d, eax; wchar_t *
0x180023665  lea     r8, aHtmlException0; "[HTML] Exception 0x%x caught in CHtmlIF"...
0x18002366c  mov     edx, 14Fh; wchar_t *
0x180023671  lea     rcx, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180023678  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18002367d  mov     ecx, ebx; wchar_t *
0x18002367f  call    ?GetOleErrorFromHRESULT@@YAJJ@Z; GetOleErrorFromHRESULT(long)
0x180023684  mov     [rbp+48h], eax
0x180023687  mov     rax, 0
0x180023691  add     rsp, 28h
0x180023695  pop     rbp
0x180023696  pop     rbx
0x180023697  retn
```
