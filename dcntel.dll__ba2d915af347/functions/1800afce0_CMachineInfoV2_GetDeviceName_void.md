# CMachineInfoV2::GetDeviceName(void)

- ea: `0x1800afce0`
- end: `0x1800afe88`
- name: `?GetDeviceName@CMachineInfoV2@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
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
- `0x1800afce0`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800afd6f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800afd6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800afdd7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800afdf3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800afdd7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800afdf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800afdad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800afdad`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800afe0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800afe0c`

## string_xrefs

- `0x1800afd82`: `Unable to load DiagnosticDataSettings.dll`
- `0x1800afd68`: `DiagnosticDataSettings.dll`

## pseudocode

```c
__int64 __fastcall CMachineInfoV2::GetDeviceName(__int64 a1, __int64 a2)
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
        "CMachineInfoV2::CanSendDeviceName",
        1639,
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
        "CMachineInfoV2::CanSendDeviceName",
        1648,
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
0x1800afce0  push    rbx
0x1800afce2  push    rbp
0x1800afce3  push    rsi
0x1800afce4  push    rdi
0x1800afce5  sub     rsp, 268h
0x1800afcec  mov     rax, cs:__security_cookie
0x1800afcf3  xor     rax, rsp
0x1800afcf6  mov     [rsp+288h+var_38], rax
0x1800afcfe  mov     rsi, rdx
0x1800afd01  mov     [rsp+288h+var_260], rdx
0x1800afd06  xor     ebp, ebp
0x1800afd08  mov     [rsp+288h+var_268], ebp
0x1800afd0c  xorps   xmm0, xmm0
0x1800afd0f  movups  xmmword ptr [rdx], xmm0
0x1800afd12  mov     [rdx+10h], rbp
0x1800afd16  mov     [rdx+18h], rbp
0x1800afd1a  lea     edi, [rbp+1]
0x1800afd1d  mov     r8d, edi
0x1800afd20  lea     rdx, asc_1801B4764; "#"
0x1800afd27  mov     rcx, rsi
0x1800afd2a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800afd2f  mov     [rsp+288h+var_268], edi
0x1800afd33  xor     edx, edx; Val
0x1800afd35  mov     r8d, 208h; Size
0x1800afd3b  lea     rcx, [rsp+288h+Buffer]; void *
0x1800afd40  call    memset_0
0x1800afd45  mov     [rsp+288h+nSize], 104h
0x1800afd4d  mov     r9d, 42EEh; unsigned __int16
0x1800afd53  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1800afd58  test    al, al
0x1800afd5a  jz      loc_1800AFDFD
0x1800afd60  xor     edx, edx; hFile
0x1800afd62  mov     r8d, 800h; dwFlags
0x1800afd68  lea     rcx, aDiagnosticdata_1; "DiagnosticDataSettings.dll"
0x1800afd6f  call    cs:__imp_LoadLibraryExW
0x1800afd75  mov     rbx, rax
0x1800afd78  mov     [rsp+288h+var_258], rax
0x1800afd7d  test    rax, rax
0x1800afd80  jnz     short loc_1800AFDA3
0x1800afd82  lea     r9, aUnableToLoadDi; "Unable to load DiagnosticDataSettings.d"...
0x1800afd89  mov     r8d, 667h
0x1800afd8f  lea     rdx, aCmachineinfov2_1; "CMachineInfoV2::CanSendDeviceName"
0x1800afd96  mov     ecx, edi
0x1800afd98  call    AslLogCallPrintf
0x1800afd9d  nop
0x1800afd9e  jmp     loc_1800AFE68
0x1800afda3  lea     rdx, aTelisrestricti; "TelIsRestrictivePolicySet"
0x1800afdaa  mov     rcx, rbx; hModule
0x1800afdad  call    cs:__imp_GetProcAddress
0x1800afdb3  test    rax, rax
0x1800afdb6  jnz     short loc_1800AFDE2
0x1800afdb8  lea     r9, aUnableToRetrie; "Unable to retrieve TelIsRestrictivePoli"...
0x1800afdbf  mov     r8d, 670h
0x1800afdc5  lea     rdx, aCmachineinfov2_1; "CMachineInfoV2::CanSendDeviceName"
0x1800afdcc  mov     ecx, edi
0x1800afdce  call    AslLogCallPrintf
0x1800afdd3  nop
0x1800afdd4  mov     rcx, rbx; hLibModule
0x1800afdd7  call    cs:__imp_FreeLibrary
0x1800afddd  jmp     loc_1800AFE68
0x1800afde2  lea     rcx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x1800afde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afdee  mov     edi, eax
0x1800afdf0  mov     rcx, rbx; hLibModule
0x1800afdf3  call    cs:__imp_FreeLibrary
0x1800afdf9  test    edi, edi
0x1800afdfb  jz      short loc_1800AFE68
0x1800afdfd  lea     r8, [rsp+288h+nSize]; nSize
0x1800afe02  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x1800afe07  mov     ecx, 5; NameType
0x1800afe0c  call    cs:__imp_GetComputerNameExW
0x1800afe12  test    eax, eax
0x1800afe14  jz      short loc_1800AFE68
0x1800afe16  lea     rax, [rsp+288h+Buffer]
0x1800afe1b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800afe1f  inc     rdx
0x1800afe22  cmp     [rax+rdx*2], bp
0x1800afe26  jnz     short loc_1800AFE1F
0x1800afe28  cmp     rdx, [rsi+18h]
0x1800afe2c  ja      short loc_1800AFE5B
0x1800afe2e  cmp     qword ptr [rsi+18h], 7
0x1800afe33  jbe     short loc_1800AFE3A
0x1800afe35  mov     rdi, [rsi]
0x1800afe38  jmp     short loc_1800AFE3D
0x1800afe3a  mov     rdi, rsi
0x1800afe3d  mov     [rsi+10h], rdx
0x1800afe41  lea     rbx, [rdx+rdx]
0x1800afe45  mov     r8, rbx; Size
0x1800afe48  lea     rdx, [rsp+288h+Buffer]; Src
0x1800afe4d  mov     rcx, rdi; void *
0x1800afe50  call    memmove_0
0x1800afe55  mov     [rbx+rdi], bp
0x1800afe59  jmp     short loc_1800AFE68
0x1800afe5b  lea     r9, [rsp+288h+Buffer]
0x1800afe60  mov     rcx, rsi
0x1800afe63  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800afe68  mov     rax, rsi
0x1800afe6b  mov     rcx, [rsp+288h+var_38]
0x1800afe73  xor     rcx, rsp; StackCookie
0x1800afe76  call    __security_check_cookie
0x1800afe7b  add     rsp, 268h
0x1800afe82  pop     rdi
0x1800afe83  pop     rsi
0x1800afe84  pop     rbp
0x1800afe85  pop     rbx
0x1800afe86  retn
```
