# GetRemoteMscoreeBaseAddress(void *,uchar * *)

- ea: `0x18002fa08`
- end: `0x18002fd28`
- name: `?GetRemoteMscoreeBaseAddress@@YAJPEAXPEAPEAE@Z`
- size: `800`
- prototype: `__int64 __fastcall(void *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ff24`

## callees

- `0x18000d434`
- `0x18000d8f0`
- `0x180028c04`
- `0x180028cb8`
- `0x18002a7c8`
- `0x18002f908`
- `0x18002fa08`
- `0x180041ac0`
- `0x180045020`
- `0x180045030`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002fa89`
- `KERNEL32!GetProcAddress` at `0x18002faa5`
- `KERNEL32!GetProcAddress` at `0x18002fac9`
- `KERNEL32!GetProcAddress` at `0x18002fbf2`
- `KERNEL32!GetProcAddress` at `0x18002fa89`
- `KERNEL32!GetProcAddress` at `0x18002faa5`
- `KERNEL32!GetProcAddress` at `0x18002fac9`
- `KERNEL32!GetProcAddress` at `0x18002fbf2`
- `KERNEL32!GetModuleFileNameW` at `0x18002fc2f`
- `KERNEL32!GetModuleFileNameW` at `0x18002fc2f`
- `KERNEL32!LoadLibraryW` at `0x18002fa60`
- `KERNEL32!LoadLibraryW` at `0x18002fa60`
- `KERNEL32!GetCurrentProcess` at `0x18002fae8`
- `KERNEL32!GetCurrentProcess` at `0x18002fae8`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18002fb36`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18002fb36`
- `KERNEL32!GetSystemDirectoryW` at `0x18002fbb0`
- `KERNEL32!GetSystemDirectoryW` at `0x18002fbb0`

## string_xrefs

- `0x18002fa59`: `kernel32.dll`
- `0x18002fbe8`: `GetSystemWow64DirectoryW`
- `0x18002fc39`: `mscoree.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetRemoteMscoreeBaseAddress(void *a1, unsigned __int8 **a2)
{
  DWORD PidFromHandleWorker; // r14d
  HMODULE LibraryW; // rbx
  FARPROC ProcAddress; // r15
  FARPROC v8; // r13
  FARPROC v9; // rax
  unsigned int (__fastcall *v10)(HANDLE, int *); // rdi
  HANDLE CurrentProcess; // rax
  unsigned int LastError; // ebx
  HANDLE Toolhelp32Snapshot; // r14
  UINT SystemDirectoryW; // eax
  size_t v15; // rsi
  unsigned int v16; // edi
  FARPROC v17; // rax
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v20; // [rsp+28h] [rbp-D8h] BYREF
  BOOL v21; // [rsp+30h] [rbp-D0h]
  HMODULE v22; // [rsp+38h] [rbp-C8h] BYREF
  BOOL v23; // [rsp+40h] [rbp-C0h]
  HMODULE hModule; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[20]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int8 *v27; // [rsp+68h] [rbp-98h]
  wchar_t String1[256]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String2[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t v30[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR Buffer[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  WCHAR Filename[264]; // [rsp+8B0h] [rbp+7B0h] BYREF

  *a2 = 0;
  PidFromHandleWorker = GetPidFromHandleWorker(a1);
  if ( !PidFromHandleWorker )
    return 2147942487LL;
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v22 = LibraryW;
  v23 = LibraryW != 0;
  ProcAddress = GetProcAddress(LibraryW, "Module32FirstW");
  if ( ProcAddress )
  {
    v8 = GetProcAddress(LibraryW, "Module32NextW");
    if ( v8 )
    {
      v19 = 0;
      v18 = 0;
      v9 = GetProcAddress(LibraryW, "IsWow64Process");
      v10 = (unsigned int (__fastcall *)(HANDLE, int *))v9;
      if ( v9 )
      {
        if ( !((unsigned int (__fastcall *)(void *, int *))v9)(a1, &v19)
          || (CurrentProcess = GetCurrentProcess(), !v10(CurrentProcess, &v18)) )
        {
          LastError = HRESULT_FROM_GetLastError();
LABEL_29:
          Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v22);
          return LastError;
        }
        if ( v19 != v18 )
        {
          LastError = 1;
          goto LABEL_29;
        }
      }
      hModule = g_hShimMod;
      Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, PidFromHandleWorker);
      v20 = Toolhelp32Snapshot;
      v21 = Toolhelp32Snapshot != (HANDLE)-1LL;
      memset_thunk_772440563353939046(v26, 0, 0x434u);
      if ( Toolhelp32Snapshot == (HANDLE)-1LL )
      {
        Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v20);
        LastError = -2147467259;
        goto LABEL_29;
      }
      v25 = 1080;
      if ( !((unsigned int (__fastcall *)(HANDLE, int *))ProcAddress)(Toolhelp32Snapshot, &v25) )
      {
LABEL_27:
        Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v20);
        Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v22);
        return 1;
      }
      SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
      v15 = SystemDirectoryW;
      if ( SystemDirectoryW )
      {
        v16 = 0;
        memset_thunk_772440563353939046(v30, 0, 0x208u);
        v17 = GetProcAddress(LibraryW, "GetSystemWow64DirectoryW");
        if ( v17 )
        {
          v16 = ((__int64 (__fastcall *)(wchar_t *, __int64))v17)(v30, 260);
          if ( !v16 )
          {
            LastError = HRESULT_FROM_GetLastError();
            if ( LastError != -2147024776 )
              goto LABEL_16;
          }
        }
        if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
        {
          while ( wcsicmp(String1, L"mscoree.dll")
               || wcsnicmp(Buffer, String2, v15) && (!v16 || wcsnicmp(v30, String2, v16)) && wcsicmp(Filename, String2) )
          {
            if ( !((unsigned int (__fastcall *)(HANDLE, int *))v8)(Toolhelp32Snapshot, &v25) )
              goto LABEL_27;
          }
          *a2 = v27;
          Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v20);
          LastError = 0;
          goto LABEL_29;
        }
      }
      LastError = HRESULT_FROM_GetLastError();
LABEL_16:
      Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v20);
      goto LABEL_29;
    }
  }
  Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v22);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18002fa08  mov     [rsp-8+arg_10], rbx
0x18002fa0d  push    rbp
0x18002fa0e  push    rsi
0x18002fa0f  push    rdi
0x18002fa10  push    r12
0x18002fa12  push    r13
0x18002fa14  push    r14
0x18002fa16  push    r15
0x18002fa18  lea     rbp, [rsp-9D0h]
0x18002fa20  sub     rsp, 0AD0h
0x18002fa27  mov     rax, cs:__security_cookie
0x18002fa2e  xor     rax, rsp
0x18002fa31  mov     [rbp+0A00h+var_40], rax
0x18002fa38  mov     r12, rdx
0x18002fa3b  mov     rsi, rcx
0x18002fa3e  xor     edi, edi
0x18002fa40  mov     [rdx], rdi
0x18002fa43  call    ?GetPidFromHandleWorker@@YAKPEAX@Z; GetPidFromHandleWorker(void *)
0x18002fa48  mov     r14d, eax
0x18002fa4b  test    eax, eax
0x18002fa4d  jnz     short loc_18002FA59
0x18002fa4f  mov     eax, 80070057h
0x18002fa54  jmp     loc_18002FCFE
0x18002fa59  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18002fa60  call    cs:__imp_LoadLibraryW
0x18002fa66  mov     rbx, rax
0x18002fa69  mov     [rsp+0B00h+var_AC8], rax
0x18002fa6e  mov     eax, edi
0x18002fa70  mov     ecx, 1
0x18002fa75  test    rbx, rbx
0x18002fa78  cmovnz  eax, ecx
0x18002fa7b  mov     [rsp+0B00h+var_AC0], eax
0x18002fa7f  lea     rdx, aModule32firstw; "Module32FirstW"
0x18002fa86  mov     rcx, rbx; hModule
0x18002fa89  call    cs:__imp_GetProcAddress
0x18002fa8f  mov     r15, rax
0x18002fa92  test    rax, rax
0x18002fa95  jz      loc_18002FCEF
0x18002fa9b  lea     rdx, aModule32nextw; "Module32NextW"
0x18002faa2  mov     rcx, rbx; hModule
0x18002faa5  call    cs:__imp_GetProcAddress
0x18002faab  mov     r13, rax
0x18002faae  test    rax, rax
0x18002fab1  jz      loc_18002FCEF
0x18002fab7  mov     [rsp+0B00h+var_ADC], edi
0x18002fabb  mov     [rsp+0B00h+var_AE0], edi
0x18002fabf  lea     rdx, aIswow64process; "IsWow64Process"
0x18002fac6  mov     rcx, rbx; hModule
0x18002fac9  call    cs:__imp_GetProcAddress
0x18002facf  mov     rdi, rax
0x18002fad2  test    rax, rax
0x18002fad5  jz      short loc_18002FB22
0x18002fad7  lea     rdx, [rsp+0B00h+var_ADC]
0x18002fadc  mov     rcx, rsi
0x18002fadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fae4  test    eax, eax
0x18002fae6  jz      short loc_18002FB02
0x18002fae8  call    cs:__imp_GetCurrentProcess
0x18002faee  mov     rcx, rax
0x18002faf1  lea     rdx, [rsp+0B00h+var_AE0]
0x18002faf6  mov     rax, rdi
0x18002faf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fafe  test    eax, eax
0x18002fb00  jnz     short loc_18002FB0E
0x18002fb02  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002fb07  mov     ebx, eax
0x18002fb09  jmp     loc_18002FCE1
0x18002fb0e  mov     eax, [rsp+0B00h+var_AE0]
0x18002fb12  cmp     [rsp+0B00h+var_ADC], eax
0x18002fb16  jz      short loc_18002FB22
0x18002fb18  mov     ebx, 1
0x18002fb1d  jmp     loc_18002FCE1
0x18002fb22  mov     rax, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimMod
0x18002fb29  mov     [rsp+0B00h+hModule], rax
0x18002fb2e  mov     edx, r14d; th32ProcessID
0x18002fb31  mov     ecx, 8; dwFlags
0x18002fb36  call    cs:__imp_CreateToolhelp32Snapshot
0x18002fb3c  mov     r14, rax
0x18002fb3f  mov     [rsp+0B00h+var_AD8], rax
0x18002fb44  xor     ecx, ecx
0x18002fb46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fb4a  lea     eax, [rcx+1]
0x18002fb4d  cmovnz  ecx, eax
0x18002fb50  mov     [rsp+0B00h+var_AD0], ecx
0x18002fb54  xor     edx, edx; Val
0x18002fb56  mov     r8d, 434h; Size
0x18002fb5c  lea     rcx, [rsp+0B00h+var_AAC]; void *
0x18002fb61  call    memset$thunk$772440563353939046
0x18002fb66  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002fb6a  jnz     short loc_18002FB80
0x18002fb6c  lea     rcx, [rsp+0B00h+var_AD8]
0x18002fb71  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18002fb76  mov     ebx, 80004005h
0x18002fb7b  jmp     loc_18002FCE1
0x18002fb80  mov     [rsp+0B00h+var_AB0], 438h
0x18002fb88  lea     rdx, [rsp+0B00h+var_AB0]
0x18002fb8d  mov     rcx, r14
0x18002fb90  mov     rax, r15
0x18002fb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb98  test    eax, eax
0x18002fb9a  jz      loc_18002FCB0
0x18002fba0  mov     r15d, 104h
0x18002fba6  mov     edx, r15d; uSize
0x18002fba9  lea     rcx, [rbp+0A00h+Buffer]; lpBuffer
0x18002fbb0  call    cs:__imp_GetSystemDirectoryW
0x18002fbb6  mov     esi, eax
0x18002fbb8  test    eax, eax
0x18002fbba  jnz     short loc_18002FBD2
0x18002fbbc  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002fbc1  mov     ebx, eax
0x18002fbc3  lea     rcx, [rsp+0B00h+var_AD8]
0x18002fbc8  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18002fbcd  jmp     loc_18002FCE1
0x18002fbd2  xor     edi, edi
0x18002fbd4  xor     edx, edx; Val
0x18002fbd6  mov     r8d, 208h; Size
0x18002fbdc  lea     rcx, [rbp+0A00h+var_670]; void *
0x18002fbe3  call    memset$thunk$772440563353939046
0x18002fbe8  lea     rdx, aGetsystemwow64; "GetSystemWow64DirectoryW"
0x18002fbef  mov     rcx, rbx; hModule
0x18002fbf2  call    cs:__imp_GetProcAddress
0x18002fbf8  test    rax, rax
0x18002fbfb  jz      short loc_18002FC20
0x18002fbfd  mov     edx, r15d
0x18002fc00  lea     rcx, [rbp+0A00h+var_670]
0x18002fc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc0c  mov     edi, eax
0x18002fc0e  test    eax, eax
0x18002fc10  jnz     short loc_18002FC20
0x18002fc12  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002fc17  mov     ebx, eax
0x18002fc19  cmp     eax, 80070078h
0x18002fc1e  jnz     short loc_18002FBC3
0x18002fc20  mov     r8d, r15d; nSize
0x18002fc23  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18002fc2a  mov     rcx, [rsp+0B00h+hModule]; hModule
0x18002fc2f  call    cs:__imp_GetModuleFileNameW
0x18002fc35  test    eax, eax
0x18002fc37  jz      short loc_18002FBBC
0x18002fc39  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x18002fc40  lea     rcx, [rbp+0A00h+String1]; String1
0x18002fc44  call    _wcsicmp
0x18002fc49  test    eax, eax
0x18002fc4b  jnz     short loc_18002FC9C
0x18002fc4d  mov     r8, rsi; MaxCount
0x18002fc50  lea     rdx, [rbp+0A00h+String2]; String2
0x18002fc57  lea     rcx, [rbp+0A00h+Buffer]; String1
0x18002fc5e  call    _wcsnicmp
0x18002fc63  test    eax, eax
0x18002fc65  jz      short loc_18002FCCC
0x18002fc67  test    edi, edi
0x18002fc69  jz      short loc_18002FC85
0x18002fc6b  mov     r8d, edi; MaxCount
0x18002fc6e  lea     rdx, [rbp+0A00h+String2]; String2
0x18002fc75  lea     rcx, [rbp+0A00h+var_670]; String1
0x18002fc7c  call    _wcsnicmp
0x18002fc81  test    eax, eax
0x18002fc83  jz      short loc_18002FCCC
0x18002fc85  lea     rdx, [rbp+0A00h+String2]; String2
0x18002fc8c  lea     rcx, [rbp+0A00h+Filename]; String1
0x18002fc93  call    _wcsicmp
0x18002fc98  test    eax, eax
0x18002fc9a  jz      short loc_18002FCCC
0x18002fc9c  lea     rdx, [rsp+0B00h+var_AB0]
0x18002fca1  mov     rcx, r14
0x18002fca4  mov     rax, r13
0x18002fca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcac  test    eax, eax
0x18002fcae  jnz     short loc_18002FC39
0x18002fcb0  lea     rcx, [rsp+0B00h+var_AD8]
0x18002fcb5  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18002fcba  nop
0x18002fcbb  lea     rcx, [rsp+0B00h+var_AC8]
0x18002fcc0  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002fcc5  mov     eax, 1
0x18002fcca  jmp     short loc_18002FCFE
0x18002fccc  mov     rax, [rsp+0B00h+var_A98]
0x18002fcd1  mov     [r12], rax
0x18002fcd5  lea     rcx, [rsp+0B00h+var_AD8]
0x18002fcda  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18002fcdf  xor     ebx, ebx
0x18002fce1  lea     rcx, [rsp+0B00h+var_AC8]
0x18002fce6  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002fceb  mov     eax, ebx
0x18002fced  jmp     short loc_18002FCFE
0x18002fcef  lea     rcx, [rsp+0B00h+var_AC8]
0x18002fcf4  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002fcf9  mov     eax, 80004001h
0x18002fcfe  mov     rcx, [rbp+0A00h+var_40]
0x18002fd05  xor     rcx, rsp; StackCookie
0x18002fd08  call    __security_check_cookie
0x18002fd0d  mov     rbx, [rsp+0B00h+arg_10]
0x18002fd15  add     rsp, 0AD0h
0x18002fd1c  pop     r15
0x18002fd1e  pop     r14
0x18002fd20  pop     r13
0x18002fd22  pop     r12
0x18002fd24  pop     rdi
0x18002fd25  pop     rsi
0x18002fd26  pop     rbp
0x18002fd27  retn
```
