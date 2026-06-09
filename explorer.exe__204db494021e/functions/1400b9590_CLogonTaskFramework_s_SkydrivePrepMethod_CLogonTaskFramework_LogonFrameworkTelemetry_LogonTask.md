# CLogonTaskFramework::s_SkydrivePrepMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1400b9590`
- end: `0x1400b98b7`
- name: `?s_SkydrivePrepMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x14001b2c8`
- `0x140020580`
- `0x140027550`
- `0x14004856c`
- `0x1400acaec`
- `0x1400b9590`
- `0x14010e160`
- `0x14010ed90`
- `0x14011106c`
- `0x14013af98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400b975d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400b975d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400b9650`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400b9650`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400b96cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400b96cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b9602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b9602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b9781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b9792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b9781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b9792`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400b972b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400b972b`

## string_xrefs

- `0x1400b9667`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400b97cf`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400b9846`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
__int64 __fastcall CLogonTaskFramework::s_SkydrivePrepMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  int v2; // eax
  unsigned int v3; // eax
  DWORD v4; // edi
  char v5; // si
  BYTE *v6; // rbx
  int v7; // eax
  int v8; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD pdwType; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v16; // [rsp+68h] [rbp-98h] BYREF
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v19[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v2 = *((_DWORD *)a1 + 54);
  if ( (v2 & 0x200) == 0 && (v2 & 3) == 3 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\OneDriveOptIn",
            0,
            0x20019u,
            &hKey) )
    {
      v16 = 0;
      v3 = RegCreateKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\OneDriveOptIn",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &v16,
             0);
      if ( v3 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x7FB,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)v3,
          phkResulta);
      }
      else
      {
        v4 = 0;
        do
        {
          v5 = 0;
          memset_0(ValueName, 0, 0x208u);
          cchValueName = 260;
          cbData = 0;
          if ( !RegEnumValueW(hKey, v4, ValueName, &cchValueName, 0, 0, 0, &cbData) )
          {
            v6 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
            if ( v6 )
            {
              pdwType = 0;
              if ( !RegGetValueW(hKey, 0, ValueName, 0x1000FFFFu, &pdwType, v6, &cbData) )
              {
                v5 = 1;
                RegSetValueExW(v16, ValueName, 0, pdwType, v6, cbData);
              }
              operator delete(v6);
            }
          }
          ++v4;
        }
        while ( v5 );
        RegCloseKey(v16);
      }
      RegCloseKey(hKey);
    }
    v7 = StringCchPrintfW(
           v18,
           0x104u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\SettingSync\\Groups\\%s",
           L"AppSync");
    if ( v7 >= 0 )
    {
      pdwType = 0;
      if ( (int)SHRegGetDWORD(HKEY_LOCAL_MACHINE, v18, L"Enabled", &pdwType) >= 0 )
        SHRegSetDWORD(HKEY_CURRENT_USER, v18, L"Enabled", pdwType);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81C,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v7,
        phkResult);
    }
    v8 = StringCchPrintfW(
           v19,
           0x104u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\SettingSync\\Groups\\%s",
           L"StartLayout");
    if ( v8 >= 0 )
    {
      pdwType = 0;
      if ( (int)SHRegGetDWORD(HKEY_LOCAL_MACHINE, v19, L"Enabled", &pdwType) >= 0 )
        SHRegSetDWORD(HKEY_CURRENT_USER, v19, L"Enabled", pdwType);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x826,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v8,
        phkResult);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400b9590  push    rbp
0x1400b9592  push    rbx
0x1400b9593  push    rsi
0x1400b9594  push    rdi
0x1400b9595  push    r12
0x1400b9597  push    r13
0x1400b9599  push    r14
0x1400b959b  lea     rbp, [rsp-5B0h]
0x1400b95a3  sub     rsp, 6B0h
0x1400b95aa  mov     rax, cs:__security_cookie
0x1400b95b1  xor     rax, rsp
0x1400b95b4  mov     [rbp+5E0h+var_40], rax
0x1400b95bb  mov     eax, [rcx+0D8h]
0x1400b95c1  bt      eax, 9
0x1400b95c5  jb      loc_1400B9893
0x1400b95cb  and     eax, 3
0x1400b95ce  cmp     al, 3
0x1400b95d0  jnz     loc_1400B9893
0x1400b95d6  lea     rax, [rsp+6E0h+hKey]
0x1400b95db  mov     r13, 0FFFFFFFF80000002h
0x1400b95e2  xor     r14d, r14d
0x1400b95e5  mov     [rsp+6E0h+phkResult], rax; phkResult
0x1400b95ea  mov     rcx, r13; hKey
0x1400b95ed  mov     [rsp+6E0h+hKey], r14
0x1400b95f2  mov     r9d, 20019h; samDesired
0x1400b95f8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b95ff  xor     r8d, r8d; ulOptions
0x1400b9602  call    cs:__imp_RegOpenKeyExW
0x1400b9609  nop     dword ptr [rax+rax+00h]
0x1400b960e  lea     r12, [r13-1]
0x1400b9612  test    eax, eax
0x1400b9614  jnz     loc_1400B979E
0x1400b961a  mov     [rsp+6E0h+lpdwDisposition], r14; lpdwDisposition
0x1400b961f  lea     rax, [rsp+6E0h+var_678]
0x1400b9624  mov     [rsp+6E0h+var_6A8], rax; phkResult
0x1400b9629  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b9630  mov     [rsp+6E0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400b9635  xor     r9d, r9d; lpClass
0x1400b9638  mov     [rsp+6E0h+samDesired], 0F003Fh; samDesired
0x1400b9640  xor     r8d, r8d; Reserved
0x1400b9643  mov     rcx, r12; hKey
0x1400b9646  mov     dword ptr [rsp+6E0h+phkResult], r14d; unsigned int
0x1400b964b  mov     [rsp+6E0h+var_678], r14
0x1400b9650  call    cs:__imp_RegCreateKeyExW
0x1400b9657  nop     dword ptr [rax+rax+00h]
0x1400b965c  test    eax, eax
0x1400b965e  jz      short loc_1400B9680
0x1400b9660  mov     rcx, [rbp+5E8h]; this
0x1400b9667  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b966e  mov     r9d, eax; char *
0x1400b9671  mov     edx, 7FBh; void *
0x1400b9676  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400b967b  jmp     loc_1400B978D
0x1400b9680  mov     edi, r14d
0x1400b9683  xor     edx, edx; Val
0x1400b9685  lea     rcx, [rsp+6E0h+ValueName]; void *
0x1400b968a  mov     r8d, 208h; Size
0x1400b9690  mov     sil, r14b
0x1400b9693  call    memset_0
0x1400b9698  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1400b969d  lea     rax, [rsp+6E0h+cbData]
0x1400b96a2  mov     [rsp+6E0h+var_6A8], rax; lpcbData
0x1400b96a7  lea     r9, [rsp+6E0h+cchValueName]; lpcchValueName
0x1400b96ac  mov     [rsp+6E0h+lpSecurityAttributes], r14; lpData
0x1400b96b1  lea     r8, [rsp+6E0h+ValueName]; lpValueName
0x1400b96b6  mov     qword ptr [rsp+6E0h+samDesired], r14; lpType
0x1400b96bb  mov     edx, edi; dwIndex
0x1400b96bd  mov     [rsp+6E0h+phkResult], r14; lpReserved
0x1400b96c2  mov     [rsp+6E0h+cchValueName], 104h
0x1400b96ca  mov     [rsp+6E0h+cbData], r14d
0x1400b96cf  call    cs:__imp_RegEnumValueW
0x1400b96d6  nop     dword ptr [rax+rax+00h]
0x1400b96db  test    eax, eax
0x1400b96dd  jnz     loc_1400B9771
0x1400b96e3  mov     ecx, [rsp+6E0h+cbData]; unsigned __int64
0x1400b96e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400b96ee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400b96f3  mov     rbx, rax
0x1400b96f6  test    rax, rax
0x1400b96f9  jz      short loc_1400B9771
0x1400b96fb  mov     rcx, [rsp+6E0h+hKey]; hkey
0x1400b9700  lea     rax, [rsp+6E0h+cbData]
0x1400b9705  mov     [rsp+6E0h+lpSecurityAttributes], rax; pcbData
0x1400b970a  lea     r8, [rsp+6E0h+ValueName]; lpValue
0x1400b970f  lea     rax, [rsp+6E0h+pdwType]
0x1400b9714  mov     qword ptr [rsp+6E0h+samDesired], rbx; pvData
0x1400b9719  mov     r9d, 1000FFFFh; dwFlags
0x1400b971f  mov     [rsp+6E0h+phkResult], rax; pdwType
0x1400b9724  xor     edx, edx; lpSubKey
0x1400b9726  mov     [rsp+6E0h+pdwType], r14d
0x1400b972b  call    cs:__imp_RegGetValueW
0x1400b9732  nop     dword ptr [rax+rax+00h]
0x1400b9737  test    eax, eax
0x1400b9739  jnz     short loc_1400B9769
0x1400b973b  mov     eax, [rsp+6E0h+cbData]
0x1400b973f  lea     rdx, [rsp+6E0h+ValueName]; lpValueName
0x1400b9744  mov     r9d, [rsp+6E0h+pdwType]; dwType
0x1400b9749  xor     r8d, r8d; Reserved
0x1400b974c  mov     rcx, [rsp+6E0h+var_678]; hKey
0x1400b9751  mov     sil, 1
0x1400b9754  mov     [rsp+6E0h+samDesired], eax; cbData
0x1400b9758  mov     [rsp+6E0h+phkResult], rbx; int
0x1400b975d  call    cs:__imp_RegSetValueExW
0x1400b9764  nop     dword ptr [rax+rax+00h]
0x1400b9769  mov     rcx, rbx; lpMem
0x1400b976c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b9771  inc     edi
0x1400b9773  test    sil, sil
0x1400b9776  jnz     loc_1400B9683
0x1400b977c  mov     rcx, [rsp+6E0h+var_678]; hKey
0x1400b9781  call    cs:__imp_RegCloseKey
0x1400b9788  nop     dword ptr [rax+rax+00h]
0x1400b978d  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1400b9792  call    cs:__imp_RegCloseKey
0x1400b9799  nop     dword ptr [rax+rax+00h]
0x1400b979e  mov     r9, cs:off_1401DE188; "AppSync"
0x1400b97a5  lea     r8, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b97ac  mov     edx, 104h; unsigned __int64
0x1400b97b1  lea     rcx, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400b97b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400b97bd  lea     rbx, aEnabled; "Enabled"
0x1400b97c4  test    eax, eax
0x1400b97c6  jns     short loc_1400B97E5
0x1400b97c8  mov     rcx, [rbp+5E8h]; this
0x1400b97cf  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b97d6  mov     r9d, eax; char *
0x1400b97d9  mov     edx, 81Ch; void *
0x1400b97de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400b97e3  jmp     short loc_1400B981C
0x1400b97e5  lea     r9, [rsp+6E0h+pdwType]; unsigned int *
0x1400b97ea  mov     [rsp+6E0h+pdwType], r14d
0x1400b97ef  mov     r8, rbx; unsigned __int16 *
0x1400b97f2  lea     rdx, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400b97f9  mov     rcx, r13; HKEY
0x1400b97fc  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400b9801  test    eax, eax
0x1400b9803  js      short loc_1400B981C
0x1400b9805  mov     r9d, [rsp+6E0h+pdwType]; unsigned int
0x1400b980a  lea     rdx, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400b9811  mov     r8, rbx; unsigned __int16 *
0x1400b9814  mov     rcx, r12; HKEY
0x1400b9817  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400b981c  mov     r9, cs:off_1401DE190; "StartLayout"
0x1400b9823  lea     r8, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b982a  mov     edx, 104h; unsigned __int64
0x1400b982f  lea     rcx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400b9836  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400b983b  test    eax, eax
0x1400b983d  jns     short loc_1400B985C
0x1400b983f  mov     rcx, [rbp+5E8h]; this
0x1400b9846  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b984d  mov     r9d, eax; char *
0x1400b9850  mov     edx, 826h; void *
0x1400b9855  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400b985a  jmp     short loc_1400B9893
0x1400b985c  lea     r9, [rsp+6E0h+pdwType]; unsigned int *
0x1400b9861  mov     [rsp+6E0h+pdwType], r14d
0x1400b9866  mov     r8, rbx; unsigned __int16 *
0x1400b9869  lea     rdx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400b9870  mov     rcx, r13; HKEY
0x1400b9873  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400b9878  test    eax, eax
0x1400b987a  js      short loc_1400B9893
0x1400b987c  mov     r9d, [rsp+6E0h+pdwType]; unsigned int
0x1400b9881  lea     rdx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400b9888  mov     r8, rbx; unsigned __int16 *
0x1400b988b  mov     rcx, r12; HKEY
0x1400b988e  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400b9893  xor     eax, eax
0x1400b9895  mov     rcx, [rbp+5E0h+var_40]
0x1400b989c  xor     rcx, rsp; StackCookie
0x1400b989f  call    __security_check_cookie
0x1400b98a4  add     rsp, 6B0h
0x1400b98ab  pop     r14
0x1400b98ad  pop     r13
0x1400b98af  pop     r12
0x1400b98b1  pop     rdi
0x1400b98b2  pop     rsi
0x1400b98b3  pop     rbx
0x1400b98b4  pop     rbp
0x1400b98b5  retn
```
