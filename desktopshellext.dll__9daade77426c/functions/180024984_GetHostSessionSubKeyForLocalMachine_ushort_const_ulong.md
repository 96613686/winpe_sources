# GetHostSessionSubKeyForLocalMachine(ushort const *,ulong)

- ea: `0x180024984`
- end: `0x180024a53`
- name: `?GetHostSessionSubKeyForLocalMachine@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800248e8`

## callees

- `0x18000c444`
- `0x1800108cc`
- `0x1800163c4`
- `0x180024984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024a2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024a2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024a0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024a0b`

## pseudocode

```c
HKEY *__fastcall GetHostSessionSubKeyForLocalMachine(HKEY *a1, __int64 a2, DWORD a3, int a4)
{
  HKEY *phkResult; // rax
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v8; // [rsp+78h] [rbp+18h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+28h] BYREF

  dwDisposition = a3;
  v8 = a2;
  lpSubKey[0] = 0;
  if ( (int)wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short const *,unsigned short [2],unsigned short const *>(
              (unsigned int)lpSubKey,
              a2,
              a3,
              a4,
              (__int64)&v8) < 0 )
  {
LABEL_6:
    *a1 = 0;
    goto LABEL_7;
  }
  hKey = 0;
  dwDisposition = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0, 1u, 0x20019u, 0, phkResult, &dwDisposition) < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_6;
  }
  *a1 = hKey;
  hKey = 0;
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x180024984  mov     r11, rsp
0x180024987  mov     [r11+8], rbx
0x18002498b  mov     [r11+18h], r8d
0x18002498f  mov     [r11+10h], rdx
0x180024993  push    rbp
0x180024994  mov     rbp, rsp
0x180024997  sub     rsp, 60h
0x18002499b  mov     rbx, rcx
0x18002499e  mov     [rbp+lpSubKey], 0
0x1800249a6  lea     rax, [rbp+arg_8]
0x1800249aa  lea     rcx, [rbp+lpSubKey]
0x1800249ae  mov     [r11-48h], rax
0x1800249b2  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEBG$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEBG1AEAY01$$CBG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort const *,ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * const &,ushort const * const &,ushort const (&)[2],ushort const * const &)
0x1800249b7  test    eax, eax
0x1800249b9  js      short loc_180024A35
0x1800249bb  lea     rcx, [rbp+hKey]
0x1800249bf  mov     [rbp+hKey], 0
0x1800249c7  mov     [rbp+dwDisposition], 0
0x1800249ce  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800249d3  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800249d7  lea     rcx, [rbp+dwDisposition]
0x1800249db  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x1800249e0  xor     r9d, r9d; lpClass
0x1800249e3  mov     [rsp+60h+phkResult], rax; phkResult
0x1800249e8  xor     r8d, r8d; Reserved
0x1800249eb  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800249f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800249fb  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180024a03  mov     [rsp+60h+dwOptions], 1; dwOptions
0x180024a0b  call    cs:__imp_RegCreateKeyExW
0x180024a11  test    eax, eax
0x180024a13  js      short loc_180024A26
0x180024a15  mov     rax, [rbp+hKey]
0x180024a19  mov     [rbx], rax
0x180024a1c  mov     [rbp+hKey], 0
0x180024a24  jmp     short loc_180024A3C
0x180024a26  mov     rcx, [rbp+hKey]; hKey
0x180024a2a  test    rcx, rcx
0x180024a2d  jz      short loc_180024A35
0x180024a2f  call    cs:__imp_RegCloseKey
0x180024a35  mov     qword ptr [rbx], 0
0x180024a3c  lea     rcx, [rbp+lpSubKey]
0x180024a40  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024a45  mov     rax, rbx
0x180024a48  mov     rbx, [rsp+60h+arg_0]
0x180024a4d  add     rsp, 60h
0x180024a51  pop     rbp
0x180024a52  retn
```
