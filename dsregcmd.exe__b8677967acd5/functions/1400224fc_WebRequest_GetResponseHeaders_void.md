# WebRequest::GetResponseHeaders(void)

- ea: `0x1400224fc`
- end: `0x14002255e`
- name: `?GetResponseHeaders@WebRequest@@QEAA?AV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@XZ`
- size: `98`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140014ea4`
- `0x1400249f0`

## callees

- `0x140001814`
- `0x14001ea98`
- `0x1400224fc`

## string_xrefs

- `0x140022519`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
_QWORD *__fastcall WebRequest::GetResponseHeaders(__int64 a1, _QWORD *a2)
{
  void *v4; // rax

  if ( *(_QWORD *)(a1 + 80) )
  {
    v4 = operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequest.cpp");
    if ( v4 )
      v4 = (void *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
                     v4,
                     *(_QWORD *)(a1 + 80));
    *a2 = v4;
  }
  else
  {
    *a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1400224fc  mov     [rsp+arg_8], rbx
0x140022501  push    rdi
0x140022502  sub     rsp, 30h
0x140022506  mov     rbx, rdx
0x140022509  mov     rdi, rcx
0x14002250c  cmp     qword ptr [rcx+50h], 0
0x140022511  jz      short loc_140022549
0x140022513  mov     r9d, 24Fh; int
0x140022519  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140022520  mov     edx, 1; int
0x140022525  lea     ecx, [rdx+0Fh]; unsigned __int64
0x140022528  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002252d  mov     [rsp+38h+arg_0], rax
0x140022532  test    rax, rax
0x140022535  jz      short loc_140022544
0x140022537  mov     rdx, [rdi+50h]
0x14002253b  mov     rcx, rax
0x14002253e  call    ??0?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAA@AEBV01@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &)
0x140022543  nop
0x140022544  mov     [rbx], rax
0x140022547  jmp     short loc_140022550
0x140022549  mov     qword ptr [rdx], 0
0x140022550  mov     rax, rbx
0x140022553  mov     rbx, [rsp+38h+arg_8]
0x140022558  add     rsp, 30h
0x14002255c  pop     rdi
0x14002255d  retn
```
