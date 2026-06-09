# MachineInfo::GetDeviceName(void)

- ea: `0x18003a850`
- end: `0x18003a9f8`
- name: `?GetDeviceName@MachineInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `424`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180009f14`
- `0x180014f2c`
- `0x1800157b8`
- `0x18002a760`
- `0x18003a850`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a8df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a8df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a947`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a963`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a947`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a963`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a91d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a91d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003a97c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003a97c`

## string_xrefs

- `0x18003a8f2`: `Unable to load DiagnosticDataSettings.dll`
- `0x18003a8d8`: `DiagnosticDataSettings.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MachineInfo::GetDeviceName(__int64 a1, __int64 a2)
{
  unsigned __int16 v3; // dx
  unsigned __int16 v4; // cx
  unsigned __int16 v5; // r8
  HMODULE Library; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  int v9; // edi
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  char *v12; // rdi
  __int64 v13; // rbx
  __int64 v15; // [rsp+20h] [rbp-268h] BYREF
  __int64 v16; // [rsp+28h] [rbp-260h]
  HMODULE v17; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF

  v16 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
  v15 = 0x10400000001LL;
  memset_0(Buffer, 0, 0x208u);
  if ( IsWindowsVersionOrGreaterEx(v4, v3, v5, 0x42EEu) )
  {
    Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
    v7 = Library;
    v17 = Library;
    if ( !Library )
    {
      AslLogCallPrintf(
        1,
        "MachineInfo::CanSendDeviceName",
        1624,
        "Unable to load DiagnosticDataSettings.dll",
        v15,
        v16,
        0);
      return a2;
    }
    ProcAddress = GetProcAddress(Library, "TelIsRestrictivePolicySet");
    if ( !ProcAddress )
    {
      AslLogCallPrintf(
        1,
        "MachineInfo::CanSendDeviceName",
        1633,
        "Unable to retrieve TelIsRestrictivePolicySet function",
        v15,
        v16,
        v17);
      FreeLibrary(v7);
      return a2;
    }
    v9 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"AllowDeviceNameInDiagnosticData");
    FreeLibrary(v7);
    if ( !v9 )
      return a2;
  }
  if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, Buffer, (LPDWORD)&v15 + 1) )
  {
    v11 = -1;
    do
      ++v11;
    while ( Buffer[v11] );
    if ( v11 > *(_QWORD *)(a2 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a2,
        v11,
        v10,
        Buffer);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v12 = (char *)a2;
      else
        v12 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = v11;
      v13 = 2 * v11;
      memmove_0(v12, Buffer, 2 * v11);
      *(_WORD *)&v12[v13] = 0;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18003a850  push    rbx
0x18003a852  push    rbp
0x18003a853  push    rsi
0x18003a854  push    rdi
0x18003a855  sub     rsp, 268h
0x18003a85c  mov     rax, cs:__security_cookie
0x18003a863  xor     rax, rsp
0x18003a866  mov     [rsp+288h+var_38], rax
0x18003a86e  mov     rsi, rdx
0x18003a871  mov     [rsp+288h+var_260], rdx
0x18003a876  xor     ebp, ebp
0x18003a878  mov     [rsp+288h+var_268], ebp
0x18003a87c  xorps   xmm0, xmm0
0x18003a87f  movups  xmmword ptr [rdx], xmm0
0x18003a882  mov     [rdx+10h], rbp
0x18003a886  mov     [rdx+18h], rbp
0x18003a88a  lea     edi, [rbp+1]
0x18003a88d  mov     r8d, edi
0x18003a890  lea     rdx, asc_1801B4764; "#"
0x18003a897  mov     rcx, rsi
0x18003a89a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003a89f  mov     [rsp+288h+var_268], edi
0x18003a8a3  xor     edx, edx; Val
0x18003a8a5  mov     r8d, 208h; Size
0x18003a8ab  lea     rcx, [rsp+288h+Buffer]; void *
0x18003a8b0  call    memset_0
0x18003a8b5  mov     [rsp+288h+nSize], 104h
0x18003a8bd  mov     r9d, 42EEh; unsigned __int16
0x18003a8c3  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18003a8c8  test    al, al
0x18003a8ca  jz      loc_18003A96D
0x18003a8d0  xor     edx, edx; hFile
0x18003a8d2  mov     r8d, 800h; dwFlags
0x18003a8d8  lea     rcx, aDiagnosticdata_1; "DiagnosticDataSettings.dll"
0x18003a8df  call    cs:__imp_LoadLibraryExW
0x18003a8e5  mov     rbx, rax
0x18003a8e8  mov     [rsp+288h+var_258], rax
0x18003a8ed  test    rax, rax
0x18003a8f0  jnz     short loc_18003A913
0x18003a8f2  lea     r9, aUnableToLoadDi; "Unable to load DiagnosticDataSettings.d"...
0x18003a8f9  mov     r8d, 658h
0x18003a8ff  lea     rdx, aMachineinfoCan; "MachineInfo::CanSendDeviceName"
0x18003a906  mov     ecx, edi
0x18003a908  call    AslLogCallPrintf
0x18003a90d  nop
0x18003a90e  jmp     loc_18003A9D8
0x18003a913  lea     rdx, aTelisrestricti; "TelIsRestrictivePolicySet"
0x18003a91a  mov     rcx, rbx; hModule
0x18003a91d  call    cs:__imp_GetProcAddress
0x18003a923  test    rax, rax
0x18003a926  jnz     short loc_18003A952
0x18003a928  lea     r9, aUnableToRetrie; "Unable to retrieve TelIsRestrictivePoli"...
0x18003a92f  mov     r8d, 661h
0x18003a935  lea     rdx, aMachineinfoCan; "MachineInfo::CanSendDeviceName"
0x18003a93c  mov     ecx, edi
0x18003a93e  call    AslLogCallPrintf
0x18003a943  nop
0x18003a944  mov     rcx, rbx; hLibModule
0x18003a947  call    cs:__imp_FreeLibrary
0x18003a94d  jmp     loc_18003A9D8
0x18003a952  lea     rcx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x18003a959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a95e  mov     edi, eax
0x18003a960  mov     rcx, rbx; hLibModule
0x18003a963  call    cs:__imp_FreeLibrary
0x18003a969  test    edi, edi
0x18003a96b  jz      short loc_18003A9D8
0x18003a96d  lea     r8, [rsp+288h+nSize]; nSize
0x18003a972  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x18003a977  mov     ecx, 5; NameType
0x18003a97c  call    cs:__imp_GetComputerNameExW
0x18003a982  test    eax, eax
0x18003a984  jz      short loc_18003A9D8
0x18003a986  lea     rax, [rsp+288h+Buffer]
0x18003a98b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003a98f  inc     rdx
0x18003a992  cmp     [rax+rdx*2], bp
0x18003a996  jnz     short loc_18003A98F
0x18003a998  cmp     rdx, [rsi+18h]
0x18003a99c  ja      short loc_18003A9CB
0x18003a99e  cmp     qword ptr [rsi+18h], 7
0x18003a9a3  jbe     short loc_18003A9AA
0x18003a9a5  mov     rdi, [rsi]
0x18003a9a8  jmp     short loc_18003A9AD
0x18003a9aa  mov     rdi, rsi
0x18003a9ad  mov     [rsi+10h], rdx
0x18003a9b1  lea     rbx, [rdx+rdx]
0x18003a9b5  mov     r8, rbx; Size
0x18003a9b8  lea     rdx, [rsp+288h+Buffer]; Src
0x18003a9bd  mov     rcx, rdi; void *
0x18003a9c0  call    memmove_0
0x18003a9c5  mov     [rbx+rdi], bp
0x18003a9c9  jmp     short loc_18003A9D8
0x18003a9cb  lea     r9, [rsp+288h+Buffer]
0x18003a9d0  mov     rcx, rsi
0x18003a9d3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003a9d8  mov     rax, rsi
0x18003a9db  mov     rcx, [rsp+288h+var_38]
0x18003a9e3  xor     rcx, rsp; StackCookie
0x18003a9e6  call    __security_check_cookie
0x18003a9eb  add     rsp, 268h
0x18003a9f2  pop     rdi
0x18003a9f3  pop     rsi
0x18003a9f4  pop     rbp
0x18003a9f5  pop     rbx
0x18003a9f6  retn
```
