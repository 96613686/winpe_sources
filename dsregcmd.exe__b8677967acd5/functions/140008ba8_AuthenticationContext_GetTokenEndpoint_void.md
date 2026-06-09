# AuthenticationContext::GetTokenEndpoint(void)

- ea: `0x140008ba8`
- end: `0x140008c2d`
- name: `?GetTokenEndpoint@AuthenticationContext@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `133`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001604c`
- `0x140018000`

## callees

- `0x140005458`
- `0x14000813c`
- `0x140008ba8`
- `0x140030010`

## string_xrefs

- `0x140008be0`: `/oauth2/token`

## pseudocode

```c
_QWORD *__fastcall AuthenticationContext::GetTokenEndpoint(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rdx
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_DWORD *)(*(_QWORD *)(a1 + 256) - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      a2,
      (__int64 *)(a1 + 256));
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v5,
      (__int64 *)(a1 + 8));
    ATL::CSimpleStringT<unsigned short,0>::Append(&v5, (__int64)L"/oauth2/token", 13);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      a2,
      &v5);
    v3 = (_QWORD *)(v5 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 8LL))(*v3);
  }
  return a2;
}

```

## disassembly

```asm
0x140008ba8  push    rbx
0x140008baa  sub     rsp, 30h
0x140008bae  mov     rbx, rdx
0x140008bb1  lea     rdx, [rcx+100h]
0x140008bb8  mov     rax, [rdx]
0x140008bbb  cmp     dword ptr [rax-10h], 0
0x140008bbf  jz      short loc_140008BCB
0x140008bc1  mov     rcx, rbx
0x140008bc4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140008bc9  jmp     short loc_140008C24
0x140008bcb  lea     rdx, [rcx+8]
0x140008bcf  lea     rcx, [rsp+38h+arg_0]
0x140008bd4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140008bd9  nop
0x140008bda  mov     r8d, 0Dh
0x140008be0  lea     rdx, aOauth2Token; "/oauth2/token"
0x140008be7  lea     rcx, [rsp+38h+arg_0]
0x140008bec  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140008bf1  lea     rdx, [rsp+38h+arg_0]
0x140008bf6  mov     rcx, rbx
0x140008bf9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140008bfe  nop
0x140008bff  mov     rdx, [rsp+38h+arg_0]
0x140008c04  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140008c08  or      eax, 0FFFFFFFFh
0x140008c0b  lock xadd [rdx+10h], eax
0x140008c10  sub     eax, 1
0x140008c13  jg      short loc_140008C24
0x140008c15  mov     rcx, [rdx]
0x140008c18  mov     rax, [rcx]
0x140008c1b  mov     rax, [rax+8]
0x140008c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c24  mov     rax, rbx
0x140008c27  add     rsp, 30h
0x140008c2b  pop     rbx
0x140008c2c  retn
```
