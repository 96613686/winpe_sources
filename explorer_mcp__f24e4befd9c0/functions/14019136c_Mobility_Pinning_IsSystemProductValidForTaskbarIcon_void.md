# Mobility::Pinning::IsSystemProductValidForTaskbarIcon(void)

- ea: `0x14019136c`
- end: `0x14019147f`
- name: `?IsSystemProductValidForTaskbarIcon@Pinning@Mobility@@YA_NXZ`
- size: `275`
- prototype: `bool __fastcall(Mobility::Pinning *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400f8da4`

## callees

- `0x14000fbdc`
- `0x1400aacd8`
- `0x14019136c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140191453`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140191453`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401913b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140191426`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401913b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140191426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401913d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401913d7`

## string_xrefs

- `0x140191388`: `SystemProductName`
- `0x140191408`: `SystemProductName`

## pseudocode

```c
bool __fastcall Mobility::Pinning::IsSystemProductValidForTaskbarIcon(Mobility::Pinning *this)
{
  bool v1; // bl
  LPVOID v2; // rax
  const WCHAR *v3; // rdi
  SIZE_T cb; // [rsp+50h] [rbp+8h] BYREF
  PVOID pvData; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(cb) = 0;
  v1 = 1;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Hardware\\Description\\System\\BIOS",
          L"SystemProductName",
          2u,
          0,
          0,
          (LPDWORD)&cb) )
  {
    pvData = 0;
    v2 = CoTaskMemAlloc((unsigned int)cb);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &pvData,
      v2);
    v3 = (const WCHAR *)pvData;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Hardware\\Description\\System\\BIOS",
            L"SystemProductName",
            2u,
            0,
            pvData,
            (LPDWORD)&cb) )
    {
      pvData = 0;
      v1 = CompareStringOrdinal(v3, -1, L"Surface Go", -1, 1) != 2;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pvData);
  }
  return v1;
}

```

## disassembly

```asm
0x14019136c  mov     r11, rsp
0x14019136f  mov     [r11+18h], rbx
0x140191373  push    rdi
0x140191374  sub     rsp, 40h
0x140191378  lea     rax, [r11+8]
0x14019137c  mov     dword ptr [rsp+48h+cb], 0
0x140191384  mov     [r11-18h], rax
0x140191388  lea     r8, aSystemproductn; "SystemProductName"
0x14019138f  mov     qword ptr [r11-20h], 0
0x140191397  lea     rdx, aHardwareDescri; "Hardware\\Description\\System\\BIOS"
0x14019139e  mov     ebx, 1
0x1401913a3  mov     qword ptr [r11-28h], 0
0x1401913ab  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1401913b2  lea     r9d, [rbx+1]; dwFlags
0x1401913b6  call    cs:__imp_RegGetValueW
0x1401913bd  nop     dword ptr [rax+rax+00h]
0x1401913c2  test    eax, eax
0x1401913c4  jnz     loc_140191471
0x1401913ca  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x1401913ce  mov     [rsp+48h+arg_8], 0
0x1401913d7  call    cs:__imp_CoTaskMemAlloc
0x1401913de  nop     dword ptr [rax+rax+00h]
0x1401913e3  mov     rdx, rax
0x1401913e6  lea     rcx, [rsp+48h+arg_8]
0x1401913eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1401913f0  mov     rdi, [rsp+48h+arg_8]
0x1401913f5  lea     rax, [rsp+48h+cb]
0x1401913fa  mov     [rsp+48h+pcbData], rax; pcbData
0x1401913ff  lea     r9d, [rbx+1]; dwFlags
0x140191403  mov     [rsp+48h+pvData], rdi; pvData
0x140191408  lea     r8, aSystemproductn; "SystemProductName"
0x14019140f  lea     rdx, aHardwareDescri; "Hardware\\Description\\System\\BIOS"
0x140191416  mov     [rsp+48h+pdwType], 0; pdwType
0x14019141f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140191426  call    cs:__imp_RegGetValueW
0x14019142d  nop     dword ptr [rax+rax+00h]
0x140191432  test    eax, eax
0x140191434  jnz     short loc_140191467
0x140191436  or      edx, 0FFFFFFFFh; cchCount1
0x140191439  mov     [rsp+48h+arg_8], 0
0x140191442  mov     r9d, edx; cchCount2
0x140191445  mov     dword ptr [rsp+48h+pdwType], ebx; bIgnoreCase
0x140191449  lea     r8, aSurfaceGo; "Surface Go"
0x140191450  mov     rcx, rdi; lpString1
0x140191453  call    cs:__imp_CompareStringOrdinal
0x14019145a  nop     dword ptr [rax+rax+00h]
0x14019145f  xor     ecx, ecx
0x140191461  cmp     eax, 2
0x140191464  cmovz   ebx, ecx
0x140191467  lea     rcx, [rsp+48h+arg_8]
0x14019146c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140191471  mov     al, bl
0x140191473  mov     rbx, [rsp+48h+arg_10]
0x140191478  add     rsp, 40h
0x14019147c  pop     rdi
0x14019147d  retn
```
