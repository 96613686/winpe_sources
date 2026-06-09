# CLONE_SYSPREP_MODULE::ExecuteModule(void)

- ea: `0x180025b94`
- end: `0x180025e95`
- name: `?ExecuteModule@CLONE_SYSPREP_MODULE@@QEAAKXZ`
- size: `769`
- prototype: `__int64 __fastcall(CLONE_SYSPREP_MODULE *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800258c0`
- `0x180025a74`

## callees

- `0x180025890`
- `0x180025b94`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025cfb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025c47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025c47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025bba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025bba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025e7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025e7d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025dce`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025e6f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025dce`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025e6f`
- `WDSCORE!CurrentIP` at `0x180025be2`
- `WDSCORE!CurrentIP` at `0x180025c6a`
- `WDSCORE!CurrentIP` at `0x180025d0d`
- `WDSCORE!CurrentIP` at `0x180025e06`
- `WDSCORE!CurrentIP` at `0x180025be2`
- `WDSCORE!CurrentIP` at `0x180025c6a`
- `WDSCORE!CurrentIP` at `0x180025d0d`
- `WDSCORE!CurrentIP` at `0x180025e06`

## string_xrefs

- `0x180025bf1`: `Failed to load DLL %ws (%lu)\n`
- `0x180025d71`: `Successfully executed method %hs in dll %ws\n`

## pseudocode

```c
__int64 __fastcall CLONE_SYSPREP_MODULE::ExecuteModule(CLONE_SYSPREP_MODULE *this)
{
  DWORD v2; // r14d
  HMODULE Library; // rax
  HMODULE v4; // r15
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  __int64 (*ProcAddress)(void); // rdi
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  unsigned int i; // ebx
  DWORD LastError; // edi
  __int64 v14; // rbx
  const char *v15; // r8
  struct tagLOG_PARTIAL_MSG *v16; // rax
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax

  v2 = 0;
  Library = LoadLibraryExW((LPCWSTR)this, 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)this + 520);
    if ( ProcAddress )
    {
      for ( i = 0; i < 3; ++i )
      {
        v2 = ProcAddress();
        if ( !v2 )
          break;
        if ( i != 2 )
          Sleep(30000 * (i + 1) * (i + 2));
      }
      LastError = GetLastError();
      v14 = CurrentIP();
      v15 = (char *)this + 520;
      if ( v2 )
      {
        v16 = ConstructPartialMsgW(0x2000000, "Failed to execute entry point %hs (%lu)\n", v15, v2);
        WdsSetupLogMessageW(
          v16,
          983040,
          L"D",
          0,
          335,
          L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
          L"CLONE_SYSPREP_MODULE::ExecuteModule",
          v14,
          LastError,
          0,
          0);
      }
      else
      {
        v17 = ConstructPartialMsgW(0x4000000, "Successfully executed method %hs in dll %ws\n", v15, this);
        WdsSetupLogMessageW(
          v17,
          983040,
          L"D",
          0,
          339,
          L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
          L"CLONE_SYSPREP_MODULE::ExecuteModule",
          v14,
          LastError,
          0,
          0);
      }
    }
    else
    {
      v2 = GetLastError();
      v9 = GetLastError();
      v10 = CurrentIP();
      v11 = ConstructPartialMsgW(0x2000000, "Failed to get entry point %hs (%lu)\n", (const char *)this + 520, v2);
      WdsSetupLogMessageW(
        v11,
        983040,
        L"D",
        0,
        306,
        L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
        L"CLONE_SYSPREP_MODULE::ExecuteModule",
        v10,
        v9,
        0,
        0);
    }
  }
  else
  {
    v2 = GetLastError();
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x2000000, "Failed to load DLL %ws (%lu)\n", this, v2);
    WdsSetupLogMessageW(
      v7,
      983040,
      L"D",
      0,
      296,
      L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
      L"CLONE_SYSPREP_MODULE::ExecuteModule",
      v6,
      v5,
      0,
      0);
  }
  if ( v2 == 574 )
  {
    v18 = GetLastError();
    v19 = CurrentIP();
    v20 = ConstructPartialMsgW(
            0x2000000,
            "Failed to execute entry point due to an unhandled exception: %hs (%lu)",
            (const char *)this + 520,
            574);
    WdsSetupLogMessageW(
      v20,
      983040,
      L"D",
      0,
      347,
      L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
      L"CLONE_SYSPREP_MODULE::ExecuteModule",
      v19,
      v18,
      0,
      0);
  }
  if ( v4 )
    FreeLibrary(v4);
  return v2;
}

```

## disassembly

```asm
0x180025b94  mov     [rsp+arg_0], rcx
0x180025b99  push    rbx
0x180025b9a  push    rdi
0x180025b9b  push    r12
0x180025b9d  push    r13
0x180025b9f  push    r14
0x180025ba1  push    r15
0x180025ba3  sub     rsp, 78h
0x180025ba7  mov     r13, rcx
0x180025baa  xor     r14d, r14d
0x180025bad  mov     [rsp+0A8h+var_40], r14
0x180025bb2  xor     edx, edx; hFile
0x180025bb4  mov     r8d, 800h; dwFlags
0x180025bba  call    cs:__imp_LoadLibraryExW
0x180025bc0  mov     r15, rax
0x180025bc3  mov     [rsp+0A8h+var_40], rax
0x180025bc8  test    rax, rax
0x180025bcb  jnz     short loc_180025C3A
0x180025bcd  call    cs:__imp_GetLastError
0x180025bd3  mov     r14d, eax
0x180025bd6  mov     [rsp+0A8h+var_48], eax
0x180025bda  call    cs:__imp_GetLastError
0x180025be0  mov     edi, eax
0x180025be2  call    cs:__imp_CurrentIP
0x180025be8  mov     rbx, rax
0x180025beb  mov     r9d, r14d
0x180025bee  mov     r8, r13
0x180025bf1  lea     rdx, aFailedToLoadDl; "Failed to load DLL %ws (%lu)\n"
0x180025bf8  mov     ecx, 2000000h; unsigned int
0x180025bfd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025c02  mov     [rsp+0A8h+var_58], r15d
0x180025c07  mov     [rsp+0A8h+var_60], r15
0x180025c0c  mov     [rsp+0A8h+var_68], edi
0x180025c10  mov     [rsp+0A8h+var_70], rbx
0x180025c15  lea     r12, aCloneSysprepMo_0; "CLONE_SYSPREP_MODULE::ExecuteModule"
0x180025c1c  mov     [rsp+0A8h+var_78], r12
0x180025c21  lea     rbx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025c28  mov     [rsp+0A8h+var_80], rbx
0x180025c2d  mov     [rsp+0A8h+var_88], 128h
0x180025c35  jmp     loc_180025DBC
0x180025c3a  lea     r12, [r13+208h]
0x180025c41  mov     rdx, r12; lpProcName
0x180025c44  mov     rcx, rax; hModule
0x180025c47  call    cs:__imp_GetProcAddress
0x180025c4d  mov     rdi, rax
0x180025c50  test    rax, rax
0x180025c53  jnz     short loc_180025CC9
0x180025c55  call    cs:__imp_GetLastError
0x180025c5b  mov     r14d, eax
0x180025c5e  mov     [rsp+0A8h+var_48], eax
0x180025c62  call    cs:__imp_GetLastError
0x180025c68  mov     edi, eax
0x180025c6a  call    cs:__imp_CurrentIP
0x180025c70  mov     rbx, rax
0x180025c73  mov     r9d, r14d
0x180025c76  mov     r8, r12
0x180025c79  lea     rdx, aFailedToGetEnt; "Failed to get entry point %hs (%lu)\n"
0x180025c80  mov     ecx, 2000000h; unsigned int
0x180025c85  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025c8a  mov     [rsp+0A8h+var_58], 0
0x180025c92  mov     [rsp+0A8h+var_60], 0
0x180025c9b  mov     [rsp+0A8h+var_68], edi
0x180025c9f  mov     [rsp+0A8h+var_70], rbx
0x180025ca4  lea     r12, aCloneSysprepMo_0; "CLONE_SYSPREP_MODULE::ExecuteModule"
0x180025cab  mov     [rsp+0A8h+var_78], r12
0x180025cb0  lea     rbx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025cb7  mov     [rsp+0A8h+var_80], rbx
0x180025cbc  mov     [rsp+0A8h+var_88], 132h
0x180025cc4  jmp     loc_180025DBC
0x180025cc9  xor     ebx, ebx
0x180025ccb  mov     [rsp+0A8h+var_44], ebx
0x180025ccf  cmp     ebx, 3
0x180025cd2  jnb     short loc_180025D05
0x180025cd4  mov     rax, rdi
0x180025cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cdc  mov     r14d, eax
0x180025cdf  mov     [rsp+0A8h+var_48], eax
0x180025ce3  test    eax, eax
0x180025ce5  jz      short loc_180025D05
0x180025ce7  cmp     ebx, 2
0x180025cea  jz      short loc_180025D01
0x180025cec  lea     ecx, [rbx+2]
0x180025cef  lea     eax, [rbx+1]
0x180025cf2  imul    ecx, eax
0x180025cf5  imul    ecx, 7530h; dwMilliseconds
0x180025cfb  call    cs:__imp_Sleep
0x180025d01  inc     ebx
0x180025d03  jmp     short loc_180025CCB
0x180025d05  call    cs:__imp_GetLastError
0x180025d0b  mov     edi, eax
0x180025d0d  call    cs:__imp_CurrentIP
0x180025d13  mov     rbx, rax
0x180025d16  mov     r8, r12
0x180025d19  test    r14d, r14d
0x180025d1c  jz      short loc_180025D6E
0x180025d1e  mov     r9d, r14d
0x180025d21  lea     rdx, aFailedToExecut; "Failed to execute entry point %hs (%lu)"...
0x180025d28  mov     ecx, 2000000h; unsigned int
0x180025d2d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025d32  mov     [rsp+0A8h+var_58], 0
0x180025d3a  mov     [rsp+0A8h+var_60], 0
0x180025d43  mov     [rsp+0A8h+var_68], edi
0x180025d47  mov     [rsp+0A8h+var_70], rbx
0x180025d4c  lea     r12, aCloneSysprepMo_0; "CLONE_SYSPREP_MODULE::ExecuteModule"
0x180025d53  mov     [rsp+0A8h+var_78], r12
0x180025d58  lea     rbx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025d5f  mov     [rsp+0A8h+var_80], rbx
0x180025d64  mov     [rsp+0A8h+var_88], 14Fh
0x180025d6c  jmp     short loc_180025DBC
0x180025d6e  mov     r9, r13
0x180025d71  lea     rdx, aSuccessfullyEx; "Successfully executed method %hs in dll"...
0x180025d78  mov     ecx, 4000000h; unsigned int
0x180025d7d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025d82  mov     [rsp+0A8h+var_58], 0
0x180025d8a  mov     [rsp+0A8h+var_60], 0
0x180025d93  mov     [rsp+0A8h+var_68], edi
0x180025d97  mov     [rsp+0A8h+var_70], rbx
0x180025d9c  lea     r12, aCloneSysprepMo_0; "CLONE_SYSPREP_MODULE::ExecuteModule"
0x180025da3  mov     [rsp+0A8h+var_78], r12
0x180025da8  lea     rbx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025daf  mov     [rsp+0A8h+var_80], rbx
0x180025db4  mov     [rsp+0A8h+var_88], 153h
0x180025dbc  xor     r9d, r9d
0x180025dbf  lea     r8, aD_0; "D"
0x180025dc6  mov     edx, 0F0000h
0x180025dcb  mov     rcx, rax
0x180025dce  call    cs:__imp_WdsSetupLogMessageW
0x180025dd4  jmp     short loc_180025DF5
0x180025dd6  mov     r14d, 23Eh
0x180025ddc  mov     [rsp+0A8h+var_48], r14d
0x180025de1  lea     r12, aCloneSysprepMo_0; "CLONE_SYSPREP_MODULE::ExecuteModule"
0x180025de8  mov     r13, [rsp+0A8h+arg_0]
0x180025df0  mov     r15, [rsp+0A8h+var_40]
0x180025df5  cmp     r14d, 23Eh
0x180025dfc  jnz     short loc_180025E75
0x180025dfe  call    cs:__imp_GetLastError
0x180025e04  mov     edi, eax
0x180025e06  call    cs:__imp_CurrentIP
0x180025e0c  mov     rbx, rax
0x180025e0f  lea     r8, [r13+208h]
0x180025e16  mov     r9d, r14d
0x180025e19  lea     rdx, aFailedToExecut_0; "Failed to execute entry point due to an"...
0x180025e20  mov     ecx, 2000000h; unsigned int
0x180025e25  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025e2a  mov     [rsp+0A8h+var_58], 0
0x180025e32  mov     [rsp+0A8h+var_60], 0
0x180025e3b  mov     [rsp+0A8h+var_68], edi
0x180025e3f  mov     [rsp+0A8h+var_70], rbx
0x180025e44  mov     [rsp+0A8h+var_78], r12
0x180025e49  lea     rcx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025e50  mov     [rsp+0A8h+var_80], rcx
0x180025e55  mov     [rsp+0A8h+var_88], 15Bh
0x180025e5d  xor     r9d, r9d
0x180025e60  lea     r8, aD_0; "D"
0x180025e67  mov     edx, 0F0000h
0x180025e6c  mov     rcx, rax
0x180025e6f  call    cs:__imp_WdsSetupLogMessageW
0x180025e75  test    r15, r15
0x180025e78  jz      short loc_180025E83
0x180025e7a  mov     rcx, r15; hLibModule
0x180025e7d  call    cs:__imp_FreeLibrary
0x180025e83  mov     eax, r14d
0x180025e86  add     rsp, 78h
0x180025e8a  pop     r15
0x180025e8c  pop     r14
0x180025e8e  pop     r13
0x180025e90  pop     r12
0x180025e92  pop     rdi
0x180025e93  pop     rbx
0x180025e94  retn
```
