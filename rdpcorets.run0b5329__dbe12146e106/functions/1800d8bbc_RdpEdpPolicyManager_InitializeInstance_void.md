# RdpEdpPolicyManager::InitializeInstance(void)

- ea: `0x1800d8bbc`
- end: `0x1800d8cc5`
- name: `?InitializeInstance@RdpEdpPolicyManager@@AEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(RdpEdpPolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d8838`

## callees

- `0x1800d6510`
- `0x1800d8bbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d8bed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d8c4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d8bed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d8c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8c5a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d8bcf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d8c30`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d8bcf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d8c30`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8cb4`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8cb4`

## string_xrefs

- `0x1800d8bc8`: `ole32.dll`
- `0x1800d8c9a`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1800d8c29`: `srpapi.dll`

## pseudocode

```c
__int64 __fastcall RdpEdpPolicyManager::InitializeInstance(RdpEdpPolicyManager *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  signed int v5; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r8
  HMODULE v8; // rax
  FARPROC v9; // rax
  signed int v10; // eax
  signed int v12; // [rsp+38h] [rbp-30h]

  LibraryW = LoadLibraryW(L"ole32.dll");
  *((_QWORD *)this + 7) = LibraryW;
  if ( !LibraryW
    || (ProcAddress = GetProcAddress(LibraryW, "OleGetClipboardWithEnterpriseInfo"),
        (*((_QWORD *)this + 6) = ProcAddress) == 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      CLegacyClipboardApi::Terminate((RdpEdpPolicyManager *)((char *)this + 48));
      v6 = L"EnterpriseClipboardApi::Initialize failed. hr[0x%x]";
      v7 = 187;
LABEL_13:
      v12 = v5;
      TRC_TraceBufferW(
        3,
        512,
        v7,
        L"RdpEdpPolicyManager::InitializeInstance",
        L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        v6,
        v12);
      return (unsigned int)v5;
    }
  }
  v8 = LoadLibraryW(L"srpapi.dll");
  *((_QWORD *)this + 9) = v8;
  if ( !v8 || (v5 = 0, v9 = GetProcAddress(v8, "SrpGetEnterpriseIds"), (*((_QWORD *)this + 8) = v9) == 0) )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
    {
      CLegacyClipboardApi::Terminate((RdpEdpPolicyManager *)((char *)this + 64));
      v6 = L"RdpEdpSrpApi::Initialize failed. hr[0x%x]";
      v7 = 193;
      goto LABEL_13;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d8bbc  push    rbx
0x1800d8bbe  push    rbp
0x1800d8bbf  push    rsi
0x1800d8bc0  push    rdi
0x1800d8bc1  sub     rsp, 48h
0x1800d8bc5  mov     rsi, rcx
0x1800d8bc8  lea     rcx, aOle32Dll_0; "ole32.dll"
0x1800d8bcf  call    cs:__imp_LoadLibraryW
0x1800d8bd5  mov     [rsi+38h], rax
0x1800d8bd9  mov     ebp, 80070000h
0x1800d8bde  test    rax, rax
0x1800d8be1  jz      short loc_1800D8BFC
0x1800d8be3  lea     rdx, aOlegetclipboar_0; "OleGetClipboardWithEnterpriseInfo"
0x1800d8bea  mov     rcx, rax; hModule
0x1800d8bed  call    cs:__imp_GetProcAddress
0x1800d8bf3  mov     [rsi+30h], rax
0x1800d8bf7  test    rax, rax
0x1800d8bfa  jnz     short loc_1800D8C29
0x1800d8bfc  call    cs:__imp_GetLastError
0x1800d8c02  mov     ebx, eax
0x1800d8c04  test    eax, eax
0x1800d8c06  jle     short loc_1800D8C0D
0x1800d8c08  movzx   ebx, ax
0x1800d8c0b  or      ebx, ebp
0x1800d8c0d  test    ebx, ebx
0x1800d8c0f  jns     short loc_1800D8C29
0x1800d8c11  lea     rcx, [rsi+30h]; this
0x1800d8c15  call    ?Terminate@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Terminate(void)
0x1800d8c1a  lea     rax, aEnterpriseclip; "EnterpriseClipboardApi::Initialize fail"...
0x1800d8c21  mov     r8d, 0BBh
0x1800d8c27  jmp     short loc_1800D8C85
0x1800d8c29  lea     rcx, aSrpapiDll; "srpapi.dll"
0x1800d8c30  call    cs:__imp_LoadLibraryW
0x1800d8c36  mov     [rsi+48h], rax
0x1800d8c3a  test    rax, rax
0x1800d8c3d  jz      short loc_1800D8C5A
0x1800d8c3f  lea     rdx, aSrpgetenterpri; "SrpGetEnterpriseIds"
0x1800d8c46  mov     rcx, rax; hModule
0x1800d8c49  xor     ebx, ebx
0x1800d8c4b  call    cs:__imp_GetProcAddress
0x1800d8c51  mov     [rsi+40h], rax
0x1800d8c55  test    rax, rax
0x1800d8c58  jnz     short loc_1800D8CBA
0x1800d8c5a  call    cs:__imp_GetLastError
0x1800d8c60  mov     ebx, eax
0x1800d8c62  test    eax, eax
0x1800d8c64  jle     short loc_1800D8C6B
0x1800d8c66  movzx   ebx, ax
0x1800d8c69  or      ebx, ebp
0x1800d8c6b  test    ebx, ebx
0x1800d8c6d  jns     short loc_1800D8CBA
0x1800d8c6f  lea     rcx, [rsi+40h]; this
0x1800d8c73  call    ?Terminate@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Terminate(void)
0x1800d8c78  lea     rax, aRdpedpsrpapiIn; "RdpEdpSrpApi::Initialize failed. hr[0x%"...
0x1800d8c7f  mov     r8d, 0C1h
0x1800d8c85  mov     [rsp+68h+var_30], ebx
0x1800d8c89  lea     r9, aRdpedppolicyma_4; "RdpEdpPolicyManager::InitializeInstance"
0x1800d8c90  mov     [rsp+68h+var_38], rax
0x1800d8c95  mov     edx, 200h
0x1800d8c9a  lea     rax, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1800d8ca1  mov     [rsp+68h+var_40], 0
0x1800d8caa  mov     ecx, 3
0x1800d8caf  mov     [rsp+68h+var_48], rax
0x1800d8cb4  call    cs:__imp_TRC_TraceBufferW
0x1800d8cba  mov     eax, ebx
0x1800d8cbc  add     rsp, 48h
0x1800d8cc0  pop     rdi
0x1800d8cc1  pop     rsi
0x1800d8cc2  pop     rbp
0x1800d8cc3  pop     rbx
0x1800d8cc4  retn
```
