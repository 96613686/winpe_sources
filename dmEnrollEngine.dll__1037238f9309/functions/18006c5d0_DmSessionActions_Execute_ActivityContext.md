# DmSessionActions::Execute(ActivityContext *)

- ea: `0x18006c5d0`
- end: `0x18006c718`
- name: `?Execute@DmSessionActions@@UEAAJPEAVActivityContext@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(DmSessionActions *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800071c0`
- `0x180016c54`
- `0x180019e8c`
- `0x18001aec8`
- `0x18003d458`
- `0x18006c5d0`
- `0x18006f7f4`
- `0x180073678`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c660`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c660`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c6e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c6e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DmSessionActions::Execute(DmSessionActions *this, struct ActivityContext *a2)
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
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, qword_1800B07A8, 0, 0x10009u, &hKey);
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
    CEnrollmentLogger::LogUnenrollDmSessionActionsFail(Logger, v5, &v11);
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
0x18006c5d0  mov     [rsp-8+arg_0], rbx
0x18006c5d5  mov     [rsp-8+arg_18], rdi
0x18006c5da  push    rbp
0x18006c5db  mov     rbp, rsp
0x18006c5de  sub     rsp, 60h
0x18006c5e2  mov     rdi, rdx
0x18006c5e5  mov     [rbp+lpSubKey], 0
0x18006c5ed  lea     rax, [rbp+lpSubKey]
0x18006c5f1  mov     [rbp+var_20], rax
0x18006c5f5  mov     [rbp+var_18], 0
0x18006c5fd  mov     [rbp+var_10], 1
0x18006c601  movups  xmm0, xmmword ptr [rdx+8]
0x18006c605  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x18006c60a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18006c60e  lea     rdx, aProviderid; "ProviderID"
0x18006c615  lea     rcx, [rbp+var_30]; struct _GUID
0x18006c619  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18006c61e  mov     ebx, eax
0x18006c620  lea     rcx, [rbp+var_20]
0x18006c624  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18006c629  test    ebx, ebx
0x18006c62b  js      short loc_18006C68D
0x18006c62d  mov     [rbp+hKey], 0
0x18006c635  xor     edx, edx
0x18006c637  lea     rcx, [rbp+hKey]
0x18006c63b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006c640  lea     rax, [rbp+hKey]
0x18006c644  mov     [rsp+60h+phkResult], rax; phkResult
0x18006c649  mov     r9d, 10009h; samDesired
0x18006c64f  xor     r8d, r8d; ulOptions
0x18006c652  mov     rdx, cs:qword_1800B07A8; lpSubKey
0x18006c659  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c660  call    cs:__imp_RegOpenKeyExW
0x18006c666  mov     ebx, eax
0x18006c668  test    eax, eax
0x18006c66a  jle     short loc_18006C675
0x18006c66c  movzx   ebx, ax
0x18006c66f  or      ebx, 80070000h
0x18006c675  cmp     ebx, 80070002h
0x18006c67b  jnz     short loc_18006C6AA
0x18006c67d  mov     rcx, [rbp+hKey]; hKey
0x18006c681  test    rcx, rcx
0x18006c684  jz      short loc_18006C68D
0x18006c686  call    cs:__imp_RegCloseKey
0x18006c68c  nop
0x18006c68d  mov     rcx, [rbp+lpSubKey]; void *
0x18006c691  test    rcx, rcx
0x18006c694  mov     [rbp+lpSubKey], 0
0x18006c69c  jz      short loc_18006C6A3
0x18006c69e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006c6a3  mov     eax, 1
0x18006c6a8  jmp     short loc_18006C706
0x18006c6aa  test    ebx, ebx
0x18006c6ac  js      short loc_18006C6C1
0x18006c6ae  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18006c6b2  mov     rcx, [rbp+hKey]; hKey
0x18006c6b6  call    ?CleanupRegistry@@YAJPEAUHKEY__@@PEBG@Z; CleanupRegistry(HKEY__ *,ushort const *)
0x18006c6bb  mov     ebx, eax
0x18006c6bd  test    eax, eax
0x18006c6bf  jns     short loc_18006C6DE
0x18006c6c1  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006c6c6  movups  xmm0, xmmword ptr [rdi+8]
0x18006c6ca  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x18006c6cf  lea     r8, [rbp+var_30]; struct _GUID
0x18006c6d3  mov     edx, ebx; int
0x18006c6d5  mov     rcx, rax; this
0x18006c6d8  call    ?LogUnenrollDmSessionActionsFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollDmSessionActionsFail(long,_GUID)
0x18006c6dd  nop
0x18006c6de  mov     rcx, [rbp+hKey]; hKey
0x18006c6e2  test    rcx, rcx
0x18006c6e5  jz      short loc_18006C6EE
0x18006c6e7  call    cs:__imp_RegCloseKey
0x18006c6ed  nop
0x18006c6ee  mov     rcx, [rbp+lpSubKey]; void *
0x18006c6f2  mov     [rbp+lpSubKey], 0
0x18006c6fa  test    rcx, rcx
0x18006c6fd  jz      short loc_18006C704
0x18006c6ff  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006c704  mov     eax, ebx
0x18006c706  lea     r11, [rsp+60h+var_s0]
0x18006c70b  mov     rbx, [r11+10h]
0x18006c70f  mov     rdi, [r11+28h]
0x18006c713  mov     rsp, r11
0x18006c716  pop     rbp
0x18006c717  retn
```
