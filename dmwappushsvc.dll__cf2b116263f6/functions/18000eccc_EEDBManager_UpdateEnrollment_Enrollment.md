# EEDBManager::UpdateEnrollment(Enrollment *)

- ea: `0x18000eccc`
- end: `0x18000ee0c`
- name: `?UpdateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct Enrollment *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010bd0`

## callees

- `0x180001a70`
- `0x18000dd1c`
- `0x18000deb0`
- `0x18000e994`
- `0x18000eccc`
- `0x18000eecc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ed21`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ed21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000edc7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000edc7`

## pseudocode

```c
__int64 __fastcall EEDBManager::UpdateEnrollment(EEDBManager *this, struct Enrollment *a2)
{
  int v3; // ebx
  LSTATUS v4; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-71h] BYREF
  HKEY v8; // [rsp+40h] [rbp-69h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-59h] BYREF
  wchar_t String1[40]; // [rsp+A0h] [rbp-9h] BYREF

  *(_DWORD *)Data = 63;
  hKey = 0;
  v8 = 0;
  String1[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 28), sz, 39) == 39 )
  {
    v3 = EEDBTrimGuidBracket(sz, String1);
    if ( v3 >= 0 )
    {
      v3 = EEDBManager::OpenEnrollmentHKEY(HKEY_LOCAL_MACHINE, String1, 131078, &v8, 0, 0);
      if ( v3 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          v8);
        v3 = (*(__int64 (__fastcall **)(struct Enrollment *, BYTE *))(*(_QWORD *)a2 + 56LL))(a2, Data);
        if ( v3 >= 0 )
        {
          v4 = RegSetValueExW(hKey, L"EnrollmentState", 0, 4u, Data, 4u);
          if ( v4 )
          {
            if ( v4 > 0 )
              v3 = (unsigned __int16)v4 | 0x80070000;
            else
              v3 = v4;
          }
        }
      }
    }
  }
  else
  {
    v3 = -2147418113;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000eccc  mov     [rsp-8+arg_0], rbx
0x18000ecd1  mov     [rsp-8+arg_10], rdi
0x18000ecd6  push    rbp
0x18000ecd7  lea     rbp, [rsp-57h]
0x18000ecdc  sub     rsp, 100h
0x18000ece3  mov     rax, cs:__security_cookie
0x18000ecea  xor     rax, rsp
0x18000eced  mov     [rbp+57h+var_10], rax
0x18000ecf1  mov     rdi, rdx
0x18000ecf4  mov     dword ptr [rbp+57h+Data], 3Fh ; '?'
0x18000ecfb  mov     [rbp+57h+hKey], 0
0x18000ed03  mov     [rbp+57h+var_C0], 0
0x18000ed0b  xor     eax, eax
0x18000ed0d  mov     [rbp+57h+String1], ax
0x18000ed11  mov     [rbp+57h+sz], ax
0x18000ed15  lea     rcx, [rdx+1Ch]; rguid
0x18000ed19  lea     r8d, [rax+27h]; cchMax
0x18000ed1d  lea     rdx, [rbp+57h+sz]; lpsz
0x18000ed21  call    cs:__imp_StringFromGUID2
0x18000ed27  cmp     eax, 27h ; '''
0x18000ed2a  jz      short loc_18000ED36
0x18000ed2c  mov     ebx, 8000FFFFh
0x18000ed31  jmp     loc_18000EDE0
0x18000ed36  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x18000ed3a  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x18000ed3e  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x18000ed43  mov     ebx, eax
0x18000ed45  test    eax, eax
0x18000ed47  js      loc_18000EDE0
0x18000ed4d  mov     qword ptr [rsp+100h+cbData], 0; unsigned __int64
0x18000ed56  mov     [rsp+100h+lpData], 0; unsigned __int16 *
0x18000ed5f  lea     r9, [rbp+57h+var_C0]; HKEY *
0x18000ed63  mov     r8d, 20006h; unsigned int
0x18000ed69  lea     rdx, [rbp+57h+String1]; String1
0x18000ed6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ed74  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x18000ed79  mov     ebx, eax
0x18000ed7b  test    eax, eax
0x18000ed7d  js      short loc_18000EDE0
0x18000ed7f  mov     rdx, [rbp+57h+var_C0]
0x18000ed83  lea     rcx, [rbp+57h+hKey]
0x18000ed87  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ed8c  mov     rax, [rdi]
0x18000ed8f  lea     rdx, [rbp+57h+Data]
0x18000ed93  mov     rcx, rdi
0x18000ed96  mov     rax, [rax+38h]
0x18000ed9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed9f  mov     ebx, eax
0x18000eda1  test    eax, eax
0x18000eda3  js      short loc_18000EDE0
0x18000eda5  mov     r9d, 4; dwType
0x18000edab  mov     [rsp+100h+cbData], r9d; cbData
0x18000edb0  lea     rax, [rbp+57h+Data]
0x18000edb4  mov     [rsp+100h+lpData], rax; lpData
0x18000edb9  xor     r8d, r8d; Reserved
0x18000edbc  lea     rdx, ValueName; "EnrollmentState"
0x18000edc3  mov     rcx, [rbp+57h+hKey]; hKey
0x18000edc7  call    cs:__imp_RegSetValueExW
0x18000edcd  test    eax, eax
0x18000edcf  jz      short loc_18000EDE0
0x18000edd1  jg      short loc_18000EDD7
0x18000edd3  mov     ebx, eax
0x18000edd5  jmp     short loc_18000EDE0
0x18000edd7  movzx   ebx, ax
0x18000edda  or      ebx, 80070000h
0x18000ede0  lea     rcx, [rbp+57h+hKey]
0x18000ede4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ede9  mov     eax, ebx
0x18000edeb  mov     rcx, [rbp+57h+var_10]
0x18000edef  xor     rcx, rsp; StackCookie
0x18000edf2  call    __security_check_cookie
0x18000edf7  lea     r11, [rsp+100h+var_s0]
0x18000edff  mov     rbx, [r11+10h]
0x18000ee03  mov     rdi, [r11+20h]
0x18000ee07  mov     rsp, r11
0x18000ee0a  pop     rbp
0x18000ee0b  retn
```
