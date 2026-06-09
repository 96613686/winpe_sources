# RdpEdpPolicyManager::InitializeInstance(void)

- ea: `0x140098394`
- end: `0x14009849c`
- name: `?InitializeInstance@RdpEdpPolicyManager@@AEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(RdpEdpPolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140098180`

## callees

- `0x140098394`
- `0x1400986fc`
- `0x140109c18`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400983a7`
- `KERNEL32!LoadLibraryW` at `0x140098408`
- `KERNEL32!LoadLibraryW` at `0x1400983a7`
- `KERNEL32!LoadLibraryW` at `0x140098408`
- `KERNEL32!GetProcAddress` at `0x1400983c5`
- `KERNEL32!GetProcAddress` at `0x140098423`
- `KERNEL32!GetProcAddress` at `0x1400983c5`
- `KERNEL32!GetProcAddress` at `0x140098423`
- `KERNEL32!GetLastError` at `0x1400983d4`
- `KERNEL32!GetLastError` at `0x140098432`
- `KERNEL32!GetLastError` at `0x1400983d4`
- `KERNEL32!GetLastError` at `0x140098432`

## string_xrefs

- `0x1400983a0`: `ole32.dll`
- `0x140098472`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x140098401`: `srpapi.dll`

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
      RdpEdpSrpApi::Terminate((RdpEdpPolicyManager *)((char *)this + 48));
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
      RdpEdpSrpApi::Terminate((RdpEdpPolicyManager *)((char *)this + 64));
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
0x140098394  push    rbx
0x140098396  push    rbp
0x140098397  push    rsi
0x140098398  push    rdi
0x140098399  sub     rsp, 48h
0x14009839d  mov     rsi, rcx
0x1400983a0  lea     rcx, aOle32Dll_0; "ole32.dll"
0x1400983a7  call    cs:__imp_LoadLibraryW
0x1400983ad  mov     [rsi+38h], rax
0x1400983b1  mov     ebp, 80070000h
0x1400983b6  test    rax, rax
0x1400983b9  jz      short loc_1400983D4
0x1400983bb  lea     rdx, aOlegetclipboar; "OleGetClipboardWithEnterpriseInfo"
0x1400983c2  mov     rcx, rax; hModule
0x1400983c5  call    cs:__imp_GetProcAddress
0x1400983cb  mov     [rsi+30h], rax
0x1400983cf  test    rax, rax
0x1400983d2  jnz     short loc_140098401
0x1400983d4  call    cs:__imp_GetLastError
0x1400983da  mov     ebx, eax
0x1400983dc  test    eax, eax
0x1400983de  jle     short loc_1400983E5
0x1400983e0  movzx   ebx, ax
0x1400983e3  or      ebx, ebp
0x1400983e5  test    ebx, ebx
0x1400983e7  jns     short loc_140098401
0x1400983e9  lea     rcx, [rsi+30h]; this
0x1400983ed  call    ?Terminate@RdpEdpSrpApi@@AEAAJXZ; RdpEdpSrpApi::Terminate(void)
0x1400983f2  lea     rax, aEnterpriseclip; "EnterpriseClipboardApi::Initialize fail"...
0x1400983f9  mov     r8d, 0BBh
0x1400983ff  jmp     short loc_14009845D
0x140098401  lea     rcx, aSrpapiDll; "srpapi.dll"
0x140098408  call    cs:__imp_LoadLibraryW
0x14009840e  mov     [rsi+48h], rax
0x140098412  test    rax, rax
0x140098415  jz      short loc_140098432
0x140098417  lea     rdx, aSrpgetenterpri_0; "SrpGetEnterpriseIds"
0x14009841e  mov     rcx, rax; hModule
0x140098421  xor     ebx, ebx
0x140098423  call    cs:__imp_GetProcAddress
0x140098429  mov     [rsi+40h], rax
0x14009842d  test    rax, rax
0x140098430  jnz     short loc_140098491
0x140098432  call    cs:__imp_GetLastError
0x140098438  mov     ebx, eax
0x14009843a  test    eax, eax
0x14009843c  jle     short loc_140098443
0x14009843e  movzx   ebx, ax
0x140098441  or      ebx, ebp
0x140098443  test    ebx, ebx
0x140098445  jns     short loc_140098491
0x140098447  lea     rcx, [rsi+40h]; this
0x14009844b  call    ?Terminate@RdpEdpSrpApi@@AEAAJXZ; RdpEdpSrpApi::Terminate(void)
0x140098450  lea     rax, aRdpedpsrpapiIn; "RdpEdpSrpApi::Initialize failed. hr[0x%"...
0x140098457  mov     r8d, 0C1h; int
0x14009845d  mov     dword ptr [rsp+68h+var_30], ebx; char
0x140098461  lea     r9, aRdpedppolicyma_4; "RdpEdpPolicyManager::InitializeInstance"
0x140098468  mov     [rsp+68h+pszFormat], rax; pszFormat
0x14009846d  mov     edx, 200h; int
0x140098472  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x140098479  mov     qword ptr [rsp+68h+var_40], 0; int
0x140098482  mov     ecx, 3; int
0x140098487  mov     qword ptr [rsp+68h+var_48], rax; int
0x14009848c  call    TRC_TraceBufferW
0x140098491  mov     eax, ebx
0x140098493  add     rsp, 48h
0x140098497  pop     rdi
0x140098498  pop     rsi
0x140098499  pop     rbp
0x14009849a  pop     rbx
0x14009849b  retn
```
