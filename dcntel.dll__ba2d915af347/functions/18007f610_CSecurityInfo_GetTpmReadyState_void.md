# CSecurityInfo::GetTpmReadyState(void)

- ea: `0x18007f610`
- end: `0x18007f70c`
- name: `?GetTpmReadyState@CSecurityInfo@@QEBAEXZ`
- size: `252`
- prototype: `unsigned __int8 __fastcall(CSecurityInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x18007f610`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f63c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f63c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f662`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f6f2`

## string_xrefs

- `0x18007f635`: `TpmCoreProvisioning.dll`
- `0x18007f658`: `TpmIsReadyInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int8 __fastcall CSecurityInfo::GetTpmReadyState(CSecurityInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v3; // ebx
  signed int v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  signed int LastError; // eax
  int v9; // edx
  unsigned int v10; // r8d
  const int *v11; // [rsp+20h] [rbp-10h] BYREF
  HMODULE v12; // [rsp+28h] [rbp-8h]
  char v13; // [rsp+48h] [rbp+18h] BYREF
  int v14; // [rsp+50h] [rbp+20h] BYREF

  v13 = 0;
  v14 = 0;
  Library = LoadLibraryExW(L"TpmCoreProvisioning.dll", 0, 0x800u);
  v11 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v12 = Library;
  if ( !Library )
    return -1;
  ProcAddress = GetProcAddress(Library, "TpmIsReadyInformation");
  if ( !ProcAddress )
  {
    v11 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v12 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v11) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v9, v10);
      JUMPOUT(0x18007F70BLL);
    }
    return -1;
  }
  v3 = ((__int64 (__fastcall *)(char *, int *))ProcAddress)(&v13, &v14);
  v11 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v12 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v11) )
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    __debugbreak();
  }
  if ( v3 < 0 )
    return -1;
  if ( v13 )
    return 2 - (v14 != 0);
  else
    return 0;
}

```

## disassembly

```asm
0x18007f610  mov     [rsp-8+arg_0], rbx
0x18007f615  mov     [rsp-8+arg_18], rsi
0x18007f61a  push    rbp
0x18007f61b  mov     rbp, rsp
0x18007f61e  sub     rsp, 30h
0x18007f622  mov     [rbp+arg_8], 0
0x18007f626  mov     [rbp+arg_10], 0
0x18007f62d  xor     edx, edx; hFile
0x18007f62f  mov     r8d, 800h; dwFlags
0x18007f635  lea     rcx, aTpmcoreprovisi_1; "TpmCoreProvisioning.dll"
0x18007f63c  call    cs:__imp_LoadLibraryExW
0x18007f642  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18007f649  mov     [rbp+var_10], rsi
0x18007f64d  mov     [rbp+var_8], rax
0x18007f651  test    rax, rax
0x18007f654  jnz     short loc_18007F658
0x18007f656  jmp     short loc_18007F6B1
0x18007f658  lea     rdx, aTpmisreadyinfo; "TpmIsReadyInformation"
0x18007f65f  mov     rcx, rax; hModule
0x18007f662  call    cs:__imp_GetProcAddress
0x18007f668  test    rax, rax
0x18007f66b  jnz     short loc_18007F686
0x18007f66d  mov     [rbp+var_10], rsi
0x18007f671  cmp     [rbp+var_8], rax
0x18007f675  jz      short loc_18007F6B1
0x18007f677  lea     rcx, [rbp+var_10]
0x18007f67b  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007f680  test    al, al
0x18007f682  jz      short loc_18007F6F2
0x18007f684  jmp     short loc_18007F6B1
0x18007f686  lea     rdx, [rbp+arg_10]
0x18007f68a  lea     rcx, [rbp+arg_8]
0x18007f68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f693  mov     ebx, eax
0x18007f695  mov     [rbp+var_10], rsi
0x18007f699  cmp     [rbp+var_8], 0
0x18007f69e  jz      short loc_18007F6AD
0x18007f6a0  lea     rcx, [rbp+var_10]
0x18007f6a4  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007f6a9  test    al, al
0x18007f6ab  jz      short loc_18007F6D8
0x18007f6ad  test    ebx, ebx
0x18007f6af  jns     short loc_18007F6B5
0x18007f6b1  mov     al, 0FFh
0x18007f6b3  jmp     short loc_18007F6C8
0x18007f6b5  cmp     [rbp+arg_8], 0
0x18007f6b9  jnz     short loc_18007F6BF
0x18007f6bb  xor     al, al
0x18007f6bd  jmp     short loc_18007F6C8
0x18007f6bf  mov     eax, [rbp+arg_10]
0x18007f6c2  neg     eax
0x18007f6c4  sbb     al, al
0x18007f6c6  add     al, 2
0x18007f6c8  mov     rbx, [rsp+30h+arg_0]
0x18007f6cd  mov     rsi, [rsp+30h+arg_18]
0x18007f6d2  add     rsp, 30h
0x18007f6d6  pop     rbp
0x18007f6d7  retn
0x18007f6d8  call    cs:__imp_GetLastError
0x18007f6de  test    eax, eax
0x18007f6e0  jle     short loc_18007F6EA
0x18007f6e2  movzx   eax, ax
0x18007f6e5  or      eax, 80070000h
0x18007f6ea  mov     ecx, eax; this
0x18007f6ec  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007f6f1  int     3; Trap to Debugger
0x18007f6f2  call    cs:__imp_GetLastError
0x18007f6f8  test    eax, eax
0x18007f6fa  jle     short loc_18007F704
0x18007f6fc  movzx   eax, ax
0x18007f6ff  or      eax, 80070000h
0x18007f704  mov     ecx, eax; this
0x18007f706  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
