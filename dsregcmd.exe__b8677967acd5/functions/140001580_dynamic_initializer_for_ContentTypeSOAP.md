# _dynamic_initializer_for__ContentTypeSOAP__

- ea: `0x140001580`
- end: `0x1400015e7`
- name: `_dynamic_initializer_for__ContentTypeSOAP__`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001580`
- `0x1400020ac`
- `0x140005c80`
- `0x1400061dc`
- `0x140030010`

## string_xrefs

- `0x1400015a6`: `application/soap+xml`
- `0x1400015c3`: `application/soap+xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__ContentTypeSOAP__()
{
  qword_140046058 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&qword_140046058,
          (__int64)L"application/soap+xml") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&qword_140046058, L"application/soap+xml", 20);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__ContentTypeSOAP__);
}

```

## disassembly

```asm
0x140001580  sub     rsp, 28h
0x140001584  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000158b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140001592  mov     rax, [rax+18h]
0x140001596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000159b  add     rax, 18h
0x14000159f  mov     cs:qword_140046058, rax
0x1400015a6  lea     rdx, aApplicationSoa_0; "application/soap+xml"
0x1400015ad  lea     rcx, qword_140046058
0x1400015b4  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400015b9  test    al, al
0x1400015bb  jnz     short loc_1400015D7
0x1400015bd  mov     r8d, 14h
0x1400015c3  lea     rdx, aApplicationSoa_0; "application/soap+xml"
0x1400015ca  lea     rcx, qword_140046058
0x1400015d1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400015d6  nop
0x1400015d7  lea     rcx, _dynamic_atexit_destructor_for__ContentTypeSOAP__
0x1400015de  add     rsp, 28h
0x1400015e2  jmp     atexit
```
