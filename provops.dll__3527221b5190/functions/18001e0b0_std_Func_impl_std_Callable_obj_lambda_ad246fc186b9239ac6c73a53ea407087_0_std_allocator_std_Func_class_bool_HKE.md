# std::_Func_impl_std::_Callable_obj__lambda_ad246fc186b9239ac6c73a53ea407087__0__std::allocator_std::_Func_class_bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call

- ea: `0x18001e0b0`
- end: `0x18001e1ca`
- name: `std::_Func_impl_std::_Callable_obj__lambda_ad246fc186b9239ac6c73a53ea407087__0__std::allocator_std::_Func_class_bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000a224`
- `0x18001b3a8`
- `0x18001e0b0`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e0d2`
- `msvcrt!_wcsicmp` at `0x18001e0d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e183`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e183`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e117`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e117`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001e0e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001e0e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall std::_Func_impl_std::_Callable_obj__lambda_ad246fc186b9239ac6c73a53ea407087__0__std::allocator_std::_Func_class_bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____bool_HKEY_____unsigned_short_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Do_call(
        __int64 a1,
        HKEY *a2,
        const wchar_t **a3)
{
  const WCHAR *v4; // rbx
  HKEY v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *); // rcx
  __int64 v10; // rax
  _BYTE *v11; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  _BYTE v15[24]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  _BYTE *v19; // [rsp+68h] [rbp+10h]

  v4 = *a3;
  v5 = *a2;
  if ( _wcsicmp(**(const wchar_t ***)(a1 + 8), *a3) )
  {
    hKey = 0;
    v7 = RegOpenKeyExW(v5, v4, 0, 0xF003Fu, &hKey);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x46C,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)v7,
        phkResulta);
    v19 = v15;
    v8 = *(_QWORD *)(a1 + 16);
    v16 = 0;
    v9 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v8 + 24);
    if ( v9 )
    {
      if ( v9 == (__int64 (__fastcall ***)(_QWORD, _BYTE *))v8 )
        v11 = v15;
      else
        v11 = 0;
      v10 = (**v9)(v9, v11);
    }
    else
    {
      v10 = 0;
    }
    v16 = v10;
    ForEachRegSubKey<std::function<bool (HKEY__ *,unsigned short const *)>>(hKey, (__int64)v15);
    if ( hKey )
      RegCloseKey(hKey);
    LOBYTE(v6) = 1;
  }
  else
  {
    v6 = RegDeleteTreeW(v5, v4);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x465,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)v6,
        phkResult);
  }
  return v6;
}

```

## disassembly

```asm
0x18001e0b0  mov     [rsp+arg_10], rbx
0x18001e0b5  mov     [rsp+arg_18], rsi
0x18001e0ba  push    rdi
0x18001e0bb  sub     rsp, 50h
0x18001e0bf  mov     rsi, rcx
0x18001e0c2  mov     rbx, [r8]
0x18001e0c5  mov     rdi, [rdx]
0x18001e0c8  mov     rcx, [rcx+8]
0x18001e0cc  mov     rdx, rbx; String2
0x18001e0cf  mov     rcx, [rcx]; String1
0x18001e0d2  call    cs:__imp__wcsicmp
0x18001e0d8  test    eax, eax
0x18001e0da  jnz     short loc_18001E0F5
0x18001e0dc  mov     rdx, rbx; lpSubKey
0x18001e0df  mov     rcx, rdi; hKey
0x18001e0e2  call    cs:__imp_RegDeleteTreeW
0x18001e0e8  test    eax, eax
0x18001e0ea  jnz     loc_18001E1B0
0x18001e0f0  jmp     loc_18001E18B
0x18001e0f5  mov     [rsp+58h+hKey], 0
0x18001e0fe  lea     rax, [rsp+58h+hKey]
0x18001e103  mov     qword ptr [rsp+58h+phkResult], rax; unsigned int
0x18001e108  mov     r9d, 0F003Fh; samDesired
0x18001e10e  xor     r8d, r8d; ulOptions
0x18001e111  mov     rdx, rbx; lpSubKey
0x18001e114  mov     rcx, rdi; hKey
0x18001e117  call    cs:__imp_RegOpenKeyExW
0x18001e11d  mov     rcx, [rsp+58h]; this
0x18001e122  test    eax, eax
0x18001e124  jnz     short loc_18001E19B
0x18001e126  lea     rax, [rsp+58h+var_28]
0x18001e12b  mov     [rsp+58h+arg_8], rax
0x18001e130  mov     rdx, [rsi+10h]
0x18001e134  mov     [rsp+58h+var_10], 0
0x18001e13d  mov     rcx, [rdx+18h]
0x18001e141  test    rcx, rcx
0x18001e144  jnz     short loc_18001E14A
0x18001e146  xor     eax, eax
0x18001e148  jmp     short loc_18001E164
0x18001e14a  mov     rax, [rcx]
0x18001e14d  mov     rax, [rax]
0x18001e150  cmp     rcx, rdx
0x18001e153  jnz     short loc_18001E15C
0x18001e155  lea     rdx, [rsp+58h+var_28]
0x18001e15a  jmp     short loc_18001E15E
0x18001e15c  xor     edx, edx
0x18001e15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e163  nop
0x18001e164  mov     [rsp+58h+var_10], rax
0x18001e169  lea     rdx, [rsp+58h+var_28]
0x18001e16e  mov     rcx, [rsp+58h+hKey]; hKey
0x18001e173  call    ??$ForEachRegSubKey@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@@YAKQEAUHKEY__@@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@Z; ForEachRegSubKey<std::function<bool (HKEY__ *,ushort const *)>>(HKEY__ * const,std::function<bool (HKEY__ *,ushort const *)>)
0x18001e178  nop
0x18001e179  mov     rcx, [rsp+58h+hKey]; hKey
0x18001e17e  test    rcx, rcx
0x18001e181  jz      short loc_18001E189
0x18001e183  call    cs:__imp_RegCloseKey
0x18001e189  mov     al, 1
0x18001e18b  mov     rbx, [rsp+58h+arg_10]
0x18001e190  mov     rsi, [rsp+58h+arg_18]
0x18001e195  add     rsp, 50h
0x18001e199  pop     rdi
0x18001e19a  retn
0x18001e19b  mov     r9d, eax; char *
0x18001e19e  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18001e1a5  mov     edx, 46Ch; void *
0x18001e1aa  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001e1b0  mov     rcx, [rsp+58h]; this
0x18001e1b5  mov     r9d, eax; char *
0x18001e1b8  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18001e1bf  mov     edx, 465h; void *
0x18001e1c4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
