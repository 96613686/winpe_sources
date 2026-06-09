# RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)

- ea: `0x18003044c`
- end: `0x180030527`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180013e00`
- `0x18001926c`
- `0x18001a2f0`
- `0x18001a758`
- `0x18001b200`
- `0x18001b7cc`
- `0x18001c0fc`

## callees

- `0x180002a90`
- `0x1800072cc`
- `0x1800118e8`
- `0x180011908`
- `0x180018f34`
- `0x18001c4f0`
- `0x1800302fc`
- `0x18003044c`
- `0x1800311c8`

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
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v10);
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
      *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr() = 0;
    }
  }
  HeapAllocator::Free(v8);
  return v4;
}

```

## disassembly

```asm
0x18003044c  mov     r11, rsp
0x18003044f  mov     [r11+20h], rbx
0x180030453  push    rsi
0x180030454  sub     rsp, 70h
0x180030458  mov     rax, cs:__security_cookie
0x18003045f  xor     rax, rsp
0x180030462  mov     [rsp+78h+var_10], rax
0x180030467  mov     rbx, r8
0x18003046a  mov     [rsp+78h+var_48], 0
0x180030472  mov     qword ptr [r11-40h], 0
0x18003047a  mov     qword ptr [r11-38h], 0
0x180030482  lea     r9, [r11-40h]
0x180030486  lea     r8, [r11-48h]
0x18003048a  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z; RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)
0x18003048f  mov     esi, eax
0x180030491  test    eax, eax
0x180030493  jnz     short loc_180030500
0x180030495  mov     r8, [rsp+78h+var_38]
0x18003049a  test    r8, r8
0x18003049d  jnz     short loc_1800304B2
0x18003049f  mov     [rbx+10h], r8
0x1800304a3  mov     rcx, rbx
0x1800304a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800304ab  xor     ecx, ecx
0x1800304ad  mov     [rax], cx
0x1800304b0  jmp     short loc_180030500
0x1800304b2  cmp     [rsp+78h+var_48], 2
0x1800304b7  jnz     short loc_1800304DF
0x1800304b9  mov     rdx, [rsp+78h+var_40]
0x1800304be  lea     rcx, [rsp+78h+var_30]
0x1800304c3  call    ?ExpandEnvironmentString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@PEB_W@Z; ExpandEnvironmentString(wchar_t const *)
0x1800304c8  mov     rdx, rax
0x1800304cb  mov     rcx, rbx
0x1800304ce  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x1800304d3  lea     rcx, [rsp+78h+var_30]
0x1800304d8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800304dd  jmp     short loc_180030500
0x1800304df  cmp     [rsp+78h+var_48], 1
0x1800304e4  jnz     short loc_1800304FB
0x1800304e6  shr     r8, 1
0x1800304e9  dec     r8
0x1800304ec  mov     rdx, [rsp+78h+var_40]
0x1800304f1  mov     rcx, rbx
0x1800304f4  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x1800304f9  jmp     short loc_180030500
0x1800304fb  mov     esi, 2
0x180030500  mov     rcx, [rsp+78h+var_40]; void *
0x180030505  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18003050a  mov     eax, esi
0x18003050c  mov     rcx, [rsp+78h+var_10]
0x180030511  xor     rcx, rsp; StackCookie
0x180030514  call    __security_check_cookie
0x180030519  mov     rbx, [rsp+78h+arg_18]
0x180030521  add     rsp, 70h
0x180030525  pop     rsi
0x180030526  retn
```
