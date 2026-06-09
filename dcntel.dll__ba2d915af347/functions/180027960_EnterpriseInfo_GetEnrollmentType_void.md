# EnterpriseInfo::GetEnrollmentType(void)

- ea: `0x180027960`
- end: `0x180027b44`
- name: `?GetEnrollmentType@EnterpriseInfo@@AEBAIXZ`
- size: `484`
- prototype: `unsigned int __fastcall(EnterpriseInfo *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x180027960`
- `0x18002a760`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027990`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800279b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800279b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b2a`

## string_xrefs

- `0x180027989`: `dmenrollengine.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnterpriseInfo::GetEnrollmentType(EnterpriseInfo *this, unsigned __int16 a2, unsigned __int16 a3)
{
  unsigned int v3; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  signed int v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  signed int v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  signed int LastError; // eax
  int v19; // edx
  unsigned int v20; // r8d
  const int *v21; // [rsp+20h] [rbp-10h] BYREF
  HMODULE v22; // [rsp+28h] [rbp-8h]
  unsigned int v23; // [rsp+58h] [rbp+28h] BYREF
  __int64 v24; // [rsp+60h] [rbp+30h] BYREF
  __int64 v25; // [rsp+68h] [rbp+38h] BYREF

  v3 = -1;
  if ( IsWindowsVersionOrGreaterEx((unsigned __int16)this, a2, a3, 0x3839u) )
  {
    Library = LoadLibraryExW(L"dmenrollengine.dll", 0, 0x800u);
    v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    v22 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, (LPCSTR)0xA);
      if ( ProcAddress )
      {
        v24 = 0;
        v7 = ((__int64 (__fastcall *)(__int64))ProcAddress)(v6);
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 32LL))(v7, 222306401, &v24);
        v9 = v24;
        if ( v8 >= 0 && v24 )
        {
          v25 = 0;
          while ( 1 )
          {
            if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 24LL))(v9, &v25) < 0 )
            {
              v10 = v25;
LABEL_15:
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              v9 = v24;
              goto LABEL_18;
            }
            v10 = v25;
            if ( !v25 )
              goto LABEL_15;
            v23 = 0;
            if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 48LL))(v25, &v23) >= 0 )
              break;
            v9 = v24;
          }
          v3 = v23;
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
          if ( v22 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v21) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v19, v20);
            JUMPOUT(0x180027B43LL);
          }
        }
        else
        {
LABEL_18:
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
          if ( v22 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v21) )
          {
            v15 = GetLastError();
            if ( v15 > 0 )
              v15 = (unsigned __int16)v15 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
            __debugbreak();
          }
        }
      }
      else
      {
        v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( v22 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v21) )
        {
          v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
          __debugbreak();
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180027960  push    rbp
0x180027962  push    rbx
0x180027963  push    rsi
0x180027964  mov     rbp, rsp
0x180027967  sub     rsp, 30h
0x18002796b  or      ebx, 0FFFFFFFFh
0x18002796e  mov     r9d, 3839h; unsigned __int16
0x180027974  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180027979  test    al, al
0x18002797b  jz      loc_180027AEC
0x180027981  xor     edx, edx; hFile
0x180027983  mov     r8d, 800h; dwFlags
0x180027989  lea     rcx, aDmenrollengine; "dmenrollengine.dll"
0x180027990  call    cs:__imp_LoadLibraryExW
0x180027996  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002799d  mov     [rbp+var_10], rsi
0x1800279a1  mov     [rbp+var_8], rax
0x1800279a5  test    rax, rax
0x1800279a8  jz      loc_180027AEC
0x1800279ae  mov     edx, 0Ah; lpProcName
0x1800279b3  mov     rcx, rax; hModule
0x1800279b6  call    cs:__imp_GetProcAddress
0x1800279bc  test    rax, rax
0x1800279bf  jnz     short loc_1800279E5
0x1800279c1  mov     [rbp+var_10], rsi
0x1800279c5  cmp     [rbp+var_8], rax
0x1800279c9  jz      loc_180027AEC
0x1800279cf  lea     rcx, [rbp+var_10]
0x1800279d3  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800279d8  test    al, al
0x1800279da  jz      loc_180027AF6
0x1800279e0  jmp     loc_180027AEC
0x1800279e5  mov     [rbp+arg_10], 0
0x1800279ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279f2  mov     rcx, rax
0x1800279f5  mov     rax, [rax]
0x1800279f8  lea     r8, [rbp+arg_10]
0x1800279fc  mov     edx, 0D402061h
0x180027a01  mov     rax, [rax+20h]
0x180027a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a0a  mov     rcx, [rbp+arg_10]
0x180027a0e  test    eax, eax
0x180027a10  js      short loc_180027A77
0x180027a12  test    rcx, rcx
0x180027a15  jz      short loc_180027A77
0x180027a17  mov     [rbp+arg_18], 0
0x180027a1f  jmp     short loc_180027A49
0x180027a21  mov     rcx, [rbp+arg_18]
0x180027a25  test    rcx, rcx
0x180027a28  jz      short loc_180027A61
0x180027a2a  mov     [rbp+arg_8], 0
0x180027a31  mov     rax, [rcx]
0x180027a34  lea     rdx, [rbp+arg_8]
0x180027a38  mov     rax, [rax+30h]
0x180027a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a41  test    eax, eax
0x180027a43  jns     short loc_180027AA3
0x180027a45  mov     rcx, [rbp+arg_10]
0x180027a49  mov     rax, [rcx]
0x180027a4c  lea     rdx, [rbp+arg_18]
0x180027a50  mov     rax, [rax+18h]
0x180027a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a59  test    eax, eax
0x180027a5b  jns     short loc_180027A21
0x180027a5d  mov     rcx, [rbp+arg_18]
0x180027a61  test    rcx, rcx
0x180027a64  jz      short loc_180027A73
0x180027a66  mov     rax, [rcx]
0x180027a69  mov     rax, [rax+10h]
0x180027a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a72  nop
0x180027a73  mov     rcx, [rbp+arg_10]
0x180027a77  test    rcx, rcx
0x180027a7a  jz      short loc_180027A89
0x180027a7c  mov     rax, [rcx]
0x180027a7f  mov     rax, [rax+10h]
0x180027a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a88  nop
0x180027a89  mov     [rbp+var_10], rsi
0x180027a8d  cmp     [rbp+var_8], 0
0x180027a92  jz      short loc_180027AEC
0x180027a94  lea     rcx, [rbp+var_10]
0x180027a98  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180027a9d  test    al, al
0x180027a9f  jz      short loc_180027B10
0x180027aa1  jmp     short loc_180027AEC
0x180027aa3  mov     ebx, [rbp+arg_8]
0x180027aa6  mov     rcx, [rbp+arg_18]
0x180027aaa  test    rcx, rcx
0x180027aad  jz      short loc_180027ABC
0x180027aaf  mov     rax, [rcx]
0x180027ab2  mov     rax, [rax+10h]
0x180027ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027abb  nop
0x180027abc  mov     rcx, [rbp+arg_10]
0x180027ac0  test    rcx, rcx
0x180027ac3  jz      short loc_180027AD2
0x180027ac5  mov     rax, [rcx]
0x180027ac8  mov     rax, [rax+10h]
0x180027acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad1  nop
0x180027ad2  mov     [rbp+var_10], rsi
0x180027ad6  cmp     [rbp+var_8], 0
0x180027adb  jz      short loc_180027AEC
0x180027add  lea     rcx, [rbp+var_10]
0x180027ae1  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180027ae6  test    al, al
0x180027ae8  jz      short loc_180027B2A
0x180027aea  jmp     short $+2
0x180027aec  mov     eax, ebx
0x180027aee  add     rsp, 30h
0x180027af2  pop     rsi
0x180027af3  pop     rbx
0x180027af4  pop     rbp
0x180027af5  retn
0x180027af6  call    cs:__imp_GetLastError
0x180027afc  test    eax, eax
0x180027afe  jle     short loc_180027B08
0x180027b00  movzx   eax, ax
0x180027b03  or      eax, 80070000h
0x180027b08  mov     ecx, eax; this
0x180027b0a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180027b0f  int     3; Trap to Debugger
0x180027b10  call    cs:__imp_GetLastError
0x180027b16  test    eax, eax
0x180027b18  jle     short loc_180027B22
0x180027b1a  movzx   eax, ax
0x180027b1d  or      eax, 80070000h
0x180027b22  mov     ecx, eax; this
0x180027b24  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180027b29  int     3; Trap to Debugger
0x180027b2a  call    cs:__imp_GetLastError
0x180027b30  test    eax, eax
0x180027b32  jle     short loc_180027B3C
0x180027b34  movzx   eax, ax
0x180027b37  or      eax, 80070000h
0x180027b3c  mov     ecx, eax; this
0x180027b3e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
