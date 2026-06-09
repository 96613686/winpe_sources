# NodeCache::Execute(ActivityContext *)

- ea: `0x18006e640`
- end: `0x18006e788`
- name: `?Execute@NodeCache@@UEAAJPEAVActivityContext@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(NodeCache *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800071c0`
- `0x180016c54`
- `0x180019e8c`
- `0x18001aec8`
- `0x18003d458`
- `0x18006e640`
- `0x18006f7f4`
- `0x180073cac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e6d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e6d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e757`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e757`

## pseudocode

```c
__int64 __fastcall NodeCache::Execute(NodeCache *this, struct ActivityContext *a2)
{
  int EnrollmentString; // ebx
  LSTATUS v4; // eax
  signed int v5; // ebx
  WCHAR *v6; // rcx
  bool v7; // zf
  CEnrollmentLogger *Logger; // rax
  WCHAR *v10; // rcx
  struct _GUID v11; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR *p_lpSubKey; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v13; // [rsp+48h] [rbp-18h] BYREF
  char v14; // [rsp+50h] [rbp-10h]
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF

  lpSubKey = 0;
  p_lpSubKey = &lpSubKey;
  v13 = 0;
  v14 = 1;
  v11 = *(struct _GUID *)((char *)a2 + 8);
  EnrollmentString = EEDBManager::GetEnrollmentString(&v11, L"ProviderID", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&p_lpSubKey);
  if ( EnrollmentString < 0 )
  {
LABEL_7:
    v6 = (WCHAR *)lpSubKey;
    v7 = lpSubKey == 0;
    lpSubKey = 0;
    if ( !v7 )
      MemoryFree(v6);
    return 1;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, qword_1800B07B0, 0, 0x10009u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 == -2147024894 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_7;
  }
  if ( v5 < 0 || (v5 = CleanupRegistry(hKey, lpSubKey), v5 < 0) )
  {
    Logger = CEnrollmentLogger::GetLogger();
    v11 = *(struct _GUID *)((char *)a2 + 8);
    CEnrollmentLogger::LogUnenrollNodeCacheFail(Logger, v5, &v11);
  }
  if ( hKey )
    RegCloseKey(hKey);
  v10 = (WCHAR *)lpSubKey;
  lpSubKey = 0;
  if ( v10 )
    MemoryFree(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006e640  mov     [rsp-8+arg_0], rbx
0x18006e645  mov     [rsp-8+arg_18], rdi
0x18006e64a  push    rbp
0x18006e64b  mov     rbp, rsp
0x18006e64e  sub     rsp, 60h
0x18006e652  mov     rdi, rdx
0x18006e655  mov     [rbp+lpSubKey], 0
0x18006e65d  lea     rax, [rbp+lpSubKey]
0x18006e661  mov     [rbp+var_20], rax
0x18006e665  mov     [rbp+var_18], 0
0x18006e66d  mov     [rbp+var_10], 1
0x18006e671  movups  xmm0, xmmword ptr [rdx+8]
0x18006e675  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x18006e67a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18006e67e  lea     rdx, aProviderid; "ProviderID"
0x18006e685  lea     rcx, [rbp+var_30]; struct _GUID
0x18006e689  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18006e68e  mov     ebx, eax
0x18006e690  lea     rcx, [rbp+var_20]
0x18006e694  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18006e699  test    ebx, ebx
0x18006e69b  js      short loc_18006E6FD
0x18006e69d  mov     [rbp+hKey], 0
0x18006e6a5  xor     edx, edx
0x18006e6a7  lea     rcx, [rbp+hKey]
0x18006e6ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006e6b0  lea     rax, [rbp+hKey]
0x18006e6b4  mov     [rsp+60h+phkResult], rax; phkResult
0x18006e6b9  mov     r9d, 10009h; samDesired
0x18006e6bf  xor     r8d, r8d; ulOptions
0x18006e6c2  mov     rdx, cs:qword_1800B07B0; lpSubKey
0x18006e6c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e6d0  call    cs:__imp_RegOpenKeyExW
0x18006e6d6  mov     ebx, eax
0x18006e6d8  test    eax, eax
0x18006e6da  jle     short loc_18006E6E5
0x18006e6dc  movzx   ebx, ax
0x18006e6df  or      ebx, 80070000h
0x18006e6e5  cmp     ebx, 80070002h
0x18006e6eb  jnz     short loc_18006E71A
0x18006e6ed  mov     rcx, [rbp+hKey]; hKey
0x18006e6f1  test    rcx, rcx
0x18006e6f4  jz      short loc_18006E6FD
0x18006e6f6  call    cs:__imp_RegCloseKey
0x18006e6fc  nop
0x18006e6fd  mov     rcx, [rbp+lpSubKey]; void *
0x18006e701  test    rcx, rcx
0x18006e704  mov     [rbp+lpSubKey], 0
0x18006e70c  jz      short loc_18006E713
0x18006e70e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006e713  mov     eax, 1
0x18006e718  jmp     short loc_18006E776
0x18006e71a  test    ebx, ebx
0x18006e71c  js      short loc_18006E731
0x18006e71e  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18006e722  mov     rcx, [rbp+hKey]; hKey
0x18006e726  call    ?CleanupRegistry@@YAJPEAUHKEY__@@PEBG@Z; CleanupRegistry(HKEY__ *,ushort const *)
0x18006e72b  mov     ebx, eax
0x18006e72d  test    eax, eax
0x18006e72f  jns     short loc_18006E74E
0x18006e731  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006e736  movups  xmm0, xmmword ptr [rdi+8]
0x18006e73a  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x18006e73f  lea     r8, [rbp+var_30]; struct _GUID
0x18006e743  mov     edx, ebx; int
0x18006e745  mov     rcx, rax; this
0x18006e748  call    ?LogUnenrollNodeCacheFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollNodeCacheFail(long,_GUID)
0x18006e74d  nop
0x18006e74e  mov     rcx, [rbp+hKey]; hKey
0x18006e752  test    rcx, rcx
0x18006e755  jz      short loc_18006E75E
0x18006e757  call    cs:__imp_RegCloseKey
0x18006e75d  nop
0x18006e75e  mov     rcx, [rbp+lpSubKey]; void *
0x18006e762  mov     [rbp+lpSubKey], 0
0x18006e76a  test    rcx, rcx
0x18006e76d  jz      short loc_18006E774
0x18006e76f  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006e774  mov     eax, ebx
0x18006e776  lea     r11, [rsp+60h+var_s0]
0x18006e77b  mov     rbx, [r11+10h]
0x18006e77f  mov     rdi, [r11+28h]
0x18006e783  mov     rsp, r11
0x18006e786  pop     rbp
0x18006e787  retn
```
