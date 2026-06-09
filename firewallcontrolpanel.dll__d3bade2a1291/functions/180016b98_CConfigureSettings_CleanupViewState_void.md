# CConfigureSettings::CleanupViewState(void)

- ea: `0x180016b98`
- end: `0x180016c0d`
- name: `?CleanupViewState@CConfigureSettings@@AEAAXXZ`
- size: `117`
- prototype: `void __fastcall(CConfigureSettings *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800171a0`
- `0x180017400`

## callees

- `0x180009040`
- `0x1800096a8`
- `0x1800096dc`
- `0x180016b98`
- `0x18001fb10`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180016bef`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180016bef`

## pseudocode

```c
void __fastcall CConfigureSettings::CleanupViewState(CConfigureSettings *this)
{
  CFwProfileViewUpdate *v2; // rbx
  DirectUI::DUIXmlParser *v3; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 7);
  while ( v4 )
  {
    v2 = *(CFwProfileViewUpdate **)ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(
                                     this,
                                     &v4);
    CFwProfileViewUpdate::Clear(v2);
    CRefObject::Release(v2);
  }
  ATL::CAtlList<CFwProfileViewRead *,ATL::CElementTraits<CFwProfileViewRead *>>::RemoveAll((char *)this + 56);
  v3 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    DirectUI::DUIXmlParser::Destroy(v3);
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x180016b98  mov     [rsp+arg_8], rbx
0x180016b9d  mov     [rsp+arg_10], rsi
0x180016ba2  push    rdi
0x180016ba3  sub     rsp, 20h
0x180016ba7  mov     rax, [rcx+38h]
0x180016bab  mov     rdi, rcx
0x180016bae  mov     [rsp+28h+arg_0], rax
0x180016bb3  test    rax, rax
0x180016bb6  jz      short loc_180016BDD
0x180016bb8  lea     rdx, [rsp+28h+arg_0]
0x180016bbd  call    ?GetNext@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@QEAAAEAPEAVCFwProfileViewUpdate@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(__POSITION * &)
0x180016bc2  mov     rbx, [rax]
0x180016bc5  mov     rcx, rbx; this
0x180016bc8  call    ?Clear@CFwProfileViewUpdate@@QEAAJXZ; CFwProfileViewUpdate::Clear(void)
0x180016bcd  mov     rcx, rbx; this
0x180016bd0  call    ?Release@CRefObject@@QEAAKXZ; CRefObject::Release(void)
0x180016bd5  cmp     [rsp+28h+arg_0], 0
0x180016bdb  jnz     short loc_180016BB8
0x180016bdd  lea     rcx, [rdi+38h]
0x180016be1  call    ?RemoveAll@?$CAtlList@PEAVCFwProfileViewRead@@V?$CElementTraits@PEAVCFwProfileViewRead@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CFwProfileViewRead *,ATL::CElementTraits<CFwProfileViewRead *>>::RemoveAll(void)
0x180016be6  mov     rcx, [rdi+30h]
0x180016bea  test    rcx, rcx
0x180016bed  jz      short loc_180016BFD
0x180016bef  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180016bf5  mov     qword ptr [rdi+30h], 0
0x180016bfd  mov     rbx, [rsp+28h+arg_8]
0x180016c02  mov     rsi, [rsp+28h+arg_10]
0x180016c07  add     rsp, 20h
0x180016c0b  pop     rdi
0x180016c0c  retn
```
