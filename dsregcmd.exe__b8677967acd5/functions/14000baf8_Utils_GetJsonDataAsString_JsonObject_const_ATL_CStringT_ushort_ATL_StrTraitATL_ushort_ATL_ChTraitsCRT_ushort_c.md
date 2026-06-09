# Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14000baf8`
- end: `0x14000bbe7`
- name: `?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, _WORD **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000ea0c`
- `0x1400251d4`

## callees

- `0x140001b60`
- `0x140003044`
- `0x1400032ec`
- `0x1400061dc`
- `0x14000baf8`
- `0x14001d2d4`
- `0x14001d36c`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Utils::GetJsonDataAsString(_QWORD *a1, __int64 a2, _WORD **a3)
{
  _QWORD *v6; // rax
  __int64 ValueForName; // rbx
  _QWORD *StringValue; // rax
  __int64 v9; // r8
  char *v11[4]; // [rsp+30h] [rbp-68h] BYREF
  char *v12[4]; // [rsp+50h] [rbp-48h] BYREF

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v6 = std::wstring::wstring(v11, *a3);
  ValueForName = JsonObject::GetValueForName(a2, v6);
  std::wstring::~wstring(v11);
  if ( ValueForName && (unsigned int)(*(_DWORD *)(ValueForName + 8) - 3) <= 2 )
  {
    StringValue = (_QWORD *)JsonPrimitive::GetStringValue(ValueForName, v12);
    if ( StringValue[3] > 7u )
      StringValue = (_QWORD *)*StringValue;
    if ( StringValue )
    {
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)StringValue + v9) );
    }
    else
    {
      v9 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, StringValue, v9);
    std::wstring::~wstring(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x14000baf8  push    rbx
0x14000bafa  push    rsi
0x14000bafb  push    rdi
0x14000bafc  sub     rsp, 80h
0x14000bb03  mov     rax, cs:__security_cookie
0x14000bb0a  xor     rax, rsp
0x14000bb0d  mov     [rsp+98h+var_28], rax
0x14000bb12  mov     rbx, r8
0x14000bb15  mov     rdi, rdx
0x14000bb18  mov     rsi, rcx
0x14000bb1b  mov     [rsp+98h+var_70], rcx
0x14000bb20  mov     [rsp+98h+var_78], 1
0x14000bb28  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000bb2f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000bb36  mov     rax, [rax+18h]
0x14000bb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb3f  add     rax, 18h
0x14000bb43  mov     [rsi], rax
0x14000bb46  mov     [rsp+98h+var_78], 1
0x14000bb4e  mov     rdx, [rbx]
0x14000bb51  lea     rcx, [rsp+98h+var_68]
0x14000bb56  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000bb5b  mov     rdx, rax
0x14000bb5e  mov     rcx, rdi
0x14000bb61  call    ?GetValueForName@JsonObject@@QEBAPEBVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JsonObject::GetValueForName(std::wstring const &)
0x14000bb66  mov     rbx, rax
0x14000bb69  lea     rcx, [rsp+98h+var_68]
0x14000bb6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bb73  xor     edi, edi
0x14000bb75  test    rbx, rbx
0x14000bb78  jz      short loc_14000BBCC
0x14000bb7a  mov     eax, [rbx+8]
0x14000bb7d  sub     eax, 3
0x14000bb80  cmp     eax, 2
0x14000bb83  ja      short loc_14000BBCC
0x14000bb85  lea     rdx, [rsp+98h+var_48]
0x14000bb8a  mov     rcx, rbx
0x14000bb8d  call    ?GetStringValue@JsonPrimitive@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; JsonPrimitive::GetStringValue(void)
0x14000bb92  nop
0x14000bb93  cmp     qword ptr [rax+18h], 7
0x14000bb98  jbe     short loc_14000BB9D
0x14000bb9a  mov     rax, [rax]
0x14000bb9d  test    rax, rax
0x14000bba0  jnz     short loc_14000BBA7
0x14000bba2  mov     r8d, edi
0x14000bba5  jmp     short loc_14000BBB5
0x14000bba7  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000bbab  inc     r8
0x14000bbae  cmp     [rax+r8*2], di
0x14000bbb3  jnz     short loc_14000BBAB
0x14000bbb5  mov     rdx, rax
0x14000bbb8  mov     rcx, rsi
0x14000bbbb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000bbc0  nop
0x14000bbc1  lea     rcx, [rsp+98h+var_48]
0x14000bbc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bbcb  nop
0x14000bbcc  mov     rax, rsi
0x14000bbcf  mov     rcx, [rsp+98h+var_28]
0x14000bbd4  xor     rcx, rsp; StackCookie
0x14000bbd7  call    __security_check_cookie
0x14000bbdc  add     rsp, 80h
0x14000bbe3  pop     rdi
0x14000bbe4  pop     rsi
0x14000bbe5  pop     rbx
0x14000bbe6  retn
```
