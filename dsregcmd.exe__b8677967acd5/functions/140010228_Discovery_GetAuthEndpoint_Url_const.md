# Discovery::GetAuthEndpoint(Url const &)

- ea: `0x140010228`
- end: `0x1400102d7`
- name: `?GetAuthEndpoint@Discovery@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVUrl@@@Z`
- size: `175`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001088c`

## callees

- `0x1400081d8`
- `0x14000f058`
- `0x140010228`
- `0x140030010`

## string_xrefs

- `0x140010289`: `/common/oauth2/authorize`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Discovery::GetAuthEndpoint(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  int v6; // [rsp+20h] [rbp-18h]
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v7,
    *(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL),
    *(unsigned int *)(*(_QWORD *)(a2 + 8) + 32LL));
  v6 = 3;
  v4 = v7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a1,
    L"https://%s%s",
    v7,
    L"/common/oauth2/authorize",
    v6);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 - 24) + 8LL))(*(_QWORD *)(v4 - 24));
  return a1;
}

```

## disassembly

```asm
0x140010228  mov     [rsp+arg_8], rbx
0x14001022d  mov     [rsp+arg_0], rcx
0x140010232  push    rdi
0x140010233  sub     rsp, 30h
0x140010237  mov     rbx, rdx
0x14001023a  mov     rdi, rcx
0x14001023d  mov     [rsp+38h+var_18], 0
0x140010245  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001024c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010253  mov     rax, [rax+18h]
0x140010257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001025c  add     rax, 18h
0x140010260  mov     [rdi], rax
0x140010263  mov     [rsp+38h+var_18], 1
0x14001026b  mov     rdx, [rbx+8]
0x14001026f  mov     r8d, [rdx+20h]
0x140010273  mov     rdx, [rdx+18h]
0x140010277  lea     rcx, [rsp+38h+arg_10]
0x14001027c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x140010281  mov     [rsp+38h+var_18], 3
0x140010289  lea     r9, aCommonOauth2Au; "/common/oauth2/authorize"
0x140010290  mov     rbx, [rsp+38h+arg_10]
0x140010295  mov     r8, rbx
0x140010298  lea     rdx, aHttpsSS; "https://%s%s"
0x14001029f  mov     rcx, rdi
0x1400102a2  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1400102a7  nop
0x1400102a8  lea     rdx, [rbx-18h]
0x1400102ac  or      eax, 0FFFFFFFFh
0x1400102af  lock xadd [rdx+10h], eax
0x1400102b4  sub     eax, 1
0x1400102b7  jg      short loc_1400102C8
0x1400102b9  mov     rcx, [rdx]
0x1400102bc  mov     rax, [rcx]
0x1400102bf  mov     rax, [rax+8]
0x1400102c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102c8  mov     rax, rdi
0x1400102cb  mov     rbx, [rsp+38h+arg_8]
0x1400102d0  add     rsp, 30h
0x1400102d4  pop     rdi
0x1400102d5  retn
```
