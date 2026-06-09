# DllGetClassObject$catch$1

- ea: `0x1800239ff`
- end: `0x180023a7b`
- name: `DllGetClassObject$catch$1`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000fab0`
- `0x18001cee0`
- `0x18001e3a0`
- `0x1800239ff`
- `0x180025010`

## string_xrefs

- `0x180023a3c`: `[HTML] Exception 0x%x caught in CHtmlIFilterCF::CreateInstance`

## pseudocode

```c
void __fastcall __noreturn DllGetClassObject_catch_1(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx

  v3 = *(_QWORD *)(a2 + 72);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 40),
    422,
    "onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\htmliflt.cxx");
}

```

## disassembly

```asm
0x1800239ff  mov     [rsp+arg_8], rdx
0x180023a04  push    rbx
0x180023a05  push    rbp
0x180023a06  sub     rsp, 28h
0x180023a0a  mov     rbp, rdx
0x180023a0d  mov     rcx, [rbp+48h]
0x180023a11  test    rcx, rcx
0x180023a14  jz      short loc_180023A22
0x180023a16  mov     rax, [rcx]
0x180023a19  mov     rax, [rax+10h]
0x180023a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a22  mov     rcx, [rbp+28h]
0x180023a26  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180023a2d  mov     edx, 1A6h
0x180023a32  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180023a37  mov     ebx, eax
0x180023a39  mov     r9d, eax; wchar_t *
0x180023a3c  lea     r8, aHtmlException0; "[HTML] Exception 0x%x caught in CHtmlIF"...
0x180023a43  mov     edx, 1A8h; wchar_t *
0x180023a48  lea     rcx, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180023a4f  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180023a54  mov     rax, [rbp+40h]
0x180023a58  mov     qword ptr [rax], 0
0x180023a5f  mov     ecx, ebx; wchar_t *
0x180023a61  call    ?GetOleErrorFromHRESULT@@YAJJ@Z; GetOleErrorFromHRESULT(long)
0x180023a66  mov     [rbp+40h], eax
0x180023a69  mov     rax, 0
0x180023a73  add     rsp, 28h
0x180023a77  pop     rbp
0x180023a78  pop     rbx
0x180023a79  retn
```
