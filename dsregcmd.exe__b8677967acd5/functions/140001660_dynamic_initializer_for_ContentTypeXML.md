# _dynamic_initializer_for__ContentTypeXML__

- ea: `0x140001660`
- end: `0x1400016c7`
- name: `_dynamic_initializer_for__ContentTypeXML__`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001660`
- `0x1400020ac`
- `0x140005c80`
- `0x1400061dc`
- `0x140030010`

## string_xrefs

- `0x140001686`: `text/xml`
- `0x1400016a3`: `text/xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__ContentTypeXML__()
{
  qword_140046050 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&qword_140046050,
          (__int64)L"text/xml") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&qword_140046050, L"text/xml", 8);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__ContentTypeXML__);
}

```

## disassembly

```asm
0x140001660  sub     rsp, 28h
0x140001664  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000166b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140001672  mov     rax, [rax+18h]
0x140001676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000167b  add     rax, 18h
0x14000167f  mov     cs:qword_140046050, rax
0x140001686  lea     rdx, aTextXml; "text/xml"
0x14000168d  lea     rcx, qword_140046050
0x140001694  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140001699  test    al, al
0x14000169b  jnz     short loc_1400016B7
0x14000169d  mov     r8d, 8
0x1400016a3  lea     rdx, aTextXml; "text/xml"
0x1400016aa  lea     rcx, qword_140046050
0x1400016b1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400016b6  nop
0x1400016b7  lea     rcx, _dynamic_atexit_destructor_for__ContentTypeXML__
0x1400016be  add     rsp, 28h
0x1400016c2  jmp     atexit
```
