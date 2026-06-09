# ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)

- ea: `0x18001cda0`
- end: `0x18001ce5e`
- name: `?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z`
- size: `190`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e100`
- `0x18001e9b8`
- `0x1800281bc`

## callees

- `0x18001886c`
- `0x18001cda0`
- `0x18001d518`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001dec8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18001ce2c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001ce2c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001ce0d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001ce0d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18001ce1f`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18001ce1f`

## pseudocode

```c
int __fastcall ATL::CComSafeArray<tagVARIANT,12>::Add(SAFEARRAY **a1, const VARIANTARG *a2)
{
  int result; // eax
  LONG LowerBound; // edi
  int Count; // eax
  SAFEARRAY *v7; // rcx
  int v8; // eax
  SAFEARRAYBOUND psaboundNew; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 || (psaboundNew = 0, result = ATL::CComSafeArray<tagVARIANT,12>::Create(a1, &psaboundNew), result >= 0) )
  {
    LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(a1, (LONG)a2);
    Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
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
            v8 = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
            return ATL::CComSafeArray<tagVARIANT,12>::SetAt((__int64)a1, LowerBound + v8 - 1, a2);
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
0x18001cda0  mov     rax, rsp
0x18001cda3  mov     [rax+10h], rbx
0x18001cda7  mov     [rax+18h], rsi
0x18001cdab  push    rdi
0x18001cdac  sub     rsp, 20h
0x18001cdb0  cmp     qword ptr [rcx], 0
0x18001cdb4  mov     rsi, rdx
0x18001cdb7  mov     rbx, rcx
0x18001cdba  jnz     short loc_18001CDD1
0x18001cdbc  lea     rdx, [rax+8]
0x18001cdc0  mov     qword ptr [rax+8], 0
0x18001cdc8  call    ?Create@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJPEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::Create(tagSAFEARRAYBOUND const *,uint)
0x18001cdcd  test    eax, eax
0x18001cdcf  js      short loc_18001CE4E
0x18001cdd1  mov     rcx, rbx
0x18001cdd4  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001cdd9  mov     rcx, rbx
0x18001cddc  mov     edi, eax
0x18001cdde  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001cde3  mov     rcx, [rbx]; psa
0x18001cde6  inc     eax
0x18001cde8  mov     [rsp+28h+psaboundNew.cElements], eax
0x18001cdec  mov     [rsp+28h+psaboundNew.lLbound], edi
0x18001cdf0  test    rcx, rcx
0x18001cdf3  jnz     short loc_18001CE00
0x18001cdf5  mov     ecx, 80004005h; int
0x18001cdfa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ce00  test    byte ptr [rcx+2], 10h
0x18001ce04  jz      short loc_18001CE0D
0x18001ce06  mov     eax, 80004005h
0x18001ce0b  jmp     short loc_18001CE4E
0x18001ce0d  call    cs:__imp_SafeArrayUnlock
0x18001ce13  test    eax, eax
0x18001ce15  js      short loc_18001CE4E
0x18001ce17  mov     rcx, [rbx]; psa
0x18001ce1a  lea     rdx, [rsp+28h+psaboundNew]; psaboundNew
0x18001ce1f  call    cs:__imp_SafeArrayRedim
0x18001ce25  test    eax, eax
0x18001ce27  js      short loc_18001CE4E
0x18001ce29  mov     rcx, [rbx]; psa
0x18001ce2c  call    cs:__imp_SafeArrayLock
0x18001ce32  test    eax, eax
0x18001ce34  js      short loc_18001CE4E
0x18001ce36  mov     rcx, rbx
0x18001ce39  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001ce3e  mov     r8, rsi
0x18001ce41  mov     rcx, rbx
0x18001ce44  lea     edx, [rax-1]
0x18001ce47  add     edx, edi
0x18001ce49  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18001ce4e  mov     rbx, [rsp+28h+arg_8]
0x18001ce53  mov     rsi, [rsp+28h+arg_10]
0x18001ce58  add     rsp, 20h
0x18001ce5c  pop     rdi
0x18001ce5d  retn
```
