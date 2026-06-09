# WinVerifyTrustThreadProc(_WINVERIFYTRUST_PARAMS *)

- ea: `0x14000c390`
- end: `0x14000c48f`
- name: `?WinVerifyTrustThreadProc@@YAKPEAU_WINVERIFYTRUST_PARAMS@@@Z`
- size: `255`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c390`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c414`
- `KERNEL32!GetProcAddress` at `0x14000c414`
- `KERNEL32!FreeLibrary` at `0x14000c464`
- `KERNEL32!FreeLibrary` at `0x14000c464`
- `KERNEL32!LoadLibraryExW` at `0x14000c3d9`
- `KERNEL32!LoadLibraryExW` at `0x14000c3d9`
- `KERNEL32!GetLastError` at `0x14000c3ed`
- `KERNEL32!GetLastError` at `0x14000c439`
- `KERNEL32!GetLastError` at `0x14000c3ed`
- `KERNEL32!GetLastError` at `0x14000c439`
- `ole32!CoInitialize` at `0x14000c3a4`
- `ole32!CoInitialize` at `0x14000c3a4`
- `ole32!CoUninitialize` at `0x14000c470`
- `ole32!CoUninitialize` at `0x14000c470`

## string_xrefs

- `0x14000c3d2`: `WinTrust.Dll`

## pseudocode

```c
__int64 __fastcall WinVerifyTrustThreadProc(_QWORD *Parameter)
{
  int v2; // ebx
  HMODULE Library; // rdi
  signed int v4; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax

  v2 = CoInitialize(0);
  if ( v2 >= 0 )
  {
    Library = (HMODULE)_InterlockedCompareExchange64(&qword_140017858, 0, 0);
    if ( Library || (Library = LoadLibraryExW(L"WinTrust.Dll", 0, 0x800u)) != 0 )
    {
      ProcAddress = GetProcAddress(Library, "WinVerifyTrust");
      if ( ProcAddress )
      {
        v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(*Parameter, Parameter[1], Parameter[2]);
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( _InterlockedCompareExchange64(&qword_140017858, (signed __int64)Library, 0) )
        FreeLibrary(Library);
    }
    else
    {
      v4 = GetLastError();
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
    }
    CoUninitialize();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000c390  mov     [rsp+arg_0], rbx
0x14000c395  mov     [rsp+arg_8], rsi
0x14000c39a  push    rdi
0x14000c39b  sub     rsp, 20h
0x14000c39f  mov     rsi, rcx
0x14000c3a2  xor     ecx, ecx; pvReserved
0x14000c3a4  call    cs:__imp_CoInitialize
0x14000c3ab  nop     dword ptr [rax+rax+00h]
0x14000c3b0  mov     ebx, eax
0x14000c3b2  test    eax, eax
0x14000c3b4  js      loc_14000C47C
0x14000c3ba  xor     edx, edx; hFile
0x14000c3bc  xor     eax, eax
0x14000c3be  lock cmpxchg cs:qword_140017858, rdx
0x14000c3c7  mov     rdi, rax
0x14000c3ca  jnz     short loc_14000C40A
0x14000c3cc  mov     r8d, 800h; dwFlags
0x14000c3d2  lea     rcx, aWintrustDll_0; "WinTrust.Dll"
0x14000c3d9  call    cs:__imp_LoadLibraryExW
0x14000c3e0  nop     dword ptr [rax+rax+00h]
0x14000c3e5  mov     rdi, rax
0x14000c3e8  test    rax, rax
0x14000c3eb  jnz     short loc_14000C40A
0x14000c3ed  call    cs:__imp_GetLastError
0x14000c3f4  nop     dword ptr [rax+rax+00h]
0x14000c3f9  mov     ebx, eax
0x14000c3fb  test    eax, eax
0x14000c3fd  jle     short loc_14000C470
0x14000c3ff  movzx   ebx, ax
0x14000c402  or      ebx, 80070000h
0x14000c408  jmp     short loc_14000C470
0x14000c40a  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x14000c411  mov     rcx, rdi; hModule
0x14000c414  call    cs:__imp_GetProcAddress
0x14000c41b  nop     dword ptr [rax+rax+00h]
0x14000c420  test    rax, rax
0x14000c423  jz      short loc_14000C439
0x14000c425  mov     r8, [rsi+10h]
0x14000c429  mov     rdx, [rsi+8]
0x14000c42d  mov     rcx, [rsi]
0x14000c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c435  mov     ebx, eax
0x14000c437  jmp     short loc_14000C454
0x14000c439  call    cs:__imp_GetLastError
0x14000c440  nop     dword ptr [rax+rax+00h]
0x14000c445  mov     ebx, eax
0x14000c447  test    eax, eax
0x14000c449  jle     short loc_14000C454
0x14000c44b  movzx   ebx, ax
0x14000c44e  or      ebx, 80070000h
0x14000c454  xor     eax, eax
0x14000c456  lock cmpxchg cs:qword_140017858, rdi
0x14000c45f  jz      short loc_14000C470
0x14000c461  mov     rcx, rdi; hLibModule
0x14000c464  call    cs:__imp_FreeLibrary
0x14000c46b  nop     dword ptr [rax+rax+00h]
0x14000c470  call    cs:__imp_CoUninitialize
0x14000c477  nop     dword ptr [rax+rax+00h]
0x14000c47c  mov     rsi, [rsp+28h+arg_8]
0x14000c481  mov     eax, ebx
0x14000c483  mov     rbx, [rsp+28h+arg_0]
0x14000c488  add     rsp, 20h
0x14000c48c  pop     rdi
0x14000c48d  retn
```
