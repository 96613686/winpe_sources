# DeletePrinterDevNode(ushort *)

- ea: `0x18009bc10`
- end: `0x18009bd77`
- name: `?DeletePrinterDevNode@@YAHPEAG@Z`
- size: `359`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180054c98`

## callees

- `0x18003ea2c`
- `0x180046650`
- `0x18009bc10`
- `0x18009bd80`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009bd4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009bd4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bd2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bd2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009bcca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009bcec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009bcca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009bcec`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009bc68`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009bc68`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009bd21`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009bd21`

## string_xrefs

- `0x18009bd34`: `ImpersonatePrinterClient Failed. Error %d`
- `0x18009bcff`: `SetupInfo.pfnRemoveDevice failed. Error %d`
- `0x18009bd06`: `DeletePrinterDevNode`
- `0x18009bd3b`: `DeletePrinterDevNode`

## pseudocode

```c
__int64 __fastcall DeletePrinterDevNode(unsigned __int16 *a1)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  HANDLE v4; // r14
  __int64 v5; // rdi
  DWORD LastError; // eax
  DWORD v7; // eax
  HMODULE hLibModule[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v9; // [rsp+40h] [rbp-40h]
  unsigned int (__fastcall *v10)(__int64, unsigned __int16 *, __int64, _QWORD, _OWORD *); // [rsp+50h] [rbp-30h]
  _OWORD v11[2]; // [rsp+58h] [rbp-28h] BYREF

  v10 = 0;
  memset(v11, 0, sizeof(v11));
  *(_OWORD *)hLibModule = 0;
  v9 = 0;
  result = LoadSetupApiDll((struct _SETUPAPI_INFO *)hLibModule);
  if ( (_DWORD)result )
  {
    v3 = 0;
    v4 = RevertToPrinterSelf();
    v5 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, _QWORD))v9)(&GUID_DEVCLASS_PRINTER, 0, -1, 0);
    if ( v5 != -1 )
    {
      LODWORD(v11[0]) = 32;
      if ( v10(v5, a1, -1, 0, v11) )
      {
        v3 = SetThreadToken(0, g_hOriginalProcessToken);
        if ( !v3 || (v3 = (*((__int64 (__fastcall **)(__int64, _OWORD *))&v9 + 1))(v5, v11), SetThreadToken(0, 0), !v3) )
        {
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "DeletePrinterDevNode",
            L"SetupInfo.pfnRemoveDevice failed. Error %d",
            LastError);
        }
      }
      ((void (__fastcall *)(__int64))hLibModule[1])(v5);
    }
    if ( !ImpersonatePrinterClient(v4) )
    {
      v7 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "DeletePrinterDevNode",
        L"ImpersonatePrinterClient Failed. Error %d",
        v7);
    }
    FreeLibrary(hLibModule[0]);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18009bc10  mov     [rsp-18h+arg_8], rbx
0x18009bc15  mov     [rsp-18h+arg_10], rsi
0x18009bc1a  push    rbp
0x18009bc1b  push    rdi
0x18009bc1c  push    r14
0x18009bc1e  mov     rbp, rsp
0x18009bc21  sub     rsp, 80h
0x18009bc28  mov     rax, cs:__security_cookie
0x18009bc2f  xor     rax, rsp
0x18009bc32  mov     [rbp+var_8], rax
0x18009bc36  xorps   xmm0, xmm0
0x18009bc39  xorps   xmm1, xmm1
0x18009bc3c  mov     rsi, rcx
0x18009bc3f  xor     eax, eax
0x18009bc41  lea     rcx, [rbp+hLibModule]; struct _SETUPAPI_INFO *
0x18009bc45  mov     [rbp+var_30], rax
0x18009bc49  movups  [rbp+var_28], xmm0
0x18009bc4d  movups  [rbp+var_18], xmm0
0x18009bc51  movups  xmmword ptr [rbp+hLibModule], xmm1
0x18009bc55  movups  [rbp+var_40], xmm1
0x18009bc59  call    ?LoadSetupApiDll@@YAHPEAU_SETUPAPI_INFO@@@Z; LoadSetupApiDll(_SETUPAPI_INFO *)
0x18009bc5e  test    eax, eax
0x18009bc60  jz      loc_18009BD53
0x18009bc66  xor     ebx, ebx
0x18009bc68  call    cs:__imp_RevertToPrinterSelf
0x18009bc6e  xor     r9d, r9d
0x18009bc71  lea     rcx, GUID_DEVCLASS_PRINTER
0x18009bc78  mov     r14, rax
0x18009bc7b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009bc7f  mov     rax, qword ptr [rbp+var_40]
0x18009bc83  xor     edx, edx
0x18009bc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bc8a  mov     rdi, rax
0x18009bc8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009bc91  jz      loc_18009BD1E
0x18009bc97  lea     rax, [rbp+var_28]
0x18009bc9b  mov     dword ptr [rbp+var_28], 20h ; ' '
0x18009bca2  mov     [rsp+80h+var_60], rax
0x18009bca7  xor     r9d, r9d
0x18009bcaa  mov     rax, [rbp+var_30]
0x18009bcae  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009bcb2  mov     rdx, rsi
0x18009bcb5  mov     rcx, rdi
0x18009bcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bcbd  test    eax, eax
0x18009bcbf  jz      short loc_18009BD12
0x18009bcc1  mov     rdx, cs:?g_hOriginalProcessToken@@3PEAXEA; Token
0x18009bcc8  xor     ecx, ecx; Thread
0x18009bcca  call    cs:__imp_SetThreadToken
0x18009bcd0  mov     ebx, eax
0x18009bcd2  test    eax, eax
0x18009bcd4  jz      short loc_18009BCF6
0x18009bcd6  mov     rax, qword ptr [rbp+var_40+8]
0x18009bcda  lea     rdx, [rbp+var_28]
0x18009bcde  mov     rcx, rdi
0x18009bce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bce6  xor     edx, edx; Token
0x18009bce8  xor     ecx, ecx; Thread
0x18009bcea  mov     ebx, eax
0x18009bcec  call    cs:__imp_SetThreadToken
0x18009bcf2  test    ebx, ebx
0x18009bcf4  jnz     short loc_18009BD12
0x18009bcf6  call    cs:__imp_GetLastError
0x18009bcfc  mov     r8d, eax
0x18009bcff  lea     rdx, aSetupinfoPfnre; "SetupInfo.pfnRemoveDevice failed. Error"...
0x18009bd06  lea     rcx, aDeleteprinterd; "DeletePrinterDevNode"
0x18009bd0d  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009bd12  mov     rax, [rbp+hLibModule+8]
0x18009bd16  mov     rcx, rdi
0x18009bd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bd1e  mov     rcx, r14; hToken
0x18009bd21  call    cs:__imp_ImpersonatePrinterClient
0x18009bd27  test    eax, eax
0x18009bd29  jnz     short loc_18009BD47
0x18009bd2b  call    cs:__imp_GetLastError
0x18009bd31  mov     r8d, eax
0x18009bd34  lea     rdx, aImpersonatepri_2; "ImpersonatePrinterClient Failed. Error "...
0x18009bd3b  lea     rcx, aDeleteprinterd; "DeletePrinterDevNode"
0x18009bd42  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009bd47  mov     rcx, [rbp+hLibModule]; hLibModule
0x18009bd4b  call    cs:__imp_FreeLibrary
0x18009bd51  mov     eax, ebx
0x18009bd53  mov     rcx, [rbp+var_8]
0x18009bd57  xor     rcx, rsp; StackCookie
0x18009bd5a  call    __security_check_cookie
0x18009bd5f  lea     r11, [rsp+80h+var_s0]
0x18009bd67  mov     rbx, [r11+28h]
0x18009bd6b  mov     rsi, [r11+30h]
0x18009bd6f  mov     rsp, r11
0x18009bd72  pop     r14
0x18009bd74  pop     rdi
0x18009bd75  pop     rbp
0x18009bd76  retn
```
