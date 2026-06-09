# RdpEdpPolicyManager::InitializeInstance(void)

- ea: `0x140060438`
- end: `0x140060540`
- name: `?InitializeInstance@RdpEdpPolicyManager@@AEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(RdpEdpPolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400600a8`

## callees

- `0x1400577e8`
- `0x140060438`
- `0x140060ae0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140060469`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400604c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140060469`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400604c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400604d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400604d6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14006044b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400604ac`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14006044b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400604ac`

## string_xrefs

- `0x140060444`: `ole32.dll`
- `0x1400604a5`: `srpapi.dll`
- `0x140060516`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`

## pseudocode

```c
__int64 __fastcall RdpEdpPolicyManager::InitializeInstance(RdpEdpPolicyManager *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  signed int v5; // ebx
  const wchar_t *pszFormat; // rax
  int v7; // r8d
  HMODULE v8; // rax
  FARPROC v9; // rax
  signed int v10; // eax

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
      pszFormat = L"EnterpriseClipboardApi::Initialize failed. hr[0x%x]";
      v7 = 187;
LABEL_13:
      TRC_TraceBufferW(
        3,
        512,
        v7,
        (int)L"RdpEdpPolicyManager::InitializeInstance",
        (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        pszFormat,
        v5);
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
      pszFormat = L"RdpEdpSrpApi::Initialize failed. hr[0x%x]";
      v7 = 193;
      goto LABEL_13;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140060438  push    rbx
0x14006043a  push    rbp
0x14006043b  push    rsi
0x14006043c  push    rdi
0x14006043d  sub     rsp, 48h
0x140060441  mov     rsi, rcx
0x140060444  lea     rcx, aOle32Dll_0; "ole32.dll"
0x14006044b  call    cs:__imp_LoadLibraryW
0x140060451  mov     [rsi+38h], rax
0x140060455  mov     ebp, 80070000h
0x14006045a  test    rax, rax
0x14006045d  jz      short loc_140060478
0x14006045f  lea     rdx, aOlegetclipboar_0; "OleGetClipboardWithEnterpriseInfo"
0x140060466  mov     rcx, rax; hModule
0x140060469  call    cs:__imp_GetProcAddress
0x14006046f  mov     [rsi+30h], rax
0x140060473  test    rax, rax
0x140060476  jnz     short loc_1400604A5
0x140060478  call    cs:__imp_GetLastError
0x14006047e  mov     ebx, eax
0x140060480  test    eax, eax
0x140060482  jle     short loc_140060489
0x140060484  movzx   ebx, ax
0x140060487  or      ebx, ebp
0x140060489  test    ebx, ebx
0x14006048b  jns     short loc_1400604A5
0x14006048d  lea     rcx, [rsi+30h]; this
0x140060491  call    ?Terminate@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Terminate(void)
0x140060496  lea     rax, aEnterpriseclip; "EnterpriseClipboardApi::Initialize fail"...
0x14006049d  mov     r8d, 0BBh
0x1400604a3  jmp     short loc_140060501
0x1400604a5  lea     rcx, aSrpapiDll; "srpapi.dll"
0x1400604ac  call    cs:__imp_LoadLibraryW
0x1400604b2  mov     [rsi+48h], rax
0x1400604b6  test    rax, rax
0x1400604b9  jz      short loc_1400604D6
0x1400604bb  lea     rdx, aSrpgetenterpri; "SrpGetEnterpriseIds"
0x1400604c2  mov     rcx, rax; hModule
0x1400604c5  xor     ebx, ebx
0x1400604c7  call    cs:__imp_GetProcAddress
0x1400604cd  mov     [rsi+40h], rax
0x1400604d1  test    rax, rax
0x1400604d4  jnz     short loc_140060535
0x1400604d6  call    cs:__imp_GetLastError
0x1400604dc  mov     ebx, eax
0x1400604de  test    eax, eax
0x1400604e0  jle     short loc_1400604E7
0x1400604e2  movzx   ebx, ax
0x1400604e5  or      ebx, ebp
0x1400604e7  test    ebx, ebx
0x1400604e9  jns     short loc_140060535
0x1400604eb  lea     rcx, [rsi+40h]; this
0x1400604ef  call    ?Terminate@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Terminate(void)
0x1400604f4  lea     rax, aRdpedpsrpapiIn; "RdpEdpSrpApi::Initialize failed. hr[0x%"...
0x1400604fb  mov     r8d, 0C1h; int
0x140060501  mov     dword ptr [rsp+68h+var_30], ebx; char
0x140060505  lea     r9, aRdpedppolicyma_4; "RdpEdpPolicyManager::InitializeInstance"
0x14006050c  mov     [rsp+68h+pszFormat], rax; pszFormat
0x140060511  mov     edx, 200h; int
0x140060516  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x14006051d  mov     qword ptr [rsp+68h+var_40], 0; int
0x140060526  mov     ecx, 3; int
0x14006052b  mov     qword ptr [rsp+68h+var_48], rax; int
0x140060530  call    TRC_TraceBufferW
0x140060535  mov     eax, ebx
0x140060537  add     rsp, 48h
0x14006053b  pop     rdi
0x14006053c  pop     rsi
0x14006053d  pop     rbp
0x14006053e  pop     rbx
0x14006053f  retn
```
