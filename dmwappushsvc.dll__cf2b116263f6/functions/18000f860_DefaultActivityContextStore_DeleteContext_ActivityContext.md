# DefaultActivityContextStore::DeleteContext(ActivityContext &)

- ea: `0x18000f860`
- end: `0x18000f94c`
- name: `?DeleteContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001a70`
- `0x180005aec`
- `0x18000dd1c`
- `0x18000deb0`
- `0x18000e938`
- `0x18000f860`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f8a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f8a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000f921`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000f921`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::DeleteContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  int v2; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  __int64 v5; // [rsp+30h] [rbp-2D8h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-2C8h] BYREF
  unsigned __int16 v7[40]; // [rsp+90h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-228h] BYREF

  v5 = 0;
  SubKey[0] = 0;
  v7[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), sz, 39) == 39 )
  {
    v2 = EEDBTrimGuidBracket(sz, v7);
    if ( v2 >= 0 )
    {
      EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
      v2 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v7, v5);
      if ( v2 >= 0 )
        RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    }
  }
  else
  {
    v2 = -2147418113;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f860  push    rbx
0x18000f862  sub     rsp, 300h
0x18000f869  mov     rax, cs:__security_cookie
0x18000f870  xor     rax, rsp
0x18000f873  mov     [rsp+308h+var_18], rax
0x18000f87b  xor     eax, eax
0x18000f87d  mov     [rsp+308h+var_2D8], 0
0x18000f886  lea     rcx, [rdx+8]; rguid
0x18000f88a  mov     [rsp+308h+SubKey], ax
0x18000f892  lea     rdx, [rsp+308h+sz]; lpsz
0x18000f897  mov     [rsp+308h+var_278], ax
0x18000f89f  mov     [rsp+308h+sz], ax
0x18000f8a4  lea     r8d, [rax+27h]; cchMax
0x18000f8a8  call    cs:__imp_StringFromGUID2
0x18000f8ae  cmp     eax, 27h ; '''
0x18000f8b1  jz      short loc_18000F8BA
0x18000f8b3  mov     ebx, 8000FFFFh
0x18000f8b8  jmp     short loc_18000F927
0x18000f8ba  lea     rdx, [rsp+308h+var_278]; unsigned __int16 *
0x18000f8c2  lea     rcx, [rsp+308h+sz]; unsigned __int16 *
0x18000f8c7  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x18000f8cc  mov     ebx, eax
0x18000f8ce  test    eax, eax
0x18000f8d0  js      short loc_18000F927
0x18000f8d2  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18000f8d7  lea     rcx, [rsp+308h+var_278]
0x18000f8df  mov     r9, rax
0x18000f8e2  mov     [rsp+308h+var_2E0], rcx
0x18000f8e7  lea     r8, aSSS; "%s\\%s\\%s"
0x18000f8ee  lea     rcx, aContext; "Context"
0x18000f8f5  mov     edx, 104h; unsigned __int64
0x18000f8fa  mov     [rsp+308h+var_2E8], rcx
0x18000f8ff  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x18000f907  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f90c  mov     ebx, eax
0x18000f90e  test    eax, eax
0x18000f910  js      short loc_18000F927
0x18000f912  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x18000f91a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f921  call    cs:__imp_RegDeleteTreeW
0x18000f927  lea     rcx, [rsp+308h+var_2D8]
0x18000f92c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f931  mov     eax, ebx
0x18000f933  mov     rcx, [rsp+308h+var_18]
0x18000f93b  xor     rcx, rsp; StackCookie
0x18000f93e  call    __security_check_cookie
0x18000f943  add     rsp, 300h
0x18000f94a  pop     rbx
0x18000f94b  retn
```
