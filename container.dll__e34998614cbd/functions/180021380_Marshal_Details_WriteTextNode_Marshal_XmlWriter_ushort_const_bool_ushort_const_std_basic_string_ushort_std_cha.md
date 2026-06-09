# Marshal::Details::WriteTextNode(Marshal::XmlWriter &,ushort const *,bool,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180021380`
- end: `0x180021520`
- name: `?WriteTextNode@Details@Marshal@@YAXAEAUXmlWriter@2@PEBG_N1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `416`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017550`
- `0x180018460`
- `0x1800185f4`
- `0x180018950`
- `0x180019f40`
- `0x18001a0a0`
- `0x18001a6f0`
- `0x18001a7d0`
- `0x18001a8b0`
- `0x18001a990`
- `0x18001aa70`
- `0x18001ab50`
- `0x18001abf0`

## callees

- `0x18000bdc8`
- `0x180021380`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x18002148c`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800214a6`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800214c0`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800214d7`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800214f1`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18002150b`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteTextNode(_QWORD *a1, __int64 a2, char a3, const char *a4, __int64 *a5)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 result; // rax
  int v11; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a3 )
  {
    if ( !a2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x5BC,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        a4);
    v8 = *a1;
    LODWORD(v9) = (_DWORD)a5;
    if ( (unsigned __int64)a5[3] > 7 )
      v9 = *a5;
    v14 = v9;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v8 + 56LL))(v8, 0, a2, 0);
    if ( (int)result < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5BD,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)result,
        v14);
  }
  else
  {
    if ( a2 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*a1 + 216LL))(*a1, 0, a2, 0);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5C3,
          (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
          (const char *)(unsigned int)v11,
          v13);
    }
    if ( a4 )
    {
      v13 = (int)a4;
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)*a1 + 56LL))(
              *a1,
              0,
              L"type",
              0);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5C8,
          (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
          (const char *)(unsigned int)v12,
          (int)a4);
    }
    result = (*(__int64 (**)(void))(*(_QWORD *)*a1 + 224LL))();
    if ( (int)result < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5CB,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)result,
        v13);
    if ( a2 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 120LL))(*a1);
      if ( (int)result < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5CE,
          (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
          (const char *)(unsigned int)result,
          v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021380  mov     [rsp+arg_0], rbx
0x180021385  mov     [rsp+arg_8], rsi
0x18002138a  push    rdi
0x18002138b  sub     rsp, 30h
0x18002138f  mov     rsi, r9
0x180021392  mov     rbx, rdx
0x180021395  mov     rdi, rcx
0x180021398  test    r8b, r8b
0x18002139b  jz      short loc_1800213E1
0x18002139d  test    rdx, rdx
0x1800213a0  jz      loc_1800214BB
0x1800213a6  mov     rcx, [rcx]
0x1800213a9  mov     rax, [rcx]
0x1800213ac  mov     r10, [rax+38h]
0x1800213b0  mov     rax, qword ptr [rsp+38h+arg_20]
0x1800213b5  cmp     qword ptr [rax+18h], 7
0x1800213ba  jbe     short loc_1800213BF
0x1800213bc  mov     rax, [rax]
0x1800213bf  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800213c4  xor     r9d, r9d
0x1800213c7  mov     rax, r10
0x1800213ca  mov     r8, rbx
0x1800213cd  xor     edx, edx
0x1800213cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213d4  test    eax, eax
0x1800213d6  js      loc_1800214A1
0x1800213dc  jmp     loc_180021476
0x1800213e1  test    rbx, rbx
0x1800213e4  jz      short loc_180021408
0x1800213e6  mov     rcx, [rcx]
0x1800213e9  xor     r9d, r9d
0x1800213ec  mov     r8, rbx
0x1800213ef  xor     edx, edx
0x1800213f1  mov     rax, [rcx]
0x1800213f4  mov     rax, [rax+0D8h]
0x1800213fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021400  test    eax, eax
0x180021402  js      loc_1800214D2
0x180021408  test    rsi, rsi
0x18002140b  jz      short loc_180021435
0x18002140d  mov     rcx, [rdi]
0x180021410  lea     r8, aType; "type"
0x180021417  xor     r9d, r9d
0x18002141a  mov     qword ptr [rsp+38h+var_18], rsi; int
0x18002141f  xor     edx, edx
0x180021421  mov     rax, [rcx]
0x180021424  mov     rax, [rax+38h]
0x180021428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002142d  test    eax, eax
0x18002142f  js      loc_1800214EC
0x180021435  mov     rdx, qword ptr [rsp+38h+arg_20]
0x18002143a  mov     rcx, [rdi]
0x18002143d  cmp     qword ptr [rdx+18h], 7
0x180021442  mov     rax, [rcx]
0x180021445  jbe     short loc_18002144A
0x180021447  mov     rdx, [rdx]
0x18002144a  mov     rax, [rax+0E0h]
0x180021451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021456  test    eax, eax
0x180021458  js      loc_180021506
0x18002145e  test    rbx, rbx
0x180021461  jz      short loc_180021476
0x180021463  mov     rcx, [rdi]
0x180021466  mov     rax, [rcx]
0x180021469  mov     rax, [rax+78h]
0x18002146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021472  test    eax, eax
0x180021474  js      short loc_180021487
0x180021476  mov     rbx, [rsp+38h+arg_0]
0x18002147b  mov     rsi, [rsp+38h+arg_8]
0x180021480  add     rsp, 30h
0x180021484  pop     rdi
0x180021485  retn
0x180021487  mov     rcx, [rsp+38h]; this
0x18002148c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180021493  mov     r9d, eax; char *
0x180021496  mov     edx, 5CEh; void *
0x18002149b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800214a1  mov     rcx, [rsp+38h]; this
0x1800214a6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800214ad  mov     r9d, eax; char *
0x1800214b0  mov     edx, 5BDh; void *
0x1800214b5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800214bb  mov     rcx, [rsp+38h]; this
0x1800214c0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800214c7  mov     edx, 5BCh; void *
0x1800214cc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800214d2  mov     rcx, [rsp+38h]; this
0x1800214d7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800214de  mov     r9d, eax; char *
0x1800214e1  mov     edx, 5C3h; void *
0x1800214e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800214ec  mov     rcx, [rsp+38h]; this
0x1800214f1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800214f8  mov     r9d, eax; char *
0x1800214fb  mov     edx, 5C8h; void *
0x180021500  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021506  mov     rcx, [rsp+38h]; this
0x18002150b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180021512  mov     r9d, eax; char *
0x180021515  mov     edx, 5CBh; void *
0x18002151a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
