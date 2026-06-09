# RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)

- ea: `0x18003165c`
- end: `0x180031738`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `220`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800145f0`
- `0x180019c34`
- `0x18001acdc`
- `0x18001b14c`
- `0x18001bc10`
- `0x18001c1e4`
- `0x18001cb34`

## callees

- `0x180002af0`
- `0x180007564`
- `0x18001204c`
- `0x18001206c`
- `0x1800198ec`
- `0x18001cf5c`
- `0x18003152c`
- `0x18003165c`
- `0x180032398`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryKey::QueryValue(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // esi
  __int64 v5; // rax
  int v7; // [rsp+30h] [rbp-48h] BYREF
  void *v8; // [rsp+38h] [rbp-40h] BYREF
  __int64 v9; // [rsp+40h] [rbp-38h]
  _BYTE v10[32]; // [rsp+48h] [rbp-30h] BYREF

  v7 = 0;
  v8 = 0;
  v9 = 0;
  v4 = RegistryKey::QueryValue(a1, a2, &v7, &v8);
  if ( !v4 )
  {
    if ( v9 )
    {
      if ( v7 == 2 )
      {
        v5 = ExpandEnvironmentString(v10, v8);
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(a3, v5);
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v10);
      }
      else if ( v7 == 1 )
      {
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(a3, v8);
      }
      else
      {
        v4 = 2;
      }
    }
    else
    {
      *(_QWORD *)(a3 + 16) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3) = 0;
    }
  }
  HeapAllocator::Free(v8);
  return v4;
}

```

## disassembly

```asm
0x18003165c  mov     r11, rsp
0x18003165f  mov     [r11+20h], rbx
0x180031663  push    rsi
0x180031664  sub     rsp, 70h
0x180031668  mov     rax, cs:__security_cookie
0x18003166f  xor     rax, rsp
0x180031672  mov     [rsp+78h+var_10], rax
0x180031677  mov     rbx, r8
0x18003167a  mov     [rsp+78h+var_48], 0
0x180031682  mov     qword ptr [r11-40h], 0
0x18003168a  mov     qword ptr [r11-38h], 0
0x180031692  lea     r9, [r11-40h]
0x180031696  lea     r8, [r11-48h]
0x18003169a  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z; RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)
0x18003169f  mov     esi, eax
0x1800316a1  test    eax, eax
0x1800316a3  jnz     short loc_180031710
0x1800316a5  mov     r8, [rsp+78h+var_38]
0x1800316aa  test    r8, r8
0x1800316ad  jnz     short loc_1800316C2
0x1800316af  mov     [rbx+10h], r8
0x1800316b3  mov     rcx, rbx
0x1800316b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800316bb  xor     ecx, ecx
0x1800316bd  mov     [rax], cx
0x1800316c0  jmp     short loc_180031710
0x1800316c2  cmp     [rsp+78h+var_48], 2
0x1800316c7  jnz     short loc_1800316EF
0x1800316c9  mov     rdx, [rsp+78h+var_40]
0x1800316ce  lea     rcx, [rsp+78h+var_30]
0x1800316d3  call    ?ExpandEnvironmentString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@PEB_W@Z; ExpandEnvironmentString(wchar_t const *)
0x1800316d8  mov     rdx, rax
0x1800316db  mov     rcx, rbx
0x1800316de  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x1800316e3  lea     rcx, [rsp+78h+var_30]
0x1800316e8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800316ed  jmp     short loc_180031710
0x1800316ef  cmp     [rsp+78h+var_48], 1
0x1800316f4  jnz     short loc_18003170B
0x1800316f6  shr     r8, 1
0x1800316f9  dec     r8
0x1800316fc  mov     rdx, [rsp+78h+var_40]
0x180031701  mov     rcx, rbx
0x180031704  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x180031709  jmp     short loc_180031710
0x18003170b  mov     esi, 2
0x180031710  mov     rcx, [rsp+78h+var_40]; void *
0x180031715  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18003171a  mov     eax, esi
0x18003171c  mov     rcx, [rsp+78h+var_10]
0x180031721  xor     rcx, rsp; StackCookie
0x180031724  call    __security_check_cookie
0x180031729  mov     rbx, [rsp+78h+arg_18]
0x180031731  add     rsp, 70h
0x180031735  pop     rsi
0x180031736  retn
```
