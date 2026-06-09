# CSystemWriter::AddCorePnPFiles(IVssCreateWriterMetadata *,void *)

- ea: `0x180007320`
- end: `0x1800075ff`
- name: `?AddCorePnPFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `735`
- prototype: `bool __fastcall(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e1d4`

## callees

- `0x180005640`
- `0x180005fc0`
- `0x180006e54`
- `0x180007320`
- `0x180007608`
- `0x18000be40`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007574`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000740e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000740e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000745d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000745d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800074a4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800074a4`
- `drvstore!DriverStoreEnumW` at `0x1800073d1`
- `drvstore!DriverStoreEnumW` at `0x1800073d1`

## string_xrefs

- `0x18000734b`: `%systemroot%\system32\DriverStore\FileRepository`
- `0x18000759b`: `AddCorePnPFiles: Unable to expand path for %ws.`
- `0x1800075db`: `AddCorePnPFiles : Opening PnpLockdownFiles key failed.`

## pseudocode

```c
__int64 __fastcall CSystemWriter::AddCorePnPFiles(CSystemWriter *this, struct IVssCreateWriterMetadata *a2, void *a3)
{
  __int64 (*v4)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...); // rax
  unsigned int v5; // eax
  unsigned __int8 v6; // bp
  unsigned int v7; // r8d
  DWORD LastError; // eax
  DWORD i; // edi
  DWORD v10; // edx
  DWORD j; // eax
  DWORD v12; // eax
  DWORD v14; // ebx
  const unsigned __int16 *v15; // rdx
  HKEY hKey; // [rsp+50h] [rbp-888h] BYREF
  __int128 v17; // [rsp+58h] [rbp-880h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-870h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-868h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp-658h] BYREF
  unsigned __int16 v21[520]; // [rsp+490h] [rbp-448h] BYREF

  v4 = *(__int64 (**)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)a2 + 40LL);
  v17 = 0;
  hKey = 0;
  cchName = 0;
  v5 = v4(a2, 0, L"System Files", L"%systemroot%\\system32\\DriverStore\\FileRepository", L"*.*", 1, 0, 3855);
  if ( v5 )
  {
    CSystemWriter::LogSystemErrorEvent(0x201u, L"AddCorePnPFiles : Adding driver store files failed.", v5);
LABEL_17:
    v6 = 0;
  }
  else
  {
    *(_QWORD *)&v17 = a3;
    DWORD2(v17) = 0;
    v6 = 1;
    if ( !(unsigned int)DriverStoreEnumW(0, 4, EnumPublishInfCallback, &v17) )
    {
      LastError = GetLastError();
      v15 = L"AddCorePnPFiles : Enumerating driver store published INFs failed.";
LABEL_31:
      v7 = LastError;
      goto LABEL_32;
    }
    v7 = DWORD2(v17);
    if ( SDWORD2(v17) < 0 )
    {
      v15 = L"AddCorePnPFiles : Adding enumerated published INFs failed.";
LABEL_32:
      CSystemWriter::LogSystemErrorEvent(0x201u, v15, v7);
      goto LABEL_18;
    }
    LastError = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\PnpLockdownFiles",
                  0,
                  0x20019u,
                  &hKey);
    if ( !LastError )
    {
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        LastError = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( LastError == 259 )
          goto LABEL_18;
        if ( LastError )
        {
          v15 = L"AddCorePnPFiles : Enumerating PnpLockdownFiles keys failed.";
          goto LABEL_31;
        }
        v10 = cchName;
        for ( j = 0; j < v10; ++j )
        {
          if ( Name[j] == 47 )
            Name[j] = 92;
        }
        v12 = ExpandEnvironmentStringsW(Name, Dst, 0x104u);
        cchName = v12;
        if ( v12 )
        {
          if ( v12 >= 0x104 )
          {
            v14 = 13;
LABEL_27:
            StringCchPrintfW(v21, 0x208u, L"AddCorePnPFiles: Unable to expand path for %ws.", Name);
            CSystemWriter::LogSystemErrorEvent(0x201u, v21, v14);
            continue;
          }
        }
        else
        {
          v14 = GetLastError();
          if ( v14 )
            goto LABEL_27;
        }
        if ( (unsigned int)pSetupFileExists(Dst) && (unsigned int)pSetupStringTableAddString(a3, Dst) == -1 )
          goto LABEL_17;
      }
    }
    if ( LastError != 2 )
    {
      v15 = L"AddCorePnPFiles : Opening PnpLockdownFiles key failed.";
      goto LABEL_31;
    }
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180007320  mov     r11, rsp
0x180007323  push    rbp
0x180007324  sub     rsp, 8D0h
0x18000732b  mov     rax, cs:__security_cookie
0x180007332  xor     rax, rsp
0x180007335  mov     [rsp+8D8h+var_38], rax
0x18000733d  mov     rax, [rdx]
0x180007340  lea     rcx, asc_180024ED8; "*.*"
0x180007347  mov     [r11+8], rbx
0x18000734b  lea     r9, aSystemrootSyst_2; "%systemroot%\\system32\\DriverStore\\Fi"...
0x180007352  mov     [r11-10h], rsi
0x180007356  mov     r10, rdx
0x180007359  mov     [r11-18h], rdi
0x18000735d  mov     rsi, r8
0x180007360  mov     rax, [rax+28h]
0x180007364  lea     r8, aSystemFiles; "System Files"
0x18000736b  mov     dword ptr [rsp+8D8h+lpftLastWriteTime], 0F0Fh
0x180007373  xorps   xmm0, xmm0
0x180007376  mov     [r11-20h], r14
0x18000737a  xor     edx, edx
0x18000737c  mov     [r11-28h], r15
0x180007380  xor     r15d, r15d
0x180007383  mov     [rsp+8D8h+lpcchClass], r15
0x180007388  mov     byte ptr [rsp+8D8h+lpClass], 1
0x18000738d  mov     [rsp+8D8h+phkResult], rcx
0x180007392  mov     rcx, r10
0x180007395  movups  [rsp+8D8h+var_880], xmm0
0x18000739a  mov     [rsp+8D8h+hKey], r15
0x18000739f  mov     [rsp+8D8h+cchName], r15d
0x1800073a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a9  test    eax, eax
0x1800073ab  jnz     loc_18000755E
0x1800073b1  lea     r9, [rsp+8D8h+var_880]
0x1800073b6  mov     qword ptr [rsp+8D8h+var_880], rsi
0x1800073bb  lea     r8, ?EnumPublishInfCallback@@YAHPEAUHDRIVERSTORE__@@PEBGPEAU_DRIVERSTORE_DRIVERPACKAGE_INFOW@@_J@Z; EnumPublishInfCallback(HDRIVERSTORE__ *,ushort const *,_DRIVERSTORE_DRIVERPACKAGE_INFOW *,__int64)
0x1800073c2  mov     dword ptr [rsp+8D8h+var_880+8], r15d
0x1800073c7  mov     edx, 4
0x1800073cc  xor     ecx, ecx
0x1800073ce  mov     bpl, 1
0x1800073d1  call    cs:__imp_DriverStoreEnumW
0x1800073d7  test    eax, eax
0x1800073d9  jz      loc_180007574
0x1800073df  mov     r8d, dword ptr [rsp+8D8h+var_880+8]
0x1800073e4  test    r8d, r8d
0x1800073e7  js      loc_180007583
0x1800073ed  lea     rax, [rsp+8D8h+hKey]
0x1800073f2  mov     r9d, 20019h; samDesired
0x1800073f8  xor     r8d, r8d; ulOptions
0x1800073fb  mov     [rsp+8D8h+phkResult], rax; phkResult
0x180007400  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007407  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000740e  call    cs:__imp_RegOpenKeyExW
0x180007414  test    eax, eax
0x180007416  jnz     loc_1800075D2
0x18000741c  mov     edi, r15d
0x18000741f  mov     r14d, 5Ch ; '\'
0x180007425  nop     word ptr [rax+rax+00000000h]
0x180007430  mov     rcx, [rsp+8D8h+hKey]; hKey
0x180007435  lea     r9, [rsp+8D8h+cchName]; lpcchName
0x18000743a  mov     [rsp+8D8h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000743f  lea     r8, [rsp+8D8h+Name]; lpName
0x180007444  mov     [rsp+8D8h+lpcchClass], r15; lpcchClass
0x180007449  mov     edx, edi; dwIndex
0x18000744b  mov     [rsp+8D8h+lpClass], r15; lpClass
0x180007450  mov     [rsp+8D8h+phkResult], r15; lpReserved
0x180007455  mov     [rsp+8D8h+cchName], 104h
0x18000745d  call    cs:__imp_RegEnumKeyExW
0x180007463  cmp     eax, 103h
0x180007468  jz      loc_1800074F9
0x18000746e  test    eax, eax
0x180007470  jnz     loc_1800075C9
0x180007476  mov     edx, [rsp+8D8h+cchName]
0x18000747a  mov     eax, r15d
0x18000747d  test    edx, edx
0x18000747f  jz      short loc_180007491
0x180007481  mov     ecx, eax
0x180007483  cmp     [rsp+rcx*2+8D8h+Name], 2Fh ; '/'
0x180007489  jz      short loc_1800074D9
0x18000748b  inc     eax
0x18000748d  cmp     eax, edx
0x18000748f  jb      short loc_180007481
0x180007491  mov     r8d, 104h; nSize
0x180007497  lea     rdx, [rsp+8D8h+Dst]; lpDst
0x18000749f  lea     rcx, [rsp+8D8h+Name]; lpSrc
0x1800074a4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800074aa  mov     [rsp+8D8h+cchName], eax
0x1800074ae  test    eax, eax
0x1800074b0  jz      loc_18000754C
0x1800074b6  cmp     eax, 104h
0x1800074bb  jnb     loc_18000758C
0x1800074c1  lea     rcx, [rsp+8D8h+Dst]; lpFileName
0x1800074c9  call    pSetupFileExists
0x1800074ce  test    eax, eax
0x1800074d0  jnz     short loc_1800074E1
0x1800074d2  inc     edi
0x1800074d4  jmp     loc_180007430
0x1800074d9  mov     [rsp+rcx*2+8D8h+Name], r14w
0x1800074df  jmp     short loc_18000748B
0x1800074e1  lea     rdx, [rsp+8D8h+Dst]
0x1800074e9  mov     rcx, rsi
0x1800074ec  call    pSetupStringTableAddString
0x1800074f1  cmp     eax, 0FFFFFFFFh
0x1800074f4  jnz     short loc_1800074D2
0x1800074f6  xor     bpl, bpl
0x1800074f9  mov     rcx, [rsp+8D8h+hKey]; hKey
0x1800074fe  mov     r15, [rsp+8D8h+var_28]
0x180007506  mov     r14, [rsp+8D8h+var_20]
0x18000750e  mov     rdi, [rsp+8D8h+var_18]
0x180007516  mov     rsi, [rsp+8D8h+var_10]
0x18000751e  mov     rbx, [rsp+8D8h+arg_0]
0x180007526  test    rcx, rcx
0x180007529  jnz     loc_1800075F4
0x18000752f  movzx   eax, bpl
0x180007533  mov     rcx, [rsp+8D8h+var_38]
0x18000753b  xor     rcx, rsp; StackCookie
0x18000753e  call    __security_check_cookie
0x180007543  add     rsp, 8D0h
0x18000754a  pop     rbp
0x18000754b  retn
0x18000754c  call    cs:__imp_GetLastError
0x180007552  mov     ebx, eax
0x180007554  test    eax, eax
0x180007556  jz      loc_1800074C1
0x18000755c  jmp     short loc_180007591
0x18000755e  mov     r8d, eax; unsigned int
0x180007561  lea     rdx, aAddcorepnpfile_0; "AddCorePnPFiles : Adding driver store f"...
0x180007568  mov     ecx, 201h; unsigned int
0x18000756d  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180007572  jmp     short loc_1800074F6
0x180007574  call    cs:__imp_GetLastError
0x18000757a  lea     rdx, aAddcorepnpfile_3; "AddCorePnPFiles : Enumerating driver st"...
0x180007581  jmp     short loc_1800075E2
0x180007583  lea     rdx, aAddcorepnpfile; "AddCorePnPFiles : Adding enumerated pub"...
0x18000758a  jmp     short loc_1800075E5
0x18000758c  mov     ebx, 0Dh
0x180007591  lea     r9, [rsp+8D8h+Name]
0x180007596  mov     edx, 208h; unsigned __int64
0x18000759b  lea     r8, aAddcorepnpfile_2; "AddCorePnPFiles: Unable to expand path "...
0x1800075a2  lea     rcx, [rsp+8D8h+var_448]; unsigned __int16 *
0x1800075aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800075af  mov     r8d, ebx; unsigned int
0x1800075b2  lea     rdx, [rsp+8D8h+var_448]; unsigned __int16 *
0x1800075ba  mov     ecx, 201h; unsigned int
0x1800075bf  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800075c4  jmp     loc_1800074D2
0x1800075c9  lea     rdx, aAddcorepnpfile_1; "AddCorePnPFiles : Enumerating PnpLockdo"...
0x1800075d0  jmp     short loc_1800075E2
0x1800075d2  cmp     eax, 2
0x1800075d5  jz      loc_1800074F9
0x1800075db  lea     rdx, aAddcorepnpfile_4; "AddCorePnPFiles : Opening PnpLockdownFi"...
0x1800075e2  mov     r8d, eax; unsigned int
0x1800075e5  mov     ecx, 201h; unsigned int
0x1800075ea  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800075ef  jmp     loc_1800074F9
0x1800075f4  call    cs:__imp_RegCloseKey
0x1800075fa  jmp     loc_18000752F
```
