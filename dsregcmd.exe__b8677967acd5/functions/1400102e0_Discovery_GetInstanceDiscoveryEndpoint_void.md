# Discovery::GetInstanceDiscoveryEndpoint(void)

- ea: `0x1400102e0`
- end: `0x140010372`
- name: `?GetInstanceDiscoveryEndpoint@Discovery@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `146`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001088c`

## callees

- `0x140005c80`
- `0x1400061dc`
- `0x1400063bc`
- `0x14000813c`
- `0x1400102e0`
- `0x140030010`

## string_xrefs

- `0x140010313`: `https://login.microsoftonline.com`
- `0x14001032c`: `https://login.microsoftonline.com`
- `0x140010359`: `/common/discovery/instance`

## pseudocode

```c
void **__fastcall Discovery::GetInstanceDiscoveryEndpoint(void **a1)
{
  *a1 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          a1,
          (__int64)L"https://login.microsoftonline.com") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, L"https://login.microsoftonline.com", 33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(a1, L"/");
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)a1, (__int64)L"/common/discovery/instance", 26);
  return a1;
}

```

## disassembly

```asm
0x1400102e0  mov     [rsp+arg_0], rcx
0x1400102e5  push    rbx
0x1400102e6  sub     rsp, 30h
0x1400102ea  mov     rbx, rcx
0x1400102ed  mov     [rsp+38h+var_18], 0
0x1400102f5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400102fc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010303  mov     rax, [rax+18h]
0x140010307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001030c  add     rax, 18h
0x140010310  mov     [rbx], rax
0x140010313  lea     rdx, aHttpsLoginMicr; "https://login.microsoftonline.com"
0x14001031a  mov     rcx, rbx
0x14001031d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140010322  test    al, al
0x140010324  jnz     short loc_14001033C
0x140010326  mov     r8d, 21h ; '!'
0x14001032c  lea     rdx, aHttpsLoginMicr; "https://login.microsoftonline.com"
0x140010333  mov     rcx, rbx
0x140010336  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001033b  nop
0x14001033c  mov     [rsp+38h+var_18], 1
0x140010344  lea     rdx, asc_140033538; "/"
0x14001034b  mov     rcx, rbx
0x14001034e  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(ushort const *)
0x140010353  mov     r8d, 1Ah
0x140010359  lea     rdx, aCommonDiscover; "/common/discovery/instance"
0x140010360  mov     rcx, rbx
0x140010363  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140010368  mov     rax, rbx
0x14001036b  add     rsp, 30h
0x14001036f  pop     rbx
0x140010370  retn
```
