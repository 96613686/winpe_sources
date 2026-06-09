# _PublishIASIdInSharedMemory

- ea: `0x18004fda8`
- end: `0x18004ff26`
- name: `_PublishIASIdInSharedMemory`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callers

- `0x18004b990`

## callees

- `0x180018410`
- `0x180025c18`
- `0x180031b30`
- `0x18004fda8`
- `0x18004ff2c`
- `0x180050060`
- `0x18005e8e4`
- `0x18005f4e0`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fe2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fe2d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18004fec6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18004fec6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004fe10`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004fe10`

## string_xrefs

- `0x18004fe5e`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x18004fe92`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x18004fee5`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`

## pseudocode

```c
_OWORD *__fastcall PublishIASIdInSharedMemory(_OWORD *a1, int a2)
{
  _OWORD *result; // rax
  HANDLE FileMappingW; // rdi
  DWORD LastError; // eax
  unsigned int v7; // ebx
  int v8; // ebx
  int v9; // eax
  _OWORD *v10; // rbx
  int dwMaximumSizeLow; // [rsp+20h] [rbp-168h]
  int dwMaximumSizeLowa; // [rsp+20h] [rbp-168h]
  WCHAR Name[160]; // [rsp+30h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  IEConfiguration_GetBool(553648152);
  result = (_OWORD *)TryGetImmutableApplicationStateId(a2);
  if ( !(_BYTE)result )
    return result;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x10u, Name);
  LastError = GetLastError();
  v7 = LastError;
  if ( !FileMappingW )
    goto LABEL_5;
  if ( LastError )
  {
    CloseHandle(FileMappingW);
LABEL_5:
    FileMappingW = 0;
    v8 = HRESULTFromWin32ErrorError(v7);
    if ( v8 == -2147024713 )
      CollectFileMappingDiagnostics(1, Name);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)v8,
        dwMaximumSizeLow);
  }
  v9 = SetWindowsHandleAccess(FileMappingW, 0x2110Fu, 0x80000005);
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
      (const char *)(unsigned int)v9,
      dwMaximumSizeLow);
  result = MapViewOfFileEx(FileMappingW, 2u, 0, 0, 0x10u, 0);
  v10 = result;
  if ( !result )
  {
    result = (_OWORD *)HRESULTFromLastErrorError();
    if ( (int)result < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)result,
        dwMaximumSizeLowa);
  }
  *v10 = *a1;
  return result;
}

```

## disassembly

```asm
0x18004fda8  mov     [rsp+arg_0], rbx
0x18004fdad  mov     [rsp+arg_10], rsi
0x18004fdb2  push    rdi
0x18004fdb3  sub     rsp, 180h
0x18004fdba  mov     rax, cs:__security_cookie
0x18004fdc1  xor     rax, rsp
0x18004fdc4  mov     [rsp+188h+var_18], rax
0x18004fdcc  mov     rsi, rcx
0x18004fdcf  mov     ebx, edx
0x18004fdd1  mov     ecx, 21000018h
0x18004fdd6  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004fddb  lea     r8, [rsp+188h+Name]
0x18004fde0  mov     dl, al
0x18004fde2  mov     ecx, ebx
0x18004fde4  call    _TryGetImmutableApplicationStateId
0x18004fde9  test    al, al
0x18004fdeb  jz      loc_18004FF01
0x18004fdf1  xor     r9d, r9d; dwMaximumSizeHigh
0x18004fdf4  lea     rax, [rsp+188h+Name]
0x18004fdf9  mov     [rsp+188h+lpName], rax; lpName
0x18004fdfe  xor     edx, edx; lpFileMappingAttributes
0x18004fe00  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004fe04  mov     [rsp+188h+dwMaximumSizeLow], 10h; int
0x18004fe0c  lea     r8d, [r9+4]; flProtect
0x18004fe10  call    cs:__imp_CreateFileMappingW
0x18004fe16  mov     rdi, rax
0x18004fe19  call    cs:__imp_GetLastError
0x18004fe1f  mov     ebx, eax
0x18004fe21  test    rdi, rdi
0x18004fe24  jz      short loc_18004FE33
0x18004fe26  test    eax, eax
0x18004fe28  jz      short loc_18004FE73
0x18004fe2a  mov     rcx, rdi; hObject
0x18004fe2d  call    cs:__imp_CloseHandle
0x18004fe33  mov     ecx, ebx; unsigned int
0x18004fe35  xor     edi, edi
0x18004fe37  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x18004fe3c  mov     ebx, eax
0x18004fe3e  cmp     eax, 800700B7h
0x18004fe43  jnz     short loc_18004FE52
0x18004fe45  lea     rdx, [rsp+188h+Name]
0x18004fe4a  lea     ecx, [rdi+1]
0x18004fe4d  call    ?CollectFileMappingDiagnostics@@YAXW4FileMappingFailure@@PEBG@Z; CollectFileMappingDiagnostics(FileMappingFailure,ushort const *)
0x18004fe52  test    ebx, ebx
0x18004fe54  jns     short loc_18004FE73
0x18004fe56  mov     rcx, [rsp+188h]; this
0x18004fe5e  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x18004fe65  mov     r9d, ebx; char *
0x18004fe68  mov     edx, 189h; void *
0x18004fe6d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18004fe73  mov     edx, 2110Fh; unsigned int
0x18004fe78  mov     r8d, 80000005h; unsigned int
0x18004fe7e  mov     rcx, rdi; void *
0x18004fe81  call    ?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18004fe86  test    eax, eax
0x18004fe88  jns     short loc_18004FEA7
0x18004fe8a  mov     rcx, [rsp+188h]; this
0x18004fe92  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x18004fe99  mov     r9d, eax; char *
0x18004fe9c  mov     edx, 18Bh; void *
0x18004fea1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18004fea7  xor     r9d, r9d; dwFileOffsetLow
0x18004feaa  mov     [rsp+188h+lpName], 0; lpBaseAddress
0x18004feb3  xor     r8d, r8d; dwFileOffsetHigh
0x18004feb6  mov     qword ptr [rsp+188h+dwMaximumSizeLow], 10h; int
0x18004febf  mov     rcx, rdi; hFileMappingObject
0x18004fec2  lea     edx, [r9+2]; dwDesiredAccess
0x18004fec6  call    cs:__imp_MapViewOfFileEx
0x18004fecc  mov     rbx, rax
0x18004fecf  test    rax, rax
0x18004fed2  jnz     short loc_18004FEFA
0x18004fed4  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18004fed9  test    eax, eax
0x18004fedb  jns     short loc_18004FEFA
0x18004fedd  mov     rcx, [rsp+188h]; this
0x18004fee5  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x18004feec  mov     r9d, eax; char *
0x18004feef  mov     edx, 18Eh; void *
0x18004fef4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18004fefa  movups  xmm0, xmmword ptr [rsi]
0x18004fefd  movdqu  xmmword ptr [rbx], xmm0
0x18004ff01  mov     rcx, [rsp+188h+var_18]
0x18004ff09  xor     rcx, rsp; StackCookie
0x18004ff0c  call    __security_check_cookie
0x18004ff11  lea     r11, [rsp+188h+var_8]
0x18004ff19  mov     rbx, [r11+10h]
0x18004ff1d  mov     rsi, [r11+20h]
0x18004ff21  mov     rsp, r11
0x18004ff24  pop     rdi
0x18004ff25  retn
```
