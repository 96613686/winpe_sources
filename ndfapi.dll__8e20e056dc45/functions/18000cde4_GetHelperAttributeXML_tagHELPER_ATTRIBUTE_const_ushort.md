# GetHelperAttributeXML(tagHELPER_ATTRIBUTE * const,ushort * *)

- ea: `0x18000cde4`
- end: `0x18000cefe`
- name: `?GetHelperAttributeXML@@YAJQEAUtagHELPER_ATTRIBUTE@@PEAPEAG@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE *const, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000bca0`
- `0x1800163b0`

## callees

- `0x180007ee4`
- `0x18000caf8`
- `0x18000cde4`
- `0x18000f800`
- `0x18001be28`
- `0x18001c720`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000ce48`
- `ole32!CoTaskMemFree` at `0x18000cee6`
- `ole32!CoTaskMemFree` at `0x18000ce48`
- `ole32!CoTaskMemFree` at `0x18000cee6`

## pseudocode

```c
__int64 __fastcall GetHelperAttributeXML(struct tagHELPER_ATTRIBUTE *const a1, unsigned __int16 **a2)
{
  int v3; // edi
  unsigned int v4; // eax
  unsigned __int16 *v5; // rbx
  unsigned __int16 *v7; // [rsp+30h] [rbp-18h] BYREF
  const ATL::CAtlException *v8; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int16 *v9; // [rsp+60h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  pv = 0;
  v9 = 0;
  v3 = EncodeHelperAttribute(a1, &pv, &v9);
  if ( v3 >= 0 )
  {
    v4 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>((unsigned __int64)v9);
    v3 = BinToHex((unsigned __int8 *)pv, v4, &v7);
    CoTaskMemFree(pv);
    pv = 0;
    if ( v3 >= 0 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v9 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v9,
          L"%s%s%s",
          L"<HelperAttribute>",
          v7,
          L"</HelperAttribute>");
        v5 = v9;
        v3 = StringCopyWithAlloc(a2, v9);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v8) )
        {
          LODWORD(v9) = *(_DWORD *)v8;
          v3 = (int)v9;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000CEDD);
        }
      }
    }
  }
  CoTaskMemFree(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000cde4  mov     rax, rsp
0x18000cde7  mov     [rax+8], rbx
0x18000cdeb  mov     [rax+10h], rsi
0x18000cdef  push    rdi
0x18000cdf0  sub     rsp, 40h
0x18000cdf4  mov     rsi, rdx
0x18000cdf7  mov     qword ptr [rax-18h], 0
0x18000cdff  mov     qword ptr [rax+20h], 0
0x18000ce07  mov     qword ptr [rax+18h], 0
0x18000ce0f  lea     r8, [rax+18h]
0x18000ce13  lea     rdx, [rax+20h]
0x18000ce17  call    EncodeHelperAttribute
0x18000ce1c  mov     edi, eax
0x18000ce1e  test    eax, eax
0x18000ce20  js      loc_18000CEE1
0x18000ce26  mov     rcx, [rsp+48h+arg_10]
0x18000ce2b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000ce30  lea     r8, [rsp+48h+var_18]; unsigned __int16 **
0x18000ce35  mov     edx, eax; unsigned int
0x18000ce37  mov     rcx, [rsp+48h+pv]; unsigned __int8 *
0x18000ce3c  call    ?BinToHex@@YAJPEAEKPEAPEAG@Z; BinToHex(uchar *,ulong,ushort * *)
0x18000ce41  mov     edi, eax
0x18000ce43  mov     rcx, [rsp+48h+pv]; pv
0x18000ce48  call    cs:__imp_CoTaskMemFree
0x18000ce4e  mov     [rsp+48h+pv], 0
0x18000ce57  test    edi, edi
0x18000ce59  js      loc_18000CEE1
0x18000ce5f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ce66  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ce6d  mov     rax, [rax+18h]
0x18000ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce76  add     rax, 18h
0x18000ce7a  mov     [rsp+48h+arg_10], rax
0x18000ce7f  lea     rax, aHelperattribut_2; "</HelperAttribute>"
0x18000ce86  mov     [rsp+48h+var_28], rax
0x18000ce8b  mov     r9, [rsp+48h+var_18]
0x18000ce90  lea     r8, aHelperattribut_1; "<HelperAttribute>"
0x18000ce97  lea     rdx, aSSS; "%s%s%s"
0x18000ce9e  lea     rcx, [rsp+48h+arg_10]
0x18000cea3  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000cea8  mov     rbx, [rsp+48h+arg_10]
0x18000cead  mov     rdx, rbx; unsigned __int16 *
0x18000ceb0  mov     rcx, rsi; unsigned __int16 **
0x18000ceb3  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18000ceb8  mov     edi, eax
0x18000ceba  lea     rdx, [rbx-18h]
0x18000cebe  or      eax, 0FFFFFFFFh
0x18000cec1  lock xadd [rdx+10h], eax
0x18000cec6  sub     eax, 1
0x18000cec9  jg      short loc_18000CEDB
0x18000cecb  mov     rcx, [rdx]
0x18000cece  mov     rax, [rcx]
0x18000ced1  mov     rax, [rax+8]
0x18000ced5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceda  nop
0x18000cedb  jmp     short loc_18000CEE1
0x18000cedd  mov     edi, dword ptr [rsp+48h+arg_10]
0x18000cee1  mov     rcx, [rsp+48h+var_18]; pv
0x18000cee6  call    cs:__imp_CoTaskMemFree
0x18000ceec  mov     eax, edi
0x18000ceee  mov     rbx, [rsp+48h+arg_0]
0x18000cef3  mov     rsi, [rsp+48h+arg_8]
0x18000cef8  add     rsp, 40h
0x18000cefc  pop     rdi
0x18000cefd  retn
```
