# Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800176fc`
- end: `0x18001775d`
- name: `?ExactDeleteBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `97`
- prototype: `int __fastcall(__int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015cd0`

## callees

- `0x180014f58`
- `0x1800176fc`
- `0x180017ab8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180017745`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180017745`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001771e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001771e`

## pseudocode

```c
int __fastcall Microsoft::IoT::ShellExtension::CAppManager::ExactDeleteBackgroundTask(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  const WCHAR *v5; // rax
  LPCWSTR v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180026650);
  v7 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v5, v6);
  if ( v7 )
  {
    v9 = 99;
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)v9, v8, (const char *)v7, a5);
  }
  v7 = RegFlushKey(HKEY_LOCAL_MACHINE);
  if ( v7 )
  {
    v9 = 101;
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)v9, v8, (const char *)v7, a5);
  }
  return 0;
}

```

## disassembly

```asm
0x1800176fc  sub     rsp, 28h
0x180017700  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017705  lea     rcx, qword_180026650
0x18001770c  mov     r8, rax
0x18001770f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017714  mov     rdx, rax; lpSubKey
0x180017717  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001771e  call    cs:__imp_RegDeleteKeyValueW
0x180017724  test    eax, eax
0x180017726  jz      short loc_18001773E
0x180017728  mov     edx, 63h ; 'c'; void *
0x18001772d  mov     rcx, [rsp+28h]; this
0x180017732  mov     r9d, eax; char *
0x180017735  add     rsp, 28h
0x180017739  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001773e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017745  call    cs:__imp_RegFlushKey
0x18001774b  test    eax, eax
0x18001774d  jz      short loc_180017756
0x18001774f  mov     edx, 65h ; 'e'
0x180017754  jmp     short loc_18001772D
0x180017756  xor     eax, eax
0x180017758  add     rsp, 28h
0x18001775c  retn
```
