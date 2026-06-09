# RdpEdpPolicyManager::InitializeInstance(void)

- ea: `0x140096224`
- end: `0x14009632c`
- name: `?InitializeInstance@RdpEdpPolicyManager@@AEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(RdpEdpPolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140096010`

## callees

- `0x140096224`
- `0x14009658c`
- `0x140107aa8`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140096237`
- `KERNEL32!LoadLibraryW` at `0x140096298`
- `KERNEL32!LoadLibraryW` at `0x140096237`
- `KERNEL32!LoadLibraryW` at `0x140096298`
- `KERNEL32!GetProcAddress` at `0x140096255`
- `KERNEL32!GetProcAddress` at `0x1400962b3`
- `KERNEL32!GetProcAddress` at `0x140096255`
- `KERNEL32!GetProcAddress` at `0x1400962b3`
- `KERNEL32!GetLastError` at `0x140096264`
- `KERNEL32!GetLastError` at `0x1400962c2`
- `KERNEL32!GetLastError` at `0x140096264`
- `KERNEL32!GetLastError` at `0x1400962c2`

## string_xrefs

- `0x140096230`: `ole32.dll`
- `0x140096291`: `srpapi.dll`
- `0x140096302`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`

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
0x140096224  push    rbx
0x140096226  push    rbp
0x140096227  push    rsi
0x140096228  push    rdi
0x140096229  sub     rsp, 48h
0x14009622d  mov     rsi, rcx
0x140096230  lea     rcx, aOle32Dll_0; "ole32.dll"
0x140096237  call    cs:__imp_LoadLibraryW
0x14009623d  mov     [rsi+38h], rax
0x140096241  mov     ebp, 80070000h
0x140096246  test    rax, rax
0x140096249  jz      short loc_140096264
0x14009624b  lea     rdx, aOlegetclipboar; "OleGetClipboardWithEnterpriseInfo"
0x140096252  mov     rcx, rax; hModule
0x140096255  call    cs:__imp_GetProcAddress
0x14009625b  mov     [rsi+30h], rax
0x14009625f  test    rax, rax
0x140096262  jnz     short loc_140096291
0x140096264  call    cs:__imp_GetLastError
0x14009626a  mov     ebx, eax
0x14009626c  test    eax, eax
0x14009626e  jle     short loc_140096275
0x140096270  movzx   ebx, ax
0x140096273  or      ebx, ebp
0x140096275  test    ebx, ebx
0x140096277  jns     short loc_140096291
0x140096279  lea     rcx, [rsi+30h]; this
0x14009627d  call    ?Terminate@RdpEdpSrpApi@@AEAAJXZ; RdpEdpSrpApi::Terminate(void)
0x140096282  lea     rax, aEnterpriseclip; "EnterpriseClipboardApi::Initialize fail"...
0x140096289  mov     r8d, 0BBh
0x14009628f  jmp     short loc_1400962ED
0x140096291  lea     rcx, aSrpapiDll; "srpapi.dll"
0x140096298  call    cs:__imp_LoadLibraryW
0x14009629e  mov     [rsi+48h], rax
0x1400962a2  test    rax, rax
0x1400962a5  jz      short loc_1400962C2
0x1400962a7  lea     rdx, aSrpgetenterpri_0; "SrpGetEnterpriseIds"
0x1400962ae  mov     rcx, rax; hModule
0x1400962b1  xor     ebx, ebx
0x1400962b3  call    cs:__imp_GetProcAddress
0x1400962b9  mov     [rsi+40h], rax
0x1400962bd  test    rax, rax
0x1400962c0  jnz     short loc_140096321
0x1400962c2  call    cs:__imp_GetLastError
0x1400962c8  mov     ebx, eax
0x1400962ca  test    eax, eax
0x1400962cc  jle     short loc_1400962D3
0x1400962ce  movzx   ebx, ax
0x1400962d1  or      ebx, ebp
0x1400962d3  test    ebx, ebx
0x1400962d5  jns     short loc_140096321
0x1400962d7  lea     rcx, [rsi+40h]; this
0x1400962db  call    ?Terminate@RdpEdpSrpApi@@AEAAJXZ; RdpEdpSrpApi::Terminate(void)
0x1400962e0  lea     rax, aRdpedpsrpapiIn; "RdpEdpSrpApi::Initialize failed. hr[0x%"...
0x1400962e7  mov     r8d, 0C1h; int
0x1400962ed  mov     dword ptr [rsp+68h+var_30], ebx; char
0x1400962f1  lea     r9, aRdpedppolicyma_4; "RdpEdpPolicyManager::InitializeInstance"
0x1400962f8  mov     [rsp+68h+pszFormat], rax; pszFormat
0x1400962fd  mov     edx, 200h; int
0x140096302  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x140096309  mov     qword ptr [rsp+68h+var_40], 0; int
0x140096312  mov     ecx, 3; int
0x140096317  mov     qword ptr [rsp+68h+var_48], rax; int
0x14009631c  call    TRC_TraceBufferW
0x140096321  mov     eax, ebx
0x140096323  add     rsp, 48h
0x140096327  pop     rdi
0x140096328  pop     rsi
0x140096329  pop     rbp
0x14009632a  pop     rbx
0x14009632b  retn
```
