# ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)

- ea: `0x18001a610`
- end: `0x18001a6ce`
- name: `?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z`
- size: `190`
- prototype: `HRESULT __fastcall(SAFEARRAY **, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a91c`

## callees

- `0x18001a610`
- `0x18001a728`
- `0x18001a748`
- `0x18001a86c`
- `0x18001a8dc`
- `0x18001ad58`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18001a69c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001a69c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001a67d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001a67d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18001a68f`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18001a68f`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<tagVARIANT,12>::Add(SAFEARRAY **a1, __int64 a2)
{
  HRESULT result; // eax
  LONG LowerBound; // edi
  int Count; // eax
  SAFEARRAY *v7; // rcx
  int v8; // eax
  SAFEARRAYBOUND psaboundNew; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 || (psaboundNew = 0, result = ATL::CComSafeArray<tagVARIANT,12>::Create(a1, &psaboundNew), result >= 0) )
  {
    LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(a1);
    Count = ATL::CComSafeArray<tagVARIANT,12>::GetCount(a1);
    v7 = *a1;
    psaboundNew.cElements = Count + 1;
    psaboundNew.lLbound = LowerBound;
    if ( !v7 )
      ATL::AtlThrowImpl(-2147467259);
    if ( (v7->fFeatures & 0x10) != 0 )
    {
      return -2147467259;
    }
    else
    {
      result = SafeArrayUnlock(v7);
      if ( result >= 0 )
      {
        result = SafeArrayRedim(*a1, &psaboundNew);
        if ( result >= 0 )
        {
          result = SafeArrayLock(*a1);
          if ( result >= 0 )
          {
            v8 = ATL::CComSafeArray<tagVARIANT,12>::GetCount(a1);
            return ATL::CComSafeArray<tagVARIANT,12>::SetAt(a1, (unsigned int)(LowerBound + v8 - 1), a2);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a610  mov     rax, rsp
0x18001a613  mov     [rax+10h], rbx
0x18001a617  mov     [rax+18h], rsi
0x18001a61b  push    rdi
0x18001a61c  sub     rsp, 20h
0x18001a620  cmp     qword ptr [rcx], 0
0x18001a624  mov     rsi, rdx
0x18001a627  mov     rbx, rcx
0x18001a62a  jnz     short loc_18001A641
0x18001a62c  lea     rdx, [rax+8]
0x18001a630  mov     qword ptr [rax+8], 0
0x18001a638  call    ?Create@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJPEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::Create(tagSAFEARRAYBOUND const *,uint)
0x18001a63d  test    eax, eax
0x18001a63f  js      short loc_18001A6BE
0x18001a641  mov     rcx, rbx
0x18001a644  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001a649  mov     rcx, rbx
0x18001a64c  mov     edi, eax
0x18001a64e  call    ?GetCount@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAKI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetCount(uint)
0x18001a653  mov     rcx, [rbx]; psa
0x18001a656  inc     eax
0x18001a658  mov     [rsp+28h+psaboundNew.cElements], eax
0x18001a65c  mov     [rsp+28h+psaboundNew.lLbound], edi
0x18001a660  test    rcx, rcx
0x18001a663  jnz     short loc_18001A670
0x18001a665  mov     ecx, 80004005h; int
0x18001a66a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001a670  test    byte ptr [rcx+2], 10h
0x18001a674  jz      short loc_18001A67D
0x18001a676  mov     eax, 80004005h
0x18001a67b  jmp     short loc_18001A6BE
0x18001a67d  call    cs:__imp_SafeArrayUnlock
0x18001a683  test    eax, eax
0x18001a685  js      short loc_18001A6BE
0x18001a687  mov     rcx, [rbx]; psa
0x18001a68a  lea     rdx, [rsp+28h+psaboundNew]; psaboundNew
0x18001a68f  call    cs:__imp_SafeArrayRedim
0x18001a695  test    eax, eax
0x18001a697  js      short loc_18001A6BE
0x18001a699  mov     rcx, [rbx]; psa
0x18001a69c  call    cs:__imp_SafeArrayLock
0x18001a6a2  test    eax, eax
0x18001a6a4  js      short loc_18001A6BE
0x18001a6a6  mov     rcx, rbx
0x18001a6a9  call    ?GetCount@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAKI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetCount(uint)
0x18001a6ae  mov     r8, rsi
0x18001a6b1  mov     rcx, rbx
0x18001a6b4  lea     edx, [rax-1]
0x18001a6b7  add     edx, edi
0x18001a6b9  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18001a6be  mov     rbx, [rsp+28h+arg_8]
0x18001a6c3  mov     rsi, [rsp+28h+arg_10]
0x18001a6c8  add     rsp, 20h
0x18001a6cc  pop     rdi
0x18001a6cd  retn
```
