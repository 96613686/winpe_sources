# _dynamic_initializer_for__WebRequest::MethodDelete__

- ea: `0x140001270`
- end: `0x1400012d7`
- name: `_dynamic_initializer_for__WebRequest::MethodDelete__`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001270`
- `0x1400020ac`
- `0x140005c80`
- `0x1400061dc`
- `0x140030010`

## string_xrefs

- `0x140001296`: `DELETE`
- `0x1400012b3`: `DELETE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__WebRequest::MethodDelete__()
{
  WebRequest::MethodDelete = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&WebRequest::MethodDelete,
          (__int64)L"DELETE") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&WebRequest::MethodDelete, L"DELETE", 6);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__WebRequest::MethodDelete__);
}

```

## disassembly

```asm
0x140001270  sub     rsp, 28h
0x140001274  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000127b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140001282  mov     rax, [rax+18h]
0x140001286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000128b  add     rax, 18h
0x14000128f  mov     cs:?MethodDelete@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B, rax; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodDelete
0x140001296  lea     rdx, aDelete; "DELETE"
0x14000129d  lea     rcx, ?MethodDelete@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodDelete
0x1400012a4  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400012a9  test    al, al
0x1400012ab  jnz     short loc_1400012C7
0x1400012ad  mov     r8d, 6
0x1400012b3  lea     rdx, aDelete; "DELETE"
0x1400012ba  lea     rcx, ?MethodDelete@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodDelete
0x1400012c1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400012c6  nop
0x1400012c7  lea     rcx, _dynamic_atexit_destructor_for__WebRequest__MethodDelete__
0x1400012ce  add     rsp, 28h
0x1400012d2  jmp     atexit
```
