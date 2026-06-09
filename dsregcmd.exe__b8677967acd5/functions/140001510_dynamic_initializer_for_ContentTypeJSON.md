# _dynamic_initializer_for__ContentTypeJSON__

- ea: `0x140001510`
- end: `0x140001577`
- name: `_dynamic_initializer_for__ContentTypeJSON__`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001510`
- `0x1400020ac`
- `0x140005c80`
- `0x1400061dc`
- `0x140030010`

## string_xrefs

- `0x140001536`: `application/json`
- `0x140001553`: `application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__ContentTypeJSON__()
{
  qword_140046040 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&qword_140046040,
          (__int64)L"application/json") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&qword_140046040, L"application/json", 16);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__ContentTypeJSON__);
}

```

## disassembly

```asm
0x140001510  sub     rsp, 28h
0x140001514  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000151b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140001522  mov     rax, [rax+18h]
0x140001526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000152b  add     rax, 18h
0x14000152f  mov     cs:qword_140046040, rax
0x140001536  lea     rdx, aApplicationJso; "application/json"
0x14000153d  lea     rcx, qword_140046040
0x140001544  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140001549  test    al, al
0x14000154b  jnz     short loc_140001567
0x14000154d  mov     r8d, 10h
0x140001553  lea     rdx, aApplicationJso; "application/json"
0x14000155a  lea     rcx, qword_140046040
0x140001561  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140001566  nop
0x140001567  lea     rcx, _dynamic_atexit_destructor_for__ContentTypeJSON__
0x14000156e  add     rsp, 28h
0x140001572  jmp     atexit
```
