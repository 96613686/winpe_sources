# CLogonTaskFramework::s_SkydrivePrepMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1400b3390`
- end: `0x1400b368c`
- name: `?s_SkydrivePrepMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `764`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400119c8`
- `0x1400158a4`
- `0x14001a3c0`
- `0x14001eba8`
- `0x1400a69d0`
- `0x1400b3390`
- `0x1401040e0`
- `0x140104ce0`
- `0x140106ffc`
- `0x14012f27c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400b344a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400b344a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b3563`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b356e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b3563`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b356e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b3402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b3402`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400b3545`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400b3545`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400b3519`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400b3519`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400b34c3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400b34c3`

## string_xrefs

- `0x1400b345b`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400b35a5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400b361c`: `shell\lib\logontasks\logontasks.cpp`

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
          (void *)0x7F7,
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
        (void *)0x818,
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
        (void *)0x822,
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
0x1400b3390  push    rbp
0x1400b3392  push    rbx
0x1400b3393  push    rsi
0x1400b3394  push    rdi
0x1400b3395  push    r12
0x1400b3397  push    r13
0x1400b3399  push    r14
0x1400b339b  lea     rbp, [rsp-5B0h]
0x1400b33a3  sub     rsp, 6B0h
0x1400b33aa  mov     rax, cs:__security_cookie
0x1400b33b1  xor     rax, rsp
0x1400b33b4  mov     [rbp+5E0h+var_40], rax
0x1400b33bb  mov     eax, [rcx+0D8h]
0x1400b33c1  bt      eax, 9
0x1400b33c5  jb      loc_1400B3669
0x1400b33cb  and     eax, 3
0x1400b33ce  cmp     al, 3
0x1400b33d0  jnz     loc_1400B3669
0x1400b33d6  lea     rax, [rsp+6E0h+hKey]
0x1400b33db  mov     r13, 0FFFFFFFF80000002h
0x1400b33e2  xor     r14d, r14d
0x1400b33e5  mov     [rsp+6E0h+phkResult], rax; phkResult
0x1400b33ea  mov     rcx, r13; hKey
0x1400b33ed  mov     [rsp+6E0h+hKey], r14
0x1400b33f2  mov     r9d, 20019h; samDesired
0x1400b33f8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b33ff  xor     r8d, r8d; ulOptions
0x1400b3402  call    cs:__imp_RegOpenKeyExW
0x1400b3408  lea     r12, [r13-1]
0x1400b340c  test    eax, eax
0x1400b340e  jnz     loc_1400B3574
0x1400b3414  mov     [rsp+6E0h+lpdwDisposition], r14; lpdwDisposition
0x1400b3419  lea     rax, [rsp+6E0h+var_678]
0x1400b341e  mov     [rsp+6E0h+var_6A8], rax; phkResult
0x1400b3423  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b342a  mov     [rsp+6E0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400b342f  xor     r9d, r9d; lpClass
0x1400b3432  mov     [rsp+6E0h+samDesired], 0F003Fh; samDesired
0x1400b343a  xor     r8d, r8d; Reserved
0x1400b343d  mov     rcx, r12; hKey
0x1400b3440  mov     dword ptr [rsp+6E0h+phkResult], r14d; unsigned int
0x1400b3445  mov     [rsp+6E0h+var_678], r14
0x1400b344a  call    cs:__imp_RegCreateKeyExW
0x1400b3450  test    eax, eax
0x1400b3452  jz      short loc_1400B3474
0x1400b3454  mov     rcx, [rbp+5E8h]; this
0x1400b345b  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b3462  mov     r9d, eax; char *
0x1400b3465  mov     edx, 7F7h; void *
0x1400b346a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400b346f  jmp     loc_1400B3569
0x1400b3474  mov     edi, r14d
0x1400b3477  xor     edx, edx; Val
0x1400b3479  lea     rcx, [rsp+6E0h+ValueName]; void *
0x1400b347e  mov     r8d, 208h; Size
0x1400b3484  mov     sil, r14b
0x1400b3487  call    memset_0
0x1400b348c  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1400b3491  lea     rax, [rsp+6E0h+cbData]
0x1400b3496  mov     [rsp+6E0h+var_6A8], rax; lpcbData
0x1400b349b  lea     r9, [rsp+6E0h+cchValueName]; lpcchValueName
0x1400b34a0  mov     [rsp+6E0h+lpSecurityAttributes], r14; lpData
0x1400b34a5  lea     r8, [rsp+6E0h+ValueName]; lpValueName
0x1400b34aa  mov     qword ptr [rsp+6E0h+samDesired], r14; lpType
0x1400b34af  mov     edx, edi; dwIndex
0x1400b34b1  mov     [rsp+6E0h+phkResult], r14; lpReserved
0x1400b34b6  mov     [rsp+6E0h+cchValueName], 104h
0x1400b34be  mov     [rsp+6E0h+cbData], r14d
0x1400b34c3  call    cs:__imp_RegEnumValueW
0x1400b34c9  test    eax, eax
0x1400b34cb  jnz     loc_1400B3553
0x1400b34d1  mov     ecx, [rsp+6E0h+cbData]; unsigned __int64
0x1400b34d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400b34dc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400b34e1  mov     rbx, rax
0x1400b34e4  test    rax, rax
0x1400b34e7  jz      short loc_1400B3553
0x1400b34e9  mov     rcx, [rsp+6E0h+hKey]; hkey
0x1400b34ee  lea     rax, [rsp+6E0h+cbData]
0x1400b34f3  mov     [rsp+6E0h+lpSecurityAttributes], rax; pcbData
0x1400b34f8  lea     r8, [rsp+6E0h+ValueName]; lpValue
0x1400b34fd  lea     rax, [rsp+6E0h+pdwType]
0x1400b3502  mov     qword ptr [rsp+6E0h+samDesired], rbx; pvData
0x1400b3507  mov     r9d, 1000FFFFh; dwFlags
0x1400b350d  mov     [rsp+6E0h+phkResult], rax; pdwType
0x1400b3512  xor     edx, edx; lpSubKey
0x1400b3514  mov     [rsp+6E0h+pdwType], r14d
0x1400b3519  call    cs:__imp_RegGetValueW
0x1400b351f  test    eax, eax
0x1400b3521  jnz     short loc_1400B354B
0x1400b3523  mov     eax, [rsp+6E0h+cbData]
0x1400b3527  lea     rdx, [rsp+6E0h+ValueName]; lpValueName
0x1400b352c  mov     r9d, [rsp+6E0h+pdwType]; dwType
0x1400b3531  xor     r8d, r8d; Reserved
0x1400b3534  mov     rcx, [rsp+6E0h+var_678]; hKey
0x1400b3539  mov     sil, 1
0x1400b353c  mov     [rsp+6E0h+samDesired], eax; cbData
0x1400b3540  mov     [rsp+6E0h+phkResult], rbx; int
0x1400b3545  call    cs:__imp_RegSetValueExW
0x1400b354b  mov     rcx, rbx; lpMem
0x1400b354e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b3553  inc     edi
0x1400b3555  test    sil, sil
0x1400b3558  jnz     loc_1400B3477
0x1400b355e  mov     rcx, [rsp+6E0h+var_678]; hKey
0x1400b3563  call    cs:__imp_RegCloseKey
0x1400b3569  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1400b356e  call    cs:__imp_RegCloseKey
0x1400b3574  mov     r9, cs:off_1401E0158; "AppSync"
0x1400b357b  lea     r8, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b3582  mov     edx, 104h; unsigned __int64
0x1400b3587  lea     rcx, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400b358e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400b3593  lea     rbx, aEnabled; "Enabled"
0x1400b359a  test    eax, eax
0x1400b359c  jns     short loc_1400B35BB
0x1400b359e  mov     rcx, [rbp+5E8h]; this
0x1400b35a5  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b35ac  mov     r9d, eax; char *
0x1400b35af  mov     edx, 818h; void *
0x1400b35b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400b35b9  jmp     short loc_1400B35F2
0x1400b35bb  lea     r9, [rsp+6E0h+pdwType]; unsigned int *
0x1400b35c0  mov     [rsp+6E0h+pdwType], r14d
0x1400b35c5  mov     r8, rbx; unsigned __int16 *
0x1400b35c8  lea     rdx, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400b35cf  mov     rcx, r13; HKEY
0x1400b35d2  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400b35d7  test    eax, eax
0x1400b35d9  js      short loc_1400B35F2
0x1400b35db  mov     r9d, [rsp+6E0h+pdwType]; unsigned int
0x1400b35e0  lea     rdx, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400b35e7  mov     r8, rbx; unsigned __int16 *
0x1400b35ea  mov     rcx, r12; HKEY
0x1400b35ed  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400b35f2  mov     r9, cs:off_1401E0160; "StartLayout"
0x1400b35f9  lea     r8, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400b3600  mov     edx, 104h; unsigned __int64
0x1400b3605  lea     rcx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400b360c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400b3611  test    eax, eax
0x1400b3613  jns     short loc_1400B3632
0x1400b3615  mov     rcx, [rbp+5E8h]; this
0x1400b361c  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b3623  mov     r9d, eax; char *
0x1400b3626  mov     edx, 822h; void *
0x1400b362b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400b3630  jmp     short loc_1400B3669
0x1400b3632  lea     r9, [rsp+6E0h+pdwType]; unsigned int *
0x1400b3637  mov     [rsp+6E0h+pdwType], r14d
0x1400b363c  mov     r8, rbx; unsigned __int16 *
0x1400b363f  lea     rdx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400b3646  mov     rcx, r13; HKEY
0x1400b3649  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400b364e  test    eax, eax
0x1400b3650  js      short loc_1400B3669
0x1400b3652  mov     r9d, [rsp+6E0h+pdwType]; unsigned int
0x1400b3657  lea     rdx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400b365e  mov     r8, rbx; unsigned __int16 *
0x1400b3661  mov     rcx, r12; HKEY
0x1400b3664  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400b3669  xor     eax, eax
0x1400b366b  mov     rcx, [rbp+5E0h+var_40]
0x1400b3672  xor     rcx, rsp; StackCookie
0x1400b3675  call    __security_check_cookie
0x1400b367a  add     rsp, 6B0h
0x1400b3681  pop     r14
0x1400b3683  pop     r13
0x1400b3685  pop     r12
0x1400b3687  pop     rdi
0x1400b3688  pop     rsi
0x1400b3689  pop     rbx
0x1400b368a  pop     rbp
0x1400b368b  retn
```
