# _lambda_99716fa30d67e4b5b63e688cef2f3ff5_::operator()

- ea: `0x1800bfc20`
- end: `0x1800bfd86`
- name: `_lambda_99716fa30d67e4b5b63e688cef2f3ff5_::operator()`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1802c41ec`

## callees

- `0x1800793cc`
- `0x1800bfc20`
- `0x1800bfd8c`
- `0x18019ae5c`
- `0x1802c4264`
- `0x180416160`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800bfc88`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800bfc88`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800bfcbd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800bfcbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfcf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfd16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfd3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfcf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfd16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfd3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800bfc6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800bfc9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800bfc6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800bfc9e`

## string_xrefs

- `0x1800bfd55`: `EXDI: LoadLibraryExW failed loading the EXDI COM DDL: %s\n`
- `0x1800bfd31`: `EXDI: GetProcAddress-DllRegisterServer failed for the EXDI COM DDL: %s\n`
- `0x1800bfce6`: `EXDI: Debugger must be run from an elevated command prompt to register the EXDI COM server.\n`
- `0x1800bfcb3`: `DllRegisterServer`
- `0x1800bfd08`: `EXDI: Failed registering the EXDI COM Server: %s and error = %d.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_99716fa30d67e4b5b63e688cef2f3ff5_::operator()(__int64 a1)
{
  _lambda_df994f46f8d10f2f7c700efdae03d4e0_ *v2; // rcx
  UINT v4; // edi
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  __int64 v7; // rcx
  signed int v8; // ebx
  DWORD LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF
  HMODULE v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = **(HMODULE **)(a1 + 8);
  v2 = _lambda_df994f46f8d10f2f7c700efdae03d4e0_::_lambda_df994f46f8d10f2f7c700efdae03d4e0_(
         (_lambda_df994f46f8d10f2f7c700efdae03d4e0_ *)&v12,
         (struct Debugger::TargetComposition::Services::OS::Windows::WindowsKernelInfrastructure *)&v13,
         *(struct IDebugServiceManager ***)a1);
  if ( (int)Debugger::DataModel::ConvertException__lambda_fe662b9ea915e352c5eea56ac58037a4___(v2) >= 0 )
    return 0;
  v4 = SetErrorMode(1u);
  Library = LoadLibraryExW(**(LPCWSTR **)(a1 + 8), 0, 0);
  v13 = Library;
  SetErrorMode(v4);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllRegisterServer");
    if ( ProcAddress )
    {
      v8 = ((__int64 (__fastcall *)(__int64))ProcAddress)(v7);
      if ( v8 < 0 )
      {
        if ( !IsUserAdmin() )
          ErrOut(L"EXDI: Debugger must be run from an elevated command prompt to register the EXDI COM server.\n");
        LastError = GetLastError();
        ErrOut(L"EXDI: Failed registering the EXDI COM Server: %s and error = %d.\n", **(_QWORD **)(a1 + 8), LastError);
      }
    }
    else
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      ErrOut(L"EXDI: GetProcAddress-DllRegisterServer failed for the EXDI COM DDL: %s\n", **(_QWORD **)(a1 + 8));
    }
  }
  else
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    ErrOut(L"EXDI: LoadLibraryExW failed loading the EXDI COM DDL: %s\n", **(_QWORD **)(a1 + 8));
  }
  VersionQuery::~VersionQuery((VersionQuery *)&v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800bfc20  mov     r11, rsp
0x1800bfc23  push    rdi
0x1800bfc24  sub     rsp, 40h
0x1800bfc28  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x1800bfc30  mov     [r11+10h], rbx
0x1800bfc34  mov     [r11+18h], rsi
0x1800bfc38  mov     rsi, rcx
0x1800bfc3b  mov     rax, [rcx+8]
0x1800bfc3f  mov     rdx, [rax]
0x1800bfc42  mov     [r11+8], rdx
0x1800bfc46  mov     r8, [rcx]; struct IDebugServiceManager **
0x1800bfc49  lea     rdx, [r11+8]; struct Debugger::TargetComposition::Services::OS::Windows::WindowsKernelInfrastructure *
0x1800bfc4d  lea     rcx, [r11-20h]; this
0x1800bfc51  call    ??0_lambda_df994f46f8d10f2f7c700efdae03d4e0_@@QEAA@PEAVWindowsKernelInfrastructure@Windows@OS@Services@TargetComposition@Debugger@@AEAPEAUIDebugServiceManager@@@Z; _lambda_df994f46f8d10f2f7c700efdae03d4e0_::_lambda_df994f46f8d10f2f7c700efdae03d4e0_(Debugger::TargetComposition::Services::OS::Windows::WindowsKernelInfrastructure *,IDebugServiceManager * &)
0x1800bfc56  mov     rcx, rax
0x1800bfc59  call    Debugger__DataModel__ConvertException__lambda_fe662b9ea915e352c5eea56ac58037a4___
0x1800bfc5e  test    eax, eax
0x1800bfc60  js      short loc_1800BFC69
0x1800bfc62  xor     eax, eax
0x1800bfc64  jmp     loc_1800BFD75
0x1800bfc69  mov     ecx, 1; uMode
0x1800bfc6e  call    cs:__imp_SetErrorMode
0x1800bfc75  nop     dword ptr [rax+rax+00h]
0x1800bfc7a  mov     edi, eax
0x1800bfc7c  mov     rcx, [rsi+8]
0x1800bfc80  xor     r8d, r8d; dwFlags
0x1800bfc83  xor     edx, edx; hFile
0x1800bfc85  mov     rcx, [rcx]; lpLibFileName
0x1800bfc88  call    cs:__imp_LoadLibraryExW
0x1800bfc8f  nop     dword ptr [rax+rax+00h]
0x1800bfc94  mov     rbx, rax
0x1800bfc97  mov     [rsp+48h+arg_0], rax
0x1800bfc9c  mov     ecx, edi; uMode
0x1800bfc9e  call    cs:__imp_SetErrorMode
0x1800bfca5  nop     dword ptr [rax+rax+00h]
0x1800bfcaa  test    rbx, rbx
0x1800bfcad  jz      loc_1800BFD3A
0x1800bfcb3  lea     rdx, aDllregisterser; "DllRegisterServer"
0x1800bfcba  mov     rcx, rbx; hModule
0x1800bfcbd  call    cs:__imp_GetProcAddress
0x1800bfcc4  nop     dword ptr [rax+rax+00h]
0x1800bfcc9  test    rax, rax
0x1800bfccc  jz      short loc_1800BFD16
0x1800bfcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfcd3  mov     ebx, eax
0x1800bfcd5  test    eax, eax
0x1800bfcd7  jns     loc_1800BFD69
0x1800bfcdd  call    ?IsUserAdmin@@YAHXZ; IsUserAdmin(void)
0x1800bfce2  test    eax, eax
0x1800bfce4  jnz     short loc_1800BFCF2
0x1800bfce6  lea     rcx, aExdiDebuggerMu; "EXDI: Debugger must be run from an elev"...
0x1800bfced  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800bfcf2  call    cs:__imp_GetLastError
0x1800bfcf9  nop     dword ptr [rax+rax+00h]
0x1800bfcfe  mov     rdx, [rsi+8]
0x1800bfd02  mov     r8d, eax
0x1800bfd05  mov     rdx, [rdx]
0x1800bfd08  lea     rcx, aExdiFailedRegi; "EXDI: Failed registering the EXDI COM S"...
0x1800bfd0f  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800bfd14  jmp     short loc_1800BFD69
0x1800bfd16  call    cs:__imp_GetLastError
0x1800bfd1d  nop     dword ptr [rax+rax+00h]
0x1800bfd22  mov     ebx, eax
0x1800bfd24  test    eax, eax
0x1800bfd26  jle     short loc_1800BFD31
0x1800bfd28  movzx   ebx, ax
0x1800bfd2b  or      ebx, 80070000h
0x1800bfd31  lea     rcx, aExdiGetprocadd; "EXDI: GetProcAddress-DllRegisterServer "...
0x1800bfd38  jmp     short loc_1800BFD5C
0x1800bfd3a  call    cs:__imp_GetLastError
0x1800bfd41  nop     dword ptr [rax+rax+00h]
0x1800bfd46  mov     ebx, eax
0x1800bfd48  test    eax, eax
0x1800bfd4a  jle     short loc_1800BFD55
0x1800bfd4c  movzx   ebx, ax
0x1800bfd4f  or      ebx, 80070000h
0x1800bfd55  lea     rcx, aExdiLoadlibrar; "EXDI: LoadLibraryExW failed loading the"...
0x1800bfd5c  mov     rdx, [rsi+8]
0x1800bfd60  mov     rdx, [rdx]
0x1800bfd63  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800bfd68  nop
0x1800bfd69  lea     rcx, [rsp+48h+arg_0]; this
0x1800bfd6e  call    ??1VersionQuery@@QEAA@XZ; VersionQuery::~VersionQuery(void)
0x1800bfd73  mov     eax, ebx
0x1800bfd75  mov     rbx, [rsp+48h+arg_8]
0x1800bfd7a  mov     rsi, [rsp+48h+arg_10]
0x1800bfd7f  add     rsp, 40h
0x1800bfd83  pop     rdi
0x1800bfd84  retn
```
