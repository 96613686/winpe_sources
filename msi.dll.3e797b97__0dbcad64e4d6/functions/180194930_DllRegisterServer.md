# DllRegisterServer

- ea: `0x180194930`
- end: `0x180194d48`
- name: `DllRegisterServer`
- size: `1048`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180010ac0`
- `0x1800200a4`
- `0x18004cb88`
- `0x18018ae70`
- `0x18018ae9c`
- `0x180194930`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180194a4f`
- `ADVAPI32!RegCloseKey` at `0x180194c86`
- `ADVAPI32!RegCloseKey` at `0x180194a4f`
- `ADVAPI32!RegCloseKey` at `0x180194c86`
- `ADVAPI32!RegSetValueExW` at `0x180194a10`
- `ADVAPI32!RegSetValueExW` at `0x180194a3e`
- `ADVAPI32!RegSetValueExW` at `0x180194c0b`
- `ADVAPI32!RegSetValueExW` at `0x180194c61`
- `ADVAPI32!RegSetValueExW` at `0x180194a10`
- `ADVAPI32!RegSetValueExW` at `0x180194a3e`
- `ADVAPI32!RegSetValueExW` at `0x180194c0b`
- `ADVAPI32!RegSetValueExW` at `0x180194c61`
- `KERNEL32!GetModuleFileNameW` at `0x180194977`
- `KERNEL32!GetModuleFileNameW` at `0x180194977`
- `KERNEL32!lstrlenW` at `0x1801949e1`
- `KERNEL32!lstrlenW` at `0x180194bde`
- `KERNEL32!lstrlenW` at `0x180194c32`
- `KERNEL32!lstrlenW` at `0x1801949e1`
- `KERNEL32!lstrlenW` at `0x180194bde`
- `KERNEL32!lstrlenW` at `0x180194c32`
- `RPCRT4!NdrDllRegisterProxy` at `0x180194a70`
- `RPCRT4!NdrDllRegisterProxy` at `0x180194a70`

## string_xrefs

- `0x1801949cf`: `%SystemRoot%\system32\msimsg.dll`
- `0x1801949a7`: `System\CurrentControlSet\Services\EventLog\Application\MsiInstaller`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  signed int ModuleFileNameW; // eax
  unsigned int v1; // r8d
  unsigned __int16 *v2; // r9
  int v3; // eax
  __int64 v4; // rbx
  wchar_t **v5; // rdi
  int v6; // eax
  HKEY v7; // rcx
  int v8; // eax
  LSTATUS v9; // eax
  int v11; // eax
  int v12; // ebx
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+30h] [rbp-D0h]
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 v21[80]; // [rsp+80h] [rbp-80h] BYREF

  word_1803121C6 = 0;
  v20 = 0;
  ModuleFileNameW = GetModuleFileNameW(g_hInstance, &Filename, 0x104u);
  if ( word_1803121C6 )
    return -2147467259;
  if ( ModuleFileNameW > 0 )
  {
    hKey = 0;
    if ( !MsiRegCreate64bitKey(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\EventLog\\Application\\MsiInstaller",
            v1,
            v2,
            (unsigned int)lpData,
            0x2001Fu,
            v15,
            &hKey,
            0) )
    {
      *(_DWORD *)Data = 7;
      v3 = lstrlenW(L"%SystemRoot%\\system32\\msimsg.dll");
      RegSetValueExW(hKey, L"EventMessageFile", 0, 2u, (const BYTE *)L"%SystemRoot%\\system32\\msimsg.dll", 2 * v3 + 2);
      RegSetValueExW(hKey, L"TypesSupported", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
    }
  }
  v4 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer) != 0;
  if ( (int)StringCchPrintfW(&qword_180311F70, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790672) < 0 )
    return -2147467259;
  if ( (int)StringCchPrintfW(&qword_180311F20, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790557) < 0 )
    return -2147467259;
  v19 = 20;
  DllGetVersion(&v19);
  LODWORD(cbData) = DWORD2(v20);
  LODWORD(lpData) = DWORD1(v20);
  if ( (int)StringCchPrintfW(&qword_180311E00, 0x64u, L"%d.%d.%d", (unsigned int)v20, lpData, cbData) < 0
    || (int)StringCchPrintfW(&qword_180311DB0, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790676) < 0
    || (int)StringCchPrintfW(&qword_180311ED0, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790674) < 0 )
  {
    return -2147467259;
  }
  v5 = &off_180273E00;
  while ( *v5 )
  {
    if ( v5[1] && v5[2] )
    {
      if ( (int)StringCchPrintfW(v21, 0x50u, *v5) < 0 )
        return -2147467259;
      *(_QWORD *)Data = 0;
      if ( (unsigned int)((__int64 (__fastcall *)(unsigned __int64, unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, BYTE *, _QWORD))RegCreateKeyAPI)(
                           0xFFFFFFFF80000000uLL,
                           v21,
                           0,
                           0,
                           0,
                           131103,
                           0,
                           Data,
                           0)
        || (v6 = lstrlenW(v5[2]), RegSetValueExW(*(HKEY *)Data, 0, 0, 1u, (const BYTE *)v5[2], 2 * v6 + 2)) )
      {
        LODWORD(v4) = v4 + 1;
      }
      v7 = *(HKEY *)Data;
      if ( *(_QWORD *)Data )
      {
        if ( v5[3] )
        {
          v8 = lstrlenW(v5[4]);
          v9 = RegSetValueExW(*(HKEY *)Data, v5[3], 0, 1u, (const BYTE *)v5[4], 2 * v8 + 2);
          v7 = *(HKEY *)Data;
          if ( v9 )
            LODWORD(v4) = v4 + 1;
        }
      }
      v5 += 5;
      if ( v7 )
        RegCloseKey(v7);
    }
  }
  if ( GetTestFlag(114) && (unsigned int)DllRegisterServerTest() )
    LODWORD(v4) = v4 + 1;
  if ( (_DWORD)v4 )
    return -2147220991;
  v18 = 0;
  v11 = ((__int64 (__fastcall *)(WCHAR *, __int64 *))OLEAUT32::LoadTypeLib)(&Filename, &v18);
  if ( v11 == -2147319784 )
    return 0;
  if ( v11 )
    return -2147220992;
  v12 = ((__int64 (__fastcall *)(__int64, WCHAR *, _QWORD))OLEAUT32::RegisterTypeLib)(v18, &Filename, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return v12 != 0 ? 0x80040200 : 0;
}

```

## disassembly

```asm
0x180194930  push    rbp
0x180194932  push    rbx
0x180194933  push    rsi
0x180194934  push    rdi
0x180194935  push    r14
0x180194937  lea     rbp, [rsp-30h]
0x18019493c  sub     rsp, 130h
0x180194943  mov     rax, cs:__security_cookie
0x18019494a  xor     rax, rsp
0x18019494d  mov     [rbp+50h+var_30], rax
0x180194951  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180194958  lea     rdx, Filename; lpFilename
0x18019495f  xorps   xmm0, xmm0
0x180194962  xor     esi, esi
0x180194964  mov     r8d, 104h; nSize
0x18019496a  mov     cs:word_1803121C6, si
0x180194971  movdqu  [rsp+150h+var_E4], xmm0
0x180194977  call    cs:__imp_GetModuleFileNameW
0x18019497e  nop     dword ptr [rax+rax+00h]
0x180194983  cmp     cs:word_1803121C6, si
0x18019498a  jnz     loc_180194D28
0x180194990  test    eax, eax
0x180194992  jle     loc_180194A5B
0x180194998  lea     rax, [rsp+150h+hKey]
0x18019499d  mov     [rsp+150h+var_110], rsi; unsigned int *
0x1801949a2  mov     [rsp+150h+var_118], rax; HKEY *
0x1801949a7  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ev"...
0x1801949ae  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1801949b5  mov     dword ptr [rsp+150h+cbData], 2001Fh; unsigned int
0x1801949bd  mov     [rsp+150h+hKey], rsi
0x1801949c2  call    ?MsiRegCreate64bitKey@@YAKPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; MsiRegCreate64bitKey(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1801949c7  test    eax, eax
0x1801949c9  jnz     loc_180194A5B
0x1801949cf  lea     rbx, Data; "%SystemRoot%\\system32\\msimsg.dll"
0x1801949d6  mov     dword ptr [rsp+150h+Data], 7
0x1801949de  mov     rcx, rbx; lpString
0x1801949e1  call    cs:__imp_lstrlenW
0x1801949e8  nop     dword ptr [rax+rax+00h]
0x1801949ed  mov     rcx, [rsp+150h+hKey]; hKey
0x1801949f2  lea     r9d, [rsi+2]; dwType
0x1801949f6  xor     r8d, r8d; Reserved
0x1801949f9  lea     rdx, aEventmessagefi; "EventMessageFile"
0x180194a00  lea     eax, ds:2[rax*2]
0x180194a07  mov     dword ptr [rsp+150h+cbData], eax; cbData
0x180194a0b  mov     [rsp+150h+lpData], rbx; lpData
0x180194a10  call    cs:__imp_RegSetValueExW
0x180194a17  nop     dword ptr [rax+rax+00h]
0x180194a1c  mov     rcx, [rsp+150h+hKey]; hKey
0x180194a21  lea     r9d, [rsi+4]; dwType
0x180194a25  lea     rax, [rsp+150h+Data]
0x180194a2a  mov     dword ptr [rsp+150h+cbData], r9d; cbData
0x180194a2f  xor     r8d, r8d; Reserved
0x180194a32  mov     [rsp+150h+lpData], rax; lpData
0x180194a37  lea     rdx, aTypessupported; "TypesSupported"
0x180194a3e  call    cs:__imp_RegSetValueExW
0x180194a45  nop     dword ptr [rax+rax+00h]
0x180194a4a  mov     rcx, [rsp+150h+hKey]; hKey
0x180194a4f  call    cs:__imp_RegCloseKey
0x180194a56  nop     dword ptr [rax+rax+00h]
0x180194a5b  mov     rcx, cs:hProxyDll; hDll
0x180194a62  lea     r8, CLSID_PSFactoryBuffer; pclsid
0x180194a69  lea     rdx, aProxyFileList; pProxyFileList
0x180194a70  call    cs:__imp_NdrDllRegisterProxy
0x180194a77  nop     dword ptr [rax+rax+00h]
0x180194a7c  lea     rdi, a08lx00000000C0; "{%08lX-0000-0000-C000-000000000046}"
0x180194a83  mov     r14d, 28h ; '('
0x180194a89  test    eax, eax
0x180194a8b  lea     rcx, qword_180311F70; unsigned __int16 *
0x180194a92  mov     ebx, esi
0x180194a94  mov     r9d, 0C1090h
0x180194a9a  mov     r8, rdi; unsigned __int16 *
0x180194a9d  mov     edx, r14d; unsigned __int64
0x180194aa0  setnz   bl
0x180194aa3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180194aa8  test    eax, eax
0x180194aaa  js      loc_180194D28
0x180194ab0  mov     r9d, 0C101Dh
0x180194ab6  lea     rcx, qword_180311F20; unsigned __int16 *
0x180194abd  mov     r8, rdi; unsigned __int16 *
0x180194ac0  mov     edx, r14d; unsigned __int64
0x180194ac3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180194ac8  test    eax, eax
0x180194aca  js      loc_180194D28
0x180194ad0  lea     rcx, [rsp+150h+var_E8]
0x180194ad5  mov     [rsp+150h+var_E8], 14h
0x180194add  call    DllGetVersion
0x180194ae2  mov     eax, dword ptr [rsp+150h+var_E4+8]
0x180194ae6  lea     r8, aDDD; "%d.%d.%d"
0x180194aed  mov     r9d, dword ptr [rsp+150h+var_E4]
0x180194af2  lea     edx, [r14+3Ch]; unsigned __int64
0x180194af6  mov     dword ptr [rsp+150h+cbData], eax
0x180194afa  lea     rcx, qword_180311E00; unsigned __int16 *
0x180194b01  mov     eax, dword ptr [rsp+150h+var_E4+4]
0x180194b05  mov     dword ptr [rsp+150h+lpData], eax
0x180194b09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180194b0e  test    eax, eax
0x180194b10  js      loc_180194D28
0x180194b16  mov     r9d, 0C1094h
0x180194b1c  lea     rcx, qword_180311DB0; unsigned __int16 *
0x180194b23  mov     r8, rdi; unsigned __int16 *
0x180194b26  mov     edx, r14d; unsigned __int64
0x180194b29  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180194b2e  test    eax, eax
0x180194b30  js      loc_180194D28
0x180194b36  mov     r9d, 0C1092h
0x180194b3c  lea     rcx, qword_180311ED0; unsigned __int16 *
0x180194b43  mov     r8, rdi; unsigned __int16 *
0x180194b46  mov     edx, r14d; unsigned __int64
0x180194b49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180194b4e  test    eax, eax
0x180194b50  js      loc_180194D28
0x180194b56  lea     rdi, off_180273E00; "CLSID\\%s\\InprocServer32"
0x180194b5d  mov     r14d, 1
0x180194b63  mov     r8, [rdi]; unsigned __int16 *
0x180194b66  test    r8, r8
0x180194b69  jz      loc_180194C97
0x180194b6f  mov     r9, [rdi+8]
0x180194b73  test    r9, r9
0x180194b76  jz      short loc_180194B63
0x180194b78  cmp     [rdi+10h], rsi
0x180194b7c  jz      short loc_180194B63
0x180194b7e  mov     edx, 50h ; 'P'; unsigned __int64
0x180194b83  lea     rcx, [rbp+50h+var_D0]; unsigned __int16 *
0x180194b87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180194b8c  test    eax, eax
0x180194b8e  js      loc_180194D28
0x180194b94  mov     [rsp+150h+var_110], rsi
0x180194b99  lea     rax, [rsp+150h+Data]
0x180194b9e  mov     [rsp+150h+var_118], rax
0x180194ba3  lea     rdx, [rbp+50h+var_D0]
0x180194ba7  mov     rax, cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180194bae  xor     r9d, r9d
0x180194bb1  mov     [rsp+150h+var_120], rsi
0x180194bb6  xor     r8d, r8d
0x180194bb9  mov     dword ptr [rsp+150h+cbData], 2001Fh
0x180194bc1  mov     rcx, 0FFFFFFFF80000000h
0x180194bc8  mov     dword ptr [rsp+150h+lpData], esi
0x180194bcc  mov     qword ptr [rsp+150h+Data], rsi
0x180194bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194bd6  test    eax, eax
0x180194bd8  jnz     short loc_180194C1B
0x180194bda  mov     rcx, [rdi+10h]; lpString
0x180194bde  call    cs:__imp_lstrlenW
0x180194be5  nop     dword ptr [rax+rax+00h]
0x180194bea  mov     rcx, qword ptr [rsp+150h+Data]; hKey
0x180194bef  mov     r9d, r14d; dwType
0x180194bf2  xor     r8d, r8d; Reserved
0x180194bf5  xor     edx, edx; lpValueName
0x180194bf7  lea     eax, ds:2[rax*2]
0x180194bfe  mov     dword ptr [rsp+150h+cbData], eax; cbData
0x180194c02  mov     rax, [rdi+10h]
0x180194c06  mov     [rsp+150h+lpData], rax; lpData
0x180194c0b  call    cs:__imp_RegSetValueExW
0x180194c12  nop     dword ptr [rax+rax+00h]
0x180194c17  test    eax, eax
0x180194c19  jz      short loc_180194C1E
0x180194c1b  add     ebx, r14d
0x180194c1e  mov     rcx, qword ptr [rsp+150h+Data]
0x180194c23  test    rcx, rcx
0x180194c26  jz      short loc_180194C79
0x180194c28  cmp     [rdi+18h], rsi
0x180194c2c  jz      short loc_180194C79
0x180194c2e  mov     rcx, [rdi+20h]; lpString
0x180194c32  call    cs:__imp_lstrlenW
0x180194c39  nop     dword ptr [rax+rax+00h]
0x180194c3e  mov     rdx, [rdi+18h]; lpValueName
0x180194c42  mov     r9d, r14d; dwType
0x180194c45  mov     rcx, qword ptr [rsp+150h+Data]; hKey
0x180194c4a  xor     r8d, r8d; Reserved
0x180194c4d  lea     eax, ds:2[rax*2]
0x180194c54  mov     dword ptr [rsp+150h+cbData], eax; cbData
0x180194c58  mov     rax, [rdi+20h]
0x180194c5c  mov     [rsp+150h+lpData], rax; lpData
0x180194c61  call    cs:__imp_RegSetValueExW
0x180194c68  nop     dword ptr [rax+rax+00h]
0x180194c6d  mov     rcx, qword ptr [rsp+150h+Data]; hKey
0x180194c72  test    eax, eax
0x180194c74  jz      short loc_180194C79
0x180194c76  add     ebx, r14d
0x180194c79  add     rdi, 28h ; '('
0x180194c7d  test    rcx, rcx
0x180194c80  jz      loc_180194B63
0x180194c86  call    cs:__imp_RegCloseKey
0x180194c8d  nop     dword ptr [rax+rax+00h]
0x180194c92  jmp     loc_180194B63
0x180194c97  mov     ecx, 72h ; 'r'; int
0x180194c9c  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x180194ca1  test    al, al
0x180194ca3  jz      short loc_180194CB1
0x180194ca5  call    DllRegisterServerTest
0x180194caa  test    eax, eax
0x180194cac  jz      short loc_180194CB1
0x180194cae  add     ebx, r14d
0x180194cb1  test    ebx, ebx
0x180194cb3  jz      short loc_180194CBC
0x180194cb5  mov     eax, 80040201h
0x180194cba  jmp     short loc_180194D2D
0x180194cbc  mov     rax, cs:?LoadTypeLib@OLEAUT32@@3P6AJPEBGPEAPEAUITypeLib@@@ZEA; long (*OLEAUT32::LoadTypeLib)(ushort const *,ITypeLib * *)
0x180194cc3  lea     rdx, [rsp+150h+var_F0]
0x180194cc8  lea     rcx, Filename
0x180194ccf  mov     [rsp+150h+var_F0], rsi
0x180194cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194cd9  cmp     eax, 80028018h
0x180194cde  jnz     short loc_180194CE4
0x180194ce0  xor     eax, eax
0x180194ce2  jmp     short loc_180194D2D
0x180194ce4  test    eax, eax
0x180194ce6  jnz     short loc_180194D21
0x180194ce8  mov     rcx, [rsp+150h+var_F0]
0x180194ced  lea     rdx, Filename
0x180194cf4  mov     rax, cs:?RegisterTypeLib@OLEAUT32@@3P6AJPEAUITypeLib@@PEAG1@ZEA; long (*OLEAUT32::RegisterTypeLib)(ITypeLib *,ushort *,ushort *)
0x180194cfb  xor     r8d, r8d
0x180194cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194d03  mov     rcx, [rsp+150h+var_F0]
0x180194d08  mov     ebx, eax
0x180194d0a  mov     rdx, [rcx]
0x180194d0d  mov     rax, [rdx+10h]
0x180194d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194d16  neg     ebx
0x180194d18  sbb     eax, eax
0x180194d1a  and     eax, 80040200h
0x180194d1f  jmp     short loc_180194D2D
0x180194d21  mov     eax, 80040200h
0x180194d26  jmp     short loc_180194D2D
0x180194d28  mov     eax, 80004005h
0x180194d2d  mov     rcx, [rbp+50h+var_30]
0x180194d31  xor     rcx, rsp; StackCookie
0x180194d34  call    __security_check_cookie
0x180194d39  add     rsp, 130h
0x180194d40  pop     r14
0x180194d42  pop     rdi
0x180194d43  pop     rsi
0x180194d44  pop     rbx
0x180194d45  pop     rbp
0x180194d46  retn
```
