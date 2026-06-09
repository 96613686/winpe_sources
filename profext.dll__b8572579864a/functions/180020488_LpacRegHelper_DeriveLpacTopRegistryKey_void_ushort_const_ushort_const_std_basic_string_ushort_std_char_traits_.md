# LpacRegHelper::DeriveLpacTopRegistryKey(void *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180020488`
- end: `0x180020550`
- name: `?DeriveLpacTopRegistryKey@LpacRegHelper@@CAJPEAXPEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f7b0`
- `0x18001fa9c`
- `0x18001fdec`
- `0x180020f70`

## callees

- `0x180004594`
- `0x18000c7d4`
- `0x18001ef5c`
- `0x180020488`
- `0x1800218a0`

## string_xrefs

- `0x1800204b0`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x1800204f9`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LpacRegHelper::DeriveLpacTopRegistryKey(_WORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // r8
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _WORD *v12; // [rsp+30h] [rbp+8h] BYREF

  v12 = a1;
  if ( !a2 )
  {
    v5 = 707;
LABEL_3:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      v10);
    return v6;
  }
  if ( !a3 )
  {
    v5 = 708;
    goto LABEL_3;
  }
  v12 = 0;
  v7 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &v12,
         L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\LpacApi\\%s",
         a3,
         a2);
  v6 = v7;
  if ( v7 >= 0 )
  {
    if ( *v12 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v12[v8] );
    }
    else
    {
      v8 = 0;
    }
    std::wstring::assign(a4, v12, v8);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v7,
      v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v12);
  return v6;
}

```

## disassembly

```asm
0x180020488  mov     [rsp+arg_8], rbx
0x18002048d  mov     [rsp+arg_10], rsi
0x180020492  mov     [rsp+arg_0], rcx
0x180020497  push    rdi; int
0x180020498  sub     rsp, 20h
0x18002049c  mov     rdi, r9
0x18002049f  xor     esi, esi
0x1800204a1  test    rdx, rdx
0x1800204a4  jnz     short loc_1800204C6
0x1800204a6  mov     edx, 2C3h; void *
0x1800204ab  mov     ebx, 80070057h
0x1800204b0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800204b7  mov     r9d, ebx; char *
0x1800204ba  mov     rcx, [rsp+28h]; this
0x1800204bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204c4  jmp     short loc_18002053D
0x1800204c6  test    r8, r8
0x1800204c9  jnz     short loc_1800204D2
0x1800204cb  mov     edx, 2C4h
0x1800204d0  jmp     short loc_1800204AB
0x1800204d2  mov     [rsp+28h+arg_0], rsi
0x1800204d7  mov     r9, rdx
0x1800204da  lea     rdx, aSSoftwareClass_0; "%s\\Software\\Classes\\Local Settings\\"...
0x1800204e1  lea     rcx, [rsp+28h+arg_0]
0x1800204e6  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800204eb  mov     ebx, eax
0x1800204ed  test    eax, eax
0x1800204ef  jns     short loc_18002050C
0x1800204f1  mov     rcx, [rsp+28h]; this
0x1800204f6  mov     r9d, eax; char *
0x1800204f9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020500  mov     edx, 2CCh; void *
0x180020505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002050a  jmp     short loc_180020533
0x18002050c  mov     rdx, [rsp+28h+arg_0]
0x180020511  cmp     [rdx], si
0x180020514  jnz     short loc_18002051B
0x180020516  mov     r8, rsi
0x180020519  jmp     short loc_180020529
0x18002051b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002051f  inc     r8
0x180020522  cmp     [rdx+r8*2], si
0x180020527  jnz     short loc_18002051F
0x180020529  mov     rcx, rdi
0x18002052c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180020531  mov     ebx, esi
0x180020533  lea     rcx, [rsp+28h+arg_0]
0x180020538  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18002053d  mov     eax, ebx
0x18002053f  mov     rbx, [rsp+28h+arg_8]
0x180020544  mov     rsi, [rsp+28h+arg_10]
0x180020549  add     rsp, 20h
0x18002054d  pop     rdi
0x18002054e  retn
```
