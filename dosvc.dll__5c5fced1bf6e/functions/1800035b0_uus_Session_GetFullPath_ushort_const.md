# uus::Session::GetFullPath(ushort const *)

- ea: `0x1800035b0`
- end: `0x1800036a2`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z`
- size: `242`
- prototype: `void *__fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180003448`

## callees

- `0x1800010f0`
- `0x180001520`
- `0x1800015e0`
- `0x1800035b0`
- `0x1800036b4`
- `0x180003700`
- `0x180005020`
- `0x18000b010`

## string_xrefs

- `0x1800035de`: `doclient.dll`

## pseudocode

```c
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 StableFolder; // rax
  const WCHAR *v9; // [rsp+30h] [rbp-29h] BYREF
  __int64 v10; // [rsp+38h] [rbp-21h]
  _BYTE v11[32]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp+17h] BYREF

  v9 = L"doclient.dll";
  v10 = 12;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v12, &v9);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v9 = (const WCHAR *)v5;
    v10 = v6;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v11, &v9);
  }
  else
  {
    StableFolder = uus::Utility::GetStableFolder(&v9);
    uus::Utility::GetGuestOrNativeArchFolder(v11, StableFolder);
    std::wstring::_Tidy_deallocate(&v9);
  }
  std::filesystem::operator/(a2, v11, (std::filesystem *)v12);
  std::wstring::_Tidy_deallocate(v11);
  std::wstring::_Tidy_deallocate(v12);
  return a2;
}

```

## disassembly

```asm
0x1800035b0  mov     [rsp-8+arg_10], rbx
0x1800035b5  push    rbp
0x1800035b6  push    rsi
0x1800035b7  push    rdi
0x1800035b8  lea     rbp, [rsp-47h]
0x1800035bd  sub     rsp, 0A0h
0x1800035c4  mov     rax, cs:__security_cookie
0x1800035cb  xor     rax, rsp
0x1800035ce  mov     [rbp+57h+var_20], rax
0x1800035d2  mov     rdi, rdx
0x1800035d5  mov     rbx, rcx
0x1800035d8  mov     [rbp+57h+var_80], rdx
0x1800035dc  xor     esi, esi
0x1800035de  lea     rax, aDoclientDll; "doclient.dll"
0x1800035e5  mov     [rbp+57h+var_80], rax
0x1800035e9  mov     [rbp+57h+var_78], 0Ch
0x1800035f1  lea     rdx, [rbp+57h+var_80]
0x1800035f5  lea     rcx, [rbp+57h+var_40]
0x1800035f9  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1800035fe  nop
0x1800035ff  mov     rcx, [rbx+8]
0x180003603  test    rcx, rcx
0x180003606  jz      short loc_18000363B
0x180003608  mov     rax, [rcx]
0x18000360b  lea     edx, [rsi+1]
0x18000360e  mov     rax, [rax+28h]
0x180003612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003617  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000361b  inc     rcx
0x18000361e  cmp     [rax+rcx*2], si
0x180003622  jnz     short loc_18000361B
0x180003624  mov     [rbp+57h+var_80], rax
0x180003628  mov     [rbp+57h+var_78], rcx
0x18000362c  lea     rdx, [rbp+57h+var_80]
0x180003630  lea     rcx, [rbp+57h+var_60]
0x180003634  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180003639  jmp     short loc_18000365C
0x18000363b  lea     rcx, [rbp+57h+var_80]
0x18000363f  call    ?GetStableFolder@Utility@uus@@SA?AVpath@filesystem@std@@XZ; uus::Utility::GetStableFolder(void)
0x180003644  nop
0x180003645  mov     rdx, rax
0x180003648  lea     rcx, [rbp+57h+var_60]
0x18000364c  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180003651  nop
0x180003652  lea     rcx, [rbp+57h+var_80]
0x180003656  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000365b  nop
0x18000365c  lea     r8, [rbp+57h+var_40]; this
0x180003660  lea     rdx, [rbp+57h+var_60]; void *
0x180003664  mov     rcx, rdi; Src
0x180003667  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000366c  nop
0x18000366d  lea     rcx, [rbp+57h+var_60]
0x180003671  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003676  nop
0x180003677  lea     rcx, [rbp+57h+var_40]
0x18000367b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003680  mov     rax, rdi
0x180003683  mov     rcx, [rbp+57h+var_20]
0x180003687  xor     rcx, rsp; StackCookie
0x18000368a  call    __security_check_cookie
0x18000368f  mov     rbx, [rsp+0B0h+arg_10]
0x180003697  add     rsp, 0A0h
0x18000369e  pop     rdi
0x18000369f  pop     rsi
0x1800036a0  pop     rbp
0x1800036a1  retn
```
