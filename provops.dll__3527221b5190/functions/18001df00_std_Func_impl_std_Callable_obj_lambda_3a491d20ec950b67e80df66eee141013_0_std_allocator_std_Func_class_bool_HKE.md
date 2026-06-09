# std::_Func_impl_std::_Callable_obj__lambda_3a491d20ec950b67e80df66eee141013__0__std::allocator_std::_Func_class_bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call

- ea: `0x18001df00`
- end: `0x18001e0a0`
- name: `std::_Func_impl_std::_Callable_obj__lambda_3a491d20ec950b67e80df66eee141013__0__std::allocator_std::_Func_class_bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x18000a224`
- `0x18000a3e4`
- `0x18000de00`
- `0x18001b3a8`
- `0x18001df00`
- `0x180020fe0`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e038`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e057`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001e01f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001e01f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001df44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001df44`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall std::_Func_impl_std::_Callable_obj__lambda_3a491d20ec950b67e80df66eee141013__0__std::allocator_std::_Func_class_bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call(
        __int64 a1,
        HKEY *a2,
        const WCHAR **a3)
{
  const WCHAR *v4; // rax
  HKEY v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 (__fastcall ***v8)(_QWORD, __int128 *); // rcx
  __int64 v9; // rax
  __int128 *v10; // rdx
  void **i; // rbx
  void **v12; // rdi
  const WCHAR *v13; // rdx
  unsigned int v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-29h]
  HKEY hKey; // [rsp+30h] [rbp-19h] BYREF
  __int128 v18; // [rsp+38h] [rbp-11h] BYREF
  __int64 v19; // [rsp+48h] [rbp-1h]
  __int64 v20; // [rsp+50h] [rbp+7h]
  LPCWSTR lpValueName[3]; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int64 v22; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v4 = *a3;
  v5 = *a2;
  hKey = 0;
  v6 = RegOpenKeyExW(v5, v4, 0, 0xF003Fu, &hKey);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47E,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)v6,
      phkResult);
  lpValueName[0] = (LPCWSTR)&v18;
  v7 = *(_QWORD *)(a1 + 8);
  v20 = 0;
  v8 = *(__int64 (__fastcall ****)(_QWORD, __int128 *))(v7 + 24);
  if ( v8 )
  {
    if ( v8 == (__int64 (__fastcall ***)(_QWORD, __int128 *))v7 )
      v10 = &v18;
    else
      v10 = 0;
    v9 = (**v8)(v8, v10);
  }
  else
  {
    v9 = 0;
  }
  v20 = v9;
  if ( !(unsigned int)ForEachRegSubKey<std::function<bool (HKEY__ *,unsigned short const *)>>(hKey, (__int64)&v18) )
  {
    v18 = 0;
    v19 = 0;
    lpValueName[0] = *(LPCWSTR *)(a1 + 16);
    lpValueName[1] = (LPCWSTR)&v18;
    ForEachRegValue__lambda_fbd86aa7485f14e8675becbcee7181c7_(hKey);
    v12 = (void **)*((_QWORD *)&v18 + 1);
    for ( i = (void **)v18; i != v12; i += 4 )
    {
      v22 = 7;
      lpValueName[2] = 0;
      LOWORD(lpValueName[0]) = 0;
      std::wstring::assign((void **)lpValueName, i, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v13 = (const WCHAR *)lpValueName;
      if ( v22 >= 8 )
        v13 = lpValueName[0];
      v14 = RegDeleteValueW(hKey, v13);
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x49C,
          (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
          (const char *)v14,
          phkResult);
      if ( v22 >= 8 )
        operator delete((void *)lpValueName[0]);
    }
    std::vector<std::wstring>::_Tidy((__int64)&v18);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18001df00  push    rbp
0x18001df02  push    rbx
0x18001df03  push    rdi
0x18001df04  lea     rbp, [rsp-47h]
0x18001df09  sub     rsp, 90h
0x18001df10  mov     rax, cs:__security_cookie
0x18001df17  xor     rax, rsp
0x18001df1a  mov     [rbp+57h+var_20], rax
0x18001df1e  mov     rbx, rcx
0x18001df21  mov     rax, [r8]
0x18001df24  mov     rcx, [rdx]; hKey
0x18001df27  mov     [rbp+57h+hKey], 0
0x18001df2f  lea     rdx, [rbp+57h+hKey]
0x18001df33  mov     qword ptr [rsp+0A0h+phkResult], rdx; unsigned int
0x18001df38  mov     r9d, 0F003Fh; samDesired
0x18001df3e  xor     r8d, r8d; ulOptions
0x18001df41  mov     rdx, rax; lpSubKey
0x18001df44  call    cs:__imp_RegOpenKeyExW
0x18001df4a  mov     rcx, [rbp+5Fh]; this
0x18001df4e  test    eax, eax
0x18001df50  jnz     loc_18001E08B
0x18001df56  lea     rax, [rbp+57h+var_68]
0x18001df5a  mov     [rbp+57h+lpValueName], rax
0x18001df5e  mov     rdx, [rbx+8]
0x18001df62  mov     [rbp+57h+var_50], 0
0x18001df6a  mov     rcx, [rdx+18h]
0x18001df6e  test    rcx, rcx
0x18001df71  jnz     short loc_18001DF77
0x18001df73  xor     eax, eax
0x18001df75  jmp     short loc_18001DF90
0x18001df77  mov     rax, [rcx]
0x18001df7a  mov     rax, [rax]
0x18001df7d  cmp     rcx, rdx
0x18001df80  jnz     short loc_18001DF88
0x18001df82  lea     rdx, [rbp+57h+var_68]
0x18001df86  jmp     short loc_18001DF8A
0x18001df88  xor     edx, edx
0x18001df8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df8f  nop
0x18001df90  mov     [rbp+57h+var_50], rax
0x18001df94  lea     rdx, [rbp+57h+var_68]
0x18001df98  mov     rcx, [rbp+57h+hKey]; hKey
0x18001df9c  call    ??$ForEachRegSubKey@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@@YAKQEAUHKEY__@@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@Z; ForEachRegSubKey<std::function<bool (HKEY__ *,ushort const *)>>(HKEY__ * const,std::function<bool (HKEY__ *,ushort const *)>)
0x18001dfa1  test    eax, eax
0x18001dfa3  jnz     loc_18001E04E
0x18001dfa9  xorps   xmm0, xmm0
0x18001dfac  movdqu  [rbp+57h+var_68], xmm0
0x18001dfb1  mov     [rbp+57h+var_58], 0
0x18001dfb9  mov     rax, [rbx+10h]
0x18001dfbd  mov     [rbp+57h+lpValueName], rax
0x18001dfc1  lea     rax, [rbp+57h+var_68]
0x18001dfc5  mov     [rbp+57h+var_38], rax
0x18001dfc9  lea     rdx, [rbp+57h+lpValueName]
0x18001dfcd  mov     rcx, [rbp+57h+hKey]; hKey
0x18001dfd1  call    ForEachRegValue__lambda_fbd86aa7485f14e8675becbcee7181c7___; ForEachRegValue__lambda_fbd86aa7485f14e8675becbcee7181c7_
0x18001dfd6  mov     rbx, qword ptr [rbp+57h+var_68]
0x18001dfda  mov     rdi, qword ptr [rbp+57h+var_68+8]
0x18001dfde  cmp     rbx, rdi
0x18001dfe1  jz      short loc_18001E044
0x18001dfe3  mov     [rbp+57h+var_28], 7
0x18001dfeb  mov     [rbp+57h+var_30], 0
0x18001dff3  xor     eax, eax
0x18001dff5  mov     word ptr [rbp+57h+lpValueName], ax
0x18001dff9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001dffd  xor     r8d, r8d
0x18001e000  mov     rdx, rbx
0x18001e003  lea     rcx, [rbp+57h+lpValueName]; void *
0x18001e007  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001e00c  nop
0x18001e00d  lea     rdx, [rbp+57h+lpValueName]
0x18001e011  cmp     [rbp+57h+var_28], 8
0x18001e016  cmovnb  rdx, [rbp+57h+lpValueName]; lpValueName
0x18001e01b  mov     rcx, [rbp+57h+hKey]; hKey
0x18001e01f  call    cs:__imp_RegDeleteValueW
0x18001e025  mov     rcx, [rbp+5Fh]; this
0x18001e029  test    eax, eax
0x18001e02b  jnz     short loc_18001E076
0x18001e02d  cmp     [rbp+57h+var_28], 8
0x18001e032  jb      short loc_18001E03E
0x18001e034  mov     rcx, [rbp+57h+lpValueName]
0x18001e038  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e03e  add     rbx, 20h ; ' '
0x18001e042  jmp     short loc_18001DFDE
0x18001e044  lea     rcx, [rbp+57h+var_68]
0x18001e048  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001e04d  nop
0x18001e04e  mov     rcx, [rbp+57h+hKey]; hKey
0x18001e052  test    rcx, rcx
0x18001e055  jz      short loc_18001E05D
0x18001e057  call    cs:__imp_RegCloseKey
0x18001e05d  mov     al, 1
0x18001e05f  mov     rcx, [rbp+57h+var_20]
0x18001e063  xor     rcx, rsp; StackCookie
0x18001e066  call    __security_check_cookie
0x18001e06b  add     rsp, 90h
0x18001e072  pop     rdi
0x18001e073  pop     rbx
0x18001e074  pop     rbp
0x18001e075  retn
0x18001e076  mov     r9d, eax; char *
0x18001e079  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18001e080  mov     edx, 49Ch; void *
0x18001e085  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001e08b  mov     r9d, eax; char *
0x18001e08e  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18001e095  mov     edx, 47Eh; void *
0x18001e09a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
